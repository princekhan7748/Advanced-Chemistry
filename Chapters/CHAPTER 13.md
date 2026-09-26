# Chapter 13 — Spectroscopy: Observing Quantum Chemistry

*Part I · The Quantum Structure of Matter*

Every earlier chapter has borrowed from this one. Section 4.8 stated $\Delta J=\pm1$ for rotation and required a permanent dipole, without derivation. Section 5.10 required a changing dipole for infrared absorption, also without derivation. Section 6.10 noted that $2s\to1s$ has no direct route and called it a parity argument to be completed later. Section 11.9 built the machinery of *whether* a transition dipole $\mathbf M_{fi}=\int\psi_f^{*}\hat{\boldsymbol\mu}\psi_i\,d\tau$ vanishes by symmetry, but never asked where $\mathbf M_{fi}$ comes from, why the rate depends on it, or what governs $\Delta l$ specifically. This chapter closes every one of those debts.

The opening question:
> **Given that Chapters 4–8 fixed every energy level a molecule can have, what decides which transitions between them are actually seen, how strong each line is, and how fast each process happens?**

**Three loose ends, restated precisely.** Chapter 11 answered *yes or no* using symmetry alone. This chapter answers *how strong* and *how fast*, and derives three rules used but not proved earlier: $\Delta l=\pm1$ (Section 6.10), $\Delta J=\pm1$ for a rotor (Section 4.8), and the dipole-derivative condition for infrared activity (Section 5.10). It also explains a fact no earlier chapter could: N$_2$ and O$_2$, both nonpolar and hence microwave-silent (Section 11.3), are visible in Raman rotational spectra.

| Mathematical result                                             | Chemical destination                                                  |
| ----------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Time-dependent perturbation of a two-level system                | Transition rates; why intensity is not just "allowed or forbidden"     |
| Detailed balance of the Einstein coefficients                    | Spontaneous vs. stimulated emission; lasers; NMR's weak signal          |
| Recursion relation of $Y_l^m$ under $z,x,y$                       | $\Delta l=\pm1$, $\Delta m=0,\pm1$ (Section 6.10, closed)               |
| Same recursion relation applied to the rotor's $Y_J^M$            | $\Delta J=\pm1$ (Section 4.8, closed)                                  |
| Ladder-operator matrix elements of $\hat x$ (harmonic oscillator) | $\Delta v=\pm1$; overtones only through anharmonicity                  |
| Linear term in $\mu(x)$ and $\alpha(x)$                           | The IR ($d\mu/dx\neq0$) and Raman ($d\alpha/dx\neq0$) intensity conditions, quantified |
| Polarizability as an $l=0,2$ tensor operator                     | Rotational Raman $\Delta J=0,\pm2$; visible even with no dipole         |
| Born–Oppenheimer factorization of the electronic transition moment | The Franck–Condon principle; vertical transitions; band shapes         |
| Spin–orbit admixture of $S=0$ and $S=1$ states                   | Phosphorescence; the heavy-atom effect, quantified with $Z^4$           |
| $\lvert\psi(0)\rvert^2\neq0$ only for $s$ character               | The Fermi contact hyperfine interaction; EPR hyperfine splitting; NMR $J$-coupling |

**Roadmap.** The interaction and its rate (13.1–13.3) → the general angular-momentum selection rules (13.4) → rotational and vibrational spectroscopy, IR (13.5–13.7) → Raman (13.8) → electronic spectroscopy, Franck–Condon, fluorescence and phosphorescence (13.9–13.11) → magnetic resonance and the contact interaction (13.12–13.13) → X-rays (13.14) → synthesis (13.15).

---

## 13.1 Matter interacting with electromagnetic radiation

**The physical setup.** A molecule with known stationary states $\psi_n$ (fixed by Chapters 4–9) sits in an oscillating field, $\mathbf E(t)=\mathbf E_0\cos\omega t$. Treated semiclassically — the field classical, the molecule quantum — this is a *time-dependent* perturbation, outside the time-independent machinery used everywhere so far.

**The dipole approximation.** The exact interaction of a charge distribution with a field involves the field's value at every point of the molecule, $\hat H'(t)=-\sum_i q_i\phi(\mathbf r_i,t)$. Visible, infrared and microwave wavelengths (hundreds of nm to cm) are enormous compared to a molecule (Ångströms), so the field is essentially uniform across it. Expanding $\phi$ in the small ratio (molecular size)/(wavelength) and keeping the leading term gives the **electric dipole approximation**:

$$
\hat H'(t)=-\hat{\boldsymbol\mu}\cdot\mathbf E(t),\qquad \hat{\boldsymbol\mu}=\sum_iq_i\mathbf r_i
$$

the operator already used without derivation in Section 11.9. The next terms in the expansion (electric quadrupole, magnetic dipole) are smaller by roughly the same ratio and explain why a dipole-forbidden transition is not always intensity-zero (Section 13.11).
> **Status of the principle: the dipole interaction operator**
> *Approximate.* It is the leading term of an expansion valid when the wavelength greatly exceeds the molecular size; X-rays (Section 13.14) begin to violate this.

---

## 13.2 Einstein coefficients

**Three processes, one relation.** For two levels $m$ (lower) and $n$ (upper) bathed in radiation of energy density $\rho(\nu)$ at the transition frequency, three things can happen: **absorption** at rate $B_{mn}\rho(\nu)$, **stimulated emission** at rate $B_{nm}\rho(\nu)$, and **spontaneous emission** at rate $A_{nm}$, independent of the field.

**Detailed balance.** At thermal equilibrium the populations obey the Boltzmann distribution of Section 1.2/8's antecedents, $N_n/N_m=e^{-h\nu/k_BT}$ (for nondegenerate levels), and the rate of upward transitions must equal the rate of downward ones:

$$
N_mB_{mn}\rho(\nu)=N_n\left[A_{nm}+B_{nm}\rho(\nu)\right]
$$

Solving for $\rho(\nu)$ and demanding the result match the Planck distribution (Section 1.2, *Derived* since Chapter 5) for every temperature forces two conclusions:

$$
B_{mn}=B_{nm},\qquad \frac{A_{nm}}{B_{nm}}=\frac{8\pi h\nu^3}{c^3}
$$

**Physical content.** $A_{nm}/B_{nm}$ grows as $\nu^3$: spontaneous emission dominates at high frequency (visible light, which is why excited electronic states decay largely on their own) while stimulated processes dominate at low frequency (radiofrequency, which is why NMR — Section 13.12 — needs to be driven and gives an inherently weak signal). Every "spectrum" in this chapter is fundamentally a plot of $B_{mn}$, hence of the matrix element behind it, as a function of frequency.
> **Status of the principle: the Einstein A/B relation**
> *Derived* from detailed balance combined with the Planck distribution, itself *Derived* in Chapter 5.

---

## 13.3 Transition probabilities

