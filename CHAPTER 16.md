# Chapter 16 — Potential-Energy Surfaces and Chemical Reactions

*Part II · From Quantum States to Chemical Behavior*

Chapter 15 answered where a reaction ends up: the equilibrium constant, built entirely from molecular partition functions, tells us the ratio of products to reactants once nothing changes anymore. It says nothing about how long that takes. A reaction with a hugely favorable equilibrium constant can sit unreacted for years (diamond does not spontaneously become graphite on any human timescale, despite graphite being lower in energy); a reaction with a barely favorable one can be over in microseconds. Chapter 14 separately gave the tools to locate a transition state (Section 14.14) and compute its vibrational frequencies (Section 14.15). This chapter fuses the two: the geometric object of Chapter 14 and the statistical machinery of Chapter 15, combined, produce a rate.

The opening question:
> **Given a potential-energy surface with a reactant valley and a product valley separated by a mountain pass (Chapter 14's transition state), what determines how quickly a molecule crosses it — and why does that rate depend on temperature in the specific way chemists have measured for over a century?**

**Two questions the chapter keeps carefully apart.** Chapter 15 answers "how favorable" (thermodynamics, $\Delta G$). This chapter answers "how fast" (kinetics, a rate constant $k$). The two are independent numbers, computed from overlapping but distinct machinery, and Section 16.12 states explicitly why a favorable $\Delta G$ guarantees nothing about speed.

| Mathematical result                                                | Chemical destination                                                        |
| ---------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| The single negative eigenvalue of the Hessian at a saddle point (Ch. 14) | The reaction coordinate: the one direction along which the transition state is unstable |
| Quasi-equilibrium between reactants and the activated complex, using Ch. 15's equilibrium-constant machinery | Transition-state theory: a rate built from an equilibrium constant and a crossing frequency |
| The universal frequency factor $k_BT/h$                              | Why the transition-state-theory rate has a clean, temperature-dependent prefactor with no adjustable parameters |
| $\Delta G^{\ddagger}=\Delta H^{\ddagger}-T\Delta S^{\ddagger}$ applied to the activated complex | The Eyring equation; the physical content behind the empirical Arrhenius parameters $A$ and $E_a$ |
| Zero-point energy (Ch. 5.5) present in the reactant but absent along the reaction coordinate at the transition state | The kinetic isotope effect, quantified                                     |
| Two harmonic curves (reactant, product) crossing at a point that shifts with their relative energy | The Hammond postulate, derived rather than asserted                        |

**Roadmap.** Reframing the objects of Chapter 14 as the stage for a reaction (16.1–16.6) → defining what is to be explained (16.7–16.8) → deriving a rate constant from first principles (16.9–16.11) → what the result does and does not say (16.12–16.14).

---

## 16.1 Reactants and products as quantum states

**Nothing new, a new use.** Chapter 9's electronic structure and Chapter 14's computational machinery already produce, for any fixed nuclear geometry, a well-defined quantum state with a definite energy. A "reactant" and a "product" are not qualitatively different kinds of object from anything built since Chapter 9 — they are simply two different regions of the same potential-energy surface (Section 14.2), each a stable arrangement of the same electrons and nuclei. What Chapters 1–15 built was the machinery to describe *a* molecule; this chapter is about the path *between* two such descriptions.
> **Status of the principle: reactants and products as points on one surface**
> *Derived*, as a direct restatement of the Born–Oppenheimer potential-energy surface already established in Section 14.2, with no new physical assumption.

---

## 16.2 Potential-energy surfaces, revisited

**The stage.** Section 14.2 introduced $E(\{R_A\})$ as the object every computational method targets. For this chapter, the *shape* of that surface — not just its value at isolated stationary points — is what matters: a reaction is a trajectory across the surface, and the question of rate is a question about the geometry of the path connecting two valleys, and about how much of that geometry the surface's height and curvature (Section 14.3's gradient and Hessian) force upon it.

