# Task 3C — Positivity, Quadratic Forms, and Spectral Constraints Along $\operatorname{Re} s = \frac{1}{4}$ / $\operatorname{Re} \rho = \frac{1}{2}$

**Status:** Analytical & Spectral Constraint Audit (Stage 3, Task 3C)  
**Builds on:**  
- `broader_program_stage3_task3a_mayer_parity_decomposition.md`  
- `broader_program_stage3_task3b_rigged_eisenstein_space.md`  
- `corrigendum_friedrichs_zeta_revised.md`  
**Purpose:** Examine positivity, quadratic forms, and spectral/symmetry constraints along the half-scaled critical line $\operatorname{Re} s = \frac{1}{4}$ ($\operatorname{Re}\rho = \frac{1}{2}$), distinguishing genuine symmetries and positivity structures from sufficient conditions for zero localization.

---

## 0. Scope and core mathematical boundary

This note examines **positivity, quadratic forms, and spectral/symmetry constraints** associated with the critical line $\operatorname{Re}\rho = \frac{1}{2}$ of the Riemann zeta function $\zeta(\rho)$ and its half-scaled image $\operatorname{Re} s = \frac{1}{4}$ in the Mayer / Selberg transfer-operator parameterization.

We maintain a strict boundary between three categories:
- **Proved / Structural:** Functional-equation reflection symmetries, unitary/scattering identities on the unitary line $\operatorname{Re} s = \frac{1}{2}$ ($\operatorname{Re}(2s) = 1$), and quadratic-form / trace / explicit-formula positivity structures.
- **Conditional / Obstruction-Aware:** Why an inequality on a line or half-plane (or a dissipative/positive-real quadratic form) does *not* by itself force all zeros of a holomorphic or meromorphic object onto a single vertical line without additional rigidity, symmetry, or zero-free-region input.
- **Open / Conjectural:** The Riemann Hypothesis itself ($\operatorname{Re}\rho = \frac{1}{2}$ for all non-trivial zeros $\rho$ of $\zeta(s)$).

---

## 1. Reflection symmetries and the two critical lines

### 1.1 Riemann's functional equation and $\operatorname{Re}\rho = \frac{1}{2}$
Let $\xi(s)$ be the completed Riemann zeta function:
\[
\xi(s) = \frac{1}{2}s(s-1)\pi^{-s/2}\Gamma\!\left(\frac{s}{2}\right)\zeta(s).
\]
It satisfies the reflection symmetry
\[
\xi(s) = \xi(1-s).
\]
Non-trivial zeros $\rho$ of $\zeta(s)$ lie in the critical strip $0 < \operatorname{Re}\rho < 1$, and by the functional equation they come in symmetric pairs $\{\rho, 1-\rho\}$ and $\{\bar\rho, 1-\bar\rho\}$. The line
\[
\operatorname{Re}\rho = \frac{1}{2}
\]
is the **fixed locus** of the involution $\rho \mapsto 1-\rho$.

### 1.2 Half-scaling to $\operatorname{Re} s = \frac{1}{4}$
Under the half-scaling map
\[
s = \frac{\rho}{2},
\]
the reflection $\rho \mapsto 1-\rho$ corresponds to
\[
s \longmapsto \frac{1}{2} - s.
\]
Its fixed line is
\[
\operatorname{Re} s = \frac{1}{4}.
\]
In the Mayer operator $\mathcal L_s$ (parameterized so that $\mathcal L_s$ has $s$-dependent transfer weights and half-scaled Riemann zeros correspond to $s = \rho/2$), the locus $\operatorname{Re} s = \frac{1}{4}$ is the exact image of $\operatorname{Re}\rho = \frac{1}{2}$.

### 1.3 Why symmetry alone does not force zeros onto the fixed line
A symmetry $F(z) = F(z^*)$ or $G(s) = G(\frac{1}{2}-s)$ ensures that if $z_0$ is a zero off the fixed line, its reflected partner is also a zero. Symmetry *balances* zeros symmetrically around the line; it does **not** forbid off-line zeros unless combined with a positivity, convexity, or zero-free-region argument that rules out zeros in the complementary half-strips.

---

## 2. Quadratic forms and spectral positivity in operator / trace formulations

