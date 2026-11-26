# Deliverable 2C — Cusp–Resonance Dictionary, Corrected Liouville CC-Sector Scaling, and the Threshold Integrability No-Go

**Status:** Corrected technical execution and sharp no-go statement (with integration sections §5.6, §8.1, and §8.2)  
**Supersedes:** Earlier draft notes on \$I\_{CC}(t)\$ asymptotics that used a single-particle exponent without accounting for the two-slot Liouville product structure or misidentified the critical threshold  
**Builds on:** `friedrichs_concrete_form_factor_discharge.md`, Stage 2 four-sector biorthogonality & trace pairings, Deliverable 2B (`broader_program_stage2_deliverable2b_lambda_lift.md`), Stage 3 non-unitary intertwiner / Lyapunov functional notes, Task 3B (`broader_program_stage3_task3b_rigged_eisenstein_space.md`), and Task 3C (`broader_program_stage3_task3c_positivity_quadratic_forms.md`)  
**Purpose:** (i) Correct the Liouville \$CC\$-sector large-\$t\$ scaling by accounting for the product structure of the Liouville pairing; (ii) identify the correct critical exponent as an integrability threshold (finite total dissipation), rather than a "power-law vs. exponential" crossover; (iii) show that the cusp/Eisenstein density of states sits on a marginal non-decaying case (\$\\alpha\_V \= \-1/2\$, \$\\alpha\_L \= \-1\$); (iv) state the sharp no-go and the exact missing axiom; and (v) integrate cleanly with Tasks 3B, 3C, and the corrigendum.

---

## 0\. Notation and Conventions

Throughout this deliverable:

- **Single-particle form-factor exponent** is denoted \$\\alpha\_V\$. The admissible Friedrichs form factor near threshold is \[ V(\\omega) \\sim v\_0 \\omega^{\\alpha\_V} \\quad \\text{as } \\omega \\downarrow 0, \\qquad J(\\omega) \= \|V(\\omega)\|^2 \\sim v\_0^2 \\omega^{2\\alpha\_V}. \]  
- **Liouville pairing exponent** is denoted \$\\alpha\_L\$. The Liouville \$CC\$-sector pairing near the origin scales as \[ \\left\|\\langle\\langle \\Psi\_{xe^{-i\\theta}, x'e^{-i\\theta}}^L \\mid \\rho\_0 \\rangle\\rangle\\right\| \\sim c\_0 (x x')^{\\alpha\_L/2}, \] so its squared modulus scales as \$(x x')^{\\alpha\_L}\$.  
- **Relation between \$\\alpha\_L\$ and \$\\alpha\_V\$:** The two exponents satisfy \$\\alpha\_L \= 2\\alpha\_V\$, because the Liouville pairing factorizes into a product of two single-particle pairings: \[ \\langle\\langle \\Psi\_{\\zeta,\\zeta'}^L \\mid \\varphi\_+ \\chi\_+^\\dagger \\rangle\\rangle \= \\langle \\psi\_\\zeta^L \\mid \\varphi\_+ \\rangle \\cdot \\overline{\\langle \\psi\_{\\zeta'}^L \\mid \\chi\_+ \\rangle}. \] Each slot contributes one factor of \$\\alpha\_V\$; the squared modulus therefore contributes \$2\\alpha\_V \= \\alpha\_L\$.  
- **Contour and measure:** The measure is the flat \$dx,dx'\$ on \$(0,\\infty)^2\$ along the deformed contour \$\\zeta \= x e^{-i\\theta}\$, \$\\zeta' \= x' e^{-i\\theta}\$, with \$\\theta \\in (0, \\pi/2)\$ fixed and \$\\mu := 2\\sin\\theta \> 0\$.

---

## 1\. Liouville \$CC\$-Sector Lyapunov Contribution \$I\_{CC}(t)\$

