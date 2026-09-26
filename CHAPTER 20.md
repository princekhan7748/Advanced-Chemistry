# Chapter 20 — Catalysis, Intermolecular Forces and Advanced Case Studies

*Part II — From Quantum States to Chemical Behavior*

## Opening question

Two facts look unrelated. First: a platinum surface makes hydrogenation of an alkene run millions of times faster at room temperature, yet the equilibrium mixture of alkane and alkene is exactly what it would have been without the platinum. Second: liquid argon condenses into a solid at 84 K even though a single argon atom has no permanent dipole, no lone pair, and no empty orbital for anything to donate into. What is a catalyst actually allowed to change, and what is it strictly forbidden from changing? And if argon has no charge separation at all, where does the attraction that binds solid argon together come from?

Both questions have the same kind of answer. Nothing new is postulated in this chapter. A catalyst's action is read off the potential-energy surface and transition-state theory built in Chapter 16. The attraction between closed-shell atoms is read off the perturbation theory of Chapter 9 applied to two separated systems. This chapter's job is to take that existing machinery and point it, section by section, at catalysis and at every non-bonded interaction that holds condensed matter and biological structure together.

### Roadmap: mathematical result → chemical destination

| Mathematical result | Chemical destination |
|---|---|
| Eyring equation, $\Delta G^\ddagger$ (Ch. 16) | Why a catalyst changes rate but not $K_{eq}$ |
| Crystal/ligand field splitting of $d$ orbitals (Ch. 8, 11) | Transition-metal catalytic cycles |
| Second-order perturbation energy $E^{(2)}=\sum_n \dfrac{\lvert\langle 0\rvert \hat V\rvert n\rangle\rvert^2}{E_0-E_n}$ (Ch. 9) | London dispersion, induction |
| Polarizability $\alpha$ from the Stark effect (Sec. 6.13) | Dispersion strength, $\pi$-stacking, solvent screening |
| Coulomb's law with dielectric screening | Hydrogen bonding, ion pairing, solvent effects |
| Transition-state stabilization energy | Enzyme rate enhancement |

---

## 20.1 What a catalyst actually changes

A rate constant is set by the height of a barrier, not by the depths of the wells on either side of it. From Chapter 16,

$$
k = \frac{k_BT}{h}\exp\!\left(-\frac{\Delta G^\ddagger}{RT}\right).
$$

A catalyst supplies an alternative reaction path — usually one with several smaller barriers rather than a single tall one — with a lower $\Delta G^\ddagger$ on every step. Because the equilibrium constant depends only on the free-energy difference between reactants and products,

$$
K_{eq} = \exp\!\left(-\frac{\Delta G^\circ_{rxn}}{RT}\right),
$$

and this quantity contains no reference to any intermediate state, a species that appears and is regenerated unchanged along the path (the definition of a catalyst) cannot appear in $\Delta G^\circ_{rxn}$. It therefore cannot shift $K_{eq}$.

> **Status of the principle: catalysts do not change equilibrium constants**
> *Derived.* This follows directly from the fact that $K_{eq}$ is a function of state (reactant and product free energies only), while a catalytic rate enhancement is a statement about the path connecting them. No new physics is needed — only the observation that $\Delta G^\ddagger$ and $\Delta G^\circ_{rxn}$ are logically independent quantities.

## 20.2 Catalytic potential-energy surfaces

An uncatalyzed reaction can be represented as a single hill on the potential-energy surface of Chapter 16. A catalytic cycle replaces that hill with a sequence of smaller hills, each corresponding to a bond-forming or bond-breaking step at the catalyst (adsorption, migratory insertion, reductive elimination, and so on), separated by intermediate minima corresponding to catalyst-bound species. The rate of the overall cycle is controlled by whichever step has the highest-lying transition state relative to the resting state of the catalyst — the turnover-limiting step — not by the sum of the individual barriers. This is the same logic already used for multistep mechanisms in Chapter 16; nothing new is added except that some of the "reactants" are now catalyst-bound intermediates rather than free molecules.

## 20.3 Acid–base catalysis

The simplest catalytic strategy is to change which species crosses the transition state. Protonating a carbonyl oxygen, for example, converts a poor electrophile (C=O) into a much better one (C=OH$^+$) by lowering the energy of the LUMO that a nucleophile must attack (Chapter 17). General acid catalysis achieves the same stabilization partway, through a hydrogen bond to the developing negative charge in the transition state, without full proton transfer.

