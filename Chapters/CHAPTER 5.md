# Chapter 5 — The Quantum Harmonic Oscillator

*Part I · The Quantum Structure of Matter*

Chapter 4 ended with a failure. The rigid rotor treats a bond as a fixed-length rod, but real molecules stretch as they spin, and their rotational lines drift from the predicted pattern. The missing ingredient is the vibration of the bond. This chapter supplies it, using the second great exactly solvable model of chemistry.

The opening questions:

> **How does a chemical bond vibrate, and why do its vibrational energies come in equal steps with a non-zero minimum?**
> **Why do stronger bonds absorb infrared light at higher frequency?**

This chapter also closes a loop left open in Chapter 1. Planck's $E_n=nh\nu$ was introduced there as an empirical fit. Here it is derived.

| Mathematical result | Chemical destination |
|---|---|
| Ladder operators, $E_n=\hbar\omega(n+\tfrac12)$ | Vibrational energy levels of bonds |
| Zero-point energy $\tfrac12\hbar\omega$ | Bond dissociation energies, isotope effects |
| Hermite-polynomial wavefunctions | Probability of bond stretching, tunneling into forbidden regions |
| Parity, $\Delta n=\pm1$ | Infrared selection rule |
| Virial theorem | Energy bookkeeping of bond formation |
| Normal modes | Infrared and Raman spectra of polyatomic molecules |
| Anharmonicity | Overtones, dissociation, corrections to frequencies |

**Roadmap.** The classical oscillator and why it matters (5.1) → quantum version and its solution by algebra (5.2–5.5) → wavefunctions (5.6–5.7) → symmetry and energy theorems (5.8–5.9) → spectroscopy (5.10) → real molecules and where the model fails (5.11).

---

## 5.1 Classical oscillator

**The model.** A mass $m$ on a spring of force constant $k$ feels $F=-kx$, with potential $V=\tfrac12kx^2$. The motion is $x(t)=A\cos(\omega t+\delta)$ with

$$
\omega=\sqrt{\frac km},\qquad \nu=\frac{\omega}{2\pi},\qquad E=\tfrac12kA^2
$$

**Why this model describes a bond.** Near the minimum of any smooth potential energy curve $V(R)$, the first derivative vanishes, so the Taylor expansion about the equilibrium bond length $R_e$ begins at second order:

$$
V(R)\approx V(R_e)+\tfrac12V''(R_e)(R-R_e)^2
$$

Every bond, whatever its details, looks like a spring at small displacements, with $k=V''(R_e)$. For a diatomic molecule the mass is the reduced mass $\mu$ of Section 4.1, and $x=R-R_e$.

**What classical physics predicts.**

- The amplitude $A$, hence the energy, is continuous, and the energy can be exactly zero (the oscillator at rest at the bottom of the well).
- Each vibrational mode contributes $k_BT$ to the thermal energy (equipartition).
- The classical probability of finding the mass at a given position is inversely proportional to its speed, so it is largest at the turning points.

**Where it fails.**

- Molecules absorb infrared light only at sharp frequencies, not as a continuum.
- The heat capacity of H$_2$ or N$_2$ at room temperature shows *no* vibrational contribution. This is the same "freezing out" of high-frequency modes that Planck found for radiation in Section 1.2: when $h\nu\gg k_BT$, the mode is not thermally excited.

> **Status of the principle: harmonic approximation**
> *Approximate.* It is the leading term of a Taylor expansion, exact only as displacements go to zero. Section 5.11 examines how it fails.

---

## 5.2 Quantum oscillator

**The Hamiltonian.** Following Section 2.3,

$$
\hat H=\frac{\hat p^2}{2m}+\tfrac12m\omega^2\hat x^2=-\frac{\hbar^2}{2m}\frac{d^2}{dx^2}+\tfrac12m\omega^2x^2
$$

**Where quantization will come from.** As in the box of Chapter 3, the particle is confined, now by a soft wall that grows without limit. Acceptable wavefunctions must vanish as $x\to\pm\infty$ to be normalizable, and only special energies allow this. The mechanism is the same as before. The route we take to the answer is different, and shows a pattern that already appeared in Chapter 4: **a spectrum can follow from commutation relations alone, with no differential equation solved.**

---

## 5.3 Ladder operators

**Definition.** Define

$$
\hat a=\sqrt{\frac{m\omega}{2\hbar}}\left(\hat x+\frac{i\hat p}{m\omega}\right),\qquad
\hat a^\dagger=\sqrt{\frac{m\omega}{2\hbar}}\left(\hat x-\frac{i\hat p}{m\omega}\right)
$$

