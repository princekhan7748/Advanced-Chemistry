# Chapter 6 — The Hydrogen Atom

*Part I · The Quantum Structure of Matter*

Everything so far has been preparation. Chapter 2 built the rules, Chapter 3 showed quantization arising from boundary conditions, Chapter 4 solved the angular part of any central-force problem, and Chapter 5 supplied the virial theorem and the habit of solving problems by algebra. Now these tools meet a real atom.

The chapter answers three questions left open earlier:

> **Can the Schrödinger equation reproduce hydrogen's spectrum without orbits, and what does it say about where the electron is?**
> **Why are the $2s$ and $2p$ levels of hydrogen exactly degenerate?** (Section 4.9)
> **What does a $1s$ or $2p$ orbital physically represent?**

Hydrogen is the last system in this book that can be solved exactly with a Coulomb potential. It matters far beyond its own chemistry: the orbitals found here, their shapes, sizes and nodes, are the vocabulary in which every larger atom and molecule is later described.

| Mathematical result | Chemical destination |
|---|---|
| Quantum numbers $n,l,m$ | Orbital labels, electron configurations |
| Radial functions $R_{nl}(r)$ | Orbital size, penetration and shielding |
| Nodes: $n-l-1$ radial, $l$ angular | Orbital energy ordering, bonding and antibonding character |
| $E_n=-13.6\,Z^2/n^2$ eV | Ionization energies, atomic spectra |
| $\langle r\rangle,\langle1/r\rangle$ | Atomic size trends |
| Orbital magnetic moment, Zeeman effect | Magnetic resonance, magnetic properties |
| Stark effect, state mixing | Polarizability, intermolecular forces, the meaning of hybridization |
| Spin (introduced) | Two electrons per orbital, periodic-table shell capacity |

**Roadmap.** The Coulomb problem (6.1–6.3) → its quantum numbers and solutions (6.4–6.7) → energies and expectation values (6.8–6.9) → spectrum and its comparison with Chapter 1 (6.10) → the atom in magnetic and electric fields (6.11–6.13) → what the theory still cannot explain (6.14).

---

## 6.1 Coulomb potential

**The problem.** A hydrogen-like atom has a nucleus of charge $+Ze$ and one electron. The potential energy is

$$
V(r)=-\frac{Ze^2}{4\pi\varepsilon_0r}
$$

**Two bodies become one.** As for the rotor (Section 4.1), the relative motion of nucleus and electron is that of a single particle of reduced mass $\mu=m_em_N/(m_e+m_N)$. For hydrogen $\mu=m_e(1-1/1836)$: a small correction, but a measurable one. Replacing $m_e$ by $\mu$ changes the Rydberg constant from $R_\infty=109\,737$ cm$^{-1}$ to $R_H=109\,678$ cm$^{-1}$, and for deuterium to $R_D=109\,707$ cm$^{-1}$. This tiny shift in spectral lines (about 0.18 nm for the red Balmer line) is how Urey discovered deuterium in 1931.

**Why it is solvable.** The potential depends only on $r$: it is a **central potential**, rotationally symmetric. By Section 4.9, $\hat H$ commutes with $\hat L^2$ and $\hat L_z$, so they share eigenstates with $\hat H$ and the angular problem has already been solved.

**What went wrong classically.** A classical electron in this potential radiates and spirals in (Section 1.5). The quantum treatment must produce stable stationary states, which it does: stationary states do not radiate (Section 2.9).

> **Status of the principle: the model**
> *Approximate.* It treats the nucleus as a point charge and ignores relativity, spin and quantum-electrodynamic effects. The point-charge Coulomb potential itself is *Fundamental* to atomic physics.

---

## 6.2 Schrödinger equation in spherical coordinates

The Hamiltonian is

$$
\hat H=-\frac{\hbar^2}{2\mu}\nabla^2-\frac{Ze^2}{4\pi\varepsilon_0r}
$$

In spherical coordinates, the Laplacian separates into a radial part and the angular operator of Section 4.2:

$$
\nabla^2=\frac1{r^2}\frac{\partial}{\partial r}\left(r^2\frac{\partial}{\partial r}\right)-\frac{\hat L^2}{\hbar^2r^2}
$$

so that

$$
\hat H=-\frac{\hbar^2}{2\mu}\frac1{r^2}\frac{\partial}{\partial r}\left(r^2\frac{\partial}{\partial r}\right)+\frac{\hat L^2}{2\mu r^2}-\frac{Ze^2}{4\pi\varepsilon_0r}
$$

The term $\hat L^2/2\mu r^2$ is the rotational kinetic energy, the same $\hat L^2/2I$ as the rigid rotor with $I=\mu r^2$.

---

## 6.3 Separation of variables

**Ansatz.** Because $\hat L^2$ acts only on angles, try

$$
\psi(r,\theta,\phi)=R(r)\,Y_l^m(\theta,\phi)
$$

Then $\hat L^2Y_l^m=\hbar^2l(l+1)Y_l^m$ turns the problem into a one-dimensional equation for $R$. With $u(r)=rR(r)$:

$$
-\frac{\hbar^2}{2\mu}\frac{d^2u}{dr^2}+\left[\frac{\hbar^2l(l+1)}{2\mu r^2}-\frac{Ze^2}{4\pi\varepsilon_0r}\right]u=Eu
$$

This is a one-dimensional problem with an **effective potential** $V_{\rm eff}=V+\hbar^2l(l+1)/2\mu r^2$. The added term is a centrifugal barrier: for $l>0$ it repels the electron from the nucleus, while for $l=0$ there is no barrier. This is the origin of a fact that will matter greatly in Chapter 8: $s$ electrons reach the nucleus, $p$ and $d$ electrons are kept away from it.

**Boundary conditions.** As in Chapters 3 and 5: $u(0)=0$ (so that $R$ is finite at the origin) and $u\to0$ as $r\to\infty$ for a bound state, with $\int_0^\infty\lvert u\rvert^2dr=1$.

**Solving it: where the quantization comes from.** For a bound state, $E<0$. Write $E=-\hbar^2\kappa^2/2\mu$. Far from the nucleus the equation becomes $u''\approx\kappa^2u$, so $u\sim e^{-\kappa r}$. Near the nucleus the centrifugal term dominates and $u\sim r^{l+1}$. So write

$$
u=r^{l+1}e^{-\kappa r}f(r),\qquad f=\sum_jc_jr^j
$$

Substituting and collecting powers of $r$ gives a recursion (with $\alpha=2\mu Ze^2/4\pi\varepsilon_0\hbar^2=2Z/a$, where $a=4\pi\varepsilon_0\hbar^2/\mu e^2\approx a_0$):

$$
c_{j+1}=\frac{2\kappa(j+l+1)-\alpha}{(j+1)(j+2l+2)}\,c_j
$$

For large $j$, $c_{j+1}/c_j\to2\kappa/j$, which sums to $f\sim e^{2\kappa r}$, and then $u\sim e^{+\kappa r}$ diverges. The wavefunction is normalizable only if the series **terminates** at some finite $j=n_r$, which requires the numerator to vanish:

$$
2\kappa\,(n_r+l+1)=\alpha\;\Longrightarrow\;\kappa=\frac{Z}{n\,a},\qquad n\equiv n_r+l+1
$$

with $n_r=0,1,2,\dots$ a non-negative integer. The energy follows from $E=-\hbar^2\kappa^2/2\mu$ (Section 6.8). **Quantization arises because only for special energies does the solution avoid blowing up at large $r$**, the same mechanism as in every previous chapter, with the polynomial $f$ (a Laguerre polynomial) playing the role of the Hermite polynomials of Section 5.7.

> **Status of the principle: separation of variables for the Coulomb problem**
> *Derived* and exact for this Hamiltonian. It works because the potential is central.

---

## 6.4 Hydrogen quantum numbers

Three integers label a state:

| Quantum number | Allowed values | Meaning | Origin |
|---|---|---|---|
| $n$ (principal) | $1,2,3,\dots$ | Energy and overall size | Termination of the radial series |
| $l$ (orbital) | $0,1,\dots,n-1$ | Angular momentum $\hbar\sqrt{l(l+1)}$ | $\hat L^2$ eigenvalue |
| $m$ (magnetic) | $-l,\dots,+l$ | $L_z=m\hbar$ | $\hat L_z$ eigenvalue |

**Why $l\le n-1$.** From $n=n_r+l+1$ and $n_r\ge0$: $l\le n-1$. This constraint is a result, not a rule.

**Why these three.** They are the eigenvalues of the commuting set $\hat H$, $\hat L^2$, $\hat L_z$ (Section 2.6). Every hydrogen state is uniquely labelled by $(n,l,m)$.

**Counting.** For each $n$ there are $\sum_{l=0}^{n-1}(2l+1)=n^2$ states. Spectroscopic letters name the values of $l$:

| $l$ | 0 | 1 | 2 | 3 |
|---|---|---|---|---|
| Letter | $s$ | $p$ | $d$ | $f$ |

so shell $n=1$ has $1s$; $n=2$ has $2s,2p$; $n=3$ has $3s,3p,3d$. Including the electron's spin (Section 6.14) doubles these to $2n^2$.

> **Status of the principle: quantum numbers**
> *Derived.* The list $n,l,m$ follows from the boundary conditions and commuting operators.

---

## 6.5 Orbital wavefunctions

The stationary states are $\psi_{nlm}=R_{nl}(r)\,Y_l^m(\theta,\phi)$. With $\rho=Zr/a_0$, the lowest radial functions are:

| Orbital | $R_{nl}(r)$ |
|---|---|
| $1s$ | $2\left(\dfrac Z{a_0}\right)^{3/2}e^{-\rho}$ |
| $2s$ | $\dfrac1{2\sqrt2}\left(\dfrac Z{a_0}\right)^{3/2}(2-\rho)\,e^{-\rho/2}$ |
| $2p$ | $\dfrac1{2\sqrt6}\left(\dfrac Z{a_0}\right)^{3/2}\rho\,e^{-\rho/2}$ |
| $3s$ | $\dfrac2{81\sqrt3}\left(\dfrac Z{a_0}\right)^{3/2}\left(27-18\rho+2\rho^2\right)e^{-\rho/3}$ |
| $3p$ | $\dfrac8{27\sqrt6}\left(\dfrac Z{a_0}\right)^{3/2}\rho\left(1-\dfrac\rho6\right)e^{-\rho/3}$ |
| $3d$ | $\dfrac4{81\sqrt{30}}\left(\dfrac Z{a_0}\right)^{3/2}\rho^2\,e^{-\rho/3}$ |

Combined with $Y_0^0=1/\sqrt{4\pi}$, the ground state is

$$
\psi_{1s}=\frac1{\sqrt\pi}\left(\frac Z{a_0}\right)^{3/2}e^{-Zr/a_0}
$$

**Structure of the solutions.**

- **Near the nucleus:** $R_{nl}\propto r^l$. Only $s$ orbitals are non-zero at $r=0$, with
$$\lvert\psi_{ns}(0)\rvert^2=\frac{Z^3}{\pi a_0^3n^3}$$
This is the origin of the contact (hyperfine) interaction between an electron and the nucleus in magnetic resonance (Chapter 13).
- **Far away:** every function decays as $e^{-Zr/na_0}$, so higher $n$ means a more diffuse orbital.
- **Angular part:** the shapes are the spherical harmonics of Section 4.5 (or their real combinations, $p_x,p_y,p_z$, and so on).

**What an orbital is.** $\psi_{nlm}$ is a probability amplitude, not a path. $\lvert\psi\rvert^2$ gives the density of finding the electron at each point. The picture of an electron circling the nucleus (Bohr) is not what the theory says.

> **Status of the principle: hydrogenic orbitals**
> *Derived.* Exact solutions of the non-relativistic, spinless model.

---

## 6.6 Radial probability distributions

**Density versus shell probability.** The volume element is $r^2\sin\theta\,dr\,d\theta\,d\phi$. Integrating over angles, the probability of finding the electron between $r$ and $r+dr$ is

