# Chapter 7 — Relativistic Quantum Mechanics, Spin and Statistics

*Part I · The Quantum Structure of Matter*

Chapter 6 ended by admitting defeat. The Schrödinger equation for hydrogen reproduces the gross spectrum without orbits, but it cannot explain why a beam of ground-state atoms splits in two in a Stern–Gerlach magnet, why the Balmer lines are not single lines but closely spaced multiplets, or why the electron's magnetic moment comes out almost exactly twice what orbital motion alone would give. Spin was inserted by hand in Section 6.14, an extra ticket, $m_s=\pm\tfrac12$, glued onto $(n,l,m)$ because experiment demanded it.

This chapter asks why. The Schrödinger equation treats space and time asymmetrically, second derivatives in space, only a first derivative in time, which cannot survive contact with special relativity. Building an equation that respects relativity forces spin into existence, together with its magnetic moment, its coupling to orbital motion, and a distinct problem the Schrödinger equation never had to face: negative-energy solutions. A second, independent argument, resting on relativity together with locality and positive energy rather than on the Dirac equation by itself, then explains why electrons must occupy each state at most once, and why an ordinary chair does not collapse into a point.

| Mathematical result | Chemical destination |
|---|---|
| Dirac equation, linear in $\partial/\partial t$ | Existence of spin as a necessity, not an add-on |
| Non-relativistic limit of the Dirac equation | $g_s\approx2$, the Pauli spin term |
| Negative-energy solutions | The positron; QED corrections to atomic spectra |
| $(1/c^2)$ corrections: kinetic, spin–orbit, Darwin | Fine structure; spin–orbit coupling in transition metals and heavy-element spectroscopy |
| $(Z\alpha)^2$ scaling of relativistic effects | Relativistic contraction of $s,p$ orbitals in heavy atoms: color of gold, liquidity of mercury, lanthanide/actinide chemistry |
| Spin–statistics theorem | Antisymmetry of the electronic wavefunction |
| Slater determinant | The working form of every many-electron wavefunction used from Chapter 8 onward |
| Pauli exclusion principle | Two electrons per orbital; shell structure; the periodic table |
| Degeneracy pressure from antisymmetry | Why bulk matter has a size at all |

**Roadmap.** Why a relativistic wave equation is needed, and why the naive one fails (7.1–7.2) → Dirac's equation and its structure (7.3–7.5) → what it reduces to at everyday atomic speeds: spin, magnetic moment, spin–orbit coupling (7.6–7.8) → relativistic effects across the periodic table (7.9) → the separate question of identical particles: the spin–statistics theorem, antisymmetry, Slater determinants, the Pauli principle, and why matter has bulk (7.10–7.14).

---

## 7.1 Why Schrödinger mechanics is insufficient

**The problem.** The time-dependent Schrödinger equation, $i\hbar\,\partial\psi/\partial t=\hat H\psi$, was built from the non-relativistic kinetic energy $E=p^2/2m$ (Section 2.9). It is first order in time but second order in space, $\hat H=-\hbar^2\nabla^2/2m+V$. Under a Lorentz transformation, space and time mix; an equation that treats them so differently cannot keep the same form in every inertial frame. It is not Lorentz invariant.

**The relativistic energy relation.** Special relativity replaces $E=p^2/2m$ with the exact relation for a free particle of mass $m$,

$$
E^2=p^2c^2+m^2c^4
$$

For $p\ll mc$ this reduces to $E\approx mc^2+p^2/2m$, the rest energy plus the familiar kinetic term, recovering Section 2.9 in the low-velocity limit. For an electron in a hydrogen-like ion, the characteristic speed scales as $v/c\sim Z\alpha$, where

$$
\alpha=\frac{e^2}{4\pi\varepsilon_0\hbar c}\approx\frac1{137}
$$

is the **fine-structure constant**, introduced here without derivation and justified by the sections that follow. For hydrogen ($Z=1$) this ratio is small, about $1/137$, which is why Chapter 6 worked as well as it did. For a heavy atom such as gold ($Z=79$), $Z\alpha\approx0.58$, and relativity is no longer a small correction (Section 7.9).

**What is needed.** An equation built from $E^2=p^2c^2+m^2c^4$ instead of its non-relativistic approximation, that reduces correctly to Chapter 6 at low $Z\alpha$ and remains consistent (a positive-definite probability density) at all speeds.
> **Status of the principle: the relativistic energy relation**
> *Fundamental.* It is the defining relation of special relativity, not a chemical result. Everything else in this chapter is a consequence of building quantum mechanics that respects it.

