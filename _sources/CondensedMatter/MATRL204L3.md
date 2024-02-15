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

## Dirac's equation

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

Now, we ask:
What form do the gamma matricies $\gamma _i$ take? 
Generally speaking, the [4x4 gamma matricies](https://en.wikipedia.org/wiki/Gamma_matrices) take the form of 

$$
\gamma _0 = \begin{bmatrix}
\symbb{1}  & 0        \\
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

### Unrelated mumbo jumbo
```{note}
Fermions cannot occupy the same state, Boson can. 
No two Fermions can have the same spin up/down, but the two Fermions can have one spin up and one spin down. 
Bosons on the other hand can have two spin up and two spin down. 

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