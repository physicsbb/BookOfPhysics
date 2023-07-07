# Linear Algebra

## Linear Combination in Physics
As Griffiths pointed out in his Quantum Mechanics textbook, a state is described by the wavefunction, which can be written as a vector; the observable is represented by an $n\times n$ operator, be it linear or not. Naturally, the operator happens to have a matrix representation, then an $n\times n$ matrix would act on the state vector, hence a linear transformation. The most friendly approach to quantum mechanics is to realize that a part of quantum mechanics satisfy the Eigenequation. That is, the (eigen)energy is an eigenvalue; the state vector is an eigenvector (or an eigenstate); the operator is a linear operator.

Let us begin with the description of the completeness of a function. 

By definition, the completeness of a function is a linear combination of its basis vectors (its basis functions). We are most accustomed to the linear algebra fashion of writing your vector as a column vector, because that is the easiest introduction to the treatement of a vector. 

The simplest n-dimensional vector takes the form of
$$
\[
    \begin{bmatrix}x_1 \\ 0   \\ 0   \vdots \\ 0   \end{bmatrix} + 
    \begin{bmatrix}  0 \\ x_2 \\ 0   \vdots \\ 0   \end{bmatrix} + 
    \begin{bmatrix}  0 \\ 0   \\ x_3 \vdots \\ 0   \end{bmatrix} + 
    \begin{bmatrix}  0 \\ 0   \\ 0   \vdots \\ x_n \end{bmatrix} + 
\]
$$ 

which, if I write them as ket vector in the bra-ket (dirac) notation, it would look like

$$
\[
    | \psi_1 \rangle + |\psi_2\rangle 
    + | \psi_3 \rangle + \dots + |\psi_4 \rangle
\]
$$