$$
P(r)\,dr=r^2R_{nl}^2\,dr
$$

**The $1s$ orbital.** $P(r)\propto r^2e^{-2Zr/a_0}$, which has its maximum at

$$
r=\frac{a_0}{Z}
$$

The Bohr radius reappears, but with a different meaning: it is the *most probable distance* from the nucleus, not the radius of an orbit. The density $\lvert\psi\rvert^2$ itself is largest *at* the nucleus, but the volume of a thin shell grows as $r^2$, so the radial probability peaks elsewhere. Both statements are true, and confusing them is a common error.

**Higher orbitals (for $Z=1$).**

| Orbital | Maxima of $P(r)$ | Interpretation |
|---|---|---|
| $1s$ | $r=1\,a_0$ | Compact |
| $2s$ | $0.76\,a_0$ and $5.24\,a_0$ | Small inner peak, main peak outside |
| $2p$ | $4\,a_0$ | One peak, no inner structure |

The $2s$ orbital has a small inner maximum close to the nucleus; $2p$ does not. **The $2s$ electron *penetrates* toward the nucleus more than a $2p$ electron**, a consequence of the centrifugal barrier of Section 6.3. In hydrogen this makes no difference to the energy (Section 6.8), but in atoms with several electrons it is the key to why $2s$ lies below $2p$ (Chapter 8).

> **Status of the principle: radial distributions**
> *Derived.* Penetration is a property of the wavefunctions themselves.

---

## 6.7 Nodes

A node is a place where the wavefunction is zero. Two kinds appear:

- **Radial nodes:** spherical surfaces where $R_{nl}=0$. Their number is $n-l-1$ (equal to $n_r$ of Section 6.3).
- **Angular nodes:** planes or cones where $Y_l^m=0$ (Section 4.5). Their number is $l$.

The total number of nodes is therefore $n-1$ for every orbital:

| Orbital | Radial nodes | Angular nodes | Location of radial nodes |
|---|---|---|---|
| $1s$ | 0 | 0 | none |
| $2s$ | 1 | 0 | $r=2a_0/Z$ |
| $2p$ | 0 | 1 | none |
| $3s$ | 2 | 0 | $1.90\,a_0$ and $7.10\,a_0$ |
| $3p$ | 1 | 1 | $6\,a_0$ |
| $3d$ | 0 | 2 | none |

**Why nodes matter.** They are the three-dimensional version of the rule from Section 3.2: more nodes mean more curvature and higher kinetic energy. In hydrogen the total node count $n-1$ fixes the energy, and **it will be the primary tool for judging orbital shapes** in molecular orbitals (Chapter 10): a bonding orbital has no node between the nuclei, an antibonding orbital has one.

> **Status of the principle: node counting**
> *Derived* exactly for hydrogenic orbitals. As a general guide to orbital energies in other systems it is *Approximate*.

---

## 6.8 Hydrogen energy levels

From $\kappa=Z/(na)$ and $E=-\hbar^2\kappa^2/2\mu$:

$$
\boxed{E_n=-\frac{\mu e^4}{2(4\pi\varepsilon_0)^2\hbar^2}\,\frac{Z^2}{n^2}=-13.6\,\frac{Z^2}{n^2}\ \text{eV}}
$$

This is exactly the Bohr energy of Section 1.6, now obtained without any orbits.

| $n$ | $E_n$ (H, eV) |
|---|---|
| 1 | $-13.60$ |
| 2 | $-3.40$ |
| 3 | $-1.51$ |
| $\infty$ | $0$ (ionization limit) |

For $E>0$ the electron is free and the levels form a continuum (as in Section 3.1, now with Coulomb-distorted waves).

**What the Schrödinger theory fixes that Bohr's could not.**

| Property | Bohr model | Schrödinger equation |
|---|---|---|
| Ground-state angular momentum | $\hbar$ (wrong) | 0 for $1s$ (correct) |
| Electron position | Planar circular orbit | Three-dimensional probability density |
| Origin of quantization | Postulated ($L=n\hbar$) | Derived (boundary conditions) |
| Number of states in shell $n$ | Not addressed | $n^2$ |

