# Master Roadmap & Index — Operator-Algebraic Irreversibility, Chaotic Dynamics, and the Mayer–Selberg–Riemann Branch

**Status:** Living architecture map and active research frontier index  
**Central Question:** *Does there exist a common spectral formulation of dynamical complexity and thermodynamic irreversibility, in which the Ruelle transfer operator and Prigogine's non-unitary transformation represent complementary aspects of the same underlying evolution?*

---

## 0. Foundational Guardrails and the Three Defining Pillars

Every module in this program is organized around **three defining pillars** of the central question:
1. **Spectral Correspondence:** How Ruelle / Pollicott–Ruelle / Mayer transfer-operator spectra relate to Prigogine's transformed generator $\Phi_{\mathrm{Prig}} = \Lambda^{-1} L \Lambda$ and rigged-space resonances;
2. **Dynamical Entropy vs. Microscopic Entropy Production:** How trajectory/Kolmogorov–Sinai entropy ($h_{KS}$) and tilted cumulants ($\psi(q)$) relate to microscopic dissipation / Lyapunov decay ($-\frac{d\Omega}{dt}$);
3. **Emergence of Irreversible Macroscopic Organization:** What general operator/rigged-space mechanism extracts forward-time irreversible structure from time-reversible or isometric microscopic dynamics—and where that structure meets (and stops short of) arithmetic zeta zeros.

Four mathematical guardrails govern every file:
- **Boundary-value & conjugation lock-in:** Keep $\eta_\mp(\zeta) = \eta(\zeta \mp i0_\theta)$, $V^*(z) = \overline{V(\bar z)}$, $\Gamma_\theta \leftrightarrow \Gamma_\theta^*$, and $(\alpha,\beta) \leftrightarrow (\beta,\alpha)$ under adjoints explicit.
- **Rigged-space vs. Hilbert-space discipline:** Keep self-adjoint/isometric generators on Hilbert/Banach spaces ($H$, $L = [H,\cdot]$, Koopman $U_T$, Laplacian $\Delta$) distinct from transformed/non-self-adjoint operators on nuclear/analytic test spaces ($\Phi$, $\mathbf{\Phi}_{\mathcal L}$, $\Phi_{\mathrm{an}}$, $\mathcal B(D)$, $\mathcal D_X$).
- **No unverified semigroup or spectral shortcuts:** Establish Lumer–Phillips contractivity and spectral gaps only where proved.
- **Clear separation of proved structure, conditional bounds, and open conjecture:** Keep operator/automorphic results distinct from unproved claims regarding the Riemann Hypothesis ($\operatorname{Re}\rho = \frac{1}{2}$, i.e., $\operatorname{Re} s = \frac{1}{4}$).

---

## 1. Unified Document & Module Index

### A. Friedrichs Model Foundation & Liouville–Prigogine Lift (Stages 1–3)

