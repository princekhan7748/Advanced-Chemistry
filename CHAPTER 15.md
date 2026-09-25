# Chapter 15 — Statistical Mechanics and Chemical Thermodynamics

*Part II · From Quantum States to Chemical Behavior*

Chapters 3 through 14 answered, with growing sophistication, a single question: what energy levels can one isolated molecule have? A test tube contains not one molecule but of order $10^{23}$ of them, and nobody measures the energy of a single one. What is measured is pressure, heat capacity, entropy, and — the quantity that decides whether a reaction happens at all — the equilibrium constant.

The opening question:
> **Given the complete ladder of quantum states a molecule can occupy (Chapters 3–14 built exactly this, level by level), how do those discrete, individual-molecule energies become a bulk equilibrium constant measured in a flask?**

**Why this is not obvious.** A single hydrogen chloride molecule has a definite rotational quantum number $J$ at any instant, hopping unpredictably between levels through collisions. A mole of them does not have "a" $J$; it has $10^{23}$ molecules distributed over every rotational level Chapter 4 derived, in proportions that depend on temperature. This chapter derives that distribution from a single postulate, builds from it the specific formulas already promised for translation, rotation, and vibration, and uses the result to derive an equilibrium constant from nothing but the spectroscopic data — bond lengths, vibrational frequencies, bond energies — that Chapters 4–14 already produced.

| Mathematical result                                              | Chemical destination                                                     |
| -------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Equal a priori probability + maximizing multiplicity                | The Boltzmann distribution: why higher levels are less populated           |
| The molecular partition function $q$                                | A single number summarizing how many states are "thermally accessible"    |
| Factorization $q=q_{\rm trans}q_{\rm rot}q_{\rm vib}q_{\rm elec}$    | Independent treatment of translation, rotation, vibration, electronic state |
| Box levels (Ch. 3) in the macroscopic-box, near-continuum limit      | $q_{\rm trans}=(2\pi mk_BT/h^2)^{3/2}V$                                    |
| Rigid-rotor levels (Ch. 4) in the classical-rotor limit               | $q_{\rm rot}=k_BT/\sigma B$, with the symmetry number of Section 11.11 justified |
| Harmonic-oscillator levels (Ch. 5), geometric series                  | $q_{\rm vib}=1/(1-e^{-h\nu/k_BT})$; why room-temperature vibrations are "frozen" |
| $S=k_B\ln\Omega$                                                     | The Sackur–Tetrode equation; entropy computed with no adjustable parameter |
| $A=-k_BT\ln Q$                                                       | The single bridge equation linking every partition function to every thermodynamic potential |
| Equilibrium condition on the chemical potential                      | The equilibrium constant, expressed entirely in molecular partition functions |

**Roadmap.** The statistical postulate and the Boltzmann distribution (15.1–15.3) → the partition function and its factorization (15.4) → the three specific partition functions promised since Chapters 3–5 (15.5–15.8) → thermodynamic functions built from $q$ (15.9–15.13) → equilibrium and the equilibrium constant (15.14–15.16).

---

## 15.1 Microstates and macrostates

**Two levels of description.** A **macrostate** is what is measured: a fixed total energy $U$, volume $V$, and number of molecules $N$ (or, equivalently, a fixed temperature and pressure). A **microstate** is a complete quantum-mechanical specification — which exact translational, rotational, vibrational, and electronic level every single molecule occupies. An enormous number of distinct microstates are consistent with the same macrostate: fixing the total energy of $10^{23}$ molecules says nothing about which molecule has which share of it.

**The bridge, stated as a postulate.** Statistical mechanics rests on one assumption, already used without comment as far back as Section 1.2's Planck argument and Section 13.2's detailed-balance derivation: **every microstate consistent with a given total energy is equally probable.** Nothing in quantum mechanics as developed so far (Chapters 2–14) forces this; it is an independent postulate about how nature behaves in the aggregate, justified entirely by the correctness of everything derived from it.
> **Status of the principle: equal a priori probabilities**
> *Fundamental.* It is the foundational postulate of statistical mechanics, not a derived consequence of the quantum mechanics built in Chapters 2–14, though every result in this chapter is consistent with — and depends on — that quantum mechanics for its energy levels.

---

