# Tarea 2 - Ejercicios Unidad 1
En esta página presento los ejercicios de la Unidad 1, cada uno con su enunciado original, mi solución en Python y una breve explicación.

## Reto 1: Simula el comportamiento de la tortuga usando solo print() e input()

**Enunciado:**  
Simula el movimiento de la tortuga sin usar la librería `turtle`, únicamente con texto, usando `print()`, `input()` y funciones.

**Código en Python:**

```python
def adelante(pasos):
    print("→" * pasos)

def abajo(pasos):
    for _ in range(pasos):
        print("↓")

def main():
    print("Simulación de la tortuga (solo con texto)")

    pasos_adelante = int(input("¿Cuántos pasos quieres avanzar hacia adelante? "))
    pasos_abajo = int(input("¿Cuántos pasos quieres avanzar hacia abajo? "))

    adelante(pasos_adelante)
    abajo(pasos_abajo)

main()

```



### Explicación
Este programa pide al usuario cuántos pasos debe avanzar la “tortuga”.
La función adelante() imprime flechas hacia la derecha (→), simulando movimiento horizontal.
La función abajo() imprime flechas hacia abajo (↓), simulando movimiento vertical.
Así se recrea el recorrido de la tortuga usando únicamente texto.

## Reto 2: Tortuga bajando

**Enunciado:**  
Crea el rastro de una tortuga moviéndose hacia abajo usando únicamente `print()` e `input()`.

**Código en Python:**

```python
def bajar(pasos):
    for _ in range(pasos):
        print("↓")

def main():
    print("Simulación de tortuga bajando")
    pasos = int(input("¿Cuántos pasos quieres que la tortuga baje? "))
    bajar(pasos)

main()
```


### Explicación
La función bajar() imprime flechas hacia abajo (↓), una por línea, simulando que la tortuga desciende.
El usuario elige cuántos pasos baja la tortuga, y el programa muestra el recorrido vertical en texto.

## Reto 3: Girar y dibujar usando solo print() e input()

**Enunciado:**  
Ahora la tortuga no solo avanza: también gira. Debes simular el comportamiento del siguiente código de turtle, pero usando solo texto:

`t.forward(100)`  
`t.right(90)`  
`t.forward(100)`

**Código en Python:**

```python
def adelante(pasos):
    print("→" * pasos)

def abajo(pasos):
    for _ in range(pasos):
        print("↓")

def main():
    print("Simulación de tortuga girando")

    pasos_adelante = int(input("¿Cuántos pasos quieres avanzar hacia adelante? "))
    pasos_abajo = int(input("¿Cuántos pasos quieres avanzar hacia abajo después del giro? "))

    adelante(pasos_adelante)
    print("Giro de 90° a la derecha")
    abajo(pasos_abajo)

main()
```

### Explicación
Primero la tortuga avanza hacia la derecha (→).
Luego se indica el giro con un mensaje: “Giro de 90° a la derecha”.
Finalmente, la tortuga avanza hacia abajo (↓).
El resultado es una figura en forma de “L”, igual que en la versión gráfica de turtle.

## Reto 4: Encapsular los comportamientos usando funciones

**Enunciado:**  
Reescribe los retos usando funciones que representen los movimientos de la tortuga solo con texto. Debes usar las funciones:

- `adelante(n)` → dibuja movimiento hacia la derecha  
- `abajo(n)` → dibuja movimiento hacia abajo  

Si se ejecuta:

### Explicación
Las funciones adelante() y abajo() encapsulan los movimientos de la tortuga. 
La primera imprime flechas hacia la derecha (→) en una misma línea, y la segunda imprime flechas hacia abajo (↓) una por línea. 
Al combinar ambas se obtiene un dibujo en forma de “L”, tal como ocurre en la versión gráfica de turtle.

## Reto 5: La tortuga baja las escaleras

**Enunciado:**  
Ajusta tus funciones para que la tortuga pueda bajar escalones.  
Cada escalón debe conservar la posición horizontal acumulada y dibujar correctamente tanto el tramo horizontal como el vertical.

```python
posicion_actual = 0

def adelante(n):
    global posicion_actual
    print("-" * n + ">")
    posicion_actual += n

def abajo(n):
    global posicion_actual
    for _ in range(n - 1):
        print(" " * posicion_actual + "|")
    print(" " * posicion_actual + "v")

# Ejemplo: tres escalones
adelante(5)
abajo(2)

adelante(5)
abajo(2)

adelante(5)
abajo(2)
```

### Explicación
El programa utiliza una variable llamada posicion_actual para recordar cuánto ha avanzado horizontalmente la tortuga.
Esto permite que, al bajar, las líneas verticales aparezcan correctamente alineadas, formando escalones.
