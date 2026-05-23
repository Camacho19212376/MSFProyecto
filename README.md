[![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](https://matlab.mathworks.com/open/github/v1?repo=Camacho19212376/MSFProyecto)

# Modelo RLC del Sistema Renal – Modelado de Sistemas Fisiológicos
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/681fd16d-369d-4ffc-9e3e-00e62fa8c394" />


## Información del estudiante

Tchandra Yahoel Camacho Llanes [19212376]; l19212376@tijuana.tecnm.mx

Victor Silvano Dino Seañez [20211964]; l20211964@tijuana.tecnm.mx

Modelado de Sistemas Fisiológicos  

Ingeniería Biomédica  

---

## Docente

Dr. Paul Antonio Valle Trujillo; paul.valle@tectijuana.edu.mx  

Departamento de Ingeniería Eléctrica y Electrónica, Tecnológico Nacional de México / IT Tijuana, Blvd. Alberto Limón Padilla s/n, Tijuana, C.P. 22454, B.C., México.

---

## Descripción de la asignatura

El modelado de sistemas fisiológicos constituye una herramienta fundamental en Ingeniería Biomédica, ya que permite representar matemáticamente procesos biológicos complejos mediante analogías físicas y electrónicas. A través de circuitos eléctricos equivalentes tipo RLC es posible describir fenómenos fisiológicos relacionados con presión, flujo, resistencia y almacenamiento de energía o volumen en órganos y sistemas del cuerpo humano.

La asignatura de Modelado de Sistemas Fisiológicos tiene como propósito desarrollar competencias para formular modelos matemáticos, analizar sistemas dinámicos y aplicar herramientas computacionales que permitan comprender la dinámica fisiológica del cuerpo humano desde una perspectiva ingenieril.  

En este trabajo se desarrolla un modelo eléctrico equivalente del sistema renal utilizando dos mallas acopladas mediante un capacitor, representando el proceso de entrada sanguínea y filtración glomerular tanto en condiciones normales como en condiciones patológicas.

---

## Objetivos

1. Representar el sistema renal mediante una analogía eléctrica RLC.
2. Formular el modelo matemático basado en leyes de Kirchhoff.
3. Analizar el comportamiento dinámico del sistema fisiológico.
4. Comparar la respuesta del sistema en condiciones normales y anormales.
5. Interpretar fisiológicamente los parámetros eléctricos del modelo.
6. Simular la dinámica temporal del sistema mediante herramientas computacionales.
7. Evaluar el efecto de cambios paramétricos asociados a enfermedad renal.
8. Analizar las variaciones en flujo y filtración glomerular.

---

## Descripción del sistema fisiológico renal

El sistema renal puede representarse mediante un circuito RLC equivalente de dos mallas acopladas por un capacitor. Esta analogía permite describir el comportamiento dinámico del flujo sanguíneo y el proceso de filtración glomerular mediante componentes eléctricos equivalentes.

### Modelo de control (normalidad)

El modelo fisiológico en condiciones normales está formado por:

- R1: resistencia asociada a la entrada sanguínea renal.
- L: inercia del flujo sanguíneo.
- C: compliance o distensibilidad glomerular.
- R2: resistencia de salida o filtración.
- Ve(t): presión arterial de entrada.

La estructura consta de dos mallas acopladas mediante un capacitor central que modela la capacidad de almacenamiento y filtración del glomérulo renal.

### Modelo de anormalidad

Para representar una condición patológica renal se mantiene exactamente la misma topología y número de componentes; únicamente cambian los valores de los parámetros:

- R1' > R1: aumento de resistencia de entrada (vasoconstricción).
- L' = L: misma inercia del flujo en ambos casos.
- C' < C: disminución de la compliance glomerular.
- R2' < R2: disminucion de la resistencia de filtración (daño glomelular).
- Ve(t): misma entrada para ambos casos.

Este enfoque permite comparar directamente el comportamiento fisiológico normal y anormal sin alterar la estructura matemática del sistema.

---

## Desarrollo matemático

El modelo se obtiene aplicando la Ley de Voltajes de Kirchhoff (KVL) a cada una de las mallas del circuito.

### Malla 1

$$
V_e(t)=R_1 i_1(t)+L\frac{di_1(t)}{dt}+\frac{1}{C}\int[i_1(t)-i_2(t)]dt
$$

### Malla 2

$$
\frac{1}{C}\int[i_1(t)-i_2(t)]dt=R_2 i_2(t)
$$

### Salida del sistema

$$
V_s(t)=R_2 i_2(t)
$$

Estas ecuaciones permiten obtener el sistema de ecuaciones diferenciales y posteriormente la función de transferencia del modelo fisiológico renal.

# Transformada de Laplace

Aplicando transformada de Laplace:

$$
V_e(s)=R_1I_1(s)+LsI_1(s)+\frac{I_1(s)-I_2(s)}{Cs}
$$

$$
\frac{I_1(s)-I_2(s)}{Cs}=R_2I_2(s)
$$

$$
V_s(s)=R_2I_2(s)
$$

# Desarrollo algebraico

Despejando I_1 de la segunda ecuación:

$$
\frac{I_1(s)}{Cs}-\frac{I_2(s)}{Cs}=R_2I_2(s)
$$

$$
\frac{I_1(s)}{Cs}=R_2I_2(s)+\frac{I_2(s)}{Cs}
$$

$$
I_1(s)=(CR_2s+1)I_2(s)
$$

Se utiliza el valor de I_1 obtenido para sustituir en la ecuación principal:

$$
V_e(s)=R_1(CR_2s+1)I_2(s)+Ls(CR_2s+1)I_2(s)+\frac{(CR_2s+1)I_2(s)-I_2(s)}{Cs}
$$

Agrupando términos:

$$
V_e(s)=[CR_2Ls^2+(CR_1R_2+L)s+R_1+R_2]I_2(s)
$$

---

# Función de transferencia
Una vez que tenemos el valor de Ve(s), lo usamos para calcular la función de transferencia:

$$
\frac{V_s(s)}{V_e(s)}= \frac{R_2}{CR_2Ls^2+(CR_1R_2+L)s+R_1+R_2}
$$

---

# Ecuaciones integrodiferenciales

$$
i_1(t)=\frac{V_e(t)-L\frac{di_1(t)}{dt}-\frac{1}{C}\int[i_1(t)-i_2(t)]dt}{R_1}
$$

$$
i_2(t)=\frac{\frac{1}{C}\int[i_1(t)-i_2(t)]dt}{R_2}
$$

$$
V_s(t)=R_2 i_2(t)
$$

---

# Error en estado estacionario

$$
e(s)=\lim_{s\to0}sV_e(s)\left[1-\frac{V_s(s)}{V_e(s)}\right]
$$

Sustituyendo valores e igualando, el error en estado estacionario es:

$$
e(s)=\frac{R_1}{R_1+R_2}
$$

## Control
Cuando se usan los valores de Control, el error en estado estacionario se muestra como:

$$
e(s)=\frac{10}{40+10}=\frac{1}{5}
$$

## Caso
En contraste, cuando se usan los valores de Caso, el error en estado estacionario se muestra como:

$$
e(s)=\frac{80}{10+80}=\frac{8}{9}
$$

---

# Análisis de estabilidad
El sistema es estable dado que ambas raices son negativas y reales. Entonces el sistema presenta una respuesta sobreamortiguada.

$$
\lambda_{1,2}= \frac{-(CR_1R_2+L)\pm \sqrt{(CR_1R_2+L)^2-4(CR_2L)(R_1+R_2)}}{2(CR_2L)}
$$

---

# Parámetros del sistema de control

- R1 = 10 Ω
- R2 = 40 Ω
- C = 100 μF
- L = 10 μH

Resultados:

$$
\lambda_1=-5.008\times10^7
$$

$$
\lambda_2=-2.496\times10^{10}
$$

---

# Parámetros del sistema patológico

- R1 = 80 Ω
- R2 = 10 Ω
- C = 20 μF
- L = 10 μH

Resultados:

$$
\lambda_1=-7.9119\times10^7
$$

$$
\lambda_2=-7.280\times10^6
$$

---

## Interpretación fisiológica de los componentes

| Componente | Interpretación fisiológica |
|---|---|
| R1 | Resistencia vascular de entrada |
| L | Inercia del flujo sanguíneo |
| C | Compliance/distensibilidad glomerular |
| R2 | Resistencia de filtración |
| Ve(t) | Presión arterial renal |

---

## Metodología de análisis

1. Formular las ecuaciones mediante KVL.
2. Obtener el modelo dinámico del sistema.
3. Determinar la función de transferencia.
4. Simular la respuesta temporal del sistema.
5. Comparar condiciones normales y patológicas.
6. Analizar cambios en flujo, presión y filtración glomerular.
7. Interpretar fisiológicamente las respuestas obtenidas.

---

## Resultados esperados

El modelo normal presenta una respuesta estable con una filtración glomerular adecuada y un equilibrio dinámico entre entrada y salida de flujo renal.

En el caso patológico se espera:

- Disminución de la capacidad de filtración.
- Incremento de resistencia vascular.
- Menor compliance glomerular.
- Alteraciones en la dinámica del flujo sanguíneo.
- Cambios en las corrientes equivalentes i1 e i2.

---

## Herramientas utilizadas

- MATLAB
- Simulink
- Python / Spyder
- Simscape Electrical
- Métodos de análisis en Laplace

---

## Archivos incluidos en el repositorio

1. Documento README.
2. Modelo matemático del sistema renal.
3. Simulación en MATLAB/Simulink.
4. Scripts de Python.
5. Diagramas del circuito equivalente.
6. Imágenes de resultados y simulaciones.
7. Análisis comparativo entre normalidad y enfermedad renal.

---

## Conclusiones

El uso de circuitos RLC equivalentes permite representar adecuadamente sistemas fisiológicos complejos como el riñón. Mantener la misma estructura eléctrica para condiciones normales y patológicas facilita el análisis comparativo del comportamiento dinámico del sistema.

Las variaciones paramétricas en resistencias, inductancias y capacitancias permiten modelar alteraciones fisiológicas asociadas a enfermedades renales sin modificar la topología original del sistema, proporcionando una representación matemática consistente y útil para simulación y análisis biomédico.

---

## Referencias

[1] P. A. Valle, *Syllabus para Modelado de Sistemas Fisiológicos*, Tecnológico Nacional de México / Instituto Tecnológico de Tijuana, Tijuana, B.C., México, 2025.

[2] M. C. Khoo, *Physiological Control Systems: Analysis, Simulation, and Estimation*, 2nd ed. IEEE Press, 2018.

[3] N. S. Nise, *Control Systems Engineering*, 8th ed. John Wiley & Sons, 2020.

[4] J. Enderle y J. Bronzino, *Introduction to Biomedical Engineering*, Academic Press, 2012.
