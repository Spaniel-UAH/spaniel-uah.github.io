---
layout: post
title: Apuntes de Análisis y Valoración de Proyectos de Inversión
date: 2025-07-14 12:46
category: [GISI, Segundo | 2023-2024]
tags: [GISI, AVPI]
summary:  Apuntes de los temas 1 a 6 (no hay del 4) de la asignatura Análisis y Valoración de Proyectos de Inversión del Grado en Ingeniería en Sistemas de Información de la UAH. Curso 2023-2024.
math: true
---

# Tema 1 - Fundamentos de la Valoración Financiera

---

{% include embed/youtube.html id='o9kUG89M3uA' %}

## 1.1. Conceptos Básicos

El dinero es un activo cuyo valor cambia con el tiempo
Elementos básicos:
- *CUANTÍA* ($C$)
- *VENCIMIENTO* ($t$) O TIEMPO

$Capital\space Financiero\space (C;t)$

Si $C_1 = C_2$ y $t_1 = t_2$, entonces $C_1 = C_2$
Si $C_1 \gt C_2$ y $t_1 \lt t_2$ es preferible $C_1$
Si $C_1 = C_2$ y $t_1 \lt t_2$ es preferible $C_1$
Si $C_1 \lt C_2$ y $t_1 \lt t_2$ necesitamos calcular $V_1$ y $V_2$

$V$ es el valor financiero de un capital en un momento determinado
$V_1 = F(C_1;t_1;p)$
$V_2 = F(C_2;t_2;p)$

$i$ es el tipo de interés, que es el precio del dinero (por cada unidad monetaria y cada unidad de tiempo). Si $i=3%$, entonces $1\text{€}$ hoy vale $1.03\text{€}$ en $n$.

## 1.2. Leyes Financieras

- **Ley financiera de capitalización simple** (*i*)
- **Ley financiera de capitalización compuesta** (*i*)
- **Ley financiera de descuento simple comercial** (*d*)

### 1.2.1. Ley de Capitalización Simple
Dos posibles formas:
- $L(n) = 1+i·n$ Siendo $n$ la duración de la operación (fin - inicio) e $i$ el tipo de interés.
- $L(t,p) = 1+i(p-t)$ Siendo $t$ el momento de inicio, $p$ el momento de fin de la operación e $i$ el tipo de interés.

Los intereses son proporcionales al capital que se presta y al tiempo durante el cual se presta. Esta ley es propia de operaciones a **corto plazo** (n<1 año).

$I(n) = i·C·n$ es el interés generado en un periodo de tiempo $n$.

Para un Capital ($C$) genérico:
*$$C_n = C+I = C+i·C·n$$*

**$$C_n = C·(1+i·n)$$**

### 1.2.2. Ley de Capitalización Compuesta
Dos posibles formas:
- $L(n) = (1+i)^n$
- $L(t,p) = (1+i)^{p-t}$

$I(n) = (1+i)^n -1$
$I(n) = C·i·n$

Los intereses van creciendo exponencialmente. Esta ley es propia de operaciones a **largo plazo** (n>=1 año).

**$$C_n = C·(1+i)^n$$**

### Ley de Descuento Simple Comercial
$\Delta(n) = 1-d·n$
$\Delta(n) = 1-d(p-t)$

$D(n) = 1·d·n$

**$$C_0 = C_n · (1-d·n)$$**

---

## 1.3. Tipos de interés
En la presentación viene un poco confuso, pero en este vídeo se explica de manera más simple: https://www.youtube.com/watch?v=pAGR_ykGYek

{% include embed/youtube.html id='pAGR_ykGYek' %}

En resumen, hay 3 tipos de interés:
- **Interés efectivo anual** ($i$): Es el tipo de interés que se aplica a un capital en un año.
- **Interés efectivo fraccionado** ($i_k$): Es el tipo de interés que se aplica a un capital en un periodo de tiempo menor a un año.
- **Interés nominal** ($j_k$): Es el tipo de interés que se aplica a un capital en un año, pero dividido en $k$ periodos de tiempo.

Donde $k$ es el número de periodos de tiempo en los que se divide el año:
- **Mensual** ($k=12$)
- **Trimestral** ($k=4$)
- **Semestral** ($k=2$)
- **Días** ($k=360$) (si usamos año comercial)

De estos tres tipos solo necesitamos saber las siguientes dos fórmulas para pasar de uno a otro:
$$\boxed{1+i = (1+i_k)^k}$$
$$\boxed{i_k = \frac{j_k}{k}}$$

**Ejemplo**: Si el tipo de interés anual es el 10% calcula el tipo de interés mensual.
$$i = 0.1 \rightarrow 1+0.1 = (1+i_k)^{12} \rightarrow (1+0.1)^{\frac{1}{12}}-1 = i_k \rightarrow i_k = 0.00797 = 0.797\%$$

**Ejemplo**: Si el tipo de interés semestral es el 2% calcula el tipo de interés anual.
$$i_2 = 0.02 \rightarrow 1+i = (1+0.02)^2 \rightarrow 1+i = 1.0404 \rightarrow i = 0.0404 = 4.04\%$$

**Ejemplo**: Si el tipo de interés nominal es el 12% calcula el tipo de interés trimestral.
$$j_4 = 0.12 \rightarrow i_k = \frac{0.12}{4} = 0.03 = 3\%$$


---

## 1.4. Rentas Financieras

Una **Renta financiera** es una sucesión de capitales que han de hacerse efectivos en determinados vencimientos.

- ***Renta**: Conjunto de importes distribuidos en un intervalo de tiempo*

Los *capitales* ($C_0, C_1, \dots, C_{n-1}, C_n$) que constituyen la renta se denominan **términos** de la renta, y sus subintervalos ($0, 1, \dots, n-1, n$) **periodos de maduración**.

