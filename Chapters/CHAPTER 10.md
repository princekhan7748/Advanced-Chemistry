# Chapter 10 — Chemical Bonding from Electronic Structure

*Part I · The Quantum Structure of Matter*

Chapter 9 closed by promising two hydrogen atoms and the molecular orbitals that form when they are brought together. This chapter delivers that promise, and with it the central question of chemistry itself.

Lewis's 1916 picture, a shared pair of electrons, predates quantum mechanics by a decade and gets a remarkable amount right. But it cannot say why a pair should be shared rather than simply repel, why some diatomics (O$_2$) are magnetic when the shared-pair picture says they should not be, why bond strengths and lengths track the periodic table in the patterns of Chapter 8, or, more subtly, what actually happens to the *kinetic* energy of the electrons as a bond forms. All of these are now within reach: the Born–Oppenheimer separation of Section 9.4 turns "why do atoms bond" into a solvable electronic-structure problem at fixed nuclear geometry, and the variational machinery of Chapter 9 supplies the method for solving it.

> **What, precisely, replaces "a shared pair of electrons" once the machinery of Chapters 6 through 9 is brought to bear?**
> **Why does O$_2$ have two unpaired electrons, when its Lewis structure has none?**
> **The virial theorem said $E=-\langle T\rangle$ for any bound Coulomb system (Section 6.9). If a bond lowers the total energy, what happens to $\langle T\rangle$?**

| Mathematical result | Chemical destination |
|---|---|
| LCAO variational trial function | Molecular orbitals built from atomic orbitals |
| Bonding/antibonding energy splitting | Why some electron configurations bond and others do not |
| Node count of a molecular orbital | Bond order, bond length and bond strength trends |
| Symmetry-forced orbital degeneracy ($\pi,\pi^*$) | Paramagnetism of O$_2$; Hund's rule applied to molecules |
| Unequal LCAO coefficients | Bond polarity; electronegativity (Chapter 8) made quantitative |
| Unitary invariance of a Slater determinant | Hybridization as a representation, not a physical process |
| Slater's molecular virial theorem | The kinetic-energy subtlety of why bonds form at all |

**Roadmap.** What a bond is, and the Coulombic bookkeeping and fixed-nuclei Hamiltonian behind it (10.1–10.3) → the one-electron test case, $\text{H}_2^+$, and the LCAO method (10.4–10.6) → the first real molecule, $\text{H}_2$ (10.7) → extending to real diatomics: homonuclear and heteronuclear bonding, bond order, magnetism (10.8–10.11) → the two historical approaches compared, and what hybridization actually is (10.12–10.14) → bond length and energy in general, and the deep question of why bonding lowers the energy at all (10.15–10.16).

---

## 10.1 What is a chemical bond?

