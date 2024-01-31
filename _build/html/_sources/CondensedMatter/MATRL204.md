# (UCSB MATRL 204) Intro to Magnetism and Magnetic Materials
Books used for all these notes:
* Griffiths E&M 4th Ed
* Griffiths QM 3rd Ed
* Magnetism In Condensed Matter by Stephen Blundell

# (MATRL204L1) Review of Maxwell's equations

This topic is aimed towards its applications in Condensed Matter. The physics involved includes Electromagnetism, Statistical Mechanics, and Quantum Mechanics. Limited Classical Mechanics is also included in terms of its formalism, such as gauge transformation, canonical momentum, and such. 

## Brief Review of Maxwell's equations

### Standard Maxwell's equations
We start off with the four Maxwell's equations

$$
\nabla\cdot \vec{E} &= \rho/\varepsilon _o           \\
\nabla\cdot \vec{B} &= 0 \text{ no magnetic monopole}\\
\nabla\times\vec{E} &= - \frac{\partial\vec{B}}{\partial t}\\
\nabla\times\vec{B} &= \mu _0 \vec{J} + \mu _0 \varepsilon _0 \frac{\partial\vec{E}}{\partial t} \\
$$

### No magnetic monopole, then how about magnetic dipole?



### Maxwell's equation in Dielectric Materials
And that inside materials, the Maxwell's equation have similar forms

$$
\nabla\cdot \vec{D} &= \rho _{\text{free}}           \\
\nabla\cdot \vec{B} &= 0                             
\text{ with } \vec{B}= \mu_0(\vec{H}+\vec{M})\\
\nabla\times\vec{E} &= - \frac{\partial\vec{B}}{\partial t} \\
\nabla\times\vec{H} &= \vec{J}_{free} + \frac{\partial\vec{D}}{\partial t} \\
$$

### Linear Response of Dielectric Materials (Griffiths E&M Ch 5&6)
And for the linear response of dielectric materials, we have 

$$
\vec{P} &=\varepsilon_0 \chi_e \vec{E}\\
\vec{M} &=\chi_m\vec{H}               \\
\vec{D} &=\varepsilon_0(1+\chi_e)\vec{E}=\varepsilon\vec{E}=\varepsilon_0\vec{E}+\vec{P}\\
\vec{B} &=\mu_0(1+\chi_m)\vec{H}=\mu\vec{H}= \mu_0(\vec{H}+\vec{M})
$$
where 

$\vec{P}$ is the charge polarization; 

$\vec{M}$ is the magnetization of the material;

$\vec{D}$ is the electric displacement field;

$\vec{H}$ is the auxiliary magnetic field;

with $\mu$ denoting permeability of dielectric material and $\varepsilon$ denoting permittivity of material. 

## Brief Review of Vector Potential: (Griffith E&M Ch 5)
The vector potential $\vec{A}$ is an analog of the potential in electrostatics. For magnetostatics, it has the form of

$$
\vec{A}_{\text{dipole}}(\vec{r})=\frac{\mu_0}{4\pi}\frac{\vec{m}\times\hat{r}}{r^2}
$$

To find the magnetic field due to the magnetic dipole moment, we can find the $\vec{m}$ based on the diagram and substitute the $\vec{m}$ in Cartesian/Cylindrical coordinate to Spherical Coordinate. Refer to the diagram from Griffiths' Figure 5.54 and the spherical coordinate unit vectors.

```{figure} ../Images/GriffithsEM_Fig5_54.png
---
height: 200px
width: 240px
---
magnetic field due to a perfect dipole along z-direction.
```

```{figure} ../Images/SphericalCoordinate.png
---
height: 200px
---
Spherical Coordinate with unit vector at point ($r$, $\theta$,$\phi$)
```
We can then find the dot product of $\vec{m}$ and $\vec{r}$ and recognize that along the position vector $\vec{r}$, $\vec{m}$ has both $\hat{r}$ and $\hat{\theta}$ components, and can be found graphically. (Insert diagram of the dot product here) For this, we get 