Al extremo inferior del primer subintervalo se le denomina **momento de constitución** u **origen de la renta**. El extremo superior del último periodo es el **fin de la renta**. El tiempo entre ambos es la **duración de la renta**.

El **valor financiero** de una renta en un punto es la suma financiera en dicho punto de los términos que forman la renta, según una ley financiera previamente establecida (normalmente la ley de capitalización compuesta).

El valor financiero se puede calcular en cualquier momento de tiempo, si bien lo normal es calcularlo al origen o al final.
- ***Valor actual o inicial ($V_0$)**: valor financiero en el origen*
$$V_0 = C_1(1+i)^{-1} + C_2(1+i)^{-2} + \dots + C_{n-1}(1+i)^{-(n-1)} + C_n(1+i)^{-n}$$

$$V_0 = \sum_{s=1}^{n}C_s(1+i)^{-s}$$
- ***Valor final o capital ($V_n$)**: valor financiero en el final*
$$V_n = C_1(1+i)^{n-1} + V_2(1+i)^{n-2} + \dots + C_{n-1}(1+i) + C_n$$
$$V_n = \sum_{s=1}^{n}C_s(1+i)^{n-s}$$

De esto podemos obtener que:

$$V_n = V_0(1+i)^n$$

$$V_0 = V_n(1+i)^{-n}$$

Para el valor actual de una renta usaremos el símbolo a ($a_{n\lnot i}$) y para el valor final usaremos el símbolo S ($S_{n\lnot i}$).


### ¿Cómo valorar rentas financieras? (Con la ley de capitalización compuesta)

1. Escogemos el momento en el que vamos a valorar la renta financiera
2. Aplicamos las fórmulas de $V_0$ o $V_n$

[`TODO` añadir un ejemplo]

### Clasificación de rentas financieras

- Atendiendo a la cuantía de los términos que lo forman
    - Rentas constantes
    - Rentas variables
- Atendiendo a la naturaleza de los capitales
    - Rentas ciertas
    - Rentas aleatorias [Seguro de vida]
    - Rentas inciertas
- Atendiendo a la medida de los intervalos
    - Rentas discretas
    - Rentas continuas
- Atendiendo al vencimiento de los términos de la renta
    - Renta pospagable (los capitales se asocian al final del periodo) [Salario]
    - Renta prepagable (los capitales se asocian al comienzo del periodo) [Alquiler]
- Atendiendo a la duración de la renta
    - Rentas temporales
    - Rentas perpetuas
- Atendiendo al punto de valoración
    - Rentas inmediatas (se valoran en el origen)
    - Rentas diferidas (se valoran antes del origen)
    - Renta anticipada (se valoran después de su final)

<br>


### Resumen de fórmulas
La fórmula base para el valor actual de una renta constante temporal inmediata y pospagable es:
$$\boxed{V_0 = a·\frac{1-(1+i)^{-n}}{i}}$$
o lo que es lo mismo:
$$\boxed{V_0 = C·a_{n\lnot i}}$$

Siendo $a$ el importe de cada término, $n$ el número de términos e $i$ el tipo de interés.

**Hay 5 reglas a tener en cuenta para los ejercicios con rentas financieras:**
1. Siempre aplicamos la fórmula del **Valor Actual**: 
   $$V_0 = a·\frac{1-(1+i)^{-n}}{i}$$
2. Si piden **Valor Final** le añadimos a la anterior $(1+i)^n$:
   $$V_n = V_0·\boxed{(1+i)^n}$$
3. Si piden **Prepagable** le añadimos a la pospagable $(1+i)$:
   $$V_0^{\text{Prepagable}}=V_0·\boxed{(1+i)}$$
4. Si piden **Diferida** le añadimos a la inmediata $(1+i)^{-D}$:
   $$V_0^{\text{Diferida}}=V_0·\boxed{(1+i)^{-D}}$$
5. Si piden **Anticipada** le añadimos a la prepagable $(1+i)^{H}$:
   $$V_0^{\text{Anticipada}}=V_0·\boxed{(1+i)^{H}}$$

Por ejemplo, si nos dicen "**Calcula el valor final de una renta prepagable anticipada 3 años de 10 términos anuales de 2.000€ siendo el tipo de interés anual efectivo el 4%**":
Aplicamos la fórmula del valor actual, al ser valor final le añadimos $(1+i)^n$, al ser prepagable le añadimos $(1+i)$ y al ser anticipada le añadimos $(1+i)^{H}$:
$$V_0 = a·\frac{1-(1+i)^{-n}}{i}·(1+i)^n·(1+i)·(1+i)^{H}$$
$$V_0 = 2000·\frac{1-(1+0.04)^{-10}}{0.04}·(1+0.04)^{10}·(1+0.04)·(1+0.04)^{3} = 28090.89$$

<br>
<br>

En el caso de rentas de progresión geométrica, la fórmula base es:

$$V_0 = C·\frac{1-(1+i)^{-n}q^n}{1+i-q}$$

En el caso de rentas de progresión aritmética, la fórmula base es:

$$V_0 = (C + \frac{d}{i}+d·n)·a_{n\lnot i}-\frac{d·n}{i}$$

<br>

---

<br>

# Tema 2. Operaciones Financieras

Una **operación financiera** es un intercambio de dos conjuntos de capitales. Conjuntos financieramente equivalentes $\rightarrow$ la suma financiera de cada uno de ellos en un momento de tiempo determinado coincide.

---

## 2.1. Introducción
- **Prestamista** (*o acreedor **A***) $\rightarrow$ persona que entrega el primer capital.
- **Prestatario** (*o deudor **D***) $\rightarrow$ persona que lo recibe y se compromete a entregar otra serie de capitales.

El conjunto de capitales que entrega el prestamista es una **prestación**, mientras que el conjunto que entrega el prestatario es una **contraprestación**.

## 2.2. Clasificación de Operaciones Financieras

