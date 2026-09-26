# Chapter 1 — The Experimental Failure of Classical Physics

*Part I · The Quantum Structure of Matter*

Quantum mechanics was not chosen because it is elegant. It was forced on physicists, one experiment at a time, by measurements that classical physics could not reproduce. This chapter follows that evidence. By the end, the postulates of Chapter 2 should look like the *minimum* needed to explain what nature does.

**Roadmap.** Each experiment removes one classical assumption. Sections 1.2–1.4 attack continuous energy, 1.5–1.6 the classical atom, 1.7–1.8 the separation of waves and particles, and 1.9–1.11 reveal internal quantum states. Section 1.12 draws the conclusion:

$$
\boxed{
\begin{array}{c}
\text{Continuous energy fails}\\
\downarrow\\
\text{Classical atom fails}\\
\downarrow\\
\text{Light and matter require dual descriptions}\\
\downarrow\\
\text{Internal quantum states appear}\\
\downarrow\\
\text{Classical trajectories cease to be fundamental}\\
\downarrow\\
\text{A new mathematical mechanics is required}
\end{array}}
$$

**Status labels.** Every important principle in this book is classified with one of four labels:

| Status | Meaning |
|---|---|
| **Fundamental** | Follows from the underlying theory |
| **Derived** | Mathematical or physical consequence of fundamental principles |
| **Approximate** | Depends on simplifying assumptions |
| **Empirical** | Established from observation rather than derived from the current theory |

---

## 1.1 Classical physics and its domain

Classical physics rests on a few assumptions that are so natural they go unstated:

- **Deterministic trajectories:** Newton's law $\mathbf F = m\ddot{\mathbf r}$ fixes $\mathbf r(t)$ from initial conditions.
- **Fields and waves:** Maxwell's equations describe light as a continuous wave; energy is spread over the wavefront.
- **Particles and waves are different things:** a particle is localized, a wave is extended.
- **Continuity:** energy, angular momentum and their orientations can take any value.
- **Gentle measurement:** observing a system can, in principle, be done without disturbing it.

This framework is superb for planets, engines and radio antennas. Its domain is large objects, where the action is enormous compared with Planck's constant $h$. The experiments below probe systems where it is not.

---

## 1.2 Black-body radiation

A cavity at temperature $T$ fills with thermal radiation. Classically, the field is a set of standing-wave modes, and equipartition gives each mode average energy $k_BT$. The number of modes per unit volume per unit frequency grows as $\nu^2$, giving the Rayleigh–Jeans law:

$$
u(\nu,T)=\frac{8\pi\nu^2}{c^3}\,k_BT
$$

This matches experiment at low frequency but grows without bound at high frequency, so the total energy diverges: the **ultraviolet catastrophe**. Real cavities glow with a finite spectrum that peaks and then falls.

Planck (1900) removed the divergence by allowing each mode of frequency $\nu$ only the energies

$$
E_n = nh\nu, \qquad n = 0, 1, 2, \dots
$$

Weighting these by the Boltzmann factor $e^{-E_n/k_BT}$ gives the average mode energy and the Planck distribution:

$$
\langle E\rangle=\frac{\sum_n nh\nu\,e^{-nh\nu/k_BT}}{\sum_n e^{-nh\nu/k_BT}}=\frac{h\nu}{e^{h\nu/k_BT}-1}
$$

$$
u(\nu,T)=\frac{8\pi h\nu^3}{c^3}\,\frac{1}{e^{h\nu/k_BT}-1}
$$

**Classical limit.** When $h\nu \ll k_BT$, the expansion $e^x \approx 1+x$ gives $\langle E\rangle \to k_BT$, recovering Rayleigh–Jeans. When $h\nu \gg k_BT$, $\langle E\rangle \approx h\nu\,e^{-h\nu/k_BT} \to 0$: high-frequency modes are "frozen out" because a single quantum costs more than the thermal energy available.

