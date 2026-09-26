# Chapter 4 — Rotation, Angular Momentum and Symmetry

*Part I · The Quantum Structure of Matter*

Chapter 2 planted two seeds about rotation. The commutator $[\hat L_x,\hat L_y]=i\hbar\hat L_z$ was said to explain why a Stern–Gerlach measurement along one axis scrambles the result along another, and $[\hat L^2,\hat L_z]=0$ was said to explain why quantum numbers exist at all. Chapter 3 showed how boundary conditions turn a continuous spectrum into a discrete one. This chapter combines the two.

The opening questions:

> **Why is angular momentum quantized, and why do its allowed magnitudes have the odd form $\hbar\sqrt{l(l+1)}$ rather than simply $l\hbar$?**
> **And why does a molecule's rotational spectrum consist of evenly spaced lines?**

The chapter also introduces a principle that will recur through the whole book: **symmetry**. Rotational symmetry is the simplest example, and it already explains quantum numbers, degeneracy, orbital shapes and selection rules.

| Mathematical result | Chemical destination |
|---|---|
| Eigenvalues of $\hat L^2,\hat L_z$ | Quantum numbers $l,m$ of atomic orbitals |
| Spherical harmonics $Y_l^m$ | Angular shapes of $s,p,d,f$ orbitals |
| Rigid-rotor levels | Microwave spectra, bond lengths |
| $(2J+1)$ degeneracy | Populations of rotational levels; Zeeman splitting |
| Symmetry $\Rightarrow$ conserved quantities | Selection rules, orbital labels, point-group chemistry |
| Particle on a ring | A first glimpse of the $4n+2$ rule |

**Roadmap.** Classical rotation (4.1) → operators and commutation relations (4.2–4.3) → the first physical system, the rigid rotor (4.4) → its wavefunctions (4.5) → orientation and degeneracy (4.6–4.7) → spectroscopy (4.8) → symmetry as the organizing idea (4.9).

---

## 4.1 Classical rotation

**What classical physics assumed.** A particle of momentum $\mathbf p$ at position $\mathbf r$ has angular momentum

$$
\mathbf L=\mathbf r\times\mathbf p
$$

It is conserved whenever the force is central (directed along $\mathbf r$), and its magnitude and direction can take any value. For a mass $m$ on a circle of radius $r$, $L=I\omega$ with moment of inertia $I=mr^2$, and the rotational energy is

$$
E=\frac{L^2}{2I}
$$

**Two bodies as one.** A diatomic molecule with masses $m_1,m_2$ at separation $R$ rotates about its centre of mass. The relative motion behaves as that of a single particle of **reduced mass** $\mu=m_1m_2/(m_1+m_2)$ at distance $R$, so

$$
I=\mu R^2
$$

**Where it fails.** Classically, a rotating molecule could have any energy, and its rotational absorption would form a continuum. Observed microwave spectra consist of sharp, evenly spaced lines. And Section 1.9 showed that orientations of angular momentum are discrete. Something must quantize $L$.

---

## 4.2 Angular momentum operators

Following Section 2.3, replace $\mathbf r$ and $\mathbf p$ by operators, $\hat{\mathbf L}=\hat{\mathbf r}\times\hat{\mathbf p}$:

$$
\hat L_x=y\hat p_z-z\hat p_y,\qquad \hat L_y=z\hat p_x-x\hat p_z,\qquad \hat L_z=x\hat p_y-y\hat p_x
$$

and $\hat L^2=\hat L_x^2+\hat L_y^2+\hat L_z^2$. In spherical coordinates $(r,\theta,\phi)$ these take a form containing only angles:

$$
\hat L_z=-i\hbar\frac{\partial}{\partial\phi},\qquad
\hat L^2=-\hbar^2\left[\frac1{\sin\theta}\frac{\partial}{\partial\theta}\left(\sin\theta\frac{\partial}{\partial\theta}\right)+\frac1{\sin^2\theta}\frac{\partial^2}{\partial\phi^2}\right]
$$

The kinetic energy separates cleanly into radial and rotational parts:

$$
\hat T=-\frac{\hbar^2}{2m}\left[\frac1{r^2}\frac{\partial}{\partial r}\left(r^2\frac{\partial}{\partial r}\right)\right]+\frac{\hat L^2}{2mr^2}
$$

This decomposition is why the hydrogen atom will separate into a radial and an angular problem in Chapter 6.

**A first quantization: the particle on a ring.** Before the full problem, consider one angle only: a particle confined to a circle of radius $r$, with $\hat H=-\frac{\hbar^2}{2I}\frac{d^2}{d\phi^2}$. The solutions of $\hat H\psi=E\psi$ are

$$
\psi_m(\phi)=\frac{1}{\sqrt{2\pi}}e^{im\phi},\qquad E_m=\frac{m^2\hbar^2}{2I}
$$

and they are also eigenfunctions of $\hat L_z$ with eigenvalue $m\hbar$. What restricts $m$? Going once around the ring returns to the same point, so the wavefunction must be **single-valued**:

$$
\psi(\phi+2\pi)=\psi(\phi)\;\Rightarrow\;e^{2\pi im}=1\;\Rightarrow\;m=0,\pm1,\pm2,\dots
$$

**Angular momentum is quantized because the wavefunction must close on itself.** This is the same mechanism as the box in Chapter 3, with the periodic boundary condition playing the role of the walls. It is also de Broglie's standing-wave condition $2\pi r=n\lambda$ from Section 1.7, now derived. States $\pm m$ share the same energy: the ring's clockwise/anticlockwise symmetry.

**Chemical consequence (preview).** Treat the six $\pi$ electrons of benzene as free on a ring. The level $m=0$ holds two electrons, and each pair $\pm m$ holds four more. Closed shells occur at 2, 6, 10, 14, ... electrons, which is the sequence $4n+2$. The ring model gives a crude first hint of the Hückel rule; Chapter 12 derives it properly and shows where the ring picture breaks down.

> **Status of the principle: quantization from single-valuedness**
> *Derived* from the Schrödinger equation plus the requirement that $\psi$ be single-valued. The ring itself is an *Approximate* model for real molecules.

---

## 4.3 Commutation relations

**The key relations.** Using only $[x,\hat p_x]=i\hbar$ (Section 2.6), one can show that the components of angular momentum do not commute. For example:

$$
[\hat L_x,\hat L_y]=[y\hat p_z,z\hat p_x]+[z\hat p_y,x\hat p_z]
=y[\hat p_z,z]\hat p_x+\hat p_y\,x[z,\hat p_z]
=-i\hbar\,y\hat p_x+i\hbar\,x\hat p_y=i\hbar\hat L_z
$$

(all other pairs of terms commute). Together with its cyclic partners:

$$
[\hat L_x,\hat L_y]=i\hbar\hat L_z,\quad[\hat L_y,\hat L_z]=i\hbar\hat L_x,\quad[\hat L_z,\hat L_x]=i\hbar\hat L_y,\qquad
[\hat L^2,\hat L_x]=[\hat L^2,\hat L_y]=[\hat L^2,\hat L_z]=0
$$

**Consequence.** No two components can be sharp simultaneously, but $\hat L^2$ and one component (conventionally $\hat L_z$) can. The label "$z$" is only a choice of axis.

**The spectrum from the algebra alone.** Define ladder operators $\hat L_\pm=\hat L_x\pm i\hat L_y$. They satisfy $[\hat L_z,\hat L_\pm]=\pm\hbar\hat L_\pm$: acting on an $\hat L_z$ eigenstate with eigenvalue $\mu$, $\hat L_\pm$ produces one with eigenvalue $\mu\pm\hbar$. So the allowed $\hat L_z$ values form a ladder in steps of $\hbar$.

The ladder cannot go on forever, since $\hat L^2-\hat L_z^2=\hat L_x^2+\hat L_y^2\ge0$ bounds $\mu^2$ by the eigenvalue of $\hat L^2$. So there is a top rung, $\mu_{\max}=\hbar l$, where $\hat L_+$ gives zero. Using the identity $\hat L_-\hat L_+=\hat L^2-\hat L_z^2-\hbar\hat L_z$:

