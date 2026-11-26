# Deliverable 2F (Task 3D) — Coupled Sub-Problems of Condition (iii), Coordinate Bridge, and the $\delta$-Window Conditional Theorem

**Status:** Constructive Analytical Program & Conditional Theorem (Stage 2 $\to$ Stage 3 $\to$ Arithmetic Frontier)

**Builds on:**

* `deliverable_2c_cusp_resonance_dictionary.md`

* `deliverable_2d_threshold_subtraction_axiom.md`

* `deliverable_2e_patterson_selberg_constructive_spec.md`

* `broader_program_stage3_task3a_mayer_parity_decomposition.md`

* `broader_program_stage3_task3b_rigged_eisenstein_space.md`

* `broader_program_stage3_task3c_positivity_quadratic_forms.md`

**Purpose:** Unpack Condition (iii) of the Threshold-Subtraction Axiom (TSA / `§14.B.8`) into its three coupled sub-problems—**(iii-c)** coordinate/transform bridge, **(iii-a)** Fredholm/trace cancellation preservation, and **(iii-b)** divisor invariance at $s = \rho/2$—clarify the density-of-states vs. coupling interpretation and trace-pairing operator definition of $\mathcal{S}_{\varepsilon,\delta}$, establish the holomorphy decision procedure for Meaning 3 at stage **(iii-c)**, and state the $\delta$-window conditional theorem with explicit $\delta_{\max}(\varepsilon, \gamma)$ dependence.

## 0. Measure vs. Coupling Clarification and Trace-Pairing Operator Definition

In constructing the partial Patterson–Selberg subtraction operator $\mathcal{S}_{\varepsilon,\delta}$ on the rigged test space $\mathcal{D}_X$, the cutoff multiplier $\chi_{\varepsilon,\delta}(\omega)$ acts on the **Eisenstein density of states / spectral threshold measure** $J_{\mathrm{Eis}}(\omega)$ (and its associated trace/pairing density), **not** as an ad-hoc modification of the bare coupling/form factor $V(\omega)$.

Treating $\chi_{\varepsilon,\delta}(\omega)$ as a $\mathrm{PSL}(2,\mathbb{Z})$-invariant threshold measure modifier preserves modular symmetry and parity commutation ($[\mathcal{S}_{\varepsilon,\delta}, \mathcal{P}] = 0$), whereas altering a bare coupling without group invariance would risk breaking automorphy.

Because $\mathcal{S}_{\varepsilon,\delta}$ is defined by its action on the density of states rather than as an arbitrary operator modification that automatically commutes with $\mathcal{L}_s$, the operator notation $\mathcal{L}_s^{\mathrm{sub}} := \mathcal{L}_s - \mathcal{S}_{\varepsilon,\delta}$ should be understood precisely as follows: $\mathcal{S}_{\varepsilon,\delta}$ is the operator on the rigged test space whose **trace pairing against test functions reproduces the threshold-modified measure**, so that the trace and pairing structure of $\mathcal{L}_s^{\mathrm{sub}}$ match the regularized spectral density without assuming $[\mathcal{S}_{\varepsilon,\delta}, \mathcal{L}_s] = 0$ in general. Making this trace-pairing convention explicit up front ensures that subsequent trace evaluations in **(iii-a)** rest on an unambiguous operator definition.

## 1. The Three Coupled Sub-Problems of Condition (iii) and Their Execution Order

Condition (iii) of TSA requires that $\det(I - \mathcal{L}_s^{\mathrm{sub}})$ agrees with the Selberg zeta function $Z_{\mathrm{Sel}}(s)$ (up to standard parity/boundary/entire factors with no zeros on the physical strip) while preserving the scattering-related divisor at $s = \rho/2$. These requirements couple three sub-problems that must be tackled in the order **(iii-c)** $\to$ **(iii-a)** $\to$ **(iii-b)**:

1. **Sub-problem (iii-c) — Bridging the Laplacian Threshold Coordinate to the Mayer Kernel (Prerequisite):**

   On $\mathrm{PSL}(2,\mathbb{Z})\backslash\mathbb{H}$, Laplacian eigenvalues $\lambda$ and spectral parameters $s$ are related by $\lambda = s(1-s)$ (so on the unitary line $s = \frac{1}{2} + ir$, $\lambda = \frac{1}{4} + r^2$ and the threshold coordinate is $\omega = \lambda - \frac{1}{4} = r^2$). Transferring $\chi_{\varepsilon,\delta}(\omega)$ from this spectral/Selberg–Harish-Chandra threshold coordinate into Mayer's transfer operator $\mathcal{L}_s$ (on its disk/interval function space) requires using the Harish-Chandra / Selberg transform rather than identifying $\omega$ and $s$ directly, producing a transferred cutoff $\chi_{\varepsilon,\delta}^{\mathrm{Mayer}}(s)$ on the transfer/spectral side.

2. **Sub-problem (iii-a) — Fredholm / Trace Cancellation Preservation:**

   Once the cutoff is represented on the transfer/trace side via the trace-pairing operator $\mathcal{S}_{\varepsilon,\delta}$, $\mathcal{L}_s^{\mathrm{sub}} = \mathcal{L}_s - \mathcal{S}_{\varepsilon,\delta}$ modifies the trace formula by an $\varepsilon$- and $\delta$-dependent term. Verifying determinant well-posedness requires showing that the continuous-spectrum cancellation against the scattering contribution remains intact and that any residual $(\varepsilon,\delta)$-dependent trace term is either entire with no zeros on the physical strip or canceled by the corresponding scattering/regularization adjustment.

