# Appendix D — Physical Constants and Units

*Reference*

Values below follow the 2019 SI redefinition (CODATA recommended values), under which $h$, $e$, $k_B$ and $N_A$ are exact by definition and every other constant is measured relative to them.

---

## D.1 Fundamental constants (SI)

| Constant | Symbol | Value |
|---|---|---|
| Speed of light in vacuum | $c$ | $2.99792458\times10^8\ \mathrm{m\,s^{-1}}$ (exact) |
| Planck constant | $h$ | $6.62607015\times10^{-34}\ \mathrm{J\,s}$ (exact) |
| Reduced Planck constant | $\hbar=h/2\pi$ | $1.054571817\times10^{-34}\ \mathrm{J\,s}$ |
| Elementary charge | $e$ | $1.602176634\times10^{-19}\ \mathrm{C}$ (exact) |
| Electron rest mass | $m_e$ | $9.1093837015\times10^{-31}\ \mathrm{kg}$ |
| Proton rest mass | $m_p$ | $1.67262192369\times10^{-27}\ \mathrm{kg}$ |
| Avogadro constant | $N_A$ | $6.02214076\times10^{23}\ \mathrm{mol^{-1}}$ (exact) |
| Boltzmann constant | $k_B$ | $1.380649\times10^{-23}\ \mathrm{J\,K^{-1}}$ (exact) |
| Molar gas constant | $R=N_Ak_B$ | $8.314462618\ \mathrm{J\,mol^{-1}\,K^{-1}}$ |
| Vacuum electric permittivity | $\varepsilon_0$ | $8.8541878128\times10^{-12}\ \mathrm{F\,m^{-1}}$ |
| Bohr radius | $a_0$ | $5.29177210903\times10^{-11}\ \mathrm{m}$ |
| Hartree energy | $E_h$ | $4.3597447222071\times10^{-18}\ \mathrm{J}$ |
| Rydberg energy | $E_h/2$ | $2.1798723611035\times10^{-18}\ \mathrm{J}$ $=13.605693\ \mathrm{eV}$ |
| Fine-structure constant | $\alpha=\dfrac{e^2}{4\pi\varepsilon_0\hbar c}$ | $7.2973525693\times10^{-3}\ \approx\ 1/137.036$ |

## D.2 SI base units used in the book

| Quantity | SI unit | Symbol |
|---|---|---|
| Length | metre | m |
| Mass | kilogram | kg |
| Time | second | s |
| Electric current | ampere | A |
| Temperature | kelvin | K |
| Amount of substance | mole | mol |

Derived SI units used repeatedly: joule ($\mathrm{J=kg\,m^2\,s^{-2}}$, energy), newton ($\mathrm{N=kg\,m\,s^{-2}}$, force), pascal ($\mathrm{Pa=N\,m^{-2}}$, pressure), coulomb (C, charge), and the non-SI but universally used electronvolt, $1\ \mathrm{eV}=1.602176634\times10^{-19}\ \mathrm{J}$ (the energy gained by one elementary charge crossing a potential difference of one volt).

## D.3 Atomic units

Electronic-structure calculations (Chapter 9, Chapter 14) are conventionally carried out in **atomic units**, defined by setting

$$
\hbar = m_e = e = \frac{1}{4\pi\varepsilon_0} = 1.
$$

| Quantity | Atomic unit | SI equivalent |
|---|---|---|
| Length | bohr, $a_0$ | $5.29177\times10^{-11}\ \mathrm{m}$ |
| Energy | hartree, $E_h$ | $4.35974\times10^{-18}\ \mathrm{J} = 27.2114\ \mathrm{eV}$ |
| Mass | $m_e$ | $9.10938\times10^{-31}\ \mathrm{kg}$ |
| Charge | $e$ | $1.60218\times10^{-19}\ \mathrm{C}$ |
| Time | $\hbar/E_h$ | $2.41888\times10^{-17}\ \mathrm{s}$ |

In these units the hydrogen-atom ground-state energy (Chapter 6) is exactly $-\tfrac12\ E_h$, and the hydrogen 1s orbital's characteristic radius is exactly $a_0$ — the reason electronic-structure output is normally reported in hartree and bohr rather than joules and metres.

## D.4 Conversion factors between common energy units

| From \ to | eV | kJ mol$^{-1}$ | kcal mol$^{-1}$ | cm$^{-1}$ | hartree |
|---|---|---|---|---|---|
| 1 hartree | 27.2114 | 2625.50 | 627.509 | 219474.6 | 1 |
| 1 eV | 1 | 96.4853 | 23.0605 | 8065.54 | 0.0367502 |
| 1 kJ mol$^{-1}$ | 0.0103643 | 1 | 0.239006 | 83.5935 | $3.80880\times10^{-4}$ |
| 1 kcal mol$^{-1}$ | 0.0433641 | 4.184 | 1 | 349.755 | $1.59360\times10^{-3}$ |
| 1 cm$^{-1}$ | $1.23984\times10^{-4}$ | 0.0119627 | $2.85914\times10^{-3}$ | 1 | $4.55634\times10^{-6}$ |

The cm$^{-1}$ (wavenumber) column is the unit spectroscopists use directly (Chapter 13), related to energy by $E=hc\tilde\nu$ with $\tilde\nu$ the wavenumber; the kJ mol$^{-1}$ and kcal mol$^{-1}$ columns are the units thermodynamic and kinetic quantities (Chapters 15, 16, 20) are normally reported in.

## D.5 Other conversions used in the book

| Quantity | Conversion |
|---|---|
| Standard atmosphere | $1\ \mathrm{atm}=101{,}325\ \mathrm{Pa}$ (exact) |
| Thermochemical calorie | $1\ \mathrm{cal}=4.184\ \mathrm{J}$ (exact) |
| Ångström | $1\ \text{Å} = 10^{-10}\ \mathrm{m} = 1.88973\ a_0$ |
| Debye (dipole moment) | $1\ \mathrm{D} = 3.33564\times10^{-30}\ \mathrm{C\,m}$ |
| Room temperature (used throughout Ch. 15–16) | $T=298.15\ \mathrm{K}$, giving $RT=2.4789\ \mathrm{kJ\,mol^{-1}}=0.592\ \mathrm{kcal\,mol^{-1}}=k_BT/hc\approx207.2\ \mathrm{cm^{-1}}$ |

---

**See also:** Appendix E, which reports computed energies in hartree by default and gives the conversions needed to compare against experimental thermochemical or spectroscopic data in the units of this appendix.
