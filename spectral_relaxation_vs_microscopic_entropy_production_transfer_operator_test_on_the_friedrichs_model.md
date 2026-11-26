# Spectral Relaxation vs. Microscopic Entropy Production — Transfer-Operator Test on the Friedrichs Model

**Status:** Analytical comparison and transfer-operator testbed (Stages 1–3 $\to$ Ruelle / Tilted Transfer Bridge)  
**Builds on:**  
- `stage3_lambda_intertwiner_star_unitarity_lyapunov.md`  
- `friedrichs_concrete_form_factor_discharge.md`  
- `tough-millennium-problem-solved.md` (Section: *A common operator language*, *The importance of the spectral gap*, and *A particularly promising bridge*)  
**Purpose:** Construct a concrete transfer-operator / tilted-generator test on the Friedrichs model and compare (i) Prigogine's microscopic entropy production / Lyapunov dissipation rate $-\frac{d\Omega}{dt}$ from Stage 3 against (ii) spectral relaxation rates and entropy-tilted cumulant generating functions $\psi(q)$—identifying where they align, where they diverge, and what is required before any number-theoretic / zeta analogy.

---

## 1. Why test the bridge on the Friedrichs model first?

In the research program (`tough-millennium-problem-solved.md`), three dynamical/statistical quantities are placed side by side:
1. $h_{KS}$: dynamical information / trajectory-entropy rate;
2. $\sigma$ / $\psi(q)$: thermodynamic entropy production and its scaled cumulant-generating function (fluctuation / large-deviation structure);
3. $\kappa$: spectral relaxation rate (from transfer-operator spectral gaps or Liouville/resonance decay rates).

Testing these side by side on the Friedrichs model—where we have an exact resolvent, a single resonance pole $z_0 = \widetilde\omega_1 - i\gamma/2$, a rotated continuum $\Gamma_\theta = e^{-i\theta}\mathbb R^+$, and the exact Stage 3 transformed generator $\Phi_{\mathrm{Prig}} = \Phi_{\mathrm{even}} + i\Phi_{\mathrm{odd}}$—prevents loose analogy by exposing the exact mathematical mechanics of each quantity.

---

## 2. Two transfer-operator constructions on the Friedrichs / Liouville dynamics

Because the Friedrichs model has a discrete state $|1\rangle$ coupled to a continuous bath $L^2(\mathbb R^+, d\omega)$ rather than a finite-dimensional expanding hyperbolic map $T$, a "transfer operator" can be introduced in two distinct, complementary ways:

### 2.1 Construction A: Reduced / Stroboscopic Bath-Transfer Operator $\mathcal T_{\Delta t}$ on $\mathcal B_2(\mathcal H)$
Fix a stroboscopic time step $\Delta t > 0$ and define the forward Liouville transfer map over one step $\Delta t$:
\[
\mathcal T_{\Delta t}(\rho) := e^{-iL\Delta t}\rho = e^{-iH\Delta t}\rho\,e^{iH\Delta t},
\qquad \mathcal T_{\Delta t}^n(\rho) = e^{-iLt_n}\rho \quad (t_n = n\Delta t).
\tag{2.1}
\]
On the nuclear test space $\mathbf{\Phi}_{\mathcal L}$, intertwining $\mathcal T_{\Delta t}$ via $\Lambda^{-1}$ gives the stroboscopic reference transfer operator $\widehat{\mathcal T}_{\Delta t} := \Lambda^{-1} \mathcal T_{\Delta t} \Lambda = e^{-i\Phi_{\mathrm{Prig}}\Delta t}$ on $\widehat{\mathcal K}$:
\[
(\widehat{\mathcal T}_{\Delta t} \widehat{\rho})_{\alpha,\beta}
= e^{-i(\alpha - \beta^*)\Delta t} \, \widehat{\rho}_{\alpha,\beta},
\qquad \alpha, \beta \in \{z_0\} \cup \Gamma_\theta.
\tag{2.2}
\]

**Spectrum of $\widehat{\mathcal T}_{\Delta t}$:**
- **Isolated discrete eigenvalue from Sector $RR$:**
  \[
  \mu_{RR} = e^{-i(z_0 - z_0^*)\Delta t} = e^{-\gamma \Delta t} < 1 \qquad (\gamma > 0),
  \tag{2.3a}
  \]
  giving the discrete exponential relaxation rate per unit time:
  \[
  \kappa_{RR} = -\frac{1}{\Delta t}\ln |\mu_{RR}| = \gamma.
  \tag{2.3b}
  \]
