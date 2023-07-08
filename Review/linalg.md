# Linear Algebra in Physics

## Elementary Descriptions Of Linear Algebra and notations
A state is described by the wavefunction, which can be written as a vector; the observable is represented by an $n\times n$ operator, be it linear or not. Naturally, the operator happens to have a matrix representation, then an $n\times n$ matrix would act on the state vector, hence a linear transformation. The most friendly approach to quantum mechanics is to realize that a part of quantum mechanics satisfy the Eigenequation. That is, the (eigen)energy is an eigenvalue; the state vector is an eigenvector (or an eigenstate); the operator is a linear operator. Wavefunction lives in Hilbert Space. This "book" will only discuss the linear algebra up to the physicist's standard –– no $\varepsilon - \delta$ proofs, we simply accept that the math just works as perfectly fine tools.

We are most accustomed to the linear algebra fashion of writing your vector as a column vector, because that is the easiest introduction to the treatement of a vector. 

The simplest n-dimensional vector takes the form 

$$
\begin{align}
    \vec{e_1} + \vec{e_2} + \vec{e_3} + \dots + \vec{e_n}
    =
    \begin{bmatrix}x_1 \\ 0   \\ 0   \\ \vdots \\ 0   \end{bmatrix} + 
    \begin{bmatrix}  0 \\ x_2 \\ 0   \\ \vdots \\ 0   \end{bmatrix} + 
    \begin{bmatrix}  0 \\ 0   \\ x_3 \\ \vdots \\ 0   \end{bmatrix} +
    \dots +  
    \begin{bmatrix}  0 \\ 0   \\ 0   \\ \vdots \\ x_n \end{bmatrix} 
\end{align}
$$


which, if I write them as ket vector in the bra-ket (dirac) notation, it would look like

$$
\begin{align}
    |\psi\rangle
    =
    | \psi_1 \rangle + |\psi_2\rangle 
    + | \psi_3 \rangle + \dots + |\psi_n \rangle
\end{align}
$$

Moving on, when we talk about what a linear combination is, we typically mean if the solution is spanned by the set. Hence, a linear combination. In lower division linear algebra, you were only used to working with vectors in, at max 5 or 6 dimensions. 

Keys to remember: 
1. we are working in n dimensions. 
2. the general solution to a system of equations in n-dimensional space has the form 

$$ 
\begin{align}
    \vec{v}(x) = c_1 \vec{v}_1(x) + c_2 \vec{v}_2(x) +  c_3 \vec{v}_3(x) + \dots + c_n \vec{v}_n(x)
\end{align}
$$

In which case, we can write the general solution as a summation series.

$$
\begin{align}
    \vec{v}(x) = \sum _{n=1} ^{N} c_n \vec{v}_n(x)
\end{align}
$$

Now that we have already established a basic understanding of how to work with n-dimensional vectors, we can move onto Hilbert Space: infinite dimensional space. 