---

## 7.2 Klein–Gordon equation

**The naive route.** Replace $E\to i\hbar\,\partial/\partial t$ and $p\to-i\hbar\nabla$ directly in $E^2=p^2c^2+m^2c^4$:

$$
-\hbar^2\frac{\partial^2\psi}{\partial t^2}=\left(-\hbar^2c^2\nabla^2+m^2c^4\right)\psi
$$

This is the **Klein–Gordon equation**. It is Lorentz invariant, and it correctly reproduces $E^2=p^2c^2+m^2c^4$ for a plane wave $\psi\sim e^{i(\mathbf k\cdot\mathbf r-\omega t)}$.

**Two problems.**

1. **The equation is second order in time.** Both $\psi$ and $\partial\psi/\partial t$ must be specified as initial data, unlike the first-order Schrödinger equation, where $\psi(t=0)$ alone determines the future. The probability density built the usual way, $\rho=|\psi|^2$, is no longer conserved by this equation; the conserved current constructed from $\psi$ and $\partial\psi/\partial t$ is not positive-definite. A quantity that is meant to be a probability but can go negative is not a probability.
2. **Negative-energy solutions.** Squaring $E=\pm\sqrt{p^2c^2+m^2c^4}$ to get $E^2$ introduces spurious solutions with $E<0$ that the original linear relation for a physical particle never had. Nothing in the equation stops a particle from cascading down through negative-energy states, releasing infinite energy.

**Why this matters here.** The Klein–Gordon equation is the correct relativistic equation for spin-0 particles (and reappears in that role, with the negative-energy problem resolved by field quantization, outside this book's scope), but it is not the equation for the electron. The electron additionally carries angular momentum $\hbar/2$ that has no place in a single scalar function $\psi(\mathbf r,t)$. Both defects point to the same fix: an equation linear, not quadratic, in $\partial/\partial t$.
> **Status of the principle: Klein–Gordon equation**
> *Derived* from the relativistic energy relation by direct substitution, but *inapplicable* to the electron: it lacks spin and its probability density is not positive-definite.

---

## 7.3 Dirac's equation

**The strategy.** Dirac (1928) sought an equation linear in both $\partial/\partial t$ and $\nabla$, whose square reproduces $E^2=p^2c^2+m^2c^4$ exactly, so that Lorentz invariance and a positive probability density can both hold. Write

$$
E=c\,\boldsymbol\alpha\cdot\mathbf p+\beta mc^2
$$

for some coefficients $\alpha_x,\alpha_y,\alpha_z,\beta$ to be determined. Squaring this and demanding that it reduce to $E^2=p^2c^2+m^2c^4$, with no cross terms in $p_xp_y$ and so on, requires

$$
\alpha_i\alpha_j+\alpha_j\alpha_i=2\delta_{ij},\qquad
\alpha_i\beta+\beta\alpha_i=0,\qquad
\alpha_i^2=\beta^2=1
$$

**Why ordinary numbers cannot satisfy this.** Numbers commute, so $\alpha_i\alpha_j=\alpha_j\alpha_i$ for any ordinary $\alpha_i$, which would force $\alpha_i\alpha_j=0$ for $i\ne j$, incompatible with $\alpha_i^2=1$. The relations demand **anticommuting** objects: matrices, not numbers. The smallest matrices satisfying all four relations simultaneously are $4\times4$. Promoting $\psi$ to a four-component object, the **Dirac equation** is

$$
i\hbar\frac{\partial\psi}{\partial t}=\left(c\,\boldsymbol\alpha\cdot\hat{\mathbf p}+\beta mc^2\right)\psi
$$

or, in the manifestly covariant form using $\gamma^0=\beta,\ \gamma^i=\beta\alpha_i$,

$$
\left(i\hbar\gamma^\mu\partial_\mu-mc\right)\psi=0
$$

**What was purchased.** The equation is first order in time, so it has a genuinely positive-definite, conserved probability density $\rho=\psi^\dagger\psi$, curing the first defect of Section 7.2. The four components of $\psi$ were not put in to describe spin; they were forced in by the algebra of the $\alpha,\beta$ matrices. That spin appears at all is a consequence of demanding relativity and a sensible probability density simultaneously, not a separate assumption.
> **Status of the principle: the Dirac equation**
> *Fundamental*, in the sense that it is not derived from a deeper principle within non-relativistic quantum mechanics; it is the minimal linear equation consistent with special relativity and a positive probability density. Its physical consequences below (spin, $g_s\approx2$, fine structure) are *Derived* from it.

---

## 7.4 Dirac matrices

**A concrete representation.** Using the $2\times2$ Pauli matrices $\sigma_x,\sigma_y,\sigma_z$ (the operators whose eigenvalues gave $m_s=\pm\tfrac12$ the algebra it needed in Section 6.14) as building blocks, one standard choice is

$$
\beta=\begin{pmatrix}I&0\\0&-I\end{pmatrix},\qquad
\alpha_i=\begin{pmatrix}0&\sigma_i\\\sigma_i&0\end{pmatrix}
$$

with $I$ the $2\times2$ identity. Because these are $4\times4$, $\psi$ is a four-component **bispinor**,

$$
\psi=\begin{pmatrix}\psi_A\\\psi_B\end{pmatrix}
$$

where $\psi_A$ and $\psi_B$ are each two-component spinors. This block structure is not decoration: Section 7.6 shows that $\psi_A$ becomes the ordinary electron wavefunction (with its two spin states) in the low-speed limit, while $\psi_B$ becomes small and describes admixture of the negative-energy states introduced next.

**Anticommutation, restated.** In four-vector notation, $\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}$, where $\eta^{\mu\nu}=\text{diag}(1,-1,-1,-1)$ is the metric of special relativity. This single algebraic relation is the entire content of the "square root" construction of Section 7.3.
> **Status of the principle: Dirac matrix representation**
> *Derived* (a solution of the anticommutation algebra required in Section 7.3). The physical content is in the algebra, not in the particular $4\times4$ matrices chosen to represent it; other equivalent representations exist.