3. **Sub-problem (iii-b) — Divisor Invariance at** $s = \rho/2$**:**

   Even with a well-defined Fredholm determinant and preserved trace cancellation, one must verify that its zeros on the physical strip—specifically within the $+1$ (even) Mayer eigenspace—remain at $s = \rho/2$ (for non-trivial Riemann zeros $\rho = \beta + i\gamma$) rather than shifting under the partial cutoff as $\varepsilon$, $\gamma$, and $\delta$ vary.

## 2. Decision Procedure for Condition (iii) at Stage (iii-c)

Flagging Condition (iii) as open in Deliverable 2E can be turned from a static taxonomy into an actionable **decision procedure** starting at **(iii-c)**:

* **Holomorphy / Singularity Test at (iii-c):** Check whether the transferred cutoff $\chi_{\varepsilon,\delta}^{\mathrm{Mayer}}(s)$ is **holomorphic on the physical strip** (for the regime of $\varepsilon$, $\gamma$, and $\delta$ under consideration):
  * **If $\chi_{\varepsilon,\delta}^{\mathrm{Mayer}}(s)$ is holomorphic on the physical strip:** We are in **Meaning 1 or Meaning 2**—either the divisor/determinant preservation follows from existing Selberg / Patterson–Selberg regularization identities (**Meaning 1**), or it requires bounding/canceling a new $(\varepsilon,\delta)$-dependent trace term via a modified trace/perturbation result (**Meaning 2**). Thus, checking holomorphy of $\chi_{\varepsilon,\delta}^{\mathrm{Mayer}}(s)$ on the physical strip is the first computation to carry out in **(iii-c)** before moving to **(iii-a)** and **(iii-b)**.
  * **If $\chi_{\varepsilon,\delta}^{\mathrm{Mayer}}(s)$ fails to be holomorphic on the physical strip (or induces divisor-disrupting singularities there):** We are in **Meaning 3**—a structural obstruction to partial threshold cutoffs of this form, signaling that a different regularization kernel, a subtraction acting on a different spectral/eigenvalue coordinate, or a refined axiom ($\mathrm{TSA}'$) is required.

## 3. Conditional Theorem (Coordinate-Dependent $\delta_{\max}(\varepsilon, \gamma)$ Formulation)

> **Conditional Theorem (Finite Dissipation & Arithmetic Preservation on a Coordinate-Dependent $\delta$-Window):**
>
> Suppose that for a given threshold scale $\varepsilon > 0$ and non-trivial zero imaginary-part range (with $\rho = \beta + i\gamma$), there exists an upper bound $\delta_{\max}(\varepsilon, \gamma) > \frac{1}{4}$ (either explicitly as a function $\delta_{\max}(\varepsilon, \gamma)$ or uniformly over a stated range of $\gamma$) such that for $\delta \in \left(\frac{1}{4}, \delta_{\max}(\varepsilon, \gamma)\right)$, the $\mathrm{PSL}(2,\mathbb{Z})$-invariant, parity-commuting partial Patterson–Selberg subtraction $\mathcal{S}_{\varepsilon,\delta}$ on $\mathcal{D}_X$ (defined via its trace pairing on the threshold-modified density of states):
>
> 1. shifts the effective threshold exponent to $\alpha_V^{\mathrm{sub}} = -\frac{1}{2} + \delta > -\frac{1}{4}$ ($\alpha_L^{\mathrm{sub}} = -1 + 2\delta > -\frac{1}{2}$), giving finite integrated $CC$-sector dissipation $\int_0^\infty I_{CC}^{\mathrm{sub}}(t)\,dt < \infty$; and
>
> 2. preserves the Fredholm determinant / Selberg zeta divisor at $s = \rho/2$ (up to a zero-free entire/boundary factor on the physical strip).
>
> Then on this regime, the regularized transfer/Liouvillian framework achieves finite total dissipation while preserving the $s = \rho/2$ scattering-related zero structure. Computing $\delta_{\max}(\varepsilon, \gamma)$ and characterizing how the divisor responds as $\delta$ varies is the central analytical task ahead.

The $\delta$-window is both **coordinate-dependent** and **parameter-dependent ($\delta_{\max}(\varepsilon, \gamma)$)**: the exponent parameter $\delta$ entering $\chi_{\varepsilon,\delta}(\omega)$ on the Laplacian threshold side is not identical to the $\delta$ parameter controlling trace cancellation and divisor invariance on the Mayer transfer side, and their exact relationship must be derived explicitly in **(iii-c)** (conflating the two $\delta$ parameters risks overestimating the width of the admissible window). Moreover, $\delta_{\max}$ is not a universal constant independent of scale and height: as $\varepsilon \to 0$ the cutoff sharpens and the transferred Mayer cutoff may develop singularities, while as $\gamma$ varies the divisor at $s = \rho/2$ may exhibit varying sensitivity to the cutoff.