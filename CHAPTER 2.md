# Chapter 2 — Mathematical and Conceptual Foundations of Quantum Mechanics

*Part I · The Quantum Structure of Matter*

Chapter 1 ended with a list of things classical physics cannot say: why energy comes in discrete amounts, why a beam of silver atoms splits into exactly two, why electrons diffract, why an atom does not collapse. It also ended with a demand: a new mechanics in which these facts *emerge* rather than being imposed.

This chapter builds that mechanics. The opening question is simple:

> **If a system does not have a definite position and velocity, what does it have?**

Every mathematical object introduced below answers a specific puzzle from Chapter 1, and every one has a chemical destination:

| Puzzle from Chapter 1 | Mathematical object | Chemical destination |
|---|---|---|
| Two beams from one atomic beam (1.9) | State vector, superposition | Molecular orbitals as superpositions |
| Electrons diffract (1.7) | Complex wavefunction, phase | Bonding and antibonding interference |
| Observable quantities are discrete (1.4, 1.10) | Operators and eigenvalues | Energy levels, spectra |
| Measured values are always real | Hermitian operators | Real, distinguishable orbital energies |
| Sequential Stern–Gerlach scrambles results (1.9) | Commutators | Quantum numbers $n, l, m$ |
| Atoms do not collapse (1.5) | Uncertainty principle | Atomic size, zero-point energy |
| Levels imply Bohr's frequency rule (1.6) | Schrödinger equation | Stationary states, time-dependent spectroscopy |
| Big things look classical (1.7) | Correspondence principle | When nuclei may be treated classically |

**Roadmap.** States (2.1–2.2) → observables (2.3–2.7) → limits on knowledge (2.8) → dynamics (2.9) → the complete rule set (2.10) → the return of classical physics (2.11).

---

## 2.1 State vectors

**What classical physics assumed.** The state of a system is a list of definite numbers: positions and momenta.

**Where it failed.** A silver atom passing through a Stern–Gerlach magnet (Section 1.9) gives one of two outcomes, "up" or "down", along the magnet's axis. A classical moment would have a continuum of orientations. Something with exactly two outcomes needs a state description with exactly two independent alternatives.

**The new idea.** The state of a system is a **vector** $|\psi\rangle$ in a complex vector space called a **Hilbert space**: a vector space with an inner product $\langle\phi|\psi\rangle$ in which sums of vectors converge sensibly. For the silver atom's spin, the space is two-dimensional, with basis states $|\!\uparrow\rangle$ and $|\!\downarrow\rangle$. The general state is a **superposition**:

$$
|\psi\rangle = c_\uparrow|\!\uparrow\rangle + c_\downarrow|\!\downarrow\rangle, \qquad |c_\uparrow|^2+|c_\downarrow|^2=1
$$

with $|c_\uparrow|^2$ and $|c_\downarrow|^2$ the probabilities of the two outcomes. In general, for a set of orthonormal basis states $|n\rangle$ (so $\langle m|n\rangle=\delta_{mn}$),

$$
|\psi\rangle=\sum_n c_n|n\rangle, \qquad c_n=\langle n|\psi\rangle
$$

**Physical interpretation.** A superposition is not a statistical mixture of "really up" and "really down" atoms. Experiment shows this: if one selects atoms that are "up along $x$", the state is

$$
|{+x}\rangle=\tfrac{1}{\sqrt2}\left(|\!\uparrow\rangle+|\!\downarrow\rangle\right),
$$

which gives 50/50 outcomes along $z$ but a certain outcome along $x$. The *relative sign* of the two coefficients matters, which a mixture could not encode.

**Chemical consequence.** A molecular orbital will be a superposition of atomic orbitals (Chapter 10). The mathematics of "a bond is a combination of two atomic states" is exactly this equation.

> **Status of the principle: states as vectors**
> *Fundamental.* It is a postulate of the theory, justified by the experiments of Chapter 1.

---

## 2.2 Complex numbers and wavefunctions

