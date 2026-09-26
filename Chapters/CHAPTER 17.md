# Chapter 17 — Frontier Molecular Orbitals and Chemical Reactivity

*Part II · From Quantum States to Chemical Behavior*

Chapter 16 converted a barrier height into a rate, but treated the barrier itself as a given number, read off a potential-energy surface computed by Chapter 14's machinery. It said nothing about what, electronically, makes one barrier low and another high before any bond has broken or formed. Two closed-shell molecules approaching each other have no half-filled orbital of the kind that made H$_2^+$ (Section 10.4) an obvious bonding problem — every orbital on both sides is either completely full or completely empty. What, then, decides whether their approach is stabilizing or not?

The opening question:
> **Before any bond has formed or broken, what is it about two approaching closed-shell molecules' electronic structure that predicts whether their reaction will be fast or slow, and at which atom it will occur?**

**Why this needs new machinery, not old machinery reused.** Chapter 10 built molecular orbitals for a molecule already at its equilibrium geometry, by direct variational minimization. That machinery describes a finished product, not an approach in progress. What is needed is perturbation theory (Section 9.3) applied to two *separate* sets of orbitals — one belonging to each reactant — before they have mixed into anything new. Frontier molecular orbital (FMO) theory is exactly this: the leading term of that perturbative expansion, and, as Section 17.15 makes explicit, only the leading term.

| Mathematical result                                                  | Chemical destination                                                       |
| ------------------------------------------------------------------------ | ---------------------------------------------------------------------------- |
| Second-order perturbation stabilization between two orbitals             | Why an interaction between the highest occupied orbital of one molecule and the lowest unoccupied orbital of the other dominates all others |
| Koopmans' theorem: orbital energy $\approx-($ionization energy$)$ or $-($electron affinity$)$ | HOMO and LUMO energies read directly from Chapter 14's computed orbital energies |
| Finite-difference derivatives of $E$ with respect to electron number $N$ | Chemical potential, electronegativity, and hardness, each derived rather than defined qualitatively |
| The spatial (local) analogue of that same derivative                     | Fukui functions: predicting *where* on a molecule a reaction occurs, not just whether it occurs |
| Relative size of the electrostatic and orbital-mixing terms in the perturbation sum | Charge-controlled versus orbital-controlled reactivity; the HSAB principle |

**Roadmap.** Why frontier orbitals dominate (17.1–17.4) → two regimes of control (17.5) → naming the players (17.6–17.7) → turning ionization energy and electron affinity into quantitative reactivity indices (17.8–17.13) → the HSAB principle as a consequence (17.14) → an honest account of where this framework stops working (17.15).

---

## 17.1 Why molecules react

**Setting up the perturbation.** Treat two approaching, still-separate molecules A and B as an unperturbed system whose orbitals — all already known from Chapter 9's Hartree–Fock or Chapter 14's computational machinery — do not yet interact. The interaction Hamiltonian $\hat H'$ that switches on as they approach mixes every orbital of A with every orbital of B. Chapter 9's second-order perturbation theory gives the energy change from any one such pairing $i$ (on A) with $j$ (on B) as

$$
\Delta E_{ij}=\frac{\lvert\langle i\rvert\hat H'\lvert j\rangle\rvert^2}{\varepsilon_i-\varepsilon_j}
$$

exactly the two-level formula already used in Section 11.7 for orbital mixing within one molecule, now applied between two. The total interaction is a sum of such terms over every occupied-on-A/unoccupied-on-B pair (an electron can be virtually promoted into an empty orbital and lower the energy) and every occupied-on-B/unoccupied-on-A pair, plus destabilizing occupied-occupied terms (Section 17.4).

**Why one term can dominate the sum.** Each term's size depends on two things: the numerator (how strongly the two orbitals overlap and interact) and the denominator (how close their energies are). A pairing with orbitals only modestly further apart in energy than another contributes a *disproportionately* larger term, because the denominator is squared in the coefficient's dependence and enters directly, not just as a correction — so, all else being roughly comparable, the single smallest-denominator term can swamp the rest of the sum. This is the physical seed of frontier orbital theory, developed precisely in Section 17.4.
> **Status of the principle: perturbative orbital interaction between approaching molecules**
> *Derived*, as a direct extension of the second-order perturbation theory of Chapter 9 and the two-level mixing formula of Section 11.7 to a pair of molecules rather than a single one.

---

## 17.2 HOMO

**Definition.** The **highest occupied molecular orbital** is, in a ground-state closed-shell molecule, the occupied orbital of highest energy — the least tightly bound electron pair, and therefore the electrons most easily donated to a partner.

**Koopmans' theorem: connecting an orbital energy to a measurable quantity.** Within Hartree–Fock theory (Section 9.7, implemented computationally in Section 14.8), removing an electron from orbital $i$ while freezing every other orbital in place (no relaxation of the remaining electrons' distribution) changes the total energy by exactly $-\varepsilon_i$ — a result that follows directly from how the Hartree–Fock energy is built from orbital energies and pairwise repulsion terms. Applied to the HOMO,

