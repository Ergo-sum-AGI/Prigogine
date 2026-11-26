# Deliverable 2E — Explicit Patterson–Selberg Construction of $\mathcal{S}$, Failure-Mode Audit, and Parity/Determinant Verification

**Status:** Constructive Open-Problem Specification & Program Synthesis (Stage 2 $\to$ Stage 3 $\to$ Arithmetic Frontier)

**Builds on:**

* `deliverable_2c_cusp_resonance_dictionary.md` (Corrected Liouville $CC$-sector scaling $I_{CC}(t) \sim C_{\alpha_V} t^{-(4\alpha_V+2)}$ and threshold integrability no-go)

* `deliverable_2d_threshold_subtraction_axiom.md` (Formal statement of the Threshold-Subtraction Axiom — TSA / `§14.B.8`)

* `broader_program_stage3_task3a_mayer_parity_decomposition.md`

* `broader_program_stage3_task3b_rigged_eisenstein_space.md`

* `broader_program_stage3_task3c_positivity_quadratic_forms.md`

* `master_roadmap_and_index.md`

**Purpose:** Translate the existential **Threshold-Subtraction Axiom (TSA)** of Deliverable 2D into an explicit operator candidate $\mathcal{S}_{\varepsilon,\delta}$ on the rigged test space $\mathcal{D}_X$ via partial Patterson–Selberg regularization, verify conditions **(i)** and **(ii)**, guard against the three structural failure modes, and audit parity commutation and determinant agreement in condition **(iii)**.

---

## 1. Constructive Ansatz for $\mathcal{S}$ via Partial Patterson–Selberg Regularization

From Deliverables 2C and 2D, on the unsubtracted cusp/Eisenstein threshold ($\omega = \lambda - 1/4 \downarrow 0$), the single-particle threshold exponent is $\alpha_V = -1/2$ and the two-slot Liouville $CC$-sector pairing exponent is $\alpha_L = 2\alpha_V = -1$, producing non-decaying $I_{CC}(t) \sim C$ and linearly divergent total dissipation $\int^T I_{CC}(t)\,dt \sim C T$. Finite integrated dissipation requires shifting the effective threshold exponent into $\alpha_V^{\mathrm{sub}} > -1/4$ ($\alpha_L^{\mathrm{sub}} > -1/2$).

### 1.1 Spectral / Cusp-Coordinate Cutoff Operator

Let $\mathcal{D}_X$ be the rigged test space associated with the modular quotient $X = \mathrm{PSL}(2,\mathbb{Z})\backslash\mathbb{H}$ (Task 3B), where test states admit a spectral/cusp-threshold representation in the threshold coordinate $\omega \ge 0$.

For a threshold scale $\varepsilon > 0$ and lifting exponent $\delta > \frac{1}{4}$, define the smooth threshold-attenuating multiplier $\chi_{\varepsilon,\delta}(\omega)$ on $[0,\infty)$ by

$$
\chi_{\varepsilon,\delta}(\omega) :=
\begin{cases}
1, & \omega \ge \varepsilon, \\[6pt]
\left(\dfrac{\omega}{\varepsilon}\right)^{\delta} \eta_\varepsilon(\omega), & 0 \le \omega < \varepsilon,
\end{cases}
\tag{1.1}
$$

where $\eta_\varepsilon(\omega)$ is a smooth transition factor satisfying $\eta_\varepsilon(\varepsilon) = 1$, $\eta_\varepsilon(0^+) = 1$, and $\eta_\varepsilon > 0$ on $[0,\varepsilon]$, so that $\chi_{\varepsilon,\delta} \in C^\infty((0,\infty))$ with $\chi_{\varepsilon,\delta}(\omega) \equiv 1$ for all $\omega \ge \varepsilon$.

Define the **partial Patterson–Selberg subtraction operator** $\mathcal{S}_{\varepsilon,\delta}$ on $\mathcal{D}_X$ by acting on the $\mathrm{PSL}(2,\mathbb{Z})$-invariant cusp/spectral coordinate with weight $1 - \chi_{\varepsilon,\delta}(\omega)$:

$$
\mathcal{L}_s^{\mathrm{sub}} := \mathcal{L}_s - \mathcal{S}_{\varepsilon,\delta}.
\tag{1.2}
$$

Because $\chi_{\varepsilon,\delta}(\omega) = 1$ for $\omega \ge \varepsilon$, $\mathcal{S}_{\varepsilon,\delta}$ vanishes identically outside the threshold neighborhood $\omega \in [0,\varepsilon)$ and tempers only the singular threshold behavior rather than removing the entire continuous spectrum.

---

## 2. Verification of Conditions (i) and (ii)

### 2.1 Condition (i): Threshold Exponent Shift

