# Modelo RLC del Sistema Renal – Modelado de Sistemas Fisiológicos

[![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](https://matlab.mathworks.com/open/github/v1?repo=Camacho19212376/MSFProyecto)

---

# Desarrollo matemático del sistema renal

## Ecuaciones de malla

Aplicando la Ley de Voltajes de Kirchhoff (KVL):

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

---

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

---

# Desarrollo algebraico

Despejando:

$$
\frac{I_1(s)}{Cs}-\frac{I_2(s)}{Cs}=R_2I_2(s)
$$

$$
\frac{I_1(s)}{Cs}=R_2I_2(s)+\frac{I_2(s)}{Cs}
$$

$$
I_1(s)=(CR_2s+1)I_2(s)
$$

Sustituyendo en la ecuación principal:

$$
V_e(s)=R_1(CR_2s+1)I_2(s)+Ls(CR_2s+1)I_2(s)+\frac{(CR_2s+1)I_2(s)-I_2(s)}{Cs}
$$

Agrupando términos:

$$
V_e(s)=[CR_2Ls^2+(CR_1R_2+L)s+R_1+R_2]I_2(s)
$$

---

# Función de transferencia

$$
\frac{V_s(s)}{V_e(s)}=
\frac{R_2}{CR_2Ls^2+(CR_1R_2+L)s+R_1+R_2}
$$

---

# Ecuaciones integrodiferenciales

$$
R_1i_1(t)=V_e(t)-L\frac{di_1(t)}{dt}-\frac{1}{C}\int[i_1(t)-i_2(t)]dt
$$

$$
i_1(t)=\frac{V_e(t)-L\frac{di_1(t)}{dt}-\frac{1}{C}\int[i_1(t)-i_2(t)]dt}{R_1}
$$

$$
i_2(t)=\frac{\frac{1}{C}\int[i_1(t)-i_2(t)]dt}{R_2}
$$

---

# Error estacionario

$$
e(s)=\lim_{s\to0}sV_e(s)\left[1-\frac{V_s(s)}{V_e(s)}\right]
$$

Sustituyendo la función de transferencia:

$$
e(s)=1-\frac{R_2}{R_1+R_2}
$$

$$
e(s)=\frac{R_1}{R_1+R_2}
$$

## Caso de control

$$
\frac{10}{40+10}=\frac{1}{5}
$$

## Caso patológico

$$
\frac{80}{10+80}=\frac{8}{9}
$$

---

# Análisis de estabilidad

$$
\lambda_{1,2}=
\frac{-(CR_1R_2+L)\pm
\sqrt{(CR_1R_2+L)^2-4(CR_2L)(R_1+R_2)}}{2(CR_2L)}
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

Como ambas raíces son negativas y reales, el sistema es estable y presenta una respuesta sobreamortiguada.