| File / Module | Core Scope & Key Results | Role in Architecture |
|---|---|---|
| `friedrichs_stage1_5_concrete_instantiation.md` | Sector-analytic countably Hilbert nuclear test space $\Phi = \mathbb C|1\rangle \oplus \Phi_{\mathrm{cont}}$ on $\overline{\mathcal S_\delta}$; continuity of resonance and deformed-continuum functionals; $H$-invariance. | Supplies the test-space topology and continuity guarantees for Stage 1 and Stage 2. |
| `establish_continuum_resolvent_jump.md` | Block-by-block evaluation of $\Delta\mathcal M_{11}, \Delta\mathcal M_{1c}, \Delta\mathcal M_{c1}, \Delta\mathcal M_{cc}$ across $\Gamma_\theta = e^{-i\theta}\mathbb R^+$, yielding the rank-one jump factorization $\frac{1}{2\pi i}\langle\phi_-|[R(\zeta)-R_+(\zeta)]|\phi_+\rangle = \langle\phi_-|\psi_\zeta^R\rangle\langle\psi_\zeta^L|\phi_+\rangle$. | Proves Eq. (7.3) with exact $\eta_\mp(\zeta)$ and $\mp i0_\theta$ orientation. |
| `stage2_liouville_lift_specification.md` | Nuclear Liouville space $\mathbf{\Phi}_{\mathcal L} = \Phi \widehat{\otimes} \Phi^\dagger$; four-sector eigenfunctionals ($RR, RC, CR, CC$); frequencies $\Lambda_{\alpha,\beta} = \alpha - \beta^*$; forward-time spectral expansion ($t \ge 0$). | Lifts single-particle resonance/continuum structure to density-operator evolution. |
| `stage2_biorthogonality_and_trace_pairings.md` | Full $4 \times 4$ sector biorthogonality; trace-functional decomposition via $\psi_\alpha^R$ and $\psi_\alpha^L$ with matching $\alpha$ ($\operatorname{Tr}(e^{-iLt}A) = \operatorname{Tr}(A)$); adjoint swap $(\alpha,\beta) \leftrightarrow (\beta,\alpha)$. | Closes Stage 2 obligations and supplies exact symmetry inputs for $\Lambda^{-1}$ and star-unitarity. |
| `stage3_lambda_intertwiner_star_unitarity_lyapunov.md` | Intertwiner $\Lambda^{-1} : \mathbf{\Phi}_{\mathcal L} \to \widehat{\mathcal K}$; Lumer–Phillips contractivity of $\widehat{W}_t = e^{-i\Phi_{\mathrm{Prig}}t}$; star-unitarity $\Lambda^{-1} = \Lambda^*$; split $\Phi_{\mathrm{Prig}} = \Phi_{\mathrm{even}} + i\Phi_{\mathrm{odd}}$; Lyapunov decay $\frac{d\Omega}{dt} \le 0$. | Completes the core Prigogine operator transformation and Lyapunov proof on $\mathbf{\Phi}_{\mathcal L}$. |
| `friedrichs_concrete_form_factor_discharge.md` | Explicit discharge on $V(z) = v_0 z^\alpha e^{-\kappa z^2}$: absence of bound/embedded states under $\lambda^2 < \frac{2\omega_1(2\kappa)^\alpha}{v_0^2\Gamma(\alpha)}$, large-arc/dominated convergence for completeness, and $L^2(\Gamma_\theta)/L^2(\Gamma_\theta^*)$ bounds. | Discharges model-level analytic/threshold proof obligations. |
| `spectral_relaxation_vs_mep_friedrichs.md` | Compares stroboscopic transfer relaxation $\kappa_{RR} = \gamma$ (plus gapless continuum $O(t^{-3})$ tail) and tilted cumulant $\psi_{RR}(q) = -2\gamma q$ ($\psi_{RR}''(0) = 0$) against Lyapunov dissipation $-\frac{d\Omega}{dt}$. | Benchmarks spectral relaxation against microscopic dissipation on the Friedrichs model. |

### B. Chaotic Dynamical Testbed (Broader Program — Stage 2)

| File / Module | Core Scope & Key Results | Role in Architecture |
|---|---|---|
| `broader_program_stage2_chaotic_dynamical_testbed.md` | Defines the dual expanding-map / chaotic-Liouvillian program linking $h_{KS}$, $\kappa$, $\psi(q)$, and $\Lambda^{-1}/\Omega(t)$. | Sets up multi-trajectory chaos with $h_{KS} > 0$ and $\psi''(0) > 0$. |
| `broader_program_stage2_deliverable2a_ruelle_tilted.md` | Asymmetric expanding map $T$ on $[0,1)$ with parameter $p$: exact Pollicott–Ruelle eigenvalues $\lambda_k = p^{k+1} + (1-p)^{k+1}$, gap $\kappa = -\ln[p^2+(1-p)^2]$, entropy $h_{KS} = -p\ln p - (1-p)\ln(1-p)$, tilted pressure $\psi(q) = \ln[p^{1+q}+(1-p)^{1+q}]$, and variance $\psi''(0) > 0$. | Exact solvable benchmark for Ruelle transfer & fluctuation thermodynamics. |
| `broader_program_stage2_deliverable2b_lambda_lift.md` | Rigged analytic space $\Phi_{\mathrm{an}}$, biorthogonal Pollicott–Ruelle basis, intertwiner $\Lambda^{-1}$, contractive evolution $\widehat{W}$, and Lyapunov functional $\Omega_n$ decaying at rate $2\kappa$ ($-\Delta\Omega_n > 0$). | Establishes the universal $2\kappa$ vs. $\kappa$ factor-of-2 law and separates $\kappa$, $h_{KS}$, and $\psi''(0)$. |
| `broader_program_stage2_deliverable2c_zeta_synthesis.md` | Synthesizes Stages 1–2 and bridges finite-branch expanding maps to the countable-branch Gauss map and Mayer operator $\mathcal L_s$ on $\mathrm{PSL}(2,\mathbb Z)\backslash\mathbb H$. | Connects chaotic transfer thermodynamics to Selberg and Riemann spectral data. |

### C. Arithmetic / Mayer–Selberg–Riemann Branch (Broader Program — Stage 3)

