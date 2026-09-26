# Chapter 3 — Exactly Solvable Quantum Systems

*Part I · The Quantum Structure of Matter*

Chapter 2 made a claim that has not yet been shown: **quantization is not an extra postulate. It comes from solving $\hat H\psi=E\psi$ with acceptable boundary conditions.** This chapter demonstrates it in the simplest settings where the equation can be solved completely.

The opening question:

> **Why does confining a particle produce discrete energies, while a free particle does not?**

A warning belongs at the start. Exactly solvable systems are rare. Real molecules are not boxes. These systems earn their place for three reasons: they show the *mechanism* of quantization without mathematical clutter, their solutions become the building blocks of approximations later, and, as Section 3.5 shows, crude versions of them already explain real chemistry (and show precisely how it fails).

| Mathematical result | Chemical destination |
|---|---|
| Continuous spectrum of the free particle | Ionization continuum, scattering, plane-wave basis sets |
| Boundary conditions → discrete levels | Energy levels of any bound electron |
| $E\propto1/L^2$ | Confinement energy, size-dependent color of nanocrystals |
| Separation of variables, degeneracy | Orbital degeneracy, symmetry and its lifting |
| $\langle x\rangle,\langle p\rangle$, uncertainty | Why localization costs energy |
| 1D box for $\pi$ electrons | Color of conjugated molecules |

**Roadmap.** No confinement (3.1) → confinement in one dimension (3.2) → more dimensions and degeneracy (3.3) → what the states tell us (3.4) → a real chemical application (3.5).

---

## 3.1 Free particle

**Setup.** No forces: $V=0$ everywhere. The time-independent Schrödinger equation is

$$
-\frac{\hbar^2}{2m}\frac{d^2\psi}{dx^2}=E\psi
$$

**Solution.** For any $E>0$ the solutions are $e^{ikx}$ and $e^{-ikx}$, with

$$
E=\frac{\hbar^2k^2}{2m}
$$

Each is a momentum eigenfunction with $p=\pm\hbar k$. Nothing restricts $k$, so **every energy $E\ge0$ is allowed**: the spectrum is continuous. No boundary condition means no quantization.

**Interpretation.**

- The two solutions $e^{\pm ikx}$ have the same energy: a two-fold degeneracy, reflecting the symmetry between left and right.
- $|e^{ikx}|^2=1$ everywhere, so a plane wave cannot be normalized to one. It is an idealization, and physical states are **wavepackets**, superpositions $\psi(x)=\int A(k)e^{ikx}dk$ with a spread of momenta.
- A wavepacket moves with group velocity $d\omega/dk=\hbar k/m=p/m$, the classical velocity. This is the correspondence principle (Section 2.11) at work. A narrow packet (small $\Delta x$) must have a large spread of momenta ($\Delta p\ge\hbar/2\Delta x$), so it spreads as time passes.

**Chemical consequence.** Free-particle states describe an electron that has been ejected from an atom, so they are the final states in photoionization. Plane waves also serve as the basis functions for electrons in periodic solids, and appear later when we compute translational motion in gases.

> **Status of the principle: free-particle spectrum**
> *Derived* from the Schrödinger equation. Its continuous character is the reference against which quantization in later sections is measured.

---

## 3.2 One-dimensional particle in a box

**Setup.** A particle is confined between two impenetrable walls:

$$
V(x)=\begin{cases}0,&0<x<L\\ \infty,&\text{otherwise}\end{cases}
$$

Outside the box $\psi=0$ (an infinite potential cannot be occupied). Inside, the equation is the free-particle equation, with general solution $\psi=A\sin kx+B\cos kx$ and $E=\hbar^2k^2/2m$.

**Boundary conditions.** The wavefunction must be continuous, so it must vanish at both walls:

$$
\psi(0)=0\;\Rightarrow\;B=0,\qquad \psi(L)=0\;\Rightarrow\;\sin kL=0\;\Rightarrow\;k=\frac{n\pi}{L}
$$

The condition $\sin kL=0$ is what discretizes the energy. Only special values of $k$ fit. Here $n=1,2,3,\dots$; $n=0$ gives $\psi=0$ (no particle) and negative $n$ gives the same states again with a sign change.