**The wavefunction.** For a particle moving in space, the basis is the set of all positions. The coefficient of the basis state at position $x$ is the **wavefunction**:

$$
\psi(x)=\langle x|\psi\rangle
$$

**The Born rule.** $|\psi(x)|^2\,dx$ is the probability of finding the particle between $x$ and $x+dx$. Probabilities sum to one, so

$$
\int_{-\infty}^{\infty}|\psi(x)|^2\,dx=1 \qquad (\text{normalization})
$$

**Why complex numbers?** De Broglie's matter waves (Section 1.7) are naturally written as $e^{i(kx-\omega t)}$ with $p=\hbar k$ and $E=\hbar\omega$, where $\hbar=h/2\pi$. A complex amplitude carries both a magnitude and a **phase**: $\psi=|\psi|e^{i\theta}$.

**Global phase is invisible; relative phase is not.** Multiplying $\psi$ by $e^{i\alpha}$ changes nothing observable. But when two amplitudes combine,

$$
|\psi_1+\psi_2|^2=|\psi_1|^2+|\psi_2|^2+2\,\mathrm{Re}\left(\psi_1^*\psi_2\right)
$$

the last term depends on the relative phase. This *interference term* is what produced the diffraction peak in the Davisson–Germer experiment.

**Chemical consequence.** When two atomic wavefunctions add in phase, the cross term increases electron density between the nuclei (bonding). When they add out of phase, it removes density there (antibonding). All of Chapter 10 grows from this equation.

> **Status of the principle: Born rule**
> *Fundamental.* It is the link between the mathematics and measurable frequencies of outcomes.

---

## 2.3 Operators

**The problem.** If the state is a vector, how does one extract "the energy" or "the momentum" from it?

**The idea.** Every observable corresponds to an **operator** that acts on the state. For a wavefunction in one dimension:

| Observable | Operator |
|---|---|
| Position | $\hat x = x$ (multiply by $x$) |
| Momentum | $\hat p=-i\hbar\,\dfrac{d}{dx}$ |
| Kinetic energy | $\hat T=\dfrac{\hat p^2}{2m}=-\dfrac{\hbar^2}{2m}\dfrac{d^2}{dx^2}$ |
| Total energy (Hamiltonian) | $\hat H=\hat T+V(\hat x)$ |
| Angular momentum | $\hat{\mathbf L}=\hat{\mathbf r}\times\hat{\mathbf p}$ |

**Where does the momentum operator come from?** It is motivated by de Broglie. A plane wave $e^{ikx}$ should represent a particle of momentum $p=\hbar k$. Then

$$
-i\hbar\frac{d}{dx}\,e^{ikx}=\hbar k\,e^{ikx}=p\,e^{ikx},
$$

so the operator $-i\hbar\,d/dx$ returns the correct momentum when acting on the de Broglie wave. The other operators follow by writing classical expressions (such as $E=p^2/2m+V$) with $x\to\hat x$ and $p\to\hat p$. In three dimensions $\hat{\mathbf p}=-i\hbar\nabla$, and $\hat L_z=-i\hbar\,\partial/\partial\phi$.

**Chemical consequence.** The Hamiltonian $\hat H$ is the central operator of chemistry. Specifying it (which particles, which interactions) defines the molecule; everything else is solving for its consequences.

> **Status of the principle: operator representation of observables**
> *Fundamental* postulate, motivated by de Broglie. Its final justification is that it works.

---

## 2.4 Eigenvalues and eigenfunctions

**The idea.** If an operator acting on a function returns the same function times a number,

$$
\hat A\psi=a\,\psi,
$$

then $\psi$ is an **eigenfunction** and $a$ its **eigenvalue**. Examples:

- $e^{ikx}$ is an eigenfunction of $\hat p$ with eigenvalue $\hbar k$.
- The spin states $|\!\uparrow\rangle,|\!\downarrow\rangle$ are eigenstates of $\hat S_z$ with eigenvalues $\pm\hbar/2$.
- Solutions of $\hat H\psi=E\psi$ are energy eigenstates; the eigenvalues $E$ are the energy levels.