| File / Module | Core Scope & Key Results | Role in Architecture |
|---|---|---|
| `broader_program_stage3_task3a_mayer_parity_decomposition.md` | Nuclear Bergman/Hardy disk space $\mathcal B(D)$ ($D = B(1, 3/2)$); Hurwitz meromorphic continuation; determinant factorization $Z_{\mathrm{Sel}}(s) = \det(I-\mathcal L_s)\det(I+\mathcal L_s)$; Lewis–Zagier parity showing Eisenstein zeros $s = \rho/2$ lie in the $+1$ (even) eigenspace. | Fixes operator normalization, trace-class validity on $0 < \operatorname{Re} s < \frac{1}{2}$, and parity localization. |
| `broader_program_stage3_task3b_rigged_eisenstein_space.md` | Roelcke–Selberg decomposition on $L^2(\mathrm{PSL}(2,\mathbb Z)\backslash\mathbb H)$; unitary scattering $\varphi(\frac{1}{2}+ir)$ on $\operatorname{Re} s = \frac{1}{2}$; rigged space $\mathcal D_X \hookrightarrow L^2(X,d\mu) \hookrightarrow \mathcal D_X^\times$ housing resonances $s = \rho/2$ without breaking self-adjointness of $\Delta$. | Gives the rigged-space interpretation of Eisenstein scattering poles and states exact limits of the thermodynamic analogy. |
| `broader_program_stage3_task3c_positivity_quadratic_forms.md` | Reflection symmetries ($\rho \leftrightarrow 1-\rho$ on $\operatorname{Re}\rho = \frac{1}{2}$ $\leftrightarrow$ $s \leftrightarrow \frac{1}{2}-s$ on $\operatorname{Re} s = \frac{1}{4}$); non-self-adjoint quadratic forms on $\mathcal B(D)$ vs. Weil/Li positivity; why half-plane/dissipativity bounds alone do not force $\operatorname{Re} s = \frac{1}{4}$. | Audits positivity and symmetry constraints around the critical line. |

---

## 2. Cross-Cutting Synthesis Across the Three Pillars

1. **Pillar 1 — Spectral correspondence:** Unitary or isometric evolution on full Hilbert/Banach spaces hides non-self-adjoint decay or resonance poles ($z_0$, $\lambda_k = p^{k+1}+(1-p)^{k+1}$, or Mayer eigenvalues $\pm 1$ at $s = \rho/2$). Restricting to nuclear/analytic test spaces in a rigged Hilbert space exposes those spectral features consistently.
2. **Pillar 2 — Dynamical entropy vs. microscopic entropy production:** Across both the Friedrichs model and the asymmetric expanding map, quadratic Lyapunov norms $\Omega = \|\Lambda^{-1}\delta\rho\|_{\widehat{\mathcal K}}^2$ decay at **twice** the leading linear spectral relaxation rate ($2\gamma$ vs. $\gamma$; $2\kappa$ vs. $\kappa$), while trajectory entropy $h_{KS}$ and fluctuation variance $\psi''(0)$ capture hyperbolic trajectory proliferation and cumulant structure that a quadratic state norm alone does not encode.
3. **Pillar 3 — Irreversible emergence vs. arithmetic zeros:** Selecting a forward-time contour/filtration produces dissipative semigroups ($\frac{d\Omega}{dt} \le 0$ or $-\Delta\Omega_n > 0$) on dynamical test spaces, whereas Eisenstein scattering zeros $s = \rho/2$ appear as rigged/analytic resonances in the $+1$ Mayer eigenspace without carrying a physical arrow of time or forcing $\operatorname{Re} s = \frac{1}{4}$ by dissipativity alone.

---

## 3. Open Research Frontiers (Deeper Investigation Threads)

- **Frontier F1 (Obstruction / Sharp No-Go Analysis):** Formulate a precise mathematical statement showing why a quadratic/dissipative inequality on a half-plane or transfer operator does not imply zero localization on $\operatorname{Re} s = \frac{1}{4}$, isolating the exact extra symmetry/positivity ingredient needed.
- **Frontier F2 (Multi-Trajectory / Chaotic Liouvillian Lift):** Extend Stage 2 beyond a two-branch map to a coupled chaotic/hyperbolic or multi-mode system so $\Lambda^{-1}$, $\Phi_{\mathrm{Prig}}$, $h_{KS}$, and $\psi(q)$ interact across multiple scales.
- **Frontier F3 ($+1$ Mayer Eigenspace & Explicit/Positivity Structure):** Examine how the $+1$ (even) eigenspace of $\mathcal L_s$ at $s = \rho/2$ interacts with scattering/trace identities and positivity criteria.
- **Frontier F4 (Concrete Numerical / Symbolic Benchmarks):** Compute explicit eigenvalues, eigenfunctions, and decay/fluctuation profiles for specific parameter choices in the expanding map or Friedrichs model.