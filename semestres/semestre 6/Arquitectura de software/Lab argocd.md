## Comando a realizar

### Iniciar minikube

```
minikube start --driver=docker --container-runtime=containerd
```

### Verificar la iniciación de los pods de minikube 

```
kubectl get pods -A
```

### Creamos el namespace para argocd

```
kubectl create namespace argocd
```

### Aplicamos el archivo para iniciar argocd

```
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

### Verificamos la iniciación de los pods en el namespace de argocd

```
kubectl get pods -n argocd
```
### Cargamos la imagen de mysql en minikube(Opcional)

```
minikube image load mysql
```

### Cargamos la imagen de la aplicación en minikube(Opcional)

```
minikube image load virtualvuelo-app
```

### Creamos dos archivos para configurar argocd respecto a nuestro repositorio de github

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

  syncPolicy:
    automated:
      selfHeal: true
      prune: true
```

### Kustomization.yaml

```
# cluster/kustomization.yaml
namespace: default
resources:
  - mysql-configmap.yml
  - mysql-deployment.yml
  - virtualvuelo-deployment.yml
```

### Aplicamos el archivo de application.yaml

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