In Quantum Mechanics, wavefunctions live in Hilbert Space. For mastery of Hilbert Space, refer to a topic called [functional analysis](https://en.wikipedia.org/wiki/Square-integrable_function) in mathematics which is not meant to be covered in here. 

Since the mathematical model of quantum mechanics builds off of Hilbert Space, and that Hilbert Space has a property that 

````{prf:definition}
:label: square-integrability
The set of all $\textbf{square-integrable}$ functions, on specified interval

$$
\begin{align}
    f(x) &\text{ such that } \int _a ^b f^{*}(x) f(x) dx < \infty \\ & \text{ where a and b are almost always } \pm \infty
\end{align}
$$

contributes to a (much smaller) vector subspace (that lives in $\mathbb{R}^{\infty}$).
````

Since the vectors are infinite dimensional, you would have to add them infinitely. That is 

$$
\begin{align}
    \sum _{i=1} ^{\infty} \vec{e_i} &= 
    \vec{e_1} + \vec{e_2} + \vec{e_3} + \dots + \vec{e_n} + \dots 
    \\ \\
    \begin{bmatrix}x_1 \\ x_2 \\ x_3 \\ \vdots \\ x_n \\ \vdots  \end{bmatrix} &= 
    \begin{bmatrix}x_1 \\ 0   \\ 0   \\ \vdots \\ 0   \\ \vdots  \end{bmatrix} + 
    \begin{bmatrix}  0 \\ x_2 \\ 0   \\ \vdots \\ 0   \\ \vdots  \end{bmatrix} + 
    \begin{bmatrix}  0 \\ 0   \\ x_3 \\ \vdots \\ 0   \\ \vdots  \end{bmatrix} +
    \dots +  
    \begin{bmatrix}  0 \\ 0   \\ 0   \\ \vdots \\ x_n \\ \vdots  \end{bmatrix} + 
    \dots 
    \\ \\
    | \psi   \rangle &= 
    | \psi_1 \rangle + |\psi_2 \rangle + | \psi_3 \rangle + \dots + |\psi_n \rangle + \dots
\end{align}
$$


What I have denoted above are the same expressions but in general coordinate, column vectors, and dirac notation.

Now, we are finally ready to talk about completeness of a function. 

## Completeness of a function & Fourier's Trick
To reiterate, a function can be a vector. 

As I quote Griffiths here, "a set of functions is complete if any other function (in Hilbert Space) can be expressed as a linear combination of them" 

$$
\begin{align}
    f(x) 
    &= 
    \sum_{n=1} ^{\infty} c_n f_n(x) 
    \\&= 
    c_1f_1(x) + c_2f_2(x) + c_3f_3(x) + \dots + c_nf_n(x) + \dots
\end{align}
$$

Or in Dirac notation, it would be 

$$
\begin{align}
    |\psi\rangle &=
    c_1|\psi _1\rangle + c_2|\psi _2\rangle + \dots + c_n|\psi _n\rangle + \dots \\ &= 
    \sum _{i=1} ^{\infty} c_i |\psi _i\rangle
\end{align}
$$

Note that $f_n(x)$ is just any generic function. If this is still confusing to you (because it was confusing to me at first), then to reverse our progress (back to ancient understanding), the above expression, if written as vectors, is just 

$$
\begin{align}
    \begin{bmatrix} c_1x_1\\c_2x_2\\c_3x_3\\ \vdots \\ c_nx_n \\ \vdots \end{bmatrix}
    =
    c_1\begin{bmatrix} x_1\\  0   \\  0   \\ \vdots \\  0   \\\vdots \end{bmatrix} + 
    c_2\begin{bmatrix} 0  \\ x_2  \\  0   \\ \vdots \\  0   \\\vdots \end{bmatrix} + 
    c_3\begin{bmatrix} 0  \\  0   \\ x_3  \\ \vdots \\  0   \\\vdots \end{bmatrix} +
    \dots +  
    c_n\begin{bmatrix} 0  \\  0   \\  0   \\ \vdots \\ x_n  \\\vdots \end{bmatrix} + 
    \dots
\end{align}
$$

In other words, 
````{prf:definition}
:label: completeness
A set $\mathcal{F}\in\{f_1,f_2,\dots,f_n,\dots\}$ is complete if any function $f_{\textbf{any}}(x) \in \textbf{Span}\{\mathcal{F}\}$. 

A set $\mathcal{F} \in \{f_1, f_2, \dots , f_n, \dots\}$ (of functions) is complete if any other vectors (or functions) $f_{\textbf{any}}(x)$ can be spanned by (is a linear combination of) the set $\mathcal{F}$. 
````
To demonstrate Fourier's trick, with the assumption in mind that a basis should be orthonormal (of unit length 1, and perpendicular to each other). 

$$
\begin{align}
    c_n &= 
    \langle f_n|f \rangle \\&=
    \begin{bmatrix} 0      &      0   &  \dots  &      f_n &  \dots \end{bmatrix}
    \begin{bmatrix} c_1 f_1\\ c_2 f_2 \\ \vdots \\ c_n f_n \\ \vdots\end{bmatrix} 
    \\&=
    \begin{bmatrix} 0      &      0   &  \dots  &      f_n &  \dots \end{bmatrix}
    \left(
        c_1\begin{bmatrix} f_1\\  0   \\  0   \\ \vdots \\  0   \\\vdots \end{bmatrix} + 
    c_2\begin{bmatrix} 0  \\ f_2  \\  0   \\ \vdots \\  0   \\\vdots \end{bmatrix} + 
    c_3\begin{bmatrix} 0  \\  0   \\ f_3  \\ \vdots \\  0   \\\vdots \end{bmatrix} +
    \dots +  
    c_n\begin{bmatrix} 0  \\  0   \\  0   \\ \vdots \\ f_n  \\\vdots \end{bmatrix} + 
    \dots  
    \right)
\end{align}
$$

which, since the set $\mathcal{F}$ is orthonormal, all other terms vanish. For example,

````{prf:definition}
:label: kroneckerDelta
$$
\begin{align}
    \begin{bmatrix} 0      &      0   &  \dots  &      f_n &  \dots \end{bmatrix}
    c_1\begin{bmatrix} f_1\\  0   \\  0   \\ \vdots \\  0   \\\vdots \end{bmatrix}
    = 0 \because 1 \neq n
\end{align}
$$

$f_n\cdot f_1$ vanishes and only one term ($f_n\cdot f_n$) survives. 

$$
\begin{align}
    c_n &= 
    \begin{bmatrix} 0      &  0   &  \dots  &  f_n &  \dots \end{bmatrix}
    \cdot
    c_n\begin{bmatrix} 0  \\  0   \\ \vdots \\ f_n \\\vdots \end{bmatrix}     
    \\&=
    c_n \cancelto{1 \textbf{ due to orthonormality}}{
    \begin{bmatrix} 0   &  0   &  \dots  &  f_n &  \dots \end{bmatrix}
    \cdot
    \begin{bmatrix} 0  \\  0   \\ \vdots \\ f_n \\\vdots \end{bmatrix}
    }
\end{align}
$$


$$
    \langle \psi | \psi \rangle = \sum_i \sum_j \psi_i \psi_j \delta_{ij}
    \rightarrow \delta_{ij} =
    \begin{cases}
    1 \text{ if } i=j\\
    0 \text{ if } i\neq j
    \end{cases}
$$
````

The above two vectors' inner (higher-dimensional dot) product denotes the essence of kronecker delta $\delta_{ij}$. 

Now, we are finally ready for Dirac notation. (at this point you should have no reason to not understand what Fourier's trick is given the gruesome detail by writing everything out by brute force.)

$$ 
\begin{align}
    c_n &=
    \langle f_n | f\rangle 
    \\ &=
    \langle f_n |\big( c_1|f_1\rangle+ c_2|f_2\rangle + \dots + c_n|f_n \rangle + \dots \big)
    \\ &=
    c_1\cancelto{0 = \delta_{n1}}{\langle f_n |f_1\rangle} +
    c_2\cancelto{0 = \delta_{n2}}{\langle f_n |f_2\rangle} + 
    \dots  
    \langle f_n | c_n |f_n \rangle + 
    \dots
    \\&=
    c_n\cancelto{1 = \delta_{nn}}{\langle f_n | f_n \rangle}
    \\
    c_n&=c_n
\end{align}
$$





