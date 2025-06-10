# reto-07
### 1. Imprimir un listado con los números del 1 al 100 cada uno con su respectivo cuadrado.

``` python
# La función range(1, 101) genera una secuencia de números desde 1 hasta 100 (el 101 no se incluye).
for i in range(1, 101):
    # Imprimimos el número actual y su cuadrado.
    # i**2 calcula el cuadrado del número i.
    print(f"{i} al cuadrado es {i**2}")
```

### 2. Imprimir un listado con los números impares desde 1 hasta 999 y seguidamente otro listado con los números pares desde 2 hasta 1000.

``` python
# Imprime los números impares del 1 al 999
print("Números impares del 1 al 999:")
# Usamos range(1, 1000, 2) para generar números desde 1 hasta 999, incrementando de 2 en 2.
for i in range(1, 1000, 2):
    print(i)

# Imprime los números pares del 2 al 1000
print("Números pares del 2 al 1000:")
# Usamos range(2, 1001, 2) para generar números desde 2 hasta 1000, también en pasos de 2.
for i in range(2, 1001, 2):
    print(i)

```

### 3. Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado

``` python
# Leer un número natural n
n = int(input("Ingrese un número natural (n ≥ 2): "))

# Verificar que n sea válido
if n >= 2:
    print(f"Números pares desde {n} hasta 2 en orden descendente:")
    for i in range(n, 1 - 1, -1):  # De n hasta 2 (inclusive), descendiendo
        if i % 2 == 0:
            print(i)
else:
    print("El número debe ser mayor o igual a 2.")
```

### 4. Imprimir los números de 1 hasta un número natural n dado, cada uno con su respectivo factorial

``` python
# Solicitamos al usuario que ingrese un número entero.
numero = int(input("Ingrese el número para hallar su factorial: "))

# Inicializamos la variable factorial en 1, ya que el factorial de 0 es 1 y es el valor neutro de la multiplicación.
factorial = 1

# Usamos un bucle for para calcular el factorial.
# El rango va desde 1 hasta numero (inclusive), por eso usamos range(1, numero + 1)
for i in range(1, numero + 1):
    factorial *= i  # Multiplicamos el valor actual de factorial por el número actual i.
    print(f"El factorial de {i} es {factorial}")  # Mostramos el factorial parcial en cada iteración.

```

### 5. Calcular el valor de 2 elevado a la potencia n usando ciclos for.

``` python
# Solicitamos al usuario que ingrese la potencia a la que se desea elevar el número 2.
potencia = int(input("Ingrese la potencia: "))

# Inicializamos la variable resultado en 1, ya que cualquier número elevado a 0 es 1.
resultado = 1

# Utilizamos un bucle for para multiplicar 2 por sí mismo tantas veces como indique la potencia.
for i in range(0, potencia):
    resultado *= 2  # En cada iteración, multiplicamos el resultado por 2.

# Finalmente, mostramos el resultado de 2 elevado a la potencia ingresada.
print(f"2 elevado a la {potencia} es {resultado}")

```

### 6. Leer un número natural n, leer otro dato de tipo real x y calcular x^n usando ciclos for.

``` python
# Solicita al usuario un número real como base
numero = float(input("Ingrese el valor que desea elevar: "))

# Solicita al usuario un número entero como exponente
potencia = int(input("Ingrese la potencia (entera): "))

# Inicializa el resultado en 1 
resultado = 1

# Multiplica 'numero' por sí mismo 'potencia' veces
for i in range(potencia):
    resultado *= numero

# Muestra el resultado final
print(f"{numero} elevado a la {potencia} es {resultado}")

```

### 7. Diseñe un programa que muestre las tablas de multiplicar del 1 al 9.

``` python
# Bucle externo: recorre los números del 1 al 9 (cada tabla de multiplicar)
for i in range(1, 10):
    print(f"\nTabla del {i}")  # Imprime el encabezado de la tabla actual

    # Bucle interno: recorre del 1 al 10 para multiplicar por i
    for j in range(1, 11):
        print(f"{i} * {j} = {i * j}")  # Imprime la multiplicación

```

### 8. Diseñar una función que permita calcular una aproximación de la función exponencial alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Taylor.

``` python
import math

def exp_aproximado(x, n):
    suma = 0
    for i in range(n + 1):
        suma += (x ** i) / math.factorial(i)
    return suma

# Leer datos
x = float(input("Ingrese un número real x: "))
n = int(input("Ingrese un número natural n: "))

# Calcular y mostrar resultados
aproximado = exp_aproximado(x, n)
real = math.exp(x)
diferencia = abs(real - aproximado)

print(f"\nAproximación de e^{x} con {n} términos: {aproximado}")
print(f"Valor real con math.exp: {real}")
print(f"Diferencia: {diferencia}")
```

### 9. Diseñar una función que permita calcular una aproximación de la función seno alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Maclaurin.

``` python
import math

def seno_aproximado(x, n):
    suma = 0
    for i in range(n):
        signo = (-1) ** i
        numerador = x ** (2 * i + 1)
        denominador = math.factorial(2 * i + 1)
        suma += signo * (numerador / denominador)
    return suma

# Leer datos
x = float(input("Ingrese un número real x (en radianes): "))
n = int(input("Ingrese el número de términos n: "))

# Calcular y mostrar resultados
aproximado = seno_aproximado(x, n)
real = math.sin(x)
diferencia = abs(real - aproximado)

print(f"\nAproximación de sin({x}) con {n} términos: {aproximado}")
print(f"Valor real con math.sin: {real}")
print(f"Diferencia: {diferencia}")
```
