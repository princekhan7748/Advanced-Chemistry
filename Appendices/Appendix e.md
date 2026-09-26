# Appendix E — Computational Chemistry Reference

*Reference*

A glossary and notation reference for the methods introduced in Chapter 14, collected here for lookup.

---

## E.1 Basis-set notation

A **basis set** is the finite collection of functions used to approximate molecular orbitals as linear combinations of atomic-orbital-like functions (Chapter 9, Chapter 14). Most practical basis sets use **Gaussian-type orbitals** ($e^{-\zeta r^2}$) rather than the exact hydrogenic **Slater-type orbitals** ($e^{-\zeta r}$, Chapter 6), because products of Gaussians remain Gaussian, making the required integrals far cheaper to evaluate; several Gaussians are then combined ("contracted") to mimic the correct cusp-and-decay shape of a Slater orbital.

| Notation | Meaning |
|---|---|
| Minimal basis (e.g. STO-3G) | One basis function per occupied atomic orbital, each a contraction of 3 Gaussians |
| Double-zeta (e.g. 6-31G) | Two basis functions per valence atomic orbital, allowing the orbital's size to adjust |
| Split-valence | Core orbitals get one function, valence orbitals get two or more (cheaper than doubling every orbital) |
| Polarization functions (e.g. 6-31G(d), 6-31G**) | Added higher-angular-momentum functions ($p$ on H, $d$ on heavy atoms) allowing orbitals to distort away from atomic symmetry, needed to describe bonding accurately |
| Diffuse functions (e.g. 6-31+G) | Added low-exponent, spatially broad functions, needed for anions, excited states, and weak intermolecular interactions (Chapter 20) |
| Correlation-consistent (e.g. cc-pVDZ, cc-pVTZ) | Systematically expandable basis families designed to converge smoothly toward the complete-basis-set limit as correlation methods (E.3) are improved |

Enlarging the basis set can only lower or leave unchanged a variational energy (Appendix B.6); it never raises it.

## E.2 Common density-functional approximations

Density functional theory (Chapter 14) replaces the many-electron wavefunction with the electron density $\rho(\mathbf{r})$ and approximates the exchange-correlation energy $E_{xc}[\rho]$, the one term in the exact theory with no closed form.

| Family | Example(s) | What it uses |
|---|---|---|
| Local density approximation (LDA) | SVWN | Density $\rho(\mathbf{r})$ only, from the uniform electron gas |
| Generalized gradient approximation (GGA) | PBE, BLYP | Density and its gradient $\nabla\rho$ |
| Meta-GGA | TPSS | Adds the kinetic-energy density |
| Hybrid | B3LYP, PBE0 | Mixes in a fixed fraction of exact Hartree–Fock exchange (Chapter 9) with a GGA |
| Range-separated hybrid | CAM-B3LYP, $\omega$B97X | Fraction of exact exchange varies with electron–electron separation, improving long-range behavior (charge-transfer states, dispersion-sensitive properties) |
| Dispersion-corrected | any of the above $+$ D3/D4 | Adds an empirical $-C_6/r^6$-type correction (Chapter 20) that standard functionals systematically underestimate |

No exchange-correlation functional is exact; each represents a specific, named approximation to the true many-body exchange-correlation energy (Chapter 9, in the spirit of the status labels used throughout the book).

## E.3 Wavefunction methods (hierarchy of approximation)

Ordered, approximately, from least to most computationally expensive and from least to most complete treatment of electron correlation (Chapter 9):

1. **Hartree–Fock (HF)** — mean-field theory; each electron moves in the averaged field of all others; captures exchange exactly but no correlation beyond that.
2. **Møller–Plesset perturbation theory (MP2, MP3, ...)** — treats electron correlation as a perturbation on the Hartree–Fock solution (Appendix B.5); MP2 is the most common low-cost correlated method.
3. **Configuration interaction (CI)** — expands the wavefunction as a linear combination of the Hartree–Fock determinant and determinants with one, two, or more electrons excited to virtual orbitals; full CI (all possible excitations) is exact within a given basis set but scales too steeply for all but the smallest systems.
4. **Coupled-cluster theory (CC, e.g. CCSD(T))** — exponentiates a cluster operator to include the effect of certain excitations to infinite order at a fraction of full CI's cost; CCSD(T) (singles, doubles, and perturbative triples) is often treated as the practical "gold standard" for benchmark accuracy on small molecules.

## E.4 Geometry optimization

Locating a stationary point on a potential-energy surface (Chapter 16) means finding a nuclear geometry where the gradient of the energy with respect to every nuclear coordinate vanishes,

$$
\frac{\partial E}{\partial \mathbf{R}_i} = 0 \quad \text{for every nucleus } i.
$$

Practical optimization algorithms use the gradient (and, for faster convergence, an approximate or exact second-derivative matrix, the **Hessian**) to step iteratively toward a stationary point, most commonly using quasi-Newton methods that update an approximate Hessian at each step rather than recomputing it from scratch.

## E.5 Frequency (Hessian) calculations

Diagonalizing the mass-weighted Hessian matrix at a stationary point gives the **normal-mode vibrational frequencies** (Chapter 5, Chapter 11) directly:

$$
\det\!\left(\frac{1}{\sqrt{m_im_j}}\frac{\partial^2E}{\partial R_i\partial R_j} - \omega^2\,\mathbb{1}\right) = 0.
$$

The number of **negative eigenvalues** (imaginary frequencies) classifies the stationary point (Chapter 16):

| Imaginary frequencies | Type of stationary point |
|---|---|
| 0 | Minimum (stable species: reactant, product, or intermediate) |
| 1 | First-order saddle point (transition state) |
| 2 or more | Higher-order saddle point — not usually chemically meaningful on its own |

A calculated transition state should always be confirmed by exactly one imaginary frequency whose associated displacement vector connects, qualitatively, the correct pair of minima.

## E.6 Glossary of common computational terms

| Term | Meaning |
|---|---|
| Ab initio | "From first principles" — a wavefunction method (E.3) using no empirically fitted parameters, as opposed to semi-empirical methods |
| Semi-empirical | A simplified quantum-chemical method (e.g. Hückel theory, Chapter 12) that replaces some integrals with parameters fitted to experimental or high-level computed data |
| Basis-set superposition error (BSSE) | An artificial stabilization of an intermolecular complex arising because each monomer can "borrow" extra basis functions from its partner; commonly corrected with the counterpoise method |
| Self-consistent field (SCF) | The iterative procedure (Chapter 9) by which Hartree–Fock or Kohn–Sham DFT orbitals are refined until the field they generate reproduces the field used to construct them |
| Potential energy surface (PES) | The energy of a system as a function of nuclear coordinates (Chapter 16), within the Born–Oppenheimer approximation (Chapter 9) |
| Zero-point energy (ZPE) | The residual vibrational energy remaining at $0\ \mathrm{K}$ from each normal mode (Chapter 5), $\sum_k \tfrac12\hbar\omega_k$, which must be added to a bare electronic energy for a meaningful comparison with experiment |
| Solvent (continuum) model | An implicit treatment of solvent as a polarizable dielectric continuum (Chapter 20) surrounding the solute, rather than as explicit solvent molecules |
| Convergence | The state in which an iterative procedure (SCF, geometry optimization) has changed by less than a specified numerical threshold between successive steps |

---

**See also:** Appendix D (units in which computed energies, most often reported in hartree, must be converted for comparison with experimental thermochemical data) and Chapter 14 (the derivation and motivation for each method summarized here).
