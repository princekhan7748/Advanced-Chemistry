# Chapter 11 — Molecular Symmetry and Electronic Structure

*Part I · The Quantum Structure of Matter*

Chapter 4 ended with a promise. Full rotational symmetry gave quantum numbers, the degeneracy $2l+1$ and selection rules, and "the point-group symmetry of a molecule replaces the full rotation group and organizes molecular orbitals and vibrations" (Section 4.9). Chapter 5 made a second one: the symmetric stretch of CO$_2$ is a genuine vibration that never appears in its infrared spectrum, and "symmetry decides which modes are active" (Section 5.11). Chapter 10 built molecular orbitals from atomic ones. This chapter shows how much of that construction can be decided before any energy is computed.

The chapter answers questions that no atomic picture can:
> **A molecule is not a sphere. What survives of the symmetry that gave atoms their quantum numbers, and what can it tell us without solving any equation?** **Why does methane, with four equivalent C–H bonds, show two ionization bands rather than one? Why is the symmetric stretch of CO$_2$ silent in the infrared?**

**Three simple expectations, and where they fail.**

- *Four equivalent bonds mean four equivalent electron pairs, hence one ionization energy.* The photoelectron spectrum of CH$_4$ has two bands, near 14 eV and 23 eV.
- *A level of angular momentum $l$ is $(2l+1)$-fold degenerate* (Section 4.7), so degeneracies should be 1, 3, 5, 7. Benzene's $\pi$ levels have degeneracy 1 or 2 only; methane has threefold levels; a molecule with no symmetry has none.
- *Every vibration is an oscillator that can absorb* (Section 5.1). The symmetric stretch of CO$_2$ does not.

All three follow from one fact: the electrons and the nuclei are subject to the same finite set of geometrical operations, and the quantum-mechanical consequences of a symmetry are independent of the details of the forces.

| Mathematical result                                        | Chemical destination                                                        |
| ---------------------------------------------------------- | --------------------------------------------------------------------------- |
| Symmetry operations form a group                           | Point group of a molecule; polarity and chirality                           |
| Irreducible representations                                | Orbital, state and vibration labels ($a_1$, $e$, $t_{2g}$, ...) replacing $l,m$ |
| Dimension of an irreducible representation                 | Degeneracy of orbitals, states and vibrations                               |
| Character tables                                           | Which orbital, function or mode has which symmetry, read off directly       |
| Projection operators                                       | Symmetry-adapted combinations of atomic orbitals                            |
| Block-diagonal Hamiltonian                                 | Which orbitals can mix; the structure of a molecular-orbital diagram        |
| Direct product contains the totally symmetric representation | Selection rules for IR, Raman and electronic spectra                      |
| Representation of atomic displacements                     | Number and symmetry of normal modes; IR and Raman activity                  |
| Order of the rotational subgroup                           | Symmetry number in the rotational partition function (Chapter 15)           |

**Roadmap.** Which operations a molecule has (11.1–11.3) → how the quantum states organize under them (11.4–11.5) → building orbitals with symmetry (11.6–11.7) → degeneracy and its limits (11.8) → what symmetry forbids: selection rules, vibrations, electronic transitions (11.9–11.11).

---

## 11.1 Symmetry operations

**What the simple theory says.** Section 4.9: if $\hat H$ commutes with an operator, the operator's eigenvalue is a good quantum number. For an atom the nucleus sits at the origin, every rotation leaves $\hat H$ unchanged, and the result is $l$, $m$ and the degeneracy $2l+1$.

**Where it fails.** With several nuclei, an electron no longer feels a spherical potential. Rotating all electrons by an arbitrary angle about the centre of the molecule moves them relative to the nuclei and changes the potential, so $l$ is not conserved and the label "$p$ orbital" no longer names a state of definite angular momentum. Some operations survive, however: those that carry the nuclear framework into itself.

**Which operations, and why.** For nuclei clamped at positions $\mathbf R_A$ (the Born–Oppenheimer picture of Chapter 9), the electronic Hamiltonian is

$$
\hat H_{\rm el}=-\frac{\hbar^2}{2m_e}\sum_i\nabla_i^2-\sum_{i,A}\frac{Z_Ae^2}{4\pi\varepsilon_0\lvert\mathbf r_i-\mathbf R_A\rvert}+\sum_{i<j}\frac{e^2}{4\pi\varepsilon_0\lvert\mathbf r_i-\mathbf r_j\rvert}
$$

Apply any orthogonal transformation (rotation, reflection, inversion) to all electron coordinates. The Laplacian and every inter-electron distance are unchanged, so the first and third terms are invariant. The attraction term is invariant *if and only if* the transformation maps each nucleus onto a nucleus of the same charge, so that the sum over $A$ is merely reordered. Hence

$$
[\hat H_{\rm el},\hat R]=0\quad\text{for every operation }R\text{ that maps the nuclear framework onto itself}
$$

**The operations.** Each acts on a function by moving the function along with the framework, $\hat Rf(\mathbf r)=f(R^{-1}\mathbf r)$.

| Operation | Symbol | Action | Example (matrix on $x,y,z$)                |
| --------- | ------ | ------ | ------------------------------------------ |
| Identity  | $E$    | nothing | $\mathrm{diag}(1,1,1)$                    |
| Rotation  | $C_n$  | by $2\pi/n$ about an axis | $C_2(z)$: $\mathrm{diag}(-1,-1,1)$ |
| Reflection | $\sigma$ | in a plane | $\sigma(xz)$: $\mathrm{diag}(1,-1,1)$    |
| Inversion | $i$    | $\mathbf r\to-\mathbf r$ | $\mathrm{diag}(-1,-1,-1)$         |
| Improper rotation | $S_n$ | $C_n$ followed by reflection in the plane perpendicular to the axis | ($S_1=\sigma$, $S_2=i$) |