---

## 7.5 Positive and negative energy solutions

**The plane-wave spectrum.** Solving the free Dirac equation for a plane wave gives, as required, $E=\pm\sqrt{p^2c^2+m^2c^4}$: the linear construction did not remove the negative-energy branch present already in the Klein–Gordon equation (Section 7.2); it was unavoidable once the equation was built to reproduce $E^2=p^2c^2+m^2c^4$.

**Why this branch cannot simply be discarded.** Unlike the Klein–Gordon case, the Dirac probability density is well behaved, so the negative-energy states are legitimate, normalizable quantum states that an electron could in principle fall into by radiating photons, with no floor to stop it. Dirac's response (1930) was the **hole theory**: postulate that in the vacuum, every negative-energy state is already occupied (the "Dirac sea"). The Pauli principle (Section 7.13, needed here before it is otherwise derived) then forbids a positive-energy electron from falling into a filled state. A hole in the sea, the absence of a negative-energy, negative-charge electron, behaves as a particle of positive energy and positive charge: the **positron**.

**Confirmation.** Anderson observed the positron in cosmic-ray tracks in 1932, four years after the equation predicted it. Electron–positron pair production and annihilation are direct manifestations of the negative-energy branch; the modern account replaces the Dirac sea with quantum field theory, in which $\psi$ is an operator that can create particles and antiparticles directly, but the qualitative prediction, and the numerical value of $g_s$ obtained below, are unchanged.

**Relevance to this book.** Antimatter itself plays no further role in a chemistry text, but the correction it signals does: virtual electron–positron pairs and related quantum-electrodynamic (QED) effects contribute small additional shifts to atomic energy levels (the Lamb shift, of order $10^{-6}$ eV in hydrogen) beyond anything obtained from the Dirac equation alone. These are mentioned here only to be set aside: they are smaller than the fine-structure terms of Section 7.9 by roughly $\alpha$, and are not needed for chemistry at the level of this book.
> **Status of the principle: negative-energy solutions / the positron**
> *Derived* from the free-particle Dirac equation; confirmed experimentally. *Fundamental* physics (antimatter, QED) beyond the electron's own dynamics, included here only for completeness.

---

## 7.6 Non-relativistic limit

**Goal.** Recover Chapter 6 as an approximation, and see what is added. Write the bispinor as $\psi=e^{-imc^2t/\hbar}\begin{pmatrix}\phi\\\chi\end{pmatrix}$, separating out the large rest-energy phase. Substituting into the Dirac equation with an electrostatic potential $V(r)$ added ($i\hbar\partial_t\to i\hbar\partial_t-V$) gives two coupled equations for $\phi$ and $\chi$. For $E-V\ll mc^2$, the equation for $\chi$ shows $\chi\sim(v/c)\phi$: the lower component is small, order $v/c\sim Z\alpha$ smaller than $\phi$, which is why $\psi_B$ of Section 7.4 was called the "small component."