**The question, made precise.** In the Born–Oppenheimer picture of Section 9.4, a bond exists wherever the electronic energy surface $E_{\rm elec}(R)$ (Chapter 5's long-unexplained $V(R)$) has a minimum at some finite separation $R_e$ lower than the energy of the fully separated atoms. Everything from here on is the search for, and interpretation of, that minimum.

**Why the naive electrostatic story is not yet an answer.** It is tempting to say: negative electron density sits between two positive nuclei, attracting both, and that attraction is the bond. This is not false, but it is incomplete in a specific, checkable way, one this chapter returns to in Section 10.16: the virial theorem (Section 6.9) ties total energy to kinetic energy as rigidly as it ties it to potential energy, and a full account of bonding has to include both.
> **Status of the principle: the bond as a minimum of $E_{\rm elec}(R)$**
> *Derived* from the Born–Oppenheimer separation of Section 9.4; a definition, not yet an explanation of the mechanism.

---

## 10.2 Coulombic interactions

**The full accounting.** For any molecule, the exact (non-relativistic, clamped-nucleus) electronic energy contains only three kinds of pairwise Coulomb term: electron–electron repulsion, electron–nucleus attraction, and nucleus–nucleus repulsion (a fixed constant once $R$ is chosen, adding directly onto the electronic energy of Section 9.4). No other force appears. Whatever a bond turns out to be, it is built entirely from these familiar $1/r$ interactions, combined with the kinetic energy operator and channeled through the boundary conditions and antisymmetry requirements of Chapters 2–7.

**What is genuinely new.** Nothing in the list of interactions is new; what is new, starting in Section 10.4, is solving the many-body quantum problem those interactions pose once two nuclei, rather than one, are present.

---

## 10.3 Born–Oppenheimer molecular Hamiltonian

**Fixing the nuclei.** Following Section 9.4, clamp two nuclei of charge $Z_Ae,Z_Be$ at separation $R$ and write the electronic Hamiltonian for the electrons alone,

$$
\hat H_{\rm elec}=\sum_i\left(-\frac{\hbar^2}{2m_e}\nabla_i^2-\frac{Z_Ae^2}{4\pi\varepsilon_0r_{iA}}-\frac{Z_Be^2}{4\pi\varepsilon_0r_{iB}}\right)+\sum_{i<j}\frac{e^2}{4\pi\varepsilon_0r_{ij}}
$$

with $r_{iA},r_{iB}$ the distances from electron $i$ to each nucleus. The total electronic energy surface used throughout this chapter is $E_{\rm elec}(R)+Z_AZ_Be^2/4\pi\varepsilon_0R$, the electronic eigenvalue plus the (classical, fixed-$R$) nuclear repulsion.

---

## 10.4 $\text{H}_2^+$

**The fundamental molecular bonding problem.** With one electron and two protons ($Z_A=Z_B=1$), this is the molecular counterpart of Chapter 6's hydrogen atom: the simplest possible case, and, remarkably, exactly solvable (in confocal elliptical coordinates, a separation of variables suited to the two-center Coulomb problem, paralleling Chapter 6's use of spherical coordinates for one center). The exact solution gives an equilibrium bond length $R_e\approx2.00\,a_0$ ($105.7$ pm) and a binding energy $D_e\approx2.79$ eV relative to a separated proton and hydrogen atom.

**Why the exact route is not pursued further.** Elliptical coordinates work only for exactly two Coulomb centers; they give no route to $\text{H}_2$, let alone larger molecules. What is needed is a method that generalizes, even at the cost of exactness. Section 10.5 supplies it.

---

## 10.5 Linear combination of atomic orbitals

**The trial function.** Apply the variational principle (Section 9.2) using, as the simplest possible basis (Section 9.13), the two atomic $1s$ orbitals already available from Chapter 6, one centered on each proton:

$$
\psi_\pm=N_\pm\left(1s_A\pm1s_B\right),\qquad N_\pm=\frac1{\sqrt{2(1\pm S)}}
$$

where $S=\langle1s_A|1s_B\rangle$ is the **overlap integral**, a function of $R$ that runs from $S\to1$ as $R\to0$ (the orbitals coincide) to $S\to0$ as $R\to\infty$ (no overlap). This is exactly Chapter 2's superposition principle, anticipated in Section 2.1 ("a molecular orbital will be a superposition of atomic orbitals"), now made concrete.
> **Status of the principle: LCAO trial wavefunction**
> *Approximate*: a variational trial family (Section 9.2) built from a minimal atomic-orbital basis (Section 9.13), not the exact two-center solution of Section 10.4.

---

## 10.6 Molecular orbitals

**Evaluating the energy.** Writing $H_{AA}=\langle1s_A|\hat H_{\rm elec}|1s_A\rangle$ (the Coulomb integral) and $H_{AB}=\langle1s_A|\hat H_{\rm elec}|1s_B\rangle$ (the resonance integral, negative), the variational energies of the two combinations are

$$
E_\pm(R)=\frac{H_{AA}\pm H_{AB}}{1\pm S}
$$