### 2.1 Self-adjoint / positive quadratic forms vs. non-self-adjoint / complex-parametered operators
In Stages 1 and 2, positivity and monotonicity entered through two distinct mechanisms:
1. **In the Friedrichs model (Stage 1):** Physical evolution $e^{-iHt}$ on $\mathcal H$ is unitary, and the bare resolvent / spectral measure on $\mathbb R^+$ has positive density. Once complex deformation $H_\theta$ is introduced, $H_\theta$ is **non-self-adjoint**, so $\langle \psi, H_\theta \psi \rangle$ is complex-valued. Positivity/dissipativity is not automatic from spectrum location; it is a quadratic-form / numerical-range condition ($\operatorname{Im}\langle\psi, H_\theta\psi\rangle \le 0$ for $A = -iH_\theta$ in the Lumer–Phillips sense).
2. **In the chaotic map & Prigogine lift (Stage 2):** For the expanding circle map $T$, the Ruelle operator $\mathcal L_0$ has a strictly positive Perron–Frobenius eigenfunction and a spectral gap $\kappa > 0$, while the tilted operator $\mathcal L_q$ has real, strictly convex pressure $\psi(q)$ for real $q$ ($\psi''(0) = \operatorname{Var}_\mu(\sigma) \ge 0$). Lyapunov decay $\frac{d\Omega}{dt} \le 0$ comes from transforming to a metric/basis where the generator has non-positive real/imaginary part on the decaying subspace, **not** from confining all eigenvalues to a single vertical line in $\mathbb C$.

### 2.2 Quadratic forms and Weil-type / spectral positivity criteria
In analytic number theory, conditions equivalent to RH are famously expressed as **positivity of quadratic forms** or **positivity of distribution pairings** (for example, Weil's positivity criterion or Li's positivity criterion):
- A quadratic form $\mathcal Q(f,f) \ge 0$ on a space of test functions $f$ encodes the location of zeros via Fourier/Mellin transforms and the explicit formula relating prime sums to zero sums.
- Crucial structural observation: **positivity of a quadratic form on an appropriate function space** is a *global* harmonic/spectral condition coupling all zeros $\rho$ via a positive kernel, rather than a local point-by-point eigenvalue condition on a single transfer operator $\mathcal L_s$ at one value of $s$.

### 2.3 Mayer operator $\mathcal L_s$ and quadratic forms
For the modular transfer operator $\mathcal L_s$ acting on a Hilbert or Banach space of holomorphic functions $\mathcal B(D)$ (such as a weighted Bergman space $A^2_\alpha(D)$):
- Even when $\mathcal L_s$ is compact/trace-class for $\operatorname{Re} s > \frac{1}{2}$ (or on an adapted disk/strip), $\mathcal L_s$ is **not** self-adjoint in general for complex $s$.
- Therefore, a quadratic form $\langle u, \mathcal L_s u \rangle$ is generally complex-valued. Its real and imaginary parts vary smoothly with $s$ and do not automatically force $\det(I - \mathcal L_s) = 0$ to occur exclusively at $\operatorname{Re} s = \frac{1}{4}$.
- Specifically, on the unitary line $\operatorname{Re} s = \frac{1}{2}$ (where $2s = 1 + 2it$), unitarity of the scattering matrix $\varphi(\frac{1}{2}+it)$ reflects the self-adjointness of the hyperbolic Laplacian $\Delta$ on $L^2(\mathrm{PSL}(2,\mathbb Z)\backslash\mathbb H)$, **not** the zeros of $\zeta(\rho)$ at $s = \rho/2$ (which sit at $\operatorname{Re} s = \frac{1}{4}$ under RH, i.e., $\operatorname{Re}(2s) = \frac{1}{2}$, halfway between the critical line $\frac{1}{2}$ and the unitary/pole line $1$ of $\zeta(2s)$).

---

## 3. Why half-plane / dissipativity bounds do not force $\operatorname{Re} s = \frac{1}{4}$

A recurring temptation in spectral-thermodynamic analogies is to reason:
*"Suppose an operator family or determinant satisfies a positivity, dissipativity, or half-plane bound; does that force zeros onto $\operatorname{Re} s = \frac{1}{4}$?"*