**Eliminating $\chi$.** Solving the $\chi$ equation for $\chi$ in terms of $\phi$ and substituting back, then expanding to leading order in $1/c^2$, gives an equation for the two-component $\phi$ alone:

$$
i\hbar\frac{\partial\phi}{\partial t}=\left[\frac{(\boldsymbol\sigma\cdot\hat{\mathbf p})^2}{2m}+V\right]\phi
$$

**The identity that produces spin.** Using the Pauli matrix identity $(\boldsymbol\sigma\cdot\mathbf A)(\boldsymbol\sigma\cdot\mathbf B)=\mathbf A\cdot\mathbf B+i\boldsymbol\sigma\cdot(\mathbf A\times\mathbf B)$ with $\mathbf A=\mathbf B=\hat{\mathbf p}$ gives $(\boldsymbol\sigma\cdot\hat{\mathbf p})^2=\hat p^2$ for a free particle, recovering exactly the Schrödinger kinetic energy of Section 2.9, now acting on a **two-component** $\phi$. This is the **Pauli equation**: the Schrödinger equation of Chapter 6, but for a spinor with an intrinsic two-valuedness built in.

**What this settles.** The two-component structure of $\phi$, and therefore $m_s=\pm\tfrac12$, was not assumed here as it was in Section 6.14; it appears automatically once the four-component Dirac bispinor is reduced to its dominant part at ordinary atomic speeds. Spin is not an extra postulate bolted onto non-relativistic quantum mechanics; it is what survives of the full relativistic description when $v\ll c$.
> **Status of the principle: electron spin**
> Was *Empirical* in Chapter 6 (inserted to match Stern–Gerlach and fine structure). It is now **Derived**: a necessary feature of any linear, Lorentz-invariant wave equation for the electron, appearing already at the level of the Dirac equation, before any statistics argument is invoked.

---

## 7.7 Magnetic moment

**Including a vector potential.** Repeating the reduction of Section 7.6 with the full electromagnetic coupling $\hat{\mathbf p}\to\hat{\mathbf p}-q\mathbf A$ produces, via the same Pauli identity, an extra term beyond the orbital one found in Section 6.11:

$$
i\hbar\frac{\partial\phi}{\partial t}=\left[\frac{(\hat{\mathbf p}-q\mathbf A)^2}{2m}+V-\frac{q\hbar}{2m}\boldsymbol\sigma\cdot\mathbf B\right]\phi
$$

Comparing the last term with the definition of a magnetic-moment energy, $-\boldsymbol\mu\cdot\mathbf B$, and writing $\mathbf S=\tfrac\hbar2\boldsymbol\sigma$ so that $\sigma=2\mathbf S/\hbar$,

$$
\boldsymbol\mu_s=-g_s\,\mu_B\,\frac{\mathbf S}{\hbar},\qquad g_s=2\ \text{exactly, at this order}
$$

**Why this matters.** In Section 6.14, $g_s\approx2.0023$ was reported as an experimental number with "no classical spinning charge reproduces it." The Dirac equation now delivers $g_s=2$ directly from the algebra of Section 7.3, with no adjustable parameter: the factor of two, twice the orbital gyromagnetic ratio of Section 6.11, is forced by exactly the same Pauli identity that produced spin itself in Section 7.6. The remaining discrepancy, $g_s-2\approx0.0023$, is the **anomalous magnetic moment**, a QED correction from the same virtual-particle physics mentioned in Section 7.5; it is far too small to matter for chemistry and is not pursued further here.
> **Status of the principle: $g_s\approx2$**
> Was *Empirical* in Chapter 6. It is now **Derived**: $g_s=2$ follows directly from the non-relativistic reduction of the Dirac equation. The correction beyond 2 is a separate, *Fundamental* QED effect, outside this book's scope.

---

## 7.8 Spin–orbit interaction

**Next order.** Carrying the $1/c^2$ expansion of Section 7.6 one term further (rather than stopping at the Pauli equation) produces, for a spherically symmetric potential $V(r)$, an additional term

$$
\hat H_{SO}=\frac1{2m^2c^2}\frac1r\frac{dV}{dr}\,\hat{\mathbf L}\cdot\hat{\mathbf S}
$$