## 15.2 Probability and multiplicity

**Counting microstates.** For $N$ molecules distributed among energy levels with $n_1$ molecules in level 1, $n_2$ in level 2, and so on, the number of distinct ways of achieving that particular distribution (the **multiplicity** $\Omega$) is, when the molecules are distinguishable by position (as in a gas, where "which molecule" is in principle trackable),

$$
\Omega=\frac{N!}{n_1!\,n_2!\,n_3!\cdots}
$$

a standard result of combinatorics: the number of ways to partition $N$ labeled objects into groups of the stated sizes.

**Entropy as multiplicity.** Boltzmann's relation identifies thermodynamic entropy with the logarithm of this count:

$$
\boxed{S=k_B\ln\Omega}
$$

The logarithm is required by a single physical demand: entropy must be *additive* for two independent systems combined into one ($S_{\rm total}=S_1+S_2$), while multiplicities *multiply* ($\Omega_{\rm total}=\Omega_1\Omega_2$, since every microstate of system 1 can be paired with every microstate of system 2); only the logarithm converts a multiplicative combination rule into an additive one. $k_B$ is fixed by matching the resulting formula to the already-established ideal-gas thermodynamics (Section 15.10 carries this out explicitly).
> **Status of the principle: $S=k_B\ln\Omega$**
> *Derived* from the postulate of Section 15.1 together with the requirement that entropy be additive over independent subsystems; this is the definitional bridge that gives the abstract postulate physical content.

---

## 15.3 The Boltzmann distribution

**The problem.** Among all the ways $N$ molecules could be spread across the available energy levels $\varepsilon_i$ (each with degeneracy $g_i$) while keeping the total number $N$ and total energy $U$ fixed, which distribution is overwhelmingly the most probable one to actually observe?

**Maximizing the multiplicity.** By Section 15.1, the most probable distribution is the one with the largest $\Omega$, since it corresponds to the largest number of microstates and therefore dominates every other distribution by an enormous factor once $N\sim10^{23}$. Using Stirling's approximation ($\ln n!\approx n\ln n-n$) and maximizing $\ln\Omega$ subject to $\sum_in_i=N$ and $\sum_in_i\varepsilon_i=U$ (via Lagrange multipliers, a standard constrained-optimization technique) gives

$$
n_i=g_i\,e^{-\alpha-\beta\varepsilon_i}
$$

**Fixing the multipliers.** The constraint $\sum n_i=N$ fixes $e^{-\alpha}=N/q$, where $q\equiv\sum_ig_ie^{-\beta\varepsilon_i}$ is defined in Section 15.4. Comparing the resulting expression for $U$ against the ideal-gas thermodynamic relations already established (or, equivalently, comparing to the Boltzmann factor $e^{-h\nu/k_BT}$ already used without derivation in Sections 1.2 and 13.2) identifies $\beta=1/k_BT$:

$$
\boxed{\frac{n_i}{N}=\frac{g_ie^{-\varepsilon_i/k_BT}}{q}}
$$

**Physical reading.** Higher-energy levels are exponentially less populated, with the exponential controlled by the ratio of the level's energy to the thermal energy scale $k_BT$ — precisely the comparison already made informally throughout this book (Section 8's electronic gaps versus $k_BT$, Section 13's rotational versus vibrational spacings) and now placed on a derived footing.
> **Status of the principle: the Boltzmann distribution**
> *Derived* from the postulate of Section 15.1 by maximizing the multiplicity subject to fixed total number and energy.

---

## 15.4 Partition functions

**Definition.** The normalizing sum appearing in Section 15.3,

$$
q=\sum_ig_i\,e^{-\varepsilon_i/k_BT}
$$

is the **molecular partition function**. It is not merely a normalization constant: it is a running count of how many states are "thermally within reach" at temperature $T$ — near $q\approx1$ if $k_BT$ is far below the first excited level's energy (only the ground state is accessible), growing large when many levels lie within $k_BT$ of each other.

**Factorization.** For a molecule whose total energy is, to good approximation, a sum of independent translational, rotational, vibrational, and electronic contributions (exactly the separability already used for the particle in a three-dimensional box, Section 3.3, and implicit in every energy-level formula since),

