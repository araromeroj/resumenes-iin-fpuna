La Segunda Ley de Newton para la rotación ($\sum \tau = I \alpha$) es el análogo rotacional de la ecuación dinámica cartesiana ($\sum F = m a$), donde el torque neto aplicado sobre un cuerpo rígido produce una aceleración angular inversamente proporcional a su momento de inercia.

  

Para aplicarla correctamente en cualquier problema de física o ingeniería, se sigue un procedimiento sistemático de 5 pasos.

  

## Metodología Paso a Paso

> [!info] Paso 1: Definir el Eje de Rotación (Pivote)
> 
> Elige el punto de referencia $O$ sobre el cual gira el objeto. Si el cuerpo rota sobre un eje fijo (un pivote o bisagra), se selecciona dicho punto. Si el cuerpo rueda o vuela libremente en el espacio, se suele tomar el **Centro de Masa ($CM$)**.
> 
>   
> 
> - **Regla clave:** Tanto el torque ($\tau$) como el momento de inercia ($I$) deben calcularse estrictamente respecto al mismo eje $O$.
>     
>       
>     

> [!note] Paso 2: Dibujar el Diagrama de Cuerpo Libre (DCL) Extendido
> 
> A diferencia de la dinámica puntual, en rotación **sí importa el punto de aplicación** de cada fuerza.
> 
>   
> 
> 1. Dibuja la geometría real del cuerpo rígido.
>     
>       
>     
> 2. Grafica cada fuerza externa ($\vec{F}$) partiendo exactamente del punto físico donde se ejerce (ej. la gravedad actuando en el $CM$, la tensión en el borde, la normal y fricción en la superficie de contacto).
>     
>       
>     

> [!tip] Paso 3: Calcular el Torque ($\tau$) de cada Fuerza
> 
> Para cada fuerza identificada en el DCL, determina su vector posición $\vec{r}$ (distancia orientada desde el eje $O$ hasta el punto de aplicación de la fuerza).
> 
>   

La magnitud del torque viene dada por:

  

$$\tau = r F \sin\theta$$

Donde $\theta$ es el ángulo formado entre los vectores $\vec{r}$ y $\vec{F}$. Alternativamente, puedes usar el **brazo de palanca** ($d_\perp = r \sin\theta$):

  

$$\tau = F \cdot d_\perp$$

**Asignación de signos (Regla de la mano derecha):**

  

- **Torque positivo ($+$):** Si la fuerza tiende a hacer girar el cuerpo en sentido **antihorario**.
    
      
    
- **Torque negativo ($-$):** Si la fuerza tiende a hacer girar el cuerpo en sentido **horario**.
    
      
    

_(Nota: Las fuerzas cuya línea de acción pasa exactamente por el pivote $O$ tienen $r = 0$, por lo que su torque es cero)._

  

> [!math] Paso 4: Determinar el Momento de Inercia ($I$)
> 
> Calcula o busca el momento de inercia del objeto según su distribución de masa respecto al eje de giro $O$.
> 
>   

- Si el eje pasa por el centro de masa, utiliza la fórmula estándar de tabla (por ejemplo, para un disco $I_{CM} = \frac{1}{2}m R^2$, o para una barra $I_{CM} = \frac{1}{12}m L^2$).
    
      
    
- Si el eje no pasa por el $CM$ pero es paralelo a él, aplica el **Teorema de Steiner (ejes paralelos)**:
    
      
    
    $$I_O = I_{CM} + m d^2$$
    
    _(Donde $d$ es la distancia entre el eje $CM$ y el pivote $O$)._
    
      
    

> [!check] Paso 5: Formular la Ecuación $\sum \tau = I \alpha$ y Resolver
> 
> Suma algebraicamente todos los torques con sus respectivos signos e iguálalos al producto $I \alpha$:
> 
>   

$$\sum \tau = \tau_1 + \tau_2 + \dots = I \alpha$$

Dependiendo de lo que pida el problema:

  

- Si se buscan aceleraciones angulares: despeja directamente $\alpha$.
    
      
    
- Si el cuerpo también se desplaza (movimiento de rodadura): relaciona la aceleración angular con la aceleración lineal mediante $a = \alpha R$.
    
      
    
- Si se busca analizar oscilaciones (como en un péndulo): sustituye $\alpha = \frac{d^2\theta}{dt^2}$ para construir la ecuación diferencial del movimiento.
    
      
    

## Ejemplo Práctico: Barra Uniforme Pivotada en un Extremo

**Problema:** Una barra uniforme de masa $m$ y longitud $L$ cuelga verticalmente sujeta a un pivote sin fricción en su extremo superior $O$. Si se desplaza un ángulo pequeño $\theta$, halla la aceleración angular inicial.

  

```
(Pivote O)  o-----------
             \         |
              \ r=L/2  |
               \       v F_g = m g
                (CM)
```

1. **Eje de rotación:** Punto $O$ en el extremo superior.
    
      
    
2. **DCL:** La fuerza de gravedad $m g$ actúa verticalmente hacia abajo en el centro de masa ($CM$), que se ubica a $r = \frac{L}{2}$ del pivote. En el pivote actúan fuerzas de reacción $R_x$ y $R_y$.
    
      
    
3. **Cálculo de Torques respecto a $O$:**
    
      
    - Las reacciones $R_x$ y $R_y$ pasan por $O$ $\implies \tau_R = 0$.
        
          
        
    - La gravedad genera un torque que tiende a regresar la barra (sentido horario, signo negativo):
        
          
        
        $$\tau_g = - m g \left(\frac{L}{2}\right) \sin\theta$$
        
          
        
4. **Momento de inercia:** Para una barra rotando sobre uno de sus extremos:
    
      
    
    $$I_O = \frac{1}{3} m L^2$$
    
5. **Aplicación de $\sum \tau = I \alpha$:**
    
      
    
    $$- m g \left(\frac{L}{2}\right) \sin\theta = \left(\frac{1}{3} m L^2\right) \alpha$$
    

Despejando la aceleración angular $\alpha$:

$$\alpha = -\frac{3 g}{2 L} \sin\theta$$