- **Continuous spectrum extending up to the spectral radius $1$:**  
  From Sector $CC$ ($\alpha = x e^{-i\theta}$, $\beta = x' e^{-i\theta}$, $x, x' \ge 0$),
  \[
  \left| e^{-i(\zeta - \zeta^*)\Delta t} \right| = e^{-2(x + x')\sin\theta\,\Delta t}.
  \tag{2.4}
  \]
  As $x, x' \downarrow 0$, $\left|e^{-i(\zeta - \zeta^*)\Delta t}\right| \to 1$!
  **Crucial structural finding:** Because the continuum touches the origin ($x, x' \downarrow 0$), there is **no uniform spectral gap** separating the continuous spectrum of $\widehat{\mathcal T}_{\Delta t}$ from the unit circle $|\mu| = 1$ on the full space $\widehat{\mathcal K}$. Instead, $\mu_{RR} = e^{-\gamma\Delta t}$ is an *isolated eigenvalue* separated from the rotated continuum wedge $\{e^{-2(x+x')\sin\theta\,\Delta t} e^{-i(x-x')\cos\theta\,\Delta t}\}$ only by a non-uniform / threshold-touching continuum.

### 2.2 Construction B: Entropy-Production Tilted Generator $\mathcal L_q$ on the Liouville / Bath Observable
In nonequilibrium statistical mechanics, tilting a generator by a parameter $q$ weights trajectories according to an accumulated observable $\Sigma_t$. On the Friedrichs model, a natural entropy-production observable for the discrete-to-bath energy/entropy exchange is the net bath-excitation / decay counter or the Stage 3 Lyapunov dissipation rate:
\[
\sigma_{\mathrm{MEP}}(t) := -\frac{d\Omega(t)}{dt} = 2\langle\langle \widehat{\rho}(t) | \Phi_{\mathrm{odd}} \widehat{\rho}(t) \rangle\rangle_{\widehat{\mathcal K}} \ge 0.
\tag{2.5}
\]

Tilting the reference generator $-i\Phi_{\mathrm{Prig}}$ in the $RR$ / dissipative sector by a tilt parameter $q \in \mathbb R$ defines a family of tilted generators:
\[
\mathcal G_q := -i\Phi_{\mathrm{Prig}} - q\,\mathcal D_{\mathrm{MEP}},
\tag{2.6}
\]
where $\mathcal D_{\mathrm{MEP}}$ acts diagonally by the sector dissipation rate $\Gamma_{\alpha,\beta} := -2\operatorname{Im}\Lambda_{\alpha,\beta} \ge 0$:
- Sector $RR$: $\Gamma_{z_0,z_0} = 2\gamma$;
- Sector $RC$: $\Gamma_{z_0,\zeta'} = \gamma + 2x'\sin\theta$;
- Sector $CR$: $\Gamma_{\zeta,z_0} = 2x\sin\theta + \gamma$;
- Sector $CC$: $\Gamma_{\zeta,\zeta'} = 2(x + x')\sin\theta$.

For the pure-resonance $RR$ component (which dominates at intermediate times before the $O(t^{-3})$ continuum tail takes over), the cumulant-generating rate of the accumulated dissipation $\Sigma_t^{RR} = \int_0^t 2\gamma\,d\tau = 2\gamma t$ is linear in $q$:
\[
\psi_{RR}(q) = \lim_{t\to\infty} \frac{1}{t}\ln \left\langle e^{-q\Sigma_t^{RR}} \right\rangle = -2\gamma q,
\qquad
-\psi_{RR}'(0) = 2\gamma,
\qquad
\psi_{RR}''(0) = 0.
\tag{2.7}
\]
The vanishing second cumulant ($\psi_{RR}''(0) = 0$) reflects the fact that at the level of the deterministic/spectral decay rate $2\gamma$ of a single resonance pole, there is no stochastic fluctuation variance—whereas in a genuine multi-trajectory or open-quantum stochastic jump process (or chaotic map), $\psi''(0) > 0$ captures trajectory-level fluctuations.

---

## 3. Direct comparison: Spectral relaxation ($\kappa$) vs. Microscopic Entropy Production ($\sigma_{\mathrm{MEP}}$)

| Dimension | Spectral relaxation ($\kappa$, Ruelle / transfer gap) | Microscopic Entropy Production ($\sigma_{\mathrm{MEP}} = -\frac{d\Omega}{dt}$, Prigogine / Stage 3) |
|---|---|---|
| **Primary object** | Eigenvalues / spectral radius ratio $-\ln|\lambda_1/\lambda_0|$ of a transfer or evolution operator | Time derivative of the positive quadratic Lyapunov functional $\Omega(t) = \|\Lambda^{-1}\rho(t)\|_{\widehat{\mathcal K}}^2$ |
| **Sign & monotonicity** | Controlled by spectral gap / subleading decay rates; may lack a uniform gap when continuum hits $0$ | Strictly monotonic dissipation: $\frac{d\Omega}{dt} = -2\langle\langle\widehat{\rho}|\Phi_{\mathrm{odd}}\widehat{\rho}\rangle\rangle_{\widehat{\mathcal K}} \le 0$ for all $t \ge 0$ |
| **Timescale / rate on Friedrichs model** | Resonance pole gives $\gamma$ (amplitude decay rate $\gamma/2$, population decay rate $\gamma$); continuum has no gap at $x,x'\to 0$, giving $O(t^{-3})$ power-law tail | Instantaneous dissipation rate sums weighted contributions across all four sectors ($2\gamma$, $\gamma + 2x'\sin\theta$, $2x\sin\theta + \gamma$, $2(x+x')\sin\theta$) |
| **Information / entropy meaning** | Measures correlation decay and trajectory proliferation ($h_{KS}$ in chaotic maps) | Measures irreversible relaxation of the transformed state's norm in the non-unitary representation $\Lambda^{-1}$ |

### Key diagnostic conclusion from the Friedrichs test
1. **They are complementary, not identical:** On the Friedrichs model, the resonance decay rate $\gamma$ sets the exponential scale of both the isolated $RR$ transfer eigenvalue $e^{-\gamma\Delta t}$ and the leading exponential term $e^{-2\gamma t}$ in $\Omega(t)$. However, $\Omega(t)$ is a **quadratic functional of the state** (so its exponential rate is $2\gamma$ in the $RR$ sector and carries sector-dependent weights across $RC, CR, CC$), whereas transfer-operator relaxation rates $\kappa$ govern **linear observables / correlation decay** and encounter a gapless threshold at $x, x' \downarrow 0$ producing algebraic $O(t^{-3})$ relaxation rather than pure exponential decay.
2. **Where a true Ruelle / fluctuation bridge requires more structure:** Because the Friedrichs model has a single discrete level coupled to a free continuum rather than a hyperbolic expanding map with a Markov partition or stochastic jump generator, $h_{KS}$ (as trajectory entropy of an expanding map) is not natively non-zero in the one-particle Friedrichs model itself. To test non-trivial trajectory fluctuations ($\psi''(0) > 0$) and Kolmogorov–Sinai entropy alongside Prigogine's $\Lambda^{-1}$ formalism, one must either move to **Stage 2 of the broader program** (a chaotic dynamical system / hard-point gas or expanding map) or couple the Friedrichs system to a multi-mode / stochastic bath.

---

## 4. Disciplined boundary before returning to zeta functions

This Friedrichs test confirms both the strength and the exact limits of the operator bridge:
- **What works cleanly:** Lifting a reversible microscopic generator $L = [H, \cdot]$ via a non-unitary intertwiner $\Lambda^{-1}$ on a rigged space onto a dissipative spectral representation where $\Phi_{\mathrm{Prig}} = \Phi_{\mathrm{even}} + i\Phi_{\mathrm{odd}}$ and $\frac{d\Omega}{dt} \le 0$.
- **What must not be overclaimed:** Equating a spectral decay rate $\kappa$ with thermodynamic entropy production $\sigma$, or treating a transfer-operator / Fredholm-determinant correspondence (as in the Mayer–Selberg–Riemann corrigendum) as a proof of physical irreversibility or of RH. Any return to zeta functions or RH remains a structural/spectral investigation rather than a thermodynamic derivation.