**Physical picture.** In the electron's own rest frame, the nucleus appears to circle it, producing a magnetic field at the electron proportional to $\mathbf L$; this field then exerts a torque on the electron's own spin magnetic moment, giving an energy proportional to $\mathbf L\cdot\mathbf S$. A naive version of this argument, done without full relativistic care, overestimates the effect by a factor of 2; the correct factor of $\tfrac12$ in the formula above is the **Thomas precession** correction, a purely kinematic effect of the electron's accelerated, non-inertial rest frame. It emerges automatically from the Dirac reduction, with no separate argument required.

**Coupling the angular momenta.** Because $\hat H_{SO}$ mixes $\hat L_z$ and $\hat S_z$ eigenstates, $l$ and $s$ separately are no longer conserved; the conserved quantity is the total angular momentum $\hat{\mathbf J}=\hat{\mathbf L}+\hat{\mathbf S}$, with quantum number $j=l\pm\tfrac12$ (for $l>0$) or $j=\tfrac12$ (for $l=0$, where $\hat H_{SO}=0$ trivially since $\mathbf L=0$). Using $\mathbf L\cdot\mathbf S=\tfrac12[j(j+1)-l(l+1)-s(s+1)]\hbar^2$, the two values of $j$ for a given $l$ acquire different energies: the level splits.
> **Status of the principle: spin–orbit interaction**
> *Derived* from the Dirac equation at the next order in $1/c^2$ beyond the Pauli equation, including the Thomas-precession factor. It is a *relativistic* effect with no counterpart in the non-relativistic Hamiltonian of Chapter 6.

---

## 7.9 Relativistic corrections in atoms

**Assembling fine structure.** Three corrections of the same order, $(Z\alpha)^2$ relative to the Bohr energy, arise together from the full $1/c^2$ expansion of the Dirac equation: the relativistic correction to the kinetic energy ($T=\sqrt{p^2c^2+m^2c^4}-mc^2\ne p^2/2m$), the spin–orbit term of Section 7.8, and the **Darwin term**, a contact correction present only for $l=0$ that reflects *zitterbewegung*, a rapid, small-amplitude jitter of the electron's position that smears out its interaction with the nucleus. Combined, they reproduce the exact energy of the hydrogen Dirac equation to this order,

$$
E_{n,j}=-\frac{13.6\ \text{eV}\,Z^2}{n^2}\left[1+\frac{(Z\alpha)^2}{n}\left(\frac1{j+\tfrac12}-\frac3{4n}\right)\right]
$$

depending on $n$ and $j$ but, remarkably, not on $l$ separately: states of the same $n$ and $j$ but different $l$ (such as $2s_{1/2}$ and $2p_{1/2}$) remain degenerate at this order. (A still smaller QED effect, the Lamb shift of Section 7.5, does split them, at about $10^{-6}$ times the Bohr energy — far below chemical relevance.)

**Hydrogen: a small correction.** For $n=2$ in hydrogen, this fine-structure splitting is about $0.36$ cm$^{-1}$, exactly the effect flagged as unexplained at the end of Chapter 6 (Section 6.10). It is a small correction because $Z\alpha\approx1/137$ is small.

**Heavy atoms: no longer small.** The correction scales as $(Z\alpha)^2$, so it grows with the square of the nuclear charge. For an inner electron of gold ($Z=79$), $Z\alpha\approx0.58$ and relativistic effects reach tens of percent of the orbital energy — comparable to the non-relativistic energy itself.

| Effect | Physical origin | Chemical consequence |
|---|---|---|
| Relativistic $s,p_{1/2}$ orbital contraction | High electron speed near a large nuclear charge increases the effective mass $m/\sqrt{1-v^2/c^2}$, shrinking $\langle r\rangle$ of Section 6.9 | Gold's absorption of blue light (its color); mercury's low melting point (a poorly bonding, contracted $6s^2$ pair); the "inert pair effect" in heavy $p$-block elements |
| Indirect $d,f$ orbital expansion | Contracted $s,p$ orbitals screen the nucleus more effectively from outer $d,f$ electrons | Altered oxidation-state preferences and bonding in the lanthanides, actinides and late transition metals |
| Spin–orbit splitting | Section 7.8, scaling with $Z^4$ for inner shells | Spectroscopic term splitting (Chapter 8); heavy-atom photochemistry (intersystem crossing, phosphorescence) |

**The pattern to keep.** These are not new, independent "rules for heavy elements." They are the same $(Z\alpha)^2$ correction derived once, in Section 7.9, evaluated at large $Z$. A rule that looks like an exception for gold or mercury is ordinary relativistic quantum mechanics becoming numerically important, exactly the philosophy stated at the start of this book: no arbitrary exceptions, only approximations (here, the non-relativistic Hamiltonian of Chapter 6) reaching the edge of their domain of validity.
> **Status of the principle: fine structure and heavy-atom relativistic effects**
> *Derived* from the Dirac equation. *Approximate* as an expansion in $Z\alpha$: for the heaviest elements the expansion converges slowly, and a full relativistic (four-component Dirac–Fock) treatment is used in practice rather than a low-order correction.