- Ciertas: 
- Aleatorias: Sin conocer la contraprestación

<br>

- A corto plazo
- A largo plazo

<br>

- Simples: Prestación y contraprestación son *únicos* (formadas por un solo capital)
- Compuestas:
    - Prestación única y contraprestación múltiple
    - Prestación multiple y contraprestación única

<br>

- De crédito unilateral: Quien comienza como prestamista termina como prestamista
- De crédito bilateral: Las que no cumplen el requisito anterior

<br>

- Predeterminadas
- Posdeterminadas


## 2.3. Cálculo de Operaciones Financieras

Análisis de operación:
1. Completar información: Ecuación equilibrio $S_A(t) = S_D(t)$
2. Estudiar evolución de la operación: **Saldo financiero**
3. Consecuencias de la operación: **Tantos efectivos**


4. $P\approx CP \rightarrow$ Completar información
5. Saldo 1º o Reserva `noseque`
    $P_1+P_2 = CP_1+CP_2 \rightarrow P_1-CP_1=CP_2-P_2 = S_{S+1} \gtrless 0\space$ Si es mayor acreedor, si es menor deudor. 


## 2.4. Liquidez en Operaciones Financieras

Pongamos que una de las partes quiere salir de la operación, es decir, dejar de formar parte de la misma.
Hay dos opciones:
- Ambas partes acuerdan cancelar antes de lo previsto $\rightarrow$ **Liquidez interna**
- Una de las partes sale de la operación, es sustituida, y la operación finaliza según lo acordado $\rightarrow$ **Liquidez externa**

<br>

- Prevista $\rightarrow$ Penalización
    - Sobre Intereses
        - La decisión la toma el Prestamista $\rightarrow$ $R_S = C_S - \alpha I_S$
        - La decisión la toma el Prestatario $\rightarrow$ $R_S = C_S + \alpha I_S$
    - Sobre Deuda
        - La decisión la toma el Prestamista $\rightarrow$ $R'_S = C_S - \alpha'C_S$
        - La decisión la toma el Prestatario $\rightarrow$ $R'_S = C_S + \alpha'C_S$
- No prevista $\rightarrow$ Negociación
    - Al **Prestamista** le interesará si podrá obtener mayor beneficio que el que obtendría al final de la operación actual. Es decir:
    $$C'_n > C_n$$
    Cualquier importe entre $C_S$ y $x$ beneficiará a los dos:
    $$C_S \leftrightarrow x \space\space\rightarrow Negociación$$
    $$\boxed{x(1+i_a)^{n-s} = C_n} \rightarrow \boxed{x=C_n(1+i_a)^{-(n-s)}}$$
    - Al **Prestatario** le interesará si podrá devolver al final menos dinero del que tendría que devolver al final de la operación actual.
    $$C''_n < C_n$$
    Cualquier importe entre $Y$ y $C_S$ beneficiará a los dos:
    $$Y \leftrightarrow C_S \space\space\rightarrow Negociación$$
    $$\boxed{Y(1+i_d)^{n-s}=C_n} \rightarrow \boxed{Y=C_n(1+i_d)^{-(n-s)}}$$

<br>

## 2.5. Tantos Efectivos

Cuando se contratan las operaciones financieras, además de los capitales que constituyen el intercambio ($Prestación \approx Contraprestación$) suelen existir una serie de condiciones o **características complementarias** que modifican la cuantía o vencimiento de dichos capitales.

$$\frac{P\approx CP}{i}$$

Donde i es la condición que modifica la relación (**!!!** *no es una fracción, $i$ va debajo del $\approx$*).
Pueden ser bilaterales:

$$\frac{P_{real\space del\space prestamista} \approx CP_{real\space del\space prestatario}}{i_e}$$

O unilaterales (hay que ver los puntos de vista de ambos, prestamista y prestatario):

$$\frac{P_{efectiva\space del\space prestamista} \approx CP_{efectiva\space para\space el\space prestamista}}{i_a}$$

$$\frac{P_{efectiva\space para\space el\space prestatario} \approx CP_{efectiva\space del\space prestatario}}{i_p}$$

### 2.5.1. Ejemplo
Supongamos tener:
$C_0$
$i$
$n$
$C^i_p \rightarrow C^i_a$
$C^d_a$
Impuesto $T^d_a = t$ sobre rendimientos

Prestatario:
$C_n=C_0(1+i)^n$
> 1. $i_p \rightarrow (C_0-G^i_p)(1+i_p)^n = C_n + G_p^t \rightarrow \boxed{i_p > i}$

> 2. $i_a \rightarrow (C_0 - G^i_a)(1+i_a)^n = C_n - G_a^t - T_a^t \rightarrow \boxed{i_a \space ? \space i}$
$T_a^t = t[C_n-G_a^t-(C_0 - G_a^i)]$

<br>

---

<br>


# Tema 3. Operaciones de Financiación


---

## 3.1. Introducción
Hola

## 3.2. Categorías
**Financiación a corto plazo**: Menos de un año
- Financiación espontánea
- Financiación negociada
  - Crédito comercial
  - Pagarés
  - Crédito bancario
  - Descuento bancario
  - Préstamos a corto plazo
  - Factoring
**Financiación a largo plazo**: Más de un año
- Ampliaciones de capital
- Préstamos a largo plazo
- Empréstitos
- Leasing
- Renting
- Otras

## 3.3. Financiación espontánea
Recursos financieros que la empresa obtiene de forma automática al realizar su actividad, fundamentalmente a través de los proveedores y los clientes.
Por ejemplo, descuentos por pronto pago.

## 3.4. Crédito comercial
El pago al proveedor se hace a plazo.
Tipologías:
- Crédito abierto: Proveedor autoriza que se deba hasta un determinado importe
- Crédito rotatorio: Cuantía límite y fechas de pago preestablecidas
- Crédito o venta en consignación (se facilita producto y se paga si se vende)
- Crédito con fecha estacional (se facilita producto y se paga después de la época de venta)

