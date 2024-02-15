# (MATRL204L3) Intro to Dirac's equation and spin

## Recap of Spherical Harmonics
Recall that from previous lecture, we have derived in spherical coordinate that 

$$
\hat{L}&= \vec{r}\times\vec{p}=\vec{r}\times(i\hbar\nabla)=\left[\frac{\partial}{\partial\theta}\hat{\phi}+ \frac{-1}{\sin\theta}\frac{\partial}{\partial\phi}\hat{\theta}\right]\left(-i\hbar\right)\\
\nabla&=\frac{\partial}{\partial r}\hat{r}+\frac{1}{r}\frac{\partial}{\partial\theta}\hat{\theta}+ \frac{1}{r\sin\theta}\frac{\partial}{\partial\phi}\hat{\phi}\\
\hat{L}_z=-i\hbar\frac{\partial}{\partial\phi}; 
\hat{L}^2 &=-\hbar^2\left(\frac{1}{\sin\theta}\frac{\partial}{\partial\theta}\left(\sin\theta\frac{\partial}{\partial\theta}\right)+\frac{1}{\sin^2\theta}\frac{\partial^2}{\partial\phi^2}\right)\\
\hat{L}_z\ket{\psi}=\hbar m\ket{\psi};\hat{L}^2\ket{\psi}&=\hbar^2 l\left(l+1\right)\ket{\psi} \longmapsto \ket{\psi}=Y^m_l(\theta,\phi)
$$
Something to keep in mind is that half-integer spin rotates in $4\pi$ rotation, and integer spin rotates in $2\pi$ rotation. 

The mathematical intuition on half-integer spin rotation can be thought of as a mobius strip. 

The primary highlight is that Spherical Harmonics cannot capture half integers angular momentum because Spin rotates from up/down to down/up in $2\pi$ rotation, and for spin to rotate from up to up again requires a $4\pi$ rotation. 

This gives rise to the necessity of SU(2) for spin and SO(3) for angular momentum. For this reason, spin angular momentum and orbital angular momentum are of two different groups, requiring different treatments. 

## Dirac's equation (Needs review and correction)

For non-relativistic energy, we have 

$$ 
E = \frac{1}{2m}\left(p^2_x + p^2_y + p^2_z\right) \implies i\hbar\partial_t\psi=\frac{\hbar^2}{2m}\nabla^2\psi 
$$


In relativity, 

$$
E               &= mc^2 = \sqrt{\left(pc\right)^2+\left(m_0 c^2\right)^2}=\gamma _0 mc^2 + \sum^3_{i=1}\gamma _i p_i c\\
E^2             &= m_0^2c^4 + p_x^2c^2 + p_y^2c^2 + p_z^2c^2\\
\frac{E^2}{c^2} &= m_0^2c^2 + p_x^2    + p_y^2    + p_z^2 
$$

Alternatively, you can also use $E = \gamma _0 m_0c^2 + \sum^3_{i=1}\gamma _i p_i c$ to derive $E^2/c^2$. 

$$
E&=\gamma _0 mc^2 + \sum^3_{i=1}\gamma _i p_i c\\
E^2 &= \left[\gamma _0 m_0c^2 + \sum^3_{i=1}\gamma _i p_i c\right]^2 \\
&=\left[\gamma _0 m_0c^2 + \sum^3_{i=1}\gamma _i p_i c\right]\left[\gamma _0 m_0c^2 + \sum^3_{i=1}\gamma _i p_i c\right]
$$
Recall that since $\gamma_i$ anti-commute, having the property that $\left\{\gamma_i\gamma_j+\gamma_j\gamma_i\right\} =2\delta_{ij}\mathbb{I}$
and that $(a+b+c+d)^2=a^2+b^2+c^2+d^2 + 2ab+2ac+2ad+2bc++2bd+2cd$ indicating the cross terms $ab, ac, ad,bc, bd,cd$ all carry $2\delta_{ij}\mathbb{I}$ and only the squared terms survive. Also $\gamma_i^2=\mathbb{I}$ 

$$
E^2 &= \gamma _0^2 m_0^2(c^2)^2 + \gamma _1^2 p_1^2c^2 + \gamma _2 ^2 p_2^2c^2 + \gamma _3 ^2 p_3^2c^2\\
\frac{E^2}{c^2}&=m_0c^2 + p_1^2 + p_2^2 + p_3^2
$$

## Minkowski Metric and Pauli Spin Matrices (For experimentalists' handwavy intuition)
The Dirac's postulate to expand the square root term in the relativistic energy term is only valid if $\gamma_i$ are matrix coefficients. So we need to describe these matrices using $\gamma_0$. 

We know the condition 

$$
\gamma_i^2=\mathbb{I}
$$ (GammaMatricesCond1)

and that 

