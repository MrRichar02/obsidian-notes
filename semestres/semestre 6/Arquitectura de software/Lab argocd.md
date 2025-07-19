portada

<div style="page-break-after: always;"></div>

## Introducción

El objetivo principal de este laboratorio fue familiarizarnos con **Kubernetes**, la filosofía **GitOps** y la herramienta de despliegue continuo **Argo CD**. Para ello, se proporcionó una aplicación sencilla desarrollada en **Spring Boot**, conectada a una base de datos **MySQL**.

Como primer paso, se construyó un clúster local utilizando **Minikube**, y se desplegaron manualmente diversos componentes mediante archivos YAML: la base de datos, la aplicación y un balanceador de carga. Esta etapa permitió comprender la estructura y funcionamiento básico de Kubernetes a través de su modelo declarativo.

Posteriormente, se integró **Argo CD** para automatizar el monitoreo y sincronización del estado del clúster con la configuración definida en un repositorio de Git. Esta herramienta permitió aplicar la filosofía GitOps, facilitando la gestión continua de la infraestructura como código.

En la fase final del laboratorio, se experimentó con el escalado horizontal de la aplicación, modificando la cantidad de réplicas directamente desde el repositorio y observando cómo **Argo CD detectaba y aplicaba automáticamente los cambios** en el entorno de ejecución.

Este informe documenta el proceso completo seguido durante el laboratorio, desde la preparación inicial del entorno, el despliegue de los servicios, la automatización con Argo CD, hasta la validación de la sincronización automática y pruebas de escalabilidad.

## Preparación Inicial del entorno

Como punto de partida para el laboratorio, se nos proporcionó una aplicación sencilla desarrollada en Spring Boot, cuyo propósito era implementar servicios RESTful aplicando el principio HATEOAS. Esta aplicación fue construida utilizando Maven y el JDK 11, y se integró con una base de datos MySQL para el almacenamiento persistente de datos.

Uno de los objetivos principales del laboratorio fue contenerizar tanto la aplicación como la base de datos, utilizando Docker, para luego desplegarlas en un entorno orquestado con Kubernetes. Para ello, se utilizó Minikube como clúster local de Kubernetes, y se proporcionaron archivos YAML que definían la infraestructura necesaria para ejecutar los distintos componentes en forma de pods: uno para la base de datos, otro para la aplicación, y uno adicional para el balanceador de carga que distribuye las peticiones entrantes entre las distintas instancias de la aplicación.

## Configuración de Argo CD

Para automatizar el proceso de despliegue y sincronización de los recursos en Kubernetes, se utilizó Argo CD, una herramienta GitOps que permite mantener el estado del cluster sincronizado con la configuración definida en un repositorio Git.

### Creación de repositorio

Como parte de la preparación, se creó un repositorio en GitHub que contiene tanto el código fuente de la aplicación Spring Boot como los archivos YAML necesarios para su despliegue. Para mantener una estructura organizada, se creó un directorio llamado `cluster/` en la raíz del proyecto. Dentro de este directorio se almacenaron todos los archivos YAML, facilitando su gestión y monitoreo desde Argo CD.
### Despliegue e instalación de Argocd

A continuación, se detallan los pasos ejecutados para instalar Argo CD en el clúster local de Minikube:

### Iniciar minikube

Iniciamos el cluster de minikube usando como driver a docker

```
minikube start --driver=docker --container-runtime=containerd
```

### Verificar la iniciación de los pods de minikube 

```
kubectl get pods -A
```

### Creamos el namespace para Argo CD

```
kubectl create namespace argocd
```

### Aplicamos el archivo para iniciar Argo CD

Aplicamos el archivo YAML que se proporciona en la documentación de Argo CD para instalarlo en el cluster

```
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

### Verificamos la iniciación de los pods en el namespace de Argo CD

```
kubectl get pods -n argocd
```

### Cargamos la imagen de mysql en minikube

Cargamos la imagen de MySQL, en este caso se utilizo la imagen con el tag :lts debido a que la imagen propuesta en la guía 5.7 presentaba errores en el entorno local

```
minikube image load mysql:lts
```

### Cargamos la imagen de la aplicación en minikube

```
minikube image load virtualvuelo-app
```

### Creamos el archivo de configuración de Argo CD

Se creó un archivo application.yml que define un recurso de tipo Application para Argo CD. Este archivo especifica:

El nombre que en este caso es virtualvuelo, se indica el namespace que es argocd.

Se define el source que es la fuente que Argo CD va a usar para comparar y mantener el estado del cluster, en este caso lo apuntamos al repositorio de GitHub creado anteriormente en el directorio cluster que es a donde movimos los archivos YAML proporcionados en la guía del laboratorio y le indicamos que debe seguir al `HEAD` esto para asegurar que tome los últimos cambios del repositorio. 

Definimos el destination aquí indicamos donde debe se va  a aplicar lo que observe en el repositorio del source, para este caso le definimos de destino el cluster local de minikube en el namespace default. 

Finalmente definimos el syncPolicy aquí le decimos a Argo CD que si se aplican cambios de manera manual al cluster se debe de regresar a los cambios definimos en el repositorio y que si se realiza un cambio en el repositorio se debe aplicar al cluster al momento de ser detectado.

### application.yml

```
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: virtualvuelo
  namespace: argocd
