# (UCSB MATRL 204) Intro to Magnetism and Magnetic Materials

# Lecture 1: Review of Maxwell's equations

This topic is aimed towards its applications in Condensed Matter. The physics involved includes Electromagnetism and Quantum Mechanics. 

## Maxwell's equations

### Standard Maxwell's equations
We start off with the four Maxwell's equations

$$
\nabla\cdot \vec{E} &= \rho/\varepsilon _o           \\
\nabla\cdot \vec{B} &= 0 \text{ no magnetic monopole}\\
\nabla\times\vec{E} &= - \frac{\partial\vec{B}}{\partial t}\\
\nabla\times\vec{B} &= \mu _0 \vec{J} + \mu _0 \varepsilon _0 \frac{\partial\vec{E}}{\partial t} \\
$$

### Maxwell's equation in Dielectric Materials
And that inside materials, the Maxwell's equation have similar forms

$$
\nabla\cdot \vec{D} &= \rho _{\text{free}}           \\
\nabla\cdot \vec{B} &= 0                             
\text{ with } \vec{B}= \mu_0(\vec{H}+\vec{M})\\
\nabla\times\vec{E} &= - \frac{\partial\vec{B}}{\partial t} \\
\nabla\times\vec{H} &= \vec{J}_{free} + \frac{\partial\vec{D}}{\partial t} \\
$$

### Linear Response of Dielectric Materials
And for the linear response of dielectric materials, we have 

$$
\vec{P} &=\varepsilon_0 \chi_e \vec{E}\\
\vec{M} &=\chi_e\vec{H}               \\
\vec{D} &=\varepsilon_0(1+\chi_e)\vec{E}=\varepsilon\vec{E}\\
\vec{B} &=\mu_0(1+\chi_m)\vec{H}=\mu\vec{H}
$$
where 

$\vec{P}$ is the charge polarization; 

$\vec{M}$ is the magnetization of the material;

$\vec{D}$ is the electric displacement field;

$\vec{H}$ is the auxiliary magnetic field;

with $\mu$ denoting permeability of dielectric material and $\varepsilon$ denoting permittivity of material. 

## Lorentz Force (Griffiths E&M Ch 10.1.4)
To briefly cover the Lorentz force, it describes when charged particles are exposed to external magnetic and electric fields. 

$$
\vec{F} =\frac{d\vec{p}}{dt}&= q\vec{E} + q\vec{v}\times \vec{B} \text{ giving cyclotron motion} \\
= m\frac{d\vec{v}}{dt} 
&= q(-\nabla V - \partial_t \vec{A}) + q(\vec{v}\times\nabla\times\vec{A})\\
&= q(-\nabla V - \partial_t \vec{A} + 
\nabla{(\vec{v}\cdot{\vec{A}})}-\vec{A}(\vec{v}\cdot\vec{\nabla})\\
m\frac{d\vec{v}}{dt} + q(\partial _t\vec{A}+(\vec{v}\cdot\nabla)\vec{A})&=-q\vec{\nabla}V + q\vec{\nabla}(\vec{v}\cdot\vec{A})) \\
$$

Recall that the convective derivative is to expose the chain rule in the partial derivative, a math trick, where


$$
\vec{A} &= \vec{A}(\vec{r}_i (t),t) \\
\frac{d}{dt}\left[\vec{A}\right]
&= \sum _{i=1}^{3}\frac{\partial \vec{A}}{\partial \vec{r}_i}\frac{d\vec{r}_i(t)}{dt}
+ \frac{\partial\vec{A}}{\partial t}\\
&= \left(\sum _{i=1}^{3}\frac{\partial }{\partial \vec{r}_i}\cdot\frac{d\vec{r}_i(t)}{dt}\right) \vec{A}
+ \frac{\partial\vec{A}}{\partial t}\\
\frac{d}{dt}\left[\vec{A}\right]&=(\vec{v}\cdot\vec{\nabla})\vec{A} + \frac{\partial\vec{A}}{\partial t}\\
$$

Combining the  expressions, we then yield

$$
m\frac{d\vec{v}}{dt} + q\frac{d\vec{A}}{dt }&=\\
\frac{d\vec{p}_{\text{can}}}{dt}=\frac{d}{dt}\left[ p+ q\vec{A}\right] &= -q\vec{\nabla}(V - \vec{v}\cdot\vec{A}) = -\vec{\nabla}U
$$
where $\vec{p}_{\text{can}}=\vec{p} + q\vec{A}$ is the canonical momentum, and the $U_{\text{vel}} = q(V-\vec{v}\cdot\vec{A})$ is the potential of velocity-dependent quantity.
