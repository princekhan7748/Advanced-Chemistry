# Chapter 8 — Many-Electron Atoms and the Periodic Table

*Part I · The Quantum Structure of Matter*

Chapter 7 finished with the tool needed to write down a wavefunction for more than one electron, the Slater determinant, and the law that governs it, the Pauli exclusion principle. Neither tool solves anything by itself. This chapter puts them to work on the first genuinely hard problem in the book: an atom with more than one electron.

Hydrogen's orbitals were exact. The moment a second electron is added, that stops being true, and with it goes the tidy fact from Section 6.8 that $2s$ and $2p$ share an energy. Real atoms show $2s$ below $2p$, $4s$ filling before $3d$, a half-filled $p^3$ shell that resists ionization more than its neighbors, and a periodic table whose shape follows directly from the machinery of Chapters 6 and 7. None of this is a new set of rules. It is what the central Coulomb problem does once the electrons are allowed to repel each other.

> **Why does $2s$ lie below $2p$ once a second electron is present, when Chapter 6 showed they are exactly degenerate in hydrogen?**
> **Why does an atom fill $4s$ before $3d$, and why does chromium break that very pattern?**
> **Where does the shape of the periodic table, its block structure and period lengths, actually come from?**

| Mathematical result | Chemical destination |
|---|---|
| Non-separability of $\hat H$ with $e^2/4\pi\varepsilon_0r_{12}$ | Why atoms beyond hydrogen need approximation at all |
| Central-field approximation, $V_{\rm eff}(r)$ | Restoring one-electron orbitals as a working picture |
| Shielding and penetration | Splitting $2s$ from $2p$; effective nuclear charge $Z_{\rm eff}$ |
| Exchange integral $K$ | Hund's rule; stability of half-filled and filled subshells |
| Madelung ($n+l$) ordering and its failures | Electron configurations; the anomalies of Cr, Cu and the $d,f$ blocks |
| Term symbols $^{2S+1}L_J$ | Atomic ground-state spectroscopy; magnetism |
| $Z_{\rm eff}$, $\langle r\rangle$ trends | Atomic and ionic radii, ionization energy, electron affinity, electronegativity |
| Nuclear charge + quantum numbers + statistics + repulsion | The periodic table itself |

**Roadmap.** The many-electron Hamiltonian and why it resists exact solution (8.1–8.3) → the central-field approximation and what it restores (8.4) → shielding, penetration and effective nuclear charge (8.5–8.7) → exchange and Hund's rule (8.8–8.9) → building up real atoms: Aufbau, configurations, term symbols (8.10–8.12) → the periodic table and its trends (8.13–8.18) → where the simple picture breaks (8.19).

---

## 8.1 The many-electron Hamiltonian

**Setting it up.** For an atom of nuclear charge $Ze$ with $N$ electrons, clamping the nucleus in place (a first use of the separation of electronic and nuclear motion formalized in Chapter 9), the non-relativistic Hamiltonian is

$$
\hat H=\sum_{i=1}^N\hat h_i+\sum_{i<j}\frac{e^2}{4\pi\varepsilon_0r_{ij}},\qquad
\hat h_i=-\frac{\hbar^2}{2m_e}\nabla_i^2-\frac{Ze^2}{4\pi\varepsilon_0r_i}
$$

Each $\hat h_i$ is a one-electron hydrogenic operator, identical in form to Chapter 6's Hamiltonian. The new piece, $\sum_{i<j}e^2/4\pi\varepsilon_0r_{ij}$, is the classical Coulomb repulsion between every pair of electrons, with $r_{ij}=|\mathbf r_i-\mathbf r_j|$.

**What is left out.** Relativistic corrections (Chapter 7), nuclear motion (Chapter 9), and magnetic (spin–spin, spin–other-orbit) interactions between electrons are all smaller than the repulsion term above and are added later where they matter.
> **Status of the principle: the many-electron Hamiltonian**
> *Derived* by adding the classical Coulomb repulsion (Section 1.1) to a sum of Chapter 6 one-electron Hamiltonians. *Approximate* in that it clamps the nucleus and omits relativity.

---

## 8.2 Why hydrogen can be solved exactly but helium cannot

