# **Fourier Neural Operators**
**MA5307** - *Análisis Numérico de Ecuaciones en Derivadas Parciales: Teoría y Laboratorio*

Proyecto desarrollado por Arian Escobar y Alfredo Padilla.

---

## Introducción

Los **Operadores Neuronales** constituyen una clase de arquitecturas de aprendizaje profundo orientadas a la aproximación de mapeos entre espacios de funciones, permitiendo abordar la resolución de ecuaciones en derivadas parciales desde un enfoque completamente basado en datos. Dentro de esta clase de modelos, el más destacado es el **Fourier Neural Operator** (FNO), cuya formulación se basa en el uso de la transformada de Fourier para representar eficientemente operadores integrales en el dominio de las frecuencias. En este proyecto se describen los aspectos teóricos asociados a esta metodología, junto con su implementación en tres casos de estudio.

---

## Formulación

Su arquitectura se define en base a una arquitectura iterativa $v_0 \mapsto v_1 \mapsto \dots \mapsto v_L$, donde $v_j$ para $j = 0,1,\dots,L$ es una sucesión de funciones a valores en $\mathbb{R}^{d_v}$.

<img width="3799" height="1251" alt="FNO" src="https://github.com/user-attachments/assets/8cc6c847-7c2b-4b81-b742-4c6eddb12acc" />


Donde el operador de kernel integral $(\mathcal{K}_l(v_l))(x)$, propio de la arquitectura de los operadores neuronales, se parametriza directamente en el espacio de Fourier al considerar $\kappa(x,y) = \kappa(x-y)$. 

$$(\mathcal{K}_l(v_l))(x)= \int_D \kappa^{(l)}(x,y)v_l(y) \ dy = (\kappa \ast v_l)(x) = \mathcal{F}^{-1} (\mathcal{F}(\kappa) \cdot \mathcal{F}(v_l))(x) = \mathcal{F}^{-1} (R \cdot \mathcal{F}(v_l))(x)$$   

---

Para usar este código se recomienda crear un entorno virtual usando el archivo $\texttt{requirements.txt}$

    pip install -r requirements.txt

---

## **Trabajo Futuro**

Para quien esté interesado/a en continuar este trabajo se recomienda seguir alguna de las siguientes líneas.

- Estudiar cómo se puede implementar en geometrías más complejas para evitar las limitaciones que impone FFT. (Revisar paper adjunto en References)
- Extenderlo a nuevos casos de estudio, considerando nuevas condiciones iniciales e incorporando dependencias paramétricas.
- Aplicarlo a casos de estudio con evolución temporal.
