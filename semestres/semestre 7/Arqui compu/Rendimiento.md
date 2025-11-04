$\large{\text{CPU Time} = \text{CPU Clock Cycles} * \text{Clock Cycle Time}}$

$\large{\text{CPU Time} = \frac{\text{CPU Clock Cycles}}{\text{Clock Rate}}}$

---
$\large{\text{CPU Clock Cycles} = \text{Instruction Count} * \text{Cycles per Instruction}}$

$\large{\text{CPU Time} = IC * CPI * \text{Clock Cycle Time}}$

$\large{\text{CPU Time} = \frac{IC * CPI}{\text{Clock Rate}}}$

---
$\large{\text{CPU Clock Cycles} = \sum_{i=1}^{n}(CPI_i * \text{Instruction Count}_i)}$

$\large{CPI = \frac{\text{CPU Clock Cycles}}{\text{Instruction Count}} = \sum_{i=1}^n (CPI_i * \frac{\text{Instruction Count}_i}{Instruction Count})}$

---
$\large{\text{CPU Time} = \frac{\text{Instructions}}{\text{Program}} * \frac{\text{Clock Cycles}}{\text{Instruction}} * \frac{\text{Seconds}}{\text{Clock Cycle}}}$


## 10
![[Pasted image 20251030182124.png]]
Alu: 1
Saltos: 2
Memoria: 3
Otras: 4
a)
Secuencia 1:
CPU clock cycles = $\large{4125 + 3458*2 + 3*86 + 4*25 = 11 399}$
CPI promedio = $\large{\frac{11399}{4125+3458+86+25} = \frac{11399}{7694} = 1.48}$

Secuencia 2:
CPU clock cycles = $\large{1178 + 1359*2 + 604*3 + 273*4 = 6800}$
CPI promedio = $\large{\frac{6800}{1178 + 1359 + 604 + 273} = \frac{6800}{3414} = 1.99}$

b)
Secuencia 1:
CPU Time = $\large{\frac{7694 * 1.48}{2.6E9} = 0.0000043 }$

Secuencia 2:
CPU Time = $\large{\frac{3414 * 1.99}{2.6E9} = 0.0000026 }$

c)
$\large{7694*1.48*C1 = 3414*1.99*C2}$

$\large{11387.12*C1 = 6793.86*C2}$

$\large{1.67*C1 = C2}$

## 11
42/34 = 1.23
se necesita mejora de 23%