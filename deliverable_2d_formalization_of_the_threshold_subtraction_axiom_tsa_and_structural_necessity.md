# Deliverable 2D — Formalization of the Threshold-Subtraction Axiom (TSA) and Structural Necessity

**Status:** Formal Axiom Specification & Structural Bridge Deliverable (Stage 2 $\to$ Stage 3 $\to$ Cusp / Mayer–Selberg)  
**Builds on:**  
- `deliverable_2c_cusp_resonance_dictionary.md` (Corrected Liouville $CC$-sector scaling $I_{CC}(t) \sim C_{\alpha_V} t^{-(4\alpha_V+2)}$ and threshold integrability no-go)  
- `broader_program_stage3_task3a_mayer_parity_decomposition.md`  
- `broader_program_stage3_task3b_rigged_eisenstein_space.md`  
- `broader_program_stage3_task3c_positivity_quadratic_forms.md`  
- `corrigendum_friedrichs_zeta_revised.md`  

**Purpose:** Formalize the **Threshold-Subtraction Axiom (TSA)** on the rigged test space $\mathcal{D}_X$, prove its dynamical/thermodynamic necessity via the $CC$-sector integrability threshold ($\alpha_V > -1/4$), and isolate the exact constructive problem (normalized Patterson–Selberg regularization) without overclaiming a proof of the Riemann Hypothesis.

---

## 1. Background: The Cusp Integrability Obstruction

From Deliverable 2C, for a Friedrichs/Liouville system with single-particle near-threshold form factor $V(\omega) \sim v_0 \omega^{\alpha_V}$ ($\omega \downarrow 0$) and factorized two-slot Liouville pairing exponent $\alpha_L = 2\alpha_V > -1$:
1. The continuum–continuum ($CC$) contribution to Prigogine's Lyapunov functional $\Omega(t)$ along the deformed contour $\zeta = x e^{-i\theta}$, $\zeta' = x' e^{-i\theta}$ scales as
   $$
   I_{CC}(t) \sim C_{\alpha_V} \, t^{-(4\alpha_V + 2)}.
   \tag{1.1}
   $$
2. Finite total Lyapunov dissipation $\int_0^\infty I_{CC}(t)\,dt < \infty$ holds if and only if
   $$
   4\alpha_V + 2 > 1 \quad \Longleftrightarrow \quad \alpha_V > -\frac{1}{4} \quad \left(\alpha_L > -\frac{1}{2}\right).
   \tag{1.2}
   $$
3. On the modular surface $X = \mathrm{PSL}(2,\mathbb{Z})\backslash\mathbb{H}$, the unsubtracted Eisenstein continuous spectrum near threshold $\lambda = 1/4$ ($\omega = \lambda - 1/4 \downarrow 0$) has density of states $J_{\mathrm{Eis}}(\omega) \sim \omega^{-1/2}$, corresponding to
   $$
   \alpha_V = -\frac{1}{2}, \qquad \alpha_L = -1 \quad \Longrightarrow \quad I_{CC}(t) \sim C \cdot t^0 = C,
   \tag{1.3}
   $$
   yielding a non-decaying $CC$ sector and linearly divergent total dissipation $\int_0^T I_{CC}(t)\,dt \sim C T$.

Consequently, no bounded intertwiner $\Lambda^{-1}$ on the unsubtracted rigged space can produce a normalized Lyapunov functional with finite total dissipation across the cusp continuum.

---

## 2. Formal Statement of the Threshold-Subtraction Axiom (TSA)

**Axiom (Threshold-Subtraction Axiom — TSA):**  
Let $\mathcal{L}_s$ be the Mayer transfer operator on the modular surface $X = \mathrm{PSL}(2,\mathbb{Z})\backslash\mathbb{H}$, with Eisenstein density of states $J_{\mathrm{Eis}}(\omega)$ near the cusp threshold $\omega = 0$ (where the unsubtracted cusp has exponent $\alpha_V = -1/2$), and let $I_{CC}(t)$ denote the continuum–continuum contribution to the Lyapunov functional of the associated Liouville lift.

Then there exists a bounded operator $\mathcal{S}$ on the rigged test space $\mathcal{D}_X$—required to be invariant under the $\mathrm{PSL}(2,\mathbb{Z})$ action and to preserve the scattering-related zeros of the Selberg zeta function at $s = \rho/2$ (where $\rho$ runs over non-trivial zeros of the Riemann zeta function $\zeta$)—such that the subtracted transfer operator
$$
\mathcal{L}_s^{\mathrm{sub}} := \mathcal{L}_s - \mathcal{S}
\tag{2.1}
$$
satisfies the following three properties:

1. **(Threshold Exponent Shift):** The subtracted Eisenstein density of states has effective threshold exponent
   $$
   \alpha_V^{\mathrm{sub}} > -\frac{1}{4} \qquad \left(\text{equivalently } \alpha_L^{\mathrm{sub}} = 2\alpha_V^{\mathrm{sub}} > -\frac{1}{2}\right),
   \tag{2.2}
   $$
   strictly above the integrability threshold violated by the unsubtracted cusp ($\alpha_V = -1/2$).
2. **(Finite Integrated Lyapunov Dissipation):** The subtracted $CC$-sector Lyapunov contribution $I_{CC}^{\mathrm{sub}}(t)$ satisfies
   $$
   \int_0^\infty I_{CC}^{\mathrm{sub}}(t)\,dt < \infty,
   \tag{2.3}
   $$
   so that total Lyapunov dissipation $\int_0^\infty (-\dot\Omega^{\mathrm{sub}}(t))\,dt$ is finite.
3. **(Fredholm / Selberg Divisor Consistency):** On the physical strip ($0 < \operatorname{Re} s < \frac{1}{2}$, and by meromorphic continuation across the critical strip), the Fredholm determinant $\det(I - \mathcal{L}_s^{\mathrm{sub}})$ agrees with the Selberg zeta function $Z_{\mathrm{Sel}}(s)$ (up to the standard parity/boundary factors), so that the $\pm 1$ eigenvalues of $\mathcal{L}_s^{\mathrm{sub}}$ continue to encode the scattering-related zeros at $s = \rho/2$:
   $$
   \zeta(\rho) = 0 \quad \Longrightarrow \quad \pm 1 \in \sigma(\mathcal{L}_{\rho/2}^{\mathrm{sub}}).
   \tag{2.4}
   $$

**Epistemic Boundary of TSA:**  
The axiom asserts the **existence** of such an operator $\mathcal{S}$ on $\mathcal{D}_X$; it does not specify its explicit construction. The constructive realization of $\mathcal{S}$—the natural candidate for which is a suitably normalized Patterson–Selberg regularization—is precisely the open constructive problem addressed in Deliverable 2E.

---

## 3. Structural Theorem: Dynamical & Spectral Necessity of TSA

**Theorem (Necessity of Threshold Subtraction):**  
In the Mayer–Selberg–Eisenstein framework, subtracting a threshold operator $\mathcal{S}$ satisfying TSA is not merely a technical convenience for trace-class convergence:
1. **Thermodynamic / Liouvillian Well-Posedness:** Without subtracting $\mathcal{S}$, the effective threshold exponent remains $\alpha_V = -1/2$, so $I_{CC}(t) \sim C$ and $\int_0^\infty I_{CC}(t)\,dt = \infty$. Thus, any non-unitary intertwiner $\Lambda^{-1}$ constructed without TSA violates finite total dissipation before the discrete/resonant spectrum is even reached.
2. **Preservation of Arithmetic Spectral Data:** Condition (iii) ensures that removing the threshold divergence does not destroy the arithmetic scattering divisor $s = \rho/2$ housed in the $+1$ (even) eigenspace of $\mathcal{L}_s$ (established in Task 3A).
3. **Independence from RH:** TSA restores well-posedness of the regularized Liouvillian/transfer representation on the critical strip; it does **not** by itself constrain the zeros $\rho$ to the critical line $\operatorname{Re}\rho = \frac{1}{2}$ ($\operatorname{Re} s = \frac{1}{4}$).

---

## 4. Integration Summary

| Component | Status | Role in Unified Program |
|---|---|---|
| **Deliverable 2C** | Completed | Proves $I_{CC}(t) \sim C_{\alpha_V} t^{-(4\alpha_V+2)}$, identifies $\alpha_V > -1/4$, and establishes the no-go at $\alpha_V = -1/2$. |
| **Deliverable 2D (This File)** | Completed | Formalizes the Threshold-Subtraction Axiom (TSA) as the exact existential bridge making $\mathcal{L}_s^{\mathrm{sub}}$ thermodynamically and spectrally well-posed. |
| **Deliverable 2E** | Next / Open Constructive | Formulates the constructive specification for $\mathcal{S}$ via normalized Patterson–Selberg regularization on $\mathcal{D}_X$. |