**The obstruction.** Chapter 6's separation of variables worked because $V(r)$ depended on one electron's coordinate alone. The term $e^2/4\pi\varepsilon_0r_{12}$ depends on *both* electrons' positions simultaneously through $r_{12}=|\mathbf r_1-\mathbf r_2|$, and it does not factor into a function of $\mathbf r_1$ times a function of $\mathbf r_2$. The ansatz $\psi=\psi(\mathbf r_1)\psi(\mathbf r_2)$ that made Chapter 3's box and Chapter 6's hydrogen solvable simply fails: substituting it into $\hat H\psi=E\psi$ leaves a term that cannot be split between the two single-particle equations.

**Not a chemistry-specific problem.** This is the same obstruction as the classical three-body problem: two bodies orbiting a third, or here two electrons repelling each other while each is attracted to the nucleus, has no general closed-form solution. Helium's Schrödinger equation is exactly this three-body problem in quantum form.

**What is not lost.** The repulsion term is a well-defined, comparatively small correction (Section 8.3 gives its size), and the single-particle structure of Chapter 6, quantum numbers, nodes, orbital shapes, is too good an organizing idea to discard. The strategy of the rest of this chapter is to keep the one-electron picture as an approximation and correct it systematically.
> **Status of the principle: non-separability of the many-electron equation**
> *Derived.* No approximation has been made yet; this is an exact statement about the mathematical structure of $\hat H$.

---

## 8.3 Electron–electron repulsion

**A first estimate.** For helium ($Z=2$), pretend the electrons are independent and simply occupy hydrogenic $1s$ orbitals scaled to $Z=2$ (ignoring $r_{12}$ entirely). The zeroth-order energy is twice the hydrogenic value from Section 6.8:

$$
E^{(0)}=2\times\left(-13.6\,Z^2\ \text{eV}\right)=2\times(-54.4\ \text{eV})=-108.8\ \text{eV}
$$

**Adding the repulsion perturbatively.** The first-order correction is the expectation value of $e^2/4\pi\varepsilon_0r_{12}$ over this product state, a standard integral over two $1s$ orbitals:

$$
E^{(1)}=\left\langle\frac{e^2}{4\pi\varepsilon_0r_{12}}\right\rangle=\frac58\,Z\left(\frac{e^2}{4\pi\varepsilon_0a_0}\right)=\frac58(2)(27.2\ \text{eV})=34.0\ \text{eV}
$$

$$
E\approx E^{(0)}+E^{(1)}=-108.8+34.0=-74.8\ \text{eV}
$$

**Comparison with experiment.** The true ground-state energy of helium, from its two ionization energies ($24.6$ eV $+\,54.4$ eV), is $-79.0$ eV. The perturbative estimate is off by about $4.2$ eV, some $5\%$, all of it because the $1s$ orbitals used were the *unperturbed* hydrogenic ones: each electron, in reality, also pushes the other's charge density outward, an effect called **correlation** that first-order perturbation theory cannot see. A better zeroth-order orbital (Chapter 9's variational method, letting the effective charge relax) closes most of this gap.

**The lesson.** Electron repulsion is not a small correction to be waved away: at $34$ eV it is comparable to the entire binding energy. It must be included, but it need not be solved exactly to be useful, which motivates the mean-field strategy of Section 8.4.
> **Status of the principle: perturbative estimate of electron repulsion**
> *Approximate.* It uses unperturbed hydrogenic orbitals and first-order perturbation theory (formalized in Chapter 9); the $5\%$ discrepancy with experiment is the size of the neglected correlation.

---

## 8.4 Central-field approximation

**The idea.** Replace the instantaneous repulsion each electron feels from every other electron by an *averaged*, spherically symmetric potential $V_{\rm eff}(r_i)$: the field of the nucleus screened by the time-averaged charge cloud of all the other electrons. The Hamiltonian becomes approximately separable again,

$$
\hat H\approx\sum_i\left[-\frac{\hbar^2}{2m_e}\nabla_i^2+V_{\rm eff}(r_i)\right]
$$

a sum of one-electron problems, each solvable exactly for its angular part (the angular operator of Chapter 4 does not care what $V_{\rm eff}(r)$ looks like) and numerically for its radial part.