$$
0=\hat L_-\hat L_+\psi_{\rm top}=\left(\lambda-\hbar^2l^2-\hbar^2l\right)\psi_{\rm top}\;\Rightarrow\;\lambda=\hbar^2l(l+1)
$$

The same argument from the bottom rung (using $\hat L_+\hat L_-=\hat L^2-\hat L_z^2+\hbar\hat L_z$) gives the bottom at $-\hbar l$. So the ladder runs from $-l$ to $+l$ in integer steps, which forces $2l$ to be an integer:

$$
\hat L^2\to\hbar^2l(l+1),\qquad \hat L_z\to m\hbar,\qquad m=-l,-l+1,\dots,+l,\qquad l=0,\tfrac12,1,\tfrac32,\dots
$$

**Why $\sqrt{l(l+1)}$ and not $l$.** Since $\hat L_x^2+\hat L_y^2=\hat L^2-\hat L_z^2$, the state with $m=l$ has

$$
\langle L_x^2+L_y^2\rangle=\hbar^2\left[l(l+1)-l^2\right]=\hbar^2l>0
$$

Angular momentum can never align perfectly with the $z$ axis, because that would make $L_x=L_y=0$ and $L_z$ sharp simultaneously, violating the uncertainty principle of Section 2.8. The total length $\hbar\sqrt{l(l+1)}$ exceeds the maximum projection $l\hbar$ for exactly this reason.

**Integers and half-integers.** The algebra allows half-integer $l$. For *orbital* angular momentum, single-valuedness of the wavefunction (Section 4.2) forces integer $l$. The half-integer values are therefore reserved for something with no classical orbital motion: spin. This is the theoretical counterpart of the Stern–Gerlach two-beam experiment (Section 1.9), developed in Chapter 7.

> **Status of the principle: angular momentum spectrum**
> *Derived* from the commutators alone. The restriction to integer $l$ for orbital motion is *Derived* from single-valuedness. The existence of half-integer angular momentum is *Empirical* here (Stern–Gerlach) and is explained in Chapter 7.

---

## 4.4 Rigid rotor

**Setup.** A diatomic molecule with fixed bond length $R$ is a particle of reduced mass $\mu$ constrained to the surface of a sphere of radius $R$. With $r$ fixed and $V=0$, the radial kinetic energy is absent and the Hamiltonian is just the angular part:

$$
\hat H=\frac{\hat L^2}{2I},\qquad I=\mu R^2
$$

**Solution.** The Hamiltonian is a function of $\hat L^2$ alone, so its eigenstates are the $\hat L^2$ eigenstates of Section 4.3. Using $J$ for molecular rotation:

$$
\boxed{E_J=\frac{\hbar^2}{2I}J(J+1)=hc\,B\,J(J+1)},\qquad J=0,1,2,\dots,\qquad B=\frac{h}{8\pi^2cI}
$$

where $B$ is the **rotational constant** (in wavenumber units, cm$^{-1}$). The successive gaps are

$$
E_{J+1}-E_J=2hcB(J+1)
$$

**Physical interpretation.**

- **Only integers.** Since the motion is on a sphere, wavefunctions must be single-valued, so $J$ is an integer.
- **No zero-point energy.** $J=0$ has $E=0$: the molecule can be at rest rotationally. Unlike the box, angles are periodic rather than confined, so no uncertainty pressure forces motion.
- **Big molecules rotate more slowly.** $B\propto1/I$: heavier atoms and longer bonds give smaller $B$ and closer levels.

**Chemical consequence.** The rotational constant is a direct measure of the moment of inertia and hence of bond length (Section 4.8).

> **Status of the principle: rigid-rotor levels**
> *Derived* exactly for the model. The model is *Approximate* for real molecules, whose bonds stretch as they rotate (Section 4.8).

---

## 4.5 Spherical harmonics

**The eigenfunctions.** The joint eigenfunctions of $\hat L^2$ and $\hat L_z$ are the **spherical harmonics** $Y_l^m(\theta,\phi)$:

