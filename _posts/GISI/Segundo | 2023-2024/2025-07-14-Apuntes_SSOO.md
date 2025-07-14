---
layout: post
title: Apuntes de Sistemas Operativos
date: 2025-07-14 16:49
category: [GISI, Segundo | 2023-2024]
tags: [GISI, SSOO, Sistemas Operativos]
summary: Colección de apuntes y ejercicios de Sistemas Operativos
---

Para esta asignatura me basté con los apuntes del profesor, que me parecieron bastante completos. Obviamente no voy a subirlos directamente porque no he pedido permiso, pero si hay algo que no se entienda y no tienes los apuntes escríbeme e igual los tengo guardados.

# Apuntes laboratorio

# SISTEMAS DE ARCHIVOS

Un dispositivo físico (p.e. disco duro) puede estar dividido en **particiones**. [`C:\`, `D:\`, `E:\` en Windows, `/dev/hda1`, `/dev/hda2`,`...` en Linux]
En el Sector 0 del disco está el **MBR** (Master Boot Record) que se usa para arrancar el ordenador. Al final del MBR está la tabla de  particiones, que indica las posiciones de inicio y fin de cada partición.

El espacio del disco está dividido en varios bloques.
En los sistemas de archivos UNIX los bloques sirven para:
- Almacenar datos de usuario (archivos)
- Almacenar metadatos del sistema (superbloque, inodos, bloques de datos, etc.)

## inodos

El i-nodo es un concepto fundamental de los sistemas Linux/Unix. Cada objeto en el sistema de archivos está representado por un i-nodo.
El i-nodo es una estructura de datos que almacena información básica sobre un archivo, directorio u otro objeto del sistema.

La estructura de un i-nodo es la siguiente:
- Propietario
- Grupo
- Tipo de fichero
- Permisos de acceso
- Fechas de acceso, modificación, modificación del i-nodo
- Número de enlaces
- Tamaño
- ...
- Punteros a bloques de datos (Dirección en disco)

*El i-nodo no almacena el nombre del archivo*

### ¿Cómo ver el i-nodo de un archivo?

Utilizando el comando `ls -i`
```bash
$ ls -i /etc/passwd
    32820 /etc/passwd
```

Utilizando el comando `stat`, que también muestra los atributos
```bash
$ stat /etc/passwd
    File: /etc/passwd
    Size: 2659            Blocks: 8          IO Block: 4096   regular file
    Device: 341h/833d     Inode: 32820         Links: 1
```


### Ver información asociada al super-bloque

Utilizando el comando `dumpe2fs`
```bash
$ dumpe2fs /dev/sda1 | less
```

---

# Algoritmos de elección de víctima

FIFO:

x:

LRU:
Mirar hacia atrás el orden de páginas cargadas (Fijate en los puntos encima de la tabla)

Algoritmo de Reloj (Basado en LRU):  Lo hacemos con bits (e.g. $1^0$ para página 1 con bit 0)
Cuando se realice el segundo acceso a una página ya cargada en memoria pasamos el bit a 1

Por ejemplo: 1 -> $1^0$ | 2 -> $1^0$, $2^0$ | 1 -> $1^1$, $2^0$
Cuando el bit está en 1, es como asignarle una vida extra a la página, por lo tanto cuando haga falta escoger víctima se pone de vuelta a 0 pero se salva, y se escoge el siguiente en su lugar

| 1     | 2     | 3     | 1     | 4     | 5     | 2     | 3     | 4     | 3     |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| $1^0$ | $1^0$ | $1^0$ | $1^1$ | $1^1$ | $1^0$ | $1^0$ | $1^0$ | $4^0$ |       |
|       | $2^0$ | $2^0$ | $2^0$ | $2^0$ | $5^0$ | $5^0$ | $5^0$ |       |       |
|       |       | $3^0$ | $3^0$ | $3^0$ | $3^0$ | $2^0$ | $2^0$ | $2^0$ |       |
|       |       |       |       | $4^0$ | $4^0$ | $4^0$ | $3^0$ | $3^0$ | $3^1$ |

---

# Ejercicio HDD

Se dispone de un HDD de 3000rpm, 64 cilindros y 4 cabezas, 8 sectores por pista. Velocidad de posicionamiento: 60 pistas/sectores
Tiempo de lectura de 5 sectores de la pista 7?
Posición inicial pista 0

$T_L = T_P + L_R + T_T$

$T_P = m * v = 7 * 1/60 = 7/60$ segundos

$L_R = T/2 = 1/2 * 1/50 = 1/100$ segundos

$T_T = nSectores/(50 vueltas/segundo * 8 sectores/vuelta) = 5/400 = 1/80$ segundos

$T_L = 7/60 + 1/100 + 1/80$ segundos

---

