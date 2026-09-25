# Chapter 12 — Hückel Theory and Conjugated Systems

*Part I · The Quantum Structure of Matter*

Two debts are due. Section 3.5 built the free-electron box model of polyenes, got the *trend* right, and named its own failure: the box ignores bond alternation and electron repulsion, and predicts that the HOMO–LUMO gap of an arbitrarily long chain falls to zero, which real polyenes do not do. Section 4.2 placed six $\pi$ electrons on a ring and found the level pattern $1,2,2,1$; Section 11.8 showed that this pattern is fixed by the point group $C_6$ alone, with no equation solved, but it did not fix the energies or say why six electrons is the closed-shell number.

The opening question:
> **Why is benzene, with three "double bonds," a single molecule with six identical C–C bonds and an unusual stability, while cyclobutadiene, built the same way, is not?**

**Three expectations from earlier chapters, and where each needs sharpening.**

- *A conjugated chain is a box* (Section 3.5): right trend, wrong asymptotic behavior.
- *A ring's degeneracy pattern is fixed by symmetry* (Section 11.8): true, but symmetry alone gives no energies and no argument for why $N=6$ is special and $N=4$ is not.
- *A double bond is a bond*: benzene has no distinct single and double C–C bonds by any measurement, so this natural language breaks down for conjugated systems specifically, though it remains a good approximation for isolated double bonds (Chapter 10).

Hückel theory replaces the box with atomic $2p_z$ orbitals, one per carbon, coupled through Chapter 10's molecular-orbital construction restricted to a minimal case. It is deliberately crude, and Section 12.7 states exactly where that shows.

| Mathematical result                                        | Chemical destination                                              |
| ------------------------------------------------------------ | ------------------------------------------------------------------- |
| Secular equations for a linear combination of $2p_z$ orbitals | $\pi$-molecular orbitals of a conjugated system                    |
| Eigenvalues $x_k=2\cos\theta_k$ of a chain/ring               | $\pi$ energy levels of polyenes and monocyclic rings                |
| Eigenvectors $c_{k,r}$                                       | Electron density and bond order at each atom and bond               |
| Closed-shell eigenvalue sum below the free-atom reference    | Delocalization ("resonance") energy                                |
| Degeneracy of $\cos\theta_k$ for $\pm\theta_k$               | The $1,2,2,1,\dots$ pattern of Section 11.8, now with energies      |
| Gap of a closed-shell ring versus an open-shell one           | The $4n+2$ rule; aromaticity and antiaromaticity                   |
| Alternant-molecule pairing theorem                            | Zero net charge on alternant hydrocarbons; the allyl system         |
| Gap that survives as $N\to\infty$ for an alternating chain     | Repair of the Section 3.5 asymptotic failure; the origin of conducting versus insulating polymers |

**Roadmap.** The orbital basis and the approximations that define the model (12.1) → the secular problem (12.2) → linear chains (12.3) → rings and the $4n+2$ rule (12.4) → charge and bond order, the allyl system (12.5) → where the box model is repaired: bond alternation (12.6) → where Hückel theory itself fails (12.7).

---

## 12.1 The $\pi$-electron approximation

**Setting up the problem correctly first.** A planar conjugated molecule such as benzene or butadiene has $\sigma$ bonds, built from $sp^2$ hybrids as in Chapter 10, holding the framework rigid and planar. Each carbon carries one more valence orbital, a $2p_z$ orbital perpendicular to the molecular plane. These $2p_z$ orbitals do not mix with the in-plane $\sigma$ system by symmetry: in the point group of a planar molecule (Section 11.5), $p_z$ is antisymmetric under reflection in the molecular plane while every $\sigma$ orbital is symmetric, so every matrix element between a $\pi$ and a $\sigma$ orbital vanishes by the vanishing theorem of Section 11.7. **The $\sigma$–$\pi$ separation is exact by symmetry for a planar molecule**, and it is this separation, not a guess, that licenses treating the $\pi$ electrons on their own.