---

## 7.10 Spin–statistics connection

**A different kind of question.** Everything so far follows from the single-electron Dirac equation. It explains why *one* electron has spin $\tfrac12$ and a magnetic moment. It says nothing yet about what happens when *two or more identical* electrons are present, which is the question left open at the very end of Section 6.14: why can an orbital hold at most two electrons?

**The claim, and what it does not rest on.** The **spin–statistics theorem** states that particles with half-integer spin (fermions, spin $\tfrac12,\tfrac32,\dots$) must have antisymmetric multi-particle wavefunctions under exchange, while particles with integer spin (bosons, spin $0,1,\dots$) must have symmetric ones. It is tempting to think this follows directly from the Dirac equation, since the Dirac equation is, after all, "the equation for spin-$\tfrac12$ particles." It does not. The single-particle Dirac equation of Section 7.3 says nothing about two-particle exchange symmetry; it is silent on the question entirely.

**What the theorem actually requires.** The proof (Fierz and Pauli, 1939–1940) uses relativistic quantum *field* theory, not single-particle quantum mechanics, and rests on three separate physical requirements holding together: Lorentz invariance, **microcausality** (measurements at spacelike-separated points cannot influence one another), and the existence of a lowest-energy (positive-definite) vacuum state. Under these three conditions, a field describing half-integer-spin particles is mathematically consistent only if quantized with anticommutation relations (forcing antisymmetric states), while an integer-spin field is consistent only with commutation relations (forcing symmetric states); the reversed assignment produces either negative probabilities or unbounded-below energies. The specific value of the spin, $\tfrac12$, is only used insofar as it is half-integer; the argument does not depend on the electron being described by the Dirac equation in particular.

**The distinction, stated plainly.**

$$
\text{Dirac equation}\ \ne\ \text{spin–statistics theorem}
$$

The Dirac equation is a statement about a single relativistic electron: it explains why the electron has spin $\hbar/2$ (Section 7.6) and predicts its magnetic moment (Section 7.7). The spin–statistics theorem is a separate, more general result about relativistic quantum field theory: it explains why *identical* half-integer-spin particles, whatever equation governs each one individually, must combine antisymmetrically. Historically Pauli first stated the exclusion principle (1925) as a bare empirical rule, years before Dirac's equation (1928) and over a decade before the general theorem bearing his name (1940) justified it from first principles. Within this book, the antisymmetry postulate of Section 7.11 is adopted as the working rule; readers should take away that its ultimate justification is a field-theoretic result about relativistic causality, not a feature of the Dirac equation itself.
> **Status of the principle: spin–statistics theorem**
> *Fundamental* — a general consequence of combining relativity, causality and stable (positive-energy) vacua in a quantum field theory, established independently of, and more broadly than, the Dirac equation for any one particle.

---

## 7.11 Fermions and antisymmetry

**The exchange operator.** Define $\hat P_{12}$ to swap the labels of particles 1 and 2 in a wavefunction: $\hat P_{12}\Psi(1,2)=\Psi(2,1)$. Since the particles are identical, exchanging them cannot change any observable, so $|\Psi(2,1)|^2=|\Psi(1,2)|^2$, meaning $\Psi(2,1)=e^{i\theta}\Psi(1,2)$ for some phase. Applying $\hat P_{12}$ twice returns the original labeling, so $e^{2i\theta}=1$, leaving only $e^{i\theta}=\pm1$.

**The assignment fixed by Section 7.10.** Electrons are spin-$\tfrac12$ fermions, so

$$
\Psi(2,1)=-\Psi(1,2)
$$

Every acceptable multi-electron wavefunction must be **antisymmetric** under exchange of any two electrons' full coordinates (space and spin together). Photons and other integer-spin particles take the opposite sign and are unrestricted in how many can occupy one state, the origin of laser light and Bose–Einstein condensation, phenomena outside this book's scope but worth naming as the road not taken by electrons.
> **Status of the principle: electron antisymmetry**
> *Fundamental*, following from the spin–statistics theorem (Section 7.10) applied to spin-$\tfrac12$ particles. Everything from here to the end of the chapter is a *Derived* consequence of this single postulate.

---