**Energies and wavefunctions.** Normalizing ($\int_0^L|\psi|^2dx=1$) fixes $A=\sqrt{2/L}$:

$$
\boxed{E_n=\frac{n^2h^2}{8mL^2}=\frac{n^2\pi^2\hbar^2}{2mL^2}},\qquad
\psi_n(x)=\sqrt{\frac2L}\sin\frac{n\pi x}{L}
$$

The wavefunctions are orthonormal: $\int_0^L\psi_m\psi_n\,dx=\delta_{mn}$ (Section 2.5).

**Physical interpretation.**

- **A standing wave.** The condition $kL=n\pi$ means $L=n\lambda/2$: an integer number of half wavelengths fits in the box. This is de Broglie's standing-wave idea (Section 1.7) with the correct boundary condition, and now it *derives* the quantization rather than assuming it.
- **Zero-point energy.** The lowest level is $E_1=h^2/8mL^2>0$. The particle cannot be at rest, because confining it forces a spread in momentum (Section 2.8).
- **Nodes.** $\psi_n$ has $n-1$ interior nodes, points where the probability of finding the particle is zero. Higher energy means more nodes.
- **Probability distribution.** $|\psi_n|^2=(2/L)\sin^2(n\pi x/L)$. For $n=1$ the particle is most likely at the centre. For large $n$ the rapid oscillations average out to the uniform density $1/L$ of a classical particle bouncing between walls.
- **Spacing.** $E_{n+1}-E_n=(2n+1)h^2/8mL^2$, so $\Delta E/E_n\approx2/n\to0$: at large $n$ the levels form an effective continuum.

**Why more nodes means more energy.** The kinetic energy is $\langle T\rangle=-\frac{\hbar^2}{2m}\int\psi\,\psi''\,dx$. Nodes force the function to curve more sharply, and curvature is kinetic energy. For one-dimensional bound states this gives a rigorous ordering (the $n$th state has $n-1$ nodes); in more dimensions it remains a useful guide rather than a law.

**Numbers.**

| System | $L$ | $E_1$ |
|---|---|---|
| Electron in a box | 1 nm | 0.376 eV |
| Electron in a box | 0.1 nm (atomic scale) | 37.6 eV |
| 1 g bead in a box | 1 cm | $\sim5\times10^{-61}$ J |

The electron values are the scale of chemistry (electron-volts). The bead's confinement energy is unmeasurably small, so its quantization is invisible.

**Chemical consequence.**

- **Confinement raises energy.** Squeezing an electron into a smaller region costs energy as $1/L^2$. This is the same competition as in the atomic-size estimate of Section 2.8.
- **Nanocrystals.** In semiconductor quantum dots, smaller crystals have larger level spacings and therefore absorb and emit bluer light. The box model gives the right qualitative trend.

> **Status of the principle: particle-in-a-box levels**
> *Derived* exactly for the idealized model. The model is *Approximate* for real systems: real walls are finite, so the wavefunction leaks into the wall region and energies are lower than $E_n$.

---

## 3.3 Two- and three-dimensional boxes

**Setup.** For a rectangular box, $0<x<a$, $0<y<b$, the Hamiltonian splits into independent pieces:

$$
\hat H=\hat H_x+\hat H_y=-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial x^2}-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial y^2}
$$

**Separation of variables.** Try $\psi(x,y)=X(x)Y(y)$. Dividing the equation by $XY$ separates it into a part depending only on $x$ and a part depending only on $y$, and each must equal a constant. The result:

$$
\psi_{n_xn_y}=\frac{2}{\sqrt{ab}}\sin\frac{n_x\pi x}{a}\sin\frac{n_y\pi y}{b},\qquad
E_{n_xn_y}=\frac{h^2}{8m}\left(\frac{n_x^2}{a^2}+\frac{n_y^2}{b^2}\right)
$$

In three dimensions there are three quantum numbers, one per dimension:

$$
E_{n_xn_yn_z}=\frac{h^2}{8m}\left(\frac{n_x^2}{a^2}+\frac{n_y^2}{b^2}+\frac{n_z^2}{c^2}\right)
$$