**The measurement rule.** A measurement of $A$ can only return one of the eigenvalues $a_n$ of $\hat A$. If the state is expanded in the eigenfunctions, $\psi=\sum_n c_n\psi_n$, then:

$$
P(a_n)=|c_n|^2, \qquad c_n=\langle\psi_n|\psi\rangle
$$

and after the measurement the state is $\psi_n$ (collapse).

**Physical interpretation.** This is the first place where the mathematics *explains* a Chapter 1 puzzle. Spectra show only discrete lines because the allowed energies are eigenvalues, and the photon emitted in a transition carries the eigenvalue difference:

$$
h\nu=E_{2}-E_{1}
$$

Why are some eigenvalue sets discrete? Because acceptable wavefunctions must be normalizable, continuous and single-valued. For a bound particle these conditions can be satisfied only for special values of $E$. **Quantization is a boundary-condition effect**, not an extra postulate. Chapter 3 shows this in detail.

*(For continuous spectra, such as free-particle momentum, the eigenfunctions cannot be normalized to one, and probabilities become densities $|c(k)|^2\,dk$.)*

> **Status of the principle: measurement gives eigenvalues**
> *Fundamental.* Discrete energy levels for bound systems are *Derived* from it plus boundary conditions.

---

## 2.5 Hermitian operators

**The problem.** Measured values are real numbers, and states with different measured values should be distinguishable (orthogonal). What property of an operator guarantees this?

**The definition.** An operator is **Hermitian** if

$$
\langle\phi|\hat A\psi\rangle=\langle\hat A\phi|\psi\rangle
$$

for all $\phi,\psi$. Observables are represented by Hermitian operators.

**Real eigenvalues.** Take $\hat A\psi=a\psi$. Then $\langle\psi|\hat A\psi\rangle=a\langle\psi|\psi\rangle$, but Hermiticity also gives $\langle\hat A\psi|\psi\rangle=a^*\langle\psi|\psi\rangle$. These are equal, so $a=a^*$.

**Orthogonal eigenfunctions.** Take $\hat A\psi_1=a_1\psi_1$ and $\hat A\psi_2=a_2\psi_2$ with $a_1\neq a_2$. Then

$$
a_1\langle\psi_2|\psi_1\rangle=\langle\psi_2|\hat A\psi_1\rangle=\langle\hat A\psi_2|\psi_1\rangle=a_2\langle\psi_2|\psi_1\rangle
$$

so $(a_1-a_2)\langle\psi_2|\psi_1\rangle=0$, and the overlap must vanish. If several eigenfunctions share an eigenvalue (degeneracy), they can always be chosen orthogonal.

**Chemical consequence.** Orbital energies are real, and orbitals of different energy are orthogonal. The orthonormality assumed in later molecular-orbital work is inherited from this theorem.

> **Status of the principle: real eigenvalues and orthogonality**
> *Derived.* Hermiticity is the assumption (a postulate); these two properties follow from it.

---

## 2.6 Commutators

**The problem.** In Section 1.9, a beam prepared "up along $z$" gives a definite $z$ result, but if measured along $x$ and then along $z$ again, the $z$ result is randomized. Some pairs of quantities cannot both be definite.

**The idea.** The **commutator** of two operators is

$$
[\hat A,\hat B]=\hat A\hat B-\hat B\hat A
$$

- If $[\hat A,\hat B]=0$, the observables are **compatible**: there exists a common set of eigenstates, so both can be sharp at once.
- If $[\hat A,\hat B]\neq0$, they cannot generally both have definite values.

**The fundamental commutator.** Acting on any function $f$:

$$
[\hat x,\hat p]f=x\left(-i\hbar f'\right)-\left(-i\hbar\right)(xf)'=i\hbar f,
\qquad\text{so}\qquad
[\hat x,\hat p]=i\hbar
$$

**Angular momentum.** $[\hat L_x,\hat L_y]=i\hbar\hat L_z$ (and cyclic permutations), and similarly for spin. But

$$
[\hat L^2,\hat L_z]=0
$$

so total angular momentum and one of its components can be sharp together, while two components cannot. This is exactly the structure seen in Stern–Gerlach.

**Chemical consequence.** Quantum numbers exist only for commuting sets. Hydrogen orbitals can be labelled by $n,l,m$ (Chapter 6) precisely because $\hat H$, $\hat L^2$ and $\hat L_z$ commute. Labels for orbitals are not conventions; they are the eigenvalues of a commuting set.

> **Status of the principle: compatibility and commutators**
> *Derived* from the operator postulates. The canonical relation $[\hat x,\hat p]=i\hbar$ is *Derived* here from $\hat p=-i\hbar\,d/dx$.

---

## 2.7 Expectation values

**The idea.** For a state that is not an eigenstate of $\hat A$, individual measurements scatter. The average over many identically prepared systems is the **expectation value**:

$$
\langle A\rangle=\langle\psi|\hat A|\psi\rangle=\int\psi^*\,\hat A\,\psi\,dx=\sum_n|c_n|^2a_n
$$

The last form shows that it is exactly the probability-weighted average of eigenvalues.

*Example.* If $\psi=c_1\psi_1+c_2\psi_2$ with energy eigenstates and $|c_1|^2=\tfrac14$, then $\langle E\rangle=\tfrac14E_1+\tfrac34E_2$, although no single measurement ever returns that number.

**Chemical consequence.** Most computed molecular properties are expectation values: energy $\langle\hat H\rangle$, dipole moment $\langle\hat\mu\rangle$, average orbital radius $\langle r\rangle$. The variational method of Chapter 9 works by minimizing $\langle\hat H\rangle$ over trial wavefunctions.

> **Status of the principle: expectation value**
> *Derived* from the Born rule and the eigenvalue postulate.

---

## 2.8 Uncertainty principle

**Statement.** For any two observables and any state,

$$
\Delta A\,\Delta B\;\ge\;\tfrac12\left|\langle[\hat A,\hat B]\rangle\right|,
\qquad \Delta A=\sqrt{\langle A^2\rangle-\langle A\rangle^2}
$$

For position and momentum this gives $\Delta x\,\Delta p\ge\hbar/2$.

**Derivation sketch.** Let $\delta\hat A=\hat A-\langle A\rangle$. The Cauchy–Schwarz inequality gives $(\Delta A)^2(\Delta B)^2\ge|\langle\delta\hat A\,\delta\hat B\rangle|^2$. Write $\delta\hat A\,\delta\hat B=\tfrac12[\hat A,\hat B]+\tfrac12\{\delta\hat A,\delta\hat B\}$: the commutator part has purely imaginary expectation, the anticommutator part purely real. Dropping the real part can only decrease the right side, so $|\langle\delta\hat A\,\delta\hat B\rangle|^2\ge\tfrac14|\langle[\hat A,\hat B]\rangle|^2$.

**Interpretation.** It is not a statement about clumsy instruments. It is a property of the *state*: a state sharply localized in $x$ is necessarily a broad superposition of momenta, and the reverse.

**Chemical consequence: why atoms do not collapse.** Chapter 1 left the classical atom spiralling into the nucleus. Confine an electron to a region of size $a$: then $p\gtrsim\hbar/a$ and the energy estimate is

$$
E(a)\approx\frac{\hbar^2}{2m_ea^2}-\frac{e^2}{4\pi\varepsilon_0a}
$$

The kinetic term rises as $a$ shrinks, so shrinking is penalized. Setting $dE/da=0$ gives

$$
a=\frac{4\pi\varepsilon_0\hbar^2}{m_ee^2}=a_0=0.529\ \text{Å},\qquad E=-\frac{\hbar^2}{2m_ea_0^2}=-13.6\ \text{eV}
$$

which is the size and binding energy of the hydrogen atom. The atom has a finite size because localizing the electron costs kinetic energy.

*Caution.* That the numbers match exactly is partly luck: "$p\approx\hbar/a$" is a rough estimate. The reliable conclusion is the *mechanism*, a competition between kinetic-energy pressure and Coulomb attraction. Exact treatment comes in Chapter 6.

> **Status of the principle: uncertainty relation**
> *Derived* rigorously from the commutator. The atomic-size estimate above is *Approximate*.

---

## 2.9 Schrödinger equation

**Motivation.** Take a free particle described by $e^{i(kx-\omega t)}$ with $p=\hbar k$, $E=\hbar\omega=p^2/2m$. Differentiating,

$$
i\hbar\frac{\partial}{\partial t}e^{i(kx-\omega t)}=\hbar\omega\,e^{i(kx-\omega t)},\qquad
-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial x^2}e^{i(kx-\omega t)}=\frac{\hbar^2k^2}{2m}e^{i(kx-\omega t)}
$$