spec:
  project: default

  source:
    repoURL: https://github.com/MrRichar02/virtualvuelo.git
    targetRevision: HEAD
    path: cluster
  destination:
    server: https://kubernetes.default.svc
	namespace: default

  syncPolicy:
    automated:
      selfHeal: true
      prune: true
```

### Aplicamos el archivo application.yml

Aplicamos el archivo en el namespace de Argo CD

```
kubectl apply -n argocd -f application.yml
```

### Verificamos la creación de los pods 

```
kubectl get pods 
```

### Abrimos el service de virtualvuelo

```
minikube service virtualvuelo-service
```

## Escalabilidad 

Con el objetivo de evaluar el impacto del escalado horizontal de la aplicación, se realizaron pruebas utilizando la herramienta Apache JMeter, simulando una carga de 1.000 usuarios que acceden concurrentemente al endpoint /flight/listAll. En la base de datos se encuentra un único vuelo registrado, lo que permite enfocar las pruebas en el comportamiento del sistema frente al tráfico, más que en la complejidad de la respuesta.

Se evaluaron dos escenarios: uno con dos réplicas (configuración base del laboratorio) y otro con cuatro réplicas de la aplicación.
### Dos replicas 

Esta es la configuración predeterminada entregada en la guía del laboratorio. No fue necesario modificar el archivo de despliegue, únicamente se ejecutó la prueba desde JMeter. A continuación, se presenta el resultado obtenido:

<figure>
  <img src="Pasted image 20250705174354.png" alt="Descripción de la imagen" />
  <figcaption>Figura 1 Gráfico de resultado obtenido en jmeter con 2 replicas</figcaption>
</figure>

### Cuatro replicas 

Para incrementar el número de réplicas, se editó el archivo virtualvuelo-deployment.yml, cambiando el parámetro replicas de 2 a 4. Posteriormente, se realizó un commit y push al repositorio. Aproximadamente tres minutos después, Argo CD detectó y aplicó los cambios automáticamente, escalando el despliegue de la aplicación a cuatro instancias.

Una vez aplicado el cambio, se ejecutó nuevamente la prueba con la misma configuración de carga. El resultado fue el siguiente:

<figure>
  <img src="Pasted image 20250705175153.png" alt="Descripción de la imagen" />
  <figcaption>Figura 2 Gráfico de resultado obtenido en jmeter con 4 replicas</figcaption>
</figure>

## Monitoreo de la aplicación

Como actividad complementaria, se implementó una solución de monitoreo utilizando Prometheus y Grafana, con el fin de observar el comportamiento y estado de la aplicación desplegada en Kubernetes.

### Exposición de métricas desde Spring Boot
#### Agregamos una nueva dependencia al pom.xml 

Se añadió la dependencia de Micrometer Prometheus, que permite generar y exponer métricas en el formato requerido:

```
    <dependency>
      <groupId>io.micrometer</groupId>
      <artifactId>micrometer-registry-prometheus</artifactId>
    </dependency>
```

#### Configuración en el application.properties

Se habilitó el endpoint de métricas y se configuró la exposición de los endpoints relevantes:

```
management.metrics.tags.application=${spring.application.name}
management.endpoints.web.exposure.include=info,health,prometheus
management.endpoint.prometheus.enabled=true
```

Con esto, la aplicación comienza a exponer métricas en el endpoint:   `/actuator/prometheus`

### Configuración de Prometheus y Grafana (docker-compose)

Para visualizar estas métricas de forma local, se creó un archivo docker-compose.yml que define dos servicios: Prometheus y Grafana.

#### Archivo docker-compose.yml

```
services:
  prometheus:
    image: prom/prometheus:latest
    network_mode: host
    volumes:
        - ./prometheus/prometheus.yml:/etc/prometheus/prometheus.yml
  grafana:
    image: grafana/grafana:latest
    network_mode: host
    environment:
      GF_SECURITY_ADMIN_USER: admin
      GF_SECURITY_ADMIN_PASSWORD: admin