Using $[\hat x,\hat p]=i\hbar$, they satisfy

$$
[\hat a,\hat a^\dagger]=1
$$

**The Hamiltonian in terms of them.** Multiplying out,

$$
\hat a^\dagger\hat a=\frac{m\omega}{2\hbar}\left(\hat x^2+\frac{\hat p^2}{m^2\omega^2}\right)-\frac12
\;\Longrightarrow\;
\hat H=\hbar\omega\left(\hat a^\dagger\hat a+\tfrac12\right)
$$

**Deriving the spectrum.** Let $\hat N=\hat a^\dagger\hat a$ and suppose $\hat N|n\rangle=n|n\rangle$. From $[\hat N,\hat a]=-\hat a$ and $[\hat N,\hat a^\dagger]=+\hat a^\dagger$:

- $\hat a|n\rangle$ is an eigenstate of $\hat N$ with eigenvalue $n-1$ (**lowering**).
- $\hat a^\dagger|n\rangle$ is an eigenstate with eigenvalue $n+1$ (**raising**).

The eigenvalues form a ladder with unit steps. But the ladder cannot extend downward forever: the squared length of $\hat a|n\rangle$ is

$$
\langle n|\hat a^\dagger\hat a|n\rangle=n\ge0
$$

so no eigenvalue can be negative. The only way to stop the descent is for some state to give exactly zero when lowered, $\hat a|0\rangle=0$, and this requires that $n$ be a non-negative integer (a non-integer $n$ would lower to negative values, a contradiction). Hence $n=0,1,2,\dots$, with

$$
\hat a|n\rangle=\sqrt n\,|n-1\rangle,\qquad \hat a^\dagger|n\rangle=\sqrt{n+1}\,|n+1\rangle
$$

**Interpretation.** The operators $\hat a^\dagger$ and $\hat a$ create and destroy one quantum of vibrational excitation. The same language is used for photons and, later, for excitations of many-electron systems.

> **Status of the principle: ladder-operator spectrum**
> *Derived* from the commutation relation alone.

---

## 5.4 Energy quantization

$$
\boxed{E_n=\hbar\omega\left(n+\tfrac12\right)=h\nu\left(n+\tfrac12\right)},\qquad n=0,1,2,\dots
$$

**The levels are equally spaced by $\hbar\omega$.** This is unusual: in the box the spacing grew as $n$ (Section 3.2), in the rigid rotor it grew as $J$ (Section 4.4). An equally spaced ladder gives absorption at a single fundamental frequency, which is what the infrared spectrum of a bond shows.

**Closing the loop with Planck.** The energy *absorbed or emitted* between adjacent levels is $h\nu$, and $n$ quanta correspond to $E-E_0=nh\nu$. Each mode of the electromagnetic field is an oscillator, so Planck's rule $E_n=nh\nu$ of Section 1.2 is now a consequence: it is the excitation energy above the ground state. The additional $\tfrac12h\nu$ per mode is a constant that does not affect the observed thermal spectrum.

**Vibrational frequency of a bond.**

$$
\tilde\nu=\frac{1}{2\pi c}\sqrt{\frac k\mu}
$$

For CO, $k\approx1857$ N/m and $\mu=1.14\times10^{-26}$ kg give $\tilde\nu\approx2144$ cm$^{-1}$, matching the observed 2143 cm$^{-1}$. The formula also explains the trends: **stiffer bonds (larger $k$) and lighter atoms (smaller $\mu$) vibrate faster.**

> **Status of the principle: oscillator energies**
> *Derived* exactly for the model. Planck's $E_n=nh\nu$, *Empirical* in Chapter 1, is now *Derived*.

---

## 5.5 Zero-point energy

**The result.** The lowest level is not zero:

$$
E_0=\tfrac12\hbar\omega
$$

**Why.** It is the uncertainty principle at work, as in the box (Section 3.2). Take the spread in position to be $\sigma$ and the spread in momentum to be $\hbar/2\sigma$. Then

$$
E(\sigma)\approx\frac{\hbar^2}{8m\sigma^2}+\tfrac12m\omega^2\sigma^2
$$

Compressing the oscillator raises the first term, stretching it raises the second. The minimum occurs at $\sigma^2=\hbar/2m\omega$, giving $E=\tfrac12\hbar\omega$. Unlike the atomic-size estimate of Section 2.8, this one is not a lucky coincidence: the ground state exactly saturates $\Delta x\,\Delta p=\hbar/2$, so the estimate is exact.

**Chemical consequences.**