**The degeneracy.** The energy depends only on $n$, not on $l$: all $n^2$ states of a shell share the same energy. Rotational symmetry alone would only make the $2l+1$ values of $m$ degenerate. The extra degeneracy is a special property of the $1/r$ potential, associated with a hidden symmetry (related to a conserved vector in the classical Kepler problem, the Runge–Lenz vector). This answers the question from Section 4.9: $2s$ and $2p$ are degenerate in hydrogen because the potential is *exactly* $1/r$. Any change, such as the screening by other electrons, lifts it (Chapter 8), as do relativistic and QED corrections (Chapter 7).

> **Status of the principle: hydrogen energy levels**
> *Derived.* The levels are *Approximate* at the level of $10^{-4}$ eV, because relativity, spin and QED are omitted. The $l$-degeneracy is *Derived* but fragile.

---

## 6.9 Expectation values

Radial integrals over $\psi_{nlm}$ give closed forms:

$$
\langle r\rangle=\frac{a_0}{2Z}\left[3n^2-l(l+1)\right],\qquad
\left\langle\frac1r\right\rangle=\frac{Z}{n^2a_0},\qquad
\langle r^2\rangle=\frac{a_0^2n^2}{2Z^2}\left[5n^2+1-3l(l+1)\right]
$$

**Checks and consequences.**

- **Virial theorem.** Since $\langle V\rangle=-\dfrac{Ze^2}{4\pi\varepsilon_0}\langle\tfrac1r\rangle=-\dfrac{Z^2}{n^2}\dfrac{e^2}{4\pi\varepsilon_0a_0}=2E_n$, we get $\langle T\rangle=-E_n$ and $E=\langle V\rangle/2$. This is exactly the Coulomb virial relation $2\langle T\rangle=-\langle V\rangle$ of Section 5.9. It also shows that pulling an electron closer to the nucleus (more negative $E$) *increases* its kinetic energy.
- **Size.** $\langle r\rangle\propto n^2/Z$: orbitals grow with $n$ and shrink with nuclear charge. This is the seed of periodic trends in atomic size (Chapter 8).
- **Size versus penetration.** For $n=2$, $\langle r\rangle_{2s}=6a_0$ and $\langle r\rangle_{2p}=5a_0$. The $2s$ orbital is on average *farther* out, yet it penetrates closer to the nucleus. Average size and penetration are different properties; the $2s$ orbital's inner peak is what matters for its energy in many-electron atoms.

> **Status of the principle: expectation values**
> *Derived.* The virial relation is a *Derived* check.

---

## 6.10 Hydrogen spectrum

**The Rydberg formula, derived.** A transition between stationary states emits a photon of energy equal to the level difference (Section 2.9):

$$
h\nu=E_{n_2}-E_{n_1}\;\Longrightarrow\;\frac1\lambda=R_H\left(\frac1{n_1^2}-\frac1{n_2^2}\right),\qquad R_H=\frac{\mu e^4}{8\varepsilon_0^2h^3c}
$$

This is the formula that Balmer and Rydberg found empirically (Section 1.4). The series limits are now understood too: the Lyman limit at 91.2 nm is the energy needed to ionize hydrogen from the ground state.

**Selection rule.** One-photon transitions require $\Delta l=\pm1$ (derived in Chapter 13), while $n$ may change by any amount. Two examples show that the rule has consequences:

| Transition | Allowed? | Lifetime |
|---|---|---|
| $2p\to1s$ (Lyman-$\alpha$) | Yes ($\Delta l=-1$) | About 1.6 ns |
| $2s\to1s$ | No ($\Delta l=0$) | About 0.12 s (decays by two-photon emission) |

The $2s$ state of hydrogen is *metastable*: it lives roughly $10^8$ times longer than $2p$ because a selection rule forbids the direct route.

**What is still not explained.** Under high resolution the Balmer lines are split into closely spaced components (fine structure, about $0.36$ cm$^{-1}$ for $n=2$). The Schrödinger equation of this chapter predicts none of this splitting.

