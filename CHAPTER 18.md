# Chapter 18 — Orbital Symmetry and Pericyclic Reactions

*Part II · From Quantum States to Chemical Behavior*

Chapter 17 deliberately worked with orbital *energies* — HOMO, LUMO, and the gaps between them — while treating orbital shape only qualitatively, as "large coefficient here, small coefficient there." One class of reaction cannot be understood that way at all. Heating 3,4-dimethylcyclobutene opens the ring to a diene with one defined stereochemical outcome; irradiating the same reaction with light gives, cleanly, the *opposite* stereochemical outcome. No change in energy supplied — heat versus light — should reverse which enantiomer or diastereomer forms, if the only thing that mattered were how much energy was available to cross a barrier. Something else is being conserved.

The opening question:
> **In a concerted reaction where bonds break and form simultaneously around a ring, with no intermediate ever formed, why does thermal activation and photochemical activation produce systematically opposite stereochemical outcomes — for some ring sizes but not others?**

**What "concerted" and "pericyclic" mean here, precisely.** A **pericyclic** reaction is one that proceeds through a single, cyclic transition state, with all bond reorganization happening at once around a ring of atoms — no stepwise mechanism, no discrete intermediate (Section 16.5) ever formed. This chapter's entire argument rests on a single physical fact already derived in Chapter 11: **orbitals of different symmetry cannot mix** (Section 11.7's vanishing theorem). Applied not just at one fixed geometry but continuously along an entire reaction path, this becomes a powerful constraint — and, as this chapter shows, a strict alternation with electron count and with thermal-versus-photochemical activation, derived rather than tabulated.

| Mathematical result                                                | Chemical destination                                                          |
| ---------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| The non-crossing rule of Section 11.7, extended along a reaction path  | Orbital correlation diagrams: which reactant orbital becomes which product orbital |
| Ground-state configuration correlating to an excited-state configuration | A symmetry-imposed barrier: the thermal reaction is "forbidden" in the frontier-orbital sense |
| Sign pattern of the terminal Hückel coefficients (Chapter 12)          | Conrotatory versus disrotatory ring closure, derived from already-computed numbers |
| Simultaneous phase-matching at two separate termini                    | Suprafacial cycloaddition allowedness ($[4+2]$ versus $[2+2]$)                |
| Eigenvalues of a ring matrix with one sign-inverted coupling (a topological twist) | The Hückel/Möbius unification of every rule in this chapter into one electron-counting principle |

**Roadmap.** The core principle and its diagrammatic tool (18.1–18.2) → why light inverts the outcome (18.3) → three concrete reaction classes, derived from Chapter 12's already-verified coefficients (18.4–18.6) → the topological unification (18.7) → the Woodward–Hoffmann rules, presented as a conclusion rather than a table (18.8).

---

## 18.1 Conservation of orbital symmetry

**Extending a known result along a path.** Section 11.7 established that two orbitals of different symmetry cannot interact at any single, fixed molecular geometry, because their coupling matrix element vanishes by symmetry. Now let the nuclei move continuously along a reaction coordinate (Section 16.6) that happens to preserve some symmetry element throughout — a mirror plane, or a rotation axis, present at every point along the path, not only at the reactant and product geometries. At every such point, the electronic Hamiltonian still commutes with that surviving symmetry operation (the argument of Section 11.1, applied instant by instant), so every molecular orbital along the path can still be labeled by its symmetry with respect to that element, and orbitals of different symmetry still cannot mix.

**The consequence: orbitals must correlate.** Because the symmetry label of each orbital cannot change discontinuously as the nuclei move smoothly, each reactant orbital must connect, as energy is tracked continuously along the path, to exactly one product orbital carrying the *same* symmetry label — never to one of different symmetry, since that would require two orbitals of different symmetry to cross, which Section 11.7's non-crossing rule already forbids for orbitals of the *same* symmetry (which repel) while explicitly *permitting* it for orbitals of different symmetry (which may cross freely, precisely because they never interact). This one-to-one, symmetry-preserving connection is what Section 18.2 organizes into a diagram.
> **Status of the principle: conservation of orbital symmetry along a reaction path**
> *Derived*, as a direct extension of the non-crossing rule already established in Section 11.7 from a single geometry to a continuous path that preserves some symmetry element throughout.

---

## 18.2 Correlation diagrams