**What survives from hydrogen, and what does not.** Because $V_{\rm eff}$ is still spherically symmetric, $[\hat h_i,\hat L_i^2]=[\hat h_i,\hat L_{iz}]=0$ (Section 4.9), so each electron still has good quantum numbers $n,l,m$ and orbitals that look qualitatively like Chapter 6's: the same node counts (Section 6.7), the same angular shapes (Section 4.5). What is lost is the exact $1/r$ form of the potential, and with it hydrogen's accidental $l$-degeneracy (Section 6.8): $V_{\rm eff}(r)$ is no longer pure Coulomb, so states of the same $n$ but different $l$ split apart. This split is the subject of the next two sections.

**What is thrown away.** Replacing the instantaneous $\sum_j e^2/4\pi\varepsilon_0r_{ij}$ by its average discards the correlated, moment-to-moment avoidance of electrons for one another. This is exactly the correlation energy missing from Section 8.3's estimate, and it is why the central-field picture, however useful, is an approximation rather than an exact reformulation (Chapter 9 makes the averaging procedure precise: the self-consistent field).
> **Status of the principle: central-field approximation**
> *Approximate.* It restores separability and one-electron quantum numbers at the cost of replacing instantaneous repulsion with an averaged potential; the omitted difference is electron correlation.

---

## 8.5 Shielding and penetration

**The physical picture.** An electron in an outer orbital does not feel the full nuclear charge $Ze$: the electrons closer to the nucleus, on average, sit between it and the nucleus and partially cancel the nuclear attraction. This is **shielding**. But "closer to the nucleus, on average" depends on the orbital's shape, not just on $n$.

**Penetration decides how much shielding an orbital escapes.** Section 6.6 showed that for the same $n$, an $s$ orbital has a small inner maximum of radial probability close to the nucleus that a $p$ orbital of the same $n$ lacks (the $2s$ orbital penetrates; $2p$ does not), a direct consequence of the centrifugal barrier of Section 6.3: $l=0$ has no barrier, $l>0$ does. An electron that penetrates close to the nucleus spends part of its time inside the shielding cloud of the other electrons, where it feels close to the *full* nuclear charge, unscreened.

**The consequence.** Because $s$ penetrates more than $p$, which penetrates more than $d$, an $s$ electron of given $n$ is, on average, more tightly bound than a $p$ electron of the same $n$, which is more tightly bound than a $d$ electron. Hydrogen's $2s$–$2p$ degeneracy (Section 6.8), tied to the exact $1/r$ form of the Coulomb potential, is broken the moment $V_{\rm eff}(r)$ departs from pure $1/r$, and it departs precisely because of shielding:

$$
E_{ns}<E_{np}<E_{nd}<E_{nf}
$$

This resolves the first opening question of this chapter. It is not a new postulate; it is Section 6.6's penetration difference, now given an energetic consequence once a second electron is present to do the shielding.
> **Status of the principle: shielding and the $s<p<d<f$ ordering**
> *Derived* from the central-field approximation together with the penetration differences already present, but energetically inert, in the exact hydrogen wavefunctions of Chapter 6.

---

## 8.6 Effective nuclear charge

**Definition.** Write the potential felt by a given electron as an effective hydrogenic $-Z_{\rm eff}e^2/4\pi\varepsilon_0r$, with

$$
Z_{\rm eff}=Z-\sigma
$$

where $\sigma$, the **shielding constant**, absorbs everything Section 8.5 described. $Z_{\rm eff}$ depends on both $n$ and $l$ of the electron in question, and, self-consistently, on the configuration of every other electron.

**Slater's rules: a working estimate.** Slater's rules give $\sigma$ as a sum of empirical contributions: $0.35$ for each other electron in the same $n$ group (for $1s$, $0.30$), $0.85$ for each electron one shell lower ($n-1$), and $1.00$ for each electron two or more shells lower. For a $2p$ electron of carbon ($1s^22s^22p^2$): three other $n=2$ electrons contribute $3\times0.35=1.05$, and two $1s$ electrons contribute $2\times0.85=1.70$, giving $\sigma=2.75$ and