The fitted constant is $h = 6.626\times10^{-34}$ J s. The peak obeys Wien's law, $\lambda_{\max}T = 2.898\times10^{-3}$ m K; for the Sun (5772 K) this gives about 502 nm.

**Lesson:** energy exchange with radiation is not continuous. The Boltzmann weighting used here returns in full in Chapter 15.

> **Status of the principle: Planck quantization, $E_n = nh\nu$**
> *Empirical* in this chapter: it was introduced to fit the spectrum. It becomes *Derived* later, from the harmonic-oscillator Schrödinger equation (Chapter 5) and the statistics of Chapter 15.

---

## 1.3 Photoelectric effect

Light striking a metal ejects electrons. Observations:

1. No emission below a **threshold frequency** $\nu_0$, however intense the light.
2. Above it, emission is essentially instantaneous.
3. The maximum kinetic energy of the electrons grows linearly with $\nu$ and does not depend on intensity.
4. Intensity only changes the *number* of electrons.

A classical wave predicts the opposite of (1)–(3): more intensity should mean more energy per electron, and dim light should need time to accumulate energy. Einstein (1905) proposed that light of frequency $\nu$ arrives in quanta (photons) of energy $h\nu$. One photon gives all its energy to one electron, which must pay the work function $\phi$:

$$
K_{\max} = h\nu - \phi, \qquad \nu_0 = \frac{\phi}{h}
$$

**Example.** Sodium has $\phi \approx 2.3$ eV $= 3.7\times10^{-19}$ J, so $\nu_0 \approx 5.6\times10^{14}$ Hz, i.e. $\lambda_0 \approx 540$ nm. Green-yellow light works; any amount of red light does not.

**Lesson:** light, a wave in interference experiments, delivers energy in indivisible packets.

> **Status of the principle: photon energy and the Einstein equation**
> The photon energy $h\nu$ is *Fundamental* (it is justified fully only by quantizing the electromagnetic field). The relation $K_{\max}=h\nu-\phi$ is *Derived* from it by energy conservation.

---

## 1.4 Atomic spectra

A hot solid emits a continuous spectrum. A hot, dilute gas emits only sharp lines at frequencies unique to each element. For hydrogen, Balmer found the visible lines, and Rydberg generalized the pattern:

$$
\frac{1}{\lambda}=R_H\left(\frac{1}{n_1^2}-\frac{1}{n_2^2}\right), \qquad n_2>n_1, \qquad R_H = 1.097\times10^{7}\ \text{m}^{-1}
$$

| Series | $n_1$ | Region |
|---|---|---|
| Lyman | 1 | Ultraviolet |
| Balmer | 2 | Visible |
| Paschen | 3 | Infrared |
| Brackett | 4 | Infrared |
| Pfund | 5 | Infrared |

For H$\alpha$ ($n_2 = 3$): $1/\lambda = R_H\left(\tfrac14-\tfrac19\right)$, so $\lambda = 656$ nm.

The Ritz combination principle says every line frequency is a difference of two "terms", $\nu = T(n_1) - T(n_2)$: the atom has discrete internal energy levels and emits the difference.

**Why classical physics fails.** A classical orbiting charge radiates at its orbital frequency and harmonics; as it loses energy the frequency drifts, so the emission should be a smooth continuum, not sharp lines whose frequencies bear no relation to any orbital frequency.

> **Status of the principle: Balmer/Rydberg formula**
> *Empirical.* It fits the data perfectly but explains nothing. Explaining it is the job of Chapter 6, which derives it from the Schrödinger equation.

---

## 1.5 Rutherford scattering

Thomson pictured the atom as a diffuse positive sphere with embedded electrons. Geiger and Marsden fired α-particles at gold foil. Nearly all passed through, but roughly one in ten thousand scattered through large angles, some backwards. A diffuse charge cannot deflect a fast α-particle that much, but a concentrated one can.

Rutherford (1911) concluded that the positive charge and almost all the mass sit in a **nucleus** of radius about $10^{-14}$ m inside an atom of about $10^{-10}$ m.

