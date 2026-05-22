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

\[
V_e(t)=R_1 i_1(t)+L\frac{di_1(t)}{dt}+\frac{1}{C}\int [i_1(t)-i_2(t)]dt
\]

## Malla 2

\[
\frac{1}{C}\int [i_1(t)-i_2(t)]dt = R_2 i_2(t)
\]

## Transformada de Laplace

\[
V_e(s)=R_1 I_1(s)+LsI_1(s)+\frac{I_1(s)-I_2(s)}{Cs}
\]

\[
\frac{I_1(s)-I_2(s)}{Cs}=R_2 I_2(s)
\]

## Función de transferencia

\[
\frac{V_s(s)}{V_e(s)}=
\frac{R_2}{CR_2Ls^2+(CR_1R_2+L)s+R_1+R_2}
\]

---

# Error estacionario

\[
e(s)=\frac{R_1}{R_1+R_2}
\]

## Caso control

\[
\frac{10}{40+10}=\frac{1}{5}
\]

## Caso patológico

\[
\frac{80}{10+80}=\frac{8}{9}
\]

---

# Análisis de estabilidad

\[
\lambda_{1,2}=
\frac{-(CR_1R_2+L)\pm
\sqrt{(CR_1R_2+L)^2-4(CR_2L)(R_1+R_2)}}{2(CR_2L)}
\]

## Parámetros del caso control

- \(R_1=10\Omega\)
- \(R_2=40\Omega\)
- \(C=100\mu F\)
- \(L=10\mu H\)

## Parámetros del caso patológico

- \(R_1=80\Omega\)
- \(R_2=10\Omega\)
- \(C=20\mu F\)
- \(L=10\mu F\)

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