$$
\vec{m}&=|m|\left(\hat{r}\left[\cos\theta\right]+ 
                 \hat{\theta}\left[-\sin\theta\right] \right)\\
       &=\vec{m}_{\parallel} + \vec{m}_{\perp}
$$

Adopting the expression that $\vec{B}=\frac{\mu_0}{4\pi r^3}(2m\cos\theta\hat{r}+m\sin\theta\hat{\theta})$, we can simply abuse the arithmetics for a bit and get

$$
\vec{B}&=\frac{\mu_0}{4\pi r^3}(2m\cos\theta\hat{r}+m\sin\theta\hat{\theta})\\
&=\frac{\mu_0}{4\pi r^3}\left(3m\cos\theta\hat{r}-m\cos\theta\hat{r}+m\sin\theta\hat{\theta}\right)\\
&=\frac{\mu_0}{4\pi r^3}\left(3\left[\vec{m}\cdot\hat{r}\right]\hat{r}-|m|\left(\hat{r}\left[\cos\theta\right]+ 
                 \hat{\theta}\left[-\sin\theta\right] \right)\right)\\
$$

which gives us the coordinate-free form of magnetic field expression due to a magnetic dipole moment.

$$
\boxed{\vec{B}
=\frac{\mu_0}{4\pi r^3}\left[3\left[\vec{m}\cdot\hat{r}\right]\hat{r}-\vec{m}\right]}
$$

Notice also that the magnetic field is partially anti-parallel to the magnetic moment, and partially along the radial direction parallel to the position vector.

###### Rabbit hole #001
Alternatively, one can attempt to get lost in vector algebra, which I believe is not impossible and in fact more general, and can shed more insight into a truly coordinate-free derivation. which involves $\nabla\times\vec{A}=\nabla\times\left[\frac{\mu_0}{4\pi}\frac{\vec{m}\times\hat{r}}{r^2}\right]$. But since we are now on a time-constraint, let's save ourselves the mental gymnastics and pursue ideas more worthwhile, not vector and differential geometry. 

## Lorentz Force (Griffiths E&M Ch 10.1.4) [Needs revision]
To briefly cover the Lorentz force, it describes when charged particles are exposed to external magnetic and electric fields. In electrodynamics, $\nabla\times\vec{E}$ gives us a time dependent term, and can contribute to the $\vec{A}(\vec{r}_i(t),t)$ term, affecting the magnetic field. 

$$
\vec{F} =\frac{d\vec{p}}{dt}&= q\vec{E} + q\vec{v}\times \vec{B} \text{ giving cyclotron motion} \\
= m\frac{d\vec{v}}{dt} 
&= q(-\nabla V - \partial_t \vec{A}) + q(\vec{v}\times\nabla\times\vec{A})\\
&= q(-\nabla V - \partial_t \vec{A} + 
\nabla{(\vec{v}\cdot{\vec{A}})}-\vec{A}(\vec{v}\cdot\nabla)\\
m\frac{d\vec{v}}{dt} + q(\partial _t\vec{A}+(\vec{v}\cdot\nabla)\vec{A})&=-q\nabla V + q\nabla(\vec{v}\cdot\vec{A})) \\
$$

Recall that the convective derivative is to expose the chain rule in the partial derivative, a math trick, where


$$
\vec{A} &= \vec{A}(\vec{r}_i (t),t) \\
\frac{d}{dt}\left[\vec{A}\right]
&= \sum _{i=1}^{3}\frac{\partial \vec{A}}{\partial \vec{r}_i}\frac{d\vec{r}_i(t)}{dt}
+ \frac{\partial\vec{A}}{\partial t}\\
&= \left(\sum _{i=1}^{3}\frac{d\vec{r}_i(t)}{dt}\cdot\frac{\partial }{\partial \vec{r}_i}\right) \vec{A}
+ \frac{\partial\vec{A}}{\partial t}\\
\frac{d}{dt}\left[\vec{A}\right]&=(\vec{v}\cdot\nabla)\vec{A} + \frac{\partial\vec{A}}{\partial t}\\
$$