> **Status of the principle: hydrogen spectrum**
> The Rydberg formula was *Empirical* in Chapter 1 and is now *Derived*. The selection rule $\Delta l=\pm1$ is stated here and *Derived* in Chapter 13. The absence of fine structure marks the boundary of this model.

---

## 6.11 Magnetic moments

**Orbital magnetic moment.** A charge moving in an orbit constitutes a current loop, and a current loop is a magnetic dipole. Classically $\boldsymbol\mu=-\dfrac{e}{2m_e}\mathbf L$. Quantum mechanically, using the eigenvalues of Section 4.3:

$$
\mu_z=-\frac{e\hbar}{2m_e}\,m=-\mu_B\,m,\qquad \mu_B=\frac{e\hbar}{2m_e}=9.274\times10^{-24}\ \text{J/T}
$$

where $\mu_B$ is the **Bohr magneton**. The ratio of moment to angular momentum is the *gyromagnetic ratio*, $-e/2m_e$ for orbital motion.

**Consequences.**

- An $s$ state ($l=0$) has no orbital magnetic moment.
- A $p$ state has three possible projections $\mu_z=-\mu_B,0,+\mu_B$.
- In a magnetic field $B$ along $z$, the interaction energy is $-\boldsymbol\mu\cdot\mathbf B=\mu_B\,mB$, the shift of Section 4.6.

> **Status of the principle: orbital magnetic moment**
> *Derived* from classical electromagnetism together with the angular-momentum eigenvalues.

---

## 6.12 Zeeman effect

**Setup.** A weak magnetic field along $z$ adds a term $\hat H'=(\mu_B/\hbar)B\hat L_z$ to the Hamiltonian. Since the hydrogen states $\psi_{nlm}$ are already eigenstates of $\hat L_z$, the shift is exact for this term:

$$
E_{nlm}=E_n+\mu_B\,B\,m
$$

**Predictions.**

- A level with angular momentum $l$ splits into $2l+1$ equally spaced sublevels: $2s$ does not split, $2p$ splits into three.
- Spectral lines split into a triplet (transitions with $\Delta m=0,\pm1$) with shifts $0,\pm\mu_BB/h$, i.e. $\pm14.0$ GHz per tesla. This is the normal Zeeman effect observed in Chapter 1 (Section 1.11), now derived.
- The scale is tiny: at $B=1$ T the shift is $5.8\times10^{-5}$ eV, compared with the 13.6 eV binding energy.

**The limit of the theory.** Real hydrogen lines show more complicated patterns than a simple triplet (the "anomalous" Zeeman effect). The extra structure is explained only by spin (Section 6.14, Chapter 7).

> **Status of the principle: normal Zeeman effect**
> *Derived* (first-order perturbation theory, formalized in Chapter 9). *Approximate* for real atoms, which show spin effects.

---

## 6.13 Stark effect

**Setup.** An electric field $F$ along $z$ adds $\hat H'=eFz$. Unlike the magnetic case, $z$ does not commute with $\hat L^2$, so the field *mixes* states.

**Ground state.** $\psi_{1s}$ has definite parity (even), so $\langle z\rangle=0$ and the first-order shift vanishes (the argument of Section 5.8). The effect appears at second order:

$$
\Delta E=-\tfrac12\alpha F^2,\qquad \alpha=\tfrac92\,(4\pi\varepsilon_0)\,a_0^3
$$

where $\alpha$ is the **polarizability**: the field pulls the electron cloud one way and the nucleus the other, inducing a dipole.

**The $n=2$ level.** Here $2s$ and $2p_0$ ($m=0$) are degenerate (Section 6.8) and opposite in parity, so the field mixes them. The mixed states $\tfrac1{\sqrt2}(2s\pm2p_0)$ have permanent dipole moments and shift **linearly** with the field:

$$
\Delta E=\pm3\,e\,a_0F
$$

This *linear* Stark effect is special to hydrogen, because of the $l$-degeneracy of Section 6.8. In most atoms and molecules, where the degeneracy is lifted, the effect is quadratic.

