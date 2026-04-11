## 1. Cuando quieres que pase una cosa "O" la otra (Regla de la Suma)

Usas la suma cuando te preguntan por la probabilidad de que ocurra el evento A **o** el evento B. Aquí es donde entra el concepto de si son excluyentes o no.
### Eventos Mutuamente Excluyentes (No pueden pasar a la vez):

Si un evento ocurre, es imposible que ocurra el otro al mismo tiempo. Por ejemplo, al tirar una moneda, no puede salir cara y cruz en el mismo tiro. Si la luz del semáforo está roja, no puede estar verde.

- **¿Qué se hace?** Simplemente **sumas** sus probabilidades.
- **Fórmula:** $P(A \cup B) = P(A) + P(B)$
- _Ejemplo:_ En el inciso "a" de tu primer ejercicio, calculamos la probabilidad de detenerse en el semáforo 4 **o** en el 6 **o** en el 9. Como no puedes detenerte por segunda vez en los tres lugares a la vez (son excluyentes), simplemente sumamos los tres resultados.
### Eventos No Excluyentes (Pueden pasar a la vez):

Pueden ocurrir al mismo tiempo. Por ejemplo, sacar una carta de una baraja que sea "Rey" **o** que sea "Corazones". Existe el Rey de Corazones, así que ambas cosas pueden pasar a la vez.

- **¿Qué se hace?** Sumas sus probabilidades, pero **restas la intersección** (la probabilidad de que pasen juntas) para no contarla dos veces.
- **Fórmula:** $P(A \cup B) = P(A) + P(B) - P(A \cap B)$

---

## 2. Cuando quieres que pase una cosa "Y" luego la otra (Regla de la Multiplicación)

Usas la multiplicación cuando necesitas que ocurra el evento A **y** también el evento B (una secuencia o al mismo tiempo). Aquí te preguntas si un evento afecta al otro.

### Eventos Independientes (No se afectan entre sí):

El resultado del primer evento no cambia la probabilidad del segundo. Por ejemplo, tirar una moneda dos veces. Lo que salga en el primer tiro no afecta al segundo. O los semáforos de tu ejercicio: que el primero esté en rojo no afecta el color del segundo.

- **¿Qué se hace?** Simplemente **multiplicas** sus probabilidades.
- **Fórmula:** $P(A \cap B) = P(A) \cdot P(B)$
- _Ejemplo:_ Si la probabilidad de cara es 0.5, la probabilidad de sacar cara **y** luego cara es $0.5 \cdot 0.5 = 0.25$.

--- 
## Eventos Dependientes (Uno afecta al otro):

El resultado del primer evento cambia la probabilidad del segundo. Por ejemplo, sacar dos cartas de una baraja _sin devolver la primera_. Si sacas un As en la primera, ahora quedan menos cartas en total y menos Ases para la segunda extracción.

- **¿Qué se hace?** Multiplicas la probabilidad del primero por la **probabilidad condicionada** del segundo (la probabilidad del segundo asumiendo que el primero ya pasó).
- **Fórmula:** $P(A \cap B) = P(A) \cdot P(B|A)$

---
# Resumen

>[!summary] En resumen:
>- Si la frase mental es **A "o" B** $\rightarrow$ **Suma** (y fíjate si debes restar la intersección).
>- Si la frase mental es **A "y" B** $\rightarrow$ **Multiplica** (y fíjate si el segundo evento cambió).
