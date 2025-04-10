## Rangos y clases de las direcciones IPv4
![[Pasted image 20250405155927.png]]

Clase A es N.H.H.H, osea que el primer numero representa la red

Clase B es N.N.H.H, osea que los primeros 2 números representan la red

Clase C es N.N.N.H, osea que los primeros 3 números representan la red

Nota Los nombres de la red tienen números en sus N pero tienen 0 en sus H, si no tienen 0  significa es el nombre de un computador

2 a public, 2 b privadas, 2 c publicas, 2 a privadas, 2 b publicas


| clase | public o private | id            | PPIC(primer pc) | UPC(ultimo pc)  | Bc(Broadcast)   | mascara       |
| ----- | ---------------- | ------------- | --------------- | --------------- | --------------- | ------------- |
| A     | Pu               | 11.0.0.0      | 11.0.0.1        | 11.255.255.254  | 11.255.255.255  | 255.0.0.0     |
| A     | Pu               | 12.0.0.0      | 12.0.0.1        | 12.255.255.254  | 11.255.255.255  | 255.0.0.0     |
| B     | Pr               | 172.16.0.0    | 172.16.0.1      | 172.16.255.254  | 172.16.255.255  | 255.255.0.0   |
| B     | Pr               | 172.31.0.0    | 172.31.0.1      | 172.31.255.254  | 172.16.255.255  | 255.255.0.0   |
| C     | Pu               | 192.0.0.0     | 192.0.0.1       | 192.255.255.254 | 192.255.255.255 | 255.255.255.0 |
| C     | Pu               | 223.255.255.0 | 223.255.255.1   | 223.255.255.254 | 223.255.255.255 | 255.255.255.0 |
| A     | Pr               | 10.0.0.0      | 10.0.0.1        | 10.255.255.254  | 10.255.255.255  | 255.0.0.0     |
|       |                  |               |                 |                 |                 |               |
| B     | pu               | 128.0.0.0     | 128.0.0.1       | 128.0.255.254   | 128.0.255.255   | 255.255.0.0   |
| B     | pu               | 191.0.0.0     | 191.0.0.1       | 191.0.255.254   | 191.0.255.255   | 255.255.0.0   |
|       |                  |               |                 |                 |                 |               |
|       |                  |               |                 |                 |                 |               |
|       |                  |               |                 |                 |                 |               |
