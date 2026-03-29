- [I] **Distancia de hamming:** es la cantidad mínima de bits cambiados para pasar de una palabra codificada válida a otra cualquiera. La **distancia de un código completo** es la menor de todas las distancias entre una palabra y otra.
	Un código con distancia mínima de Hamming **d** puede detectar palabras codificadas (codewords) con hasta **s** bits con error, donde $d_{min}\gt{s}$

>[!info] Funcionamiento de control de errores
>- Toma un mensaje de longitud **m**
>- Le agrega **r** bits de redundancia
>- Se obtiene una **palabra codificada** de longitud **n** $$n=m+r$$

| **Detección de errores**                                                                                                       | **Corrección de errores**                                                                                                |
| ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| $d_{\text{min}}$ : distancia de Hamming<br>$s$ : cantidad de bits con error **máximos a detectar**<br>$$d_\text{{min}}\gt{s}$$ | $d_{\text{min}}$ : distancia de Hamming<br>$t$ : cantidad de bits con error **máximos a corregir**<br>$$d_{min}\gt{2t}$$ |
| ![[Pasted image 20260329172902.png\|250]]                                                                                      | ![[Pasted image 20260329172830.png\|300]]                                                                                |

---
## Corrección de errores de un solo bit
Se presenta en el código de Hamming
==ESTUDIAR PORQUE EL PROFE DIJO QUE PUEDE PREGUNTAR ALGO ASI==
>[!info] Se tiene **m** bits de mensaje y **r** bits de verificación y se quiere corregir todos los errores de **un bit**.
>- Mensajes posibles: $2^m$
>- Cant de codewords: $(m+r+1)$
>	Para indicar la ausencia de error (una codeword válida)
>	Para indicar la ubicación del error ($m+r$posibilidades)
>- Cant de codewords: $2^n=2^{m+r}$ palabras codificadas
>$$2^m*(m+r+1)\leq{2^{m+r}=2^m*2^r}$$
>$$(m+r+1)\leq{2^r}$$



---
# Enlaces relacionados
- Siguiente nota: 
- [[2. Capa de Enlace de Datos]]