**What is lost and what is not.** The isolated molecule as a whole is still rotationally symmetric in space, and its total angular momentum $J$ is conserved (Chapter 4). What the framework breaks is the symmetry of the *electrons relative to the nuclei*. An atom is simply the case where the framework is a single point, and its group of operations is the full rotation group; the molecular case is a finite subgroup.

**A limit of the idea.** The operations belong to one fixed geometry. Real nuclei vibrate, and some molecules are *non-rigid* (ammonia inverts through the planar form, with a ground-state tunneling splitting of 0.79 cm$^{-1}$, the 23.87 GHz of the ammonia maser). For such motions a single point group is insufficient. Section 11.8 shows a second failure, Jahn–Teller distortion. A complete treatment of non-rigid molecules requires permutation–inversion groups and is not developed in this book.
> **Status of the principle: symmetry operations of the framework**
> *Approximate.* For a clamped framework $[\hat H_{\rm el},\hat R]=0$ holds exactly, as rotational symmetry did for an atom in Section 4.9, but real nuclei move, so a point group describes an idealized rigid geometry.

---

## 11.2 Point groups

**Why "group".** Doing one symmetry operation and then another must give a third symmetry operation, because the framework is mapped onto itself twice. The set of all operations of a molecule therefore satisfies four properties: **closure** (the product of two is in the set), an **identity** $E$, an **inverse** for each operation, and **associativity**. A set with these properties is a *group*, and because every operation leaves at least one point fixed (the centre of mass), it is a **point group**. Its size $h$ is its *order*.

**Example: water, $C_{2v}$** (with the molecule in the $yz$ plane). The operations are $E$, $C_2$, $\sigma_v(xz)$ and $\sigma_v'(yz)$, so $h=4$. Closure can be checked with the matrices of Section 11.1: applying $\sigma(xz)$ and then $C_2$ gives $\mathrm{diag}(-1,-1,1)\,\mathrm{diag}(1,-1,1)=\mathrm{diag}(-1,1,1)$, which is $\sigma(yz)$. All operations commute with each other.

**Example: ammonia, $C_{3v}$.** The operations are $E$, $C_3$, $C_3^2$ and three reflections, $h=6$. Here order matters:

$$
\sigma_vC_3=C_3^{-1}\sigma_v\neq C_3\sigma_v
$$

(the two products give different reflection matrices). A group whose operations do not all commute is **non-Abelian**. This one fact will produce degenerate orbitals in Section 11.4.

**A short catalogue.**

| Point group  | Order $h$ | Example                 | Essential operations                 |
| ------------ | --------- | ----------------------- | ------------------------------------ |
| $C_s$        | 2         | HOCl (planar)           | one mirror plane                     |
| $C_{2v}$     | 4         | H$_2$O, H$_2$CO         | $C_2$ and two mirror planes containing it |
| $C_{3v}$     | 6         | NH$_3$                  | $C_3$ and three mirror planes        |
| $C_{\infty v}$ | infinite | CO, HCl                 | linear, no inversion centre          |
| $D_{\infty h}$ | infinite | H$_2$, N$_2$, CO$_2$    | linear, with inversion centre        |
| $D_{3h}$     | 12        | BF$_3$                  | $C_3$, three $C_2$, $\sigma_h$       |
| $D_{6h}$     | 24        | benzene                 | $C_6$, six $C_2$, $\sigma_h$, $i$    |
| $T_d$        | 24        | CH$_4$                  | four $C_3$ axes, tetrahedral         |
| $O_h$        | 48        | SF$_6$, $[\mathrm{Fe(CN)}_6]^{4-}$ | octahedral, with inversion |
| $I_h$        | 120       | C$_{60}$                | icosahedral                          |

The infinite groups are the linear molecules, which keep rotation about their own axis; their labels $\Sigma,\Pi,\Delta$ are the analogues of $m=0,\pm1,\pm2$ (Section 4.6).
> **Status of the principle: point groups**
> *Derived.* The group structure is a mathematical consequence of operations composing; which group a real molecule is assigned to depends on the rigid-framework idealization of Section 11.1.

---

## 11.3 Symmetry elements

**Elements versus operations.** A symmetry *element* is the geometrical object (an axis, a plane, a point) about which an operation is performed. One element can generate several operations: a $C_3$ axis generates $C_3$ and $C_3^2$; a $C_6$ axis generates $C_6,C_3,C_2,C_3^2,C_6^5$.