The \$CC\$-sector contribution to Prigogine's Lyapunov functional \$\\Omega(t)\$ is \[ I\_{CC}(t) := \\iint\_{(0,\\infty)^2} e^{-2(x+x')\\sin\\theta \\cdot t} \\cdot \\left\|\\langle\\langle \\Psi\_{xe^{-i\\theta}, x'e^{-i\\theta}}^L \\mid \\rho\_0 \\rangle\\rangle\\right\|^2 , dx , dx'. \] Assume the near-threshold Liouville pairing scaling \[ \\left\|\\langle\\langle \\Psi\_{xe^{-i\\theta}, x'e^{-i\\theta}}^L \\mid \\rho\_0 \\rangle\\rangle\\right\| \\sim c\_0 (x x')^{\\alpha\_L/2} \\quad \\text{as } x, x' \\downarrow 0, \] with \$\\alpha\_L \> \-1\$ so the pairing is locally integrable at the threshold, and with decay or regularization at infinity ensuring convergence.

### 1.1 Rescaling and Exact Asymptotic Exponent

Set \$\\mu := 2\\sin\\theta \> 0\$ and change variables: \[ u := \\mu t x, \\qquad v := \\mu t x', \\qquad dx,dx' \= (\\mu t)^{-2},du,dv. \] Substituting into \$I\_{CC}(t)\$ gives \[ I\_{CC}(t) \= \\iint\_{(0,\\infty)^2} e^{-(u+v)} \\left\|\\langle\\langle \\Psi\_{\\frac{u}{\\mu t}e^{-i\\theta}, \\frac{v}{\\mu t}e^{-i\\theta}}^L \\mid \\rho\_0 \\rangle\\rangle\\right\|^2 (\\mu t)^{-2},du,dv. \] Using the near-origin scaling for large \$t\$: \[ I\_{CC}(t) \\sim c\_0^2 \\iint\_{(0,\\infty)^2} e^{-(u+v)} \\left(\\frac{u}{\\mu t}\\right)^{\\alpha\_L} \\left(\\frac{v}{\\mu t}\\right)^{\\alpha\_L} (\\mu t)^{-2},du,dv \= c\_0^2 (\\mu t)^{-2\\alpha\_L \- 2} \\left(\\int\_0^\\infty e^{-u} u^{\\alpha\_L},du\\right)^2. \] Evaluating the Gamma integral \$\\int\_0^\\infty e^{-u} u^{\\alpha\_L},du \= \\Gamma(\\alpha\_L \+ 1)\$ for \$\\alpha\_L \> \-1\$ yields the exact power-law asymptotics \[ I\_{CC}(t) \\sim C\_{\\alpha\_L} \\cdot t^{-2(\\alpha\_L \+ 1)}, \\qquad C\_{\\alpha\_L} := \\frac{c\_0^2 , \\Gamma(\\alpha\_L \+ 1)^2}{(2\\sin\\theta)^{2\\alpha\_L \+ 2}}. \] In terms of the single-particle form-factor exponent \$\\alpha\_V\$ (using \$\\alpha\_L \= 2\\alpha\_V\$): \[ I\_{CC}(t) \\sim C\_{\\alpha\_V} \\cdot t^{-(4\\alpha\_V \+ 2)}. \] Because the Liouville pairing factorizes across two slots, the \$CC\$-sector exponent is \$4\\alpha\_V \+ 2\$, not \$2\\alpha\_V \+ 2\$ (which governs single-particle survival behavior; in particular, \$\\alpha\_V \= 1/2\$ gives \$t^{-4}\$ in the Liouville \$CC\$ sector rather than \$t^{-3}\$).

---

## 2\. Competition with Exponential Resonance Decay \$e^{-2\\gamma t}\$: The Correct Statement

The isolated \$RR\$ resonance contributes \[ I\_{\\mathrm{res}}(t) \\sim A\_{\\mathrm{res}} \\cdot e^{-2\\gamma t}, \\qquad \\gamma \> 0\. \] Comparing \$I\_{\\mathrm{res}}\$ and \$I\_{CC}\$: \[ \\frac{I\_{\\mathrm{res}}(t)}{I\_{CC}(t)} \= \\frac{A\_{\\mathrm{res}}}{C\_{\\alpha\_L}} \\cdot t^{2(\\alpha\_L \+ 1)} \\cdot e^{-2\\gamma t} \\longrightarrow 0 \\quad \\text{as } t \\to \\infty, \] for every \$\\alpha\_L \> \-1\$ and every \$\\gamma \> 0\$. Therefore:

- The power law dominates asymptotically at large \$t\$ for every \$\\alpha\_L \> \-1\$, because exponential decay decays faster than any fixed power law.  
- A crossover time \$t\_*(\\alpha\_L, \\gamma)\$ where \$I\_{\\mathrm{res}}(t\_*) \= I\_{CC}(t\_*)\$ satisfies \[ t\_*^{\\alpha\_L \+ 1} e^{-\\gamma t\_*} \= \\sqrt{\\frac{C\_{\\alpha\_L}}{A\_{\\mathrm{res}}}}, \] scaling asymptotically as \$t\_* \= \\mathcal{O}(\\gamma^{-1}\\ln(A\_{\\mathrm{res}}/C\_{\\alpha\_L}))\$ when \$A\_{\\mathrm{res}} \\gg C\_{\\alpha\_L}\$. For \$t \< t\_*\$, the resonance dominates; for \$t \> t\_*\$, the \$CC\$ tail dominates.

---

## 3\. The Correct Critical Exponent: Integrability of Total Dissipation

The physically meaningful threshold is **finite total dissipation**: \[ \\int\_0^\\infty I\_{CC}(t),dt \< \\infty. \] Since \$I\_{CC}(t) \\sim C\_{\\alpha\_L} t^{-2(\\alpha\_L \+ 1)}\$, \[ \\int^T I\_{CC}(t),dt \\text{ converges as } T \\to \\infty \\iff 2(\\alpha\_L \+ 1\) \> 1 \\iff \\alpha\_L \> \-\\frac{1}{2}. \] Equivalently, in terms of the single-particle form-factor exponent (\$\\alpha\_L \= 2\\alpha\_V\$): \[ \\int\_0^\\infty I\_{CC}(t),dt \< \\infty \\iff \\alpha\_V \> \-\\frac{1}{4}. \] Total Lyapunov dissipation is \$\\int\_0^\\infty (-\\dot\\Omega(t)),dt \= \\Omega(0) \- \\Omega(\\infty)\$. When \$\\int I\_{CC},dt\$ diverges, total dissipation is infinite and no normalized Lyapunov functional with finite total dissipation exists.

### 3.1 The Cusp / Eisenstein Case

Near the cusp, the Eisenstein density of states at threshold \$\\lambda \= 1/4\$ behaves as \$\\sim (\\lambda \- 1/4)^{-1/2}\$, i.e., \$J(\\omega) \\sim \\omega^{-1/2}\$ with \$\\omega \= \\lambda \- 1/4\$. In the Friedrichs normalization \$V(\\omega) \\sim v\_0 \\omega^{\\alpha\_V}\$, this corresponds to \[ \\alpha\_V \= \-\\frac{1}{2}, \\qquad \\text{hence } \\alpha\_L \= 2\\alpha\_V \= \-\\frac{1}{2} \\cdot 2 \= \-1. \] Substituting into the \$CC\$-sector exponent gives \[ 4\\alpha\_V \+ 2 \= 4\!\\left(-\\frac{1}{2}\\right) \+ 2 \= 0, \] so \[ I\_{CC}(t) \\sim C \\cdot t^0 \= C \\quad (\\text{constant, non-decaying}). \] The \$CC\$-sector contribution to the Lyapunov functional fails to decay at all in the cusp/Eisenstein case, and the integrated dissipation \$\\int^T C,dt \= C T\$ diverges linearly.

---

## 4\. Sharp No-Go Statement

**No-Go Proposition (Threshold Integrability Obstruction to Prigogine's Construction on Cusp Models):**  
Let the Friedrichs model have form factor \$V(\\omega) \\sim v\_0 \\omega^{\\alpha\_V}\$ near threshold, and let \$\\rho\_0\$ be an analytic initial state with non-vanishing \$CC\$-sector pairing scaling \$\\alpha\_L \= 2\\alpha\_V \> \-1\$. Then:

1. The Liouville \$CC\$-sector Lyapunov contribution scales as \$I\_{CC}(t) \\sim C\_{\\alpha\_V} t^{-(4\\alpha\_V \+ 2)}\$.  
2. The time-integrated dissipation \$\\int\_0^\\infty I\_{CC}(t),dt\$ is finite if and only if \$\\alpha\_V \> \-\\frac{1}{4}\$.  
3. The cusp/Eisenstein continuum corresponds to \$\\alpha\_V \= \-\\frac{1}{2}\$, which lies below the integrability threshold \$-\\frac{1}{4}\$. In this case \$I\_{CC}(t)\$ approaches a positive constant and total dissipation diverges linearly.

Consequently, no bounded intertwiner \$\\Lambda^{-1}\$ on the rigged space \$\\Phi\_{\\mathcal L}\$ can produce a finite Lyapunov functional with exponential decay rate \$2\\gamma\$ on the cusp model uniformly across the continuum.

**The exact missing axiom:** Threshold subtraction (cusp regularization) must shift the effective threshold exponent from \$\\alpha\_V \= \-\\frac{1}{2}\$ into the integrable regime \$\\alpha\_V \> \-\\frac{1}{4}\$ before Prigogine's \$\\Lambda^{-1}\$ construction can be applied. Equivalently, the Eisenstein/continuous-spectrum contribution must be subtracted from the transfer operator before constructing the reference dissipative semigroup—not merely as a technical convenience, but as a structural necessity.

This obstruction is independent of the Riemann Hypothesis: RH enters in the location of discrete/resonant spectral data, whereas the \$CC\$-sector integrability obstruction is a threshold phenomenon at the cusp.

---

## 5\. Cusp–Resonance Dictionary (Corrected)

| Friedrichs / Liouville (Stages 1–3) | Mayer–Selberg / Cusp (Corrigendum / Stage 3\) | Exponent / Structural Role |
| :---- | :---- | :---- |
| Discrete state \$\|1\\rangle\$, energy \$\\omega\_1\$ | Residual spectrum at \$s \= 1\$ (constant function) | Isolated leading / equilibrium reference |
| Continuum \$\\omega \\in \[0,\\infty)\$, threshold \$\\omega \= 0\$ | Eisenstein continuum \$s \= 1/2 \+ it\$, threshold \$\\lambda \= 1/4\$ | Continuous spectrum |
| Resonance \$z\_0 \= \\tilde\\omega\_1 \- i\\gamma/2\$ | Pollicott–Ruelle resonance / scattering pole | Isolated complex spectral point |
| Form factor \$V(\\omega) \\sim v\_0 \\omega^{\\alpha\_V}\$ | Scattering phase / cusp behavior near threshold | \$\\alpha\_V \= \-1/2\$ for cusp |
| Single-particle tail \$\\mathcal O(t^{-3})\$ (\$\\alpha\_V \= 1/2\$) | — (single-particle, not Liouville) | Exponent \$2\\alpha\_V \+ 2\$ |
| Liouville \$CC\$ tail \$t^{-(4\\alpha\_V \+ 2)}\$ | — (Liouville product of two slots) | Exponent \$4\\alpha\_V \+ 2\$ |
| \$\\Lambda^{-1}\$ requires isolated resonance / anchor | \$\\Lambda^{-1}\$ requires isolated resonance / anchor | Fails at cusp |
| Integrability threshold \$\\alpha\_V \> \-1/4\$ | Cusp \$\\alpha\_V \= \-1/2 \< \-1/4\$ | Missing axiom: threshold subtraction |

### 5.6 Relation to Task 3B and Task 3C

Task 3B's "directly analogous" framing in §2.1 is consistent with the threshold no-go above, provided it includes a one-sentence clarification that the analogy stops at the bounded-\$\\Lambda^{-1}\$ level: even when rigged test spaces and spectral decompositions mirror one another structurally, a bounded intertwiner \$\\Lambda^{-1}\$ cannot uniformly convert the unsubtracted cusp/Eisenstein continuous spectrum into finite-dissipation exponential decay.

Likewise, Task 3C's §4 summary table is strengthened by adding a fourth row distinguishing **pointwise positivity vs. integrated dissipation**: a pointwise or instantaneous positivity/dissipativity condition along a line or at a given time does not guarantee finite integrated dissipation \$\\int\_0^\\infty I\_{CC}(t),dt \< \\infty\$, which requires crossing the threshold exponent \$\\alpha\_V \> \-1/4\$ (\$\\alpha\_L \> \-1/2\$).

---

## 6\. Structural Lessons

- **Liouville vs. single-particle scaling:** Because the Liouville pairing factorizes across two slots, the \$CC\$-sector tail exponent is \$4\\alpha\_V \+ 2\$, distinct from single-particle exponents.  
- **Integrability over asymptotic dominance:** Exponential decay outpaces any fixed power law at large \$t\$; the decisive physical criterion for total dissipation is integrability \$\\int\_0^\\infty I\_{CC}(t),dt \< \\infty\$, requiring \$\\alpha\_V \> \-1/4\$.  
- **Marginal non-decay at the cusp:** At \$\\alpha\_V \= \-1/2\$, \$I\_{CC}(t)\$ is asymptotically constant and total dissipation diverges linearly, making threshold/Eisenstein subtraction structurally necessary.  
- **RH independence:** The threshold integrability obstruction concerns cusp/continuous-spectrum behavior rather than the location of non-trivial zeros of \$\\zeta\$.

---

## 7\. Numerical Sanity Check (Recommended)

For a regulated form factor \$V(\\omega) \= v\_0 \\omega^{\\alpha\_V} e^{-\\kappa \\omega^2}\$:

- **\$\\alpha\_V \= 1/2\$ (integrable case):** \$I\_{CC}(t) \\sim C t^{-4}\$; a log–log plot of \$I\_{CC}\$ vs. \$t\$ yields asymptotic slope \$-4\$ and finite \$\\int\_0^\\infty I\_{CC}(t),dt\$.  
- **\$\\alpha\_V \= \-1/2\$ (cusp case):** \$I\_{CC}(t) \\sim C t^0\$; a log–log plot yields slope \$0\$, with \$I\_{CC}(t)\$ approaching a constant and \$\\int^T I\_{CC}(t),dt\$ growing linearly.  
- **Crossover \$t\_\*\$:** Comparing \$I\_{\\mathrm{res}}(t) \= A\_{\\mathrm{res}} e^{-2\\gamma t}\$ against \$I\_{CC}(t)\$ shows \$t\_\* \\approx \\frac{1}{2\\gamma}\\ln(A\_{\\mathrm{res}}/C)\$ in the regime where \$A\_{\\mathrm{res}}\$ dominates initially, while total dissipation remains finite only when \$\\alpha\_V \> \-1/4\$.

---

## 8\. Integration Notes and Handoff

### 8.1 New Task for §14.B (§14.B.8 — Threshold-Subtraction Axiom)

**§14.B.8 (Threshold-Subtraction Axiom):** Eisenstein / cusp subtraction shifts the effective threshold exponent from \$\\alpha\_V \= \-1/2\$ (\$\\alpha\_L \= \-1\$, non-decaying \$I\_{CC}(t) \\sim C\$ with linearly divergent integrated dissipation) into the finite-dissipation regime \$\\alpha\_V \> \-1/4\$ (\$\\alpha\_L \> \-1/2\$). This subtraction is required for a dynamical and thermodynamic reason—preserving finite total Lyapunov dissipation and well-posedness of the Liouvillian/intertwiner construction—and not merely as a technical or analytical convenience.

### 8.2 Supporting §13 Item 3 (Justification for Withdrawing the Contractive-Semigroup Claim)

This threshold no-go directly supports the corrigendum's withdrawal of the contractive-semigroup claim in §13 item 3\. Even if dissipativity and range/domain conditions were established in a regime with \$\\alpha\_V \> \-1/4\$, the unsubtracted cusp case \$\\alpha\_V \= \-1/2\$ fails to yield finite total dissipation (\$\\int\_0^\\infty I\_{CC}(t),dt \= \\infty\$), showing that withdrawing the contractive-semigroup claim is structurally necessary rather than merely cautious.