That model has a fatal flaw. Electrons must orbit to avoid falling in, but accelerated charges radiate (Larmor). Classical electrodynamics predicts the electron spirals into the nucleus in about $10^{-11}$ s. Atoms would not exist.

---

## 1.6 Bohr model

Bohr (1913) kept classical circular orbits and added one non-classical rule: angular momentum is quantized, $L = m_e v r = n\hbar$, and orbiting electrons do not radiate. Combining this with Coulomb force = centripetal force,

$$
\frac{m_e v^2}{r}=\frac{e^2}{4\pi\varepsilon_0 r^2},
$$

gives

$$
r_n = n^2 a_0, \qquad a_0=\frac{4\pi\varepsilon_0\hbar^2}{m_e e^2}=0.529\ \text{Å}, \qquad E_n=-\frac{13.6\ \text{eV}}{n^2}\quad (Z=1)
$$

A jump $n_2 \to n_1$ emits a photon with $h\nu = E_{n_2}-E_{n_1}$, which reproduces the Rydberg formula with

$$
R_\infty=\frac{m_e e^4}{8\varepsilon_0^2 h^3 c},
$$

matching the measured value. Hydrogen-like ions (He$^+$, Li$^{2+}$) work with $E_n = -13.6\,Z^2/n^2$ eV.

**Failures.** Bohr's model:

- cannot treat helium or any many-electron atom;
- predicts a ground state with $L=\hbar$ when the true value is zero;
- misses fine structure and line intensities;
- cannot explain molecules;
- gives no reason *why* $L$ should be quantized.

It is a bridge, not a theory.

> **Status of the principle: Bohr model**
> *Approximate and superseded.* The energies are right for hydrogen; the orbits are not real. Chapter 6 recovers the same energies without orbits.

---

## 1.7 Matter waves

If light, a wave, has particle character, de Broglie (1924) proposed that matter has wave character:

$$
\lambda=\frac{h}{p}
$$

This explains Bohr's rule: a standing wave around an orbit needs $2\pi r = n\lambda$, hence $L = pr = n\hbar$.

The wavelength of an electron accelerated through $V$ volts is $\lambda \approx 12.26/\sqrt{V}$ Å. At 100 V, $\lambda = 1.2$ Å, comparable to atomic spacings, so crystals should diffract electrons. A 0.145 kg baseball at 40 m/s has $\lambda \approx 10^{-34}$ m, which is why we never see it.

**Davisson–Germer (1927).** Electrons of 54 eV ($\lambda = 1.67$ Å) scattered from nickel showed a sharp intensity peak at 50°. The Bragg-type condition $\lambda = d\sin\theta$ with $d = 2.15$ Å gives 1.65 Å, in agreement.

**G. P. Thomson** independently observed diffraction rings from electrons passing through thin foils. Electrons, the archetypal particles, diffract.

> **Status of the principle: de Broglie relation, $\lambda = h/p$**
> *Fundamental* postulate at this stage, supported by diffraction. Its place in the full theory is settled in Chapter 2, where momentum becomes an operator.

---

## 1.8 Compton scattering

A photon carries momentum $p = h/\lambda = h\nu/c$. Compton (1923) scattered X-rays from electrons and found the scattered radiation had a longer wavelength that depended on angle. A classical wave would re-radiate at the same wavelength. Treating the event as a relativistic collision of two particles, with energy and momentum conserved, gives

$$
\Delta\lambda=\lambda'-\lambda=\frac{h}{m_e c}\,(1-\cos\theta), \qquad \frac{h}{m_e c}=2.426\ \text{pm}
$$

**Lesson:** together with the photoelectric effect, this settles that light carries energy and momentum in quanta. Together with de Broglie, it forces *wave–particle duality*: neither classical picture alone describes light or matter.

> **Status of the principle: Compton formula**
> *Derived* from photon momentum plus conservation of relativistic energy and momentum.

---

## 1.9 Stern–Gerlach experiment