$$
Z_{\rm eff}=6-2.75=3.25
$$

far less than the full nuclear charge of $6$, and less still than the $Z_{\rm eff}\approx5.7$ felt by a $1s$ electron itself (shielded only by the $0.30$ from its partner).

**Chemical use.** $Z_{\rm eff}$ is what determines orbital size ($\langle r\rangle\propto n^2/Z_{\rm eff}$, the many-electron analogue of Section 6.9) and orbital energy, and its systematic growth across a period, and much slower growth down a group, is the root of nearly every periodic trend in Sections 8.13–8.18.
> **Status of the principle: effective nuclear charge and Slater's rules**
> Shielding itself is *Derived* from the central-field approximation. Slater's specific numerical recipe for $\sigma$ is *Empirical*, a fit to atomic data rather than a first-principles calculation; the self-consistent field of Chapter 9 supplies the first-principles version.

---

## 8.7 Orbital energy ordering

**Within a shell.** Section 8.5 fixed the order $s<p<d<f$ for the same $n$. Across shells, the ordering that emerges from solving the central-field problem for real atoms follows approximately the **Madelung ($n+l$) rule**: orbitals fill in order of increasing $n+l$, and for equal $n+l$, in order of increasing $n$:

$$
1s<2s<2p<3s<3p<4s<3d<4p<5s<4d<5p<6s<4f<5d<6p<7s<5f<6d
$$

**Why $4s$ can lie below $3d$.** This is not a violation of "higher $n$ means higher energy": $4s$ has $n+l=4$, $3d$ has $n+l=5$, so the rule places $4s$ lower, consistent with $4s$'s greater penetration (no centrifugal barrier at all, versus $3d$'s $l=2$ barrier) outweighing its larger $n$. The ordering is close, and, as Section 8.10 shows, it can be reversed by the details of a particular atom's electron count.

**A caution already visible here.** The $n+l$ rule is a regularity found by fitting the results of central-field calculations across the periodic table; it is not a theorem. It predicts the *filling order* well but should not be read as a permanent statement about which orbital has lower energy in every ion or every degree of occupation, a point Section 8.10 makes precise.
> **Status of the principle: Madelung ($n+l$) ordering**
> *Approximate* and *Empirical*: a regularity of central-field orbital energies across the periodic table, not a derived law. Section 8.19 catalogues where it fails outright.

---

## 8.8 Exchange interaction

**Two electrons, two orbitals.** Consider two electrons occupying distinct spatial orbitals $\varphi_a,\varphi_b$ of a central-field atom. Antisymmetry (Section 7.11) permits two combinations: spin singlet ($S=0$) with **symmetric** spatial part, or spin triplet ($S=1$) with **antisymmetric** spatial part,

$$
\Psi_{\rm singlet}=\frac1{\sqrt2}\left[\varphi_a(1)\varphi_b(2)+\varphi_a(2)\varphi_b(1)\right]\chi_{S=0},\qquad
\Psi_{\rm triplet}=\frac1{\sqrt2}\left[\varphi_a(1)\varphi_b(2)-\varphi_a(2)\varphi_b(1)\right]\chi_{S=1}
$$

**The repulsion energy differs.** Evaluating $\langle e^2/4\pi\varepsilon_0r_{12}\rangle$ over each spatial part gives

$$
E_{\rm singlet}=J+K,\qquad E_{\rm triplet}=J-K
$$