$$
\hat L^2Y_l^m=\hbar^2l(l+1)Y_l^m,\qquad \hat L_zY_l^m=m\hbar\,Y_l^m
$$

Writing $Y=\Theta(\theta)\,e^{im\phi}/\sqrt{2\pi}$, the $\phi$-part is the ring solution of Section 4.2, and the $\theta$-part obeys an equation whose solutions (associated Legendre functions) remain finite at $\theta=0$ and $\pi$ only if $l=0,1,2,\dots$ and $\lvert m\rvert\le l$. The requirement that $\psi$ be finite is another boundary condition, and it produces the same result the ladder-operator algebra did.

**The first few:**

| $l$ | $m$ | $Y_l^m$ |
|---|---|---|
| 0 | 0 | $\dfrac{1}{\sqrt{4\pi}}$ |
| 1 | 0 | $\sqrt{\dfrac{3}{4\pi}}\cos\theta$ |
| 1 | $\pm1$ | $\mp\sqrt{\dfrac{3}{8\pi}}\sin\theta\,e^{\pm i\phi}$ |
| 2 | 0 | $\sqrt{\dfrac{5}{16\pi}}\left(3\cos^2\theta-1\right)$ |
| 2 | $\pm1$ | $\mp\sqrt{\dfrac{15}{8\pi}}\sin\theta\cos\theta\,e^{\pm i\phi}$ |
| 2 | $\pm2$ | $\sqrt{\dfrac{15}{32\pi}}\sin^2\theta\,e^{\pm2i\phi}$ |

They are orthonormal: $\int Y_{l'}^{m'*}Y_l^m\,d\Omega=\delta_{ll'}\delta_{mm'}$.

**Interpretation.**

- **Angular nodes.** $Y_l^m$ has $l$ nodal surfaces: $\lvert m\rvert$ planes containing the $z$ axis and $l-\lvert m\rvert$ cones. More nodes, more angular curvature, more rotational energy (Section 3.2).
- **Parity.** Inverting all coordinates multiplies $Y_l^m$ by $(-1)^l$. This will control selection rules.
- **Real forms.** Because states with the same $l$ have the same energy, any combination of them is also an eigenfunction of $\hat L^2$. Combining $m=+1$ and $m=-1$ gives real functions proportional to $\sin\theta\cos\phi=x/r$ and $\sin\theta\sin\phi=y/r$, while $m=0$ gives $\cos\theta=z/r$. These are the familiar $p_x,p_y,p_z$. The real combinations are no longer eigenfunctions of $\hat L_z$; they are the ones with pointing directions, which is why chemists prefer them for describing bonds.

**Chemical consequence.** The angular part of every atomic orbital is a spherical harmonic (Chapter 6). The shapes of $s,p,d,f$ orbitals are not conventions: they are the angular solutions with $l=0,1,2,3$.

> **Status of the principle: spherical harmonics**
> *Derived* as the eigenfunctions of $\hat L^2$ and $\hat L_z$. The pointing-direction $p_x,p_y,p_z$ are *Derived* linear combinations, equally valid because of degeneracy.

---

## 4.6 Magnetic quantum numbers

**Space quantization.** For a given $l$ the projection $L_z=m\hbar$ takes $2l+1$ values. The angle between $\mathbf L$ and the $z$ axis is therefore quantized:

$$
\cos\theta=\frac{m}{\sqrt{l(l+1)}}
$$

For $l=1$ the allowed angles are $45^\circ,90^\circ,135^\circ$. The picture of $\mathbf L$ precessing on a cone is only a picture: $L_x$ and $L_y$ are never sharp.

**Why "magnetic".** A rotating charge makes a magnetic moment. For an electron, $\boldsymbol\mu=-(e/2m_e)\mathbf L$. In a field $B$ along $z$, the energy is $-\boldsymbol\mu\cdot\mathbf B$:

$$
\Delta E=m\,\mu_BB,\qquad \mu_B=\frac{e\hbar}{2m_e}
$$

This is precisely the normal Zeeman effect of Section 1.11. The "structured sublevels" that puzzled us there are the $2l+1$ values of $m$. The finite number of sublevels is explained too.