$$
\left\{\gamma_i,\gamma_j\right\}=2\delta_{ij}\mathbb{I}
$$(GammaMatricesCond2)

we need to construct a basis that satisfies the two conditions above. 

$$
\gamma _0 = \begin{bmatrix}
\symbb{1}  & 0         \\
0          & -\symbb{1}\\
\end{bmatrix}
=\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 &-1 & 0 \\
0 & 0 & 0 &-1 \\
\end{bmatrix}
$$(GammaNot)

This is our given vector of the basis, we need to find the other 3 components to form an orthogonal basis.

$$
\gamma _i = \begin{bmatrix}
0 & \sigma _i^{\dagger}\\
\sigma _i & 0          \\
\end{bmatrix}
= \begin{bmatrix}
0 & 0 & * & * \\ 
0 & 0 & * & * \\
* & * & 0 & 0 \\
* & * & 0 & 0 \\
\end{bmatrix}
$$(GammaI)

We have assumed that all the $\gamma$ matrices are Hermitian, but we need  to know what $\sigma$'s are, and they cannot simply be complex numbers but matrices to satisfy the condition of equation {eq}`GammaMatricesCond1`.

As an example, 

$$
\gamma_1\gamma_1 =\mathbb{1}=\sigma_1^{\dagger}\sigma_1=\sigma_1\sigma_1^{\dagger}=\mathbb{1}
$$(SigmaMatricesUnitaryCond1)

and more generally,

$$
\sigma_i\sigma_i^{\dagger}=\sigma_i^{\dagger}\sigma_i=\mathbb{1}
$$(SigmaMatricesUnitaryCond2)

so, this way you can substitute $\sigma_i=e^{i\phi_i}$ to satisfy the condition. 

Now, along with the condition from equation {eq}`GammaMatricesCond2`, it implies that 

$$
\left\{\gamma_i,\gamma_j\right\}=2\delta_{ij}\mathbb{1}\implies\sigma_i^{\dagger}\sigma_j+ \sigma_j^{\dagger}\sigma_i&=0=2\delta_{ij}\mathbb{1}=\sigma_i\sigma_j^{\dagger}+\sigma_j^{\dagger}\sigma_i \\
e^{i(\phi_i-\phi_j)}+e^{-i(\phi_i-\phi_j)}&= \\
\cancel{2}\cos(\phi_i-\phi_j)&=0 =\cancel{2}\delta_{ij}\mathbb{1}
$$(SigmaUnitaryCond1)

and we know that $\phi_i - \phi_j= \pi/2$ due to orthogonality. This is true only if we have $\sigma_1$ and $\sigma_2$, but we have 3 $\gamma_i$ matrices. If we don't do anything about this, then $\phi_i\perp\phi_j$ but one of them will be 180˚ away from another one of the $\sigma_i$. This means that $\sigma_i$ cannot just be any complex numbers but also matrices and have their own "basis".

To find the basis for $\sigma$, we now repeat the exercise done for $\gamma$ matrices and denote that 

$$
\sigma _3=\begin{bmatrix}
1 &  0 \\
0 & -1 \\
\end{bmatrix}
$$(SigmaMatrix3)

as a basis to find $\sigma_1$ and $\sigma_2$. Quick note, we already have the condition that $\sigma$ matrices are unitary from equation {eq}`SigmaMatricesUnitaryCond2`, so if we have one of the pauli spin matrices as one of the basis vectors from equation {eq}`SigmaMatrix3`, then we can say that 

$$
\sigma_i=
\begin{bmatrix} 
0        & \alpha_i^{\dagger}\\ 
\alpha_i & 0                 \\ 
\end{bmatrix}
$$(SigmaMatricesI)

for $i = 1, 2$.

What $\alpha$'s are at the moment can be put on hold. It is more important to relabel and relate $\sigma_1$, $\sigma_2$ and $\sigma_3$ to be $\sigma_x$, $\sigma_y$, and $\sigma_z$ respectively. So we need to satisfy a condition similar to equation {eq}`GammaMatricesCond1` and {eq}`GammaMatricesCond2` but for $\sigma$ matrices. Note also you can also hold the $\sigma$ matrices to be Hermitian. 

so we have

$$
\sigma_i &= \sigma_i^{\dagger}\\
\left\{\sigma_i,\sigma_j\right\}&=0\implies\left[\sigma_i,\sigma_j\right]=2\sigma_x\sigma_y=(const)\sigma_z\\
$$(SigmaMatricesCond1)

Which is similar to $\left[\hat{L}_x,\hat{L}_y\right]=i\hbar\hat{L}_z$

Some of the more formal treatment which is only meant to be saved for later, you can do it and find that 