El coste se valorará según exista o no descuento por pronto pago:
- No existe descuento ppp: se deberá aprovechar la financiación establecida
- Existe descuento ppp: El coste implícito recae en el descuento ppp

### Análisis técnico

### Alternativas
Utilizar al proveedor como fuente de financiación, pagando en $n$ el nominal $N$.
Pagamos $N*(1-p)$ en $s$ y financiamos a un tipo de interés $i$.

#### Coste capitalización simple
$$N*(1-p)*[1+i\frac{n-s}{360}]=N \rightarrow i=\frac{p}{1-p}*\frac{360}{n-s}$$

#### Coste capitalización compuesta
$$N*(1-p)*(1+i)^{\frac{n-s}{360}}=N \rightarrow i=(\frac{1}{1-p})^{\frac{360}{n-s}}-1$$


## 3.5. Pagarés
Títulos negociables a la orden o al portador. El emisor se obliga a pagar al suscriptor, tomador o beneficiario una cierta cantidad de dinero en una fecha determinada.

Desde el punto de vista financiero es una operación en la que el pago único inicial da derecho a recibir al vencimiento la cuantía comprometida del pagaré.

Esta operación se valora con la ley de capitalización simple:
$$E*(1+i*\frac{n}{360})=N$$

Donde:
- E = Valor efectivo del pagaré (inicial)
- N = Valor nominal del pagaré (final)

## 3.6. Crédito bancario
Se pone a disposición de la empresa una cuantía de dinero del que la empresa puede disponer según sus necesidades, documentándose en la ***Póliza de Crédito***.

Dos tipos:
- *Simple*: El cliente hace un único reintegro al término de la operación.
- *Cuenta corriente de crédito*: El cliente puede hacer reintegros en la cuenta cuando quiera.

No vamos a entrar en detalles de cómo calcularlo. (Así que entiendo que no entra porque la profe no lo ha explicado)

## 3.7. Descuento bancario
El descuento bancario es una operación mediante la cual el banco abona a quien presenta el efecto el valor descontado de su nominal.

Valorada con la ley de descuento simple.

- Prestación = Efectivo que entrega el banco a su cliente
- Contraprestación = Nominal del título

Clases de descuento bancariro:
- **DESCUENTO CAMBIARIO**: Título de crédito que se descuenta es la letra de cambio
    - ***Descuento comercial***: Los efectos a descontar proceden de transacciones comerciales. El objetivo es obtener liquidez.
    - ***Descuento financiero***: La letra de cambio instrumenta un préstamo del banco a su cliente.
- **DESCUENTO NO CAMBIARIO**: Título descontado no es una letra de cambio


#### Operación Pura
- $C_n$ = Nominal del efecto
- $C_0$ = Efectivo que entrega el banco al cliente
- $d$ = Tipo de descuento aplicado
- $n$ = Duración de la operación, normalmente en días

$$\boxed{C_0 = C_n * (1-d\frac{n}{360})}$$

#### Características complementarias
- $g$ = Comisión por negociación
- $T$ = IAJD, suele ser pagado por el librador de la letra

Recibe: 
```math
\boxed{C^1_0=C_0-C_n*g}=C_n(1-d\frac{n}{360})-C_n*g=C_n(1-(d\frac{n}{360}+g))
```

Entrega: $C_n$

## 3.8. Factoring
Nada


## 3.9. Acciones
Primera fuente de financiación de una empresa: las aportaciones de los socios.
Al inicio de una empresa se emiten acciones por su valor nominal, tal que *Capital Social* = *Valor nominal * Número de acciones*

El capital social mínimo de una sociedad anónima es de 60.000€.

El capital social mínimo de una sociedad limitada es de 3.000€.


## 3.10. Préstamos
El banco da una tabla de amortizaciones:

| $s$   | $i_s$     | $a_s$     | $I_s$         | $\Delta_s$ | $m_s$                  | $C_s$                           |
| ----- | --------- | --------- | ------------- | ---------- | ---------------------- | ------------------------------- |
| 0     | -         | -         | -             | -          | -                      | $C_0$                           |
| 1     | $i_1$     | $a_1$     | $C_0·i_1$     | $a_1-I_1$  | $\Delta_1$             | $C_1=C_0-\Delta_1=C_0-m_1$      |
| 2     | $i_2$     | $a_2$     | $C_1·i_2$     | $a_2-I_2$  | $m_1+\Delta_2$         | $C_2=C_1-\Delta_2=C_0-m_3$      |
| ...   | $i_{...}$ | $a_{...}$ | -             | -          | -                      | -                               |
| $n-1$ | $i_{n-1}$ | $a_{n-1}$ | -             | -          | -                      | -                               |
| $n$   | $i_n$     | $a_n$     | $C_{n-1}·i_n$ | $a_n-I_n$  | $m_n=m_{n-1}+\Delta_n$ | $C_n=C_{n-1}-\Delta{n}=C_0-m_n$ |


Donde:
$s$ = periodo de amortización (el número de periodos)
$i_s$ = tipo de interés aplicado en el periodo $s$
$a_s$ = cuota o término anual (pago completo del periodo $s$)
$I_s$ = interés del periodo $s$ (interés que se paga en el periodo $s$)
$\Delta_s$ = cuota de amortización del periodo $s$ (capital que se paga en el periodo $s$)
$m_s$ = capital amortizado total después del periodo $s$ (desde el principio)
$C_s$ = capital pendiente de amortizar al final del periodo $s$

Como fórmulas generales:
$C_0 = C_s + m_s$
$I_s = C_{s-1} * i_s$
$\Delta_s = C_{s-1} - C_s$
$a_s = I_s + \Delta_s$