$$
I\approx-\varepsilon_{\rm HOMO}
$$

identifying the first ionization energy with (minus) the HOMO's computed orbital energy — a genuine, checkable prediction from Chapter 14's Hartree–Fock output, not a qualitative correlation.
> **Status of the principle: Koopmans' theorem for the HOMO**
> *Approximate.* It neglects orbital relaxation (the remaining electrons reorganizing after ionization) and electron correlation (Section 14.9) entirely; both are genuine physical effects it discards by construction, quantified further in Section 17.15.

---

## 17.3 LUMO

**Definition.** The **lowest unoccupied molecular orbital** is the lowest-energy orbital available to accept an additional electron — the frontier for electron acceptance, exactly complementary to Section 17.2's HOMO.

**The same theorem, applied more shakily.** By the identical Koopmans' argument, $A\approx-\varepsilon_{\rm LUMO}$, identifying the electron affinity with the LUMO's orbital energy. This approximation is markedly less reliable than the HOMO case: the LUMO of the *neutral* $N$-electron molecule is being used to stand in for an orbital of the *anion*, an $(N+1)$-electron system whose relaxation upon adding an electron is typically far more significant, both because an extra electron more strongly perturbs the remaining electron distribution and because standard Hartree–Fock basis sets (Section 14.12) are usually not designed to describe the diffuse character an added electron often needs.
> **Status of the principle: Koopmans' theorem for the LUMO**
> *Approximate*, and markedly more so than for the HOMO (Section 17.2) — a distinction that matters directly for Section 17.15's assessment of the whole framework's reliability.

---

## 17.4 Orbital overlap

**Two kinds of pairing, two different signs.** Consider the two categories of interaction from Section 17.1's sum. An occupied orbital on A mixing with an occupied orbital on B produces two new combinations — one bonding, one antibonding — and *both* are filled (four electrons total, two pairs), so the stabilization of the bonding combination is largely cancelled by the destabilization of the antibonding one: this is a net repulsive, four-electron interaction, the same effect already noted (implicitly) for He$_2$'s bonding-and-antibonding-both-filled configuration in Chapter 10. An occupied orbital on A mixing with an *unoccupied* orbital on B, by contrast, only fills the lower (bonding) combination — a genuine, uncancelled, two-electron stabilization.

**Why HOMO–LUMO specifically.** Among all the occupied(A)–unoccupied(B) pairings available (and the mirror set, occupied(B)–unoccupied(A)), Section 17.1's argument singles out the one with the smallest energy denominator: generically, this is the gap between one molecule's HOMO and the other's LUMO, since the HOMO is (by definition) the highest-lying occupied level and the LUMO the lowest-lying unoccupied one — the smallest gap achievable between an occupied and an unoccupied orbital across the whole pair of molecules, assuming the relevant overlap integrals are not anomalously small for that particular pairing (a real caveat, returned to in Section 17.15).
> **Status of the principle: HOMO–LUMO dominance**
> *Approximate.* It follows from Section 17.1's perturbation sum only under the assumption that overlap magnitudes are roughly comparable across candidate orbital pairs, so that the energy denominator alone selects the dominant term; Section 17.15 catalogues where this assumption breaks down.

---

## 17.5 Charge-controlled versus orbital-controlled reactions

