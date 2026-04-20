Tags: #programacion #prolog #logica #IA

Prolog (Programming in Logic) es un lenguaje de programación **declarativo**. En lugar de decirle a la computadora *cómo* hacer algo (paso a paso), le describes la situación (hechos) y las reglas que la gobiernan. Prolog usará la **lógica** y el **backtracking** para encontrar respuestas a tus preguntas (consultas).

---

## 🧱 Componentes Básicos

Todo programa en Prolog se compone de una **Base de Conocimiento** (Knowledge Base o KB), que se define mediante hechos y reglas.
### 1. Hechos (Facts)

Los hechos son declaraciones que se asumen como **verdaderas incondicionalmente**. Definen las relaciones entre objetos.

* **Sintaxis:** `predicado(argumento1, argumento2).`
* Empiezan con minúscula.
* Terminan con un punto (`.`).

**Ejemplo de Hechos:**
```Prolog
% 'juan' es padre de 'ana'.
padre(juan, ana).

% 'ana' es madre de 'diego'.
madre(ana, diego).

% 'juan' es hombre.
hombre(juan).
mujer(ana).
hombre(diego).

% A 'ana' le gusta el 'chocolate'.
le_gusta(ana, chocolate).
````

### 2. Reglas (Rules)

Las reglas definen relaciones que son **verdaderas si otras condiciones (premisas) son verdaderas**. Permiten inferir nuevos conocimientos a partir de los hechos.

- **Sintaxis:** `cabeza :- cuerpo.`
- La `cabeza` es la conclusión.
- El `:-` se lee como "si" (es el "cuello" de la cláusula).
- El `cuerpo` son las condiciones o premisas.
- La coma (`,`) en el cuerpo significa "Y" lógico (conjunción).
- El punto y coma (`;`) significa "O" lógico (disyunción).

**Ejemplo de Reglas:**

```Prolog
% A es abuelo de C SI A es padre de B Y B es progenitor de C.
abuelo(A, C) :- 
    padre(A, B),
    progenitor(B, C).

% B es progenitor de C SI B es padre de C O B es madre de C.
progenitor(B, C) :- padre(B, C).
progenitor(B, C) :- madre(B, C).

% A y B son hermanos SI tienen el mismo padre Y tienen la misma madre Y A es diferente de B.
hermanos(A, B) :-
    progenitor(P, A),
    progenitor(P, B),
    progenitor(M, A),
    progenitor(M, B),
    A \= B. % \= significa "no unificable" o "diferente"
```

### 3. Consultas (Queries)

Las consultas son las **preguntas** que hacemos a la base de conocimiento. Prolog intentará **unificar** la consulta con los hechos y reglas para encontrar una respuesta.

- Se escriben en la terminal de Prolog, que usualmente muestra `?-`.
- Las **Variables** (que buscan un valor) siempre empiezan con Mayúscula o guion bajo (`_`).

**Ejemplo de Consultas (usando los hechos y reglas anteriores):**

```Prolog
% ¿Es juan padre de ana?
?- padre(juan, ana).
% Respuesta: true.

% ¿De quién es padre juan?
?- padre(juan, X).
% Respuesta: X = ana.

% ¿Quién es el abuelo de diego?
?- abuelo(Abuelo, diego).
% Respuesta: Abuelo = juan.

% ¿Le gusta el chocolate a ana?
?- le_gusta(ana, chocolate).
% Respuesta: true.

% ¿A quién le gusta el chocolate?
?- le_gusta(Quien, chocolate).
% Respuesta: Quien = ana.
```

---

## 🗂️ Estructuras de Datos

### Listas

La lista es la estructura de datos **más importante** en Prolog. Es una colección ordenada de elementos.

- **Lista vacía:** `[]`
- **Lista con elementos:** `[1, 2, 3]`, `[a, b, c]`, `[gato, [perro, 5]]`

#### El Patrón Cabeza | Cola (Head | Tail)

Prolog procesa las listas de forma recursiva usando el separador `|` (pipe).

- `[H | T]`
- `H` (Head): Es el **primer elemento** de la lista.
- `T` (Tail): Es el **resto de la lista** (que es, a su vez, otra lista).

**Ejemplo de unificación con listas:**

```Prolog
% Unificar [a, b, c] con [H|T]
?- [a, b, c] = [H|T].
% Respuesta: H = a, T = [b, c].

% Unificar [a] con [H|T]
?- [a] = [H|T].
% Respuesta: H = a, T = [].

% Unificar [] con [H|T]
?- [] = [H|T].
% Respuesta: false. (La lista vacía no tiene cabeza)
```

#### Ejemplo de Reglas con Listas: `miembro/2`

Esta regla comprueba si un elemento (`X`) pertenece a una lista (`L`).

```Prolog
% Caso Base: X es miembro si es la cabeza de la lista.
miembro(X, [X | _T]). % No nos importa la cola (_T)

% Caso Recursivo: X es miembro si pertenece a la cola de la lista.
miembro(X, [_H | T]) :- 
    miembro(X, T).
```

**Consultas de ejemplo:**

```Prolog
?- miembro(2, [1, 2, 3]).
% Respuesta: true.

?- miembro(5, [1, 2, 3]).
% Respuesta: false.
```

### "Arreglos" (Arrays) - Aclaración

Prolog **no tiene arreglos (arrays)** en el sentido tradicional (como en C, Java o Python) donde se accede a elementos por un índice (ej: `mi_array[3]`).

La estructura de datos que cumple esa función es la **Lista**.

Si se necesita acceso indexado (aunque es poco idiomático en Prolog), se suelen usar **estructuras** o **términos** (Functors). Por ejemplo, se podría representar un "array" `[a, b, c]` como `mi_array(a, b, c)`. Prolog tiene predicados como `arg/3` para acceder al N-ésimo argumento de un término, pero esto es mucho menos común que el procesamiento recursivo de listas.

> **Conclusión:** Para colecciones de datos, siempre piensa en **Listas** primero.

---

## 🚀 Ejemplo Completo: `concatenar/3`

Este es un ejemplo clásico que usa recursividad de listas para unir dos listas. `concatenar(L1, L2, L3)` significa "L3 es el resultado de unir L1 y L2".

``` Prolog
% Caso Base: Concatenar una lista vacía con L2 da como resultado L2.
concatenar([], L2, L2).

% Caso Recursivo:
% Para concatenar [H|T1] con L2:
% 1. La cabeza de la lista resultante (L3) debe ser H.
% 2. La cola de la lista resultante (T3) debe ser la concatenación de T1 y L2.
concatenar([H | T1], L2, [H | T3]) :-
    concatenar(T1, L2, T3).
```

**Consultas de ejemplo:**

``` Prolog
% ¿Cuál es el resultado de unir [a, b] y [c, d]?
?- concatenar([a, b], [c, d], Resultado).
% Respuesta: Resultado = [a, b, c, d].

% ¿Qué listas (X e Y) unidas dan [1, 2, 3]?
% Prolog usará backtracking para encontrar TODAS las soluciones.
?- concatenar(X, Y, [1, 2, 3]).
% Respuesta 1: X = [], Y = [1, 2, 3]
% Respuesta 2: X = [1], Y = [2, 3]
% Respuesta 3: X = [1, 2], Y = [3]
% Respuesta 4: X = [1, 2, 3], Y = []
```