Combining the expressions, we then yield

$$
m\frac{d\vec{v}}{dt} + q\frac{d\vec{A}}{dt }&=\\
\frac{d\vec{p}_{\text{can}}}{dt}=\frac{d}{dt}\left[ p+ q\vec{A}\right] &= -q\nabla(V - \vec{v}\cdot\vec{A}) = -\nabla U_{\text{vel}}
$$
where $\vec{p}_{\text{can}}=\vec{p} + q\vec{A}$ is the canonical momentum, and the $U_{\text{vel}} = q(V-\vec{v}\cdot\vec{A})$ is the potential of velocity-dependent quantity.

## Magnetization from vector and E&M standpoint:
We have discussed in the above section that vector potential and the magnetic field are generated due to the magnetic dipole moment. But what is a dipole moment? What is magnetization? 

When an electric current goes around an area $\vec{a} = |a|\hat{n}$, a magnetic dipole moment $\mu= Ia\hat{n}$ is generated. This is similar to but not the same description as the fourth Maxwell's equation $\nabla\times\vec{B}=\mu_0\vec{J}+\frac{1}{c^2}\partial_t\vec{E}$, this is different than the Amperian loop picture. 

The electric current goes around like a toroid, which forms the shape of a circle. The area enclosed by a circle of radius $r$ gives $a=\pi r^2$ and the magnetic dipole moment is formed. The magnetic field circles around the current like a smoke vortex ring, but the dipole points upward normal to the circle. The Ampere model of magnetic dipole moment is analogous to the magnetic field in a solenoid. 


### Bohr-Miss van Leeuwen Theorem (brief explanation):
Magnetization is considered a "magnetic dipole density", or dipole moment per unit volume, induced by an external magnetic field. A brief explanation of Bohr-van Leeuwen Theorem is that a classical system does NOT have a thermal equilibruim magnetization. However, reality says you need quantum theory to address why there IS in fact a net magnetization, and so, this theorem breaks down on a quantum level.

Mathematically, we know that 

$$
M = - \left(\frac{\partial F}{\partial B}\right)_{T,V}
$$

So the partition function $Z$ for N particles, and each with charge q, would take the form of 

$$

Z &\propto \int\int\dots\int \exp 
\left( 
\frac{
    -E(
        \left\{
            \vec{r}_i,\vec{p}_i 
    \right\}
    )
    }
    {k_B T}
\right)
d\vec{r}_1\dots d\vec{r}_N d\vec{p}_1\dots d\vec{p}_N
\\
&\text{where}\\
&E\left(\left\{\vec{r}_i,\vec{p}_i\right\}\right)= 
\sum _i ^N \frac{
    \left( \vec{p}_{\text{can},i}-q\vec{A}_i\right)^2
    }{2m_i} +V(\vec{r}_i)

$$

All position and momentum integrals integrate from $-\infty$ to $+\infty$ and that the phase space (momentum (3N) with respect to position (3N)) is $3N + 3N = 6N$ dimensional.

Something to also keep in mind is that magnetic fields do no work because the velocity's direction of the charged particle is perpendicular to the force produced by the $\vec{B}$-field. Since no work is done by the field, the energy of the system also does not explicitly depend on the external field applied. When the external $\vec{B}$-field is removed, then the momentum reverts, as in $\vec{p}_{\text{can}}-q\vec{A}_i \mapsto \vec{p}_{\text{can}}$.

## Questions I want to ask about lecture 1:
* Why is $\sum\mu_s = -\mu_l$? 
* The diagram shown is that the mini current curls around, we are just summing the microscopic current due to the microscopic motion of electrons, but why is the diagram showing $\mu$ when $\mu$ is supposed to be pointing out of page?
* What exactly is this vector potential? are we taking into account that the magnetic field affects the vector potential, and not explicitly the external magnetic field, which alters the momentum of a charged particle?