**The approximations that are not exact.** Three further steps are needed before a soluble problem remains, and each is a genuine approximation with the status *Approximate*:

1. **One electron at a time**, in an averaged field of the rest — the same orbital approximation used for atoms in Chapter 8 and formalized in Chapter 9.
2. **Only nearest-neighbor atomic orbitals overlap or interact.** A $2p_z$ orbital on atom $r$ is taken to overlap and couple only with its immediately bonded neighbors, not with atoms further away.
3. **Overlap is neglected outright** in writing the basis as orthonormal ($\int\phi_r\phi_s\,d\tau=\delta_{rs}$), even though adjacent $2p_z$ orbitals do overlap physically. This is purely a simplification of the algebra (Section 12.2 shows what it removes), not a claim that the overlap is small.

**The trial wavefunction.** Following the LCAO construction of Chapter 10, each $\pi$ molecular orbital is built from the $N$ atomic $2p_z$ orbitals $\phi_1,\dots,\phi_N$ (one per conjugated carbon):

$$
\psi=\sum_{r=1}^{N}c_r\phi_r
$$

and the coefficients $c_r$ and energies $E$ are found from the variational principle (to be derived in Chapter 9, used here as in Section 6.9's variational estimate): minimizing $E=\langle\psi|\hat H|\psi\rangle/\langle\psi|\psi\rangle$ over the $c_r$.
> **Status of the principle: $\sigma$–$\pi$ separation**
> *Derived*, for a planar molecule, from the antisymmetry of $p_z$ under the molecular-plane reflection (Section 11.7). The one-electron, nearest-neighbor and zero-overlap steps that follow it are each *Approximate*.

---

## 12.2 The secular equations

**From the variational principle to a matrix problem.** Setting $\partial E/\partial c_r=0$ for every $r$ (the same procedure that produces the secular determinant in any linear variational problem) gives, for each $r$,

$$
\sum_{s=1}^{N}c_s\left(H_{rs}-ES_{rs}\right)=0,\qquad H_{rs}=\int\phi_r\hat H\phi_s\,d\tau,\quad S_{rs}=\int\phi_r\phi_s\,d\tau
$$

a nontrivial solution requires the secular determinant to vanish, $\det(H_{rs}-ES_{rs})=0$. Hückel theory assigns numbers to $H_{rs}$ by the approximations of Section 12.1:

$$
H_{rr}=\alpha\ \text{(the same for every carbon)},\qquad
H_{rs}=\beta\ \text{if }r,s\text{ bonded},\qquad H_{rs}=0\ \text{otherwise}
$$
$$
S_{rr}=1,\qquad S_{rs}=0\ (r\neq s)
$$

$\alpha$, the **Coulomb integral**, is the energy of an electron in an isolated $2p_z$ orbital; $\beta$, the **resonance integral**, is negative (bonding lowers energy, as in Chapter 10) and is the sole parameter controlling all splittings. With $S_{rs}=\delta_{rs}$ the problem is an ordinary eigenvalue equation,

$$
\mathbf{Hc}=E\mathbf{c},\qquad H_{rr}=\alpha,\ H_{rs}=\beta\ (\text{bonded})
$$

It is standard to write $E=\alpha+x\beta$ and solve $\det(\mathbf{A}-x\mathbf{I})=0$ for the dimensionless matrix $\mathbf A$, whose entries are $1$ for bonded pairs and $0$ otherwise. Because $\beta<0$, the *most negative* $x$ (i.e., the largest positive $x$ as conventionally tabulated) is the lowest energy.

**Ethylene, minimal check.** $N=2$, one bond: $\det\begin{pmatrix}-x&1\\1&-x\end{pmatrix}=x^2-1=0$, so $x=\pm1$, giving $E_\pm=\alpha\pm\beta$. This is exactly the two-orbital result of Section 11.7 ($E_\pm=(\alpha_a+\alpha_b)/2\pm\sqrt{(\cdots)^2+\beta^2}$ with $\alpha_a=\alpha_b=\alpha$), confirming that Hückel theory is that general MO framework specialized to identical, nearest-neighbor-coupled $2p_z$ orbitals. Two electrons fill $E_+=\alpha+\beta$, giving $\pi$ energy $2\alpha+2\beta$.
> **Status of the principle: Hückel secular problem**
> *Approximate.* It is the exact variational eigenvalue problem (*Derived*, Chapter 9) of the approximate Hamiltonian matrix defined by the assumptions of Section 12.1.

---

## 12.3 Linear polyenes

**The chain matrix.** For $N$ atoms in a line, $\mathbf A$ has $1$ on the two off-diagonals and $0$ elsewhere. This is a standard tridiagonal eigenvalue problem, with solution

$$
x_k=2\cos\left(\frac{k\pi}{N+1}\right),\qquad k=1,2,\dots,N,\qquad
c_{k,r}=\sqrt{\frac{2}{N+1}}\,\sin\!\left(\frac{k r\pi}{N+1}\right)
$$

**This is the particle-in-a-box, discretized.** Compare the box wavefunction of Section 3.2, $\psi_n(x)\propto\sin(n\pi x/L)$: the coefficient pattern $c_{k,r}\propto\sin(kr\pi/(N+1))$ is the same sine standing wave, sampled only at the $N$ atomic sites instead of every point of a continuum. The continuous box of Section 3.5 is recovered as the small-$\theta_k$, large-$N$ limit of this discrete chain, and this is why that box model captured the right *trend*.

**Butadiene ($N=4$).**

$$
x_k=2\cos\frac{k\pi}5,\qquad x=1.618,\ 0.618,\ -0.618,\ -1.618
$$

Four $\pi$ electrons fill $k=1,2$: $\pi$ energy $=2(\alpha+1.618\beta)+2(\alpha+0.618\beta)=4\alpha+4.472\beta$. Compare two isolated ethylenes, $2(2\alpha+2\beta)=4\alpha+4\beta$: butadiene is lower by $0.472|\beta|$, the **delocalization energy**, the energy gained by letting electrons spread over four atoms instead of being confined to two separate double bonds.

**Fitting $\beta$.** The HOMO–LUMO gap is $\Delta E=x_{N/2}\beta-x_{N/2+1}\beta=4|\beta|\sin[\pi/(2(N+1))]$ (using $\cos A-\cos B$ trigonometric identities). Butadiene absorbs at 217 nm, giving $\Delta E=5.71$ eV and

$$
|\beta|=\frac{5.71\ \text{eV}}{2\times1.618-2\times0.618}=\frac{5.71}{1.236}\approx4.6\ \text{eV}
$$

Using this single empirically fitted number, the model can now be tested predictively on longer chains:

| Molecule             | $N$ | Hückel $\lambda$ (this $\beta$) | Experiment | Section 3.5 box model |
| --------------------- | --- | -------------------------------- | ---------- | ---------------------- |
| 1,3-Butadiene         | 4   | 217 nm (fitted)                  | 217 nm     | 207 nm                 |
| 1,3,5-Hexatriene      | 6   | 301 nm                           | 258 nm     | 332 nm                 |
| 1,3,5,7-Octatetraene  | 8   | 386 nm                           | 290 nm     | 460 nm                 |
| $\beta$-Carotene ($N\approx22$) | 22 | 983 nm                  | 450 nm     | 1360 nm                |

Fitted to one molecule, Hückel theory is directionally closer than the box for the next two members but still overshoots badly for long chains, and for the same reason the box did: $x_{N/2}-x_{N/2+1}=4\sin[\pi/(2(N+1))]\to 2\pi/(N+1)\to0$ as $N\to\infty$ — a uniform-$\beta$ chain, like a uniform box, predicts a gap closing to zero. Section 12.6 identifies the missing physics.
> **Status of the principle: Hückel chain energies**
> *Derived* as the exact eigenvalues of the Hückel chain matrix; *Approximate* as a description of any real polyene, since $\alpha$ and $\beta$ are treated as constants along the whole chain (examined further in Sections 12.6–12.7).

---

## 12.4 Monocyclic rings and the $4n+2$ rule

**The ring matrix.** Closing the chain into a ring adds one bond between atoms $1$ and $N$. The eigenvalues become

$$
x_k=2\cos\left(\frac{2k\pi}{N}\right),\qquad k=0,\pm1,\pm2,\dots
$$

**Recovering Section 11.8 with numbers attached.** For $k$ and $-k$, $\cos(2k\pi/N)=\cos(-2k\pi/N)$: every level with $k\neq0$ (and $k\neq N/2$ for even $N$) is doubly degenerate. This is exactly the irrep-dimension argument of Section 11.8 (the $C_N$ rotation multiplies the coefficient pattern $e^{2\pi ikr/N}$ by a phase, so $\pm k$ pair into a two-dimensional irrep), now carrying an explicit energy $2\beta\cos(2k\pi/N)$. Benzene ($N=6$):

$$
x=2,\ 1,\ 1,\ -1,\ -1,\ -2\qquad\Longrightarrow\qquad\text{degeneracy pattern } 1,2,2,1
$$

exactly as anticipated in Section 11.8, now ordered by energy: one level at $\alpha+2\beta$, two degenerate at $\alpha+\beta$, two degenerate at $\alpha-\beta$, one at $\alpha-2\beta$.

**Why $N=6$ closes a shell and $N=4$ does not.** Level $k=0$ is single. Levels $\lvert k\rvert=1,2,\dots$ come in degenerate pairs, until, if $N$ is even, the top level $k=N/2$ is single again. With one $\pi$ electron per carbon (the neutral case) there are $N$ electrons to place, two per level:

- If $N=4n+2$, the pattern of level widths is $1,2,2,\dots,2,1$ and $N=4n+2$ electrons exactly fill the lowest $(2n+1)$ levels — one non-degenerate level plus $n$ full degenerate pairs — leaving no partially filled degenerate pair. The result is a **closed-shell** configuration with a nonzero HOMO–LUMO gap, verified numerically for $N=6,10,14$.
- If $N=4n$ (as in cyclobutadiene, $N=4$), the last two electrons must be split between a degenerate pair of orbitals, one electron in each (by the exchange argument previewed in Chapter 8's Hund's rule, and derived properly there). Numerically: $x=2,0,0,-2$ for cyclobutadiene, and the two non-bonding orbitals at $x=0$ each take one electron. This is an **open-shell** ring, reactive and not aromatic in the ordinary sense.

This is the origin of the **$4n+2$ rule** (Hückel's rule): only $N=4n+2$ monocyclic, fully conjugated rings close a shell at the "one $\pi$ electron per atom" filling. It sharpens the shell-count idea of the particle-on-a-ring model of Section 4.2 (which gave the same degeneracy pattern with no chemical mechanism attached) into a specific, checkable count of electrons.

**Resonance energy, benzene versus its open-chain isomer.** Filling benzene's six electrons: $\pi$ energy $=2(\alpha+2\beta)+4(\alpha+\beta)=6\alpha+8\beta$. The corresponding open chain (hexatriene, $N=6$) has $\pi$ energy $6\alpha+6.988\beta$. Benzene is lower by

$$
8\beta-6.988\beta=1.012\,\lvert\beta\rvert
$$

Using the fitted $\lvert\beta\rvert\approx4.6$ eV, this is about $4.7$ eV, or roughly $450$ kJ mol$^{-1}$. Experimental thermochemical estimates of the resonance energy of benzene relative to a hypothetical "cyclohexatriene" are of order $150$–$170$ kJ mol$^{-1}$, smaller than this simple Hückel number by roughly a factor of three — an overestimate typical of the uniform-$\beta$, no-repulsion model, not a coincidence, and it is quantified again in Section 12.7. Cyclobutadiene, by contrast, is calculated to be $0.47|\beta|$ *higher* in $\pi$ energy than two isolated ethylenes with the same bond count — a **destabilization**, consistent with cyclobutadiene's observed extreme reactivity and its tendency to distort away from a square geometry (a Jahn–Teller-type distortion of exactly the kind derived in Section 11.8, since its open-shell configuration is orbitally degenerate).
> **Status of the principle: the $4n+2$ rule**
> *Derived* within Hückel theory: it follows from the pairing $x_{\pm k}$ of ring eigenvalues (itself *Derived* from the $C_N$ symmetry of Section 11.8) together with one-electron-per-atom filling. Whether a given real molecule is aromatic by this count depends on the Hückel approximations of Section 12.1, so applying the rule to a specific molecule is *Approximate*.

---

## 12.5 Charge density, bond order, and the allyl system

**What the coefficients mean.** In the LCAO wavefunction the $\pi$-electron density on atom $r$, summed over occupied orbitals $k$ with occupation $n_k$ (0, 1, or 2), is

$$
q_r=\sum_kn_kc_{k,r}^2
$$

and the **$\pi$-bond order** between bonded atoms $r,s$ is

$$
p_{rs}=\sum_kn_kc_{k,r}c_{k,s}
$$

$p_{rs}$ measures the extent to which a given bond carries $\pi$ character; $p_{rs}=1$ for an isolated double bond (as in ethylene, where $c_{1,1}=c_{1,2}=1/\sqrt2$ gives $p_{12}=1$), $p_{rs}=0$ for none.

**Butadiene.** Occupied orbitals $k=1,2$ give $q_r=1$ at every carbon (uniform charge, expected by the mirror symmetry of the chain) and

$$
p_{12}=0.894,\qquad p_{23}=0.447
$$

so the "single" central bond (classically C2–C3) already carries substantial $\pi$ character, longer than an isolated double bond but shorter than an isolated single bond — matching the observed bond-length pattern of butadiene (1.34, 1.48, 1.34 Å against 1.33 Å and 1.54 Å for isolated double and single C–C bonds) without ever writing a distinct "single" and "double" bond into the model.

**Benzene.** All six $p_{12}=p_{23}=\dots=0.667$: every bond carries identical, intermediate $\pi$ character. This is the calculation behind the qualitative statement at the start of the chapter — benzene has six identical bonds because the Hückel wavefunction, built with no bias toward any particular pairing, gives every bond the same bond order.

**The allyl system, and a check.** Three $2p_z$ orbitals in a row give $x=\sqrt2,0,-\sqrt2$, with the nonbonding ($x=0$) orbital having coefficients $(1/\sqrt2,\,0,\,-1/\sqrt2)$ — zero density at the central atom. Comparing cation ($n=2$ electrons), radical ($n=3$) and anion ($n=4$):

| Species       | $\pi$ energy       | $q_1=q_3$ | $q_2$ |
| ------------- | ------------------- | --------- | ----- |
| Allyl cation  | $2\alpha+2.828\beta$ | 0.5       | 1.0   |
| Allyl radical | $3\alpha+2.828\beta$ | 1.0       | 1.0   |
| Allyl anion   | $4\alpha+2.828\beta$ | 1.5       | 1.0   |

All three share the same delocalization energy ($0.828|\beta|$ relative to a localized structure) because the added or removed electron occupies the nonbonding orbital, which contributes nothing to the energy sum; only the terminal-carbon charge changes. This reproduces, from one calculation, the standard resonance picture of the allyl cation and anion sharing charge equally between the two terminal carbons — derived here rather than drawn as two resonance structures with an arrow between them.

**A structural theorem, stated without proof.** For **alternant hydrocarbons** — those whose atoms can be divided into two sets (starred and unstarred) such that every bond joins a starred to an unstarred atom, true of chains and even-membered rings with no odd-membered ring fused in — the eigenvalues occur in pairs $\pm x_k$, and every atom has $q_r=1$ in the neutral closed-shell molecule. Benzene and butadiene are both alternant; this is why their charge densities above came out perfectly uniform, and it is a structural fact about the connectivity graph, not a numerical coincidence.
> **Status of the principle: charge density and bond order**
> *Derived* from the LCAO coefficients within the model of Section 12.1; the pairing theorem for alternant hydrocarbons is an exact *Derived* consequence of the bipartite bond graph, independent of the numerical values of $\alpha,\beta$.

---

## 12.6 Bond alternation: repairing the polyene-gap failure

**The unfinished business.** Section 3.5 flagged bond alternation as one of the two pieces of missing physics behind the box model's failure to predict a nonzero gap for infinitely long polyenes. Section 12.3 showed the uniform-$\beta$ Hückel chain has exactly the same flaw, for exactly the same reason: nothing in a uniform chain distinguishes a "double bond" position from a "single bond" position.

**The physical correction.** Nothing so far has justified treating every $\beta$ as equal. A shorter bond has a larger orbital overlap and a larger (more negative) $\beta$. Real polyenes have alternating bond lengths — short ($\approx1.34$ Å) and long ($\approx1.46$ Å) — so the resonance integral should alternate too: $\beta_1=\beta(1+\delta)$ for one set of bonds and $\beta_2=\beta(1-\delta)$ for the other, with $\delta>0$ measuring the alternation.

**The result.** Solving the alternating chain (most simply seen in the infinite limit) gives a HOMO–LUMO gap that does *not* close as $N\to\infty$:

$$
\Delta E\ \xrightarrow{N\to\infty}\ 2\lvert\beta_1-\beta_2\rvert=4\delta\lvert\beta\rvert
$$

instead of the $\to0$ behavior of the uniform chain. This is confirmed directly: for a uniform chain the gap at $N=4,8,16,32,64$ shrinks steadily toward zero ($1.24,\ 0.69,\ 0.37,\ 0.19,\ 0.10$, in units of $|\beta|$), while for an alternating chain with $\beta_2/\beta_1=0.8$ the gap *saturates* near $1.35,\ 0.89,\ 0.62,\ 0.49,\ 0.43$ instead of continuing to fall, converging toward the predicted infinite-chain value $2(1-0.8)=0.4$.

**What this repairs, and what it does not.** This single modification is precisely the missing piece that Section 3.5 identified: bond alternation caps the gap at a finite value, so long polyenes absorb at a finite, not ever-decreasing, wavelength — matching the qualitative leveling-off visible already in the experimental column of Section 12.3's table ($\beta$-carotene's 450 nm is far short of both the box's and the uniform-Hückel's extrapolation). **It does not, by itself, close the quantitative gap** between Hückel and experiment; Section 3.5's other flagged cause, electron repulsion, is still absent from this chapter and remains unaddressed until Chapter 9's variational and correlation methods are applied to $\pi$ systems in later chapters. Bond alternation is also the one-dimensional chemist's version of a general solid-state fact: a chain with two atoms (or two bond lengths) per repeat unit opens a gap at the zone boundary — the same mechanism, in the language of Chapter 20's treatment of solids, as the origin of the distinction between a metal and an insulator or semiconductor in a regular one-dimensional lattice (the Peierls instability).
> **Status of the principle: bond-alternation gap**
> *Derived* within the alternating-$\beta$ Hückel model; the existence of alternation itself is an *Empirical* structural fact (confirmed independently by diffraction) that this chapter does not derive from more fundamental principles — doing so requires the vibronic and elastic-energy balance that produces Peierls-type distortions, only sketched here by analogy with Section 11.8's Jahn–Teller argument.

---

## 12.7 Where Hückel theory fails

**Restating the rule of Section 5.9 (approximation before failure).** Hückel theory works because the $\sigma$–$\pi$ separation is exact and because nearest-neighbor, one-electron delocalization captures the dominant qualitative physics of conjugation: bond-length patterns, aromatic stability, and the $4n+2$ count. Its failures are traceable, one by one, to the three steps flagged as *Approximate* in Section 12.1 and to the details left out of the parametrization.

- **No electron repulsion.** Every calculation in this chapter has treated $\pi$ electrons as independent particles feeling only an averaged field folded into $\alpha$ and $\beta$; the explicit $\sum_{i<j}e^2/4\pi\varepsilon_0 r_{ij}$ term of Chapter 8 is entirely absent. This is why the resonance energy of benzene came out roughly three times the thermochemical value, and it is the same missing physics flagged for the box model in Section 3.5. Restoring it (Pariser–Parr–Pople-type treatments) is a task for the correlation methods of later chapters, not this one.
- **Overlap set to zero.** Real adjacent $2p_z$ orbitals have $S_{rs}\approx0.25$, not $0$. Including it shifts and asymmetrizes the levels but leaves the *pattern* of degeneracies — governed by symmetry, not by the numerical value of $S$ — unchanged, since Section 11.8's argument never used $S$.
- **Constant $\alpha,\beta$.** Section 12.6 already showed that even one refinement (letting $\beta$ track bond length) is essential for the correct asymptotic gap. Heteroatoms (as in pyridine or furan) need different $\alpha$ for different elements and different $\beta$ for different bond types; plain Hückel theory as presented here handles hydrocarbons only.
- **No account of the $\sigma$ framework's own strain.** Cyclobutadiene's $\pi$-electron destabilization (Section 12.4) is real, but the ring's actual instability also involves $\sigma$-bond angle strain that this chapter's $\pi$-only Hamiltonian cannot see.
- **Excited states and spectra beyond the orbital energy gap.** Treating an electronic transition as simply "HOMO energy minus LUMO energy" neglects the same electron-repulsion terms; a proper account of electronic excitation energies needs configuration interaction, introduced in Chapter 9's discussion of correlation.

None of this makes Hückel theory arbitrary. Each shortfall is a named, absent piece of physics with a known repair, in keeping with the philosophy that has organized every chapter so far: **there are no arbitrary exceptions, only approximations with domains of validity**, and this chapter has now shown explicitly where that domain of validity ends.
> **Status of the principle: domain of validity of Hückel theory**
> *Approximate*, stated in full: the theory is reliable for qualitative trends in bond order, charge distribution, and closed-shell/open-shell classification of planar hydrocarbon $\pi$ systems, and unreliable for absolute energies, heteroatom systems, and anything requiring electron correlation.

---

## What remains unexplained

| Open question                                                                                   | Where it is resolved |
| ------------------------------------------------------------------------------------------------- | --------------------- |
| How does electron repulsion enter explicitly, and how much does it change the resonance energy?   | Chapter 9 (correlation methods), applied to $\pi$ systems in later treatments |
| Why does one electron per level minimize energy before pairing (used silently in filling rings)?   | Chapter 8 (Hund's rule from exchange)                |
| What physically drives the bond-length alternation assumed in Section 12.6?                        | Peierls-type instabilities, touched on again in Chapter 20 |
| How are the actual vibrational and spin–orbit mechanisms that make "forbidden" transitions observable? | Chapter 13 |
| How is a full self-consistent-field treatment of $\pi$ or all valence electrons set up?             | Chapter 9             |
| How does conjugation extend to three-dimensional and solid-state systems (graphene, conducting polymers)? | Chapter 20      |

**Next:** Chapter 13 returns to spectroscopy and derives, rather than states, the selection rules $\Delta l=\pm1$ and $\Delta J=\pm1$, the Franck–Condon principle, and the contact hyperfine interaction — completing the promise made when Section 11.9 used the transition dipole without deriving where it, or the intensity of a transition, comes from.