The two right-hand sides are equal, so the free-particle relation $E=p^2/2m$ is the equation $i\hbar\,\partial\psi/\partial t=-\frac{\hbar^2}{2m}\partial^2\psi/\partial x^2$. Adding a potential $V$ gives the general form.

**Time-dependent Schrödinger equation:**

$$
i\hbar\frac{\partial\psi}{\partial t}=\hat H\psi
$$

**Time-independent equation.** For $\hat H$ independent of time, try $\psi(x,t)=\varphi(x)\,e^{-iEt/\hbar}$. Then

$$
\hat H\varphi=E\varphi
$$

This is an eigenvalue problem: **stationary states** are energy eigenstates. Their probability density $|\psi|^2=|\varphi|^2$ does not change with time, which is why atoms in energy eigenstates do not radiate. This resolves the classical instability of Section 1.5.

**Bohr's frequency rule, derived.** Consider a superposition of two stationary states:

$$
\psi=c_1\varphi_1e^{-iE_1t/\hbar}+c_2\varphi_2e^{-iE_2t/\hbar}
$$

The density contains the cross term $2\,\mathrm{Re}\!\left[c_1^*c_2\varphi_1^*\varphi_2\,e^{-i(E_2-E_1)t/\hbar}\right]$, so the charge distribution oscillates at angular frequency

$$
\omega_{21}=\frac{E_2-E_1}{\hbar}
$$

This is Bohr's postulated $h\nu=\Delta E$, now a consequence, and the origin of the Ritz combination principle. An oscillating charge distribution couples to light at exactly this frequency; Chapter 13 develops this into spectroscopy.

**Determinism and probability.** The equation is deterministic and linear: given $\psi(0)$, it fixes $\psi(t)$, and sums of solutions are solutions. Randomness enters only at measurement (Section 2.10).

**Chemical consequence.** Solving $\hat H\varphi=E\varphi$ for a molecule gives its energy levels and orbitals. All of quantum chemistry, in the sense of Chapters 3 to 14, is the art of solving or approximating this one equation.

> **Status of the principle: Schrödinger equation**
> *Fundamental* postulate for non-relativistic matter. It is motivated above but not derived; its authority is its predictive record. It is *Approximate* in that it ignores relativity (Chapter 7).

---

## 2.10 The postulates of quantum mechanics

Everything so far can be gathered into a compact rule set:

