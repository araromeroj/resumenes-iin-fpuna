# Modulación por Desplazamiento de Fase (PSK)

La **Modulación por Desplazamiento de Fase** (Phase Shift Keying o **PSK**) es una técnica de modulación digital en la que los datos se transmiten variando la **fase** de la onda portadora en momentos específicos.


![PSK_image](https://www.open.edu/openlearn/pluginfile.php/871656/mod_oucontent/oucontent/44735/596a8165/2d071fde/tm355_bk1_pt2_f020.eps.jpg)

## 1. Concepto Fundamental

En PSK, los valores binarios se representan mediante cambios en el ángulo de fase de la señal.

- La amplitud y la frecuencia de la portadora permanecen **constantes**.
    
- Lo que cambia es el **punto de inicio** de la onda (su fase).
    

## 2. Funcionamiento Técnico (BPSK)

La forma más básica es el **BPSK** (Binary PSK), donde se utilizan dos fases separadas por 180°:

- **Bit 1:** La fase comienza en 0°.
    
- **Bit 0:** La fase se desplaza 180° (la onda se "invierte").
    

Matemáticamente, la señal se expresa como:

$s(t) = A \cos(2\pi f_c t + \phi_i)$

Donde $ϕ_i​$ puede ser 0 (0°) o $π$ (180°) según el bit.

---

## 3. Variantes: De BPSK a QPSK

A diferencia de ASK o FSK, PSK permite enviar más de un bit por cada cambio en la señal (símbolo) usando más ángulos de fase:

- **BPSK (Binary PSK):** 2 fases, 1 bit por símbolo.

- **QPSK (Quadrature PSK):** 4 fases $(45°, 135°, 225°, 315°)$, lo que permite enviar **2 bits por símbolo**. Esto duplica la velocidad de transmisión sin aumentar el ancho de banda.


---

## 4. Ventajas y Desventajas

### Ventajas

- **Alta eficiencia:** Especialmente en sus versiones como QPSK, permite transmitir mucha información en poco ancho de banda.

- **Excelente inmunidad al ruido:** Es mucho más resistente a las interferencias que ASK.

- **Baja tasa de error:** Es muy eficiente en términos de potencia para la cantidad de datos que mueve.


### Desventajas

- **Complejidad técnica:** El receptor debe ser capaz de detectar cambios de fase muy precisos, lo que requiere circuitos de recuperación de portadora más complejos y costosos.

- **Sensibilidad al desfase:** Pequeños retardos en la señal pueden confundir al receptor.


---

## 5. Aplicaciones Comunes

- **Redes Wi-Fi:** Utilizan variantes de PSK para las conexiones inalámbricas.

- **Bluetooth:** Emplea técnicas basadas en el desplazamiento de fase.

- **Comunicaciones por Satélite:** Es el estándar debido a su gran eficiencia.

- **Telefonía móvil:** Fundamental en tecnologías 4G y 5G.