**Bonding.** $\psi_+$, the in-phase combination, interferes constructively between the nuclei (Section 2.2's interference term, now applied to two atomic centers rather than two plane waves): electron density builds up in the internuclear region, where it is simultaneously close to both nuclei. $E_+(R)$ develops a minimum below the separated-atom energy: this is the **bonding orbital**, conventionally labeled $\sigma_{1s}$.

**Antibonding.** $\psi_-$, the out-of-phase combination, interferes destructively between the nuclei and has a node exactly on the internuclear axis, the molecular counterpart of Chapter 6's node-counting rule (flagged for this purpose already in Section 6.7): more nodes, more curvature, higher kinetic energy, higher total energy. $E_-(R)$ rises monotonically as $R$ decreases; no bonding minimum forms. This is the **antibonding orbital**, $\sigma_{1s}^*$.

**How the simple LCAO result compares with the exact one.** Using un-scaled $1s$ orbitals, this method gives $R_e\approx2.49\,a_0$ ($132$ pm) and $D_e\approx1.76$ eV for $\text{H}_2^+$, qualitatively correct but numerically well short of the exact $2.79$ eV of Section 10.4. The gap closes substantially if the orbital exponent is treated as a variational parameter, exactly as Section 9.2 did for helium: the atomic orbitals are allowed to contract in response to the second nucleus, recovering much of the missing binding.
> **Status of the principle: bonding and antibonding molecular orbitals**
> *Derived* from the variational principle applied to the LCAO trial family. *Approximate* in its numerical accuracy, improvable by orbital-exponent optimization (Section 9.2) or a larger basis (Section 9.13).

---

## 10.7 $\text{H}_2$

**Filling the orbitals.** With two electrons and the same $\sigma_{1s},\sigma_{1s}^*$ orbitals available, the ground state places both electrons in the lower-energy bonding orbital with paired spins, an antisymmetric single Slater determinant (Section 7.12) built from molecular rather than atomic spin-orbitals: $\Psi\approx\sigma_{1s}(1)\sigma_{1s}(2)\times\tfrac1{\sqrt2}[\alpha(1)\beta(2)-\alpha(2)\beta(1)]$, the direct molecular analogue of helium's $1s^2$ configuration worked out in Section 7.12.

**A large, informative discrepancy.** This simple MO wavefunction gives $D_e\approx2.68$ eV, sharply short of the experimental $D_e\approx4.75$ eV already used in Section 5.5. The reason is traceable and specific, not a mysterious failure: expanding $\sigma_{1s}(1)\sigma_{1s}(2)$ in atomic orbitals gives equal weight to the "covalent" terms ($1s_A(1)1s_B(2)$ and its exchange partner, one electron on each atom) and "ionic" terms ($1s_A(1)1s_A(2)$ and $1s_B(1)1s_B(2)$, both electrons on the *same* atom, i.e. $\text H^-\text H^+$). At large $R$, where the molecule should simply become two neutral atoms, this $50\%$ ionic character is unphysical, and it persists at all $R$ in the simple MO wavefunction, artificially raising the energy relative to the true dissociation limit. This is exactly the correlation problem of Section 9.10, now seen in a bond rather than an atom; adding configuration interaction (Section 9.11), specifically mixing in the doubly excited configuration built from $\sigma_{1s}^*$, systematically removes the excess ionic character and repairs the dissociation behavior.
> **Status of the principle: the simple $\text{H}_2$ MO wavefunction**
> *Approximate*, for a diagnosable reason: excess ionic character from the single-determinant restriction of Section 9.7, the same defect Section 9.10 quantified for helium.

---

## 10.8 Homonuclear diatomics

**Beyond $1s$.** For period-2 diatomics, the valence $2s$ and $2p$ atomic orbitals combine by symmetry: the $2p$ orbitals aligned along the bond axis form $\sigma_{2p},\sigma_{2p}^*$; the two perpendicular $2p$ orbitals form doubly degenerate $\pi_{2p},\pi_{2p}^*$ pairs, degenerate for the same reason the atomic $p$ orbitals were degenerate in Chapter 4 (rotational symmetry about the bond axis).

**A level crossing, and why.** For $\text{Li}_2$ through $\text{N}_2$, the $\sigma_{2p}$ orbital lies *above* the $\pi_{2p}$ pair in energy; from $\text{O}_2$ onward, the more intuitive ordering $\sigma_{2p}<\pi_{2p}$ is restored. The cause is $2s$–$2p$ mixing: where the atomic $2s$ and $2p$ orbitals are close enough in energy (true for the lighter elements, where $Z_{\rm eff}$, Section 8.6, is smaller and the $s$–$p$ gap of Section 8.5 is narrower), any two molecular orbitals of the same symmetry that the Hamiltonian is allowed to couple *will* couple and repel each other in energy, exactly the near-degenerate perturbation-theory mechanism of Section 9.3. This pushes $\sigma_{2s}^*$ up and $\sigma_{2p}$ up, enough to cross above $\pi_{2p}$ for the lighter elements.
> **Status of the principle: molecular orbital energy ordering**
> *Derived*, qualitatively, from orbital symmetry and near-degenerate mixing (Section 9.3); the specific crossing point is an *Approximate*, system-dependent numerical result rather than a fixed rule.

---

## 10.9 Heteronuclear molecules

**Unequal coefficients.** When the two atoms differ, $H_{AA}\ne H_{BB}$ (the atomic orbital energies differ), and the LCAO coefficients that minimize the energy are no longer forced equal by symmetry: $\psi=c_A\phi_A+c_B\phi_B$ with $|c_A|\ne|c_B|$ in general. The bonding orbital weights more heavily toward the lower-energy atomic orbital, generally the more electronegative atom (Section 8.16).

**What this delivers.** Electronegativity, introduced in Chapter 8 purely as an atomic index, now has a direct molecular meaning: it measures how unevenly a bonding LCAO coefficient will split between two atoms. A small electronegativity difference gives nearly equal coefficients (a covalent bond); a large one gives wildly unequal coefficients, approaching one atom holding essentially all the electron density (an ionic bond). Covalent and ionic bonding are not different mechanisms; they are the same LCAO variational problem at opposite ends of one continuum.

---

## 10.10 Bond order

**Definition.**

$$
\text{bond order}=\frac{(\text{electrons in bonding MOs})-(\text{electrons in antibonding MOs})}2
$$

Each antibonding electron adds a node between the nuclei (Section 10.6) and weakens the net bonding effect of one bonding electron; the formula is a direct bookkeeping of that cancellation.

| Molecule | Configuration (valence) | Bond order | $D_0$ (eV) |
|---|---|---|---|
| $\text{N}_2$ | $\sigma_{2s}^2\sigma_{2s}^{*2}\pi_{2p}^4\sigma_{2p}^2$ | 3 | $\approx9.8$ |
| $\text{O}_2$ | $\sigma_{2s}^2\sigma_{2s}^{*2}\sigma_{2p}^2\pi_{2p}^4\pi_{2p}^{*2}$ | 2 | $\approx5.1$ |
| $\text{F}_2$ | as O$_2$ with $\pi_{2p}^{*4}$ | 1 | $\approx1.7$ |
| $\text{Ne}_2$ | fully antibonding-cancelled | 0 | (unbound) |

Higher bond order tracks shorter, stronger bonds directly, exactly as Section 6.7 anticipated when it first flagged node-counting as "the primary tool for judging orbital shapes in molecular orbitals."

---

## 10.11 Magnetism

**Where MO theory outperforms the simple electron-pair picture.** A Lewis structure for O$_2$ places all electrons in pairs and predicts a diamagnetic molecule. Experimentally, liquid O$_2$ is paramagnetic, attracted into a magnetic field. The MO configuration of Section 10.10 explains this immediately: the last two electrons occupy the *degenerate* $\pi_{2p}^*$ pair, and Hund's rule (Section 8.9, its exchange-energy mechanism applying to molecular orbitals exactly as it did to atomic ones) places them with parallel spins, one in each degenerate orbital. Two unpaired electrons make O$_2$ paramagnetic, a direct, checkable prediction that the electron-pair picture cannot make at all.
> **Status of the principle: O$_2$ paramagnetism**
> *Derived* from the MO configuration of Section 10.8 combined with Hund's rule (Section 8.9); a case where the molecular-orbital picture succeeds precisely where the simpler shared-pair picture fails.

---

## 10.12 Valence bond theory

**A different starting point.** Heitler and London (1927), predating the full LCAO-MO treatment, built a trial wavefunction that keeps each electron's atomic identity explicit and adds antisymmetry directly:

$$
\Psi_{\rm VB}=N\left[1s_A(1)1s_B(2)+1s_A(2)1s_B(1)\right]\times\text{(singlet spin)}
$$

This is purely **covalent**: it contains no ionic ($\text H^-\text H^+$) terms at all, the opposite imbalance from Section 10.7's MO wavefunction. The original Heitler–London calculation gave $D_e\approx3.14$ eV, an improvement on the simple MO result of Section 10.7 but still short of the experimental $4.75$ eV, now because the wavefunction has *no* ionic flexibility where some is genuinely needed, especially near $R_e$.

**Resonance.** Adding ionic terms back in, with a variationally optimized weight, is what valence bond theory calls "resonance between covalent and ionic structures," the VB-theory route to the same physics MO–CI reaches from the opposite direction in Section 10.7.
> **Status of the principle: valence bond (Heitler–London) wavefunction**
> *Approximate*, for the mirror-image reason to Section 10.7: it excludes ionic character that is present, to some degree, in the true wavefunction at all but the largest separations.

---

## 10.13 Molecular orbital theory vs valence bond theory

**Not a competition between physical pictures.** Both MO and VB wavefunctions are variational trial functions (Section 9.2) applied to the identical exact Hamiltonian of Section 10.3. Simple MO theory overweights ionic character; simple VB theory excludes it entirely. The exact wavefunction lies between the two, and both methods converge toward it under systematic improvement: MO theory by configuration interaction (Section 9.11, mixing in antibonding-derived excited determinants to dilute the excess ionic weight), VB theory by adding ionic resonance structures with optimized weight. Neither is more "correct" as a starting point; each is a different zeroth-order approximation to the same underlying physics, with different, identifiable, and correctable defects.

---

## 10.14 Hybridization

**Recalling the preview.** Section 6.13 already showed the essential mathematics: an external electric field mixed hydrogen's degenerate $2s$ and $2p_0$ orbitals into $\tfrac1{\sqrt2}(2s\pm2p_0)$, states with a permanent dipole pointing in one direction, and called this "nothing more than a superposition of degenerate states... a representation, not a separate physical process."

**The same mixing, driven by bonding instead of a field.** In a molecule, it is not an external field but the variational optimization of Section 9.7 that selects, for a given atom, the combination of its valence $s$ and $p$ orbitals best oriented to overlap with its bonding partners. Mixing one $2s$ and three $2p$ orbitals on carbon produces four equivalent $sp^3$ hybrids pointing toward the vertices of a tetrahedron, matching methane's observed geometry; mixing one $2s$ and two $2p$ orbitals gives three $sp^2$ hybrids at $120^\circ$ plus one unhybridized $p$ orbital, matching the trigonal-planar geometry and $\pi$ system of ethylene.

**Why this is a representation, not a discovery of new physics.** A Slater determinant (Section 7.12) is invariant, up to an overall constant, under any unitary transformation mixing its occupied orbitals among themselves: rotating a set of canonical molecular orbitals into a set of localized hybrid orbitals changes *how the same total wavefunction is described*, not the wavefunction, the total electron density, or the total energy themselves. Hybrid orbitals are chosen because they give a chemically intuitive, localized, bond-by-bond picture; they are not a separate physical state competing with the delocalized canonical molecular orbitals of Sections 10.6–10.9. This is the direct chemical payoff of the same mathematics previewed in Section 6.13.
> **Status of the principle: hybridization**
> *Derived*, as a unitary reorganization of an already-derived set of occupied orbitals (Sections 7.12 and 9.7). It changes the representation, not the physics; it is not itself an independent physical process.

---

## 10.15 Bond length and bond energy

**Reading the curve.** The full $E_{\rm elec}(R)+$ nuclear-repulsion curve constructed section by section above has a minimum at $R=R_e$ of depth $D_e$ below the separated-atom limit; Section 5.11's Morse potential is the standard empirical fit to this same curve, now understood as the electronic energy surface of Section 9.4 rather than an assumed shape. The measured dissociation energy $D_0=D_e-\tfrac12\hbar\omega$ (Section 5.5) subtracts the zero-point vibrational energy the nuclei carry even at their lowest vibrational level.

**Trends.** Bond length and strength inherit the periodic trends of Chapter 8 through $Z_{\rm eff}$ and orbital size (Section 8.13): smaller, more compact atomic orbitals of similar energy overlap more effectively at short range, giving shorter, stronger bonds; higher bond order (Section 10.10) does the same by adding bonding electron pairs directly.

---

## 10.16 Why bonds exist

**The subtlety promised at the start of this chapter.** Section 6.9 established, for any bound Coulomb system, the virial relation $2\langle T\rangle=-\langle V\rangle$, hence $E=-\langle T\rangle$. For a molecule at fixed nuclear separation $R$, the exact statement (Slater's molecular virial theorem, 1933) carries one extra term:

$$
2\langle T\rangle(R)=-\langle V\rangle(R)-R\,\frac{dE}{dR}
$$

where $E(R)$ is the full electronic-plus-nuclear-repulsion energy of Section 10.3. At the equilibrium bond length, $dE/dR=0$ by definition of a minimum, and the extra term vanishes: the simple atomic relation is restored exactly,

$$
2\langle T\rangle(R_e)=-\langle V\rangle(R_e)\qquad\Longrightarrow\qquad E(R_e)=-\langle T\rangle(R_e)
$$

**The consequence.** Bond formation lowers the total energy: $E(R_e)<E(\infty)$, where $E(\infty)$ is the energy of the fully separated atoms, each individually obeying its own atomic virial theorem, $E(\infty)=-\langle T\rangle(\infty)$ (Section 6.9). Combining the two exact relations,

$$
E(R_e)<E(\infty)\quad\Longrightarrow\quad -\langle T\rangle(R_e)<-\langle T\rangle(\infty)\quad\Longrightarrow\quad \langle T\rangle(R_e)>\langle T\rangle(\infty)
$$

**The total kinetic energy of the electrons is higher at the bonded equilibrium than in the separated atoms**, exactly as the virial theorem requires whenever the total energy falls. Since $E=T+V$ and $T$ rises while $E$ falls, $V$ must fall by *more* than $E$ does: the potential-energy stabilization from Section 10.1's "shared density attracts both nuclei" picture is real and is, in fact, larger in magnitude than the net binding energy, with the kinetic-energy rise acting as a cost paid against it, not a benefit contributing to it. The naive electrostatic story of Section 10.1 was not wrong about the sign of $\langle V\rangle$; it was incomplete for omitting that $\langle T\rangle$ cannot simply stay put while $E$ falls, and for that reason it cannot, by itself, be turned into a quantitative account of bond formation.
> **Status of the principle: the virial-theorem accounting of bonding**
> *Derived* exactly, via Slater's molecular virial theorem, at the equilibrium geometry. It shows precisely what must happen to $\langle T\rangle$ as a bond forms; it does not by itself resolve every detail of how the electron density redistributes to produce that increase, a finer question this book does not pursue further.

---

## What remains unexplained

| Open question | Where it is resolved |
|---|---|
| How does symmetry classify which atomic orbitals are even allowed to combine, beyond the $\sigma,\pi$ labels used informally here? | Chapter 11 |
| How is the qualitative MO diagram of Section 10.8 turned into quantitative orbital energies for a real polyatomic molecule? | Chapter 11 (symmetry-adapted orbitals), Chapter 14 (computation) |
| How does the same LCAO method extend to conjugated $\pi$ systems and aromaticity? | Chapter 12 |
| How are the electronic transitions between these molecular orbitals observed spectroscopically? | Chapter 13 |
| How is the bonding-energy accounting of Section 10.16 extended to reaction energetics along a full potential-energy surface? | Chapter 16 |
| How do frontier molecular orbitals (HOMO, LUMO) built here predict which molecules react with which? | Chapter 17 |

**Next:** Chapter 11 supplies the systematic tool this chapter used only informally: point-group symmetry. It formalizes why $\sigma$ and $\pi$ orbitals cannot mix by symmetry alone, replaces the full rotational symmetry of Chapter 4 with the symmetry of a specific molecular shape, and prepares the classification of vibrations and electronic transitions that Chapter 13's spectroscopy will depend on.
