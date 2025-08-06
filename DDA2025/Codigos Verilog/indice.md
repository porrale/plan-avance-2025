# Ejemplos Básicos en Verilog

Este documento contiene una colección de ejemplos de diseño digital en Verilog, con sus enlaces correspondientes para simular directamente en [EDA Playground](https://www.edaplayground.com).

---

## ✅ Ejemplo 1: Compuerta AND

**Descripción:** Implementación de una compuerta AND de 2 entradas con su testbench.

🔗 [Ver en EDA Playground](https://www.edaplayground.com/x/wuv4)

---

## 🔜 Ejemplo 2: Compuerta OR
🔗 [Ver en EDA Playground](https://www.edaplayground.com/x/MfUb)



---

¡Claro! Acá tenés una **explicación paso a paso en texto** de cada uno de los dos ejemplos que faltaban: **multiplexor 2:1** y **sumador completo (full adder)**, ideal para entender cómo funcionan antes de escribir el código.

---

## 🧠 Ejemplo 3: Multiplexor 2:1
🔗 [Ver en EDA Playground](https://www.edaplayground.com/x/GyRe)


### 🔷 ¿Qué es un multiplexor?

Un **multiplexor** (MUX) es un componente que selecciona una de varias señales de entrada y la dirige a la salida, según el valor de un selector.

En un **multiplexor 2:1**, hay:

* 2 entradas de datos (`a` y `b`)
* 1 señal de selección (`sel`)
* 1 salida (`y`)

El comportamiento es:

* Si `sel = 0` → `y = a`
* Si `sel = 1` → `y = b`

### 🔧 ¿Cómo se implementa en Verilog?

Usamos una **asignación condicional** (`? :`) para seleccionar qué entrada se conecta a la salida según `sel`.

```verilog
assign y = (sel) ? b : a;
```

Este código dice literalmente:

> “Si `sel` vale 1, asigná `b` a `y`. Si no, asigná `a`.”

### 🔬 ¿Cómo se prueba?

Creamos un testbench donde:

* Fijamos valores a `a` y `b`
* Cambiamos `sel` entre 0 y 1
* Verificamos si `y` cambia como corresponde

Por ejemplo:

* Si `a=0`, `b=1` y `sel=0`, esperamos `y=0` (valor de `a`)
* Si `a=0`, `b=1` y `sel=1`, esperamos `y=1` (valor de `b`)

---

## 🧠 Ejemplo 4: Sumador completo (Full Adder)
🔗 [Ver en EDA Playground](https://www.edaplayground.com/x/GyRe)



### 🔷 ¿Qué hace un sumador completo?

Un **full adder** suma tres bits de entrada:

* `a` (bit 1)
* `b` (bit 2)
* `cin` (acarreo de entrada, viene de un bit menos significativo)

Y entrega:

* `sum` (resultado de la suma en esa posición)
* `cout` (acarreo de salida, que se suma en el siguiente bit)

### 📚 Tabla de verdad de un full adder:

| a | b | cin | sum | cout |
| - | - | --- | --- | ---- |
| 0 | 0 | 0   | 0   | 0    |
| 0 | 0 | 1   | 1   | 0    |
| 0 | 1 | 0   | 1   | 0    |
| 0 | 1 | 1   | 0   | 1    |
| 1 | 0 | 0   | 1   | 0    |
| 1 | 0 | 1   | 0   | 1    |
| 1 | 1 | 0   | 0   | 1    |
| 1 | 1 | 1   | 1   | 1    |

### 🧠 ¿Cómo se calcula en lógica?

#### Para la suma (`sum`):

* Se usa el **XOR**: `sum = a ^ b ^ cin`

  * XOR de 3 bits se comporta como una suma binaria sin acarreo

#### Para el acarreo (`cout`):

* Se usa esta fórmula lógica:
  `cout = (a & b) | (cin & (a ^ b))`

  * Si `a` y `b` son 1, hay acarreo
  * Si `cin` y uno solo de `a` o `b` es 1, también hay acarreo

### 🔬 ¿Cómo se prueba?

Se prueban **todas las combinaciones posibles** de `a`, `b`, `cin` (son 3 bits → 8 combinaciones) y se observa `sum` y `cout`.

Ejemplo:

* Entrada: `a=1`, `b=1`, `cin=1` → suma binaria: `1 + 1 + 1 = 3` (en binario: `11`)

  * `sum = 1`
  * `cout = 1`

---

¿Querés que te lo pase como archivo de texto para imprimir o estudiar offline? También puedo incluir dibujos de tablas de verdad o circuitos si te sirve.


- Todos los ejemplos están escritos en Verilog clásico.
- Usar **Icarus Verilog** como simulador en EDA Playground.