$$
\sigma_1 = \sigma_x = \begin{bmatrix} 0 & 1 \\ 1& 0 \\ \end{bmatrix}; \sigma_2 = \sigma_y = \begin{bmatrix} 0 &-i \\ i& 0 \\ \end{bmatrix}; \sigma_3 = \sigma_z = \begin{bmatrix} 1 & 0 \\ 0&-1 \\ \end{bmatrix};
$$(PauliSpinMatrices)

that they're just the Pauli Spin Matrices that we have been working with. 

```{toggle}
## Old one
Now, we ask:
What form do the gamma matricies $\gamma _i$ take? 
Generally speaking, the [4x4 gamma matricies](https://en.wikipedia.org/wiki/Gamma_matrices) take the form of 

$$
\gamma _0 = \begin{bmatrix}
\symbb{1}  & 0         \\
0          & -\symbb{1}\\
\end{bmatrix}
&=\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 &-1 & 0 \\
0 & 0 & 0 &-1 \\
\end{bmatrix}

\gamma _i = \begin{bmatrix}
0 & \sigma _i^{\dagger}\\
\sigma _i & 0          \\
\end{bmatrix}
&= \begin{bmatrix}
0 & 0 & * & * \\ 
0 & 0 & * & * \\
* & * & 0 & 0 \\
* & * & 0 & 0 \\
\end{bmatrix}
$$

and the contravariant 4x4 gamma matricies are also hermitian $\gamma = \gamma^{\dagger}$ indicating that these are real observables.
The $\sigma_i$ matricies are the spin 1/2 pauli spin matricies. 

$$
\symbb{1}= \sigma _0= \begin{bmatrix}
1 & 0\\
0 & 1\\
\end{bmatrix},
\sigma _1 = \begin{bmatrix}
0  & 1 \\ 
1  & 0 \\
\end{bmatrix},
\sigma _2 = \begin{bmatrix}
0 &-i \\
i & 0 \\ 
\end{bmatrix},
\sigma _3 = \begin{bmatrix}
1 & 0\\
0 &-1\\
\end{bmatrix}
$$

$$
\symbb{1}=\sigma_i^{\dagger}\sigma_i=\sigma_i\sigma_i^{\dagger} 
$$
```

## Spin matrices treatment

## Classical and Semiclassical picture of spin?
So now we have formally established two types of angular momentum. 
* Orbital Angular Momentum
* Spin Angular Momentum 

How do we think about the gyromagnetic ratio classically?

### Classical picture: 
Imagine an electron orbiting about z-axis at a position vector $\vec{r}$ away. The time for one revolution is $t = \frac{2\pi r}{|v|}$. We know also classically that the magnetic moment $\mu = IA = I(\pi r^2)$. By substituting the variables in $I = -e|v|/2\pi r$. Substituting in $L = mvr$, we have $ I = \frac{-eL}{2\pi r^2 m_e}$. Next, extract the classical orbital magnetic moment, we have $\vec{\mu}_l = \frac{-e}{2m_e}\vec{L} = \gamma_l\vec{L}$.

This is the explicit relationship and a classical picture of the gyromagnetic ratio –– a charge to mass ratio for protons and electrons. 

### Unrelated mumbo jumbo
```{note}
Fermions cannot occupy the same state, Boson can. 
Bosons can have antiparallel and parallel spins, Fermions can only have antiparallel spins. 

Half-integer spins are Fermions. 
Integer spins are Bosons. 
Spherical Harmonics is used for both Fermions and Bosons, but only for the orbital angular momentum portion of the wavefunction, which is the spatial component of the wavefunction.

$$
\psi = \phi_{\text{space}}\chi_{\text{spin}}
$$

Spherical Harmonics are used for orbital angular momentum. 
Spinor fields are used for spin angular momentum. 

Electron is a type of fermion. Spehrical harmonics can also be used to describe the electrons in an atom/crystal field. 

```{toggle}
#### Confusion debugging:
Q: How about the spin? how does half-integer spin fail in a spherically symmetric potential? I know Spherical Harmonic fails to describe it because rotation in Spherical Harmonics follows the $2\pi$ convention. What is the treatment to account for the $4\pi$ rotation in half-integer spin? 

A: Spinor is a separate component of the wavefunction. 
Spherical Harmonics is only used to describe the angular component of the wavefunction, which involves the orbital angular momentum. and its l(l+1) comes from using/borrowing the solution to the differential equation (Legendre Equation). Turns out the l(l+1) can be thought of as the "eigenvalue" to the legendre's differential equation. Also, due to the limitation of Spherical Harmonics only being able to capture integer angular momentum, the needs for half integer spin angular momentum give rise to the use of minkowski metric and pauli spin matrices. But the "eigenvalue" for the $S^2$ operator takes a similar form to the orbital angular momentum operator, taking the form of $s(s+1)$.


```


Now let's talk about the spin component of the wavefunction. 