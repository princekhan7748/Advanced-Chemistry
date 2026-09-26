# Appendix A — Mathematical Toolkit

*Reference*

This appendix collects, without new derivation, the mathematical results used throughout the book. Each entry gives the definition or result actually used, and points back to where it first appeared.

---

## A.1 Complex numbers

A complex number $z=x+iy$, with $i^2=-1$, has real part $\mathrm{Re}(z)=x$ and imaginary part $\mathrm{Im}(z)=y$. Its complex conjugate is $z^*=x-iy$, and its modulus squared is $\lvert z\rvert^2=z^*z=x^2+y^2$.

**Polar/Euler form:**

$$
z = re^{i\theta} = r(\cos\theta+i\sin\theta), \qquad r=\lvert z\rvert,\ \theta=\arg(z).
$$

Quantum-mechanical wavefunctions are complex-valued (Chapter 2); only $\lvert\psi\rvert^2=\psi^*\psi$, a real, non-negative quantity, is directly observable as a probability density. A plane wave $\psi(x)=Ae^{ikx}$ (Chapter 3) and a time-evolution factor $e^{-iEt/\hbar}$ (Chapter 2) are the two most common complex exponentials in the book.

## A.2 Linear algebra and vector spaces

A **vector space** is a set closed under addition and scalar multiplication satisfying the usual axioms (associativity, distributivity, existence of a zero vector). Quantum states live in a complex vector space called **Hilbert space** (Chapter 2), with an inner product $\langle\phi\vert\psi\rangle$ satisfying

$$
\langle\phi\vert\psi\rangle = \langle\psi\vert\phi\rangle^*, \qquad \langle\psi\vert\psi\rangle \geq 0.
$$

A set of vectors $\{\vert n\rangle\}$ is **orthonormal** if $\langle m\vert n\rangle=\delta_{mn}$ (the Kronecker delta: $1$ if $m=n$, $0$ otherwise), and **complete** if any state can be written as $\vert\psi\rangle=\sum_n c_n\vert n\rangle$ with $c_n=\langle n\vert\psi\rangle$. Molecular orbitals as linear combinations of atomic orbitals (Chapter 10) and vibrational normal modes as linear combinations of Cartesian displacements (Chapter 11) are both expansions of this kind.

## A.3 Matrices

A matrix $A$ represents a linear operator in a chosen basis. Its **Hermitian conjugate** (or adjoint) $A^\dagger$ is the complex conjugate of its transpose, $(A^\dagger)_{ij}=A_{ji}^*$. A matrix is **Hermitian** if $A^\dagger=A$ (used for every observable operator, Chapter 2 and Appendix B), and **unitary** if $A^\dagger A = \mathbb{1}$ (used for basis changes and for symmetry operations, Appendix C).

Matrix multiplication is not commutative in general: $AB\neq BA$. The failure of two operators to commute, measured by the commutator $[A,B]=AB-BA$, is the algebraic origin of the uncertainty principle (Chapter 2, Appendix B).

## A.4 Eigenvalue problems

An **eigenvalue equation** for an operator $\hat A$ and a nonzero vector $\vert\psi\rangle$ is

$$
\hat A\vert\psi\rangle = a\vert\psi\rangle,
$$

with $a$ the eigenvalue and $\vert\psi\rangle$ the eigenvector (or eigenfunction). For an $N\times N$ matrix, eigenvalues are found from the **secular equation**

$$
\det(A-a\mathbb{1}) = 0,
$$

an $N$-th degree polynomial in $a$ with (up to) $N$ roots. Hermitian matrices always have real eigenvalues and an orthogonal (or orthonormal, after normalization) set of eigenvectors — the mathematical fact underlying every observable in quantum mechanics (Appendix B). The time-independent Schrödinger equation (Chapter 2) is itself an eigenvalue equation, $\hat H\psi=E\psi$; the Hückel secular equations (Chapter 12) and Hartree–Fock/Roothaan equations (Chapter 9, Chapter 14) are finite-matrix versions of exactly the same problem.

## A.5 Differential equations

Most equations solved in Part I are **linear, ordinary or partial differential equations** with boundary or periodicity conditions that select a discrete set of allowed solutions:

- The particle-in-a-box (Chapter 3) solves $-\dfrac{\hbar^2}{2m}\dfrac{d^2\psi}{dx^2}=E\psi$ with $\psi(0)=\psi(L)=0$.
- The rigid rotor (Chapter 4) and the hydrogen atom's angular part (Chapter 6) solve the same angular equation on the sphere, with single-valuedness in $\phi$ forcing integer $m$.
- The harmonic oscillator (Chapter 5) solves $-\dfrac{\hbar^2}{2m}\dfrac{d^2\psi}{dx^2}+\tfrac12 m\omega^2x^2\psi=E\psi$, solved by Hermite polynomials times a Gaussian.

In every case, it is the **boundary condition**, not the differential equation alone, that produces quantization; the same equation without boundary conditions (a free particle, Chapter 3) has a continuous spectrum.

## A.6 Fourier transforms

A function and its Fourier transform,

$$
\tilde f(k) = \frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty} f(x)\,e^{-ikx}\,dx,
$$

form a conjugate pair: a function sharply localized in $x$ has a broad transform in $k$, and vice versa. This is the direct mathematical origin of the position–momentum uncertainty relation (Chapter 2, Appendix B): position and momentum wavefunctions are Fourier transforms of one another, and no function can be made arbitrarily narrow in both variables simultaneously.

## A.7 Probability and statistics

The Born interpretation (Chapter 2) treats $\lvert\psi(x)\rvert^2\,dx$ as the probability of finding a particle between $x$ and $x+dx$, so $\psi$ must be normalized, $\int\lvert\psi\rvert^2\,dx=1$. The **expectation value** of an observable is

$$
\langle A\rangle = \int \psi^*\hat A\psi\,dx = \langle\psi\vert\hat A\vert\psi\rangle.
$$

Statistical mechanics (Chapter 15) uses the same probabilistic language at the level of an entire ensemble of molecules: the Boltzmann distribution gives the probability of a molecule occupying state $i$ as $p_i=e^{-E_i/k_BT}/q$, with the partition function $q=\sum_i e^{-E_i/k_BT}$ acting as the normalization constant, exactly analogous to normalizing $\psi$.

## A.8 Vector calculus

The gradient, divergence, curl and Laplacian appear throughout the book in their standard Cartesian forms; the one used constantly is the Laplacian in the kinetic-energy operator,

$$
\hat T = -\frac{\hbar^2}{2m}\nabla^2, \qquad \nabla^2 = \frac{\partial^2}{\partial x^2}+\frac{\partial^2}{\partial y^2}+\frac{\partial^2}{\partial z^2}.
$$

In spherical coordinates $(r,\theta,\phi)$, used for the hydrogen atom (Chapter 6) and the rigid rotor (Chapter 4), the Laplacian separates into a radial part and an angular part, the latter being (up to a constant) the operator $\hat L^2$ whose eigenfunctions are the spherical harmonics $Y_l^m(\theta,\phi)$.

---

**See also:** Appendix B (quantum-mechanical formalism built on this toolkit) and Appendix C (group theory, which is linear algebra specialized to symmetry operations).