where $J=\left\langle\varphi_a\varphi_b\left|\dfrac{e^2}{4\pi\varepsilon_0r_{12}}\right|\varphi_a\varphi_b\right\rangle$ is the ordinary (Coulomb) repulsion, and $K$, the **exchange integral**, is positive for real orbitals. The antisymmetric spatial wavefunction vanishes identically when $\mathbf r_1=\mathbf r_2$ (a direct restatement of Section 7.13's vanishing determinant, here for two *different* orbitals rather than the same one): electrons with parallel spin are automatically kept apart by antisymmetry alone, before any force pushes them apart, so their Coulomb repulsion is systematically lower.

**Not a new force.** $K$ is not a magnetic interaction between the spins; it is a purely electrostatic ($e^2/4\pi\varepsilon_0r_{12}$) consequence of the exchange symmetry built into the wavefunction by the Pauli principle. Spin enters only because antisymmetry ties the spin state to the spatial state.

**A measured example.** In helium's excited $1s2s$ configuration, the triplet term ($^3S$) lies roughly $0.8$ eV below the singlet ($^1S$), an experimentally resolved splitting that is pure exchange energy: identical orbitals, identical $J$, different $K$.
> **Status of the principle: exchange interaction**
> *Derived* from antisymmetry (Section 7.11) applied to two distinct one-electron orbitals; the numerical value of $K$ for a given pair of orbitals is a property of the central-field solution and is *Approximate* to that extent.

---

## 8.9 Hund's rule

**The generalization.** For a partially filled shell of degenerate orbitals (a $p^2$, $p^3$, $d^5$ configuration, and so on), each pair of electrons that can be placed in *different* orbitals with *parallel* spin lowers the energy by one exchange integral $K$ relative to pairing them with opposite spin. Maximizing the number of such parallel-spin pairs means maximizing the total spin $S$ of the configuration, which is exactly **Hund's first rule**: for a given electron configuration, the ground term has the maximum multiplicity $2S+1$ allowed by the Pauli principle.

**Worked case: carbon's $2p^2$.** Placing the two $2p$ electrons in different orbitals ($p_x,p_y$, say) with parallel spins avoids both the extra Coulomb repulsion of double occupation *and* pays the exchange energy $-K$ relative to putting them in the same orbital or pairing their spins. This is why carbon's ground configuration is $2p_x^12p_y^1$ with parallel spins, not $2p_x^2$.

**Why this is not a mnemonic.** Hund's rule is often taught as an arbitrary filling instruction. Here it is the same physics as Section 8.8, applied to more than two electrons: a direct energetic consequence of antisymmetry combined with Coulomb repulsion, nothing else.

**A second and third rule, noted but not derived here.** Hund's second rule (maximize orbital angular momentum $L$ for the chosen $S$) and third rule (minimize $J=|L-S|$ for a shell less than half full, maximize $J=L+S$ for one more than half full, the sign set by the spin–orbit coupling of Section 7.8) refine the ordering further. Their justification is more involved, resting on subtler correlation and relativistic effects, and they are stated here as working rules (used in Section 8.12) rather than derived in full.
> **Status of the principle: Hund's first rule**
> *Derived* from the exchange interaction of Section 8.8. Hund's second and third rules are *Empirical* as presented here, though each has a physical origin (correlation; spin–orbit coupling) that could in principle be derived with more machinery than this book develops.

---

## 8.10 Aufbau-like configurations

**The naive picture.** Fill the Madelung-ordered orbitals of Section 8.7 from the bottom, two electrons per spatial orbital (Pauli, Section 7.13) with parallel spins within a degenerate subshell wherever possible (Hund, Section 8.9). This is the **Aufbau principle**.

**Why it is an approximation, not a law.** The central-field orbital energies of Section 8.4 are not fixed numbers; they depend on $V_{\rm eff}(r)$, which depends on which orbitals are occupied, which is exactly what Aufbau is trying to determine. Treating the Section 8.7 ordering as fixed and filling it mechanically ignores this self-consistency (made precise in Chapter 9), and it also ignores that the *total* energy of a configuration includes the exchange stabilization of Section 8.9, which the ordering of individual orbital energies does not.

**Where it breaks: chromium and copper.** The naive rule predicts chromium as $[\text{Ar}]3d^44s^2$; the observed ground configuration is $[\text{Ar}]3d^54s^1$. Moving one electron from $4s$ to $3d$ costs the small $4s$–$3d$ energy gap of Section 8.7, but it converts a shell with four parallel-spin $3d$ electrons and a doubly occupied $4s$ into two exactly half-filled, all-parallel-spin subshells, $3d^5$ and $4s^1$, gaining several extra exchange pairs at once (Section 8.9). The exchange gain outweighs the orbital-energy cost. Copper, $[\text{Ar}]3d^{10}4s^1$ rather than $3d^94s^2$, is the same trade in favor of a fully filled $3d^{10}$ shell (filled shells, like half-filled ones, maximize a particular kind of pairing stabilization). Analogous irregularities recur through the $d$- and $f$-blocks (Section 8.19).

**The pattern to keep.** This is not chromium behaving exceptionally. It is the same two ingredients, orbital energy ordering (Section 8.7) and exchange stabilization (Section 8.9), competing, with exchange occasionally winning. A one-line ordering rule cannot see that competition; a total-energy calculation can.
> **Status of the principle: Aufbau principle**
> *Approximate.* It is a first-pass, non-self-consistent bookkeeping device; Sections 8.9–8.10 show it can be overridden by exchange stabilization the ordering itself does not include.

---

## 8.11 Electron configurations

**Notation.** A configuration lists occupied subshells with their electron counts as superscripts, in order of filling: sodium is $1s^22s^22p^63s^1$, or, using the core-abbreviation that separates the chemically inert filled shells from the valence electrons that dominate reactivity, $[\text{Ne}]3s^1$.

| Element | Configuration |
|---|---|
| H | $1s^1$ |
| C | $[\text{He}]2s^22p^2$ |
| Ne | $[\text{He}]2s^22p^6$ |
| K | $[\text{Ar}]4s^1$ |
| Sc | $[\text{Ar}]3d^14s^2$ |
| Cr | $[\text{Ar}]3d^54s^1$ |
| Zn | $[\text{Ar}]3d^{10}4s^2$ |

**Ions.** Removing electrons from a transition-metal atom removes them from $4s$ before $3d$, even though $4s$ filled first: once occupied, the more diffuse, less penetrating $4s$ orbital is *less* tightly bound than the contracted $3d$ orbital for the resulting ion, because the ordering of Section 8.7 was computed for the neutral-atom screening environment and shifts once electrons, and their shielding, are removed. $\text{Fe}$ is $[\text{Ar}]3d^64s^2$; $\text{Fe}^{2+}$ is $[\text{Ar}]3d^6$, not $[\text{Ar}]3d^44s^2$. This is the same self-consistency warning as Section 8.10, now affecting which electron leaves rather than which enters.

---

## 8.12 Ground states and term symbols

**Coupling the angular momenta.** For light atoms, where the spin–orbit interaction of Section 7.8 is a small perturbation, the individual electrons' orbital angular momenta couple to a total $\mathbf L=\sum_i\mathbf l_i$ and their spins couple to a total $\mathbf S=\sum_i\mathbf s_i$ (Russell–Saunders, or $LS$, coupling), and only then does spin–orbit coupling combine them into $\mathbf J=\mathbf L+\mathbf S$. A **term symbol** records the result:

$$
{}^{2S+1}L_J
$$

with $L=0,1,2,3,\dots$ written as $S,P,D,F,\dots$ (capital letters, not to be confused with the orbital labels $s,p,d,f$ of a single electron).

**Worked case: carbon.** The $2p^2$ configuration of Section 8.9 allows several terms ($^1S,{}^1D,{}^3P$, from combining two $l=1$ electrons subject to the Pauli principle); Hund's first rule selects the triplet, $^3P$, as lowest. Hund's third rule then selects $J$: a shell less than half full favors the smallest $J$, so $J=|L-S|=|1-1|=0$. Carbon's ground term is $^3P_0$.

**Why this matters chemically.** The term symbol fixes the atom's total angular momentum, hence its response to a magnetic field (Section 6.12's Zeeman effect, generalized), its ground-state degeneracy ($2J+1$), and the selection rules governing its spectrum (derived in Chapter 13). It also underlies the paramagnetism or diamagnetism of transition-metal complexes (Chapter 20).
> **Status of the principle: term symbols and Russell–Saunders coupling**
> *Approximate*, valid when spin–orbit coupling (Section 7.8) is weak compared with electron repulsion, which holds for light atoms and fails progressively up the periodic table, where $jj$-coupling (individual $\mathbf j_i=\mathbf l_i+\mathbf s_i$ coupling first) becomes the better starting point.

