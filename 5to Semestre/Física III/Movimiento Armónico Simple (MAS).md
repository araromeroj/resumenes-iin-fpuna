
## 1. Conceptos Fundamentales

- **Movimiento Periódico:** Movimiento rectilíneo o curvilíneo que se repite regularmente en intervalos de tiempo idénticos.

- **Movimiento Oscilatorio:** Movimiento de vaivén en el cual una partícula oscila entre dos puntos equidistantes siguiendo exactamente la misma trayectoria.

- **Movimiento Armónico Simple (MAS):** Caso particular de movimiento oscilatorio y periódico sobre un medio sin fricción, donde las variables cinemáticas ($x$, $v$, $a$) se expresan mediante funciones armónicas (seno o coseno).

- **Amplitud ($A$):** Desplazamiento o posición máxima de la partícula respecto al punto de equilibrio ($x = 0$).

- **Fase inicial ($\varphi$):** Constante angular que define el estado cinemático inicial del movimiento en $t = 0$.

- **Fase del movimiento:** Ángulo total en un instante determinado, expresado como $(\omega t + \varphi)$.

- **Frecuencia angular ($\omega$):** Velocidad angular o pulsación del movimiento oscilatorio, expresada en $\text{rad/s}$.

- **Periodo ($T$):** Tiempo total invertido por la partícula para efectuar un ciclo u oscilación completa.

- **Frecuencia ($f$):** Cantidad de oscilaciones completas realizadas por unidad de tiempo ($\text{Hz}$ o $\text{s}^{-1}$).    

## 2. Sistema Masa-Resorte Horizontal

> [!info] Dinámica del Sistema Para un objeto de masa $m$ unido a un resorte de constante elástica $k$ sobre una superficie horizontal sin rozamiento:
> 
>   

- **Ley de Hooke (Fuerza Restauradora):**$$F_s = -k x$$
- **Segunda Ley de Newton:**$$F_s = m a_x \implies -k x = m a_x \implies a_x = -\frac{k}{m} x$$

### Ecuaciones Cinemáticas

- **Posición:**$$x(t) = A \cos(\omega t + \varphi)$$
-  **Velocidad Instantánea:** $$v(t) = \frac{dx}{dt} = -\omega A \sin(\omega t + \varphi)$$
- **Aceleración Instantánea:** $$a(t) = \frac{d^2x}{dt^2} = -\omega^2 A \cos(\omega t + \varphi) = -\omega^2 x(t)$$
### Valores Extremos

- **Rapidez Máxima:** $$v_{\text{máx}} = \omega A = \sqrt{\frac{k}{m}} A$$
(Ocurre al cruzar el punto de equilibrio $x = 0$).    
- **Aceleración Máxima:** $$a_{\text{máx}} = \omega^2 A = \frac{k}{m} A$$
(Ocurre en los extremos de máxima amplitud $x = \pm A$).

### Parámetros Oscilatorios

- **Frecuencia Angular:** $$\omega = \sqrt{\frac{k}{m}}$$
- **Periodo de Oscilación:** $$T = \frac{2\pi}{\omega} = 2\pi \sqrt{\frac{m}{k}}$$
- **Frecuencia:** $$f = \frac{1}{T} = \frac{\omega}{2\pi} = \frac{1}{2\pi} \sqrt{\frac{k}{m}}$$

## 3. Péndulo Físico

> [!note] Descripción Rotacional Sistema compuesto por un cuerpo rígido de masa $m$ que oscila en torno a un eje fijo $O$ separado una distancia $d$ de su centro de masa ($CM$).
> 
>   

- **Segunda Ley de Newton para Rotación:** $$\sum \tau = I \alpha \implies -m g d \sin\theta = I \frac{d^2\theta}{dt^2}$$
- **Aproximación de Pequeños Ángulos ($\sin\theta \approx \theta$):** $$\frac{d^2\theta}{dt^2} + \left(\frac{m g d}{I}\right) \theta = 0$$
- **Frecuencia Angular:** $$\omega = \sqrt{\frac{m g d}{I}}$$
- **Periodo de Oscilación:** $$T = \frac{2\pi}{\omega} = 2\pi \sqrt{\frac{I}{m g d}}$$
(Donde $I$ es el momento de inercia respecto al eje de rotación $O$).

## 4. Balance Energético

En ausencia de fuerzas no conservativas (fricción), la energía mecánica total $E$ del oscilador permanece constante:

- **Energía Cinética ($K$):** $$K = \frac{1}{2} m v^2 = \frac{1}{2} m \omega^2 A^2 \sin^2(\omega t + \varphi) = \frac{1}{2} k A^2 \sin^2(\omega t + \varphi)$$
- **Energía Potencial Elástica ($U$):** $$U = \frac{1}{2} k x^2 = \frac{1}{2} k A^2 \cos^2(\omega t + \varphi)$$
- **Energía Mecánica Total ($E$):** $$E = K + U = \frac{1}{2} k A^2 \left[ \sin^2(\omega t + \varphi) + \cos^2(\omega t + \varphi) \right] = \frac{1}{2} k A^2$$
> [!important] Conservación de la Energía La energía mecánica total es constante y directamente proporcional al cuadrado de la amplitud ($E \propto A^2$).
> 
>   

## 5. Recordatorio: Ecuación Diferencial del MAS

La ecuación fundamental que rige cualquier sistema en MAS corresponde a una Ecuación Diferencial Ordinaria (EDO) homogénea de segundo orden con coeficientes constantes:
$$\frac{d^2x}{dt^2} + \omega^2 x = 0$$

1. **Ecuación Característica Asociada:** $$\lambda^2 + \omega^2 = 0 \implies \lambda = \pm i \omega$$
2. **Solución General Compleja:** $$x(t) = C_1 e^{i \omega t} + C_2 e^{-i \omega t}$$
3. **Conversión al Campo Real (Identidad de Euler $e^{i\theta} = \cos\theta + i\sin\theta$):** $$x(t) = B \cos(\omega t) + C \sin(\omega t)$$
    _O expresada en forma de amplitud y fase inicial:_ $$x(t) = A \cos(\omega t + \varphi)$$
    _Donde la amplitud es $A = \sqrt{B^2 + C^2}$ y el ángulo de fase satisface $\tan\varphi = -\frac{C}{B}$._