| # | Postulate | Chapter 1 puzzle it addresses |
|---|---|---|
| 1 | The state of a system is a normalized vector $\lvert\psi\rangle$ (wavefunction $\psi$) in a Hilbert space | Two-outcome beams, superposition |
| 2 | Each observable is a Hermitian operator | Real, measurable quantities |
| 3 | A measurement can only yield an eigenvalue of that operator | Discrete spectra, Franck–Hertz |
| 4 | The probability of eigenvalue $a_n$ is $\lvert\langle\psi_n\lvert\psi\rangle\rvert^2$ (Born rule) | Diffraction patterns, intensities |
| 5 | After a measurement giving $a_n$, the state is $\psi_n$ | Repeated Stern–Gerlach results |
| 6 | Between measurements, $\psi$ evolves by $i\hbar\,\partial_t\psi=\hat H\psi$ | Stable atoms, Bohr frequencies |

Two clarifications:

- **Identical particles and spin.** For electrons, additional structure (spin, antisymmetry) is required. It is introduced in Chapter 7 and is essential for every atom beyond hydrogen.
- **Interpretation.** Postulates 4 and 5 raise a question, the "measurement problem", that different interpretations answer differently (Copenhagen, many-worlds, and others). They agree on every prediction chemistry uses. This book uses the postulates as a computational recipe and does not depend on choosing an interpretation.

> **Status of the principle: the postulates**
> *Fundamental.* They are not derived from anything simpler in this framework. Their status rests on the breadth and precision of agreement with experiment.

---

## 2.11 Correspondence principle

**The problem.** The baseball of Section 1.7 has $\lambda\approx10^{-34}$ m, and no one has seen it interfere. The new mechanics must reduce to the old for large objects. How?

**Ehrenfest's theorem.** For a time-independent operator, differentiating $\langle A\rangle=\langle\psi|\hat A|\psi\rangle$ and using the Schrödinger equation gives

$$
\frac{d\langle A\rangle}{dt}=\frac{i}{\hbar}\langle[\hat H,\hat A]\rangle
$$

For $\hat H=\hat p^2/2m+V(x)$, the commutators are $[\hat H,\hat x]=-i\hbar\hat p/m$ and $[\hat H,\hat p]=i\hbar\,V'(x)$. Therefore

$$
\frac{d\langle x\rangle}{dt}=\frac{\langle p\rangle}{m},\qquad
\frac{d\langle p\rangle}{dt}=-\left\langle\frac{dV}{dx}\right\rangle
$$

These look like Newton's laws for the *averages*, with one catch: the force is $\langle V'(x)\rangle$, not $V'(\langle x\rangle)$. The two agree when the wavepacket is narrow compared with the distance over which the force varies. For macroscopic objects the wavelength is so small and the action so large compared with $\hbar$ that this holds to extraordinary precision.

**The general criterion.** Classical behaviour emerges when typical actions are much larger than $\hbar$, or equivalently when quantum numbers are large (Bohr's original form of the correspondence principle).

**Chemical consequence.** This tells us when classical mechanics is a legitimate approximation in chemistry. Heavy nuclei have short wavelengths and often move nearly classically, which underlies molecular-dynamics simulations. Electrons never do. Light nuclei, especially hydrogen, sit in the borderline region where zero-point energy and tunneling matter, which is why isotope effects exist. The formal separation of nuclear and electronic motion is the Born–Oppenheimer approximation (Chapter 9).

> **Status of the principle: classical limit**
> *Derived* (Ehrenfest theorem) for the average motion; the full statement of when classical trajectories emerge is *Approximate* and depends on the system.

---

## What remains unexplained

| Open question | Where it is resolved |
|---|---|
| What are the actual allowed energies for real systems, and how does quantization arise from boundary conditions? | Chapter 3 |
| Why are angular momentum components quantized in exactly this way, and what are the eigenfunctions? | Chapter 4 |
| Where does spin come from, given that the Schrödinger equation contains none? | Chapter 7 |
| How do many identical electrons obey these postulates? | Chapters 7 and 8 |
| What happens when $\hat H\psi=E\psi$ cannot be solved exactly? | Chapter 9 |
| How does light drive transitions between eigenstates? | Chapter 13 |

**Next:** Chapter 3 applies the machinery to exactly solvable systems, beginning with the particle in a box, where the meaning of "quantization from boundary conditions" becomes explicit.