**Construction.** A **correlation diagram** plots the energy of every relevant molecular orbital as a function of position along the reaction coordinate, from reactant geometry to product geometry, with each reactant orbital's line drawn connecting to the product orbital of matching symmetry (Section 18.1) — never to a product orbital of different symmetry, and never crossing the line of another orbital of the *same* symmetry along the way (Section 11.7's repulsion between same-symmetry levels, exactly as invoked for avoided crossings in Section 11.7's original context).

**Reading the diagram.** If every orbital *occupied* in the reactant's ground state correlates to an orbital *occupied* in the product's ground state, the reactant's ground electronic configuration connects smoothly, without an intervening energy spike, to the product's ground electronic configuration: the reaction is **symmetry-allowed** for the thermal (ground-state) pathway. If, instead, the symmetry-forced correlation connects an occupied reactant orbital to an orbital that is *unoccupied* in the product's ground state (and, correspondingly, forces some reactant unoccupied orbital to correlate down to a product occupied one), then following the ground-state configuration along the path leads not to the product's ground state but to one of its *excited* configurations — a substantial extra energy cost with no name other than "symmetry," since nothing about bond strengths or sterics forces it. The reaction is **symmetry-forbidden** for the thermal pathway, meaning not literally impossible, but forced either through a much higher-energy pathway or through an entirely different (non-concerted, stepwise) mechanism that never preserves the relevant symmetry element in the first place.
> **Status of the principle: correlation diagrams**
> *Derived*, as a direct diagrammatic restatement of Section 18.1; the classification into "allowed" and "forbidden" that a diagram produces is exact within the approximation that some symmetry element truly is preserved throughout an idealized concerted path (Section 18.3 examines what changes when it is not the ground configuration being followed).

---

## 18.3 Thermal versus photochemical reactions

**What light changes.** Section 13.9's electronic spectroscopy showed that absorbing a photon promotes an electron from an occupied orbital (typically the HOMO) to an unoccupied one (typically the LUMO), producing a new electronic configuration entirely — not more energy in the same configuration, but a *different* configuration, with a different occupied-orbital set.

**Why the selection rule inverts.** Section 18.2's correlation diagram is built entirely from *which* orbitals are occupied. Promoting an electron from HOMO to LUMO changes exactly that: an orbital that was empty (and therefore free to correlate, without penalty, to whatever product orbital symmetry demanded) is now occupied, and vice versa for the vacated HOMO. A correlation that was forbidden for the ground configuration — forcing an occupied orbital to correlate to an empty one — can become perfectly allowed for the *excited* configuration, if the newly occupied orbital happens to correlate to a product orbital that is itself occupied in the corresponding product excited state (or, after the excited-state system relaxes, funnels efficiently toward a stereochemical outcome set by that excited-state correlation before returning to the ground state). This is the mechanism, and not merely the coincidence, behind thermal and photochemical pericyclic reactions of the same overall transformation giving systematically opposite stereochemical outcomes: **the same physical principle (Section 18.1) applied to two different electronic configurations necessarily gives two different answers.**
> **Status of the principle: inversion of allowedness under photoexcitation**
> *Derived*, as the direct consequence of applying Section 18.1's symmetry-correlation argument to an electronically excited configuration instead of the ground configuration.

---

## 18.4 Electrocyclic reactions: conrotatory and disrotatory closure

