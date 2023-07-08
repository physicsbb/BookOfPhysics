# Linear Algebra

## Linear Combination in Physics
A state is described by the wavefunction, which can be written as a vector; the observable is represented by an $n\times n$ operator, be it linear or not. Naturally, the operator happens to have a matrix representation, then an $n\times n$ matrix would act on the state vector, hence a linear transformation. The most friendly approach to quantum mechanics is to realize that a part of quantum mechanics satisfy the Eigenequation. That is, the (eigen)energy is an eigenvalue; the state vector is an eigenvector (or an eigenstate); the operator is a linear operator. Wavefunction lives in Hilbert Space. This "book" will only discuss the linear algebra up to the physicist's standard –– no $\epsilon \delta$ proofs, we simply accept that the math just works as perfectly fine tools.

Let us begin with the description of the completeness of a function. 

By definition, the completeness of a function is a linear combination of its basis vectors (its basis functions). We are most accustomed to the linear algebra fashion of writing your vector as a column vector, because that is the easiest introduction to the treatement of a vector. 

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

Keys to understanding the completeness of a function: 
1. we are working in n dimension. 
2. the general solution to a system of equations in n-dimensional space has the form 

$$ 
\begin{align}
    y(x) = c_1 y_1(x) + c_2 y_2(x) +  c_3 y_3(x) + \dots + c_n y_n(x)
\end{align}
$$

In which case, we can write the general solution as a power series.

$$
\begin{align}
    y(x) = \sum _{n=1} ^{N} c_n y_n(x)
\end{align}
$$

In Quantum Mechanics, wavefunctions live in Hilbert Space. For mastery of Hilbert Space, refer to a topic called functional analysis in mathematics which is not meant to be covered in here. 