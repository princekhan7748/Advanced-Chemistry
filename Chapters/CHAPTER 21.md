# Chapter 21 — Chemistry Without Memorization: Complete Derivations

*Part III — Chemistry Derived: Case Studies*

## Opening question

Twenty chapters have built a single chain: quantum mechanics, quantum statistics, many-electron atoms, molecular orbitals, symmetry, spectroscopy, thermodynamics, potential-energy surfaces, and the electronic origin of reactivity. A textbook chemistry course hands the student twelve of its most memorized facts as flat statements — carbon is tetravalent, benzene is aromatic, $S_N2$ inverts configuration, and so on — without showing where any of them come from. The test of everything built so far is simple: can each of these twelve facts be reconstructed, in full, from material already derived, with no new postulate introduced anywhere in this chapter?

That is the only task here. Nothing below is a new physical law. Every derivation is a specific application of a general result from an earlier chapter to a specific chemical fact.

### Roadmap: fact reconstructed → chapters supplying the machinery

| Case | Fact | Machinery used |
|---|---|---|
| 1 | Carbon forms four bonds | Ch. 8 (configuration), Ch. 10 (hybridization as representation) |
| 2 | Benzene is aromatic | Ch. 3 (particle in a ring), Ch. 12 (Hückel, $4n+2$) |
| 3 | $S_N2$ gives inversion | Ch. 10 (MO nodal structure), Ch. 17 (frontier orbitals), Ch. 19 |
| 4 | Diels–Alder works thermally | Ch. 11 (symmetry), Ch. 18 (Woodward–Hoffmann) |
| 5 | Some metals are colored | Ch. 8 (many-electron atoms), Ch. 11 ($d$-orbital splitting), Ch. 13 |
| 6 | Transition metals show unusual magnetism | Ch. 7 (spin, exchange), Ch. 8 (Hund's rule), Ch. 11 |
| 7 | Hydrogen bonding exists | Ch. 9 (perturbation theory), Ch. 20 |
| 8 | Some reactions are spontaneous but slow | Ch. 15 (thermodynamics) vs Ch. 16 (kinetics) |
| 9 | Some reactions are fast but unfavorable | Ch. 16 (TST), Ch. 15 ($K_{eq}$) |
| 10 | Catalysts accelerate reactions | Ch. 16, Ch. 20 |
| 11 | Periodic trends exist | Ch. 8 (shielding, penetration, $Z_{eff}$) |
| 12 | "Exceptions" occur | Ch. 8, Ch. 9 (limits of every approximation used) |

---

## 21.1 Case 1 — Why carbon forms four bonds

Carbon's ground-state configuration is $1s^2 2s^2 2p^2$ (Chapter 8), with only two unpaired electrons in separate $2p$ orbitals. A naive reading of valence as "number of unpaired electrons" predicts divalent carbon. Promoting one $2s$ electron to the empty $2p_z$ orbital costs a well-defined promotion energy, but yields four singly occupied orbitals ($2s^1\,2p_x^1\,2p_y^1\,2p_z^1$) available for four separate bonds instead of two. Whether promotion is worthwhile is a question about total bond energy, not about counting unpaired electrons: four bonds, each releasing energy on formation, more than repay the one-time promotion cost, while forming only two bonds would not repay it. The four resulting bonds are then not four different types of orbital — they are four equivalent combinations of $2s,2p_x,2p_y,2p_z$, i.e. the $sp^3$ hybrids introduced in Chapter 10 as a mathematical rotation of the occupied orbital set, chosen because that particular linear combination maximizes directional overlap with four ligands in a tetrahedral arrangement.

> **Status of the principle: carbon's tetravalence**
> *Derived.* The $s\to p$ promotion energy is a calculable atomic quantity (Chapter 8); the conclusion that four bonds outweigh the promotion cost is an energetic comparison, not a postulate. The $sp^3$ description itself is *Approximate* in the sense defined in Chapter 10 — a representation of the occupied orbitals, not evidence that four physically distinct hybrid orbitals exist prior to bond formation.

## 21.2 Case 2 — Why benzene is aromatic

Benzene's six $2p_z$ orbitals form a closed ring, mathematically the same boundary-value problem as the particle on a ring already solved in Chapter 3 (periodic boundary conditions, $\psi(\phi+2\pi)=\psi(\phi)$), giving energy levels in degenerate pairs above a single lowest level. Filling the six $\pi$ electrons into the Hückel molecular orbitals derived in Chapter 12 places two electrons in the lowest orbital and four in the next degenerate pair, exactly filling every bonding orbital and leaving every antibonding orbital empty — a closed-shell, maximally stabilized configuration. Counting electrons that achieves this "all bonding orbitals filled, all antibonding orbitals empty" condition for a cyclic, fully conjugated, planar system of $N$ $p_z$ orbitals occurs whenever the electron count is $4n+2$; for benzene, $n=1$.

> **Status of the principle: Hückel $4n+2$ rule**
> *Approximate.* It is a specific consequence of the simplified Hückel model (Chapter 12: nearest-neighbor overlap only, no explicit electron repulsion) applied to a particular geometry (planar, cyclic, equal bond lengths). The underlying electron-counting logic — filled bonding, empty antibonding — is *Derived* from the particle-on-a-ring solution; the numerical value "$4n+2$" is a property of that specific approximate model, not an independent law of nature.

## 21.3 Case 3 — Why $S_N2$ gives inversion

The nucleophile in an $S_N2$ reaction attacks along the extension of the C–leaving-group axis because that is the only geometry in which its donor orbital (a lone pair) has the correct nodal overlap with the empty $\sigma^*_{C-LG}$ acceptor orbital — the frontier-orbital argument of Chapter 17. The $\sigma^*$ orbital has its largest lobe directly opposite the leaving group, and any other angle of attack gives poorer overlap and a higher-energy transition state. Because bonding electron density is being simultaneously withdrawn from the front (into the leaving group) and built up at the back (from the nucleophile), the three remaining substituents flatten toward a planar arrangement at the transition state and then complete their motion to the opposite side, inverting the configuration at carbon — the same nodal-overlap argument already applied to this exact reaction in Chapter 19.

> **Status of the principle: backside attack and Walden inversion**
> *Derived.* It follows from the shape and symmetry of the $\sigma^*$ acceptor orbital (Chapter 10, Chapter 17), not from a separate steric or electrostatic rule; steric hindrance to backside attack (from bulky substituents) is a real, separate effect that modulates the *rate* of this pathway but is not what determines its *stereochemical outcome*.

## 21.4 Case 4 — Why Diels–Alder works thermally

The Diels–Alder cycloaddition combines a diene HOMO with a dienophile LUMO (or vice versa). Constructing a correlation diagram (Chapter 18) for the suprafacial–suprafacial approach shows that the symmetry of every occupied orbital of the diene–dienophile pair correlates smoothly, without crossing, to an occupied orbital of the cyclohexene product. Because no filled reactant orbital must cross to become an empty product orbital, the ground-state (thermal) reaction proceeds with a modest activation barrier through an allowed pathway. The alternative, purely antarafacial mode is geometrically strained for a six-membered transition state and is not the operative pathway here, unlike the photochemical cycloadditions and sigmatropic shifts of Chapter 18, where light first promotes an electron to change which orbital symmetry set is being conserved, flipping which geometric mode is now allowed.

> **Status of the principle: thermal Diels–Alder is symmetry-allowed**
> *Derived.* It is a direct application of the orbital-symmetry conservation argument of Chapter 18 to this specific pair of $\pi$ systems in the suprafacial–suprafacial geometry; no separate "Diels–Alder rule" is required once the general correlation-diagram method is available.

## 21.5 Case 5 — Why some metals are colored

An octahedral or tetrahedral ligand field splits the five $d$ orbitals of a transition-metal ion into two sets separated by $\Delta_{oct}$ (or $\Delta_{tet}$), derived in Chapter 20 from the point-group symmetry of Chapter 11. If the ion has a partially filled $d$ shell, an electron can be promoted from the lower set to the upper set by absorbing a photon of energy $h\nu=\Delta$, exactly the transition-probability and selection-rule machinery of Chapter 13. Because $\Delta$ for most first-row transition-metal complexes falls in the range corresponding to visible-light photon energies (roughly 1.5–3 eV), these complexes absorb specific visible wavelengths and appear colored in the complementary color; a $d^0$ or $d^{10}$ ion has no partially filled shell to promote an electron within, no available $d$–$d$ transition, and is typically colorless (or colored only through a separate charge-transfer transition).

> **Status of the principle: $d$–$d$ transitions and color**
> *Derived.* Given the $d$-orbital splitting (itself Approximate, Chapter 20) and the general absorption formalism of Chapter 13, the prediction that partially filled $d$-shell complexes absorb in the visible follows directly; predicting the specific absorbed wavelength for a given metal and ligand set requires the numerical value of $\Delta$, which is where the approximate nature of the splitting model reenters.

## 21.6 Case 6 — Why transition metals have unusual magnetic properties

Hund's rule, derived in Chapter 8 from the exchange interaction between same-spin electrons, favors maximally parallel spin filling of degenerate orbitals. In a free ion the five $d$ orbitals are degenerate and this maximizes total spin straightforwardly. In a ligand field the $d$ orbitals split into two sets separated by $\Delta$ (Chapter 20), and now two filling strategies compete: pay the exchange-energy cost of pairing electrons in the lower set (low-spin) or pay the orbital-energy cost $\Delta$ of promoting an electron to the upper set to keep spins parallel (high-spin). Which strategy wins is a direct energetic comparison between the pairing energy $P$ (from Hund's exchange term) and $\Delta$ (from the ligand field): weak-field ligands (small $\Delta$) give high-spin complexes; strong-field ligands (large $\Delta$) give low-spin complexes. The resulting number of unpaired electrons sets the paramagnetic moment measured experimentally.