Ecuación de equilibrio: $$\boxed{C_0=\sum_{r=1}^{n}a_r\prod^r_{h=1}(1+i_h)^{-1}}$$
Reserva por el método retrospectivo: 
```math
C_s=C_0\prod^s_{h=1}(1+i_h)-[\sum^{s-1}_{r=1}a_r\prod^s_{h=r+1}(1+i_h)+a_s] =
```
$$=\boxed{C_0(1+i)^s- \sum^{s}_{r=1}a_r(1+i)^{s-r}}$$
Reserva por el método prospectivo: $$C_s=\sum^n_{r=s+1}a_r\prod^r_{h=s+1}(1+i_h)^{-1}$$
Reserva por el método recurrente: $$C_s=C_{s-1}(1+i_s)-a_s$$



#### Préstamo Americano
Todas las cuotas de amortización son 0, excepto la última que coincide con el nominal del préstamo.

Los pagos que se efectúan periódicamente corresponden únicamente a los intereses del periodo, excepto el último que añade la devolución del préstamo.

Por lo tanto:
$a_s=I_s$ y $a_n=I_n+C_0$
$I_s=C_0·i_s$
$\Delta_s=0$ y, al final, $\Delta_n=C_0$
$m_s=0$ y, al final, $m_n=C_0$
$C_s=C_0$ y, al final, $C_n=0$

#### Préstamo Francés
Los pagos periódicos del préstamo (términos amortizativos) son constantes. Es el más frecuente sobre todo con particulares.

Por lo tanto (asumiendo que el tipo de interés es constante para simplificar):
$a_s=a \rightarrow C_0=a·\alpha_{n\lnot i}$
$I_s=C_{s-1}·i$
$\Delta_s=a-I_s$
$m_s=C_0-C_s$
$C_s=a·\alpha_{n-s\lnot i}=C_0\frac{\alpha_{n-s\lnot i}}{\alpha_{n\lnot i}}$

Ecuación de equilibrio: $$C_0=a·\alpha_{n\lnot i}$$

Reserva retrospectivo: $$C_s=C_0(1+i)^s-a·S_{n\lnot i}$$

Reserva prospectivo:
$$C_s=a·\alpha_{n-s\lnot i}$$

Reserva recurrente:
$$C_s=C_{s-1}(1+i)-a$$

#### Préstamo con cuotas de amortización constantes

$a_s=I_s+\Delta$

$I_s=C_{s-1}·i$

$\Delta_s =\Delta \rightarrow C_0=\sum^{n}_{r=1}\Delta_r=n·\Delta \rightarrow \boxed{\Delta=\frac{C_0}{n}}$
$m_s=C_0-C_s=s·\Delta$
$C_s=\sum^{n}_{r=s+1}\Delta_r=(n-s)·\Delta$


## 3.11. Empréstitos
Operaciones de financiación en las que el importe total está dividido en partes alícuotas. Cada parte recibe el nombre de *obligación* o *bono* y es a su vez una operación de préstamo.

El emisor del empréstito es el prestatario, quienes adquieren las obligaciones o bonos son los prestamistas de la operación.

`TODO añadir formulas`

$C_0$



### Obligaciones Americanas


### Obligaciones Cupón Cero



## 3.12. Leasing o Arrendamiento Financiero
Una empresa o profesional puede disponer de un bien, mueble o inmueble, pagando una renta periódica en concepto de alquiler...
La diferencia con el Renting es que el leasing suele incorporar una opción de adquirir el bien tras el plazo, en el renting no.

Puede ser Mobiliario (~2 años) o Inmobiliario (~10 años)

Puede ser financiero u operativo.

## 3.13. Capital Riesgo
Sociedades especializadas en inversiones que aportan recursos en la empresa en proporción minoritaria y con carácter temporal (3-5 años habitualmente), con objetivo de obtener beneficio.
### Sociedades de Capital Riesgo

### Fondos de Capital Riesgo

## 3.14. Project Finance
Financiación de proyectos intensivos en capital. Normalmente para financiar construcción y explotación de infraestructuras que generan cash-flows suficientes para pagar la financiación recibida. Requiere proyectos viables y cash-flows estables.

## 3.15. Crowdfunding
Financiación colectiva que permite que cualquier persona contribuya con cualquier cantidad de dinero para desarrollar una iniciativa empresarial.

## 3.16. Business Angels
Un ángel inversor aporta el capital necesario tras analizar la viabilidad del proyecto. Suelen intervenir en las etapas iniciales de las empresas, ayudando a los nuevos emprendedores a desarrollar sus iniciativas.

<br>

---

<br>

# Tema 5. Métodos de Valoración de Proyectos de Inversión


---

## 5.1. Introducción
En este tema se presentan las herramientas principales a tener en cuenta al adoptar decisiones acerca de un proyecto de inversión.

## 5.2. Métodos Parciales o Incompletos
Los sistemas de valoración incompletos no incluyen la totalidad de los datos disponibles. Se dispone de los flujos de caja y/o el momento de tiempo en que estos están disponibles.

#### 5.2.1. Flujo neto de caja total por u.m. invertida
Relaciona la suma aritmética de **todos** los flujos frente al desembolso inicial.

$$f=\frac{\sum^n_{s=1}{R_s}}{D_0}$$

Criterio de decisión:
- Si $f>1$ la inversión es **aceptable**.
- Si $f<1$ la inversión **no** es **aceptable**.

Es un método fácil de calcular, pero agrega magnitudes heterogéneas.

#### 5.2.2. Flujo neto de caja medio por u.m. invertida
Relaciona la suma aritmética de todos los flujos **divididos entre el número de estos** con el desembolso inicial.

$$f^- = \frac{\frac{\sum^n_{s=1}{R_s}}{n}}{D_0} = \frac{1}{n} · f$$

Criterio de decisión:
- Si $f>1/n$ la inversión es **aceptable**.
- Si $f<1/n$ la inversión **no** es **aceptable**.