**Closing the loop on Stern–Gerlach.** For orbital angular momentum the number of beams is $2l+1$, always odd. The silver atom's ground state has $l=0$ and should give one beam, yet two are observed. The extra ingredient is spin (Chapter 7), and the theory now says exactly why orbital motion cannot account for it.

> **Status of the principle: space quantization and the Zeeman shift**
> *Derived* from the angular-momentum spectrum. The magnetic-moment relation for orbital motion is *Derived* from classical electromagnetism (correspondence).

---

## 4.7 Degeneracy

**Why the $2J+1$ states have the same energy.** The rigid-rotor energy depends on $J$ alone. Choosing a different $z$ axis relabels which combination of states has definite $m$ but cannot change the energy, because free rotation in empty space has no preferred direction. The $2J+1$ states of a level are therefore the *same* physical state seen from different orientations. This is degeneracy from symmetry (Section 3.3).

**Lifting degeneracy.** Any perturbation that singles out a direction breaks rotational symmetry and splits the levels: a magnetic field (Zeeman), an electric field (Stark), or, for an atom in a molecule, the neighboring atoms.

**Chemical consequence: populations.** In thermal equilibrium the population of level $J$ is proportional to $(2J+1)\,e^{-E_J/k_BT}$. The degeneracy factor grows with $J$ while the Boltzmann factor falls, so the population peaks at

$$
J_{\max}=\sqrt{\frac{k_BT}{2hcB}}-\frac12
$$

For CO ($B=1.93$ cm$^{-1}$) at 298 K, $k_BT/hc=207$ cm$^{-1}$ and $J_{\max}\approx7$. The lowest level $J=0$ is *not* the most populated. This same counting of states and weights is the foundation of statistical mechanics in Chapter 15.

> **Status of the principle: rotational degeneracy $2J+1$**
> *Derived* from rotational symmetry. It is *Approximate* for real molecules wherever external fields or hyperfine interactions are present.

---

## 4.8 Rotational spectroscopy

**Selection rule.** Absorption of a microwave photon changes $J$ by $\pm1$ and requires the molecule to have a **permanent dipole moment**. The rule is stated here and derived in Chapter 13, where the transition dipole integral between $Y_l^m$ functions vanishes unless $\Delta J=\pm1$ (a photon carries one unit of angular momentum, and the parity $(-1)^J$ must change). Consequently HCl and CO absorb, while H$_2$ and N$_2$ do not.

**The spectrum.** The absorption wavenumbers are

$$
\tilde\nu(J\to J+1)=2B(J+1),\qquad J=0,1,2,\dots
$$

a ladder of lines at $2B,4B,6B,\dots$ spaced by $2B$. This resolves the opening question: the lines are evenly spaced because $E_J\propto J(J+1)$.

**From spectrum to structure.** For CO the spacing is 3.86 cm$^{-1}$, so $B=1.93$ cm$^{-1}$. Then

$$
I=\frac{h}{8\pi^2cB}=1.45\times10^{-46}\ \text{kg m}^2,\qquad
\mu=\frac{12\times15.995}{27.995}\,\text{u}=1.14\times10^{-26}\ \text{kg},\qquad
R=\sqrt{\frac I\mu}=1.13\ \text{Å}
$$

which is the accepted CO bond length. Changing an isotope (for example $^{13}$C$^{16}$O) changes $\mu$ and shifts $B$, confirming the interpretation.

**Energy scales.** The energy required to excite each kind of motion differs enormously:

| Motion | Typical energy (CO) | Region |
|---|---|---|
| Rotation | $2B\approx4$ cm$^{-1}$ ($\sim0.5$ meV) | Microwave |
| Vibration | $\approx2140$ cm$^{-1}$ ($\sim0.27$ eV) | Infrared |
| Electronic | several eV | Ultraviolet |

The hierarchy electronic $\gg$ vibrational $\gg$ rotational reflects the large ratio of electron mass to nuclear mass. This is the physical origin of the Born–Oppenheimer approximation (Chapter 9).