Near the cusp threshold ($\omega \downarrow 0$), the unsubtracted threshold scaling has single-particle exponent $\alpha_V = -1/2$ and Liouville exponent $\alpha_L = 2\alpha_V = -1$. Multiplication by $\chi_{\varepsilon,\delta}(\omega) \sim (\omega/\varepsilon)^\delta$ shifts the effective threshold exponents of $\mathcal{L}_s^{\mathrm{sub}}$ to

$$
\alpha_V^{\mathrm{sub}} = -\frac{1}{2} + \delta, \qquad \alpha_L^{\mathrm{sub}} = 2\alpha_V^{\mathrm{sub}} = -1 + 2\delta.
\tag{2.1}
$$

For any $\delta > \frac{1}{4}$, we obtain

$$
\alpha_V^{\mathrm{sub}} > -\frac{1}{4}, \qquad \alpha_L^{\mathrm{sub}} > -\frac{1}{2},
\tag{2.2}
$$

strictly crossing the integrability threshold $\alpha_V = -1/4$ ($\alpha_L = -1/2$).

### 2.2 Condition (ii): Finite Integrated $CC$-Sector Dissipation

Applying Deliverable 2C (§1.1) with $\alpha_L^{\mathrm{sub}} = -1 + 2\delta > -1/2$, the subtracted $CC$-sector Lyapunov contribution decays at large $t$ as

$$
I_{CC}^{\mathrm{sub}}(t) \sim C_{\alpha_L^{\mathrm{sub}}} \, t^{-2(\alpha_L^{\mathrm{sub}} + 1)} = C_\delta \, t^{-4\delta}.
\tag{2.3}
$$

Integrating over $t \in [0,\infty)$ yields

$$
\int_0^\infty I_{CC}^{\mathrm{sub}}(t)\,dt < \infty \iff 4\delta > 1 \iff \delta > \frac{1}{4} \iff \alpha_V^{\mathrm{sub}} > -\frac{1}{4},
\tag{2.4}
$$

guaranteeing finite total Lyapunov dissipation $\int_0^\infty (-\dot\Omega^{\mathrm{sub}}(t))\,dt < \infty$.

---

## 3. Guarding Against the Three Structural Failure Modes

To serve as a valid realization of TSA, $\mathcal{S}_{\varepsilon,\delta}$ is explicitly structured to avoid three failure modes:

1. **Failure Mode 1 — Over-Aggressive Subtraction (Full Eisenstein Removal):**  
   Subtracting the entire Eisenstein/cusp contribution removes the cusp completely ($\alpha_V^{\mathrm{sub}} \to +\infty$, trivializing (i)–(ii)) but strips out the scattering-related zeros at $s = \rho/2$, violating **(iii)**.  
   *Resolution:* Because $\chi_{\varepsilon,\delta}(\omega) \equiv 1$ for $\omega \ge \varepsilon$ and only attenuates $\omega < \varepsilon$ by $(\omega/\varepsilon)^\delta$, $\mathcal{S}_{\varepsilon,\delta}$ removes the singular $\omega^{-1/2}$ threshold divergence without erasing the global scattering structure.

2. **Failure Mode 2 — Automorphy-Breaking Cutoff:**  
   An ad-hoc cutoff that fails to commute with $\mathrm{PSL}(2,\mathbb{Z})$ destroys modular invariance, so $\mathcal{L}_s^{\mathrm{sub}}$ ceases to represent the modular quotient and violates **(iii)**.  
   *Resolution:* Because the threshold coordinate $\omega$ and the cusp/spectral representation are defined on the $\mathrm{PSL}(2,\mathbb{Z})$-invariant quotient $\mathrm{PSL}(2,\mathbb{Z})\backslash\mathbb{H}$ (commuting with the parabolic stabilizer), $\mathcal{S}_{\varepsilon,\delta}$ preserves modular invariance on $\mathcal{D}_X$.

3. **Failure Mode 3 — Domain Restriction Masquerading as Subtraction:**  
   Restricting $\mathcal{D}_X$ to functions whose Eisenstein transforms vanish faster than $\omega^{1/4}$ near the cusp is a domain restriction rather than an operator subtraction $\mathcal{L}_s^{\mathrm{sub}} = \mathcal{L}_s - \mathcal{S}$, and risks shrinking the test space below what is needed to resolve $s = \rho/2$.  
   *Resolution:* $\mathcal{S}_{\varepsilon,\delta}$ acts as an explicit subtraction operator $\mathcal{L}_s - \mathcal{S}_{\varepsilon,\delta}$ on the full rigged test space $\mathcal{D}_X$, keeping the domain of test functions intact.

---

## 4. Condition (iii), Parity Preservation, and the Remaining Analytical Stress Test

### 4.1 Parity Decomposition and Explicit Parity Commutation

From Task 3A, the Selberg zeta function decomposes across parity sectors:

$$
Z_{\mathrm{Sel}}(s) = \det(I - \mathcal{L}_s^2) = \det(I - \mathcal{L}_s)\det(I + \mathcal{L}_s) \quad (\text{up to standard boundary/normalization factors}),
\tag{4.1}
$$