Es un método fácil de calcular, pero agrega magnitudes heterogéneas.

#### 5.2.3. Plazo de recuperación de la inversión
Número de periodos necesarios para recuperar el desembolso inicial.

$$P \rightarrow \sum^p_{s=1}R_s \geq D_0$$

$R_S$ debe permitir recuperar el desembolso inicial en $P$ periodos.

Para establecer un criterio, la empresa debe establecer un periodo de recuperación máximo:
- Si $P < P_{máximo}$ la inversión es **aceptable**.
- Si $P > P_{máximo}$ la inversión **no** es **aceptable**.

Es fácil de calcular, pero no considera el momento de disponibilidad de los flujos y se basa en criterios de liquidez y no de rentabilidad.

## 5.3. Métodos Completos o Globales
Los métodos completos incorporan toda la información cuantitativa del proyecto.
En estos métodos tiene especial importancia el horizonte temporal de los flujos previstos y el tipo de interés o tanto de valoración al que se valoran estos.

### 5.3.1. Valor Actual Neto (VAN) o Beneficio Total Actualizado
Es una medida financiera del Beneficio Actualizado adicional calculado bajo un tipo de interés determinado.
Lo normal es tomar como punto de valoración el inicio del proyecto, si bien se puede calcular en cualquier otro punto. Hay que tener en cuenta la actualización/capitalización al tipo de interés correspondiente:

$${VAN}(i) = \sum^n_{s=1}C_s · (1+i)^{-s}-\sum^n_{s=0}D_s · (1+i)^{-s} = \boxed{\sum^n_{s=1}R_s(1+i)^{-s}-D_0}$$

- Si VAN > 0 **se acepta**, ya que me permite recuperar lo invertido obteniendo además un beneficio adicional.
- Si VAN = 0 la inversión **es indiferente**, hará frente a los gastos pero no generará beneficios.
- Si VAN < 0 **se rechaza** ya que no hace frente a los pagos derivados del mismo.

El tipo de interés considerado debe ser como mínimo el de mercado, si bien se debe aplicar una prima/margen/spread (el diferencial) al tipo de interés de mercado.
El tipo de interés de valoración debería ser mayor a medida que asumamos mayor riesgo.

El cálculo del VAN lleva implícito que los flujos netos de caja del proyecto son reinvertidos al mismo tipo de interés de valoración $i$.

### 5.3.2. Relación Beneficio-Coste
Índice que mide el valor creado por la inversión por cada u.m. invertida en el mismo.

$$I_{bc} = \frac{\sum^n_{s=1}R_s(1+i)^{-s}}{D_0} = \boxed{\sum^n_{s=1}\frac{R_s}{D_0}(1+i)^{-s}}$$

- Si $I_{bc} > 1$ la inversión es **aceptable**.
- Si $I_{bc} = 1$ la inversión es **indiferente**.
- Si $I_{bc} < 1$ la inversión **no** es **aceptable**.

### 5.3.3. Tanto Interno de Rentabilidad (TIR)
Es el tipo de interés que hace que el VAN del proyecto sea 0.
$TIR = i_e$
$VAN(i_e) = 0$

$$\sum^n_{s=1}C_s(1+i_e)^{-s}-\sum^n_{s=0}D_s(1+i_e)^{-s} = \boxed{\sum^n_{s=1}R_s(1+i_e)^{-s}-D_0 = 0 \rightarrow i_e}$$

El $i_e$ mide la rentabilidad del proyecto por u.m. invertida y por unidad de tiempo.

Como criterio, comparamos $i_e$ con el tipo de interés $i$ que indica la rentabilidad mínima exigida por la empresa al proyecto.

- Si $i_e > i$ la inversión es **aceptable**.
- Si $i_e = i$ la inversión es **indiferente**.
- Si $i_e < i$ la inversión **no** es **aceptable**.

Características
- Al comparar varios proyectos no será necesario homogeneizarlos.
- Subjetividad a la hora de establecer la rentabilidad mínima exigida.
- Dificultad de cálculo e inconsistencia en el resultado cuando la inversión no es simple.
- Lleva implícito que los flujos netos de caja del proyecto son reinvertidos al tipo de interés $i_e$.

## 5.4. Ejemplo

| Proyecto | Desembolso | 1      | 2      | 3      | 4      | 5      |
| -------- | ---------- | ------ | ------ | ------ | ------ | ------ |
| A        | -40.000    | 16.000 | 18.000 | 20.000 | -      | -      |
| B        | -40.000    | -      | 16.000 | 18.000 | 20.000 | -      |
| C        | -40.000    | -      | -      | 16.000 | 18.000 | 20.000 |

### 5.4.1. Incompletos
- Flujo neto de caja total

$$f_A=\frac{16.000+18.000+20.000}{40.000} = 1,35$$
$$f_B=\frac{0+16.000+18.000+20.000}{40.000} = 1,35$$
$$f_C=\frac{0+0+16.000+18.000+20.000}{40.000} = 1,35$$

- Flujo neto de caja medio
$$f_A=\frac{\frac{16.000+18.000+20.000}{3}}{40.000} = 0,45$$
$$f_B=\frac{\frac{0+16.000+18.000+20.000}{4}}{40.000} = 0,33$$
$$f_C=\frac{\frac{0+0+16.000+18.000+20.000}{5}}{40.000} = 0,25$$

- Plazo de Recuperación
$$16.000+18.000+20.000 \geq 40.000 \rightarrow P_A = 3$$
Lo mismo ocurre con los otros, considerando periodos 1 y 2