**Where the rigid rotor fails.** Real bonds stretch as the molecule spins faster, so $I$ increases with $J$ and level spacings shrink at high $J$. The first correction is

$$
E_J=hc\left[BJ(J+1)-DJ^2(J+1)^2\right]
$$

with a small centrifugal distortion constant $D$. The failure is not new physics: it is the neglected vibration, treated in Chapter 5. Polyatomic molecules have up to three different moments of inertia, and their rotational structure (linear, symmetric top, asymmetric top) is more complex, but rests on the same angular-momentum algebra.

> **Status of the principle: rotational spectroscopy**
> *Derived* for the rigid rotor. The selection rule $\Delta J=\pm1$ is stated here and *Derived* in Chapter 13. The rigid-rotor description is *Approximate*, with centrifugal distortion as the first correction.

---

## 4.9 Symmetry as a recurring principle

This chapter's results share a single origin. The Hamiltonian of an isolated atom or free rotor does not change when the system is rotated: it is **rotationally symmetric**. Mathematically, symmetry means that the Hamiltonian commutes with the corresponding operator, $[\hat H,\hat L]=0$. From Section 2.6, commuting operators share eigenstates, so:

$$
\boxed{\text{symmetry of }\hat H\;\Longrightarrow\;\text{conserved quantity}\;\Longrightarrow\;\text{good quantum number}}
$$

| Symmetry of $\hat H$ | Conserved quantity | Consequence |
|---|---|---|
| Translation | Momentum $p$ | Plane waves (Section 3.1) |
| Rotation about $z$ | $L_z$ | Quantum number $m$ |
| Full rotational symmetry | $\hat L^2$ and $\hat{\mathbf L}$ | Quantum number $l$, degeneracy $2l+1$ |
| Inversion of coordinates | Parity | Parity $(-1)^l$, dipole selection rules |
| Exchange of identical particles | Permutation symmetry | Pauli principle (Chapter 7) |

Symmetry therefore constrains the whole of quantum chemistry:

- **Energy and degeneracy:** symmetric systems have degenerate levels; lowering symmetry splits them.
- **Wavefunctions:** the $2l+1$ functions with the same $l$ transform among themselves under rotation.
- **Transitions:** parity and angular momentum decide which spectral lines can appear.
- **Molecular structure:** the point-group symmetry of a molecule replaces the full rotation group and organizes molecular orbitals and vibrations (Chapter 11).

**A caution: not all degeneracies come from obvious symmetry.** In the hydrogen atom, the $2s$ and $2p$ levels have exactly the same energy, although rotational symmetry alone would only make the three $2p$ orbitals degenerate with each other. That extra degeneracy comes from a hidden symmetry of the $1/r$ potential and disappears in every many-electron atom, where $2s$ lies below $2p$ (Chapter 8). Seeing symmetry requires knowing the *whole* Hamiltonian, and approximations that change the Hamiltonian change the symmetry.

> **Status of the principle: symmetry $\Rightarrow$ conservation and degeneracy**
> *Derived* for exact symmetries of $\hat H$. Symmetry used for real molecules is often *Approximate*, because the true environment is slightly less symmetric than the model.

---

## What remains unexplained

| Open question | Where it is resolved |
|---|---|
| How does a bond vibrate, and what corrects the rigid rotor? | Chapter 5 |
| What is the radial part that completes the hydrogen orbitals, and why are $2s$ and $2p$ degenerate in hydrogen? | Chapter 6 |
| Where does half-integer angular momentum (spin) come from? | Chapter 7 |
| Why does $2s$ lie below $2p$ in many-electron atoms? | Chapter 8 |
| How is $\Delta J=\pm1$ derived, and how do intensities arise? | Chapter 13 |
| How does molecular (point-group) symmetry replace full rotational symmetry? | Chapter 11 |
| How are rotational populations turned into thermodynamic properties? | Chapter 15 |

**Next:** Chapter 5 turns from rotation to vibration. A molecule's bond acts as a spring, and the quantum harmonic oscillator will give the vibrational levels, the infrared spectrum, and the correction to the rigid rotor.
