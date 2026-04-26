Dentro de las redes de computadoras existen 3 tipos de sistenas de numeración
- **Binario**
 0 y 1
- **Decimal**
0,1,2,3,4,5,6,7,8,9
- **Hexadecimal**
0,1,2,3,4,5,6,7,8,9,A(10),B(11),C(12),D(13),E(14),F(15)

# Sistemas de Factor de Ponderación de sistema binario

2^10    2^9    2^8    2^7    2^6    2^5    2^4    2^3    2^2    2^1    2^0
1024    512    256    128    64     32     16      8       4     2      1 

## Ejercicios de conversión de sistema Binario a Decimal:

- 00110011 = 51
- 01011001 = 89
- 01010111 = 87
- 10101010 = 170
- 11001100 = 204
- 111000110 = 454
- 110000111 = 391
- 1010110011 = 691
- 1100110011 = 819
- 11011100010 = 1, 762

## Ejercicios de conversion de Decimal a Binario

- 128 = 10000000  
- 192 = 11000000 
- 224 = 11100000
- 240 = 11110000
- 252 = 11111100
- 254 = 11111110
- 255 = 11111111
- 1000 = 1111101000
- 1311 = 10100011111

## Clases de direcciones IPv4

Clase       Rango       Mascara defecto       Prefijo       BO       BL
A           0-127       255.0.0.0             /8            8        24
B           128-191     255.255.0.0           /16           16       16
C           192-223     255.255.255.0         /24           24       8
D           224-239     255.255.255.255       /32           32       0
E           240-255     255.255.255.255       /32           32       0


**BO = Bits ocupados**

## Ejercicios de clases de direccionamiento IP.

Escribe cada una de las caracteristicas por defecto de cada dirección IP

- 192.168.10.10

**Clase** = C
**Mascara por defecto** = 255.255.255.0
**Bits Ocupados** = 24
**Bits Libres** = 8

- 10.10.10.10

**Clase** = A
**Mascara por defecto** = 255.0.0.0
**Bits Ocupados** = 8
**Bits Libres** = 24

- 224.0.0.10

**Clase** = = D
**Mascara por defecto** = 255.255.255.255
**Bits Ocupados** = 32
**Bits Libres** = 0

- 172.16.255.200

**Clase** = B
**Mascara por defecto** 255.255.0.0
**Bits Ocupados** 16
**Bits Libres** 16

- 250.255.39.178

**Clase** E
**Mascara por defecto** = 255.255.255.255
**Bits Ocupados** = 32
**Bits Libres** = 0


# Subneting
Se utiliza para dividir una red en diferentes subredes, permite una mejor administración, control del tráfico, seguridad al segmentar la red y mejora la performance de la red al reducir el tráfico de broadcast.  
Una subred es un segmento o dominio de broadcast separado.  
Un Host es un dispositivo de usuario final: impresoras, computadoras, servidores, cámaras IP, teléfonos IP, terminales de telepresencia, etc.  

Formulas para calcular el subneteo  

$2^n-2$ = Calcular la cantidad de subredes o host utilizables.

$2^n$ = Calcula la cantidad de subredes o host totales. 

## Ejercicios de Subnetting VLSM clase C

Utilizando la dirección IP 192.168.1.0/24, realizar un Subneteo VLSM para las siguientes cantidades de host : 50 Host Utilizables, 25HU, 25HU y 10HU.

Siendo $n = 3$ representando 3 subredes

$2^3$ = 8 