$$
\varepsilon=\varepsilon_{\rm trans}+\varepsilon_{\rm rot}+\varepsilon_{\rm vib}+\varepsilon_{\rm elec}
$$

the exponential of a sum is a product of exponentials, so the partition function factorizes exactly:

$$
\boxed{q=q_{\rm trans}\,q_{\rm rot}\,q_{\rm vib}\,q_{\rm elec}}
$$

licensing the separate treatment of each degree of freedom in Sections 15.5–15.8, using the level structures already derived, respectively, in Chapters 3, 4, 5, and 8–9.
> **Status of the principle: factorization of the partition function**
> *Derived*, wherever the separability of Section 15.3's $\varepsilon$ itself holds — the same condition (Section 3.3's separation of variables) already flagged there as *Approximate* for any coupling between the modes (for instance, rotation–vibration coupling, Section 13.7).

---

## 15.5 Translational partition function

**From a discrete sum to an integral.** Section 3.2 gave the particle-in-a-box levels $E_n=n^2h^2/8mL^2$ and already noted that, for macroscopic $L$, adjacent levels are spaced by a fraction $\Delta E/E\sim2/n$ that becomes vanishingly small. At room temperature the level spacing is many orders of magnitude below $k_BT$, so the sum defining $q_{\rm trans}$ can be replaced by an integral without meaningful error:

$$
q_{\rm trans}=\sum_ne^{-n^2h^2/8mL^2k_BT}\ \approx\ \int_0^\infty e^{-n^2h^2/8mL^2k_BT}\,dn=\left(\frac{2\pi mk_BT}{h^2}\right)^{1/2}L
$$