### 5.4.2. Completos
- VAN
$$VAN_A = -40.000 + 16.000(1+0,09)^{-1}+18.000(1+0,09)^{-2}+20.000(1+0,09)^{-3} = $$
$$VAN_B = -40.000 + 16.000(1+0,09)^{-2}+18.000(1+0,09)^{-3}+20.000(1+0,09)^{-4} = 1.534,69$$
$$VAN_C = -40.000 + 16.000(1+0,09)^{-3}+18.000(1+0,09)^{-4}+20.000(1+0,09)^{-5} = -1.894,78$$

- Relación benefio-coste
$$I_{bc\space A} = \frac{16.000(1+0,09)^{-1}+18.000(1+0,09)^{-2}+20.000(1+0,09)^{-3}}{40.000} = 1,13$$
$$I_{bc\space B} = \frac{16.000(1+0,09)^{-2}+18.000(1+0,09)^{-3}+20.000(1+0,09)^{-4}}{40.000} = 1,03$$
$$I_{bc\space C} = \frac{16.000(1+0,09)^{-3}+18.000(1+0,09)^{-4}+20.000(1+0,09)^{-5}}{40.000} = 0,95$$

- TIR
$$TIR_A = 15\%$$
$$TIR_B = 10\%$$
$$TIR_C = 7\%$$

<br>

---

<br>

# Tema 6. Criterios de Decisión

---

## 6.1. Criterio de Decisión ante un Proyecto de Inversión Aislado


### 6.1.1. Comparación de los criterios VAN y TIR en un proyecto aislado
$$\text{VAN}(i) = -D_0 + \sum^n_{s=1}R_S(1+i)^{-s} \gt \lt 0$$
$$\text{TIR} = i_e \rightarrow -D_0  + \sum^n_{s=1}R_s(1+i_e)^{-s} = 0 \rightarrow D_0 = \sum^n_{s=1}R_s(1+i_e)^{-s} \rightarrow i_e \gt \lt i$$

$$\text{VAN}(i) = -\sum^n_{s=1}R_s(1+i_e)^{-s} + \sum^n_{s=1}R_s(1+i)^{-s} = \sum^n_{s=1}R_s[(1+i)^{-s}-(1+i_e)^{-s}]$$


## 6.2. Criterio de Decisión ante un Conjunto de Proyectos de Inversión
Dos proyectos son homogéneos cuando coinciden en desembolso y duración.
Para tomar una decisión frente a dos proyectos, deben ser homogéneos. Si no lo son se deben homogeneizar.

Primero analizamos individualmente cada proyecto, luego homogeneizamos.

### 6.2.1 - Homogeneización de proyectos de inversión con el mismo desembolso inicial y distinta duración
Duración de los proyectos: mínimo común múltiplo de las duraciones de cada proyecto y se repite cada uno tantas veces como sea necesario hasta completar la duración establecida

$$P_1 = [D_0;R_s^1;n_1]$$
$$P_2 = [D_0;R_s^2;n_2]$$

$$n = m.c.m[n_1;n_2]$$

#### Ejemplo de clase:
```plaintext
   -10     2,5    4,5    6,5
A    |------|------|------|
     0      1      2      3

   -10      6     6,5
B    |------|------|
     0      1      2
```
1. **Valorar individualmente cada proyecto**
$\text{VAN}_A(10\%)=-10+2,5(1+0,10)^{-1}+4,5(1+0,10)^{-2}+6,5(1+0,10)^{-3}=875,28$
$\text{VAN}_B(10\%)=-10+6(1+0,10)^{-1}+6,5(1+0,10)^{-2}=826,45$

2. **Homogeneizar los proyectos**
Hacemos el mínimo común múltiplo de las duraciones de los proyectos, en este caso 6 años. Por lo tanto, el proyecto A se repite 2 veces y el proyecto B 3 veces.

```plaintext
   -10     2,5    4,5    6,5
                         -10    2,5    4,5    6,5
A    |------|------|------|------|------|------|
     0      1      2      3      4      5      6

   -10      6     6,5
                  -10     6     6,5
                                -10     6     6,5
B    |------|------|------|------|------|------|
     0      1      2      3      4      5      6
```
<br>

$\text{VAN}_A^H(10\%)=-10+2,5(1+0,10)^{-1}+4,5(1+0,10)^{-2}+(6,5-10)(1+0,10)^{-3}+2,5(1+0,10)^{-4}+4,5(1+0,10)^{-5}+(6,5)(1+0,10)^{-6}=\boxed{\text{VAN}_A(10\%)[1+(1+0,10)^{-3}]}$

$\text{VAN}_B^H(10\%)=-10+6(1+0,10)^{-1}+(6,5-10)(1+0,10)^{-2}+6(1+0,10)^{-3}+(6,5-10)(1+0,10)^{-4}+6(1+0,10)^{-5}+6,5(1+0,10)^{-6}=\boxed{\text{VAN}_B(10\%)[1+(1+0,10)^{-2}+(1+0,10)^{-4}]}$

Como se puede ver, en vez de hacer el cálculo completo podemos utilizar el VAN inicial y actualizarlo según los años en los que lo hemos repetido:
$$\boxed{\text{VAN}_X^H=\text{VAN}_X[1+(1+0,10)^{-k}+...]}$$

Podemos hacer lo mismo con el TIR:
$\text{TIR}_A\rightarrow-10+2,5(1+i_A)+4,5(1+i_A)^{-2}+6,5(1+i_A)^{-3}=14,22\%$
$\text{TIR}_B\rightarrow-10+6(1+i_B)^{-1}+6,5(1+i_B)^{-2}=16,02\%$

$\text{TIR}_A^H\rightarrow-10+2,5(1+i_A^H)+4,5(1+i_A^H)^{-2}+(6,5-10)(1+i_A^H)^{-3}+2,5(1+i_A^H)^{-4}+4,5(1+i_A^H)^{-5}+(6,5)(1+i_A^H)^{-6}=14,22\%$
$\text{TIR}_B^H\rightarrow-10+6(1+i_B^H)^{-1}+(6,5-10)(1+i_B^H)^{-2}+6(1+i_B^H)^{-3}+(6,5-10)(1+i_B^H)^{-4}+6(1+i_B^H)^{-5}+6,5(1+i_B^H)^{-6}=16,02\%$

