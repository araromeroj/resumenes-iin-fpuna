# Modulación por Desplazamiento de Amplitud (ASK)

La **Modulación por Desplazamiento de Amplitud** (Amplitude Shift Keying o **ASK**) es una forma de modulación digital donde los datos digitales se representan como variaciones en la amplitud de una onda portadora.


![ASK_image|600x300](https://www.open.edu/openlearn/pluginfile.php/871656/mod_oucontent/oucontent/44735/596a8165/8d9dd44b/tm355_bk1_pt2_f018.eps.jpg)

## 1. Concepto Fundamental

En ASK, la fuerza (amplitud) de la señal portadora analógica varía conforme a los valores binarios (0 y 1) de la señal de datos.

- La frecuencia y la fase de la portadora permanecen **constantes**.

- Solo cambia la **amplitud**.


## 2. Funcionamiento Técnico

Para una señal binaria, el proceso se puede resumir de la siguiente manera:

- **Bit 1:** Se transmite la onda portadora con una amplitud máxima determinada.

- **Bit 0:** Se transmite la onda portadora con una amplitud reducida (o nula).


Matemáticamente, la señal modulada s(t) se puede expresar como:

s(t)=Ai​cos(2πfc​t)

Donde:

- $A_i$​ es la amplitud que cambia según el bit de datos.

- $f_c$​ es la frecuencia de la portadora.


---

## 3. On-Off Keying (OOK)

La forma más simple y común de ASK es el **OOK**. En este método:

- El **1 lógico** se representa mediante la presencia de la portadora.
    
- El **0 lógico** se representa mediante la ausencia total de la portadora.
    

Es el método utilizado, por ejemplo, en transmisiones de fibra óptica (encendido/apagado de luz) y en algunos controles remotos sencillos.

---

## 4. Ventajas y Desventajas

###  Ventajas

- **Simplicidad:** Tanto el modulador como el demodulador son muy fáciles y baratos de implementar.
    
- **Eficiencia de ancho de banda:** Requiere menos ancho de banda que otras técnicas como FSK (Frequency Shift Keying).
    

###  Desventajas

- **Sensibilidad al ruido:** La amplitud es muy susceptible a las interferencias atmosféricas y al ruido electrónico, lo que puede causar errores en la detección de los bits.
    
- **Ineficiencia de potencia:** No es la técnica más eficiente para transmisiones de larga distancia en medios muy ruidosos.
    

---

## 5. Aplicaciones Comunes

- **Sistemas de Fibra Óptica:** Donde se usa luz "encendida" o "apagada".
    
- **Comunicaciones Inalámbricas de Corto Alcance:** Mandos de garaje, llaves de coche y sensores domésticos.
    
- **Telegrafía:** Históricamente relacionada con el código Morse.
    

---