- **Dissociation energies.** A molecule can never sit at the bottom of its potential well. The energy needed to break a bond from its ground vibrational state is $D_0=D_e-\tfrac12\hbar\omega$ (to lowest order). For H$_2$, the well depth is $D_e\approx4.75$ eV, the zero-point energy is $\approx0.27$ eV, and the measured $D_0\approx4.48$ eV.
- **Isotope effects.** Since $\omega\propto1/\sqrt\mu$, heavier isotopes have lower zero-point energy. For a C–H bond, $\mu\approx0.930$ u; for C–D, $\mu\approx1.725$ u, so the C–D frequency is $\sqrt{0.930/1.725}=0.73$ times the C–H frequency (about 2900 cm$^{-1}$ falling to about 2100 cm$^{-1}$). The C–D bond starts lower and is effectively harder to break, which is the origin of kinetic isotope effects (Chapter 16).

> **Status of the principle: zero-point energy**
> *Derived.* It is a direct consequence of the commutation relation $[\hat x,\hat p]=i\hbar$.

---

## 5.6 Wavefunctions

**The ground state.** The condition $\hat a\psi_0=0$ becomes a first-order equation:

$$
\left(x+\frac\hbar{m\omega}\frac{d}{dx}\right)\psi_0=0\;\Longrightarrow\;
\psi_0(x)=\left(\frac{m\omega}{\pi\hbar}\right)^{1/4}e^{-m\omega x^2/2\hbar}
$$

a Gaussian. Higher states come from raising: $|n\rangle=\dfrac{1}{\sqrt{n!}}(\hat a^\dagger)^n|0\rangle$. With the dimensionless coordinate $\xi=\sqrt{m\omega/\hbar}\,x$, and $N=(m\omega/\pi\hbar)^{1/4}$:

| $n$ | $\psi_n(\xi)$ | Nodes |
|---|---|---|
| 0 | $N\,e^{-\xi^2/2}$ | 0 |
| 1 | $N\sqrt2\,\xi\,e^{-\xi^2/2}$ | 1 |
| 2 | $N\dfrac{1}{\sqrt2}\left(2\xi^2-1\right)e^{-\xi^2/2}$ | 2 |

**Interpretation.**

- **Nodes and energy.** $\psi_n$ has $n$ nodes, so energy rises with nodes, as in the box.
- **Ground-state statistics.** $\langle x\rangle=0$, $\langle x^2\rangle=\hbar/2m\omega$, $\langle p^2\rangle=m\hbar\omega/2$, and their product gives $\Delta x\,\Delta p=\hbar/2$ exactly. In general $\langle x^2\rangle_n=(\hbar/m\omega)(n+\tfrac12)$.
- **Tunneling into the classically forbidden region.** A classical oscillator with energy $E_n$ cannot go beyond $x_t=\sqrt{(2n+1)\hbar/m\omega}$. The quantum wavefunction extends past it. For $n=0$ the probability of finding the particle *outside* the classical region is $\operatorname{erfc}(1)\approx16\%$. In chemical terms, a bond in its ground state spends a sixth of its time stretched or compressed beyond what classical mechanics allows.
- **Correspondence.** The classical oscillator is most likely found at the turning points. The ground state is most likely at the centre, the opposite. But at large $n$ the quantum density, averaged over its rapid oscillations, follows the classical $1/\sqrt{A^2-x^2}$ shape, as Section 2.11 requires.

> **Status of the principle: oscillator wavefunctions**
> *Derived.*

---

## 5.7 Hermite polynomials

Solving the differential equation directly gives the same states in the standard form

$$
\psi_n(x)=\frac{1}{\sqrt{2^nn!}}\left(\frac{m\omega}{\pi\hbar}\right)^{1/4}H_n(\xi)\,e^{-\xi^2/2}
$$

where $H_n$ are the **Hermite polynomials**, generated by $H_{n+1}=2\xi H_n-2nH_{n-1}$:

| $n$ | $H_n(\xi)$ |
|---|---|
| 0 | $1$ |
| 1 | $2\xi$ |
| 2 | $4\xi^2-2$ |
| 3 | $8\xi^3-12\xi$ |
| 4 | $16\xi^4-48\xi^2+12$ |

**Interpretation.** The degree of $H_n$ equals the number of nodes. The Gaussian $e^{-\xi^2/2}$ forces the wavefunction to vanish at large $\lvert x\rvert$, satisfying the boundary condition of Section 5.2. That the ladder operators, acting on a Gaussian, always give a polynomial times the same Gaussian is what makes this family closed. These functions reappear in the vibrational structure of electronic transitions (the Franck–Condon principle, Chapter 13).

> **Status of the principle: Hermite form**
> *Derived.* It is the same solution as Section 5.6, written in the traditional notation.