**A second term in the same expansion.** Section 17.1's perturbative energy is not the whole interaction energy between two approaching molecules; a classical electrostatic (Coulombic) term, from each molecule's net atomic charges (computable, for instance, from the LCAO coefficients and bond orders already introduced in Section 12.5) interacting with the other molecule's charge distribution, adds separately and does not depend on any orbital energy gap at all.

**Two limiting regimes.** When the frontier-orbital energy gap (Section 17.4) is small, the orbital (covalent) term can dominate the total interaction — an **orbital-controlled** reaction, whose outcome (which site reacts, how fast) is best predicted from HOMO/LUMO shapes and energies. When the gap is large, the orbital term is suppressed (Section 17.1's denominator is large), and the electrostatic term — governed simply by which atoms carry the largest partial charges — dominates instead: a **charge-controlled** reaction, predictable from a simpler electrostatic picture with no need to invoke frontier orbitals at all. Real reactions sit somewhere on a continuum between these two limits, foreshadowing the hardness-based classification of Section 17.14.
> **Status of the principle: charge control versus orbital control**
> *Derived*, as the recognition that the total interaction energy between two approaching species has (at minimum) two additive contributions — one orbital, one electrostatic — of comparable but not generally equal size.

---

## 17.6 Nucleophiles

**Definition, now quantitative.** A nucleophile is a species with a relatively high-energy HOMO (equivalently, by Section 17.2, a relatively low ionization energy): its electrons are loosely enough bound to be donated readily into a partner's low-lying unoccupied orbital. Amines, thiolates, and alkoxides are strong nucleophiles because their lone-pair HOMOs sit at comparatively high orbital energy — a statement now traceable to an actual computed number (Section 17.2), not merely a qualitative label.
> **Status of the principle: nucleophilicity as HOMO energy**
> *Approximate*, inheriting directly the Koopmans'-theorem approximation of Section 17.2, and further limited by Section 17.5's observation that a strong nucleophile in the orbital-control sense need not be a strong nucleophile in the charge-control sense (or in solution, where solvation, Section 14.13, substantially modifies the effective donating power).

---

## 17.7 Electrophiles

**Definition.** An electrophile has a relatively low-energy LUMO (a relatively high electron affinity, Section 17.3): it accepts electron density readily. Carbonyl carbons, protonated species, and many metal cations are strong electrophiles because their relevant unoccupied orbital sits at comparatively low energy.
> **Status of the principle: electrophilicity as LUMO energy**
> *Approximate*, inheriting the weaker of the two Koopmans' approximations (Section 17.3), and subject to the same charge-versus-orbital caveat as Section 17.6.

---

## 17.8 Electronegativity

**A finite-difference definition, not a qualitative one.** Section 8.16 introduced electronegativity qualitatively, as an atom's "tendency to attract electrons," without a precise formula. Mulliken's definition supplies one directly from the two quantities already derived in Sections 17.2–17.3:

$$
\chi=\frac{I+A}{2}
$$

the average of the energy cost of removing an electron and the energy gained by adding one — a single number summarizing an atom's or fragment's overall electron-attracting tendency, built entirely from ionization energy and electron affinity, both already meaningful, measurable quantities since Chapter 8.
> **Status of the principle: Mulliken electronegativity**
> *Derived*, as a specific, motivated combination of the ionization energy and electron affinity already established in Chapter 8; the motivation for precisely this combination (rather than some other average) is completed in Section 17.9.

---

## 17.9 Chemical potential

**Electronegativity as a derivative.** Consider the total electronic energy $E$ as a function of the (in principle continuous) number of electrons $N$, at fixed nuclear positions — the same $E(N)$ whose formal justification is the Hohenberg–Kohn theorem of Section 14.10 (electron number, like electron density, is a legitimate variable of the energy functional). Its first derivative,

$$
\mu=\left(\frac{\partial E}{\partial N}\right)_{v(\mathbf r)}
$$

is the **electronic chemical potential** — the energy cost of adding an infinitesimal amount of electron density. Because $N$ can only change by whole electrons in reality, $\mu$ is estimated by a finite difference using $E(N_0+1)=E(N_0)-A$ and $E(N_0-1)=E(N_0)+I$ (Sections 17.2–17.3's definitions restated), giving

$$
\mu\approx-\frac{I+A}{2}=-\chi
$$

**This completes Section 17.8's motivation**: Mulliken electronegativity is, up to a sign, exactly the electronic chemical potential — the same combination of $I$ and $A$ appears because both are estimating the same underlying derivative. A species with high $\chi$ (low $\mu$) lowers its energy by *accepting* electron density from a partner with lower $\chi$ (higher $\mu$); electron flow between two approaching species, in this picture, runs from high $\mu$ to low $\mu$, precisely analogous to how heat flows from high to low temperature.

**A notational note.** This $\mu$, a per-electron quantity, is not the thermodynamic chemical potential $\mu$ of Section 15.13 (a per-mole-of-molecules quantity); the two share a name and a defining idea — the derivative of an energy-like quantity with respect to a particle number — but operate on different particles (electrons here, whole molecules there) and are not interchangeable.
> **Status of the principle: chemical potential as (minus) electronegativity**
> *Derived*, given the finite-difference approximation to $\partial E/\partial N$; the approximation's accuracy is bounded by the same Koopmans'-theorem limitations already flagged in Sections 17.2–17.3.

---

## 17.10 Hardness and softness

**The second derivative.** Continuing the Taylor expansion of $E(N)$ begun in Section 17.9, the second derivative is the **chemical hardness**,

$$
\eta=\left(\frac{\partial^2E}{\partial N^2}\right)_{v(\mathbf r)}\approx I-A
$$

(again by finite difference, using the same three energies as Section 17.9). $\eta$ measures how sharply the energy rises as electron number is pushed away from its equilibrium value — equivalently, how large the HOMO–LUMO gap is, since $I-A\approx\varepsilon_{\rm LUMO}-\varepsilon_{\rm HOMO}$ by Sections 17.2–17.3's Koopmans' identifications.

**Physical reading.** A **hard** species (large $\eta$, large HOMO–LUMO gap) strongly resists any change in its electron distribution — its energy rises steeply if electron density is pushed onto or pulled off it — and, by Section 17.5's logic, tends toward charge-controlled behavior, since the orbital term of its interactions is suppressed by the large denominator. A **soft** species (small $\eta$, small gap) has a more polarizable, more readily perturbed electron distribution and tends toward orbital-controlled behavior, exactly the regime where Section 17.4's frontier-orbital argument is strongest.
> **Status of the principle: chemical hardness**
> *Derived*, as the second term of the same finite-difference expansion that produced Section 17.9's chemical potential; its size is fixed almost entirely by the HOMO–LUMO gap of Sections 17.2–17.3.

---

## 17.11 Conceptual DFT

**Naming the whole framework.** Sections 17.9–17.10 are the first two terms of a general expansion,

$$
E(N)=E(N_0)+\mu\,\Delta N+\tfrac12\eta\,(\Delta N)^2+\cdots
$$

rooted formally in the density-functional theory of Section 14.10: because the Hohenberg–Kohn theorem establishes $E$ as a well-defined functional of the electron density (and, through it, of $N$ and the external potential $v(\mathbf r)$ set by the nuclei), *every* derivative of $E$ with respect to $N$ or $v(\mathbf r)$ is, in principle, a legitimate, well-defined physical quantity. **Conceptual DFT** is the systematic study of this family of derivatives as chemical reactivity descriptors — $\mu$ and $\eta$ being the two lowest-order, *global* (whole-molecule) members. Section 17.12 introduces the analogous *local* (position-resolved) member, needed to answer not just "will this molecule react readily" but "at which atom."
> **Status of the principle: conceptual DFT as a systematic expansion**
> *Derived*, as a direct organizational consequence of the Hohenberg–Kohn theorem (Section 14.10) applied to electron-number derivatives rather than only to the ground-state energy itself.

---

## 17.12 Fukui functions

**Making Section 17.9's derivative local.** Rather than asking how the *total* energy responds to a change in electron number, ask how the electron *density at each point in space* responds:

$$
f(\mathbf r)=\left(\frac{\partial\rho(\mathbf r)}{\partial N}\right)_{v(\mathbf r)}
$$

the **Fukui function**. Two finite-difference versions matter: $f^{+}(\mathbf r)$, approximated by the frontier LUMO density $\lvert\psi_{\rm LUMO}(\mathbf r)\rvert^2$ (the density added when an electron arrives, so the relevant descriptor for attack by a nucleophile), and $f^{-}(\mathbf r)$, approximated by the HOMO density $\lvert\psi_{\rm HOMO}(\mathbf r)\rvert^2$ (the density removed when an electron leaves, relevant for attack by an electrophile) — the spatial refinement of exactly the HOMO/LUMO logic of Sections 17.2–17.3, now telling *where on the molecule* rather than only *whether*.

**Worked example, using coefficients already verified in Chapter 12.** The allyl cation's two $\pi$ electrons occupy only the lowest bonding orbital, so its LUMO is the nonbonding orbital derived in Section 12.5, with coefficients $(1/\sqrt2,\,0,\,-1/\sqrt2)$ on carbons 1, 2, 3. The condensed Fukui function for nucleophilic attack, $f_r^{+}\propto c_{{\rm LUMO},r}^2$, is therefore $\left(\tfrac12,\,0,\,\tfrac12\right)$: **exactly zero at the central carbon**, predicting that a nucleophile attacks an allyl cation only at the terminal carbons, never at the center — precisely the outcome organic chemistry observes, now derived from the same Hückel coefficients already computed and checked in Section 12.5, rather than stated as a memorized regiochemical rule.
> **Status of the principle: Fukui functions from frontier-orbital densities**
> *Approximate*, inheriting the same finite-difference and Koopmans'-theorem approximations as Sections 17.2–17.3, restricted further (in the worked example) to the Hückel-level orbital picture of Chapter 12, itself already flagged with the specific limitations of Section 12.7.

---

## 17.13 Dual descriptor

**One function instead of two.** Some sites on a molecule are susceptible to attack by *either* a nucleophile or an electrophile depending on conditions (**ambident** reactivity, as in an enolate, reactive at both oxygen and carbon). The **dual descriptor**,

$$
\Delta f(\mathbf r)=f^{+}(\mathbf r)-f^{-}(\mathbf r)
$$

combines both susceptibilities into a single signed function: $\Delta f(\mathbf r)>0$ marks a site favorable to nucleophilic attack (LUMO character dominates there), $\Delta f(\mathbf r)<0$ marks a site favorable to electrophilic attack (HOMO character dominates), and the sign can, in principle, differ from atom to atom on the same molecule — directly predicting site-selective, condition-dependent reactivity from one calculation rather than two separate, potentially inconsistent ones.
> **Status of the principle: the dual descriptor**
> *Derived*, as a direct combination of the two Fukui functions of Section 17.12, carrying forward exactly their approximations.

---

## 17.14 HSAB

**The principle.** The **hard–soft acid–base (HSAB) principle** states that hard acids (electron acceptors) preferentially bind hard bases (electron donors), and soft acids preferentially bind soft bases — F$^-$ (hard) coordinates strongly to Al$^{3+}$ (hard) but only weakly to soft metal centers, while I$^-$ (soft) does the reverse.

**Derived, not merely catalogued.** This follows directly from Sections 17.5 and 17.10. A hard–hard pairing has a large combined HOMO–LUMO-type gap (Section 17.10: high $\eta$ on both sides), suppressing the orbital term (Section 17.4's denominator is large) and leaving the interaction charge-controlled (Section 17.5) — well served by the strong, localized electrostatic attraction between two small, non-polarizable, high-charge-density species, exactly what "hard" species are. A soft–soft pairing has a small combined gap, so the orbital term (Section 17.4's stabilization, inversely proportional to that gap) can become large — an orbital-controlled interaction, favored when both partners are large, diffuse, and polarizable, exactly the character of "soft" species. **A hard–soft mismatch is unfavorable because neither mechanism operates efficiently**: the gap is neither small enough for strong orbital stabilization nor is the electrostatic term reinforced by comparable charge densities on both sides.
> **Status of the principle: the HSAB principle**
> *Derived*, as a direct qualitative consequence of Sections 17.4–17.5 and 17.10, though it remains a classification scheme rather than a quantitative predictive formula — a molecule's designation as "hard" or "soft" is a matter of degree, not a binary label, and borderline cases are common.

---

## 17.15 Limits of orbital-based reaction explanations

**This chapter's central caution, stated explicitly.** Frontier molecular orbital theory is a genuinely useful, and genuinely derived (Section 17.1), approximation — but it is an approximation with specific, nameable failure modes, not a new fundamental law standing alongside the theorems of earlier chapters, and it must not be treated as one.

- **It is a truncated sum.** Section 17.1's perturbation series has many terms; frontier orbital theory keeps only the smallest-denominator one. When two or more orbital pairings have comparable denominators — common whenever a molecule has several closely spaced occupied or unoccupied orbitals — the HOMO–LUMO term alone can badly mispredict both reactivity and regioselectivity, and the full sum (or a direct computation, Chapter 14) is needed.
- **The overlap can be small precisely where the gap is smallest.** Section 17.4's argument assumed comparable overlap magnitudes across candidate pairings; symmetry (Chapter 11's vanishing theorem, extended here to an intermolecular interaction) can force the overlap integral for the nominal HOMO–LUMO pair to be small or zero even when the energy gap favors it, in which case a formally "less favorable" pairing dominates in practice.
- **Koopmans' theorem is an approximation with an uneven error.** Sections 17.2–17.3 already flagged that the LUMO/electron-affinity identification is markedly less reliable than the HOMO/ionization-energy one; any conclusion drawn primarily from LUMO energies (electrophilicity, Section 17.7; $f^{+}$, Section 17.12) inherits a correspondingly larger uncertainty than one drawn from HOMO energies.
- **Sterics, solvation, and dynamics are entirely absent.** Nothing in this chapter's machinery accounts for steric hindrance blocking an otherwise orbital-favored approach, for the solvent reorganization energy of Section 14.13, or for the dynamical, multidimensional character of the actual reaction path (Chapter 16) — a frontier-orbital argument identifies an electronic *tendency*, not a computed barrier height.
- **Charge control versus orbital control is a spectrum, not a switch.** Section 17.5 already noted this; treating every reaction as cleanly one or the other, rather than checking which term of the underlying sum actually dominates for the specific case at hand, is the single most common misuse of this entire chapter's framework.

**What this chapter has actually shown.** Frontier orbital theory correctly identifies the *leading term* of a well-defined perturbative expansion, and every quantitative index built from it (Sections 17.8–17.13) is traceable to that same leading-order approximation. It is powerful because that leading term is often genuinely dominant, and it fails, predictably and explainably, exactly where it is not — the same lesson stated at the end of every approximation introduced in this book: **there are no arbitrary exceptions, only approximations with domains of validity**, and knowing this chapter's domain is what makes it useful rather than misleading.
> **Status of the principle: the reliability of frontier-orbital reasoning**
> *Approximate*, by construction: every reactivity index derived in this chapter is the leading-order term of a perturbative expansion (Section 17.1) evaluated with an additional Koopmans'-theorem approximation (Sections 17.2–17.3), and its predictive value is exactly as good as those two approximations are for the specific reaction under consideration.

---

## What remains unexplained

| Open question                                                                                       | Where it is resolved |
| ---------------------------------------------------------------------------------------------------- | --------------------- |
| How does the *symmetry* (not just the energy) of frontier orbitals decide whether a concerted reaction pathway is even geometrically allowed? | Chapter 18            |
| How do the qualitative orbital-control/charge-control ideas of this chapter connect to the actual, quantitatively computed barrier heights of Chapter 16? | Chapter 14 and Chapter 16, taken together |
| How does a catalyst change the effective HOMO/LUMO energies or gaps available to a reaction?          | Chapter 20            |
| How do these frontier-orbital arguments extend to specific, named organic mechanisms (nucleophilic substitution, addition, elimination)? | Chapter 19            |

**Next:** Chapter 18 adds what this chapter deliberately left out — orbital *symmetry*, not just orbital energy — to explain why some concerted reactions proceed readily under thermal conditions while their apparent photochemical counterparts require light, and vice versa.