An atom with magnetic moment $\boldsymbol\mu$ in a non-uniform field feels a force proportional to $\mu_z$. If orientations were continuous, a beam would smear into a band. Stern and Gerlach (1922) sent silver atoms through such a field and saw **two** distinct spots.

Two spots is doubly surprising:

- The orientation of a magnetic moment is discrete (space quantization).
- Silver's ground state ($4d^{10}5s^1$) has zero orbital angular momentum, and an orbital $l$ would give $2l+1$ (odd) components, never two.

The moment must come from an intrinsic angular momentum with two projections: **spin** $\tfrac12$. Spin is thus first an experimental fact, and only later (Chapter 7) a theoretical consequence.

> **Status of the principle: spin**
> *Empirical* in this chapter: two beam components observed, no explanation offered. Chapter 7 asks where spin comes from in the theory.

---

## 1.10 Franck–Hertz experiment

Franck and Hertz (1914) accelerated electrons through mercury vapor. The collector current rose with voltage, then dropped sharply near 4.9 V, and repeated dips appeared at multiples of 4.9 V.

- Below 4.9 eV the collisions are elastic.
- At 4.9 eV the electron loses all its energy by exciting a mercury atom.
- The excited atoms emitted UV light at 254 nm, exactly $hc/\lambda = 4.9$ eV.

Atoms accept energy only in discrete amounts, in direct support of the levels implied by spectra.

---

## 1.11 Zeeman and Stark effects

Placing atoms in a magnetic field splits spectral lines (Zeeman effect), and in an electric field it splits them differently (Stark effect). For the normal Zeeman effect the shift of a level with orbital magnetic quantum number $m_l$ is

$$
\Delta E = m_l\,\mu_B B, \qquad \mu_B=\frac{e\hbar}{2m_e}=9.274\times10^{-24}\ \text{J/T}\ \ (5.79\times10^{-5}\ \text{eV/T})
$$

The splitting proves that levels carry hidden orientation labels, and that the number of sublevels is finite. Many atoms show "anomalous" Zeeman patterns that only spin can explain. Each level is therefore a structured set of states, not a single energy.

---

## 1.12 The collapse of the classical picture

| Experiment | Classical assumption broken | New fact |
|---|---|---|
| Black-body | Continuous energy exchange | $E = nh\nu$ |
| Photoelectric | Light is only a wave | Photons, $h\nu$ |
| Atomic spectra | Continuous emission | Discrete levels |
| Rutherford | Stable classical atom | Nuclear atom needs new dynamics |
| Bohr / de Broglie | Matter is only a particle | $\lambda = h/p$ |
| Compton | Light lacks momentum | $p = h/\lambda$ |
| Stern–Gerlach | Continuous orientation | Spin, discrete projections |
| Franck–Hertz | Atoms absorb any energy | Discrete excitation |
| Zeeman / Stark | Single-valued levels | Structured sublevels |

The experiments do not merely reveal isolated anomalies. Together they show that the classical concepts of continuous energy, classical trajectories, fixed wave or particle identities, and continuously oriented angular momentum cannot serve as the fundamental description of microscopic matter. Planck's constant $h$ marks the scale at which these failures become visible, but it does not explain them. The old quantum theory (Planck, Einstein, Bohr) patched each failure without explaining it. What is needed is a new mechanics in which quantization emerges from the equations rather than being imposed:

$$
\boxed{\text{Classical description}}
\;\not\rightarrow\;
\boxed{\text{microscopic reality}}
$$

$$
\Downarrow
$$

$$
\boxed{\text{Quantum mechanics}}
$$

### What remains unexplained

| Open question from this chapter | Where it is resolved |
|---|---|
| Why energy and angular momentum are quantized | Chapters 2–4 |
| Why hydrogen has exactly the Bohr energies, without orbits | Chapter 6 |
| Where spin comes from | Chapter 7 |
| Why atoms with more than one electron behave as they do | Chapter 8 |
| How light and matter are described consistently as waves and particles | Chapters 2 and 13 |

**Next:** Chapter 2 builds the mathematical language: state vectors, operators, eigenvalues and the Schrödinger equation.