**The geometric question.** An electrocyclic ring closure — butadiene to cyclobutene, or hexatriene to cyclohexadiene — forms one new $\sigma$ bond between the two terminal carbons of an open conjugated chain, by rotating each terminal $p$ orbital until its lobes point toward the other terminus. Two limiting motions preserve a symmetry element throughout the whole rotation (Section 18.1's requirement): **disrotatory** closure (the two termini rotate in opposite senses, preserving a mirror plane bisecting the molecule throughout) and **conrotatory** closure (the two termini rotate in the same sense, preserving a $C_2$ axis throughout instead). Which one a given system prefers is decided entirely by which one brings same-sign lobes together at the new bond — because only a same-sign (bonding, constructive) overlap lowers the energy as the new $\sigma$ bond forms; a closure that brings opposite-sign lobes together produces a node in the new bond and is strongly disfavored.

**Reading off the answer from already-computed coefficients.** Section 12.3 derived the $\pi$ molecular orbital coefficients of a linear polyene chain, $c_{k,r}\propto\sin(kr\pi/(N+1))$, and verified them numerically. For **butadiene** ($N=4$, four $\pi$ electrons filling $k=1,2$), the HOMO ($k=2$) has coefficients $(0.6015,\,0.3717,\,-0.3717,\,-0.6015)$: the two termini, C1 and C4, carry **opposite-sign** lobes. Bringing opposite-sign lobes into constructive (same-sign-to-same-sign) contact requires rotating the two termini in the *same* rotational sense — **conrotatory** closure — since only that motion can flip one terminus's exposed face to match the other's without passing through a symmetric (mirror-preserving) intermediate that would instead force the lobes into destructive contact.

**The photochemical inversion, read from the same table.** Promoting an electron (Section 18.3) empties the HOMO and populates the LUMO ($k=3$), whose coefficients are $(0.6015,\,-0.3717,\,-0.3717,\,0.6015)$: the termini now carry **same-sign** lobes. Bringing same-sign lobes into constructive contact requires the opposite motion — **disrotatory** closure. **Butadiene's thermal ring closure is conrotatory and its photochemical ring closure is disrotatory**, a result now derived directly from the same Hückel coefficients checked numerically in Section 12.3, not asserted as a memorized rule.

**Hexatriene, and the alternation.** Repeating the identical calculation for hexatriene ($N=6$, six $\pi$ electrons filling $k=1,2,3$) gives a HOMO ($k=3$) with coefficients $(0.5211,\,0.2319,\,-0.4179,\,-0.4179,\,0.2319,\,0.5211)$ — **same-sign** termini — requiring **disrotatory** thermal closure, and a LUMO ($k=4$) with **opposite-sign** termini, requiring **conrotatory** photochemical closure: the exact reverse pattern from butadiene. **Every additional pair of $\pi$ electrons in the chain flips the terminal sign pattern**, because each successive $k$ adds one more sign change (one more node) across the chain (Section 12.3's node-counting), and this single observation is what Section 18.7 generalizes into one electron-counting rule covering every reaction in this chapter.
> **Status of the principle: conrotatory/disrotatory selectivity in electrocyclic reactions**
> *Derived*, directly from the sign pattern of the terminal LCAO coefficients already computed in Section 12.3, combined with the requirement (Section 18.1) that the closure motion preserve constructive overlap at the forming bond.

---

## 18.5 Cycloadditions

**A different geometric question, the same tool.** A cycloaddition joins two separate $\pi$ systems at two new $\sigma$ bonds simultaneously, with each component approaching the other **suprafacially** (using the same face of its own $\pi$ system at both of its termini) in the most common geometry. Whether a thermal, ground-state, doubly-suprafacial approach is allowed depends on whether both new bonds can be simultaneously bonding — that is, whether the sign pattern of one component's frontier orbital matches the other's at *both* termini at once, exactly the same phase-matching logic as Section 18.4, now applied across two separate molecules' termini rather than within one molecule's ends.

**The Diels–Alder reaction, $[4+2]$.** Pairing the diene's HOMO with the dienophile's LUMO (Section 17.4's frontier-orbital dominance argument, now applied to a specific, geometrically explicit case): butadiene's HOMO has termini of opposite sign, $(+,-)$ (Section 18.4), and ethylene's LUMO — from Section 12.3's $N=2$ formula, coefficients $(0.7071,\,-0.7071)$ — also has termini of opposite sign, $(+,-)$. Overlapping the diene's C1 with one ethylene carbon and the diene's C4 with the other, a suprafacial–suprafacial approach brings a $(+,-)$ pattern into register with a $(+,-)$ pattern at *both* new bonds simultaneously: both are bonding at once. **The thermal Diels–Alder cycloaddition is doubly-suprafacial-allowed**, consistent with its well-known readiness to proceed thermally, with no light required.

**The $[2+2]$ cycloaddition.** Pairing one ethylene's HOMO, coefficients $(0.7071,\,0.7071)$ (same sign, Section 12.3's $k=1$), with a second ethylene's LUMO, coefficients $(0.7071,\,-0.7071)$ (opposite sign, $k=2$): one terminus pair can be brought into constructive overlap, but the same-sign HOMO and opposite-sign LUMO cannot simultaneously match at *both* termini in a suprafacial–suprafacial geometry — whichever end is made bonding, the other is necessarily antibonding. **The thermal, doubly-suprafacial $[2+2]$ cycloaddition of two alkenes is symmetry-forbidden**, matching the long-standing observation that simple alkenes do not thermally dimerize this way, while $[2+2]$ cycloadditions proceed readily *photochemically* (Section 18.3's inversion: exciting one component swaps its HOMO for its LUMO, restoring a matched same-sign/opposite-sign pairing at both termini simultaneously) — exactly the pattern seen in the laboratory.
> **Status of the principle: suprafacial cycloaddition allowedness**
> *Derived*, using the same terminal-sign-matching argument as Section 18.4, together with the frontier-orbital pairing already established in Chapter 17.

---

## 18.6 Sigmatropic rearrangements

**A third geometry, the same electron-counting logic.** A sigmatropic rearrangement migrates a $\sigma$ bond across an adjacent, conjugated $\pi$ system — for instance, a $[1,5]$-hydrogen shift along a pentadienyl framework, or a $[1,3]$-hydrogen shift along an allyl framework — while the migrating group can travel either **suprafacially** (staying on the same face of the $\pi$ system throughout) or **antarafacially** (switching to the opposite face partway through). The identical correlation-diagram logic of Sections 18.1–18.2 applies once the migrating atom's orbital is included alongside the $\pi$ system's orbitals in the full symmetry analysis, and it produces the identical electron-counting pattern already found for electrocyclic reactions and cycloadditions: a $[1,5]$-shift (six electrons in the full cyclic array of orbitals involved, counting the migrating bond) is thermally allowed suprafacially, matching the disrotatory-type (untwisted) pattern of hexatriene's six-electron electrocyclization (Section 18.4); a $[1,3]$-shift (four electrons) is thermally forbidden suprafacially and requires either the geometrically awkward antarafacial pathway or photochemical activation, matching butadiene's four-electron, twisted-pathway pattern. Section 18.7 makes the reason for this recurring four-versus-six electron split explicit and general.
> **Status of the principle: suprafacial/antarafacial selectivity in sigmatropic shifts**
> *Derived*, by the same correlation-diagram logic as Sections 18.1–18.5, applied to the extended orbital array that includes the migrating group; worked out here only qualitatively, in the interest of not re-deriving the full Hückel-coefficient calculation a third time.

---

## 18.7 Hückel and Möbius transition states

**A single topological idea unifying Sections 18.4–18.6.** Consider the cyclic array of $p$ orbitals present at the transition state of any pericyclic reaction, regardless of which specific reaction class it belongs to. Two topologically distinct arrangements are possible: an ordinary, untwisted ring, where following the orbitals all the way around returns to the starting phase with **zero** sign inversions (**Hückel topology** — the same topology already used, and its electron-counting rule already derived, for the aromatic rings of Section 12.4) — or a ring with a single half-twist built into the connectivity, so that following the orbitals around introduces exactly **one** sign inversion before closing (**Möbius topology**, named for the one-sided surface with the same topological structure).

**The eigenvalue problem, and its inverted electron count.** A Möbius-topology ring is described by exactly the same Hückel ring matrix as Section 12.4's ordinary ring, except that the single "wraparound" coupling element carries a flipped sign (representing the one phase inversion). Diagonalizing this modified matrix for $N=4$ gives eigenvalues $x=+1.414,+1.414,-1.414,-1.414$ — **no** nondegenerate level at the top, in sharp contrast to Section 12.4's ordinary ring, whose $N=4$ eigenvalues $x=2,0,0,-2$ left the middle pair only half-fillable with four electrons. Filling this Möbius $N=4$ system with four electrons **exactly closes the top degenerate pair** — a closed shell, stabilized, exactly analogous to Section 12.4's $4n+2$ result but achieved here with only $4$ electrons, because the Möbius twist inverts which electron count produces a closed shell. Repeating for $N=6$: the ordinary Hückel ring closes a shell at six electrons (Section 12.4's benzene result), while the Möbius $N=6$ ring, with eigenvalues $1.732,1.732,0,0,-1.732,-1.732$, leaves a degenerate pair only half-filled at six electrons — an open shell, destabilized.