> **Status of the principle: high-spin/low-spin crossover**
> *Derived*, as a competition between two already-derived quantities ($P$ from Chapter 8's exchange interaction, $\Delta$ from Chapter 20's ligand field), not as an independent magnetic rule. The direction of the crossover for a specific metal–ligand pair is an *Empirical* input (the spectrochemical series ranks ligands by $\Delta$ without yet deriving that ranking from first principles).

## 21.7 Case 7 — Why hydrogen bonding exists

This case was fully derived already, in Chapter 20, Section 20.5: an electrostatic term from the D–H bond dipole (Coulomb's law, Fundamental) plus a second-order perturbative charge-transfer term in which a lone pair on the acceptor donates into the D–H $\sigma^*$ orbital (Chapter 9). It is repeated in this list only because it is exactly the kind of fact — quoted in introductory courses as a bare rule about "electronegative atoms" — that this book is built to eliminate as an unexplained exception.

## 21.8 Case 8 — Why some reactions are spontaneous but slow

Spontaneity is a statement about $\Delta G^\circ_{rxn}$ (Chapter 15): whether the products lie lower in free energy than the reactants at equilibrium. Rate is a statement about $\Delta G^\ddagger$ (Chapter 16): how high the barrier is between them. These two quantities are computed from entirely different parts of the potential-energy surface — one from the endpoints, one from the point in between — and nothing links their magnitudes. The conversion of diamond to graphite is thermodynamically favorable ($\Delta G^\circ_{rxn}<0$) yet has such a high activation barrier that diamond persists indefinitely at room temperature: a textbook case of large negative $\Delta G^\circ_{rxn}$ with large positive $\Delta G^\ddagger$.

> **Status of the principle: thermodynamic favorability is independent of rate**
> *Derived.* $\Delta G^\circ_{rxn}$ and $\Delta G^\ddagger$ are computed from different points on the same potential-energy surface (Chapter 16); no general relationship forces one to track the other, though for closely related reaction series an empirical correlation between them (a Brønsted–Evans–Polanyi relationship) is often observed.

## 21.9 Case 9 — Why some reactions are fast but unfavorable

This is the mirror image of Case 8: a small $\Delta G^\ddagger$ permits a fast approach to equilibrium, but $\Delta G^\circ_{rxn}>0$ means that equilibrium lies toward reactants. A reaction can therefore reach its unfavorable equilibrium position rapidly (proton transfers between many acids and bases are diffusion-limited in either direction) precisely because both directions of the equilibrium share the same, low-lying transition state; the position of equilibrium and the speed of approaching it are, again, set by different features of the same surface (Chapters 15 and 16).

## 21.10 Case 10 — Why catalysts accelerate reactions

Fully derived in Chapter 20, Section 20.1: a catalyst supplies an alternate path with lower $\Delta G^\ddagger$ at every step while leaving $\Delta G^\circ_{rxn}$, and therefore $K_{eq}$, untouched, because $K_{eq}$ depends only on the free energies of reactants and products and a catalyst is regenerated unchanged.

## 21.11 Case 11 — Why periodic trends exist

Atomic size, ionization energy, electron affinity and electronegativity are all set by the same two competing effects derived in Chapter 8: the effective nuclear charge $Z_{eff}=Z-\sigma$ felt by a valence electron (increasing left to right across a period as shielding from added electrons in the same shell is imperfect) and the principal quantum number $n$ of the valence shell (increasing down a group, placing the valence electron in a larger, more diffuse orbital with weaker binding). Ionization energy and electronegativity increase with $Z_{eff}$ and decrease with $n$; atomic radius does the opposite. Every standard periodic trend is this same pair of competing quantities, evaluated for a different observable.

> **Status of the principle: periodic trends from $Z_{eff}$ and $n$**
> *Derived*, from the shielding and penetration arguments of Chapter 8, themselves *Approximate* (the central-field approximation to the true many-electron Hamiltonian). This is why periodic trends are reliable in overall direction but routinely show local irregularities — see Case 12.

## 21.12 Case 12 — Why "exceptions" occur

Every fact reconstructed above rested on an explicitly stated approximation: the central-field approximation for many-electron atoms (Chapter 8), the neglect of explicit electron repulsion in Hückel theory (Chapter 12), the point-charge or simple orbital-overlap treatment of ligand fields (Chapter 20), the assumption of a single dominant reaction coordinate in transition-state theory (Chapter 16). An "exception" to a rule built on one of these chapters is not a violation of quantum mechanics; it is a case where the neglected term (electron–electron repulsion beyond the mean field, spin–orbit coupling, relativistic contraction in a heavy element, a second competing reaction pathway) is no longer small enough to ignore. The anomalous stability of a half-filled or fully filled $d$ subshell (an exchange-energy effect, Chapter 8) breaking the naive Aufbau filling order for chromium and copper is the standard example: it is not an exception to any fundamental law, only a case where an approximation (fill orbitals strictly by energy, ignore exchange stabilization) was pushed past the point where it remains a good approximation.

> **Status of the principle: exceptions signal a breaking approximation, not a broken law**
> *Fundamental*, in the sense that it follows directly from the definition of an approximation set out in Chapter 9: every simplified model in this book was built by discarding a specific, named term from an exact Hamiltonian, and any case where that discarded term becomes non-negligible will appear, from inside the simplified model, as an unexplained exception.

---

## What remains unexplained

| Open question | Chapter that resolves it |
|---|---|
| A single compressed statement of how all twelve cases, and the twenty chapters behind them, fit into one picture | 22 |

**Next:** Chapter 22 compresses the entire book — quantum mechanics through reaction mechanisms — into a single map, and restates the manifesto this chapter was built to demonstrate: there are no arbitrary exceptions, only approximations with domains of validity.
