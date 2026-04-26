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

- **192.168.1.0/24**

Utilizando la dirección IP 192.168.1.0/24, realizar un Subneteo VLSM para las siguientes cantidades de host : 50 Host Utilizables, 28 Host Utilizables, 25 Host Utilizables y 10 Host Utilizables.


SRED 1
____ HU
(Para el siguiente paso no tenemos que sustituir la N por los HU, sino que debemos buscar un numero que al ser potencia de 2 se acerque a la cantidiad de host nos estan pidiendo)
2^N-2 = __ Host Utilizables
2^N = Host Totales.
MASK = XXX.XXX.XXX.XXX
Prefijo = /
RED - Broadcast =  R + I - 1 =
Rango de red y broadcast XXX.XXX.XXX.XXX - XXX.XXX.XXX.XXX
Rango Utilizable = XXX.XXX.XXX.XXX - XXX.XXX.XXX.XXX
R = RED     I = Incremento (el incremento lo tomamos de los Host Totales)

**RED1** 50 Host Utilizables
50 HU
(Para el siguiente paso no tenemos que sustituir la N por los HU, sino que debemos buscar un numero que al ser potencia de 2 se acerque a la cantidiad de host nos estan pidiendo)
2^6-2 = 62 Host Utilizables
2^6 = 64 Host Totales.
(Para la mascara tomamos en cuenta la mascara original de la red y a esa le apagamos la cantidad de bits que se tomaron prestados en la parte anterior)
MASK = 255.255.255.11000000 = 255.255.255.192
Prefijo = /26
(la red la comenzamos con 0)
(el incremento es la cantidad de HT)
RED - Broadcast =  R + I - 1 = 0 + 64 - 1 = 63
Rango de red y broadcast 192.168.1.0 - 192.168.1.63
(aumentamos 1 a la ip de red y para la ultima direccion utilizable le restamos 1 a la ip de broadcas)
Rango Utilizable = 192.168.1.1 - 192.168.1.62
R = RED     I = Incremento (el incremento lo tomamos de los Host Totales)

**RED2** 28 Host Utilizables
28 HU
(Para el siguiente paso no tenemos que sustituir la N por los HU, sino que debemos buscar un numero que al ser potencia de 2 se acerque a la cantidiad de host nos estan pidiendo)
2^5-2 = 30 Host Utilizables
2^5 = 32 Host Totales.
(Para la mascara tomamos en cuenta la mascara original de la red y se dejaran apagados ese numero de bits del ultimo octeto)
MASK = 255.255.255.11100000 = 255.255.255.224
Prefijo = /27
(la IP de red siempre la comienza despues de la IP de Broadcast anterior )
(el incremento es la cantidad de HT)
RED - Broadcast =  R + I - 1 = 64 + 32 - 1 = 95
Rango de red y broadcast 192.168.1.64 - 192.168.1.95
(aumentamos 1 a la ip de red y para la ultima direccion utilizable le restamos 1 a la ip de broadcas)
Rango Utilizable = 192.168.1.65 - 192.168.1.94
R = RED     I = Incremento (el incremento lo tomamos de los Host Totales)

**RED3** 25 Host Utilizables
50 HU
(Para el siguiente paso no tenemos que sustituir la N por los HU, sino que debemos buscar un numero que al ser potencia de 2 se acerque a la cantidiad de host nos estan pidiendo)
2^6-2 = 62 Host Utilizables
2^6 = 64 Host Totales.
(Para la mascara tomamos en cuenta la mascara original de la red y a esa le apagamos la cantidad de bits que se tomaron prestados en la parte anterior)
MASK = 255.255.255.11000000 = 255.255.255.192
Prefijo = /26
(la red siempre la comenzamos con 0)
(el incremento es la cantidad de HT)
RED - Broadcast =  R + I - 1 = 0 + 63 - 1 = 63
Rango de red y broadcast 192.168.1.0 - 192.168.1.63
(aumentamos 1 a la ip de red y para la ultima direccion utilizable le restamos 1 a la ip de broadcas)
Rango Utilizable = 192.168.1.1 - 192.168.1.62
R = RED     I = Incremento (el incremento lo tomamos de los Host Totales)

**RED4** 10 Host Utilizables.
50 HU
(Para el siguiente paso no tenemos que sustituir la N por los HU, sino que debemos buscar un numero que al ser potencia de 2 se acerque a la cantidiad de host nos estan pidiendo)
2^6-2 = 62 Host Utilizables
2^6 = 64 Host Totales.
(Para la mascara tomamos en cuenta la mascara original de la red y a esa le apagamos la cantidad de bits que se tomaron prestados en la parte anterior)
MASK = 255.255.255.11000000 = 255.255.255.192
Prefijo = /26
(la red siempre la comenzamos con 0)
(el incremento es la cantidad de HT)
RED - Broadcast =  R + I - 1 = 0 + 63 - 1 = 63
Rango de red y broadcast 192.168.1.0 - 192.168.1.63
(aumentamos 1 a la ip de red y para la ultima direccion utilizable le restamos 1 a la ip de broadcas)
Rango Utilizable = 192.168.1.1 - 192.168.1.62
R = RED     I = Incremento (el incremento lo tomamos de los Host Totales)