---

## 8.13 Atomic size

**Down a group.** Adding a shell increases $n$; from $\langle r\rangle\propto n^2/Z_{\rm eff}$ (the many-electron form of Section 6.9), and because $Z_{\rm eff}$ for the outermost electron grows only slowly down a group (Section 8.6), size increases.

**Across a period.** $Z$ increases by one each step, but the added electron enters the *same* shell as the ones already there and shields the others by only about $0.35$ (Slater, Section 8.6), so $Z_{\rm eff}$ grows nearly as fast as $Z$ itself while $n$ stays fixed: $\langle r\rangle$ shrinks. This is why atomic radius falls sharply across a period and rises sharply at the start of the next.

---

## 8.14 Ionization energy

**The main trend.** Ionization energy tracks $Z_{\rm eff}^2/n^2$ (Section 6.8's energy formula, with $Z\to Z_{\rm eff}$): it rises across a period as $Z_{\rm eff}$ rises and $\langle r\rangle$ shrinks, and falls down a group as $n$ grows.

**Two exceptions, both already explained.**

- **Be $>$ B.** Removing an electron from beryllium's filled $2s^2$ costs more than removing boron's single, more shielded and less penetrating $2p^1$ electron (Section 8.5): $2p$ is simply higher in energy than $2s$ at the same $n$, independent of any new effect.
- **N $>$ O.** Nitrogen's $2p^3$ is a half-filled shell with three parallel spins, maximally exchange-stabilized (Section 8.9). Oxygen's $2p^4$ must pair two electrons in one orbital, losing an exchange pair and adding extra same-orbital Coulomb repulsion; the electron removed in ionizing oxygen is one of that paired set, and is correspondingly easier to remove.

Neither exception is arbitrary; both are Section 8.5 and Section 8.9 read off directly.

---

## 8.15 Electron affinity

**The main trend.** Adding an electron generally releases energy (a negative, favorable electron affinity) across a period, tracking the same growing $Z_{\rm eff}$, and becomes less favorable down a group as the added electron enters a larger, more distant orbital.

**Where it is weak or unfavorable.** Noble gases (filled shells: the new electron must start a new, poorly penetrating shell) and group 2 elements (filled $s^2$ subshell: the new electron must enter $p$, again higher in energy, Section 8.5) have near-zero or positive (unfavorable) electron affinities. Nitrogen's electron affinity is also close to zero, weaker than its neighbors: adding an electron to the exchange-stabilized $2p^3$ forces a pairing that loses exchange energy, the electron-affinity counterpart of Section 8.14's ionization-energy anomaly.

---

## 8.16 Electronegativity

**Mulliken's definition**, built directly from the two quantities just derived,

$$
\chi_{\rm Mulliken}=\frac{\text{IE}+\text{EA}}2
$$

is a chemical index rather than a new physical quantity: an atom that binds its own electrons tightly (large IE) and gains an extra electron favorably (very negative EA, hence large $-\text{EA}$ in this convention) will also, in a bond, pull shared electron density toward itself. The more familiar Pauling scale is built instead from measured bond dissociation energies and calibrated against Mulliken-like behavior; both scales track the same underlying $Z_{\rm eff}$ trend of Section 8.6, and their periodic pattern, rising across a period, falling down a group, is inherited entirely from Sections 8.14–8.15.
> **Status of the principle: electronegativity**
> The Mulliken definition is *Derived* from ionization energy and electron affinity, once those are accepted. The Pauling scale is *Empirical*, fit to thermochemical bond data. The underlying periodic trend in either scale is *Derived* from $Z_{\rm eff}$ (Section 8.6). Electronegativity's role in an actual bond is previewed here and developed in Chapter 10.

---

## 8.17 The periodic table

**Assembling the ingredients.** Nothing in this chapter is new physics beyond Chapters 6 and 7; the periodic table is what results from combining four things already derived:

$$
\boxed{\text{nuclear charge}\ +\ \text{quantum numbers }(n,l,m,m_s)\ +\ \text{Pauli exclusion}\ +\ \text{shielding and exchange}}
$$

**Block structure.** The $s$-, $p$-, $d$- and $f$-blocks correspond to which value of $l$ is being filled in the Aufbau sequence of Section 8.7; their widths, $2$, $6$, $10$, $14$, are exactly the orbital degeneracies $2(2l+1)$ of Section 6.4. **Period length** follows the same accounting: period 2 fills $2s,2p$ (2+6=8 elements); period 4 additionally picks up the $3d$ shell, delayed by the $4s$-before-$3d$ ordering of Section 8.7, giving 18 elements; period 6 additionally picks up $4f$, giving 32.

**What the table is not.** It is not an independent organizing principle laid over chemistry from outside. It is a bookkeeping device that becomes exactly the shell-filling pattern derived here once one knows the four ingredients above.

---

## 8.18 Periodic trends

A summary, with each trend's physical origin already established above:

| Property | Across a period | Down a group | Physical origin |
|---|---|---|---|
| Atomic radius | Decreases | Increases | $Z_{\rm eff}$ grows faster than shielding (8.6, 8.13) |
| Ionization energy | Increases | Decreases | $Z_{\rm eff}^2/n^2$ scaling of binding (8.14) |
| Electron affinity | More favorable | Less favorable | Same $Z_{\rm eff}$ trend (8.15) |
| Electronegativity | Increases | Decreases | Combines IE and EA (8.16) |

---

## 8.19 Where simple periodic rules fail

**$d$-block irregularities.** Beyond Cr and Cu (Section 8.10), similar exchange-driven exceptions recur for Mo, Ag, and others: the competition between orbital-energy ordering and exchange stabilization is close throughout the transition series, and no simple rule predicts every case without the underlying total-energy comparison.

**Lanthanide contraction.** The $4f$ orbitals, filling across the lanthanides, are poorly shielding (like $d$ electrons, they penetrate weakly and shield the outer $6s$ electrons less than a full unit of nuclear charge each), so $Z_{\rm eff}$ felt by the outer electrons rises steadily across the series, and atomic radius falls more than a simple one-electron picture predicts. Relativistic contraction of the inner $s,p$ orbitals (Section 7.9) adds to this effect for the heaviest lanthanides and actinides; the two causes are often inseparable in the observed radii.

**The inert-pair effect.** Heavy $p$-block elements (Tl, Pb, Bi) show a marked preference for oxidation states two below the group maximum, historically treated as an isolated rule. It is the same relativistic $s$-orbital contraction flagged in Section 7.9: the outermost $s^2$ pair is pulled in and stabilized enough that it resists participating in bonding.

**The statement to carry forward.** Every failure catalogued here is traceable to a specific, already-derived mechanism, exchange competing with orbital ordering, imperfect $f$-shell shielding, relativistic contraction, never to an unexplained exception. This is the philosophy stated at the start of the book, now demonstrated at the point where introductory chemistry usually just lists exceptions without asking why.
> **Status of the principle: periodic trends and their exceptions**
> The trends of Section 8.18 are *Derived* from $Z_{\rm eff}$. Their exceptions are *Derived* once the competing mechanism (exchange, $f$-shell shielding, relativity) is identified; none is *Empirical* in the sense of being unexplained, though predicting exactly when an exception occurs generally requires the numerical self-consistent-field calculation of Chapter 9 rather than a rule of thumb.

---

## What remains unexplained

| Open question | Where it is resolved |
|---|---|
| How is $V_{\rm eff}(r)$ actually computed, rather than estimated by Slater's rules? | Chapter 9 (Hartree–Fock, self-consistent field) |
| What is lost by the central-field/single-determinant picture, and how much does correlation actually contribute? | Chapter 9 |
| How do atomic orbitals and their energies combine to form molecular orbitals and bonds? | Chapter 10 |
| How does point-group symmetry replace the full rotational symmetry used here once atoms join into molecules? | Chapter 11 |
| How do term symbols determine which atomic transitions are spectroscopically allowed? | Chapter 13 |
| How does the $d$-orbital splitting hinted at here become ligand-field theory in transition-metal complexes? | Chapter 20 |

**Next:** Chapter 9 asks a question this chapter has repeatedly deferred: given that $\hat H\psi=E\psi$ cannot be solved exactly for more than one electron, what principled methods exist for approximating it? The variational principle, perturbation theory, the Born–Oppenheimer separation of electronic and nuclear motion, and the Hartree–Fock self-consistent field, the very field whose averaged form this chapter has been assuming, are built from first principles there.