**From the perturbation to a rate.** First-order time-dependent perturbation theory (the full apparatus belongs to Chapter 9's toolkit; only the result is needed here) gives, for a field oscillating near the transition frequency $\omega_{fi}=(E_f-E_i)/\hbar$, a transition rate

$$
\Gamma_{i\to f}\ \propto\ \lvert\langle f\rvert\hat{\boldsymbol\mu}\cdot\hat{\mathbf e}\lvert i\rangle\rvert^2\,\rho(\omega_{fi})
$$

where $\hat{\mathbf e}$ is the field's polarization direction. Comparing to Section 13.2's $B_{mn}\rho(\nu)$ identifies

$$
B_{mn}\ \propto\ \lvert\mathbf M_{fi}\rvert^2,\qquad \mathbf M_{fi}=\langle f\rvert\hat{\boldsymbol\mu}\lvert i\rangle
$$

**This closes the loop with Chapter 11.** Section 11.9's vanishing theorem said $\mathbf M_{fi}$ is exactly zero unless $\Gamma_f\otimes\Gamma_\mu\otimes\Gamma_i$ contains $A_1$: that is the *yes/no* answer. This section adds the *how much*: when the integral is nonzero, its numerical size sets the intensity, and nothing in group theory fixes that number. A symmetry-allowed transition can still be experimentally weak if $\mathbf M_{fi}$ happens to be numerically small.
> **Status of the principle: transition rate from the dipole matrix element**
> *Derived*, given first-order perturbation theory (itself developed properly as part of Chapter 9).

---

## 13.4 Selection rules: $\Delta l=\pm1$

**The integral to evaluate.** For one electron in a central potential (Section 6.10's unfinished business), the states are $\psi_{nlm}=R_{nl}Y_l^m$. The dipole components are, up to constants, $z=r\cos\theta$ and $x\pm iy=r\sin\theta\,e^{\pm i\phi}$: each is (a function of $r$) times ($l=1$ angular functions). The angular integral needed is $\int Y_{l'}^{m'*}\,Y_1^{m_1}\,Y_l^m\,d\Omega$.

**The recursion relation.** The associated Legendre functions obey an exact recursion,

$$
\cos\theta\,Y_l^m=a_{l,m}\,Y_{l+1}^m+b_{l,m}\,Y_{l-1}^m
$$

for specific coefficients $a_{l,m},b_{l,m}$ (a consequence of the differential equation defining $Y_l^m$, not an approximation). Multiplying by $Y_{l'}^{m'*}$ and integrating, orthogonality of spherical harmonics (Section 4.5) kills every term except $l'=l+1$ or $l'=l-1$:

$$
\int Y_{l'}^{m*}\cos\theta\,Y_l^m\,d\Omega\neq0\quad\text{only if}\quad l'=l\pm1
$$

The same recursion applied to $x\pm iy\propto\sin\theta\,e^{\pm i\phi}Y_l^m$ gives $l'=l\pm1$ together with $m'=m\pm1$ (from the $e^{\pm i\phi}$ factor and $\phi$-integral orthogonality, Section 4.6). Collecting all three components:

$$
\boxed{\Delta l=\pm1,\qquad \Delta m=0,\pm1}
$$

**Physical reading: a photon carries angular momentum.** A photon emitted or absorbed in a dipole transition carries one unit of angular momentum, $\hbar$ (this is why it has spin 1). Conservation of total angular momentum then requires the atom's orbital angular momentum to change by exactly the amount the photon carries away or brings in — one unit — which is the content of the abstract recursion relation above, restated as a conservation law. This is why $2s\to1s$ in hydrogen (Section 6.10, both $l=0$) has no electric-dipole route: it would require the photon to carry zero angular momentum, which an electric-dipole photon cannot do.

**Many-electron atoms: $\Delta J=0,\pm1$, with $J=0\to J=0$ forbidden.** For a many-electron atom the good quantum number after spin–orbit coupling is the total angular momentum $J$ (Chapter 7), not $l$ of a single electron. The identical argument, now applied to the coupled state, gives $\Delta J=0,\pm1$ — a transition with no change in $J$ is now allowed because $J$ mixes orbital and spin momentum in a way a single electron's $l$ cannot — except that $J=0\to J=0$ remains strictly forbidden: a photon carrying one unit of angular momentum cannot connect two states of zero angular momentum by any vector-addition rule.

**Note on notation.** The next two sections reuse the letter $J$ for a *different* quantum number, the rotational quantum number of Section 4.4's rigid rotor. The two $J$'s are conventional in their respective subfields and are not the same physical quantity; context (atomic fine structure versus molecular rotation) always disambiguates.
> **Status of the principle: $\Delta l=\pm1$, $\Delta m=0,\pm1$, $\Delta J=0,\pm1$**
> *Derived* from the exact recursion relations of spherical harmonics, equivalent to conservation of angular momentum with a spin-1 photon.

---

## 13.5 Rotational spectroscopy

**Applying Section 13.4 to the rotor.** The rigid rotor's eigenfunctions are themselves spherical harmonics, $Y_J^M(\theta,\phi)$ (Section 4.4), so the identical recursion-relation argument applies verbatim, with the rotor's $J$ in place of the atomic $l$:

$$
\boxed{\Delta J=\pm1,\qquad \Delta M=0,\pm1}
$$

closing the promise of Section 4.8. ($\Delta J=0$ is now excluded outright, since a rotor has no internal spin analogue to relax the strict rule.)

**The requirement of a permanent dipole, made quantitative.** The transition moment is $\mathbf M_{fi}=\langle J',M'\rvert\boldsymbol\mu_0\lvert J,M\rangle$, where $\boldsymbol\mu_0$ is the molecule's fixed dipole vector, carried along by the rotating frame. If $\mu_0=0$ (Section 11.3's symmetry criterion), every such integral is zero regardless of $J,J'$: **no permanent dipole means no pure rotational spectrum**, the requirement stated but not derived in Section 4.8.

**The spectrum.** With $E_J=BJ(J+1)$, $B=\hbar^2/2I$ (Section 4.4), the allowed transitions $J\to J+1$ appear at

$$
\tilde\nu_J=2B(J+1),\qquad J=0,1,2,\dots
$$

a ladder of equally spaced lines, spacing $2B$. **Worked check, HCl.** With $r=127.45$ pm and the reduced mass of $^1$H and $^{35}$Cl, $I=\mu r^2$ gives $B=10.59$ cm$^{-1}$ (matching the measured value), so the $J=0\to1$ line falls at $21.19$ cm$^{-1}$ ($635$ GHz), in the microwave region — consistent with rotational spectroscopy's usual name.

**Where it needs correcting.** A real rotor is not perfectly rigid; centrifugal distortion stretches the bond at high $J$, and $E_J=BJ(J+1)-DJ^2(J+1)^2$ with a small distortion constant $D$. This is the rotational analogue of the anharmonicity correction of Section 5.11: the rigid-rotor model is *Approximate*, and its failure at high $J$ is missing elastic physics, not an exception.
> **Status of the principle: $\Delta J=\pm1$ and the permanent-dipole requirement**
> *Derived*, both parts, from the same recursion-relation argument as Section 13.4.

---

## 13.6 Vibrational spectroscopy

**The harmonic selection rule.** In the ladder-operator form of the harmonic oscillator (Section 5.3), $\hat x\propto(\hat a+\hat a^\dagger)$, and $\hat a,\hat a^\dagger$ change $v$ by exactly $\mp1,\pm1$. So $\langle v'\rvert\hat x\lvert v\rangle\neq0$ only for $v'=v\pm1$:

$$
\boxed{\Delta v=\pm1}\qquad\text{(harmonic approximation)}
$$

**The dipole-derivative requirement, quantified.** Expanding the dipole moment about the equilibrium bond length, $\mu(x)\approx\mu_0+(d\mu/dx)_0x+\cdots$, the transition moment for the fundamental is

$$
M_{1,0}=\left(\frac{d\mu}{dx}\right)_0\langle1\rvert x\lvert0\rangle
$$

The constant term $\mu_0$ contributes nothing (it gives $\langle1\rvert0\rangle=0$ by orthogonality); only the *derivative* survives. This is the full, quantitative version of Section 5.10's requirement and Section 11.10's symmetry form: **infrared intensity is proportional to $(d\mu/dx)^2$**, not merely nonzero-or-zero.

**Overtones.** In the pure harmonic model $\langle v'\rvert x\lvert v\rangle=0$ for $\lvert\Delta v\rvert\neq1$, so overtones ($\Delta v=2,3,\dots$) are exactly forbidden. Real spectra show them weakly (Section 5.11) because the true potential is anharmonic: a cubic term in $V(x)$ mixes a small amount of $v=2$ character into the $v=1$ state (Chapter 9's perturbation theory), giving the $v=0\to2$ transition a small but nonzero moment. This is again missing physics (anharmonicity), not an arbitrary exception.
> **Status of the principle: $\Delta v=\pm1$ and $d\mu/dx\neq0$**
> *Derived* in the harmonic approximation; the appearance of overtones is *Derived* once anharmonicity is included as a perturbation.

---

## 13.7 IR spectroscopy

**Combining rotation and vibration.** A real molecule vibrates and rotates simultaneously; to leading order (Born–Oppenheimer-like separation of fast vibration from slower rotation, itself a preview of the full Born–Oppenheimer argument of Chapter 9) the two selection rules of Sections 13.5–13.6 apply together: $\Delta v=+1$ (absorption) and $\Delta J=\pm1$. This produces, for a diatomic, two branches around the vibrational origin $\tilde\nu_0$:

$$
\text{R branch }(\Delta J=+1):\ \tilde\nu=\tilde\nu_0+2B(J+1),\qquad
\text{P branch }(\Delta J=-1):\ \tilde\nu=\tilde\nu_0-2BJ
$$

with a gap of $4B$ at the centre where the forbidden $\Delta J=0$ line (the "Q branch") would fall for a simple diatomic; a Q branch does appear for certain vibrations of linear polyatomics (bending modes), where the vibrational angular momentum relaxes the strict $\Delta J\neq0$ rule — a detail belonging to a fuller rovibrational treatment than this chapter develops. **The rovibrational spectrum is therefore a direct readout of both $B$ (line spacing) and the vibrational frequency (band origin) at once**, and it is how bond lengths and force constants are measured in practice.
> **Status of the principle: rovibrational band structure**
> *Derived* from the combination of Sections 13.5 and 13.6, within the approximation that vibration and rotation are independent (the same approximation invoked, and to be justified quantitatively, in the Born–Oppenheimer separation of Chapter 9).

---

## 13.8 Raman spectroscopy

**A different mechanism.** Raman scattering does not require the molecule to absorb a whole photon at the transition energy. An incident photon induces an oscillating dipole via the polarizability (Section 6.13), $\boldsymbol\mu_{\rm ind}=\boldsymbol\alpha\cdot\mathbf E$, and the scattered light carries away a photon shifted in energy by exactly a vibrational or rotational quantum, while $\alpha$ itself is modulated by the molecule's motion.

**Vibrational Raman.** Expanding $\alpha(x)\approx\alpha_0+(d\alpha/dx)_0x+\cdots$, the same ladder-operator argument as Section 13.6 gives $\Delta v=\pm1$ with intensity $\propto(d\alpha/dx)^2$: **Raman needs a changing polarizability, exactly as IR needs a changing dipole**, and Section 11.10's mutual-exclusion rule (a centrosymmetric molecule's mode cannot satisfy both conditions at once) is this pair of requirements read off from parity.

