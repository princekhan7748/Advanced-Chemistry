# Appendix B — Quantum Mechanics Reference

*Reference*

A working summary of the quantum-mechanical formalism developed across Chapters 2, 7 and 9, collected here for lookup rather than re-derivation.

---

## B.1 Operators

An **operator** $\hat A$ acts on a wavefunction to produce another function, $\hat A\psi(x)=\phi(x)$. Every measurable quantity (an **observable**) corresponds to a **Hermitian** linear operator, guaranteeing real eigenvalues (Appendix A.3–A.4). The operators used throughout the book:

| Observable | Operator (position representation) |
|---|---|
| Position | $\hat x = x$ |
| Momentum | $\hat p_x = -i\hbar\,\partial/\partial x$ |
| Kinetic energy | $\hat T = -\dfrac{\hbar^2}{2m}\nabla^2$ |
| Potential energy | $\hat V = V(x,y,z)$ |
| Total energy (Hamiltonian) | $\hat H = \hat T + \hat V$ |
| Angular momentum ($z$-component) | $\hat L_z = -i\hbar\,\partial/\partial\phi$ |

A measurement of an observable yields one of the operator's eigenvalues, and immediately after the measurement the system is in the corresponding eigenstate (Chapter 2).

## B.2 Commutators

The commutator of two operators is $[\hat A,\hat B]=\hat A\hat B-\hat B\hat A$. Two observables can be measured simultaneously with arbitrary precision if and only if their operators commute (share a complete set of eigenfunctions). The canonical commutation relation,

$$
[\hat x,\hat p_x] = i\hbar,
$$

is the algebraic source of the Heisenberg uncertainty relation,

$$
\Delta x\,\Delta p_x \geq \frac{\hbar}{2},
$$

via the general result $\Delta A\,\Delta B \geq \tfrac12\lvert\langle[\hat A,\hat B]\rangle\rvert$ (Chapter 2). Angular momentum components do **not** commute with one another,

$$
[\hat L_x,\hat L_y]=i\hbar\hat L_z \quad(\text{and cyclic permutations}),
$$

but $\hat L^2$ commutes with each component $\hat L_z$, which is why $l$ and $m$ (but not two different components of angular momentum) can be specified simultaneously (Chapter 4).

## B.3 Angular momentum

Orbital angular momentum eigenvalues, derived from the commutation relations alone (Chapter 4):

$$
\hat L^2 Y_l^m = \hbar^2 l(l+1)\,Y_l^m, \qquad \hat L_z Y_l^m = \hbar m\,Y_l^m,
$$

with $l=0,1,2,\dots$ and $m=-l,-l+1,\dots,+l$ ($2l+1$ values). The familiar orbital labels $s,p,d,f$ correspond to $l=0,1,2,3$.

## B.4 Spin

Spin angular momentum obeys the same commutation algebra as orbital angular momentum but is not a function of position; it has no classical analogue and was introduced empirically (Stern–Gerlach, Chapter 1) before being derived from the relativistic Dirac equation (Chapter 7):

$$
\hat S^2\chi = \hbar^2 s(s+1)\chi, \qquad \hat S_z\chi = \hbar m_s\chi,
$$

with $s=\tfrac12$ for an electron and $m_s=\pm\tfrac12$. The Dirac equation predicts the electron $g$-factor $g_s\approx2$ (Chapter 7); higher-order quantum-electrodynamic corrections refine this value slightly further.

## B.5 Perturbation theory

For a Hamiltonian $\hat H=\hat H^{(0)}+\hat V$, where $\hat H^{(0)}$ has known eigenstates $\vert n^{(0)}\rangle$ and eigenvalues $E_n^{(0)}$, and $\hat V$ is a small perturbation, the corrected energy through second order is

$$
E_n = E_n^{(0)} + \langle n^{(0)}\vert\hat V\vert n^{(0)}\rangle + \sum_{k\neq n}\frac{\lvert\langle k^{(0)}\vert\hat V\vert n^{(0)}\rangle\rvert^2}{E_n^{(0)}-E_k^{(0)}} + \cdots
$$

The first correction is the **first-order** energy shift (used for the Zeeman and Stark effects, Chapter 6); the second term is the **second-order** shift, always lowering the ground-state energy, and is the origin of the London dispersion interaction (Chapter 20). Time-dependent perturbation theory, applied to an oscillating electromagnetic field, gives the transition rates and selection rules underlying all of spectroscopy (Chapter 13).

## B.6 Variational method

For any normalized trial function $\vert\Phi\rangle$, the expectation value of the true Hamiltonian is never below the true ground-state energy:

$$
E_{trial} = \langle\Phi\vert\hat H\vert\Phi\rangle \;\geq\; E_0.
$$

Minimizing $E_{trial}$ over a set of adjustable parameters in $\Phi$ therefore gives a rigorous upper bound to the true ground-state energy and the best approximation to the true wavefunction available within that trial form (Chapter 9). The Hartree–Fock method, Hückel theory, and every basis-set electronic-structure calculation in Chapter 14 are variational in this sense: enlarging the trial function's flexibility (a bigger basis set) can only lower or leave unchanged the computed energy, never raise it.

---

**See also:** Appendix A (the linear algebra and differential-equation machinery this formalism is built on) and Appendix C (symmetry operators, a special class of operator satisfying additional group-theoretic relations).