**The rule, stated once and for all.** A **Möbius-topology transition state is stabilized ("aromatic") for $4n$ electrons** and destabilized for $4n+2$; an ordinary **Hückel-topology transition state is stabilized for $4n+2$ electrons** (Section 12.4's original result) and destabilized for $4n$. Every result of Sections 18.4–18.6 is this single statement in disguise: conrotatory electrocyclic closure introduces exactly the kind of half-twist that defines a Möbius array, and butadiene's four thermally-conrotatory electrons are precisely the $4n$ case favoring that topology; disrotatory closure keeps the array untwisted (Hückel topology), and hexatriene's six thermally-disrotatory electrons are precisely the $4n+2$ case favoring *that* topology instead. The Diels–Alder transition state (six electrons, untwisted, doubly-suprafacial) is the $4n+2$/Hückel case; the forbidden thermal $[2+2]$ (four electrons, untwisted) is the $4n$/Hückel case — stabilized only if it *could* twist into a Möbius array, which a simple, small four-membered ring geometrically cannot do without severe strain.
> **Status of the principle: the Hückel–Möbius unification**
> *Derived*, as a direct extension of Section 12.4's ring-eigenvalue argument to a topologically twisted ring, verified numerically for $N=4$ and $N=6$; it reproduces every case-by-case result of Sections 18.4–18.6 as a single $4n$-versus-$4n+2$, Möbius-versus-Hückel electron-counting statement.

---

## 18.8 The Woodward–Hoffmann rules

**A conclusion, not a starting point.** Stated first, "the Woodward–Hoffmann rules" would be one more set of selection rules to memorize, indistinguishable in kind from any arbitrary chemical mnemonic. Stated last, having derived every piece — Section 18.1's symmetry conservation, Section 18.2's correlation diagrams, Section 18.3's photochemical inversion, and Section 18.7's topological electron count, each checked case by case against coefficients already computed and verified in Chapter 12 — they are a single, compact summary of results already established:

$$
\boxed{
\begin{array}{ll}
\text{Thermal, ground-state reaction:} & (4n+2)\text{ electrons} \Rightarrow \text{Hückel (untwisted) topology favored}\\
& (4n)\text{ electrons} \Rightarrow \text{Möbius (twisted) topology favored}\\[4pt]
\text{Photochemical, excited-state reaction:} & \text{the above two rules invert (Section 18.3)}
\end{array}
}
$$

For an electrocyclic reaction, "untwisted" means disrotatory and "twisted" means conrotatory; for a cycloaddition, "untwisted" means (both components) suprafacial; for a sigmatropic shift, "untwisted" means suprafacial migration. The specific geometric vocabulary changes from one reaction class to the next; the underlying electron count and topology do not.

**What this chapter has actually shown.** Every rule stated here traces back to Section 11.7's vanishing theorem — orbitals of different symmetry do not mix — applied consistently along a full reaction path rather than at a single geometry, and checked, wherever possible, against the specific numerical coefficients already computed in Chapter 12. Nothing in this chapter introduced a new physical principle beyond that one, extended and applied.
> **Status of the principle: the Woodward–Hoffmann rules**
> *Derived*, as the compact synthesis of Sections 18.1–18.7; the underlying non-crossing/symmetry-conservation principle (Section 11.7) is itself *Derived*, so nothing in the final boxed statement rests on an unexplained empirical foundation.

---

## What remains unexplained

| Open question                                                                                  | Where it is resolved |
| --------------------------------------------------------------------------------------------------| --------------------- |
| How do these idealized, symmetry-preserving pathways connect to the actual computed transition-state geometries and barrier heights of Chapter 14? | Chapter 14 (in combination with this chapter's qualitative predictions) |
| What happens when no symmetry element is preserved at all along the lowest-energy path — do these rules simply not apply, or is there a generalized version? | Not developed in this book; the frontier-orbital reasoning of Chapter 17 remains applicable even without strict symmetry |
| How do these concerted, single-transition-state reactions fit alongside the stepwise, multi-intermediate mechanisms of ordinary organic chemistry? | Chapter 19            |
| Can a catalyst change which topology (Hückel or Möbius) is accessible, altering which electron count reacts fastest? | Chapter 20            |

**Next:** Chapter 19 turns from this chapter's specialized, highly symmetric concerted reactions to the stepwise mechanisms that make up the bulk of ordinary organic chemistry — substitution, elimination, and addition — building each one from the same frontier-orbital and electronic-structure principles established in Chapters 9 through 18, now applied without the luxury of a single, symmetry-preserving transition state to lean on.
