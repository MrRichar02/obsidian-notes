## Primera parte comprobar ley de enfriamiento de newton

$\large{T = \text{Temperatura}}$ 
$\large{T_m = \text{Temperatura de ambiente}}$ 
$\large{r = \text{Constante de proporcionalidad}}$ 

$\Large{T(t) = -r(T - T_m)}$

## Segunda parte calor especifico 

$\Large{C_{obj} = \frac{(m_{agua} C_{agua} + m_{termo} C_{termo})(T_{eq} - T_{amb})}{m_{obj} (T_{obj} - T_{eq})}}$

![[Pasted image 20251101220110.png]]

Error:

$\Large{f(m_{agua}, m_{termo}, m_{obj} T_{eq}, T_{amb}, T_{obj}) = \frac{(m_{agua} C_{agua} + m_{termo} C_{termo})(T_{eq} - T_{amb})}{m_{obj} (T_{obj} - T_{eq})}}$

$\large{\Delta f(m_{agua}, m_{termo}, T_{eq}, T_{amb}, T_{obj})  =  \mid \frac{\partial f}{\partial m_{agua}} \mid * \Delta m_{agua} + \frac{\partial f}{\partial m_{termo}} \mid * \Delta m_{termo} + \mid \frac{\partial f}{\partial m_{obj}} \mid * \Delta m_{obj} +  \frac{\partial f}{\partial T_{eq}} \mid * \Delta T_{eq} + \frac{\partial f}{\partial T_{amb}} \mid * \Delta T_{amb} + \frac{\partial f}{\partial T_{obj}} \mid * \Delta T_{obj}}$

$\large{\Delta m_{agua} = 1}$

$\large{\Delta m_{termo} = 1}$

$\large{\Delta m_{obj} = 1}$

$\large{\Delta T_{eq} = 0.1}$

$\large{\Delta T_{amb} = 12.22}$

$\large{\Delta T_{obj} = 12.22}$

$\large{ \frac{\partial f}{\partial m_{agua}} (m_{agua} C_{agua} + m_{termo} C_{termo}) * \frac{T_{eq} - T_{amb}}{m_{obj}(T_{obj} - T_{eq})} = C_{agua} * \frac{T_{eq} - T_{amb}}{m_{obj}(T_{obj} - T_{eq})} = 0.000058}$

$\large{\frac{\partial f}{\partial m_{termo}} (m_{agua} C_{agua} + m_{termo} C_{termo}) * \frac{T_{eq} - T_{amb}}{m_{obj}(T_{obj} - T_{eq})} = C_{termo} * \frac{T_{eq} - T_{amb}}{m_{obj}(T_{obj} - T_{eq})} = 0.000012}$

$\large{\frac{\partial f}{\partial m_{obj}} \frac{1}{m_{obj}} \frac{(m_{agua} C_{agua} + m_{termo} C_{termo})(T_{eq} - T_{amb})}{(T_{obj} - T_{eq})} = -\frac{1}{m_{obj}^2} \frac{(m_{agua} C_{agua} + m_{termo} C_{termo})(T_{eq} - T_{amb})}{(T_{obj} - T_{eq})} = -0.00087}$

$\large{\frac{\partial f}{\partial T_{eq}} \frac{(T_{eq} - T_{amb})}{ (T_{obj} - T_{eq})} * \frac{(m_{agua} C_{agua} + m_{termo} C_{termo})}{m_{obj}} = \frac{(T_{obj} - T_{eq}) + (T_{eq} - T_{amb})}{(T_{obj} - T_{eq})^2} * \frac{(m_{agua} C_{agua} + m_{termo} C_{termo})}{m_{obj} (T_{obj} - T_{eq})} = 0.0061}$

$\large{\frac{\partial f}{\partial T_{amb}} (T_{eq} - T_{amb}) * \frac{(m_{agua} C_{agua} + m_{termo} C_{termo})}{m_{obj} (T_{obj} - T_{eq})} = \frac{(m_{agua} C_{agua} + m_{termo} C_{termo})}{m_{obj} (T_{obj} - T_{eq})} = -0.30}$

$\large{\frac{\partial f}{\partial T_{obj}} \frac{1}{(T_{obj} - T_{eq})} * \frac{(m_{agua} c_{agua} + m_{termo} c_{termo})(T_{eq} - T_{amb})}{m_{obj}} = -\frac{1}{(T_{obj} - T_{eq})^2} \frac{(m_{agua} c_{agua} + m_{termo} c_{termo})(T_{eq} - T_{amb})}{m_{obj}} = -0.00054}$

$\large{\Delta f(m_{agua}, m_{termo}, T_{eq}, T_{amb}, T_{obj})  = 0.000058 + 0.000012 + 0.00087 + 0.0061*0.1 + 0.30*12.22 + 0.00054*12.22 = 3.67}$