**A minimal picture.** For a single-step reaction, the relevant slice of the surface can be idealized as one dimension, the reaction coordinate (Section 16.6): a valley (reactant), a rise to a mountain pass (transition state), and a descent to a second valley (product) — the object every subsequent section in this chapter refers to as "the" reaction profile.
> **Status of the principle: the reaction profile as a one-dimensional slice**
> *Approximate.* A real PES has $3M-6$ dimensions (Section 14.2); reducing it to a single reaction coordinate is a simplification, exact only along the true minimum-energy path (Section 16.6) and only to the extent that motion perpendicular to that path can be neglected or averaged over.

---

## 16.3 Minima

**Reactants, products, and nothing in between — yet.** A minimum of the PES (Section 14.3: all Hessian eigenvalues positive) is a geometry stable against any small nuclear displacement. Both reactant and product are minima of the same surface; nothing in the mathematics of Section 14.3 distinguishes "reactant" from "product" except which side of the highest point in between it lies on, and by convention, which state is present before the reaction is considered to have occurred.
> **Status of the principle: reactant and product minima**
> *Derived*, as a direct application of Section 14.3's stationary-point classification.

---

## 16.4 Transition states

**The mountain pass, precisely defined.** The transition state is the first-order saddle point of Section 14.3: a maximum along exactly one direction and a minimum along every other. Physically, it is the highest-energy point along the *lowest*-energy path connecting the reactant and product valleys — the path a system takes if it is to cross between them at the smallest possible energetic cost, not the highest point of every conceivable path (a system could, in principle, cross an arbitrarily high ridge elsewhere on the surface, but essentially no population does so, for the same Boltzmann-weighting reason developed in Section 15.3).

**Not a molecule you can bottle.** Unlike a minimum, the transition state has zero lifetime along the reaction coordinate: any infinitesimal displacement along the single negative-curvature direction rolls the system downhill, toward either reactant or product, with no restoring force to hold it there. This is the structural reason a transition state cannot be isolated or observed directly by the equilibrium spectroscopic methods of Chapter 13 (which require a state stable enough to populate and probe), and can only be inferred — from kinetics (this chapter) or from computation (Section 14.14).
> **Status of the principle: the transition state as a first-order saddle point**
> *Derived*, as the chemical interpretation of the mathematical classification already established in Section 14.3.

---

## 16.5 Intermediates

**A crucial distinction.** A multi-step reaction crosses more than one transition state, passing through one or more additional minima along the way — **intermediates**. Unlike the transition state (Section 16.4), an intermediate sits in a genuine local minimum of the PES: it has a finite (however short) lifetime, a well-defined structure, and can in principle — and sometimes in practice, for a long-lived enough intermediate — be observed by the spectroscopic methods of Chapter 13. The distinction is not one of degree but of the mathematics of Section 14.3: an intermediate has all positive Hessian eigenvalues; a transition state has exactly one negative eigenvalue. No structure is ever "almost" a transition state in this classification — it is one or the other.
> **Status of the principle: intermediates versus transition states**
> *Derived*, as a sharpened restatement of Section 14.3's stationary-point classification applied to a multi-step reaction profile.

---

## 16.6 Reaction coordinates