The answer is **no, not without extra structure**, for three clear mathematical reasons:

1. **A half-plane or strip inequality constrains a *region*, not a *line*:** Even if a function or quadratic form is non-negative or dissipative on a domain (say $\operatorname{Re} s > \frac{1}{4}$ or $\operatorname{Re} s < \frac{1}{4}$), an inequality on a region generally permits zeros (or interior/boundary behavior) across a two-dimensional region or off a 1D line unless a rigid identity (such as a functional equation + positivity/Herglotz/Nevanlinna structure) pins the zeros.
2. **Dissipativity governs *decay/growth*, not *line confinement*:** In Stage 1 (Friedrichs) and Stage 2 (chaotic map), dissipativity / spectral gap governs exponential decay rates ($\gamma$, $\kappa$, $-\frac{d\Omega}{dt}$). In $\zeta(s)$, non-trivial zeros $\rho = \beta + i\gamma$ have $\gamma \in \mathbb R$ as the *imaginary* part (oscillation frequency) and $\beta \in (0,1)$ as the *real* part. A dissipation rate corresponds to a real decay exponent, not automatically to $\beta = \frac{1}{2}$ ($\operatorname{Re} s = \frac{1}{4}$).
3. **Self-adjointness of the Laplacian lives at $\operatorname{Re} s = \frac{1}{2}$, while RH lives at $\operatorname{Re} s = \frac{1}{4}$:** The self-adjointness of $\Delta$ on $L^2(\mathrm{PSL}(2,\mathbb Z)\backslash\mathbb H)$ anchors the unitary line $\operatorname{Re} s = \frac{1}{2}$ (and discrete Maass eigenvalues $\frac{1}{2} \pm ir_n$). The Riemann zeros in the Selberg divisor sit at $s = \rho/2$, which lies on $\operatorname{Re} s = \frac{1}{4}$ iff $\operatorname{Re}\rho = \frac{1}{2}$. Bridging $\operatorname{Re} s = \frac{1}{2}$ (Laplacian self-adjointness / scattering unitarity) to $\operatorname{Re} s = \frac{1}{4}$ (Riemann critical line) is precisely the depth of RH—it cannot be bypassed by a generic dissipativity or norm estimate.

---

## 4. Summary of spectral constraints and status

| Aspect | Status | Mathematical role |
|---|---|---|
| **Involutions & fixed lines** | **Established** | $\rho \leftrightarrow 1-\rho$ fixes $\operatorname{Re}\rho = \frac{1}{2}$; under $s = \rho/2$, $s \leftrightarrow \frac{1}{2}-s$ fixes $\operatorname{Re} s = \frac{1}{4}$. |
| **Symmetry vs. zero localization** | **Established** | Symmetry pairs zeros across $\operatorname{Re} s = \frac{1}{4}$ but does not exclude off-line zeros by itself. |
| **Quadratic forms & positivity** | **Established (as criteria / structure)** | Positivity structures (e.g., Weil/Li-type quadratic forms or convex pressure $\psi(q)$) capture global/convex behavior, not automatic line confinement for non-self-adjoint $\mathcal L_s$. |
| **Dissipativity / spectral gap vs. $\operatorname{Re} s = \frac{1}{4}$** | **Established (no shortcut)** | Decay/dissipativity bounds do not force $\operatorname{Re}\rho = \frac{1}{2}$; RH remains independent and open. |

---

## 5. Closing assessment of Stage 3 (Zeta / Arithmetic)

Across Tasks 3A, 3B, and 3C, the arithmetic/spectral branch is now cleanly organized:
- **Task 3A** isolates the $+1$ (even) Mayer eigenspace $\det(I - \mathcal L_{\rho/2}) = 0$ for Eisenstein scattering zeros $s = \rho/2$ distinct from Maass zeros.
- **Task 3B** places the Eisenstein continuous spectrum and rigged states in a rigged Hilbert-space setting while keeping the absence of a physical thermodynamic arrow in $\zeta(\rho)=0$ explicit.
- **Task 3C** clarifies the exact role of reflection symmetries, quadratic forms, and positivity constraints around $\operatorname{Re}\rho = \frac{1}{2}$ / $\operatorname{Re} s = \frac{1}{4}$ without claiming an unproved reduction of RH.