Repeating this for all three dimensions of a box of volume $V=L_xL_yL_z$ (Section 3.3's separable three-dimensional box) gives

$$
\boxed{q_{\rm trans}=\left(\frac{2\pi mk_BT}{h^2}\right)^{3/2}V}
$$

**Physical reading: the thermal wavelength.** Defining $\Lambda\equiv h/\sqrt{2\pi mk_BT}$ (the **thermal de Broglie wavelength**, the same de Broglie relation as Section 1.7, now evaluated at thermal momentum), $q_{\rm trans}=V/\Lambda^3$: the number of thermally accessible translational states is simply the number of "boxes" of volume $\Lambda^3$ that fit in the container. For argon at $298$ K, $\Lambda\approx16$ pm, giving $q_{\rm trans}\sim10^7$ for one mole in typical laboratory volume — an enormous number of accessible states, confirming that the continuum approximation above is justified.
> **Status of the principle: translational partition function**
> *Derived*, in the continuum (large-box, high-temperature) limit of the exact particle-in-a-box levels of Section 3.2; *Approximate* only in the sense that any real container is finite, an approximation whose error is utterly negligible at laboratory scales.

---

## 15.6 Rotational partition function

**The high-temperature limit.** Section 4.4 gave the rigid-rotor levels $E_J=BJ(J+1)$ with degeneracy $2J+1$. When $k_BT\gg B$ (true for most molecules at room temperature, though not for H$_2$, as the worked check below shows), the sum over $J$ can again be approximated by an integral, giving

$$
q_{\rm rot}=\frac{k_BT}{\sigma B}\qquad\text{(linear molecule)}
$$

**The symmetry number, justified.** $\sigma$ is the **symmetry number** used without derivation in Section 11.11: the number of indistinguishable orientations a molecule passes through under a full rotation. It enters because the classical integral above counts every orientation of the rotor as distinct, but rotating a homonuclear diatomic like H$_2$ by $180°$ produces a configuration of identical nuclei that is not a new microstate at all — it must be divided out, exactly as $N!$ was divided out for indistinguishable particles in Section 15.2's counting. $\sigma=1$ for a heteronuclear diatomic (HCl), $\sigma=2$ for a homonuclear one (H$_2$, N$_2$) or a bent symmetric molecule (H$_2$O), and, as already stated without proof in Section 11.11, $\sigma=12$ for methane or benzene — the order of the molecule's rotational subgroup.

**Worked check, and a caution.** For HCl ($B=10.59$ cm$^{-1}$, Section 13.5) at $298$ K, $q_{\rm rot}\approx20$: about twenty rotational levels are thermally populated, consistent with the classical (continuum) approximation used to derive the formula. For H$_2$ ($B=60.9$ cm$^{-1}$, an unusually large rotational constant because of hydrogen's small reduced mass), the same formula gives $q_{\rm rot}\approx1.7$ at $298$ K — too close to unity for the continuum approximation to be trusted, and the explicit sum over the first few $J$ levels must be used instead. This is the same lesson as every approximation in this book: the formula is *Derived* within a stated domain, and H$_2$ sits outside it.
> **Status of the principle: rotational partition function and the symmetry number**
> *Derived* in the high-temperature (classical) limit of the exact rigid-rotor levels of Section 4.4; *Approximate* for light, stiffly-bound rotors such as H$_2$ at ordinary temperatures.

---

## 15.7 Vibrational partition function

**An exact sum.** Section 5.4 gave the harmonic-oscillator levels $E_v=(v+\tfrac12)h\nu$. Measuring energies from the $v=0$ level (so the zero-point energy is treated separately, absorbed later into the reaction energy $\Delta E_0$ of Section 15.15), the sum is an exact geometric series:

$$
q_{\rm vib}=\sum_{v=0}^\infty e^{-vh\nu/k_BT}=\boxed{\frac{1}{1-e^{-h\nu/k_BT}}}
$$

no continuum approximation needed, unlike Sections 15.5–15.6, because a geometric series sums in closed form regardless of how large the level spacing is.

**Why room-temperature vibrations are "frozen."** For HCl's stretching vibration ($\tilde\nu\approx2990$ cm$^{-1}$, Section 13.6), $h\nu/k_BT\approx14$ at $298$ K, so $q_{\rm vib}\approx1.0000005$: essentially every molecule sits in $v=0$. This is the same statement, now quantitative, behind the qualitative observation running throughout Chapters 1 and 5 that vibrational quanta are large compared to $k_BT$ at ordinary temperature — the direct statistical-mechanical reason a room-temperature gas shows negligible vibrational heat capacity while its translational and rotational motions behave classically.
> **Status of the principle: vibrational partition function**
> *Derived* exactly from the harmonic-oscillator levels of Section 5.4, with no approximation beyond the harmonic model itself (already flagged as *Approximate* in Section 5.11).

---

## 15.8 Electronic partition function

**Usually just the ground-state degeneracy.** With electronic energy gaps of order electron-volts (Chapters 6–9) and $k_BT\approx0.026$ eV at room temperature (Section 13.4's comparison, made explicit here), $e^{-\Delta E_{\rm elec}/k_BT}$ is astronomically small for any but the lowest electronic state, so

$$
q_{\rm elec}\approx g_0
$$

the degeneracy of the ground electronic state alone (for most closed-shell molecules, $g_0=1$).

**Where it matters.** A ground state with orbital or spin degeneracy (O$_2$'s triplet ground state, $g_0=3$; many transition-metal ions, Chapter 20) contributes a nontrivial $q_{\rm elec}$ even at room temperature, and any molecule with a low-lying excited electronic state within a few $k_BT$ of the ground state requires the full sum rather than the single-term approximation — the same domain-of-validity caveat as every truncated formula in this chapter.
> **Status of the principle: electronic partition function**
> *Approximate* in the common single-term form, valid whenever the first excited electronic state lies many $k_BT$ above the ground state; *Derived* exactly as the full sum in general.

---

## 15.9 Internal energy

**The general formula.** From the Boltzmann-weighted average energy per molecule, a short calculation (differentiating the partition function with respect to $\beta=1/k_BT$) gives the standard statistical-thermodynamic result

$$
U-U(0)=Nk_BT^2\left(\frac{\partial\ln q}{\partial T}\right)_V
$$

where $U(0)$ is the energy at $T=0$ (all molecules in their ground states). Because $q$ factorizes (Section 15.4) and $\ln$ of a product is a sum of logs, $U-U(0)$ splits additively into translational, rotational, vibrational, and electronic contributions, each computed from its own partition function.

**Equipartition recovered as a limit, not assumed.** Applying the formula to Section 15.5's $q_{\rm trans}\propto T^{3/2}$ gives $U_{\rm trans}=\tfrac32Nk_BT$; to Section 15.6's $q_{\rm rot}\propto T$ (linear molecule) gives $U_{\rm rot}=Nk_BT$ — exactly the classical **equipartition theorem** ($\tfrac12k_BT$ per quadratic degree of freedom in the energy), which this book has not previously derived. It appears here as the *high-temperature limit* of the underlying quantum statistics, valid precisely when the relevant level spacing is small compared to $k_BT$ (Sections 15.5–15.6's continuum approximation). Applying the same formula to Section 15.7's exact $q_{\rm vib}$ gives $U_{\rm vib}=Nh\nu/(e^{h\nu/k_BT}-1)$, which reduces to the equipartition value $Nk_BT$ only when $h\nu\ll k_BT$ — for HCl's vibration at room temperature this contribution is essentially zero, not $Nk_BT$, exactly consistent with $q_{\rm vib}\approx1$ found in Section 15.7. **Equipartition is not a separate postulate; it is what quantized energy levels look like once their spacing becomes negligible next to $k_BT$**, and its failure for vibrations at ordinary temperature is precisely the same physics that produced the ultraviolet-catastrophe resolution of Section 1.2.
> **Status of the principle: internal energy from the partition function, and equipartition as its classical limit**
> *Derived* from Section 15.3's Boltzmann distribution; equipartition itself is *Derived* as the high-temperature limiting case, not assumed.

---

## 15.10 Entropy

**From multiplicity to the partition function.** Combining Section 15.2's $S=k_B\ln\Omega$ with the Boltzmann distribution (Section 15.3) and the internal-energy result (Section 15.9), a standard rearrangement gives entropy directly in terms of $q$. For $N$ *indistinguishable* particles (correcting the distinguishable-particle counting of Section 15.2 by dividing by $N!$, since swapping two identical gas molecules produces no new microstate — precisely the indistinguishability principle already central to Chapter 7's discussion of identical particles), using Stirling's approximation for $\ln N!$:

$$
S=\frac{U-U(0)}{T}+Nk_B\left[\ln\left(\frac{q}{N}\right)+1\right]
$$

**The Sackur–Tetrode equation, and a parameter-free check.** Substituting Section 15.5's $q_{\rm trans}$ (rotational and vibrational contributions are negligible for a monatomic gas, since there is no rotation and no vibration to contribute) gives the **Sackur–Tetrode equation** for the molar entropy of an ideal monatomic gas:

$$
S_m=R\left[\ln\left(\frac{q_{\rm trans}}{N_A}\right)+\frac52\right]
$$

**Worked check: argon at $298.15$ K, $1$ bar.** Using only argon's atomic mass, the temperature, and the pressure — no measured entropy, no fitted parameter — this formula gives $S_m=154.85$ J mol$^{-1}$ K$^{-1}$, matching the measured third-law entropy of argon gas, $154.846$ J mol$^{-1}$ K$^{-1}$, to five significant figures. **This is the payoff promised at the start of the chapter: a macroscopic thermodynamic quantity, entropy, computed entirely from quantum mechanics (the particle-in-a-box levels of Chapter 3) and nothing else.**
> **Status of the principle: the Sackur–Tetrode equation**
> *Derived*, given the translational partition function of Section 15.5; its striking numerical agreement with experiment is direct evidence for the correctness of the whole chain of reasoning back to Chapter 3's particle-in-a-box quantization.

---

## 15.11 Enthalpy

**A minor bookkeeping step.** For a system at constant pressure, enthalpy is defined thermodynamically as $H=U+pV$. For an ideal gas, $pV=Nk_BT$ (an empirical relation this book has not derived from first principles, since it belongs to the classical, non-quantum thermodynamics of a gas's translational motion rather than to any internal energy level), so

$$
H-H(0)=\left(U-U(0)\right)+Nk_BT
$$

directly from Section 15.9's internal energy. Enthalpy differences ($\Delta H$ for a reaction) are what calorimetry measures directly and what Section 15.15's equilibrium constant will ultimately be checked against.
> **Status of the principle: enthalpy from internal energy**
> *Derived* from Section 15.9 together with the ideal-gas equation of state, itself *Empirical* within the scope of this book (a classical result about bulk gas behavior, not derived here from molecular quantum mechanics).

---

## 15.12 Helmholtz and Gibbs free energies

**The master bridge equation.** Thermodynamics defines the Helmholtz free energy as $A=U-TS$. Substituting Section 15.9's $U$ and Section 15.10's $S$ produces dramatic cancellation, leaving the single cleanest relation in statistical thermodynamics:

$$
\boxed{A-A(0)=-k_BT\ln Q}
$$

where $Q$ is the *total system* partition function ($Q=q^N/N!$ for $N$ indistinguishable, non-interacting molecules — Section 15.10's indistinguishability correction, now folded directly into the free energy). **Every thermodynamic quantity derived so far in this chapter, and every one still to come, is obtainable from this single equation** by the ordinary thermodynamic relations ($S=-(\partial A/\partial T)_V$, $p=-(\partial A/\partial V)_T$, and so on) — $A$, not $U$ or $S$ separately, is the fundamental link between the molecular partition function and macroscopic thermodynamics.

**Gibbs free energy.** $G=A+pV$, so for an ideal gas, using Section 15.11's $pV=Nk_BT$,

$$
G-G(0)=-k_BT\ln Q+Nk_BT
$$

$G$, not $A$, is the quantity that governs equilibrium at the constant pressure conditions of most chemistry (Sections 15.14–15.16).
> **Status of the principle: $A=-k_BT\ln Q$**
> *Derived* directly from the definitions of Sections 15.9–15.10; it is the central organizing relation of statistical thermodynamics, every other formula in this chapter being a special case or consequence of it.

---

## 15.13 Chemical potential

**Definition and formula.** The chemical potential is the free-energy cost of adding one more molecule, $\mu=(\partial G/\partial N)_{T,p}$. For an ideal gas, differentiating Section 15.12's $G$ with respect to $N$ (using $q\propto V$ from Section 15.5, so $q/N$ depends on $N$ only through the density) gives

$$
\mu=-k_BT\ln\left(\frac{q}{N}\right)
$$

**Physical reading.** $\mu$ decreases (adding a molecule becomes more favorable) as $q$ grows — more thermally accessible states per molecule — and increases with the density $N/V$, since a more crowded system leaves less "room" (in the translational partition function's sense, Section 15.5) for one more molecule. This single quantity, evaluated separately for every species in a reacting mixture, is what Section 15.14 uses to locate chemical equilibrium.
> **Status of the principle: chemical potential from the partition function**
> *Derived* from Section 15.12's free-energy relation, specialized to an ideal gas.

---

## 15.14 Equilibrium

**The condition.** At constant temperature and pressure, a system evolves toward lower $G$ and is at equilibrium precisely when $G$ can decrease no further: $dG=0$ for any small, allowed change. For a reaction $aA+bB\rightleftharpoons cC+dD$, the only allowed changes are those that convert reactants to products in the fixed stoichiometric ratio, so $dG=0$ becomes

$$
\boxed{c\mu_C+d\mu_D-a\mu_A-b\mu_B=0}
$$

**Why this is the whole condition.** Nothing about rates or mechanism enters this statement; it is a condition on the free energy alone (Section 16 will show separately that the *rate* of approach to this state is an entirely different question, governed by activation barriers rather than by $\Delta G$). Equilibrium, in this sense, is exactly the point at which the chemical potentials of Section 15.13 — each one itself built from a molecular partition function — balance across the stoichiometric equation.
> **Status of the principle: the equilibrium condition on chemical potential**
> *Derived* from the thermodynamic requirement that $G$ be minimized at fixed $T,p$, applied to the definition of $\mu$ in Section 15.13.

---

## 15.15 Equilibrium constants

**Assembling the pieces.** Substituting Section 15.13's $\mu_i=-k_BT\ln(q_i/N_i)$ (with $q_i$ measured, for each species, from its own zero-point/ground-state energy, and an explicit reaction energy $\Delta E_0$ — the difference between the ground-state energies of products and reactants, essentially the bond energies of Chapter 10 and the computed energies of Chapter 14 — added back in) into Section 15.14's equilibrium condition and rearranging gives

$$
\boxed{K=\frac{(q_C/V)^c(q_D/V)^d}{(q_A/V)^a(q_B/V)^b}\,e^{-\Delta E_0/k_BT}}
$$

the **equilibrium constant expressed entirely in terms of molecular partition functions** — each one built, by Sections 15.5–15.8, from nothing but a molecular mass (translation), a bond length (rotation, via Chapter 4's moment of inertia), a vibrational frequency (Chapter 5), and the ground-state energy difference $\Delta E_0$ (Chapters 9–10's bond energies, computable as in Chapter 14).

**What this closes.** This is the destination the entire book has been building toward since Chapter 1: an equilibrium constant, a macroscopic quantity a chemist measures with a burette, computed entirely from spectroscopic and structural data about individual molecules — bond lengths from microwave spectroscopy (Section 13.5), vibrational frequencies from infrared spectroscopy (Section 13.6), and bond energies from quantum-chemical calculation (Chapter 14) or thermochemistry. No new physical principle is needed beyond what Chapters 1–14 already derived; this chapter supplied only the statistical bridge connecting one molecule's quantum states to $10^{23}$ of them at temperature $T$.
> **Status of the principle: equilibrium constant from partition functions**
> *Derived*, as a direct consequence of Sections 15.5–15.14, given the (already flagged) approximations underlying each individual partition function — most significantly, the harmonic and rigid-rotor approximations of Chapters 4–5, and the accuracy of $\Delta E_0$, whose limitations were catalogued in Section 14.16.

---

## 15.16 Why reactions occur

**The synthesis.** $\Delta G=\Delta H-T\Delta S$ combines two things this chapter has shown to have a common origin. $\Delta H$ (Section 15.11) is dominated, for most reactions, by $\Delta E_0$ — the bond-energy differences traced to electronic structure since Chapter 10. $\Delta S$ (Section 15.10) reflects the change in the number of thermally accessible states — how much translational, rotational, and vibrational "room" the products have compared to the reactants, an entirely separate accounting from bond energy, and one this book had no machinery to discuss before this chapter. **A reaction is not spontaneous because its products are "more stable"** in the sense of lower bond energy alone; it is spontaneous when the combination $\Delta H-T\Delta S<0$, and either term can dominate. A reaction releasing energy but reducing the number of accessible microstates (for example, one that decreases the number of gas-phase molecules, sharply lowering $q_{\rm trans}$ for the system as a whole) can be disfavored at high temperature even with $\Delta H<0$; conversely, an endothermic reaction that increases molecular disorder (dissociation of a diatomic into two atoms, multiplying the accessible translational and rotational states) can become spontaneous once $T\Delta S$ overtakes $\Delta H$.

This is the final piece connecting the book's two questions, asked back in Chapter 9's closing box: *what is matter*, answered by Chapters 1–14, and *what does matter do*, which this chapter has now shown is governed by exactly the same quantum-mechanical energy levels, filtered through the statistical machinery of this chapter alone.
> **Status of the principle: $\Delta G=\Delta H-T\Delta S$ as the criterion for spontaneity**
> *Derived*, as the direct definition of $G$ combined with the results of Sections 15.9–15.11; both $\Delta H$ and $\Delta S$ are themselves *Derived* from the same underlying partition functions, so the criterion is not two independent physical effects but one calculation viewed from two angles.

---

## What remains unexplained

| Open question                                                                                  | Where it is resolved |
| --------------------------------------------------------------------------------------------------| --------------------- |
| How fast does a system reach the equilibrium this chapter locates, and what determines that rate? | Chapter 16            |
| How does the equilibrium constant depend on the shape of the whole potential-energy surface, not just its stationary points? | Chapter 16 |
| Why does the kinetic isotope effect (a rate, not an equilibrium, phenomenon) also trace back to the zero-point energy of Section 5.5? | Chapter 16 |
| How is the ideal-gas equation of state ($pV=Nk_BT$), used without derivation in Section 15.11, itself justified from molecular motion? | Not developed in this book; a standard result of kinetic theory |
| What changes in solution, where translational and rotational motion are hindered compared to the gas-phase partition functions derived here? | Touched on by Section 14.13's solvent models; not developed statistically in this book |

**Next:** Chapter 16 turns from *where* equilibrium lies to *how fast* a system gets there — building the potential-energy surface of Chapter 14 and the statistical machinery of this chapter into a theory of reaction rates.
