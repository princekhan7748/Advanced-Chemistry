# Chapter 9 — Approximation: How Real Quantum Chemistry Becomes Possible

*Part I · The Quantum Structure of Matter*

Chapter 8 kept deferring a question. The central-field approximation of Section 8.4 replaced the true electron–electron repulsion with an averaged potential, but never said how to compute that average. Slater's rules of Section 8.6 gave a shielding constant, but admitted it was a fit, not a calculation. Section 8.3's perturbative estimate of helium's energy missed experiment by five percent, and the gap was left unexplained. This chapter answers all three deferrals at once, because they are the same deferral: given that $\hat H\psi=E\psi$ cannot be solved exactly for more than one electron (Section 8.2), what principled, improvable methods exist for approximating it?

> **If exact solution is impossible beyond hydrogen, what distinguishes a good approximation from an arbitrary one?**
> **How, precisely, is the averaged potential of Section 8.4 supposed to be built?**
> **Why can nuclei be treated as fixed points while solving for the electrons, as implicitly assumed since Chapter 4's rigid rotor?**

| Mathematical result | Chemical destination |
|---|---|
| Variational upper bound on $E_0$ | Systematic improvement of trial wavefunctions; the origin of Section 8.6's effective nuclear charge |
| Perturbation series in a small parameter | Formal justification for the informal Zeeman and Stark calculations of Sections 6.12–6.13 |
| Born–Oppenheimer separation | The potential-energy surface $V(R)$ left unexplained since Chapter 5; the electronic/vibrational/rotational hierarchy of Section 4.8 |
| Hartree–Fock equations, Fock operator | A first-principles version of Section 8.4's central-field potential |
| Self-consistent field iteration | Precise meaning of "effective nuclear charge" (Section 8.6) |
| Configuration interaction, coupled-cluster | Systematic recovery of electron correlation; benchmark-quality energies |
| Basis sets | The practical machinery behind every computed molecular property in Chapters 10–20 |
| Model = physics retained + physics neglected | A permanent auditing tool for every approximation in the rest of the book |

**Roadmap.** What "approximate but not arbitrary" means (9.1) → two general strategies, variational and perturbative (9.2–9.3) → separating nuclear and electronic motion (9.4) → building a many-electron wavefunction properly: Hartree products, antisymmetrization, Hartree–Fock, the self-consistent field, and what exchange means inside it (9.5–9.9) → what Hartree–Fock still misses, and how to recover it (9.10–9.12) → the practical machinery, basis sets (9.13) → an audit of every approximation introduced (9.14).

---

## 9.1 Exact vs approximate theories

**What "exact" means here.** The non-relativistic Schrödinger equation of Section 2.9 is treated in this book as exact (setting aside the relativistic and QED corrections of Chapter 7). What fails is not the equation but the ability to solve it in closed form once more than one electron, or more than two bodies of any kind, are coupled together (Section 8.2).

**Two disciplined responses.** Rather than guessing an answer, as Bohr did for hydrogen (Section 1.6) before Chapter 6 supplied the real solution, this chapter builds two general-purpose strategies that apply to *any* Hamiltonian too hard to solve exactly:

- **Variational methods** (Section 9.2) turn "guess a wavefunction" into a controlled procedure: any guess gives an energy that is provably too high, and the guess can be systematically improved.
- **Perturbative methods** (Section 9.3) start from a solvable reference Hamiltonian and add the hard part as a small correction, formalizing what Sections 6.12 and 6.13 already did informally for the Zeeman and Stark effects.

**The standard to hold every later approximation to.** An acceptable approximation must state exactly which term of the exact Hamiltonian it drops or averages, and in principle allow that term to be added back. Every method in this chapter, and the central-field picture of Chapter 8 it makes precise, is held to that standard.
> **Status of the principle: approximation as a disciplined method**
> This is a statement of scope, not itself a physical claim requiring a status label; it is the organizing rule for everything that follows.

---

## 9.2 Variational principle

**The bound.** For any normalized trial function $\phi$ and the true Hamiltonian $\hat H$ with exact ground-state energy $E_0$,

$$
\langle\phi|\hat H|\phi\rangle\ge E_0
$$

