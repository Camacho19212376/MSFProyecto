# Modelo RLC del Sistema Renal – Modelado de Sistemas Fisiológicos

![Sistema renal RLC](https://github.com/user-attachments/assets/681fd16d-369d-4ffc-9e3e-00e62fa8c394)

## Información del estudiante

**Tchandra Yahoel Camacho Llanes** — 19212376 — l19212376@tijuana.tecnm.mx  
**Victor Silvano Dino Seañez** — 20211964 — l20211964@tijuana.tecnm.mx

**Materia:** Modelado de Sistemas Fisiológicos  
**Carrera:** Ingeniería Biomédica

---

## Docente

**Dr. Paul Antonio Valle Trujillo**  
paul.valle@tectijuana.edu.mx

Departamento de Ingeniería Eléctrica y Electrónica  
Tecnológico Nacional de México / IT Tijuana

---

# Descripción de la asignatura

El modelado de sistemas fisiológicos constituye una herramienta fundamental en Ingeniería Biomédica, ya que permite representar matemáticamente procesos biológicos complejos mediante analogías físicas y electrónicas. A través de circuitos eléctricos equivalentes tipo RLC es posible describir fenómenos fisiológicos relacionados con presión, flujo, resistencia y almacenamiento de energía o volumen en órganos y sistemas del cuerpo humano.

La asignatura de Modelado de Sistemas Fisiológicos tiene como propósito desarrollar competencias para formular modelos matemáticos, analizar sistemas dinámicos y aplicar herramientas computacionales que permitan comprender la dinámica fisiológica del cuerpo humano desde una perspectiva ingenieril.

En este trabajo se desarrolla un modelo eléctrico equivalente del sistema renal utilizando dos mallas acopladas mediante un capacitor, representando el proceso de entrada sanguínea y filtración glomerular tanto en condiciones normales como en condiciones patológicas.

---

# Objetivos

1. Representar el sistema renal mediante una analogía eléctrica RLC.
2. Formular el modelo matemático basado en leyes de Kirchhoff.
3. Analizar el comportamiento dinámico del sistema fisiológico.
4. Comparar la respuesta del sistema en condiciones normales y anormales.
5. Interpretar fisiológicamente los parámetros eléctricos del modelo.
6. Simular la dinámica temporal del sistema mediante herramientas computacionales.
7. Evaluar el efecto de cambios paramétricos asociados a enfermedad renal.
8. Analizar las variaciones en flujo y filtración glomerular.

---

# Desarrollo matemático

## Malla 1

<img width="531" height="77" alt="image" src="https://github.com/user-attachments/assets/ac97cd13-984a-4598-8a19-07b3e2b77819" />

## Malla 2

<img width="566" height="534" alt="image" src="https://github.com/user-attachments/assets/a7231871-b706-4d18-bd49-e4b16b442026" />


## Salida del sistema
<img width="256" height="67" alt="image" src="https://github.com/user-attachments/assets/7ebc2e6d-acad-400e-aff0-c49658c60c09" />

## Transformada de Laplace

<img width="484" height="466" alt="image" src="https://github.com/user-attachments/assets/2560d9d1-8c9c-45f1-ab04-1d27fbebc171" />

<img width="339" height="228" alt="image" src="https://github.com/user-attachments/assets/6dd93616-3e5f-4920-b281-17158294f7aa" />


## Sustitucion en la ecuacion principal

<img width="884" height="258" alt="image" src="https://github.com/user-attachments/assets/cb50f36c-f75f-4af3-aa17-6c6f590e53a1" />

## Función de transferencia


<img width="517" height="101" alt="image" src="https://github.com/user-attachments/assets/08be677a-8c4e-4468-86da-57bd1b4ee39a" />


# Error estacionario

<img width="352" height="73" alt="image" src="https://github.com/user-attachments/assets/ef59d625-e251-4e60-8cbc-4ca566f6e06b" />


## Caso control

<img width="267" height="232" alt="image" src="https://github.com/user-attachments/assets/09438816-4272-4ea1-ad25-1914fbd87fb1" />


## Caso patológico

<img width="179" height="103" alt="image" src="https://github.com/user-attachments/assets/f73fdc7c-2afd-40ea-8d61-5714e13a16c1" />


# Análisis de estabilidad

<img width="708" height="126" alt="image" src="https://github.com/user-attachments/assets/b2532ac5-d89d-4eaa-977d-552eb5aed149" />


## Parámetros del caso control

<img width="210" height="161" alt="image" src="https://github.com/user-attachments/assets/ba819209-8a13-423f-a514-ffaff47c73a4" />

<img width="336" height="181" alt="image" src="https://github.com/user-attachments/assets/8ddb97ab-af5a-458b-8287-77703e91dce5" />

## Parámetros del caso patológico

<img width="221" height="167" alt="image" src="https://github.com/user-attachments/assets/bd1200e7-70ae-4e5a-86e3-5d6fa18fcb43" />

<img width="262" height="196" alt="image" src="https://github.com/user-attachments/assets/57230e40-3cf7-4c3d-b692-cf6347a1ef8c" />

El sistema es estable debido a que ambas raíces son reales y negativas, produciendo una respuesta sobreamortiguada.

---

# Conclusiones

El uso de circuitos RLC equivalentes permite representar adecuadamente sistemas fisiológicos complejos como el riñón. Mantener la misma estructura eléctrica para condiciones normales y patológicas facilita el análisis comparativo del comportamiento dinámico del sistema.

Las variaciones paramétricas permiten modelar alteraciones fisiológicas asociadas a enfermedades renales sin modificar la topología original del sistema.

---

# Referencias

1. P. A. Valle, *Syllabus para Modelado de Sistemas Fisiológicos*, 2025.
2. M. C. Khoo, *Physiological Control Systems*, IEEE Press, 2018.
3. N. S. Nise, *Control Systems Engineering*, Wiley, 2020.