The empirical Brønsted relation connects the rate constant of a family of related acid- or base-catalyzed reactions to the strength of the catalyzing acid or base,

$$
\log k = \alpha \log K_a + C,
$$

with $0<\alpha<1$ measuring how far proton transfer has progressed by the transition state.

> **Status of the principle: Brønsted catalysis law**
> *Empirical.* It is a linear free-energy relationship fitted across a reaction series; $\alpha$ is a useful transition-state diagnostic (an early or late transition state) rather than a quantity derived from first principles.

## 20.4 Transition-metal catalysis

Transition-metal catalysts do their work with $d$ orbitals, and the splitting of those orbitals is exactly the point-group problem of Chapter 11 applied to the atomic orbitals of Chapter 8. Six ligands arranged octahedrally around a metal ion split the five degenerate $d$ orbitals, by symmetry, into a doubly degenerate $e_g$ set (pointing at the ligands) and a triply degenerate $t_{2g}$ set (pointing between them), with $e_g$ higher in energy because those lobes overlap more strongly with ligand electron density.

$$
\Delta_{oct} = E(e_g) - E(t_{2g}).
$$

The simplest version of this picture (crystal field theory) treats the ligands as point charges and predicts the splitting from electrostatics alone. Real ligand-field splittings, however, depend on covalent metal–ligand orbital overlap and on whether a ligand is a $\pi$-donor or $\pi$-acceptor, which crystal field electrostatics cannot capture.

> **Status of the principle: $d$-orbital splitting pattern**
> *Approximate.* The qualitative ordering and degeneracy pattern follow rigorously from the point-group symmetry of the ligand arrangement (Chapter 11) and are therefore reliable. The magnitude of $\Delta_{oct}$, and its ordering along the spectrochemical series, requires the covalent, MO-based ligand-field treatment; the point-charge crystal-field model gets the pattern right and the number wrong.

With this splitting in hand, the elementary steps of a catalytic cycle become orbital-symmetry statements rather than isolated rules to memorize:

- **Oxidative addition** breaks an X–Y bond across a metal center, formally raising the metal's oxidation state by two and its $d$-electron count correspondingly; it requires a filled metal orbital of the right symmetry to donate into the X–Y $\sigma^*$ orbital, exactly the donor–acceptor language of Chapter 17.
- **Reductive elimination** is its microscopic reverse: two cis ligands couple and depart, re-forming a bond and restoring the lower oxidation state.
- **Migratory insertion** moves a ligand from the metal into a bond with an adjacent coordinated group (commonly alkene into M–H or M–C), converting a $\pi$-coordinated species into a $\sigma$-bonded one through a four-centered transition state.
- **$\beta$-hydride elimination** is migratory insertion's reverse: an agostic C–H bond on the carbon $\beta$ to the metal aligns with an empty metal orbital, and the hydride transfers to the metal as an alkene is released.

None of these four steps is an independent rule; each is orbital overlap and electron counting applied to the $d$-orbital manifold set up above.

## 20.5 Hydrogen bonding

A hydrogen bond, D–H$\cdots$A, is not simply a strong dipole–dipole interaction, and it is not a covalent bond either. Its energetics come from two contributions treated by ordinary perturbation theory (Chapter 9) applied to the interaction between the D–H bond and a lone pair on A: an electrostatic term from the permanent dipole created by the polarized D–H bond, and a smaller but non-negligible charge-transfer (donor–acceptor) term in which the lone pair on A donates partial electron density into the D–H $\sigma^*$ antibonding orbital, weakening and lengthening that bond. The characteristic infrared red-shift of the D–H stretch on hydrogen-bond formation is direct evidence for this second, orbital-mixing contribution; a purely electrostatic interaction would not populate an antibonding orbital.

Bond strengths range from roughly 5 to 30 kJ mol$^{-1}$ for weak hydrogen bonds (C–H$\cdots$O) up to 150 kJ mol$^{-1}$ or more for the strongest examples (F–H$\cdots$F$^-$), where the charge-transfer contribution becomes comparable to a genuine partial covalent bond.

> **Status of the principle: hydrogen bonding is electrostatic plus charge transfer**
> *Approximate.* The electrostatic part follows directly from Coulomb's law (Fundamental) applied to the bond dipole; the charge-transfer part is a second-order perturbative correction (Derived, Chapter 9). Which term dominates is system-dependent, so no single fixed ratio of the two contributions can be quoted as if it were universal.