**Proof.** Expand $\phi=\sum_nc_n\psi_n$ in the (unknown, but existing) exact eigenbasis of $\hat H$. Then $\langle\phi|\hat H|\phi\rangle=\sum_n|c_n|^2E_n\ge E_0\sum_n|c_n|^2=E_0$, since every $E_n\ge E_0$ and $\sum_n|c_n|^2=1$ by normalization. Equality holds only if $\phi$ is the exact ground state.

**Turning a guess into a method.** Choose a trial function with adjustable parameters and minimize $\langle\phi|\hat H|\phi\rangle$ over them; the minimum is the best estimate of $E_0$ available within that family, and it is guaranteed not to undershoot the truth. This converts guessing into optimization.

**Helium, improved.** Section 8.3 used *unperturbed* hydrogenic $1s$ orbitals (true nuclear charge $Z=2$) and found $-74.8$ eV against an experimental $-79.0$ eV. Instead, let the orbital exponent itself be a variational parameter $Z'$, allowing each electron's orbital to relax in response to the other's shielding:

$$
\psi(\mathbf r_1,\mathbf r_2)=\left(\frac{Z'^3}{\pi a_0^3}\right)e^{-Z'(r_1+r_2)/a_0}
$$

Evaluating $\langle\hat H\rangle$ with the *true* $Z=2$ Hamiltonian but this trial function (kinetic energy scales as $Z'^2$, nuclear attraction as $ZZ'$, the repulsion integral of Section 8.3 as $Z'$) gives

$$
\langle H\rangle(Z')=27.2\,Z'^2-2Z(27.2)Z'+\frac58(27.2)Z'=27.2\,Z'^2-91.8\,Z'\quad(\text{eV, at }Z=2)
$$

Minimizing, $d\langle H\rangle/dZ'=0$, gives

$$
Z'=\frac{27}{16}=1.6875,\qquad E_{\min}=-77.5\ \text{eV}
$$

**Interpretation.** $Z'<Z$: each electron variationally "discovers" that it should behave as if it saw a nuclear charge reduced by $5/16=0.3125$, a first-principles counterpart to Slater's empirical shielding constant of $0.35$ (Section 8.6), derived here rather than fitted. The variational energy, $-77.5$ eV, is closer to the experimental $-79.0$ eV than Section 8.3's perturbative estimate, and it is guaranteed to lie above the true value rather than on either side of it by chance.
> **Status of the principle: variational principle**
> *Derived* directly from the eigenvalue expansion of $\hat H$; an exact inequality with no approximation in its statement. Its use to estimate $E_0$ is *Approximate*, limited by the flexibility of the chosen trial family.

---

## 9.3 Perturbation theory

**Setup.** Split the Hamiltonian as $\hat H=\hat H^{(0)}+\hat H'$, where $\hat H^{(0)}$ has known eigenstates $\psi_n^{(0)}$ and energies $E_n^{(0)}$, and $\hat H'$ is treated as small. Expanding the true energy and state in powers of the perturbation gives, to first and second order,

$$
E_n=E_n^{(0)}+\underbrace{\langle\psi_n^{(0)}|\hat H'|\psi_n^{(0)}\rangle}_{E_n^{(1)}}+\underbrace{\sum_{m\ne n}\frac{|\langle\psi_m^{(0)}|\hat H'|\psi_n^{(0)}\rangle|^2}{E_n^{(0)}-E_m^{(0)}}}_{E_n^{(2)}}+\cdots
$$

**What this formalizes.** This is exactly the calculation performed informally in Sections 6.12 and 6.13: the Zeeman shift $E_{nlm}=E_n+\mu_BBm$ is a first-order result, $E_n^{(1)}=\langle\psi_{nlm}|\hat H'|\psi_{nlm}\rangle$ with $\hat H'=(\mu_B/\hbar)B\hat L_z$; the quadratic Stark shift of the $1s$ ground state is a second-order result, the sum above evaluated for $\hat H'=eFz$.

**Degenerate perturbation theory.** When several unperturbed states share an energy, as hydrogen's $2s$ and $2p_0$ do (Section 6.8), the first-order formula above is ambiguous: any combination of the degenerate states is an equally good zeroth-order choice. The correct procedure diagonalizes $\hat H'$ *within* the degenerate subspace first; the eigenvectors of that smaller problem are the "correct" zeroth-order states, and only they have a well-defined linear shift. This is precisely why the $n=2$ Stark effect (Section 6.13) is linear in $F$: the states $\tfrac1{\sqrt2}(2s\pm2p_0)$ diagonalize $\hat H'=eFz$ within the degenerate $n=2$ subspace and have nonzero $\langle z\rangle$, while $1s$, non-degenerate, has none and shifts only quadratically.

**When it fails.** The expansion is only useful if $\hat H'$ is genuinely small compared with the energy gaps of $\hat H^{(0)}$. Section 8.3's electron repulsion in helium, at $34$ eV against gaps of comparable size, is a marginal case; this is exactly why the perturbative helium estimate carried a $5\%$ error that the variational method of Section 9.2 reduced.
> **Status of the principle: perturbation theory**
> *Derived* as a formal power-series solution of the Schrödinger equation. *Approximate* whenever truncated at low order, with accuracy controlled by the size of $\hat H'$ relative to the unperturbed spectrum.

---

## 9.4 Born–Oppenheimer approximation

**The observation to explain.** Section 4.8 tabulated a large energy hierarchy: electronic transitions (several eV), vibrational transitions ($\sim0.1$–$0.3$ eV), rotational transitions ($\sim$ meV). This hierarchy was used without justification from Chapter 4 onward, whenever a molecule's rotation or vibration was solved separately from its electronic structure.

**Its origin.** The nuclear kinetic energy operator carries $1/M$, the electronic kinetic energy $1/m_e$, and $M/m_e\gtrsim1836$ for even the lightest nucleus. Electrons, far lighter, respond to nuclear motion essentially instantaneously; on the electrons' timescale the nuclei are effectively frozen. This licenses a two-step separation of the full molecular Hamiltonian $\hat H=\hat T_{\rm nuc}+\hat T_{\rm elec}+V(\mathbf r,\mathbf R)$:

1. **Fix the nuclei** at positions $\mathbf R$ and solve the purely electronic problem,
$$
\left[\hat T_{\rm elec}+V(\mathbf r,\mathbf R)\right]\varphi_{\rm elec}(\mathbf r;\mathbf R)=E_{\rm elec}(\mathbf R)\,\varphi_{\rm elec}(\mathbf r;\mathbf R)
$$
This is the many-electron problem of Chapter 8, solved for one nuclear geometry at a time, with $\mathbf R$ appearing only as a fixed parameter.
2. **Let the nuclei move** on the resulting energy landscape,
$$
\left[\hat T_{\rm nuc}+E_{\rm elec}(\mathbf R)\right]\chi(\mathbf R)=E\,\chi(\mathbf R)
$$

**What this resolves.** $E_{\rm elec}(\mathbf R)$ is exactly the potential $V(R)$ whose existence Chapter 5 assumed and whose origin was left as an open question at the end of that chapter: it is the electronic energy, recomputed at each nuclear geometry, of Chapter 8's many-electron problem. Vibration (Chapter 5) is nuclear motion in the well of $E_{\rm elec}(\mathbf R)$ near its minimum; rotation (Chapter 4) is nuclear motion around it. The energy-scale hierarchy of Section 4.8 is now explained rather than assumed: it is the mass ratio $m_e/M$, appearing as a small parameter in exactly the sense Section 2.11's correspondence principle already anticipated for heavy, nearly classical nuclei.

**Where it fails.** The separation assumes $E_{\rm elec}(\mathbf R)$ is a single, well-isolated surface. Where two electronic states come close in energy as $\mathbf R$ varies (near a conical intersection), the "instantaneous" assumption breaks down and nuclear and electronic motion must be treated together; this regime, central to photochemistry, is outside this book's scope.
> **Status of the principle: Born–Oppenheimer approximation**
> *Approximate*, controlled by the small parameter $m_e/M$. It is exact only in the limit $M\to\infty$; its breakdown near electronic near-degeneracies is a known, well-characterized failure, not an unexplained exception.

---

## 9.5 Hartree product

**The simplest many-electron guess.** Suppose each electron occupies its own orbital, independently: $\Psi_{\rm Hartree}=\varphi_1(1)\varphi_2(2)\cdots\varphi_N(N)$. Applying the variational principle (Section 9.2) to this restricted family, minimizing $\langle\Psi_{\rm Hartree}|\hat H|\Psi_{\rm Hartree}\rangle$ over the individual orbitals, reproduces exactly the central-field picture assumed without derivation in Section 8.4: each $\varphi_i$ satisfies a one-electron equation with an effective potential built from the averaged charge density of all the other electrons.

**The defect.** A simple product is not antisymmetric (Section 7.11): exchanging two electrons' labels changes $\Psi_{\rm Hartree}$ but does not negate it. The Hartree product violates the Pauli principle outright and must be discarded as a final answer, though it correctly identifies the mean-field *idea*.
> **Status of the principle: Hartree product**
> *Approximate* and, by itself, *inconsistent*: it fails the antisymmetry requirement of Section 7.11 and is used here only as a stepping stone to Section 9.7.

---

## 9.6 Antisymmetrization

**The fix, already built.** Chapter 7 supplied exactly the tool needed: the Slater determinant of Section 7.12,

$$
\Psi(1,\dots,N)=\frac1{\sqrt{N!}}\det\left[\chi_i(j)\right]
$$

automatically antisymmetric under exchange of any two electrons, for any choice of one-electron spin-orbitals $\chi_i$. Applying the variational principle to this restricted family, a single determinant rather than a single product, rather than to the Hartree product of Section 9.5, is the origin of the theory in Section 9.7.
> **Status of the principle: antisymmetrization via the Slater determinant**
> *Derived* in Chapter 7; restated here as the correct variational trial-function family.

---

## 9.7 Hartree–Fock theory

**The variational problem.** Minimize $\langle\Psi|\hat H|\Psi\rangle$ over all choices of orthonormal spin-orbitals $\{\chi_i\}$ in a single Slater determinant. Using Lagrange multipliers to enforce orthonormality, the minimization yields a set of coupled one-electron eigenvalue equations, the **Hartree–Fock equations**,

$$
\hat f_i\,\chi_i=\varepsilon_i\,\chi_i,\qquad
\hat f_i=\hat h_i+\sum_j\left(\hat J_j-\hat K_j\right)
$$

where $\hat h_i$ is the bare kinetic-plus-nuclear-attraction operator of Section 8.1, $\hat J_j$ is the **Coulomb operator** (the average electrostatic repulsion from the charge density of the electron in orbital $j$), and $\hat K_j$ is the **exchange operator**, a genuinely non-classical, non-local operator that exists only because $\Psi$ is a determinant rather than a product.

**What this delivers.** The operator $\hat f_i$ *is* the precise, first-principles version of Section 8.4's $V_{\rm eff}(r)$: Chapter 8 asserted that such an averaged potential exists and used it; this section derives its exact form from the variational principle applied to an antisymmetric wavefunction.
> **Status of the principle: Hartree–Fock equations**
> *Derived* from the variational principle applied to a single Slater determinant. *Approximate* as a description of the true many-electron wavefunction, restricted to the single-determinant form (Section 9.10 quantifies what this restriction misses).

---

## 9.8 Self-consistent field

**The circularity, and its resolution.** The Fock operator $\hat f_i$ depends on the orbitals $\{\chi_j\}$ (through $\hat J_j,\hat K_j$) that are themselves the unknowns being solved for. The equations are solved iteratively: guess a set of orbitals, build $\hat f_i$ from them, solve the resulting eigenvalue problem for a new set of orbitals, rebuild $\hat f_i$, and repeat until the orbitals no longer change from one cycle to the next. The field each electron moves in is then **self-consistent** with the charge distribution that field itself produces.

**What this makes precise.** This iteration is the exact procedure that Section 8.6's "effective nuclear charge" and Section 8.4's "central-field approximation" were informally describing: $Z_{\rm eff}$ is not a fixed number chosen in advance (as Slater's rules approximate it) but the outcome of this self-consistent loop, converged for a particular atom or molecule.
> **Status of the principle: self-consistent field**
> *Derived* as the natural iterative solution of the coupled Hartree–Fock equations. The converged orbitals are, within the single-determinant approximation, *exact*; the approximation is entirely in Section 9.7's restriction to one determinant.

---

## 9.9 Exchange

**Exchange, exactly, within Hartree–Fock.** The operator $\hat K_j$ of Section 9.7 acts only between electrons of the *same* spin: antisymmetry forces same-spin electrons apart in space (Section 7.13's vanishing determinant for coincident same-spin electrons), and $\hat K_j$ is precisely the energy consequence of that forced avoidance. Section 8.8's exchange integral $K$ is not an approximation layered on top of Hartree–Fock; it is computed exactly by $\hat K_j$, for whatever orbitals the self-consistent field converges to.

**Why Hund's rule is exact at this level.** Because $\hat K_j$ only couples same-spin electrons, a configuration with more parallel spins has more exchange stabilization available to it, exactly the mechanism of Section 8.9, now identified as an exact term of the Hartree–Fock energy rather than a separate physical assumption.
> **Status of the principle: exchange within Hartree–Fock**
> *Derived* exactly, given the single-determinant restriction. What Hartree–Fock does *not* capture, correlation between opposite-spin electrons, is the subject of Section 9.10.

---

## 9.10 Electron correlation

**What is still missing.** Hartree–Fock places each electron in the *average* field of the others; it does not let electrons of opposite spin dodge each other instant by instant, only on average through $\hat J_j$. This missing physics is called **correlation**, and the correlation energy is defined as

$$
E_{\rm corr}=E_{\rm exact}-E_{\rm HF}
$$

always negative, since the variational principle (Section 9.2) guarantees $E_{\rm HF}\ge E_{\rm exact}$ for any single determinant.

**Helium, quantified.** The Hartree–Fock limit for helium (the best possible single determinant, reached with an essentially complete basis set) gives $E_{\rm HF}\approx-77.87$ eV; the exact non-relativistic ground-state energy is $-79.01$ eV. The correlation energy is therefore

$$
E_{\rm corr}\approx-1.14\ \text{eV}
$$

a small fraction, under $1.5\%$, of the total energy, but larger than typical chemical bond energies and reaction barriers. This is the central practical lesson of this section: correlation is numerically small relative to the total electronic energy, yet often decisive for the chemistry.
> **Status of the principle: electron correlation**
> A precisely *Derived* quantity, $E_{\rm corr}=E_{\rm exact}-E_{\rm HF}$, once both energies are defined; its physical content, instantaneous opposite-spin avoidance, is exactly what the single-determinant approximation of Section 9.7 was constructed to leave out.

---

## 9.11 Configuration interaction

**A systematic recovery.** Write the true wavefunction as a linear combination of the Hartree–Fock determinant and determinants generated by exciting one, two, or more electrons from occupied to unoccupied ("virtual") orbitals,

$$
\Psi_{\rm CI}=c_0\Psi_{\rm HF}+\sum_ic_i\Psi_i^{\rm singles}+\sum_{i}c_i\Psi_i^{\rm doubles}+\cdots
$$

and determine the coefficients variationally, by diagonalizing $\hat H$ in this larger basis of determinants. **Full CI**, including every possible excitation, is exact within the limits of the underlying one-electron basis set (Section 9.13); in practice the expansion is truncated (commonly at single and double excitations, CISD), trading completeness for tractable computational cost.
> **Status of the principle: configuration interaction**
> *Derived* as an exact expansion in the full-CI limit; *Approximate*, and increasingly so with system size, whenever truncated, which is nearly always in practice.

---

## 9.12 Coupled-cluster methods

**A more efficient route to the same physics.** Rather than adding excited determinants linearly, the coupled-cluster ansatz writes the wavefunction as an exponential of an excitation operator,

$$
\Psi_{\rm CC}=e^{\hat T}\Psi_{\rm HF},\qquad \hat T=\hat T_1+\hat T_2+\cdots
$$

where $\hat T_1,\hat T_2,\dots$ generate single, double, and higher excitations. The exponential automatically generates products of lower excitations (for example, two simultaneous but independent double excitations) even when only $\hat T_1$ and $\hat T_2$ are kept explicitly (the widely used CCSD level, often supplemented perturbatively by triples, CCSD(T)). This captures a large share of the correlation missed at a given truncation level more efficiently than truncated CI at the same excitation order, and CCSD(T) is commonly treated as a practical benchmark against which cheaper methods are checked.
> **Status of the principle: coupled-cluster methods**
> *Approximate* at any finite truncation of $\hat T$, but part of a systematically improvable hierarchy that converges, in principle, to the exact correlation energy of Section 9.10.

---

## 9.13 Basis sets

**Turning equations into numbers.** Every method above requires the unknown orbitals to be represented concretely. The standard choice expands each molecular orbital as a linear combination of a fixed, finite set of known functions ("linear combination of atomic orbitals," previewed for bonding in Chapter 10),

$$
\chi_i(\mathbf r)=\sum_\mu c_{\mu i}\,\phi_\mu(\mathbf r)
$$

This turns the Hartree–Fock integro-differential equations of Section 9.7 into a matrix eigenvalue problem (the Roothaan–Hall equations), solvable numerically. Basis functions $\phi_\mu$ are usually Gaussian-type functions, computationally convenient for evaluating the resulting integrals despite not matching the true $e^{-Zr/a_0}$ decay of Chapter 6's exact hydrogenic orbitals near and far from the nucleus; several Gaussians are typically combined to approximate that correct shape.

**A second, independent source of error.** A finite basis set introduces error distinct from, and in addition to, the correlation error of Section 9.10: even an exact treatment of correlation (full CI) is only exact *within* the span of the chosen basis functions. Larger, more flexible basis sets approach the true, infinite-basis (complete-basis-set) limit at increasing computational cost.
> **Status of the principle: basis-set expansion**
> *Approximate*, with an error that is independent of, and must be assessed alongside, the electronic-structure method (Hartree–Fock, CI, coupled-cluster) used to build the wavefunction.

---

## 9.14 What each approximation throws away

Every method in this chapter fits the same audit:

$$
\boxed{\text{Model}=\text{Physics retained}+\text{Physics neglected}}
$$

| Model | Physics retained | Physics neglected |
|---|---|---|
| Central-field / Aufbau (Chapter 8) | One-electron orbital picture, shielding | Self-consistency; all correlation |
| Hartree–Fock | Exact exchange, self-consistent mean field | Opposite-spin (and residual same-spin) correlation |
| Configuration interaction / coupled-cluster | Correlation, systematically to a chosen order | Completeness beyond the truncation level |
| Finite basis set | Orbital shapes, to the flexibility of the basis | Everything outside the basis's span |
| Born–Oppenheimer | Electronic structure at fixed nuclei | Coupling between nuclear and electronic motion, largest near electronic near-degeneracies |

No entry in this table is an unexplained failure. Each is a named, quantifiable omission, and each can be systematically repaired, at a systematically rising computational cost, by moving down the corresponding hierarchy: bigger basis sets, higher excitation levels, or an explicit treatment of nuclear–electronic coupling where Born–Oppenheimer breaks down.
> **Status of the principle: the audit itself**
> Not a physical claim but a bookkeeping discipline; every approximation introduced from Chapter 8 onward, and every one still to come, should be statable in this form.

---

## What remains unexplained

| Open question | Where it is resolved |
|---|---|
| How do the self-consistent orbitals of this chapter combine when two atoms are brought together to form a bond? | Chapter 10 |
| How does symmetry reduce the cost of the self-consistent-field procedure for real molecules? | Chapter 11 |
| Why is hybridization, previewed in Section 6.13, a reorganization of these same self-consistent orbitals rather than a separate physical process? | Chapter 10 |
| How is the electronic energy surface $E_{\rm elec}(\mathbf R)$ of Section 9.4 actually explored to find equilibrium geometries and transition states? | Chapters 14 and 16 |
| What replaces wavefunction-based correlation methods in the density-based approach used for most large-molecule calculations? | Chapter 14 (density functional theory) |
| How do the partition functions of statistical mechanics build on the electronic, vibrational and rotational energies this chapter's Born–Oppenheimer separation makes well-defined? | Chapter 15 |

**Next:** Chapter 10 puts the self-consistent orbitals of this chapter to their first chemical use: two hydrogen atoms, brought together, and the molecular orbitals, bonding and antibonding, that the variational and Hartree–Fock machinery built here can now construct explicitly.