with the $+1$ (even) eigenspace housing the scattering-related zeros at $s = \rho/2$.

For $\mathcal{L}_s^{\mathrm{sub}} = \mathcal{L}_s - \mathcal{S}_{\varepsilon,\delta}$ to preserve this parity decomposition, $\mathcal{S}_{\varepsilon,\delta}$ must **commute with the parity involution** $\mathcal{P}$:

$$
[\mathcal{S}_{\varepsilon,\delta}, \mathcal{P}] = 0.
\tag{4.2}
$$

Because $\mathcal{P}$ is induced by the modular reflection/involution on $\mathrm{PSL}(2,\mathbb{Z})\backslash\mathbb{H}$ and $\chi_{\varepsilon,\delta}(\omega)$ depends solely on the $\mathrm{PSL}(2,\mathbb{Z})$-invariant threshold variable $\omega$, parity commutation holds naturally. To avoid any ambiguity in condition **(iii)**, **parity invariance ($[\mathcal{S}, \mathcal{P}] = 0$) is recorded explicitly as a required sub-condition alongside $\mathrm{PSL}(2,\mathbb{Z})$-invariance**.

### 4.2 Where Condition (iii) Remains Open as an Analytical Verification Target

While conditions **(i)** and **(ii)** follow directly from $\delta > 1/4$ and parity commutation **(4.2)** aligns with modular symmetry, **proving that $\det(I - \mathcal{L}_s^{\mathrm{sub}})$ agrees with $Z_{\mathrm{Sel}}(s)$ up to a non-vanishing entire factor on the physical strip—without perturbing or shifting the zeros at $s = \rho/2$—is the central analytical bottleneck of Deliverable 2E**:

* One must verify that tempering the threshold via $\chi_{\varepsilon,\delta}(\omega)$ preserves the Fredholm/trace cancellation of the continuous spectrum without introducing spurious zeros/poles or shifting the divisor at $s = \rho/2$.
* One must bridge the spectral threshold coordinate $\omega = \lambda - 1/4$ of the Laplacian $\Delta$ on $\mathrm{PSL}(2,\mathbb{Z})\backslash\mathbb{H}$ directly to the disk/interval kernel representation of Mayer's transfer operator $\mathcal{L}_s$.

---

## 5. Updated End-to-End Program Synthesis (Stages 1–3 + Deliverables 2A–2E)

| Layer | Module / Deliverable | Core Mathematical Content | Epistemic Status |
|---|---|---|---|
| **Layer 1: Quantum / Field Prototype** | Friedrichs Stages 1–3 (`friedrichs_stage1_5...`, `stage2...`, `stage3...`) | Sector-analytic nuclear space $\mathbf{\Phi}_{\mathcal{L}}$; 4-sector biorthogonality; star-unitary $\Lambda^{-1}$; Lyapunov decay $\dot\Omega \le 0$ ($2\gamma$ rate + continuum tail). | **Proved** (model-complete) |
| **Layer 2: Uniform Chaotic Prototype** | Deliverables 2A & 2B (`broader_program_stage2_deliverable2a/2b...`) | Expanding circle map: exact Ruelle spectrum $\lambda_k = p^{k+1}+(1-p)^{k+1}$, gap $\kappa$, entropy $h_{KS}$, tilted pressure $\psi(q)$, and Lyapunov decay $2\kappa$. | **Proved** (exact closed form) |
| **Layer 3: Cusp No-Go & Dictionary** | Deliverable 2C (`deliverable_2c_cusp_resonance_dictionary.md`) | Two-slot Liouville tail $I_{CC}(t) \sim C_{\alpha_V} t^{-(4\alpha_V+2)}$; finite dissipation iff $\alpha_V > -1/4$; unsubtracted cusp ($\alpha_V = -1/2$) gives $I_{CC}(t) \sim C$ (linear divergence). | **Proved** (sharp no-go) |
| **Layer 4: Existential Bridge** | Deliverable 2D (`deliverable_2d_threshold_subtraction_axiom.md`) | **Threshold-Subtraction Axiom (TSA / `§14.B.8`):** posits bounded $\mathrm{PSL}(2,\mathbb{Z})$-invariant $\mathcal{S}$ on $\mathcal{D}_X$ lifting $\alpha_V \mapsto \alpha_V^{\mathrm{sub}} > -1/4$ while preserving $s = \rho/2$ in $\det(I - \mathcal{L}_s^{\mathrm{sub}})$. | **Formalized Axiom** |
| **Layer 5: Constructive & Arithmetic Frontier** | Tasks 3A–3C & Deliverable 2E (`deliverable_2e_patterson_selberg_constructive_spec.md`) | Partial cutoff operator $\mathcal{S}_{\varepsilon,\delta}$ satisfies (i)–(ii) and avoids Failure Modes 1–3; Condition (iii) determinant/divisor invariance and RH ($\operatorname{Re} s = \frac{1}{4}$) remain open. | **Constructive Target & Open Frontier** |