Observamos que el TIR no cambia, ya que el TIR es un tipo de interés y no depende del tiempo. Por lo tanto, el TIR de los proyectos homogéneos es el mismo que el de los proyectos individuales. Significa que si el proyecto se repite **con exactamente los mismos términos** no habrá variación en el TIR.


### 6.2.2 - Homogeneización de proyectos de inversión con distinto desembolso inicial y misma duración
Distintas posibilidades, una es tomar como referencia el proyecto con mayor desembolso e incrementar en el resto el desembolso y los flujos proporcionalmente. Se puede hacer a la inversa.

#### Ejemplo de clase:

| s   | $C_s$ Proyecto A | $C_s$ Proyecto B |
| --- | ---------------- | ---------------- |
| 0   | -10.000          | -12.000          |
| 1   | 2.500            | 5.200            |
| 2   | 4.500            | 5.200            |
| 3   | 6.500            | 5.200            |

```plaintext
    -10    2,5    4,5    6,5
A    |------|------|------|
     0      1      2      3

    -12    5,2    5,2    5,2
B    |------|------|------|
     0      1      2      3
```

1. **Valorar individualmente cada proyecto**
$\text{VAN}_A(10\%)=-10+2,5(1+0,10)^{-1}+4,5(1+0,10)^{-2}+6,5(1+0,10)^{-3}=875,28$
$\text{VAN}_B(10\%)=-12+5,2(1+0,10)^{-1}+5,2(1+0,10)^{-2}+5,2(1+0,10)^{-3}=931,63$

$\text{TIR}_A\rightarrow-10+2,5(1+i_A)^{-1}+4,5(1+i_A)^{-2}+6,5(1+i_A)^{-3}=14,22\%$
$\text{TIR}_B\rightarrow-12+5,2(1+i_B)^{-1}+5,2(1+i_B)^{-2}+5,2(1+i_B)^{-3}=14,36\%$

2. **Homogeneizar los proyectos**
Cogeré el de menor desembolso inicial, en este caso el A, y le aplicaré la relación entre ambos. Como todo cambia proporcionalmente puedo aplicar la proporción directamente sobre el VAN, quedando:

$\text{VAN}_A^H(10\%)=\frac{12}{10}\text{VAN}_A=1050,336$
$\text{VAN}_B^H(10\%)=\text{VAN}_B(10\%)=931,63$

Si hubiéramos comparado con los datos iniciales habríamos asumido que el proyecto B es mejor, sin embargo al homogeneizar queda claro que el proyecto A es mejor. Por lo tanto, **siempre homogeneizar**.

### 6.2.3 - Homogeneización de proyectos de inversión con distinto desembolso inicial y distinta duración

| s   | $C_s$ Proyecto A | $C_s$ Proyecto B | $C_s$ Proyecto C |
| --- | ---------------- | ---------------- | ---------------- |
| 0   | -3000            | -4000            | -8000            |
| 1   | 1000             | 1600             | 1600             |
| 2   | 1000             | 1600             | 1600             |
| 3   | 1000             | 2200             | 1600             |
| 4   | 1300             |                  | 1600             |
| 5   |                  |                  | 1600             |
| 6   |                  |                  | 1600             |
| 7   |                  |                  | 1600             |
| 8   |                  |                  | 1600             |
| 9   |                  |                  | 2800             |

```plaintext
   -3000  1000   1000   1000   1300
A    |------|------|------|------|
     0      1      2      3      4

   -4000   1600   1600   2200
B    |------|------|------|
     0      1      2      3

   -8000   1600   1600   1600   1600   1600   1600   1600   1600   2800
C    |------|------|------|------|------|------|------|------|------|
     0      1      2      3      4      5      6      7      8      9
```

1. **Valorar individualmente cada proyecto**
$\text{VAN}_A(10\%)=374,77$
$\text{VAN}_B(10\%)=429,75$
$\text{VAN}_C(10\%)=\bold{1723,36}$

$\text{TIR}_A=15,42\%$
$\text{TIR}_B=\bold{15,68\%}$
$\text{TIR}_C=14,92\%$

2. **Homogeneizar los proyectos**
Primero homogeneizar por duración, el mínimo común múltiplo de los años es 36. Por lo tanto, el proyecto A se repite 9 veces, el proyecto B 12 veces y el proyecto C 4 veces.

$\text{VAN}_A^H(10\%)=\text{VAN}_A(10\%)[1+(1+0,10)^{-4}+(1+0,10)^{-8}+(1+0,10)^{-12}+(1+0,10)^{-16}+(1+0,10)^{-20}+(1+0,10)^{-24}+(1+0,10)^{-28}+(1+0,10)^{-32}]=1144,04$

$\text{VAN}_B^H(10\%)=\text{VAN}_B(10\%)[1+(1+0,10)^{-3}+(1+0,10)^{-6}+(1+0,10)^{-9}+(1+0,10)^{-12}+(1+0,10)^{-15}+(1+0,10)^{-18}+(1+0,10)^{-21}+(1+0,10)^{-24}+(1+0,10)^{-27}+(1+0,10)^{-30}+(1+0,10)^{-33}]=1672,18$

$\text{VAN}_C^H(10\%)=\text{VAN}_C(10\%)[1+(1+0,10)^{-9}+(1+0,10)^{-18}+(1+0,10)^{-27}]=2895,64$

^ **ALGO ESTA MAL**, EL PROYECTO B DEBERIA SER EL MEJOR, dejo las soluciones de la profe:
A = 9152,34
B = 10033,16
C = 8686,91 (?)


Después homogeneizamos por capitales:


[`TODO homogeneizar`]