## 20.6 Van der Waals interactions

"Van der Waals interaction" is an umbrella term for three physically distinct contributions to the interaction energy between two closed-shell species, all of which fall off with some power of separation and all of which come from applying perturbation theory to two non-overlapping charge distributions:

1. **Keesom (orientation) energy** — the interaction between two permanent dipoles, averaged over thermal rotation, giving an attractive $-C/r^6$ term.
2. **Debye (induction) energy** — a permanent dipole on one molecule polarizing the other, again $-C/r^6$, with the coefficient set by the permanent dipole moment and the partner's polarizability $\alpha$.
3. **London (dispersion) energy** — present even between two species with zero permanent dipole, treated in the next section.

All three share the same distance dependence because all three arise from a dipole–dipole-type interaction operator inserted into the same second-order perturbation formula; they differ only in what generates the dipoles.

## 20.7 Dispersion

Take two hydrogen atoms, or two argon atoms, far enough apart that their electron clouds do not overlap. Classically there is no interaction: each atom, time-averaged, is spherically symmetric and has zero dipole moment. Quantum mechanically this is not the whole story, because the electron distribution at any instant is not static — it fluctuates, and the instantaneous dipole on one atom polarizes the other, inducing a correlated instantaneous dipole that lowers the energy of the pair.

Treating the dipole–dipole coupling between two atoms as a perturbation and applying the second-order expression from Chapter 9,

$$
E^{(2)} = -\sum_{n\neq 0}\frac{\lvert\langle 0\rvert \hat V\rvert n\rangle\rvert^2}{E_n-E_0},
$$

with $\hat V$ the dipole–dipole operator connecting the ground state to excited states of the atom pair, gives the London dispersion formula,

$$
E_{disp}(r) \approx -\frac{3}{2}\,\frac{\alpha_1\alpha_2}{r^6}\,\frac{I_1 I_2}{I_1+I_2},
$$

where $\alpha_1,\alpha_2$ are the atomic polarizabilities already introduced through the Stark effect in Section 6.13, and $I_1,I_2$ are the atoms' ionization energies. Dispersion is always attractive (a second-order energy is always negative), grows with polarizability, and requires no permanent charge separation on either partner.

> **Status of the principle: London dispersion**
> *Derived.* It follows from ordinary quantum-mechanical second-order perturbation theory applied to two atoms with fluctuating charge densities; nothing beyond the machinery of Chapter 9 and the polarizability already defined in Chapter 6 is required. It has no classical counterpart: a classical charge distribution with zero average dipole exerts zero average force on a distant neutral partner.

At short range, where electron clouds begin to overlap, the Pauli exclusion principle of Chapter 7 forces electrons into higher-energy orbitals to avoid double occupancy, producing a steep repulsive wall. The combination of $-1/r^6$ attraction and a short-range repulsive wall is the physical content behind empirical potential forms such as the Lennard-Jones potential; the attractive exponent is derived, the repulsive exponent is a convenient fit.

## 20.8 $\pi$-stacking

Two aromatic rings stacked face to face are commonly described as attracting through their $\pi$ electron clouds, but a $\pi$ system is more polarizable than a comparable $\sigma$ system precisely because its electrons are more delocalized — which means $\pi$-stacking is, quantitatively, dominated by the dispersion mechanism of Section 20.7, enhanced by the larger polarizability of a delocalized $\pi$ cloud. A separate electrostatic contribution comes from the quadrupole moment of an aromatic ring (a negative charge above and below the ring plane, positive charge in the plane at the periphery from the C–H bonds), which by itself would favor a face-to-face geometry but disfavor perfect eclipsing, and which correctly predicts the commonly observed offset-parallel and edge-to-face stacking geometries.

> **Status of the principle: $\pi$-stacking is dispersion-dominated**
> *Approximate.* The dominant attractive term is London dispersion (Derived, from 20.7); the geometric preferences are set by a secondary electrostatic quadrupole–quadrupole term. Describing $\pi$-stacking as arising from direct $\pi$-orbital "donation" between rings is not supported by the energetics and should not be treated as a separate mechanism.

## 20.9 Solvent effects