# (MATRL204L2) Review of Quantum Mechanics and Operators
Book used:
* Griffiths 3rd Ed Intro to QM
* Griffiths 4th Ed Intro to E&M

## Quantum Origin of Magnetism

### How do you get the Hamiltonian that we work with?
When a magnetic dipole is placed under an external magnetic field, a torque would be generated as the magnetic dipole moment aligns itself to $\vec{B}_{ext}$. In this context here, we see a trippy example that magnetic field causes the dipole to do work through the torque generated from aligning the dipole to the (non-uniform) external magnetic field. (The field has to be non-uniform at different spatial points, or it won't do any work). For the sake of time, refer to Griffith E&M section 8.3 for an example of emf to show that *a magnetic field can be used as a medium to translate mechanical/external work into potential energy*. **Magnetic field, and magnetic force itselves still do no work**.

Recall that, from general physics, conserved quantity just means $\Delta E = 0$, but for the non-conservative case, 

$$
W_{nc} &= \Delta E \\
&= \int\vec{\tau} d\theta =\int(\vec{m}\times\vec{B})d\theta\\
&=mB\int_{\theta _i}^{\theta _f} \sin\theta d\theta\\
&=-mB\left[\cos\theta _f-\cos\theta _i\right]\\
\Delta U &= U(\theta _f)- U(\theta _i) = U(\theta _{\parallel}) - \cancelto{0}{U(\theta _{\perp})}\\
&=-mB\cos\theta\\
U=\mathcal{H}'&=-\vec{m}\cdot\vec{B}
$$

This becomes the first order perturbation $\mathcal{H}_z'$ that would be used for the calculation of Zeeman effect in later discussions.

## Let's solve the Schrodinger's Equation

### TDSE
Let us first accept that the schrodinger's equation simply reads

$$
i \hbar \frac{\partial}{\partial t}\ket{\Psi} &= \mathcal{H}\ket{\Psi} \\
\mathcal{H} &= -\frac{\hbar^2}{2m}\nabla^2+V \\
$$

and the laplacian depends on the coordinate of choice. Before that step, we need to find a solution for the wavefunction. To turn the partial differential equation into two ordinary differential equation requires separation of variable, and that means both sides need to equal to each other, and such is only true if they are both the same constant. We can then say

$$ 

E &= E\\
i\hbar\frac{\partial}{\partial t}\psi\phi&=\mathcal{H}\psi\phi\\
i\hbar\frac{1}{\phi}\frac{\partial}{\partial t}\phi&=\frac{1}{\psi}\left[-\frac{\hbar^2}{2m}\nabla^2+V\right]\psi\\
i\hbar\frac{1}{\phi}\frac{d\phi}{dt}&=E\\
\left[-\frac{\hbar^2}{2m}\nabla^2+V\right]&=E\\
$$

Separation of variable is completed. Now solve the two ODEs. 

$$
i\hbar\frac{1}{\phi}\frac{d\phi}{dt}&=E\\
\int\frac{d\phi}{\phi}&=-iEt/\hbar\\
\phi(t) &= \exp\left[-iEt/\hbar \right]\\
$$

and like that we get the solution for the "wiggle factor", or a time dependent phase. Now we have the wavefunction of the form 

$$
\Psi(\vec{r},t)=\phi(t)\psi(\vec{r})=e^{-iEt/\hbar}\psi(\vec{r})
$$


### TISE and Separation of Variables
Next, solve the time independent Schrodinger's equation (TISE). We have

$$
\left[-\frac{\hbar^2}{2m}\nabla^2+V\right]\psi&=E\psi\\
$$

But our choice for the spin requires the use of spherical coordinate, and the solution of this differential equation requires that the wavefunction be separated into two different components. 

We have $\psi(r,\theta,\phi) = R(r)Y(\theta,\phi)$, and that the spherical laplacian is given to be 

$$
\nabla^2 = 
\frac{1}{r^2}\frac{\partial}{\partial r}\left(r^2\frac{\partial}{\partial r}\right)
+
\frac{1}{r^2\sin\theta}
\frac{\partial}{\partial\theta}\left(\sin\theta\frac{\partial}{\partial\theta}\right)
+
\frac{1}{r^2\sin^2\theta}\left(\frac{\partial^2}{\partial\phi^2}\right)
$$

and naturally, the schrodinger's equation will read

$$
\left[-\frac{\hbar^2}{2m}\left[\frac{1}{r^2}\frac{\partial}{\partial r}\left(r^2\frac{\partial}{\partial r}\right)
+
\frac{1}{r^2\sin\theta}
\frac{\partial}{\partial\theta}\left(\sin\theta\frac{\partial}{\partial\theta}\right)
+
\frac{1}{r^2\sin^2\theta}\left(\frac{\partial^2}{\partial\phi^2}\right)\right]

+
V\right]\psi=E\psi
$$

And if you accept that the substitution of $\psi(r,\theta,\phi) = R(r)Y(\theta,\phi)$, and multiplying both sides with $\frac{-2mr^2}{\hbar^2}\frac{1}{R(r)Y(\theta,\phi)}$, then you will get 

$$
\left\{
\frac{1}{R}\frac{d}{dr}\left(r^2\frac{dR}{dr}\right)-\frac{2mr^2}{\hbar^2}\left[V(r)-E\right]
\right\}
+ 
\frac{1}{Y}
\left\{
\frac{1}{\sin\theta}\frac{\partial}{\partial\theta}\left(\sin\theta\frac{\partial Y}{\partial\theta}\right)
+
\frac{1}{\sin^2\theta}\frac{\partial^2Y}{\partial\phi^2}
\right\}
=
0
$$

We will yet again use a constant for separation of variables, and to satisfy the homogenous equation, we need a constant $C$ where $ +C - C = 0$. Additionally, since the the legendre's polynomials are used as part of the solution, this arbitrary constant is in fact $C = l(l+1)$. In which case, we have two equations from separation of variables. 

$$
\frac{1}{R}\frac{d}{dr}\left(r^2\frac{dR}{dr}\right)-\frac{2mr^2}{\hbar^2}\left[V(r)-E\right]
&=
l(l+1)
\\
\frac{1}{Y}
\left[
\frac{1}{\sin\theta}\frac{\partial}{\partial\theta}\left(\sin\theta\frac{\partial Y}{\partial\theta}\right)
+
\frac{1}{\sin^2\theta}\frac{\partial^2Y}{\partial\phi^2}
\right]
&= 
-l(l+1)
\\
l\left(l+1\right)-l\left(l+1\right)&=0\\
$$

### Angular Component of the wavefunction
Let us now extract the **Angular Component** of the Schrodinger's equation and solve for the solution (wavefunction) to the differential equation. 

Earlier, we separated the wavefunction into 2 different components $\psi(r,\theta,\phi)=R(r)Y(\theta,\phi)$. Now, $Y(\theta,\phi) = \Theta(\theta)\Phi(\phi)$, and we will need to do another separation of variable in the angular component of the wavefunction. 


$$
\frac{1}{Y}
\left[
\frac{1}{\sin\theta}\frac{\partial}{\partial\theta}\left(\sin\theta\frac{\partial Y}{\partial\theta}\right)
+
\frac{1}{\sin^2\theta}\frac{\partial^2Y}{\partial\phi^2}
\right]
&= 
-l(l+1)
\\
\sin\theta\frac{\partial}{\partial\theta}
\left(
\sin\theta\frac{\partial Y}{\partial\theta}
\right)
+
\frac{\partial^2 Y}{\partial\phi^2}
&=
-l\left(l+1\right)\sin^2\theta Y\\
\left\{
\frac{1}{\Theta}
\left[
\sin\theta\frac{d}{d\theta}\left(\sin\theta\frac{d\Theta}{d\theta}\right)    
\right]
+l\left(l+1\right)\sin^2\theta
\right\}
+
\frac{1}{\Phi}\frac{d^2\Phi}{d\phi^2}
&=
0
$$

and out of that you get two different ODEs, and have the separation constant to be $m^2$ and get

$$
\frac{1}{\Theta}
\left[
\sin\theta\frac{d}{d\theta}\left(\sin\theta\frac{d\Theta}{d\theta}\right)    
\right]
+l\left(l+1\right)\sin^2\theta
&=m^2\\
\frac{1}{\Phi}\frac{d^2\Phi}{d\phi^2} &= -m^2\\
$$

The general solution to $\Phi$ is $D^2\Phi=-m^2\Phi\mapsto\Phi(\phi)=c_1\exp\left[i m \phi\right]+ c_2\exp\left[-i m \phi\right]$ but for our immediate case, it is best to just treat it as $\Phi(\phi)=\exp\left[im\phi\right]$, and drop the minus sign. The set of integers m can include negative integers; the arbitrary constant can also be absorbed by the $\Theta$ component of this angular component of the schrodinger's equation. Lastly, the periodicity that $\Phi(\phi+ 2\pi)=\Phi(\phi)$ is also satisfied. The general solution $\Phi(\phi)=\exp\left[im\phi\right]$ works. 

Moving on to the solution for the polar angle, we have 

$$
\sin\theta\frac{d}{d\theta}\left(\sin\theta\frac{d\Theta}{d\theta}\right)
+\left[l\left(l+1\right)\sin^2\theta - m^2\right]\Theta&=0\\
\Theta(\theta)&= AP_l^m(\cos\theta)\\
$$

It has a similar form to the [General Legendre Equation](https://en.wikipedia.org/wiki/Associated_Legendre_polynomials). Simply accept that the solution uses the Legendre polynomials, and save yourself the effort in unrelated/unnecessary derivation. *Physics is not Math*. [Physics is still physics regardless of how you describe it anyways. Check section: Drude's electron theory of metals.](https://arxiv.org/pdf/physics/0612159.pdf)  

The associated Legendre function is the solution to the associated Legendre Equation, and has the form of 

$$
P_l ^m(x)&=\left(-1\right)^{|m|}\left(1-x^2\right)^{\frac{|m|}{2}}\left(\frac{d}{dx}\right)^{|m|}P_l(x)\\
P_l(x)&=\frac{1}{2^l l!}\left(\frac{d}{dx}\right)^l\left(x^2-1\right)^l\text{(This is the Rodrigues Formula)}\\
$$

The Legendre function has two parameters, $m$ and $l$, where the $l$ determines the degree of the [Legendre Polynomial](https://en.wikipedia.org/wiki/Legendre_polynomials), and its parity (mirror symmetry). The $m$ integer shows the $\sin\theta$ term in the Legendre function where if $x = \cos\theta$, then $(1-\cos^2\theta)^{m/2}=\sin^m\theta$.

Some takeaways in the general Legendre Function:
1. if $m > l$, then $P^m_l = 0$
2. for any given $l$, the number of $m$'s available is $(2l+1)$. 
    |    orbital quantum number $l$   |     "magnetic" quantum number $m$       |
    | :------- | -----:         |
    | $0$      |    $0$         |
    | $1$      |    $-1,0,+1$   |
    | $\dots$  |    $\dots$     |
    | $5$      | $-5,-4,-3,...,0,...,+3,+4,+5$|
3. If you look at the above table, you see very clearly why $|m|>l$ is simply not allowed. The magnetic quantum number should only be within the range of orbital angular quantum number $-l\leq m\leq +l$.

So after all, we finally have an expression for the spherical harmonics $Y(\theta,\phi)$

Earlier we said that when deriving $\Phi(\phi)$ that we can just let $\Theta(\theta)$ absorb the normalization constant. We now know that the general solution of $Y(\theta,\phi)$ takes the form $Y(\theta,\phi)=A\exp\left[im\phi\right]P_l^m(\cos\theta)$

To normalize it, throw the full wavefunction into the 3D volume integral

$$
1&= \int\int\int|\psi^{*}\psi|r^2\sin\theta dr d\theta d\phi \\
&= \int R^{*}(r) R(r)r^2dr\int\int Y^{*}(\theta,\phi)Y(\theta,\phi)\sin\theta d\theta d\phi\\
$$

But you want to normalize the two different components of the wavefunction separately, and this is legal because $1\times 1 = 1$. 

$$
1&=\int R^{*}(r) R(r) r^2 dr\\ 
1&=\int\int Y^{*}(\theta,\phi)Y(\theta,\phi)\sin\theta d\theta d\phi\\
1&=\int\int A^{*}e^{-im\phi}P_l^{*m}(\cos\theta)Ae^{im\phi}P_l^m(\cos\theta) \sin\theta d\theta d\phi\\
$$

Skipping the derivation for the normalization, and you get the solution for spherical harmonics to be 

$$
\boxed{
Y_l^m(\theta,\phi)=\sqrt{
    \frac{(2l+1)}{4\pi}\frac{(l-m)!}{(l+m)!}
    }
    e^{im\phi}P_l^m(\cos\theta)
}
$$

### Rabbit hole #002 
Why can you use the solution of the general legendre equation to a different differential equation? This is an entirely unrelated question to physics, but it would be helpful to know why. 

### Things to keep in the back of your mind
* Spherical Harmonics cannot capture half integer angular momentum.
* Spherical Harmonics is the embodiment that we have a spherically symmetrical potential. However, in a solid, you no longer have this continuous rotational symmetry.
* When symmetry is broken in an attempt to align the magnetic dipole moment to the external field, the (orbital) degeneracy is "lifted" and requires the use of perturbation theory to find the correction. The orbital degeneracy is what generates the orbital magnetism. This is the so-called "crystal field solution". 

## What is angular momentum operators?
Classical description of angular momentum is 

$$
\vec{L} = \vec{r}\times\vec{p}
$$

and the linear momenta has the form of 

$$ 
&(y p_z - zp_y)\hat{x} -(xp_z-zp_x)\hat{y}+(xp_y-yp_x)\hat{z}\\
=&\hat{L}_x + \hat{L}_y + \hat{L}_z
$$

The commutator gives

$$
&\left[\hat{L}_x,\hat{L}_y\right] =\hat{L}_x\hat{L}_y-\hat{L}_y\hat{L}_x=i\hbar\hat{L}_z\\
&\left[\hat{L}_y,\hat{L}_z\right] =\hat{L}_x\\
&\left[\hat{L}_z,\hat{L}_x\right] =\hat{L}_y\\
$$

The above 3 commutation show that these operators do not have simultaneous eigenfunctions.

However, $\left[\hat{L}^2,\hat{L}_x\right]=\left[\hat{L}^2,L_y\right]=\left[\hat{L}^2,\hat{L}_z\right]=0$, and since the two operators are compatible, they can have simultaneous eigenfunctions and can even share eigenvalues. Note also that the typical convention is to have $\hat{L_z}$ as the special direction. 

In Quantum Harmonic Oscillator, you develop ladder operators to move through the different eigenstates, and the different energies of the harmonic oscillator.

Now, define the ladder operators. 

$$
\hat{L}_+ = \hat{L}_x+i\hat{L}_y;\hat{L}_- = \hat{L}_x - i\hat{L}_y;\\
\left[\hat{L}_z,\hat{L}_{\pm}\right]=\pm\hbar\hat{L}_{\pm}
$$

Now we can use the algebra trick to find the simultaneous eigenfunctions of $\hat{L}^2$ and $\hat{L}_z$. Suppose we have an electronic wavefunction $\ket{\psi}$, and have the operators $\hat{L}^2$ and $\hat{L}_z$ acting on it, we can get

$$
\hat{L}^2\ket{\hat{L}}          &=\alpha\ket{\psi}\\
\hat{L}_z\ket{\psi}             &=\beta\ket{\psi}\\
\hat{L}^2\hat{L}_{\pm}\ket{\psi}&=\hat{L}_{\pm}\hat{L}^2\ket{\psi}\\
                                &=\hat{L}_{\pm}\alpha\ket{\psi}\\
                                &=\alpha\hat{L}_{\pm}\ket{\psi}\\
$$

The above is legal with $\hat{L}_{\pm}$ because we know that $\left[\hat{L}^2,\hat{L}_{x/y/z}\right]=0$ and the $i$ can simply be thought of as a constant. 

Applying the same concept to the $\hat{L}_z$ operator,

$$
\left[\hat{L}_{z},\hat{L}_{\pm}\right]\ket{\psi}=\left(\hat{L}_z\hat{L}_{\pm}-\hat{L}_{\pm}\hat{L}_{z}\right)\ket{\psi}
&=\pm\hbar\hat{L}_\pm\ket{\psi}\\
\hat{L}_z\hat{L}_{\pm}\ket{\psi}
&=\left(\pm\hbar\hat{L}_{\pm}+\hat{L}_{\pm}\hat{L}_z\right)\ket{\psi}\\
&=(\pm\hbar+\beta)\hat{L}_\pm\ket{\psi}\\
$$

and so by some clever algebraic tricks, we now know that the operator $\hat{L}_z\mapsto\left(\pm\hbar+\beta\right)$ carries such eigenvalue depending on the raising or lowering operator. 


## Correlating the eigenvalues of $l$ and $m$:
Let us now correlate the two different eigenvalues of $l$ orbital angular momentum quantum number and $m$ magnetic quantum number. 

we have 

$$
\left<\hat{L}^2\right> = \bra{\psi}\hat{L}^2\ket{\psi}= \left<\hat{L}_x^2\right>+ \left<\hat{L}_y^2\right>+\left<\hat{L}_z^2\right>
$$

Intuitively, we have specified previously that $hat{z}$ is the special direction, and we correlate this special direction to the direction along the magnetic dipole moment. 

By more clever algebraic tricks, and since we know that the expectation value of each of the $\left<\hat{L}^2\right>\geq 0$, we can then incorporate what we have previously stated to say

$$
\hat{L}^2&\mapsto\alpha\\
\hat{L}_z&\mapsto\beta \\
\because \left<\hat{L}^2\right>&=\left<\hat{L}_x^2\right>+\left<\hat{L}_y^2\right>+\left<\hat{L}_z^2\right>\geq 0\\
\therefore \left<\hat{L}^2\right>&=\alpha\geq\beta^2\\
$$

I have used the symbol "$\mapsto$" to denote the operator's corresponding eigenvalue. Get used to it. 

Let us take our final step and find the correspondance of the eigenvalues to the quantum numbers. 
It is important to note that since $\beta$ is bounded by $\alpha$, then we can easily say that the followings are true. You are imposing the equality condition from the expectation value to impose the maximum and minimum of the $\beta$ value from $\alpha$.

$$
\alpha            &= \hbar l(l+1)\\
\beta             &= \hbar m     \\
\beta_{\text{max}}&=+\hbar l     \\
\beta_{\text{min}}&=-\hbar l     \\
$$

The angular momentum of the electronic wavefunction is a spherical harmonic. The $\theta$ component is associated to legendre polynomial of integer $l$.

# (MATRL204L4) Review of Spin (supplemented with Griffiths QM)
Books used for this section:
* Intro to Quantum Mechanics by Griffiths 3rd Ed. 

Recall that from our last lecture, we have derived the vector potential used for the magnetic field, a coordinate free expression of the magnetic field. The vivid physical reality of electrons in a Magnetic Field can be explained on a few different levels. 
* Electron in a Magnetic Field
    1. magnetic dipole moment $\vec{m}$ or some books might use $\vec{\mu}$
    2. Separate components to the spin, 
        1. Electron **Spin** Dipole moment 
        2. Electron **Orbital** Dipole moment
    3. Zeeman Effect, which uses perturbation to account for the dipole moment under a uniform external magnetic field $\vec{B}$. 