**Why the number of quantum numbers equals the number of dimensions.** Each independent direction has its own boundary conditions and hence its own integer. The energies add because $\hat H$ is a sum. This structure, a separable Hamiltonian giving additive energies and product wavefunctions, returns for the hydrogen atom in Chapter 6.

**Degeneracy.** In a square box ($a=b$), the states $(n_x,n_y)=(1,2)$ and $(2,1)$ have the same energy but different wavefunctions: they are **degenerate**. The degeneracy exists because the square is symmetric under exchange of $x$ and $y$. Make the box slightly rectangular ($a\neq b$) and the degeneracy is lifted.

In a cube the energy depends only on $n_x^2+n_y^2+n_z^2$:

| $n_x^2+n_y^2+n_z^2$ | States | Degeneracy |
|---|---|---|
| 3 | (1,1,1) | 1 |
| 6 | (2,1,1) and permutations | 3 |
| 9 | (2,2,1) and permutations | 3 |
| 12 | (2,2,2) | 1 |
| 14 | (3,2,1) and permutations | 6 |
| 27 | (5,1,1) and permutations, plus (3,3,3) | 4 |

Most degeneracies here come from exchanging axes. The fourfold degeneracy at 27 is different: it is *accidental*, a coincidence of integer sums that no geometric symmetry of the cube requires.

**Chemical consequence.**

- **Degeneracy tracks symmetry.** The same principle appears for the three $p$ orbitals of an atom (spherical symmetry) and the $d$ orbitals in molecules, where lowering the symmetry splits degenerate levels. Chapters 4 and 11 make this systematic.
- **Translational motion of molecules.** The energy levels of a molecule in a macroscopic box are these formulas with enormous $L$. They are so closely spaced that they form a near-continuum, and they become the translational partition function in Chapter 15.

> **Status of the principle: separability and degeneracy**
> *Derived.* Separation of variables works only for special forms of $\hat H$, so it is *Approximate* whenever used on real molecules. Degeneracy from symmetry is *Derived*; accidental degeneracy is a property of the specific potential.

---

## 3.4 Momentum and position

The box states let us test the machinery of Chapter 2 on something concrete.

**Position.** By symmetry $\langle x\rangle=L/2$ for every $n$. For the spread,

$$
\langle x^2\rangle=L^2\left(\frac13-\frac1{2n^2\pi^2}\right)\;\Rightarrow\;
\Delta x=L\sqrt{\frac1{12}-\frac1{2n^2\pi^2}}
$$

**Momentum.** The state $\psi_n$ is **not** an eigenfunction of $\hat p$, since $-i\hbar\,d/dx$ turns $\sin$ into $\cos$. Instead, writing

$$
\sin\frac{n\pi x}{L}=\frac{1}{2i}\left(e^{in\pi x/L}-e^{-in\pi x/L}\right),
$$

the state is an equal superposition of a right-moving wave ($p=+n\pi\hbar/L$) and a left-moving wave ($p=-n\pi\hbar/L$). A momentum measurement gives $+n\pi\hbar/L$ or $-n\pi\hbar/L$ with probability $\tfrac12$ each, so

$$
\langle p\rangle=0,\qquad \langle p^2\rangle=\left(\frac{n\pi\hbar}{L}\right)^2,\qquad
\Delta p=\frac{n\pi\hbar}{L}
$$

As a check, $\langle p^2\rangle/2m=n^2\pi^2\hbar^2/2mL^2=E_n$: all the energy is kinetic, as expected inside the box.

**Uncertainty product.**

$$
\Delta x\,\Delta p=\hbar\sqrt{\frac{n^2\pi^2}{12}-\frac12}
$$

For $n=1$ this is $0.568\,\hbar$, just above the minimum $0.5\,\hbar$ required by Section 2.8. For larger $n$ it grows, because $\Delta p$ increases while $\Delta x$ saturates at $L/\sqrt{12}$, the standard deviation of a uniform classical distribution.

**Interpretation.** The ground state is nearly a minimum-uncertainty state, which is why it is the lowest-energy state: it has the smallest momentum spread consistent with confinement. A standing wave is a superposition of travelling waves, and this picture (orbitals as standing waves of electrons) is the right one to carry forward.

