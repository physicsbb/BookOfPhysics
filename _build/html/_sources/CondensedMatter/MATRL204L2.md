# (MATRL204L2) Review of Quantum Mechanics and Operators
Book used:
* Griffiths 3rd Ed Intro to QM
* Griffiths 4th Ed Intro to E&M

## Quantum Origin of Magnetism

### How do you get the Hamiltonian that we work with?
When a magnetic dipole is placed under an external magnetic field, a torque would be generated as the magnetic dipole moment aligns itself to $\vec{B}_{ext}$. In this context here, we see a trippy example that magnetic field causes the dipole to do work through the torque generated from aligning the dipole to the (non-uniform) external magnetic field. (The field has to be non-uniform at different spatial points, or it won't do any work). For the sake of time, refer to Griffiths E&M section 8.3 for an example of emf to show that *a magnetic field can be used as a medium to translate mechanical/external work into potential energy*. **Magnetic field, and magnetic force itselves still do no work**.

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

But our choice for the spin requires the use of spherical coordinate, and we are working with ***spherically symmetric potential***, and the solution of this differential equation requires that the wavefunction be separated into two different components. 

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
    | $\vdots$  |    $\vdots$     |
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

## What are angular momentum operators?
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

In Quantum Harmonic Oscillator, you develop ladder operators to move through the different eigenstates, and the different energies of the harmonic oscillator. We can also devise the same tools for spherically symmetric potential. The spherically symmetric potential can be used to model physics such as Hydrogen atom.

Now, define the ladder operators. 

$$
\hat{L}_+ &= \hat{L}_x + i\hat{L}_y\\
\hat{L}_- &= \hat{L}_x - i\hat{L}_y\\
\left[\hat{L}_z,\hat{L}_{\pm}\right]&=\pm\hbar\hat{L}_{\pm}
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

Intuitively, we have specified previously that $\hat{z}$ is the special direction, and we correlate this special direction to the direction along the magnetic dipole moment. 

By more clever algebraic tricks, and since we know that the expectation value of each of the $\left<\hat{L}^2\right>\geq 0$, we can then incorporate what we have previously stated to say

$$
\hat{L}^2&\mapsto\alpha\\
\hat{L}_z&\mapsto\beta \\
\because \left<\hat{L}^2\right>&=\left<\hat{L}_x^2\right>+\left<\hat{L}_y^2\right>+\left<\hat{L}_z^2\right>\geq 0\\
\therefore \left<\hat{L}^2\right>&=\alpha\geq\beta^2\\
$$

I have used the symbol "$\mapsto$" to denote the operator's corresponding eigenvalue. Get used to it. 

Let us take our final step and find the correspondance of the eigenvalues to the quantum numbers. 
It is important to note that since $\beta$ is bounded by $\alpha$, then we can easily say that the followings are true. You are using the equality condition from the expectation value to impose the maximum and minimum of the $\beta$ value from $\alpha$.

$$
\alpha            &= \hbar l(l+1)\\
\beta             &= \hbar m     \\
\beta_{\text{max}}&=+\hbar l     \\
\beta_{\text{min}}&=-\hbar l     \\
$$

The angular momentum of the electronic wavefunction is a spherical harmonic. The $\theta$ component is associated to legendre polynomial of integer $l$.

Let us look at the allowed quantum numbers a little more carefully. 