```

#### Archivo prometheus.yml

Prometheus necesita saber de dónde obtener las métricas. Para esto, se utiliza la IP del clúster de Minikube (por defecto 192.168.49.2) y el puerto expuesto por el Service de la aplicación. Este puerto puede variar con cada despliegue y se obtiene mediante el comando

```
minikube service virtualvuelo-service --url
```

El archivo prometheus.yml se ubicó en el directorio prometheus/ en la raíz del proyecto

```
scrape_configs:
  - job_name: 'spring-boot-monitoring-app'
    metrics_path: '/actuator/prometheus'
    static_configs:
      - targets: ['192.168.49.2:32514']
```

### Visualización en Grafana 

Iniciamos los dos servicios con:

```
docker compose up -d 
```

Con esto se crean los servicios sus rutas 

Prometheus: [http://localhost:9090](http://localhost:9090)
Grafana: [http://localhost:3000](http://localhost:3000)

#### Configuración del data source en Grafana

1. Iniciar sesión con usuario y contraseña: admin / admin.

2. Ir a Connections > Data sources.

3. Hacer clic en Add new data source y seleccionar Prometheus.

4. En el campo de conexión, ingresar: http://localhost:9090.

5. Hacer clic en Save & Test.

#### Importación de un dashboard

Para visualizar métricas relevantes de Spring Boot, se importó un dashboard predefinido desde Grafana Labs:

Dashboard utilizado: [Spring Boot 2.1 System Monitor](https://grafana.com/grafana/dashboards/11378-justai-system-monitor/)

Proceso:

1. Ir a Dashboards > New > Import.
2. Seleccionar el archivo .json descargado.
3. Elegir Prometheus como fuente de datos.
4. Clic en Import.

A continuación, se generó el siguiente dashboard con métricas en tiempo real de la aplicación:

#### Basic Statistics
<figure>
  <img src="Pasted image 20250706122259.png" alt="Descripción de la imagen" />
  <figcaption>Figura 3 Sección basic statistics del dashboard</figcaption>
</figure>
#### JVM Statistics - Heaps

<figure>
  <img src="Pasted image 20250706122347.png" alt="Descripción de la imagen" />
  <figcaption>Figura 4 Sección JVM statistics - heaps del dashboard</figcaption>
</figure>

#### JVM STatistics Threads/Buffers

<figure>
  <img src="Pasted image 20250706122448.png" alt="Descripción de la imagen" />
  <figcaption>Figura 5 Sección JVM statistics Threads/Buffers del dashboard</figcaption>
</figure>

#### JVM Statistics - GC
<figure>
  <img src="Pasted image 20250706122521.png" alt="Descripción de la imagen" />
  <figcaption>Figura 6 Sección JVM statistics - GC del dashboard</figcaption>
</figure>
#### HikariCP  Statistics
<figure>
  <img src="Pasted image 20250706122606.png" alt="Descripción de la imagen" />
  <figcaption>Figura 7 Sección HikariCP statistics - GC del dashboard</figcaption>
</figure>
#### Logback Statistics
<figure>
  <img src="Pasted image 20250706122642.png" alt="Descripción de la imagen" />
  <figcaption>Figura 8 Sección Logback statistics - GC del dashboard</figcaption>
</figure>

![[Pasted image 20250706122642.png|This is caption]]

## Conclusiones

El presente laboratorio permitió aplicar de manera práctica conceptos fundamentales de la arquitectura moderna de software, como la contenerización, orquestación, automatización de despliegues y monitoreo. A partir de una aplicación desarrollada en Spring Boot, se implementó un flujo completo de despliegue en un clúster de Kubernetes utilizando Minikube como entorno local.

Inicialmente, se trabajó con archivos YAML proporcionados por la guía del laboratorio para desplegar manualmente la aplicación y su base de datos en Kubernetes. Posteriormente, se integró Argo CD como herramienta GitOps, lo que permitió automatizar la gestión del estado del clúster con base en un repositorio Git, logrando que cualquier cambio en la configuración (como el número de réplicas) se propagara automáticamente al entorno de ejecución.

Además, se exploró la escalabilidad horizontal, modificando el número de réplicas de la aplicación y evaluando su impacto mediante pruebas de carga con Apache JMeter. Los resultados evidenciaron cómo Kubernetes y su balanceador de carga distribuyen eficientemente el tráfico entre múltiples instancias, mejorando la capacidad de respuesta bajo alta concurrencia.

Finalmente, se integraron herramientas de monitoreo como Prometheus y Grafana, permitiendo visualizar métricas clave de la aplicación en tiempo real. Esta integración refuerza la importancia de contar con observabilidad en sistemas distribuidos para garantizar su correcto funcionamiento y detectar posibles cuellos de botella.

En conslusión, este laboratorio ofreció una visión integral de cómo diseñar, desplegar, escalar y monitorear aplicaciones modernas utilizando tecnologías ampliamente utilizadas en la industria. 