## Ejercicio 2

Establecer el orden de la ecuación diferencial ordinaria dada. Determinar si la ecuación es lineal o no. Escribir la ecuación diferencial de forma general y de forma normal.
### **(a)**

$$\frac{d^2y}{dx^2} - xy \left(\frac{dy}{dx}\right)^3 = \sin x$$

- **Orden:** 2 (La derivada más alta es la segunda derivada $\frac{d^2y}{dx^2}$).
    
- **Linealidad:** **No lineal**. El término $xy \left(\frac{dy}{dx}\right)^3$ multiplica a la variable dependiente $y$ por su derivada, y además la derivada está elevada al cubo.
    
- **Forma general:** Todo igualado a cero.
    
    $$\frac{d^2y}{dx^2} - xy \left(\frac{dy}{dx}\right)^3 - \sin x = 0$$
    
- **Forma normal:** Despejando la derivada de mayor orden.
    
    $$\frac{d^2y}{dx^2} = \sin x + xy \left(\frac{dy}{dx}\right)^3$$
    

---

### **(b)**

$$2y'' = 2 - y$$

- **Orden:** 2 (La derivada más alta es $y''$).
    
- **Linealidad:** **Lineal**. No hay potencias ni productos entre la variable dependiente $y$ y sus derivadas.
    
- **Forma general:**
    
    $$2y'' + y - 2 = 0$$
    
- **Forma normal:**
    
    $$y'' = 1 - \frac{y}{2}$$
    

---

### **(c)**

$$\left(\frac{dy}{dt}\right)^2 + t \frac{d^3y}{dt^3} = e^{-2t}$$

- **Orden:** 3 (La derivada más alta es la tercera derivada $\frac{d^3y}{dt^3}$).
    
- **Linealidad:** **No lineal**. La primera derivada está elevada al cuadrado en el término $\left(\frac{dy}{dt}\right)^2$.
    
- **Forma general:**
    
    $$t \frac{d^3y}{dt^3} + \left(\frac{dy}{dt}\right)^2 - e^{-2t} = 0$$
    
- **Forma normal:**
    
    $$\frac{d^3y}{dt^3} = \frac{e^{-2t} - \left(\frac{dy}{dt}\right)^2}{t}$$
    

---

### **(d)**

$$(x^2 + y^2)y' - 2xy = x^2$$

- **Orden:** 1 (La única derivada presente es la primera derivada $y'$).
    
- **Linealidad:** **No lineal**. Al distribuir, obtenemos el término $y^2y'$, lo que significa que la variable dependiente está al cuadrado y multiplica a su derivada.
    
- **Forma general:**
    
    $$(x^2 + y^2)y' - 2xy - x^2 = 0$$
    
- **Forma normal:**
    
    $$y' = \frac{x^2 + 2xy}{x^2 + y^2}$$
    

---

### **(e)**

$$y^{(5)} - 5xy'' = xy' - 2xy - x^2$$

- **Orden:** 5 (La derivada más alta es $y^{(5)}$).
    
- **Linealidad:** **Lineal**. Todas las variables dependientes ($y$, $y'$, $y''$, $y^{(5)}$) están elevadas a la potencia 1 y sus coeficientes dependen únicamente de la variable independiente $x$.
    
- **Forma general:**
    
    $$y^{(5)} - 5xy'' - xy' + 2xy + x^2 = 0$$
    
- **Forma normal:**
    
    $$y^{(5)} = 5xy'' + xy' - 2xy - x^2$$
    

---

### **(f)**

$$\left(\frac{d\phi}{dt}\right)^3 + \frac{d^2\phi}{dt^2} + 5\phi^2 = \cos(t\pi)$$

_(Nota: Aquí la variable dependiente es $\phi$ y la independiente es $t$)_

- **Orden:** 2 (La derivada de mayor orden es $\frac{d^2\phi}{dt^2}$).
    
- **Linealidad:** **No lineal**. La primera derivada está al cubo y la variable $\phi$ está al cuadrado.
    
- **Forma general:**
    
    $$\frac{d^2\phi}{dt^2} + \left(\frac{d\phi}{dt}\right)^3 + 5\phi^2 - \cos(t\pi) = 0$$
    
- **Forma normal:**
    
    $$\frac{d^2\phi}{dt^2} = \cos(t\pi) - \left(\frac{d\phi}{dt}\right)^3 - 5\phi^2$$
    

---

### **(g)**

$$\frac{d^4x}{dy^4} - y\left(\frac{d^2x}{dy^2}\right)^3 + \frac{d^2x}{dy^2} + 5x^2 = y^2 - y + 1$$

_(Nota importante: Aquí se han invertido los roles tradicionales. La variable dependiente es $x$ y la independiente es $y$)_

- **Orden:** 4 (La derivada más alta es $\frac{d^4x}{dy^4}$).
    
- **Linealidad:** **No lineal**. La segunda derivada de la variable dependiente $\left(\frac{d^2x}{dy^2}\right)$ está elevada al cubo, y la variable dependiente $x$ está elevada al cuadrado ($5x^2$).
    
- **Forma general:**
    
    $$\frac{d^4x}{dy^4} - y\left(\frac{d^2x}{dy^2}\right)^3 + \frac{d^2x}{dy^2} + 5x^2 - y^2 + y - 1 = 0$$
    
- **Forma normal:**
    
    $$\frac{d^4x}{dy^4} = y\left(\frac{d^2x}{dy^2}\right)^3 - \frac{d^2x}{dy^2} - 5x^2 + y^2 - y + 1$$