**Classes.** Two operations belong to the same *class* if one is turned into the other by another operation of the group (for example, the three reflections of $C_{3v}$ are interchanged by $C_3$). Operations in a class are physically equivalent and will have identical characters (Section 11.4). $C_{3v}$ has three classes: $\{E\}$, $\{C_3,C_3^2\}$, $\{\sigma_v,\sigma_v',\sigma_v''\}$, written $E$, $2C_3$, $3\sigma_v$.

**Assigning the point group** (a procedure, not a memory test):

1. Linear? $D_{\infty h}$ if it has an inversion centre, otherwise $C_{\infty v}$.
2. Several axes of order three or more? Then $T_d$, $O_h$ or $I_h$.
3. Otherwise find the highest-order axis $C_n$ (the principal axis).
4. $n$ twofold axes perpendicular to it? The group is $D$-type; otherwise $C$-type.
5. A horizontal plane $\sigma_h$ (perpendicular to the axis) gives $C_{nh}$ or $D_{nh}$; vertical planes give $C_{nv}$; planes between the $C_2$ axes give $D_{nd}$.
6. No axis at all: $C_s$ (one plane), $C_i$ (only inversion) or $C_1$ (nothing).

(This omits the rare $S_{2n}$ groups, which have only an improper axis.)

**Two chemical consequences, derived from the group alone.**

- **Polarity.** A permanent dipole moment is a vector that must be unchanged by every operation. A vector is unchanged by all operations only if it lies along every axis and in every plane, which is possible only in $C_1$, $C_s$, $C_n$ and $C_{nv}$. Hence H$_2$O and NH$_3$ can be polar while CH$_4$, BF$_3$ and CO$_2$ cannot. This is the symmetry side of the requirement, met in Sections 4.8 and 5.10, that a molecule needs a permanent dipole to absorb microwaves.
- **Chirality.** A rigid molecule is superimposable on its mirror image unless it has an improper axis $S_n$ (which includes $\sigma=S_1$ and $i=S_2$). A molecule with no improper axis is chiral. Fast interconversion, as in amines, can hide this.
> **Status of the principle: polarity and chirality criteria**
> *Derived.* They follow from the group structure of a rigid framework; for flexible molecules they apply only to the geometry considered.

---

## 11.4 Representations

**The problem.** Each operation commutes with $\hat H$, and commuting operators can share eigenstates (Section 2.6). But in a non-Abelian group the operations do not commute with *each other*, so the eigenstates of $\hat H$ cannot all be eigenstates of every $\hat R$ at once. What can be said about them?

**The chain.** Let $\psi_k$ be an eigenfunction of $\hat H$ with energy $E$. Then $\hat H(\hat R\psi_k)=\hat R\hat H\psi_k=E(\hat R\psi_k)$: applying any operation to $\psi_k$ gives another function with the *same* energy. So the set of degenerate eigenfunctions of a level is carried into itself:

$$
\hat R\psi_k=\sum_jD_{jk}(R)\,\psi_j
$$

The matrices $D(R)$ multiply in the same way as the operations, $D(R)D(S)=D(RS)$. A set of matrices with this property is a **representation** of the group, and its dimension is the number of degenerate functions. If a change of basis can block-diagonalize all the $D(R)$ at once, the representation is *reducible*; the blocks that cannot be reduced further are **irreducible representations** (irreps). Each energy level of the molecule belongs to one irrep, and *the dimension of the irrep is the degeneracy of the level*.

**Example: $(x,y)$ in $C_{3v}$.** The functions $x$ and $y$ (equivalently $p_x$ and $p_y$) transform among themselves. The matrices are

$$
D(C_3)=\begin{pmatrix}-\tfrac12&-\tfrac{\sqrt3}2\\ \tfrac{\sqrt3}2&-\tfrac12\end{pmatrix},\qquad
D(\sigma_v)=\begin{pmatrix}1&0\\0&-1\end{pmatrix}
$$

These do not commute, so no choice of basis makes both diagonal: $(x,y)$ is a genuinely two-dimensional irrep, and $p_x$ and $p_y$ in ammonia *must* be degenerate.

**Characters.** The trace of $D(R)$, its *character* $\chi(R)$, does not depend on the choice of basis and is the same throughout a class. For $(x,y)$: $\chi(E)=2$, $\chi(C_3)=-1$, $\chi(\sigma_v)=0$. Everything needed is contained in the characters, because of three theorems of group theory:

$$
\sum_i l_i^2=h,\qquad \sum_R\chi_i(R)\chi_j(R)=h\,\delta_{ij},\qquad n_i=\frac1h\sum_R\chi(R)\chi_i(R)
$$

The first fixes the irrep dimensions $l_i$ (for $C_{3v}$: $1^2+1^2+2^2=6$). The second is orthogonality of characters. The third, the *reduction formula*, counts how many times irrep $i$ occurs in any reducible representation with characters $\chi$. The number of irreps equals the number of classes.

**The atom is the special case.** For the full rotation group, rotating by $\alpha$ multiplies $Y_l^m$ by $e^{-im\alpha}$ (Section 4.2), so the character of the $(2l+1)$-dimensional representation is

$$
\chi_l(\alpha)=\sum_{m=-l}^{l}e^{-im\alpha}=\frac{\sin[(l+\tfrac12)\alpha]}{\sin(\alpha/2)}
$$

The irreps of the rotation group are labelled by $l$, and the degeneracy $2l+1$ of Chapter 4 is exactly the dimension rule of this section. **The label $l$ was an irrep label all along;** the point group replaces the infinite family of irreps by a small finite one.
> **Status of the principle: irreducible representations and degeneracy**
> *Derived.* Their existence follows from $[\hat H,\hat R]=0$ and group theory; the dimension-equals-degeneracy statement is exact for the symmetric Hamiltonian, and spin is not yet included (spin–orbit coupling in molecules needs "double groups", not developed here).

---

## 11.5 Character tables

**How to read a table.** A character table lists, for each irrep, its characters for each class, together with the simple functions that transform as that irrep. **Mulliken labels:** $A$ and $B$ are one-dimensional ($A$ symmetric, $B$ antisymmetric under the principal rotation), $E$ two-dimensional, $T$ three-dimensional. Subscripts $1,2$ distinguish behavior under other operations, $g$ and $u$ (*gerade*, *ungerade*) give even or odd parity under inversion, and primes refer to $\sigma_h$. Lower case is used for orbitals, capitals for many-electron states and vibrations.

**$C_{2v}$** (molecule in the $yz$ plane):

| $C_{2v}$ | $E$ | $C_2$ | $\sigma_v(xz)$ | $\sigma_v'(yz)$ | Linear      | Quadratic       |
| -------- | --- | ----- | -------------- | --------------- | ----------- | --------------- |
| $A_1$    | 1   | 1     | 1              | 1               | $z$         | $x^2,y^2,z^2$   |
| $A_2$    | 1   | 1     | $-1$           | $-1$            | $R_z$       | $xy$            |
| $B_1$    | 1   | $-1$  | 1              | $-1$            | $x,R_y$     | $xz$            |
| $B_2$    | 1   | $-1$  | $-1$           | 1               | $y,R_x$     | $yz$            |

**$C_{3v}$:**

| $C_{3v}$ | $E$ | $2C_3$ | $3\sigma_v$ | Linear             | Quadratic                          |
| -------- | --- | ------ | ----------- | ------------------ | ---------------------------------- |
| $A_1$    | 1   | 1      | 1           | $z$                | $x^2+y^2,\ z^2$                    |
| $A_2$    | 1   | 1      | $-1$        | $R_z$              | —                                  |
| $E$      | 2   | $-1$   | 0           | $(x,y),(R_x,R_y)$  | $(x^2-y^2,xy),\ (xz,yz)$           |

**Why these functions.** The angular parts of atomic orbitals are the functions $x,y,z$ ($p$) and the quadratic products ($d$) of Section 4.5. To find the symmetry of an atomic orbital sitting on the central atom, read the irrep from the right-hand columns: in water the oxygen $2p_z$ is $a_1$, $2p_x$ is $b_1$, $2p_y$ is $b_2$, and $2s$ is $a_1$. The linear functions will also stand for the dipole operator and the quadratic ones for the polarizability (Sections 11.9–11.10), and the rotations $R_x,R_y,R_z$ identify the rotational motion to be removed when counting vibrations.

**Checks.** In each table the rows are orthogonal, e.g. for $C_{2v}$, $\sum_R\chi_{B_1}\chi_{B_2}=1+1-1-1=0$ and $\sum_R\chi_{B_1}^2=4=h$. A wrong entry is caught immediately.
> **Status of the principle: character tables**
> *Derived.* They are a mathematical property of each group, independent of any molecule or physics.

---

## 11.6 Symmetry-adapted orbitals

**The problem.** A molecule has several equivalent atoms (the two H in water, the three H in ammonia), each with an atomic orbital. Chapter 10 combined atomic orbitals into molecular orbitals; symmetry says *which* combinations to form: those that transform as irreps of the point group, called **symmetry-adapted linear combinations** (SALCs).

**The projection operator.** Given any function, the operator

$$
\hat P_i=\frac{l_i}{h}\sum_R\chi_i(R)\,\hat R
$$

extracts from it the part that transforms as irrep $i$ (this is the reduction formula of Section 11.4 applied to a function instead of a trace).

**Example: the two H $1s$ orbitals of water.** Acting on $s_1$, the operations $(E,C_2,\sigma_v(xz),\sigma_v'(yz))$ produce $(s_1,s_2,s_2,s_1)$: the rotation and the perpendicular mirror swap the hydrogens, the molecular-plane reflection does not. The characters of this pair are $(2,0,0,2)$, which reduces to $A_1+B_2$. Projecting:

$$
\hat P_{A_1}s_1\propto s_1+s_2+s_2+s_1,\qquad
\hat P_{B_2}s_1\propto s_1-s_2-s_2+s_1
$$

so that

$$
\phi_{a_1}=\frac{s_1+s_2}{\sqrt2},\qquad \phi_{b_2}=\frac{s_1-s_2}{\sqrt2}
$$

(normalization shown for negligible overlap). The projections onto $A_2$ and $B_1$ vanish identically, confirming that they are absent.

**Ammonia.** The three H $1s$ orbitals have characters $(3,0,1)$, which reduce to $A_1+E$, giving

$$
\phi_{a_1}=\frac{s_1+s_2+s_3}{\sqrt3},\qquad
\phi_{e}=\frac{2s_1-s_2-s_3}{\sqrt6},\ \ \frac{s_2-s_3}{\sqrt2}
$$

**Octahedral complexes.** The six $\sigma$-donor orbitals of the ligands of an $O_h$ complex reduce to $a_{1g}+e_g+t_{1u}$ (dimensions $1+2+3=6$). The metal orbitals of matching symmetry are $4s$ ($a_{1g}$), $3d_{z^2},3d_{x^2-y^2}$ ($e_g$) and $4p$ ($t_{1u}$); the $3d_{xy},3d_{xz},3d_{yz}$ set ($t_{2g}$) has *no* $\sigma$ partner.
> **Status of the principle: symmetry-adapted combinations**
> *Derived.* The combinations are fixed by the group alone; their energies are not (Section 11.7).

---

## 11.7 Molecular orbital construction using symmetry

**The vanishing theorem.** The integral of a function over all space cannot change when the space is rotated, reflected or inverted, so $\int f\,d\tau=\int\hat Rf\,d\tau$ for every operation. Averaging over the whole group,

$$
\int f\,d\tau=\int\left(\frac1h\sum_R\hat Rf\right)d\tau
$$

and the bracket is the projection of $f$ onto the totally symmetric irrep. **Therefore $\int f\,d\tau=0$ unless $f$ contains a component that transforms as $A_1$.** This single fact drives the rest of the chapter.

**Consequence for orbital mixing.** The Hamiltonian is totally symmetric, so a matrix element $\int\phi_a^{*}\hat H\phi_b\,d\tau$ between two functions vanishes unless $\phi_a$ and $\phi_b$ belong to the same irrep (and the same row of it). The same is true of overlap integrals. So in a SALC basis the secular problem *factorizes* into one small block per irrep.

**Example: water.** Six valence functions (O $2s$, $2p_x$, $2p_y$, $2p_z$ and the two SALCs of Section 11.6) instead of one $6\times6$ problem give:

| Irrep | Functions                                    | Molecular orbitals                                  |
| ----- | -------------------------------------------- | --------------------------------------------------- |
| $a_1$ | O $2s$, O $2p_z$, $\phi_{a_1}$               | $2a_1,3a_1,4a_1$ (three orbitals from a $3\times3$ block) |
| $b_2$ | O $2p_y$, $\phi_{b_2}$                       | $1b_2$ (bonding), $2b_2$ (antibonding)              |
| $b_1$ | O $2p_x$                                     | $1b_1$: no partner, so *nonbonding*                 |
| $a_2$ | none                                         | —                                                   |

With the O $1s$ as $1a_1$, the ten electrons occupy

$$
(1a_1)^2(2a_1)^2(1b_2)^2(3a_1)^2(1b_1)^2
$$

**How much symmetry decides.** Symmetry fixes the blocks; the energies come from within them. For two same-symmetry orbitals with energies $\alpha_a<\alpha_b$ and coupling $\beta$ (overlap neglected), the $2\times2$ problem gives

$$
E_\pm=\frac{\alpha_a+\alpha_b}{2}\pm\sqrt{\left(\frac{\alpha_b-\alpha_a}{2}\right)^2+\beta^2}
$$

The lower orbital falls and the upper rises, more strongly for larger coupling and smaller energy gap. Two consequences follow. **Levels of the same symmetry repel and cannot cross as a parameter (such as a bond angle) is varied; levels of different symmetry do not interact and may cross.** This non-crossing rule is what makes correlation diagrams work (Chapter 18). And the ordering of the levels within and between blocks is *not* given by symmetry.

**Observation.** The photoelectron spectrum of water has separate bands at about 12.6, 14.7, 18.6 and 32 eV, assigned to $1b_1$, $3a_1$, $1b_2$ and $2a_1$. The two "lone pairs" are therefore *not* equivalent in the symmetry-adapted description: one is the pure out-of-plane $2p$ orbital ($b_1$), the other is an in-plane $a_1$ orbital. The familiar picture of two equivalent rabbit-ear lone pairs, like the four equivalent bonds of methane (whose ionization gives an $a_1$ and a triply degenerate $t_2$ band), is a *different representation* of the same occupied space, useful for the ground state but not a description of the individual ionization energies. This is the distinction on which the statement that hybridization is a representation rather than a physical process (Section 10.14) rests, and it is used again in Chapter 21.
> **Status of the principle: symmetry-blocked molecular orbitals**
> *Derived.* The block structure is exact for the symmetric Hamiltonian; the orbital picture built on it inherits the orbital approximation of Chapter 9.

---

## 11.8 Degeneracy

**What symmetry requires.** Degeneracy equals the dimension of an irrep (Section 11.4). Which dimensions occur is set by the group:

| Kind of group                            | Largest irrep dimension | Example                                   |
| ---------------------------------------- | ----------------------- | ----------------------------------------- |
| Abelian ($C_{2v}$, $D_{2h}$, ...)        | 1                       | no symmetry-required degeneracy in water  |
| One axis of order $\ge3$ ($C_{3v}$, $D_{6h}$) | 2                  | $e$ in NH$_3$; the $e_{1g},e_{2u}$ of benzene |
| Cubic ($T_d$, $O_h$)                     | 3                       | $t_2$ in CH$_4$; $t_{2g}$ in an octahedron |
| Icosahedral ($I_h$)                      | 5                       | C$_{60}$                                  |
| Full rotation group                      | $2l+1$, unbounded       | atoms                                     |

So the observation of the introduction is now derived: **triply degenerate orbitals need cubic or icosahedral symmetry**, and the benzene ring has nothing above twofold.

**Benzene, from the ring.** In Section 4.2 the six $\pi$ electrons were placed on a ring, with levels labelled by $m$. The molecule keeps only the rotation $C_6$ (by $60^\circ$), which multiplies $e^{im\phi}$ by $e^{2\pi im/6}$: only $m$ modulo 6 is meaningful. Then $m=+3$ and $m=-3$ coincide, while $m=\pm1$ and $\pm2$ remain pairs (mirror planes turn $m$ into $-m$). The degeneracy pattern is

$$
m=0\ (a_{2u}),\quad \pm1\ (e_{1g}),\quad \pm2\ (e_{2u}),\quad 3\ (b_{2g})\qquad\Rightarrow\qquad 1,2,2,1
$$

with no equation solved. The quantum number $m$ has not disappeared; it has become an irrep label defined modulo 6. Energies, and the $4n+2$ consequence, come in Chapter 12.

**Lowering the symmetry splits levels along a predictable pattern.** Descending from a larger group to a subgroup (a *correlation*) splits an irrep into the irreps of the subgroup, and a perturbation that lowers the symmetry causes exactly this splitting. Using the character formula of Section 11.4 for the five $d$ functions ($l=2$) under the rotations of the octahedron,

$$
\chi_2=(5,-1,1,-1,1)\ \text{for}\ (E,8C_3,3C_2,6C_4,6C_2'),\qquad\text{which reduces to}\qquad E+T_2
$$

| Atomic level $l$ | Full rotation group | Octahedron $O_h$        | Bent $C_{2v}$                   |
| ---------------- | ------------------- | ----------------------- | ------------------------------- |
| $s$              | 1                   | $a_{1g}$                | $a_1$                           |
| $p$              | 3                   | $t_{1u}$                | $a_1+b_1+b_2$                   |
| $d$              | 5                   | $e_g+t_{2g}$            | $2a_1+a_2+b_1+b_2$              |
| $f$              | 7                   | $a_{2u}+t_{1u}+t_{2u}$  | (all one-dimensional)           |

The five $d$ orbitals of a metal ion in an octahedral field split into $e_g$ ($d_{z^2},d_{x^2-y^2}$) and $t_{2g}$ ($d_{xy},d_{xz},d_{yz}$); an elongation along $z$ ($D_{4h}$) splits them further into $a_{1g}+b_{1g}$ and $b_{2g}+e_g$. The same rule accounts for the Stark effect of Chapter 6: a field along $z$ lowers full rotation to $C_{\infty v}$, and $l=1$ becomes $m=0$ plus $\lvert m\rvert=1$. **Symmetry says how many levels and with what degeneracy; it does not say how large the splitting is or which is lower.** The magnitude belongs to the physics of ligand fields (Chapter 20; Cases 5 and 6 of Chapter 21).

**Where the degeneracy fails: the Jahn–Teller effect.** The symmetric geometry can be an unstable place for an orbitally degenerate state. Let $Q$ be a displacement along a vibration that lowers the symmetry (it can couple to an electronic state of irrep $E$ because $E\otimes E=A_1+A_2+E$ contains an $E$). The two components of the state then vary linearly with $Q$ while the elastic energy varies as $Q^2$:

$$
E_\pm(Q)=\tfrac12kQ^2\pm FQ\ \Longrightarrow\ Q_{\min}=\mp\frac Fk,\qquad E_{\min}=-\frac{F^2}{2k}
$$

For any non-zero coupling $F$ the symmetric geometry is not the minimum, so a non-linear molecule in an orbitally degenerate state is unstable toward a distortion that removes the degeneracy (the distortion may be static, or averaged by motion in the *dynamic* Jahn–Teller effect). Examples include the elongated octahedron of many Cu(II) complexes and the ionized methane whose photoelectron band is broad. This is not an exception to the group theory: the derivation assumed a fixed symmetric framework, and the missing physics is the coupling of electronic and nuclear motion that the Born–Oppenheimer approximation neglects (Chapter 9). Degeneracy from symmetry is also not the only kind: the $2s$–$2p$ degeneracy of hydrogen comes from a hidden symmetry of the $1/r$ potential (Section 6.8), invisible in any point group.
> **Status of the principle: degeneracy from symmetry**
> *Derived.* Degeneracy equals irrep dimension for the symmetric Hamiltonian, and nuclear motion (Jahn–Teller) can lift it in real molecules.

---

## 11.9 Selection rules

**The question.** Chapters 4 and 5 stated rules for when a transition can occur ($\Delta J=\pm1$, $\Delta n=\pm1$, a dipole change), promising derivations. The proper derivation of the rates is in Chapter 13. A prior question can be settled here: *when can the relevant integral be non-zero at all?*

**What determines whether a transition can occur.** Absorption of a photon by a molecule is governed by the *transition dipole* (why is derived in Chapter 13):

$$
\mathbf M_{fi}=\int\psi_f^{*}\,\hat{\boldsymbol\mu}\,\psi_i\,d\tau
$$

The operator $\hat{\boldsymbol\mu}$ has components transforming like $x,y,z$. The integrand transforms as the *direct product* $\Gamma_f\otimes\Gamma_\mu\otimes\Gamma_i$ (whose characters are the products of the characters). By the vanishing theorem of Section 11.7:

$$
\boxed{M_{fi}\neq0\ \text{only if}\ \Gamma_f\otimes\Gamma_\mu\otimes\Gamma_i\ \text{contains}\ A_1}
$$

For Abelian groups the product of two irreps is again a single irrep, and the condition says: **$\Gamma_f\otimes\Gamma_i$ must equal the irrep of $x$, $y$ or $z$**, which also gives the polarization of the light. For example, in $C_{2v}$: $B_1\otimes B_2=A_2$, $A_1\otimes B_1=B_1$.

**Raman.** In light scattering the operator is the polarizability, whose components transform like the quadratic functions $x^2,xy,\dots$ in the character table (the polarizability appeared in Section 6.13; the mechanism is derived in Chapter 13). The condition is the same with $\Gamma_\mu$ replaced by an irrep of a quadratic function.

**Parity.** In a molecule with an inversion centre, $x,y,z$ are *ungerade* and the quadratic functions *gerade*. Hence:

- one-photon absorption requires $g\leftrightarrow u$ (the **Laporte rule**);
- two-photon absorption and Raman scattering require $g\leftrightarrow g$ or $u\leftrightarrow u$.

For atoms this is the parity $(-1)^l$ noted in Section 4.5, so a one-photon transition needs $l$ to change by an odd number. It also explains why $2s\to1s$ of hydrogen, with both states even, has no direct dipole route (Section 6.10). The full result $\Delta l=\pm1$, which uses the angular-momentum algebra as well as parity, is derived in Chapter 13.

**Two limits of what symmetry can say.** It gives a *yes or no*, never an intensity: an allowed transition can be weak because the integral is small. And "forbidden" means zero only in the model that supplied the symmetry, namely clamped nuclei and no spin coupling. Section 11.11 shows how forbidden transitions nevertheless occur.
> **Status of the principle: symmetry selection rules**
> *Derived.* The symmetry criterion, stated without proof in Chapters 4 to 6, follows here from the vanishing theorem; the rules $\Delta l=\pm1$ and $\Delta J=\pm1$ and the origin of the transition dipole follow in Chapter 13.

---

## 11.10 Vibrational symmetry

**The problem.** Section 5.11 said a molecule of $N$ atoms has $3N-6$ normal modes ($3N-5$ if linear) and that some are invisible in the infrared. Which modes exist, and which are visible?

**Modes belong to irreps.** The potential energy is unchanged by every symmetry operation, so its matrix of second derivatives commutes with them, and the normal modes fall into irreps just as orbitals do. Modes of different symmetry cannot mix; degenerate modes belong to irreps of dimension greater than one. Symmetry tells us *how many modes of each symmetry* there are. It does not tell us the frequencies, which need the force constants (Chapter 14).

**The recipe.**

1. Take the $3N$ Cartesian displacements as a basis. Only atoms that are *unmoved* by an operation contribute to its character, each contributing $3$ for $E$, $1+2\cos(2\pi/n)$ for $C_n$, $1$ for $\sigma$, $-3$ for $i$ and $-1+2\cos(2\pi/n)$ for $S_n$.
2. Reduce with the formula of Section 11.4.
3. Subtract the translations (irreps of $x,y,z$) and rotations (irreps of $R_x,R_y,R_z$).

**Water ($C_{2v}$).** The characters of the $3N=9$ displacements are $(9,-1,1,3)$ for $(E,C_2,\sigma_v(xz),\sigma_v'(yz))$, which reduces to $3A_1+A_2+2B_1+3B_2$. Subtracting translations ($A_1+B_1+B_2$) and rotations ($A_2+B_1+B_2$):

$$
\Gamma_{\rm vib}(\text{H}_2\text{O})=2A_1+B_2
$$

the symmetric stretch and bend ($A_1$) and the asymmetric stretch ($B_2$), as listed in Section 5.11. **Ammonia:** $(12,0,2)$ reduces to $3A_1+A_2+4E$, and $\Gamma_{\rm vib}=2A_1+2E$. **Methane:** $(15,0,-1,-1,3)$ for $(E,8C_3,3C_2,6S_4,6\sigma_d)$ reduces to $A_1+T_1+E+3T_2$ and $\Gamma_{\rm vib}=A_1+E+2T_2$.

**IR activity, derived.** The vibrational ground state is totally symmetric, and the fundamental of a mode $Q$ reaches a state of the symmetry of $Q$. The transition dipole is non-zero only if $\Gamma_Q$ contains $x$, $y$ or $z$. Equivalently, expanding $\mu_x(Q)\approx\mu_0+(\partial\mu_x/\partial Q)Q$, the derivative can be non-zero only if $Q$ transforms like $x$ (and likewise $y,z$). This is the symmetry form of the requirement of Section 5.10 that the dipole must change. **A mode is Raman-active if it transforms like a quadratic function.**

| Molecule (point group)           | $\Gamma_{\rm vib}$                             | Modes | Distinct frequencies | IR-active | Raman-active |
| -------------------------------- | ---------------------------------------------- | ----- | -------------------- | --------- | ------------ |
| H$_2$O ($C_{2v}$)                | $2A_1+B_2$                                     | 3     | 3                    | 3         | 3            |
| NH$_3$ ($C_{3v}$)                | $2A_1+2E$                                      | 6     | 4                    | 4         | 4            |
| CH$_4$ ($T_d$)                   | $A_1+E+2T_2$                                   | 9     | 4                    | 2 ($T_2$) | 4            |
| CO$_2$ ($D_{\infty h}$)          | $\Sigma_g^{+}+\Sigma_u^{+}+\Pi_u$              | 4     | 3                    | 2         | 1            |

For CO$_2$ the answer to the opening question follows from parity alone. The symmetric stretch is $g$; $x,y,z$ are $u$; so it cannot absorb. The asymmetric stretch ($\Sigma_u^{+}$, like $z$) and the doubly degenerate bend ($\Pi_u$, like $x,y$) are both $u$ and are IR-active. Since quadratic functions are $g$, these $u$ modes cannot be Raman-active, while the symmetric stretch ($g$) is. This is the **rule of mutual exclusion**: *in a molecule with an inversion centre, no vibration is both IR- and Raman-active.* Comparing the two spectra of CO$_2$ (IR at 667 and 2349 cm$^{-1}$, Raman at 1388 cm$^{-1}$) shows the rule in action, and it can be used to detect an inversion centre.
> **Status of the principle: vibrational symmetry and activity**
> *Derived* for fundamentals in the harmonic model: the dipole-change requirement stated in Section 5.10 takes its symmetry form here, while overtones, combination bands and activity caused by anharmonicity lie outside this counting.

---

## 11.11 Electronic transitions

**State symmetry.** The rule of Section 11.9 applies to whole many-electron states, whose symmetry is the direct product of the irreps of the singly occupied orbitals. A closed-shell configuration is *totally symmetric* (a filled set of degenerate orbitals is left unchanged by any operation), so the ground state of a closed-shell molecule is $A_1$ (or $A_{1g}$).

**Example 1: water, $A_1\to B_1$.** The lowest excitation promotes an electron from the $1b_1$ lone pair to $4a_1$ (Section 11.7). The excited state has symmetry $B_1\otimes A_1=B_1$. Since $A_1\otimes B_1=B_1$ transforms like $x$, the transition is allowed, with light polarized perpendicular to the molecular plane.

**Example 2: formaldehyde, $n\to\pi^{*}$.** The oxygen lone pair $n$ lies in the molecular plane ($b_2$) and the $\pi^{*}$ orbital is perpendicular to it ($b_1$), so the excited state is $B_2\otimes B_1=A_2$. Since $A_2$ matches none of $x,y,z$ ($C_{2v}$ table), the $A_1\to A_2$ transition is **symmetry-forbidden**, and indeed $n\to\pi^{*}$ bands are weak (molar absorption coefficients of order $10$–$10^2$ M$^{-1}$cm$^{-1}$, against about $10^4$ for allowed $\pi\to\pi^{*}$ bands).

**Example 3: colors of octahedral and tetrahedral complexes.** The $d$–$d$ transitions of an octahedral complex connect $g$ to $g$ orbitals ($t_{2g}\to e_g$), forbidden by the Laporte rule. A tetrahedral complex has no inversion centre, so parity is not a label and the restriction is absent. Experimentally, octahedral $d$–$d$ bands have typical absorption coefficients of $1$–$10^2$ M$^{-1}$cm$^{-1}$ and tetrahedral ones of $10^2$–$10^3$ M$^{-1}$cm$^{-1}$ (compare the pale pink of $[\mathrm{Co(H_2O)}_6]^{2+}$ with the deep blue of $[\mathrm{CoCl}_4]^{2-}$).

**Why forbidden transitions are seen at all.** "Forbidden" means zero when the nuclei are clamped and the electrons carry no spin coupling. Two pieces of missing physics remove those idealizations. **Vibronic coupling:** during a vibration of symmetry $\Gamma_v$ the molecule is momentarily less symmetric, and the transition is allowed if $\Gamma_i\otimes\Gamma_f\otimes\Gamma_v$ contains $x$, $y$ or $z$. An odd-parity vibration lets an octahedral $d$–$d$ band borrow intensity. **Spin–orbit coupling** (Chapter 7) weakens the spin selection rule $\Delta S=0$, which is treated with fluorescence and phosphorescence in Chapter 13. So a forbidden band is a weak allowed band in a less symmetric or less idealized model, not an arbitrary exception.

**Where else symmetry decides.** Reactions proceed along paths, and *if a symmetry element is preserved throughout, orbitals of different symmetry cannot mix* (Section 11.7). This is the basis of orbital-symmetry correlation diagrams (Chapter 18). Overlap between the frontier orbitals of two reactants is non-zero only for orbitals of matching symmetry (Chapter 17). Finally, the number of proper rotations that map a molecule onto itself is the **symmetry number** that divides the rotational partition function (2 for H$_2$O, 3 for NH$_3$, 12 for CH$_4$ and benzene; Chapter 15).
> **Status of the principle: electronic selection rules**
> *Approximate.* The rules are exact within the clamped-nucleus, spin-free model; real spectra add weak forbidden bands through vibronic and spin–orbit coupling.

---

## What remains unexplained

| Open question                                                                                          | Where it is resolved |
| ------------------------------------------------------------------------------------------------------ | -------------------- |
| Why is absorption governed by the transition dipole, and how are $\Delta l=\pm1$, $\Delta J=\pm1$ and the Raman rule derived? | Chapter 13 |
| How do vibronic and spin–orbit coupling give the observed intensity of forbidden bands?                | Chapter 13           |
| What sets the *energies* of the symmetry-blocked orbitals (symmetry gives only the blocks)?            | Chapters 9 and 14    |
| How large is the $e_g$–$t_{2g}$ splitting, and why do some complexes have unusual magnetism?           | Chapter 20; Chapter 21 (Cases 5 and 6) |
| How are the $\pi$ energies of benzene obtained, and how does $4n+2$ arise?                             | Chapter 12           |
| How are vibrational frequencies computed from force constants?                                         | Chapter 14           |
| How does symmetry constrain the orbitals along a reaction path?                                        | Chapter 18           |
| How does the symmetry number enter thermodynamic quantities?                                           | Chapter 15           |
| How reliable is one point group for a flexible molecule?                                               | Chapter 9 (Born–Oppenheimer); permutation–inversion groups are outside this book |

**Next:** Chapter 12 applies this machinery to the $\pi$ electrons of conjugated molecules. Symmetry will reduce benzene's $6\times6$ problem to blocks, the ring model of Section 4.2 will be replaced by Hückel theory, the $4n+2$ rule will be derived as a consequence of a simplified model, and the failure of the box model for polyenes noted in Section 3.5 will be repaired.