Every electrostatic interaction derived so far — hydrogen bonding, ion pairing, dipole–dipole forces — assumed the two interacting partners in vacuum. Immersing them in a solvent of dielectric constant $\varepsilon$ screens Coulomb's law,

$$
V(r) = \frac{q_1q_2}{4\pi\varepsilon_0\varepsilon r},
$$

weakening electrostatic interactions by a factor of $\varepsilon$ (roughly 80 for water, close to 2 for hexane). This single substitution explains why an ion pair that is essentially undissociated in a nonpolar solvent dissociates freely in water, and why hydrogen bonds to solute molecules are readily outcompeted by hydrogen bonds to bulk water.

Because a polar transition state is stabilized more than a nonpolar one by a polar solvent (and a solvent that must reorganize to solvate a developing charge costs entropy), solvent polarity systematically shifts the rates of ionic mechanisms relative to concerted ones — the empirical Hughes–Ingold rules for $S_N1$ versus $S_N2$ pathways (Chapter 19) are a direct consequence of this screening and reorganization cost, not an independent rule about substitution reactions.

## 20.10 Supramolecular chemistry

Supramolecular assemblies — host–guest complexes, molecular capsules, self-assembled cages — are held together by nothing beyond the interactions already derived in this chapter: hydrogen bonding, electrostatics, dispersion, and $\pi$-stacking, acting simultaneously and cooperatively. The distinctive feature of supramolecular chemistry is not a new force but multivalency: many individually weak (a few kJ mol$^{-1}$) contacts acting in parallel can sum to a binding free energy comparable to a covalent bond, provided the host and guest are geometrically preorganized so that all contacts can form simultaneously without an unfavorable entropic or strain penalty. Preorganization — paying the conformational entropy cost once, during synthesis, rather than at every binding event — is the single largest lever available for increasing binding affinity built from weak interactions.

## 20.11 Enzyme catalysis

An enzyme is, in the language of Chapter 16, a device that lowers $\Delta G^\ddagger$ for one specific reaction by stabilizing the transition state more than it stabilizes the ground state. Four contributions, each already derived elsewhere in this chapter or earlier in the book, combine to do this:

- **Electrostatic transition-state stabilization**: the active site is preorganized (its polar groups and bound water are already oriented) to solvate the charge distribution of the transition state, which is normally more polarized than the ground state — the same electrostatic screening logic as Section 20.9, but with the "solvent" prearranged in advance rather than reorganizing on the fly, avoiding the reorganization free-energy penalty a fully flexible polar solvent would pay.
- **Proximity and orientation**: binding reactants in a fixed relative geometry converts an unfavorable intermolecular entropy loss (which would otherwise be paid at every collision in solution) into a one-time binding event, effectively raising the local concentration and correct orientation of reacting groups.
- **General acid–base catalysis**: active-site residues (histidine, aspartate, and others) donate or accept protons exactly as in Section 20.3, lowering the barrier for proton-transfer steps.
- **Quantum-mechanical tunneling of the transferring proton or hydride**, made significant by the low mass of hydrogen and its zero-point energy (Chapter 5), can further increase the effective rate beyond what classical transition-state theory alone predicts — the same zero-point-energy physics already used for the kinetic isotope effect promised in Chapter 16.

> **Status of the principle: mechanism of enzymatic rate enhancement**
> *Approximate.* That catalysis works by lowering $\Delta G^\ddagger$ without shifting $K_{eq}$ is Derived (Section 20.1); that transition-state electrostatic stabilization is typically the largest single contributor is well supported for many enzymes but is a conclusion from case-by-case computational and mutagenesis studies, not a universal law. The relative size of the four contributions above varies from one enzyme to the next.

---

## What remains unexplained

| Open question | Chapter that resolves it |
|---|---|
| Which specific bonds break and form in named organic and enzymatic mechanisms, worked through explicitly | 21 (Case studies) |
| Why the same orbital-symmetry logic used for oxidative addition also governs pericyclic reactions | 18 (already derived); connected explicitly in 21 |
| How large a rate enhancement any specific catalyst gives, quantitatively | 14 (computational chemistry, already covered) applied case by case |

**Next:** Chapter 21 takes twelve concrete chemical phenomena — including why catalysts accelerate reactions (Case 10) and why hydrogen bonding exists (Case 7) — and reconstructs each one, without new physics, entirely from the machinery assembled across Chapters 1 through 20.