**Locally, an eigenvector; globally, a path.** At the transition state itself, the reaction coordinate is, precisely, the eigenvector of the Hessian (Section 14.3) belonging to the single negative eigenvalue — the one direction of instability. Away from the transition state, the reaction coordinate is generalized to the full **minimum-energy path**: the trajectory obtained by following steepest descent away from the transition state in both directions (Section 14.14's intrinsic reaction coordinate), tracing out the actual lowest-energy route connecting reactant and product valleys. Every subsequent section's "one-dimensional profile" (Section 16.2) is, properly, energy plotted against distance along this specific path, not against any arbitrarily chosen internal coordinate.
> **Status of the principle: the reaction coordinate**
> *Derived* at the transition state itself, from the Hessian eigenvector of Section 14.3; the extension to a full minimum-energy path is the *Approximate* one-dimensional reduction already flagged in Section 16.2.

---

## 16.7 Activation energy

**Definition, with a quantum correction already available.** The (electronic) barrier height is $E^{\ddagger}=E(\text{transition state})-E(\text{reactant})$, computed directly from Chapter 14's methods. But neither the reactant nor the transition state actually sits at the bottom of its electronic energy well: both carry zero-point vibrational energy (Section 5.5), and Section 14.15 already showed how to compute it for any stationary point. The activation energy that governs an actual rate is therefore

$$
E_a=\left[E^{\ddagger}+\text{ZPE}^{\ddagger}\right]-\left[E_R+\text{ZPE}_R\right]
$$

with $\text{ZPE}^{\ddagger}$ computed only over the *bound* vibrational modes of the transition state — the reaction coordinate itself, being the direction of instability (Section 16.4), contributes no zero-point energy of its own and does not enter this sum. This omission is the seed of Section 16.10's kinetic isotope effect.
> **Status of the principle: zero-point-corrected activation energy**
> *Derived*, as the direct combination of Chapter 14's computed electronic barrier and Section 5.5's zero-point energy, applied to a transition state's bound modes only.

---

## 16.8 Reaction kinetics

**The phenomenological starting point.** Before any first-principles derivation, a rate law is an empirical, macroscopic statement: for a reaction $A+B\to\text{products}$, the observed rate often (not always — this is itself an approximation whose validity is checked experimentally) follows $\text{rate}=k[A]^m[B]^n$, with $k$ the **rate constant** and $m,n$ determined experimentally, not necessarily equal to the reaction's stoichiometric coefficients. This is not a law derived from anything in this book; it is the empirical object every remaining section works to explain, in the same sense that Chapter 1's Balmer formula was an empirical object Chapter 6 eventually derived.
> **Status of the principle: empirical rate laws**
> *Empirical.* The functional form, and the values of $m,n$, are determined by experiment; Sections 16.9–16.11 derive $k$ itself, not the form of the rate law as a whole, which depends on the specific reaction mechanism.

---

## 16.9 Transition-state theory

**The central idea: a quasi-equilibrium.** Assume the reactants and the transition-state structures are in equilibrium with each other, even though the overall reaction is not (a genuine approximation, examined below): a small, constantly-replenished population of systems sits transiently at the geometry of the transition state, related to the reactant population by an equilibrium constant $K^{\ddagger}$ of exactly the form derived in Section 15.15,

$$
K^{\ddagger}=\frac{q^{\ddagger}/V}{q_R/V}\,e^{-E_a/k_BT}
$$

where $q^{\ddagger}$ is the partition function of the transition state, built (Sections 15.5–15.8) from its translational, rotational, and vibrational partition functions exactly as for any stable species — **except for the reaction coordinate itself**, which is not a bound vibration at all (Section 16.4) and is treated separately below.

**Converting a population into a rate.** A system that reaches the transition-state geometry does not stay there; it proceeds to products at some rate set by the "vibration" along the reaction coordinate — except this is not an oscillation but a one-way passage over the barrier, so instead of the ordinary vibrational partition function of Section 15.7, this special degree of freedom is treated as a translational motion of infinitesimal width $\delta$ crossing the barrier region. The number of activated complexes crossing per unit time is (population at the barrier) $\times$ (the frequency at which each one moves across it), and working through this construction (the reaction-coordinate "translational" partition function contributes a factor that exactly cancels the $\delta$ against the crossing rate) leaves a **universal** frequency factor, independent of the specific system:

$$
\boxed{k=\frac{k_BT}{h}K^{\ddagger}}
$$

**A number worth checking.** At $298$ K, $k_BT/h\approx6.2\times10^{12}$ s$^{-1}$ — the same order of magnitude as a typical bond-vibration frequency (Chapter 5), which is exactly the physical picture this derivation encodes: an activated complex "attempts" to cross the barrier roughly once per vibrational period, and does so successfully with probability set by $K^{\ddagger}$.

**Where the approximation is.** The quasi-equilibrium assumption fails whenever a significant fraction of systems that reach the transition state recross back to reactants rather than proceeding on to products (the **transmission coefficient** $\kappa$, conventionally inserted as $k=\kappa(k_BT/h)K^{\ddagger}$ with $\kappa\leq1$, and taken as $\kappa=1$ throughout the rest of this chapter) — a genuine, named approximation, most severe for reactions with a shallow or ill-defined barrier.
> **Status of the principle: transition-state theory**
> *Approximate.* The rate formula is *Derived* given the quasi-equilibrium assumption; that assumption itself, equivalent to $\kappa=1$, is not exact and can fail for reactions with significant barrier recrossing.

---

## 16.10 The Eyring equation

**Restating the rate in thermodynamic language.** Section 15.12's $A=-k_BT\ln Q$ (and its Gibbs-energy counterpart) applies to $K^{\ddagger}$ exactly as to any equilibrium constant, giving $K^{\ddagger}=e^{-\Delta G^{\ddagger}/RT}$ with $\Delta G^{\ddagger}=\Delta H^{\ddagger}-T\Delta S^{\ddagger}$ the free energy, enthalpy, and entropy of activation. Substituting into Section 16.9's result gives the **Eyring equation**:

$$
\boxed{k=\frac{k_BT}{h}\,e^{-\Delta G^{\ddagger}/RT}=\frac{k_BT}{h}\,e^{\Delta S^{\ddagger}/R}\,e^{-\Delta H^{\ddagger}/RT}}
$$

$\Delta H^{\ddagger}$ is essentially Section 16.7's zero-point-corrected barrier; $\Delta S^{\ddagger}$ reflects how much translational, rotational, and vibrational freedom (Sections 15.5–15.7) is lost or gained in forming the constrained transition-state geometry from the more loosely structured reactants — typically negative for a bimolecular reaction (two freely translating and rotating species become one rigid activated complex, sharply reducing $q^{\ddagger}$ relative to $q_R$) and a useful diagnostic of whether a mechanism is concerted or stepwise, ordered or loose.

**The kinetic isotope effect.** Section 16.7 noted that the reaction-coordinate mode contributes no zero-point energy at the transition state, while every bond in the reactant does. Consider a reaction whose rate-determining step breaks a C–H (or C–D) bond directly along the reaction coordinate: in the reactant, this bond has a real zero-point energy, $\text{ZPE}=\tfrac12h\nu$ (Section 5.5); at the transition state, this specific vibration has become the reaction coordinate itself and contributes none. The activation energy is therefore *lowered*, relative to the bare electronic barrier, by exactly the reactant's zero-point energy — and since $\nu\propto1/\sqrt{\mu}$ (Section 5.1), the lighter isotope has the larger $\nu$, the larger zero-point energy, and therefore the larger reduction in its own barrier:

$$
E_a(\mathrm D)-E_a(\mathrm H)=\text{ZPE}_{\rm H}-\text{ZPE}_{\rm D}=\frac{h}{2}(\nu_{\rm H}-\nu_{\rm D})
$$

**Worked check.** For a typical C–H stretch at $2900$ cm$^{-1}$, the C–D reduced-mass ratio gives $\nu_{\rm D}\approx2129$ cm$^{-1}$, so $\text{ZPE}_{\rm H}-\text{ZPE}_{\rm D}\approx4.6$ kJ mol$^{-1}$, and

$$
\frac{k_{\rm H}}{k_{\rm D}}=e^{(\text{ZPE}_{\rm H}-\text{ZPE}_{\rm D})/RT}\approx6.4\quad(298\text{ K})
$$

matching the experimentally typical range for a primary kinetic isotope effect on a C–H/C–D bond-breaking step (commonly observed between about $2$ and $7$). **This closes the promise made when zero-point energy was first derived in Section 5.5**: an effect with no classical analogue at all (classically, $E=0$ at $T=0$ regardless of mass, so there would be no isotope effect whatsoever) is here shown to be directly responsible for a measurable, and mechanistically diagnostic, rate difference.
> **Status of the principle: the Eyring equation and the kinetic isotope effect**
> *Derived*, both, directly from transition-state theory (Section 16.9) combined with the zero-point energy of Section 5.5; the size of the isotope effect depends on how completely the isotopically sensitive bond's motion is converted into the reaction coordinate, so its magnitude (though not its existence) is *Approximate* case by case.

---

## 16.11 The Arrhenius equation

**A century-old empirical law, now explained.** Long before transition-state theory, Arrhenius proposed, purely from fitting rate-versus-temperature data, $k=Ae^{-E_a/RT}$, with $A$ (the pre-exponential factor) and $E_a$ treated as empirical constants. Comparing this directly to Section 16.10's Eyring result identifies

$$
A\approx\frac{k_BT}{h}\,e^{\Delta S^{\ddagger}/R}\ (\times e),\qquad E_a\approx\Delta H^{\ddagger}+RT
$$

(the small correction factors arise from the differing conventions for how temperature dependence is bookkept between the two forms, and do not affect the substance of the identification.) **Arrhenius's $A$ and $E_a$, taken as adjustable fitting parameters for over a century before transition-state theory existed, are now understood to encode the entropy and enthalpy of activation of Section 16.10** — an empirical law absorbed into a derived one, in the same pattern as the Balmer formula (Chapter 1, derived in Chapter 6) and the Planck distribution (Chapter 1, derived in Chapter 5).
> **Status of the principle: the Arrhenius equation**
> *Empirical* in its historical origin; *Derived* as the high-level approximation to the Eyring equation once $\Delta H^{\ddagger}$ and $\Delta S^{\ddagger}$ are identified with the activation enthalpy and entropy of transition-state theory.

---

## 16.12 The relationship between thermodynamics and kinetics

**Two independent numbers.** Chapter 15's $\Delta G$ (between reactant and product minima) governs *where equilibrium lies*; this chapter's $\Delta G^{\ddagger}$ (between reactant minimum and transition state) governs *how fast it is reached*. Nothing forces these to be correlated: a reaction can have a strongly negative $\Delta G$ (thermodynamically very favorable) and simultaneously a large $\Delta G^{\ddagger}$ (kinetically negligible at ordinary temperature) — the everyday situation for diamond-to-graphite conversion, and for the combustion of paper at room temperature (thermodynamically strongly favorable, kinetically inert until ignited). Conversely, a reaction with only a marginally favorable $\Delta G$ can proceed essentially instantaneously if $\Delta G^{\ddagger}$ is small.

**A restatement of the book's governing philosophy.** A reaction that "should" happen thermodynamically but visibly does not is not an exception to anything derived in Chapter 15 — Chapter 15's machinery never claimed to say anything about rate. This is the same structural point made about every other apparent contradiction in this book: the two theories answer different, precisely stated questions, and confusing them (not the theories themselves) is the source of any apparent paradox.
> **Status of the principle: the independence of $\Delta G$ and $\Delta G^{\ddagger}$**
> *Derived*, directly from the fact that they are computed from two different pairs of points on the same potential-energy surface (reactant-to-product for $\Delta G$, reactant-to-transition-state for $\Delta G^{\ddagger}$), with no mathematical relationship required to connect the two in general.

---

## 16.13 The Hammond postulate

**A qualitative rule, derived from a minimal model.** Chemists commonly state: an exothermic reaction has an "early," reactant-like transition state; an endothermic one has a "late," product-like transition state. This can be derived, not merely asserted, from the simplest possible model of the reaction profile (Section 16.2): two harmonic curves, one centered on the reactant geometry ($x=0$) and one on the product geometry ($x=1$), with the same curvature $k$ but shifted vertically by the reaction energy $\Delta E$ (negative for an exothermic reaction):

$$
E_R(x)=\tfrac12kx^2,\qquad E_P(x)=\tfrac12k(x-1)^2+\Delta E
$$

Approximating the transition state as the point where the two curves cross (a simplification of the true saddle point, but one that captures the essential physics) and solving $E_R(x^{\ddagger})=E_P(x^{\ddagger})$ gives

$$
x^{\ddagger}=\frac12+\frac{\Delta E}{k}
$$

**Reading the result.** For an exothermic reaction ($\Delta E<0$), $x^{\ddagger}<\tfrac12$: the crossing point sits closer to the reactant geometry ($x=0$) than the midpoint — an **early transition state**, structurally closer to the reactant, exactly as the Hammond postulate states. For an endothermic reaction ($\Delta E>0$), $x^{\ddagger}>\tfrac12$: a **late transition state**, structurally closer to the product. The postulate is not a new, unexplained rule of thumb; it is what a two-well crossing model predicts once the wells are allowed to have different depths.
> **Status of the principle: the Hammond postulate**
> *Derived* from the minimal two-parabola crossing model; *Approximate* as applied to any real reaction, since the true transition state is a genuine saddle point of the full potential-energy surface (Section 16.4), not merely the intersection of two idealized one-dimensional curves, and the two curves' curvatures are assumed equal here purely for simplicity.

---

## 16.14 Kinetic versus thermodynamic control

**Two different questions about product distribution.** When a reaction can proceed by more than one pathway to different products, which product dominates depends on the conditions. Under **kinetic control** (low temperature, short reaction time, or an effectively irreversible step), the product formed fastest dominates — the one reached through the *lower* $\Delta G^{\ddagger}$ (Section 16.9), regardless of its own thermodynamic stability. Under **thermodynamic control** (high temperature, long reaction time, or reversible conditions allowing the system to equilibrate), the product distribution instead approaches the ratio set by $\Delta G$ between the products themselves (Section 15.15's equilibrium constant), regardless of which one formed faster initially — because with enough time and reversibility, any product can convert back to a common intermediate and re-partition toward whichever is more stable.

**Not a contradiction, a difference in timescale.** A system under kinetic control at low temperature and the same system under thermodynamic control at high temperature or extended reaction time can give opposite major products from identical starting materials. This is not two rules in tension; it is Section 16.12's distinction between $\Delta G^{\ddagger}$ (Sections 16.9–16.11, governing which pathway is fastest) and $\Delta G$ (Chapter 15, governing which product is favored once equilibrium is actually reached) made visible in a single, commonly observed experimental phenomenon.
> **Status of the principle: kinetic versus thermodynamic control**
> *Derived*, as the direct experimental consequence of Section 16.12's distinction between the rate-determining $\Delta G^{\ddagger}$ and the equilibrium-determining $\Delta G$, applied to a branching reaction with more than one accessible product.

---

## What remains unexplained

| Open question                                                                                    | Where it is resolved |
| ------------------------------------------------------------------------------------------------- | --------------------- |
| What decides whether a reaction path is thermally or photochemically allowed in the first place?  | Chapter 18 (orbital symmetry) |
| Why do some barriers exist at all — what electronic-structure feature of the transition state sets $E^{\ddagger}$? | Chapter 17 (frontier orbitals) |
| How does a catalyst change $\Delta G^{\ddagger}$ without changing $\Delta G$?                     | Chapter 20            |
| What happens when the transmission coefficient $\kappa$ (Section 16.9) is far from 1 — tunneling through, rather than over, the barrier? | Not developed in this book; a further correction to transition-state theory |
| How do these single-step rate constants combine into the multi-step kinetics of a real mechanism (Section 19)? | Chapter 19            |

**Next:** Chapter 17 asks what actually determines the height of the barrier this chapter has learned to convert into a rate — turning to the frontier molecular orbitals (HOMO and LUMO) that control which reactions have low barriers and which do not.