**Chemical consequences.**

- **Polarizability** governs how electron clouds respond to neighboring charges, and it underlies dispersion forces and solvent effects (Chapter 20).
- **Hybridization, previewed.** The state $\tfrac1{\sqrt2}(2s+2p_0)$ is a lopsided "sp hybrid". It is nothing more than a superposition of degenerate states, chosen so that it points in one direction. Hybridization in molecules (Chapter 10) is the same mathematical operation, with neighboring atoms rather than an electric field producing the mixing. It is a representation, not a separate physical process.

> **Status of the principle: Stark effect**
> *Derived* by perturbation theory. Mixing of degenerate states is *Derived*; the physical picture of "hybrid orbitals" is a *Derived* mathematical reorganization of the same states.

---

## 6.14 Introduction to spin

**Where the theory of this chapter stops.** Three experimental facts about hydrogen cannot be obtained from $\psi_{nlm}$:

1. **Stern–Gerlach with hydrogen atoms.** A beam of ground-state hydrogen ($l=0$) splits into two, not one (Sections 1.9 and 4.6). Orbital motion cannot do this.
2. **Fine structure.** The $n=2$ level splits by about $0.36$ cm$^{-1}$, and lines show multiplets (Section 6.10).
3. **The anomalous Zeeman effect** (Section 6.12).

**The proposal.** Uhlenbeck and Goudsmit (1925) supplied one extra property of the electron: an intrinsic angular momentum, **spin**, with quantum number $s=\tfrac12$ and projections $m_s=\pm\tfrac12$. It obeys the same commutation algebra as orbital angular momentum, $[\hat S_x,\hat S_y]=i\hbar\hat S_z$, and so uses the *half-integer* solution that Section 4.3 showed the algebra allows but that single-valuedness forbids for orbital motion. Its magnetic moment is

$$
\mu_z=-g_s\,\mu_B\,m_s,\qquad g_s\approx2.0023
$$

almost exactly twice the orbital ratio, which no classical spinning charge reproduces.

**The complete state.** A hydrogen electron is specified by four quantum numbers, $(n,l,m,m_s)$, and each orbital $\psi_{nlm}$ accommodates two spin states. The shell $n$ therefore holds $2n^2$ spin-orbitals: 2, 8, 18, 32, ... This is the *hydrogenic* counting only. Real periods of the periodic table (2, 8, 8, 18, 18, 32) differ, because in many-electron atoms the orbital energies no longer depend on $n$ alone (Chapter 8).

**A caution.** The word "spin" is historical: the electron is not a small ball rotating about its axis. Spin is an intrinsic quantum property with no classical counterpart.

**The open question.** Spin has been *added* here, as an experimental fact. Why does the electron have it, where does $g_s\approx2$ come from, and why does it lead to the exclusion principle? The answer requires a relativistic equation, taken up in Chapter 7.

> **Status of the principle: electron spin**
> *Empirical* in this chapter: it is inserted to match experiment. It becomes *Derived* from the Dirac equation in Chapter 7. The two-per-orbital rule is *Empirical* here and becomes *Fundamental* (via the spin–statistics connection) in Chapter 7.

---

## What remains unexplained

| Open question | Where it is resolved |
|---|---|
| Where does spin come from, and why $g_s\approx2$? | Chapter 7 |
| What produces fine structure, and how large are relativistic effects in heavy atoms? | Chapter 7 |
| Why two electrons per orbital, and what is antisymmetry? | Chapter 7 |
| What changes when an atom has more than one electron, so that $2s$ and $2p$ separate? | Chapter 8 |
| What can be done when exact solutions do not exist? | Chapter 9 |
| How is the selection rule $\Delta l=\pm1$ derived? | Chapter 13 |
| How do hydrogen-like orbitals combine into bonds? | Chapter 10 |
| How does polarizability produce intermolecular forces? | Chapter 20 |

**Next:** Chapter 7 tackles what the Schrödinger equation of this chapter could not: the electron's spin, relativistic corrections and the requirement that identical electrons obey the Pauli principle, which together explain why matter does not collapse.