## 7.12 Slater determinants

**Building an antisymmetric function.** Suppose, as a first guess, that $N$ electrons simply occupy $N$ one-electron spin-orbitals $\chi_1,\dots,\chi_N$ (each a product of a spatial orbital like $1s$ from Chapter 6 and a spin function $\alpha$ or $\beta$). The naive product $\chi_1(1)\chi_2(2)\cdots\chi_N(N)$, a **Hartree product**, is not antisymmetric: swapping labels 1 and 2 gives a different function, not its negative.

**The determinant construction.** Slater's device builds the required antisymmetry automatically:

$$
\Psi(1,2,\dots,N)=\frac1{\sqrt{N!}}
\begin{vmatrix}
\chi_1(1)&\chi_2(1)&\cdots&\chi_N(1)\\
\chi_1(2)&\chi_2(2)&\cdots&\chi_N(2)\\
\vdots&\vdots&\ddots&\vdots\\
\chi_1(N)&\chi_2(N)&\cdots&\chi_N(N)
\end{vmatrix}
$$

Rows index electrons, columns index spin-orbitals. A determinant changes sign whenever two rows are swapped, which is exactly the exchange of two electrons' coordinates, so $\Psi$ is antisymmetric automatically, for any choice of one-electron functions $\chi_i$. The factor $1/\sqrt{N!}$ normalizes it.

**Two electrons: a worked case.** For helium's ground configuration, both electrons in $1s$ with opposite spin ($\chi_1=1s\alpha$, $\chi_2=1s\beta$):

$$
\Psi=\frac1{\sqrt2}\left[1s(1)\alpha(1)\,1s(2)\beta(2)-1s(2)\alpha(2)\,1s(1)\beta(1)\right]
=1s(1)\,1s(2)\cdot\frac1{\sqrt2}\left[\alpha(1)\beta(2)-\alpha(2)\beta(1)\right]
$$

The spatial part factors out because both electrons share the same spatial orbital; the antisymmetry is carried entirely by the spin singlet in brackets. This factorization is special to two electrons in one orbital and will not generally occur once more than one spatial orbital is involved (Chapter 8).

**Why this is the working tool of the rest of the book.** From Chapter 8 onward, every many-electron wavefunction used in this book, Hartree–Fock (Chapter 9), configuration interaction, and the qualitative pictures of bonding (Chapter 10), is built from Slater determinants or sums of them. The determinant is not a separate physical assumption; it is simply the general-purpose device for writing down *any* antisymmetric function of one-electron orbitals.
> **Status of the principle: Slater determinant**
> *Derived* — a mathematical construction guaranteed to satisfy the antisymmetry postulate of Section 7.11 for any choice of one-electron orbitals. It is not itself an independent physical law.

---

## 7.13 Pauli exclusion principle

**The consequence.** Suppose two of the spin-orbitals in the determinant of Section 7.12 are identical, $\chi_i=\chi_j$ for $i\ne j$. Two equal columns make the determinant vanish identically: $\Psi\equiv0$. A wavefunction that is identically zero describes a state with zero probability of ever occurring.

$$
\boxed{\text{No two electrons can occupy the same spin-orbital.}}
$$

This is the familiar statement of Section 6.14, now obtained as an automatic feature of the determinant, not asserted separately. An orbital ($1s$, say) can therefore hold at most two electrons, one with $m_s=+\tfrac12$ and one with $m_s=-\tfrac12$, since $(n,l,m,m_s)$ together label a spin-orbital and no two electrons may share all four values. This restores, with justification, the $2n^2$ shell capacity of Section 6.14.

**What is fundamental and what is a bookkeeping consequence.** Antisymmetry (Section 7.11) is the fundamental postulate; "no two electrons in the same spin-orbital" is the bookkeeping consequence of writing that antisymmetric state as a determinant. Restricting attention to configurations of distinct one-electron orbitals, as done from Chapter 8 onward, is a convenience of the single-determinant approximation, not a separate law of nature; the underlying and complete statement is always the antisymmetry of $\Psi$ itself.
> **Status of the principle: Pauli exclusion principle**
> Was *Empirical* through Chapter 6 (the two-per-orbital rule, inserted to match observed shell structure). It is now **Fundamental**, in the sense of following necessarily, via the spin–statistics theorem, from relativity, causality and the existence of a stable vacuum — though its immediate derivation here, via the vanishing determinant, is a *Derived* mathematical consequence of antisymmetry.

---

## 7.14 Why matter does not simply collapse