> **Status of the principle: uncertainty in the box**
> *Derived.* It is an explicit check of the *Derived* uncertainty relation of Chapter 2.

---

## 3.5 Applications to $\pi$ electrons

**The problem.** Why do some molecules absorb visible light, and why does the absorption move to longer wavelength as the conjugated chain grows?

**The model (free-electron model).** In a linear conjugated polyene with $N$ carbon atoms, each carbon contributes one $\pi$ electron that is delocalized along the chain. Treat these electrons as non-interacting particles in a one-dimensional box of length $L\approx Nd$, with $d\approx1.40$ Å an average C–C bond length.

**Filling the levels.** Each level can hold two electrons of opposite spin. This is the Pauli principle, stated here as a rule and justified in Chapter 7. For even $N$, levels $n=1,\dots,N/2$ are filled. The highest occupied level is $n=N/2$ (the HOMO) and the lowest empty level is $n=N/2+1$ (the LUMO).

**Absorption.** The lowest-energy electronic transition promotes an electron from HOMO to LUMO:

$$
\Delta E=E_{N/2+1}-E_{N/2}=\frac{h^2}{8mL^2}\left[\left(\tfrac N2+1\right)^2-\left(\tfrac N2\right)^2\right]=\frac{h^2(N+1)}{8mL^2}
$$

The photon wavelength is $\lambda=hc/\Delta E$:

$$
\boxed{\lambda=\frac{8mcL^2}{h(N+1)}}
$$

**Results.**

| Molecule | $N$ | Model $\lambda$ | Experiment (approx.) |
|---|---|---|---|
| 1,3-Butadiene | 4 | 207 nm | 217 nm |
| 1,3,5-Hexatriene | 6 | 332 nm | 258 nm |
| 1,3,5,7-Octatetraene | 8 | 460 nm | 290 nm |
| $\beta$-Carotene | 22 | 1360 nm | 450 nm |

**What the model gets right.** The correct *trend*: the gap shrinks as the chain grows, so absorption moves to longer wavelength. That is why short polyenes are colorless (UV absorption) while long ones are colored. $\beta$-Carotene absorbs blue light near 450 nm and so appears orange. The model also gets butadiene nearly right.

**Where it fails, and why.** The quantitative agreement deteriorates quickly. Three approximations are responsible:

1. **The box length is ambiguous.** Nothing in the model fixes where the "walls" are.
2. **Electron repulsion is ignored.** Each electron is treated as moving independently, but electrons repel one another (Chapters 8 and 9).
3. **Bond alternation is ignored.** Real polyenes have alternating short and long C–C bonds, not a uniform potential. In the box model the gap falls as $1/N\to0$, predicting that very long chains would absorb in the infrared (metallic behavior). Real polyenes converge to a finite gap, as the experimental values show.

**The lesson.** The failure is not a new law, it is a missing piece of physics: a simplified potential and neglected repulsion. The next models restore them in stages, starting with Hückel theory in Chapter 12, which builds the $\pi$ system from atomic orbitals instead of a featureless box.

**Chemical consequence.** Color in organic molecules, from dyes to the retinal molecule of vision, is largely a question of the size of the conjugated $\pi$ system and hence of the HOMO–LUMO gap.

> **Status of the principle: free-electron model of polyenes**
> *Approximate.* The trend (longer chain, longer wavelength) is robust; the numbers are not. The Pauli filling rule used here is *Empirical* at this point in the book and becomes *Fundamental* in Chapter 7.

---

## What remains unexplained

| Open question | Where it is resolved |
|---|---|
| How does rotation quantize angular momentum, and what are the eigenfunctions? | Chapter 4 |
| What happens for a *restoring* potential, as in a bond vibrating? | Chapter 5 |
| What changes when the potential is the Coulomb attraction of a nucleus? | Chapter 6 |
| Where does the "two electrons per level" rule come from? | Chapter 7 |
| How are electron repulsion and many-electron effects included? | Chapters 8 and 9 |
| How does the $\pi$ system get built from atomic orbitals? | Chapter 12 |

**Next:** Chapter 4 turns to rotation. Angular momentum quantization and the spherical harmonics, prepared by the commutators of Section 2.6, will be the direct route to atomic orbitals.