---

## 5.8 Parity and symmetry

**Symmetry.** The potential $V=\tfrac12m\omega^2x^2$ is unchanged under $x\to-x$. The parity operator $\hat\Pi\psi(x)=\psi(-x)$ therefore commutes with $\hat H$, and by Section 4.9 the eigenstates have definite parity:

$$
\psi_n(-x)=(-1)^n\psi_n(x)
$$

Even $n$ gives even functions, odd $n$ gives odd functions.

**Consequences.**

- $\langle x\rangle=0$ in every stationary state, since $\lvert\psi_n\rvert^2$ is even.
- **A selection rule, derived.** Writing $\hat x=\sqrt{\hbar/2m\omega}\,(\hat a+\hat a^\dagger)$,

$$
\langle m|\hat x|n\rangle=\sqrt{\frac{\hbar}{2m\omega}}\left(\sqrt n\,\delta_{m,n-1}+\sqrt{n+1}\,\delta_{m,n+1}\right)
$$

is non-zero only when $m=n\pm1$. In Chapter 4 the rotational selection rule was stated without proof. Here the matching vibrational rule follows directly from the ladder operators.

> **Status of the principle: parity and $\Delta n=\pm1$**
> *Derived* from the symmetry of the potential and the ladder algebra.

---

## 5.9 Virial theorem

**Statement.** In a stationary state, the average kinetic and potential energies are related. Using $[\hat H,\hat x\hat p]$ and the fact that $\langle\hat x\hat p\rangle$ does not change in time in a stationary state,

$$
2\langle T\rangle=\left\langle x\frac{dV}{dx}\right\rangle
$$

**For the oscillator**, $x\,dV/dx=kx^2=2V$, so

$$
\langle T\rangle=\langle V\rangle=\tfrac12E_n
$$

The energy is always shared equally. This matches the ground-state values: $\langle p^2\rangle/2m=\hbar\omega/4=\tfrac12E_0$.

**For a Coulomb potential** ($V\propto1/r$) the same theorem gives $2\langle T\rangle=-\langle V\rangle$, so $E=-\langle T\rangle$. This is used in Chapter 6 for hydrogen and in Chapter 10 for a subtle point about bonding: when a bond forms and the total energy *falls*, the kinetic energy *rises* in the accounting.

> **Status of the principle: virial theorem**
> *Derived* from the Schrödinger equation for any stationary state.

---

## 5.10 Vibrational spectroscopy

**Two conditions for infrared absorption.**

1. **Selection rule** $\Delta n=\pm1$, from Section 5.8.
2. **A changing dipole moment.** The molecule's dipole varies with the bond length, $\mu(x)\approx\mu_0+(d\mu/dx)\,x$, and the absorption strength is proportional to $(d\mu/dx)\langle m|\hat x|n\rangle$. If $d\mu/dx=0$ the vibration is infrared-inactive. This condition is stated here and derived in Chapter 13. Consequently CO and HCl absorb, while H$_2$ and N$_2$ do not.

**The fundamental.** The $0\to1$ transition at $\tilde\nu=(1/2\pi c)\sqrt{k/\mu}$ is the main band. Since almost all molecules are in $n=0$ at room temperature (for CO the excited-state population is $e^{-h\nu/k_BT}\approx3\times10^{-5}$), the fundamental dominates. Contrast this with rotation, where the population is spread over $J\approx7$ (Section 4.7). Vibration is frozen out; rotation is not.

**From frequency to bond.** Since $\tilde\nu\propto\sqrt{k/\mu}$, stretching frequencies track bond stiffness:

| Bond type | Typical stretching region (cm$^{-1}$) |
|---|---|
| C–H | 2850–3000 |
| C≡C, C≡N | 2100–2260 |
| C=O | 1650–1750 |
| C=C | 1620–1680 |
| C–O | 1050–1150 |

Multiple bonds are stiffer than single bonds, and X–H stretches are high because of H's small mass. These are group frequencies, and they are transferable because a vibration localized in one bond depends mostly on that bond's $k$ and its atoms' masses.

**Overtones and rovibrational structure.** In the pure harmonic model, transitions with $\Delta n=\pm2$ are forbidden. They appear weakly in real spectra because of anharmonicity (Section 5.11). In the gas phase, each vibrational band shows rotational fine structure: an R branch ($\Delta J=+1$) and a P branch ($\Delta J=-1$), with a gap at the centre. This is Chapter 4's rotor riding on this chapter's oscillator.