**The question.** Nothing said so far seems to forbid every electron in a large piece of matter from falling into the lowest-energy orbital simultaneously, releasing an enormous amount of energy and collapsing every atom, and the bulk material built from them, to a size set only by nuclear dimensions. This does not happen, and the reason is a direct, macroscopic consequence of Sections 7.11–7.13.

**Inside one atom.** Antisymmetry already forces electrons in an atom beyond helium to occupy successively higher orbitals (Chapter 8 works out the details of the ordering), each with more radial or angular nodes (Section 6.7) and hence higher kinetic energy (Section 3.2). An atom's size is set by the highest occupied shell, not by $1s$ alone, because the Pauli principle keeps most of the electrons out of $1s$.

**Between atoms.** The same mechanism operates when atoms are pushed together. As two atoms approach, their electron clouds begin to overlap; if the electrons obeyed no exclusion principle, all of them could pool into the lowest combined orbital, and the energy would fall monotonically as the atoms merge, with nothing to stop the collapse. Because electrons are fermions, however, only two can occupy the lowest combined orbital; the rest are forced into higher orbitals whose kinetic energy rises steeply (again, the particle-in-a-box scaling of Section 3.2, now with a box shrinking as the atoms approach) as the available volume shrinks. This rapidly rising kinetic energy, known as **degeneracy pressure** when analyzed for a bulk collection of fermions, opposes further compression and is the reason a solid resists being squeezed: not primarily electrostatic repulsion between electrons (which is comparatively weak and, in any case, attractive toward the nuclei), but the kinetic-energy cost of confining fermions into a smaller volume while respecting the Pauli principle.

**The counterfactual, made concrete.** A rigorous argument along these lines (Dyson and Lenard, 1967, building on the physical picture above) shows that ordinary matter has a stable *volume proportional to the number of particles* precisely because electrons are spin-$\tfrac12$ fermions. Were electrons instead bosons, with no restriction on multiple occupancy of one orbital, the analogous calculation shows that bulk matter would collapse to a size shrinking with the number of particles, releasing energy that grows faster than linearly with system size, and ordinary chemistry, and ordinary matter, could not exist in a stable form.

**The synthesis of this chapter.** A single relativistic electron obeying the Dirac equation has spin and a magnetic moment (Sections 7.6–7.7) and, via the separate spin–statistics theorem, must combine antisymmetrically with every other electron (Sections 7.10–7.11). The two results are logically independent, yet chemistry needs both: the first gives every electron its intrinsic angular momentum; the second dictates how many electrons of that kind can share a state. Together they explain not only the shell structure glimpsed empirically in Chapter 6, but why matter has bulk at all.

$$
\boxed{\text{relativity (Dirac)}\ +\ \text{spin–statistics theorem}\ \longrightarrow\ \text{stable, extended matter}}
$$

> **Status of the principle: stability of matter**
> *Derived*, ultimately, from the antisymmetry of the electronic wavefunction (Section 7.11) together with the kinetic-energy cost of spatial confinement (Section 3.2). The full mathematical proof of bulk stability is beyond this book's scope; the qualitative mechanism, degeneracy pressure resisting compression, is not.

---

## What remains unexplained

| Open question | Where it is resolved |
|---|---|
| Given that $2s$ and $2p$ are no longer degenerate once a second electron is present, which orbital fills first, and why? | Chapter 8 |
| What is the physical origin of Hund's rule, and how does the exchange term implicit in the Slater determinant of Section 7.12 produce it? | Chapter 8 |
| How is a Slater determinant actually optimized to approximate a real many-electron atom or molecule? | Chapter 9 (Hartree–Fock) |
| What is lost by using a single Slater determinant, and how is it recovered? | Chapter 9 (electron correlation) |
| How do spin–orbit-split atomic states combine into molecular term symbols and selection rules? | Chapter 13 |
| How does the relativistic contraction of Section 7.9 change bonding and reactivity in heavy-element and transition-metal chemistry? | Chapters 10 and 20 |
| Why do only two electrons, not more, ever occupy one *spatial* molecular orbital in ordinary bonding? | Chapter 10 |

**Next:** Chapter 8 puts the antisymmetric many-electron wavefunction of this chapter to work. With the Pauli principle now derived rather than assumed, and the Slater determinant available as its working expression, the next task is to see what a second electron does to hydrogen's exact energy levels, why shielding and penetration (previewed in Section 6.6) split $2s$ from $2p$, and how exchange, made explicit in Section 7.12, gives rise to Hund's rule and the structure of the periodic table.
