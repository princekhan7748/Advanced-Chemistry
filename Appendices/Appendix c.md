# Appendix C — Group Theory Reference

*Reference*

A working summary of the symmetry formalism used in Chapters 11, 18 and 20, collected here for lookup rather than re-derivation.

---

## C.1 Groups

A **group** is a set of elements together with a combination rule (here, "perform one symmetry operation, then another") satisfying four properties: closure (combining two elements of the group gives another element of the group), associativity, existence of an identity element $E$, and existence of an inverse for every element. A molecule's **point group** is the set of symmetry operations (rotations, reflections, inversion, improper rotations) that leave at least one point fixed and map the molecule onto an indistinguishable copy of itself (Chapter 11).

Common point groups encountered in the book: $C_{2v}$ (water), $D_{3h}$ (planar BF$_3$), $D_{6h}$ (benzene), $T_d$ (methane), $O_h$ (an octahedral transition-metal complex).

## C.2 Representations

A **representation** assigns a matrix to each symmetry operation of the group, describing how that operation transforms a chosen basis (a set of atomic orbitals, bond vectors, or Cartesian displacements). Representations can generally be **reduced** — block-diagonalized by a suitable change of basis — into a sum of **irreducible representations**, the group's smallest indivisible building blocks. Every irreducible representation carries a label (e.g. $A_1$, $B_2$, $E$, $T_2$) that specifies precisely how an object of that symmetry transforms under every operation of the group.

## C.3 Character tables

A **character table** lists, for each irreducible representation of a point group, the trace (character, $\chi$) of the matrix representing each class of symmetry operation, together with which simple functions ($x,y,z$; $x^2,y^2,z^2$; rotations $R_x,R_y,R_z$) transform according to each representation. Example, for $C_{2v}$ (relevant to water and to many transition-metal fragments):

| $C_{2v}$ | $E$ | $C_2$ | $\sigma_v(xz)$ | $\sigma_v'(yz)$ | linear functions | quadratic functions |
|---|---|---|---|---|---|---|
| $A_1$ | 1 | 1 | 1 | 1 | $z$ | $x^2,y^2,z^2$ |
| $A_2$ | 1 | 1 | -1 | -1 | — | $xy$ |
| $B_1$ | 1 | -1 | 1 | -1 | $x$ | $xz$ |
| $B_2$ | 1 | -1 | -1 | 1 | $y$ | $yz$ |

The number of irreducible representations always equals the number of symmetry classes, and the sum of the squares of the dimensions of the irreducible representations equals the order of the group (here, $1^2+1^2+1^2+1^2=4$, the order of $C_{2v}$).

## C.4 Direct products

Two irreducible representations combine according to a **direct product**, whose reduction determines whether a particular integral (overlap, transition dipole) can be nonzero. The general selection rule used throughout Chapters 11 and 13:

$$
\int \Gamma_i \times \Gamma_{operator} \times \Gamma_f \; d\tau \neq 0 \quad\text{only if}\quad \Gamma_i\otimes\Gamma_{operator}\otimes\Gamma_f \supset A_1\ (\text{the totally symmetric representation}).
$$

This single statement is the group-theoretic content behind vibrational IR/Raman activity (Chapter 11) and electronic/vibrational spectroscopic selection rules (Chapter 13): a transition is allowed only if the direct product of the initial state's symmetry, the operator's symmetry (transforming as $x,y,z$ for an electric-dipole transition), and the final state's symmetry contains the totally symmetric representation.

## C.5 Symmetry-adapted linear combinations

A **symmetry-adapted linear combination (SALC)** is a combination of atomic orbitals (or other basis functions) constructed, using the **projection operator** method, to transform as a single irreducible representation of the molecular point group. Building molecular orbitals from SALCs rather than from raw atomic orbitals (Chapter 11) guarantees by construction that only orbitals of matching symmetry mix, dramatically reducing the size of the secular equation (Appendix A.4) that must actually be solved, and explains why certain orbital interactions are symmetry-forbidden regardless of energy match.

Orbital-symmetry correlation diagrams (Chapter 18), used to decide whether pericyclic reactions are thermally or photochemically allowed, are a direct application of this same idea: tracking which irreducible representation each reactant and product orbital belongs to along a proposed reaction coordinate, and requiring that occupied orbitals correlate only with occupied orbitals of the same symmetry label.

---

**See also:** Appendix A.3–A.4 (matrices and eigenvalue problems, the linear-algebra machinery representations are built from) and Appendix B.1 (operators, since a symmetry operation is itself a special unitary operator).