> **Status of the principle: infrared spectroscopy**
> *Derived* for $\Delta n=\pm1$ in the harmonic model. The dipole-change requirement is stated here and *Derived* in Chapter 13. The group-frequency table is *Empirical*: a useful pattern built on the harmonic result, with ranges that depend on the molecular environment.

---

## 5.11 Real molecular vibrations

**Where the harmonic model fails.** A real bond potential is not a parabola. It flattens at large $R$ (the bond breaks) and rises steeply at small $R$ (the atoms repel). A common model that captures this is the Morse potential

$$
V(R)=D_e\left[1-e^{-a(R-R_e)}\right]^2
$$

whose levels are

$$
E_n=hc\left[\tilde\omega_e\left(n+\tfrac12\right)-\tilde\omega_ex_e\left(n+\tfrac12\right)^2\right]
$$

with $\tilde\omega_ex_e=\tilde\omega_e^2/4D_e$ in wavenumber units. The levels **converge** as they approach dissociation instead of staying equally spaced.

**A test case.** For HCl, the harmonic formula with $k=516$ N/m gives $\tilde\omega_e=2991$ cm$^{-1}$. The anharmonicity constant is $\tilde\omega_ex_e\approx52.8$ cm$^{-1}$, so the observed fundamental is $\tilde\omega_e-2\tilde\omega_ex_e\approx2885$ cm$^{-1}$, matching the measured 2886 cm$^{-1}$. The harmonic model was 100 cm$^{-1}$ off, and the correction accounts for it.

**What anharmonicity changes.**

- Levels are not equally spaced, so overtones and "hot bands" do not fall at integer multiples of the fundamental.
- The selection rule $\Delta n=\pm1$ becomes approximate, with weak overtones.
- A harmonic well cannot dissociate; a Morse well can.
- Vibration and rotation couple: the average bond length grows with $n$, so the rotational constant decreases, $B_n\approx B_e-\alpha(n+\tfrac12)$. This, together with centrifugal stretching, is the correction to the rigid rotor foreshadowed in Section 4.8.

**Polyatomic molecules and normal modes.** A molecule with $N$ atoms has $3N-6$ vibrational degrees of freedom ($3N-5$ if linear). The atoms' motions are coupled, but a coordinate transformation to **normal modes** decouples them: each mode is an independent oscillator, and the total energy is

$$
E=\sum_i\hbar\omega_i\left(n_i+\tfrac12\right)
$$

| Molecule | Mode | $\tilde\nu$ (cm$^{-1}$) | IR active? |
|---|---|---|---|
| CO$_2$ (linear, 4 modes) | Symmetric stretch | 1388 | No (no dipole change) |
| | Bend (twofold degenerate) | 667 | Yes |
| | Asymmetric stretch | 2349 | Yes |
| H$_2$O (bent, 3 modes) | Symmetric stretch | 3657 | Yes |
| | Bend | 1595 | Yes |
| | Asymmetric stretch | 3756 | Yes |

CO$_2$ is the instructive case: a mode can exist and yet be invisible in the infrared because it produces no change in dipole moment. Symmetry decides which modes are active (Chapter 11), and Raman spectroscopy (Chapter 13) sees the modes that infrared misses. Modern codes compute normal modes by diagonalizing the matrix of second derivatives of the energy (Chapter 14).

**Why molecules are not perfect harmonic oscillators.** The harmonic picture is an approximation that improves with lower energy. Real molecules have anharmonic potentials, couple different modes to one another, and can dissociate. Nevertheless the harmonic approximation remains the standard starting point for zero-point energies, vibrational partition functions (Chapter 15), and thermochemistry.

> **Status of the principle: real vibrations**
> *Approximate.* The harmonic model is accurate at low excitation and forms the reference frame for everything else. Morse levels are an *Approximate* model of anharmonicity, not an exact solution for real bonds.

---

## What remains unexplained

| Open question | Where it is resolved |
|---|---|
| What is the potential that the atoms actually feel, and where does its shape $V(R)$ come from? | Chapters 9 and 10 |
| How does the Schrödinger equation behave for the attractive Coulomb potential of an atom? | Chapter 6 |
| How are IR intensities and the dipole-change requirement derived? | Chapter 13 |
| Why does Raman scattering reveal the modes that IR misses? | Chapter 13 |
| How do symmetry labels classify normal modes? | Chapter 11 |
| How are vibrational energies turned into heat capacity and entropy? | Chapter 15 |
| How are vibrational frequencies computed for a molecule? | Chapter 14 |

**Next:** Chapter 6 applies the machinery of Chapters 2 to 4 to the atom itself: the hydrogen atom, in which the Coulomb potential provides the radial problem and the spherical harmonics of Chapter 4 supply the angular part.