**Rotational Raman: the missing piece for nonpolar molecules.** The polarizability is a rank-2 tensor, transforming under rotations like the quadratic functions $x^2,xy,\dots$, i.e. as an $l=2$ object (Section 11.5's character-table entries). The recursion-relation argument of Section 13.4, run twice (an $l=2$ operator connects $Y_J^M$ to $Y_{J\pm2}^M$ and $Y_J^M$ itself), gives

$$
\boxed{\Delta J=0,\pm2}\qquad\text{(rotational Raman)}
$$

and it requires an **anisotropic** polarizability ($\alpha$ different along different molecular axes), not a permanent dipole. This is exactly why homonuclear diatomics such as N$_2$ and O$_2$ — nonpolar, so silent in microwave absorption (Section 13.5) — nonetheless show a rotational Raman spectrum with lines spaced by $4B$ (from $\Delta J=\pm2$): the two techniques probe different tensors of the same molecule and are genuinely complementary, not two ways of measuring the same thing.
> **Status of the principle: Raman selection rules**
> *Derived*, by the identical mechanism as Sections 13.4–13.6, applied to the polarizability operator's tensor rank instead of the dipole's vector rank.

---

## 13.9 Electronic spectroscopy

**Factorizing the transition moment.** An electronic transition moves the whole electronic wavefunction, which depends parametrically on the nuclear positions $R$ (Section 9's Born–Oppenheimer separation, previewed here): $\Psi=\psi_e(r;R)\chi_v(R)$. The transition moment is

$$
M_{fi}=\int\psi_{e'}^{*}(r;R)\chi_{v'}^{*}(R)\,\hat{\boldsymbol\mu}\,\psi_e(r;R)\chi_v(R)\,d\tau_e\,dR
$$

Because the electronic transition moment $\boldsymbol\mu_e(R)=\int\psi_{e'}^{*}\hat{\boldsymbol\mu}\,\psi_e\,d\tau_e$ varies only slowly with $R$ over the small range the nuclei sample, it can be pulled outside the nuclear integral (the **Condon approximation**, an application of the same "electrons are fast, nuclei are slow" logic that underlies Born–Oppenheimer):

$$
M_{fi}\approx\boldsymbol\mu_e(R_0)\int\chi_{v'}^{*}(R)\chi_v(R)\,dR
$$

The intensity therefore factorizes into an electronic part and a purely nuclear overlap, $\lvert\int\chi_{v'}^{*}\chi_v\,dR\rvert^2$, called the **Franck–Condon factor**. Section 13.10 shows what controls its value.
> **Status of the principle: Condon approximation**
> *Approximate.* It assumes the electronic transition moment is constant over the nuclear wavefunction's spread, reasonable because nuclei are far heavier (and hence far slower) than electrons — quantified next.

---

## 13.10 UV–Visible spectroscopy and the Franck–Condon principle

**Why the transition is "vertical."** The proton is roughly 1800 times heavier than the electron (Section 13.9's assumption, made quantitative): $m_e/m_p\approx5.4\times10^{-4}$. An electron rearranges on a timescale of order $10^{-16}$ s; a bond vibrates on a timescale of order $10^{-13}$–$10^{-14}$ s. The electronic transition is effectively instantaneous on the nuclear timescale, so the nuclei have neither the time nor the impulse to move during the transition: on a plot of energy against bond length, the transition is drawn as a **vertical line** from the initial to the final electronic curve, at fixed $R$.

**What the vertical line means for intensity.** The transition lands preferentially on whichever vibrational level $v'$ of the excited state has its wavefunction $\chi_{v'}$ overlapping best, at the *original* equilibrium bond length, with the ground-state $\chi_v$ (usually $v=0$, a function peaked at $R_0$). If the excited-state potential is displaced to a longer bond length (typical, since excitation often weakens a bond, Section 10.16), the largest overlap is not with $v'=0$ but with some higher $v'$ near the classical turning point at $R_0$ — producing a **progression** of absorption lines at $\Delta v'=0,1,2,\dots$, with the most intense line away from the band origin. This is the quantitative content behind the (previously underived) shape of real UV–visible spectra, such as the vibronic fine structure seen in gas-phase I$_2$ absorption.

**A precise distinction, worth restating.** The **Franck–Condon principle** (this section: vibrational-overlap intensities within one electronic transition) is not the **Franck–Hertz experiment** (Section 1.10: discrete energy loss of electrons colliding with atoms, demonstrating that atomic excitation is quantized at all). They share an author and a decade, and nothing else; conflating them is a labeling error to avoid explicitly.
> **Status of the principle: the Franck–Condon principle**
> *Derived* from the Condon approximation (Section 13.9) together with the large nuclear-to-electronic mass ratio.

---

## 13.11 Fluorescence and phosphorescence

**Fluorescence and the Stokes shift.** After absorption to some excited vibronic level, vibrational relaxation within the excited electronic state (collisional energy loss, typically picoseconds) is much faster than radiative decay (typically nanoseconds), so emission always begins from the *lowest* vibrational level of the excited state (**Kasha's rule**) regardless of which level absorption first populated. By the same Franck–Condon logic as Section 13.10, applied now to emission, this produces a mirror-image emission band systematically shifted to lower energy (longer wavelength) than the absorption band — the **Stokes shift** — because emission again lands vertically on a range of vibrational levels of the ground state, from a $v'=0$ starting point rather than the original ground-state minimum.

**Phosphorescence and the debt to Chapter 7.** A transition from an excited triplet state ($S=1$) to the singlet ground state ($S=0$) is spin-forbidden: the dipole operator does not act on spin, so $\langle S=0\rvert\hat{\boldsymbol\mu}\lvert S=1\rangle=0$ exactly in the absence of any spin–orbit coupling. Spin–orbit coupling (Chapter 7) mixes a small amount of singlet character into the nominally triplet state, $\lvert T_1\rangle\approx\lvert{}^3\psi\rangle+\lambda\lvert{}^1\psi\rangle$ with $\lambda$ proportional to the spin–orbit coupling strength, which Chapter 7 showed scales roughly as $Z^4$ for the innermost electrons. The transition moment is then $M_{fi}\approx\lambda\langle S_0\rvert\hat{\boldsymbol\mu}\lvert{}^1\psi\rangle\neq0$, small but nonzero — exactly the vibronic/spin–orbit "borrowing" mechanism named without derivation in Section 11.11, now made explicit. Because $\lambda$ is small, the phosphorescence lifetime (microseconds to seconds) vastly exceeds fluorescence (nanoseconds), and because $\lambda^2$ grows with $Z^4$, heavier atoms (the **heavy-atom effect**, e.g. bromine- or iodine-substituted molecules) phosphoresce far more readily — a direct, quantitative link back to Chapter 7's fine-structure formula.
> **Status of the principle: fluorescence and phosphorescence mechanisms**
> *Derived*, given the Franck–Condon principle (fluorescence lineshape) and spin–orbit coupling (Chapter 7) as the source of the small admixture that makes phosphorescence possible at all.

---

## 13.12 Nuclear magnetic resonance (NMR)

**The Zeeman splitting of a nuclear spin.** A nucleus with spin $I$ (for example $^1$H, $I=\tfrac12$) has a magnetic moment $\boldsymbol\mu_N=\gamma_N\hbar\mathbf I$. In an external field $B_0$ along $z$, the energy is $E_{m_I}=-\gamma_N\hbar B_0m_I$, splitting the $2I+1$ nuclear spin states — the direct nuclear analogue of the atomic Zeeman effect of Section 6.12. Absorption occurs at the **Larmor frequency**,

$$
\nu_L=\frac{\gamma_NB_0}{2\pi}
$$

For a proton at a typical spectrometer field $B_0=11.7$ T, $\nu_L\approx500$ MHz — a radiofrequency, which is why (Section 13.2) NMR is a stimulated-emission-dominated, inherently weak-signal technique, unlike electronic spectroscopy.

**Chemical shift.** Electrons circulating around a nucleus generate a small local field opposing (usually) the applied one, so different chemical environments shift $\nu_L$ slightly — this is a perturbation-theory correction to the bare Larmor formula, and its size is set by the local electron density, a quantity already computed for simple systems in Chapters 6 and 12.

**Spin–spin ($J$) coupling.** Two nearby nuclear spins interact indirectly, transmitted through the bonding electrons rather than through space (which would average to zero under molecular tumbling in solution). The dominant mechanism for a one-bond coupling is the same **Fermi contact interaction** derived explicitly in Section 13.13: the electron density at each nucleus is not independent, and polarization of the bonding electron pair's spins couples the two nuclear spins together. This is why NMR coupling constants are largest for directly bonded nuclei and fall off sharply with the number of intervening bonds — the contact mechanism requires finite electron density *at* each nucleus, which only $s$-character orbitals provide (Section 13.13).
> **Status of the principle: Larmor resonance and chemical shift**
> *Derived* for the bare Zeeman splitting; chemical shift and $J$-coupling are *Approximate*, since both are perturbative corrections whose size depends on the detailed electron distribution.

---

## 13.13 Electron paramagnetic resonance (EPR) and the Fermi contact interaction

**The electron analogue.** A molecule or ion with an unpaired electron shows the electronic Zeeman effect: $E_{m_S}=g_e\mu_BB_0m_S$, with the $g$-factor of Chapter 7 now appearing as a directly measured number ($g_e\approx2.0023$ for a free electron). Resonance occurs at $h\nu=g_e\mu_BB_0$; at a typical X-band frequency of 9.5 GHz this requires only $B_0\approx339$ mT. Because the electron's magnetic moment is roughly 660 times a proton's (the ratio $g_e\mu_B/g_N\mu_N$, tracing to the same electron/nucleon mass ratio behind Section 13.10's Franck–Condon argument), the same field splits electron spin states far more than nuclear ones: EPR reaches a convenient microwave frequency at a field roughly 35 times *smaller* than the multi-tesla fields NMR needs to reach its own convenient radiofrequency range.

**Deriving the contact term.** An electron's magnetic moment interacts with a nucleus's in two ways: a **dipolar** term (anisotropic, like two bar magnets, and averaged to zero by rapid tumbling in solution or gas) and a term that survives even after averaging, because it depends only on the electron's probability density *at* the nucleus rather than on any spatial direction. This second term arises from the same relativistic reduction of the Dirac equation that produced the Darwin term of Section 7.9 (both are contact interactions localized at the nucleus, one with the external Coulomb field and one with the nuclear magnetic moment) and takes the form

$$
\hat H_{\rm contact}=\frac{2}{3}\mu_0\,g_e\mu_B\,g_N\mu_N\,\hat{\mathbf S}\cdot\hat{\mathbf I}\,\delta(\mathbf r)
$$

**Only $s$ character contributes.** Because $\delta(\mathbf r)$ picks out the electron density exactly at the nucleus, and every $p$, $d$, and $f$ orbital vanishes there (Section 6.5's node structure — an angular node at the origin for any $l>0$), the contact interaction is nonzero *only* for electrons with $s$ character. Taking the expectation value in an $s$ orbital gives the isotropic hyperfine coupling constant

$$
a_{\rm iso}=\frac{2}{3}\mu_0\,g_e\mu_B\,g_N\mu_N\,\lvert\psi(0)\rvert^2
$$

**Worked check: the hydrogen atom, and the 21 cm line.** For a hydrogen $1s$ electron, $\lvert\psi_{1s}(0)\rvert^2=1/(\pi a_0^3)$ (Section 6.6). Substituting the known constants gives $a_{\rm iso}\approx1423$ MHz, matching the measured hydrogen hyperfine splitting of $1420.4$ MHz to within a fraction of a percent — the same transition, between the two hyperfine levels of atomic hydrogen's ground state, that produces the 21 cm line used throughout radio astronomy to map galactic hydrogen. **This single formula, assembled from the electron mass, the proton's $g$-factor, and nothing but the Bohr radius already derived in Chapter 6, reproduces one of the best-known numbers in astrophysics.**

**Chemical consequence.** An EPR spectrum of a radical splits into $2nI+1$ lines from $n$ equivalent nuclei of spin $I$ (for protons, $n+1$ lines with binomial intensities), because the contact interaction couples the unpaired electron to every nucleus where the singly occupied orbital has $s$ character — including, through hyperconjugation, protons not directly bonded to the radical center. Measuring these splittings maps out exactly where the unpaired electron's density sits.
> **Status of the principle: Fermi contact hyperfine interaction**
> *Derived* from the nonrelativistic reduction of the Dirac equation (Chapter 7); its restriction to $s$ character is *Derived* from the orbital node structure of Chapter 6.

---

## 13.14 X-ray methods

**Core-electron transitions and Moseley's law.** X-rays arise from transitions involving inner-shell electrons, which see a nuclear charge screened only by the few electrons closer to the nucleus (Section 8.5's shielding). Treating a core electron hydrogenically with effective charge $Z-\sigma$ (Section 6.8's energy formula, Section 8.6's effective nuclear charge) gives an emission frequency $\nu\propto(Z-\sigma)^2$, or

$$
\sqrt\nu=k(Z-\sigma)
$$

**Moseley's law** — a direct consequence of formulas already derived, not a new postulate, and historically the tool that established atomic number (rather than atomic mass) as the correct ordering principle of the periodic table (Section 8.17).

**A different character of technique.** X-ray *diffraction*, used to determine molecular structure, is not a spectroscopic transition between quantum states at all: it is classical wave interference off a periodic lattice of scatterers, governed by $n\lambda=2d\sin\theta$ (Bragg's law), and belongs conceptually with the wave mechanics of Chapter 1 rather than with the transition-rate machinery built in this chapter. It is included in this section only because "X-ray methods" conventionally covers both; the two techniques answer different questions (electronic energies versus atomic positions) by entirely different physics.
> **Status of the principle: Moseley's law**
> *Derived* as a direct application of the hydrogenic energy formula (Chapter 6) with the shielding correction of Chapter 8.

---

## 13.15 Spectroscopy as inverse quantum mechanics

Look back over the chapter. Every selection rule derived here — $\Delta l=\pm1$, $\Delta J=\pm1$ for a rotor, $\Delta v=\pm1$, $\Delta J=0,\pm2$ for rotational Raman, the Franck–Condon factor, the Fermi contact term — came from the same two-step recipe: take the eigenstates already constructed in Chapters 4 through 9 (spherical harmonics, harmonic-oscillator ladder states, hydrogenic orbitals, Born–Oppenheimer-separated electronic and nuclear wavefunctions, spin-mixed states from Chapter 7), and evaluate a matrix element of a physically motivated operator — dipole, polarizability, or the contact $\delta(\mathbf r)$ — between them. No new quantum mechanics was introduced in this chapter; every rule was an *unpacking* of structure already present in earlier chapters' wavefunctions.

$$
\boxed{\text{Theory predicts spectra}\quad\Longleftrightarrow\quad\text{spectra reveal quantum structure}}
$$

This is why spectroscopy is used, in practice, to *test* and *measure* the theory built so far: a bond length from a rotational spacing (Section 13.5), a force constant from a vibrational frequency (Section 13.6), an electron affinity's fine structure from a photoelectron spectrum (Section 11.7), an unpaired electron's location from a hyperfine pattern (Section 13.13). The next chapter turns from analytic derivation to numerical computation, needed precisely because most real molecules are too large for the exact matrix elements of this chapter to be evaluated by hand.
> **Status of the principle: spectroscopy as a readout of prior theory**
> *Derived* — a summary observation about the structure of this chapter's arguments, not a new physical claim.

---

## What remains unexplained

| Open question                                                                                   | Where it is resolved |
| ------------------------------------------------------------------------------------------------- | --------------------- |
| How is first-order time-dependent perturbation theory itself derived (used without proof in 13.3)? | Chapter 9             |
| How is the Born–Oppenheimer separation, used repeatedly here (13.7, 13.9), justified quantitatively? | Chapter 9            |
| Why does vibrational relaxation (Kasha's rule, Section 13.11) happen so much faster than radiative decay? | Chapter 15 (statistical/collisional relaxation) |
| How are these transition rates and populations combined into macroscopic absorption coefficients and equilibrium constants? | Chapter 15 |
| How is a large molecule's full spectrum computed when no formula like $B=\hbar^2/2I$ is available? | Chapter 14            |
| How does the same contact mechanism reappear in transition-metal EPR and in catalytic mechanism studies? | Chapter 20            |

**Next:** Chapter 14 turns to computational chemistry. Every exact formula in this chapter — for a rigid rotor, a harmonic oscillator, a hydrogenic atom — existed only because the corresponding Schrödinger equation happened to separate. Most real molecules offer no such luck, and Chapter 14 builds the numerical methods that make quantum chemistry possible without one.
