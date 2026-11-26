# Deliverable 2B — Non-Unitary Intertwiner $\Lambda^{-1}$, Lyapunov Functional, and Comparison with Tilted Cumulants

**Status:** Core Stage 2 synthesis and comparison note  
**Builds on:**  
- `broader_program_stage2_deliverable2a_ruelle_tilted.md`  
- `stage3_lambda_intertwiner_star_unitarity_lyapunov.md`  
- `corrigendum_friedrichs_zeta_revised.md`  
**Purpose:** Construct the rigged-space non-unitary intertwiner $\Lambda^{-1}$, reference dissipative evolution $\widehat{W}_n = \Lambda^{-1}\mathcal P^n\Lambda$, and monotonic Lyapunov functional $\Omega_n$ for the asymmetric expanding map $T$ of Deliverable 2A, and perform an exact comparison between Prigogine's Lyapunov dissipation $-\Delta\Omega_n$ and the Ruelle spectral/fluctuation quantities $\kappa$, $h_{KS}$, and $\psi(q)$.

---

## 1. Reversible Koopman dynamics vs. irreversible Perron–Frobenius representation

On the Hilbert space $\mathcal H = L^2([0, 1), dx)$, the Koopman operator
\[
(U_T g)(x) := g(T(x))
\tag{1.1}
\]
is an **isometry** ($\|U_T g\|_{L^2} = \|g\|_{L^2}$, preserving the $L^2$ norm of every observable without decay) whose spectrum lies on the unit circle $\{z \in \mathbb C : |z| = 1\}$ (unitary on the natural extension / baker-type invertible lift $\widetilde{T}$ on $[0,1)^2$).

Its $L^2$-adjoint is the Perron–Frobenius operator $\mathcal P = U_T^\dagger$:
\[
\langle \mathcal P \rho, g \rangle_{L^2} = \langle \rho, U_T g \rangle_{L^2},
\qquad
(\mathcal P \rho)(x) = p\,\rho(px) + (1 - p)\,\rho\big(p + (1 - p)x\big).
\tag{1.2}
\]

### 1.1 Why a non-unitary rigged-space transformation $\Lambda^{-1}$ is needed
On $L^2([0, 1), dx)$, $\mathcal P$ has essential spectrum filling the unit disk $\{|z| \le 1\}$ and cannot be diagonalized into discrete decaying modes. Just as in Stage 1–3 for the Friedrichs model, restricting densities $\rho$ to a **nuclear analytic test space** $\Phi_{\mathrm{an}}$ (such as entire functions of exponential type or analytic functions on a disk $D_R$ of radius $R > 1$, forming a Gelfand triple $\Phi_{\mathrm{an}} \hookrightarrow L^2([0,1)) \hookrightarrow \Phi_{\mathrm{an}}^\times$) exposes the discrete Pollicott–Ruelle eigenvalues $\lambda_k = p^{k+1} + (1 - p)^{k+1}$ ($k = 0, 1, 2, \dots$) derived in Deliverable 2A Eq. (2.2b).

---

## 2. Construction of the biorthogonal Pollicott–Ruelle basis and $\Lambda^{-1}$

### 2.1 Right eigenfunctions and left generalized eigenfunctionals
From Deliverable 2A §2.1, on $\Phi_{\mathrm{an}}$:
- **Right eigenfunctions $|\psi_k^R\rangle \in \Phi_{\mathrm{an}}$:**  
  For $k = 0$, $\psi_0^R(x) = 1$ with eigenvalue $\lambda_0 = 1$.  
  For $k \ge 1$, $\psi_k^R(x)$ is the unique monic Bernoulli-type polynomial of degree $k$ satisfying $\mathcal P \psi_k^R = \lambda_k \psi_k^R$ (e.g., $\psi_1^R(x) = x - \frac{1}{2}$, $\psi_2^R(x) = x^2 - x + \frac{1 - 2p(1-p)}{6[1 - p^3 - (1-p)^3]}$).
- **Left generalized eigenfunctionals $\langle \psi_k^L | \in \Phi_{\mathrm{an}}^\times$:**  
  Because $\mathcal P^\dagger = U_T$ satisfies $\langle \psi_k^L | \mathcal P \rho \rangle = \lambda_k \langle \psi_k^L | \rho \rangle$, testing on Taylor / derivative functionals at $x = 0$ or contour integrals around $[0,1]$ yields the dual polynomials / distributional derivatives $\langle \psi_k^L | \rho \rangle$ satisfying exact biorthogonality:
  \[
  \langle \psi_j^L | \psi_k^R \rangle = \delta_{jk}, \qquad j, k \in \{0, 1, 2, \dots\},
  \tag{2.1}
  \]
  with $\langle \psi_0^L | \rho \rangle = \int_0^1 \rho(x)\,dx = \operatorname{Tr}(\rho)$.

On $\Phi_{\mathrm{an}}$, every analytic density $\rho$ admits the convergent spectral expansion:
\[
\rho(x) = \langle \psi_0^L | \rho \rangle \, \mathbf{1}(x) + \sum_{k=1}^{\infty} \langle \psi_k^L | \rho \rangle \, \psi_k^R(x),
\tag{2.2}
\]
and after $n \ge 0$ iterations of the dynamics:
\[
(\mathcal P^n \rho)(x) = \langle \psi_0^L | \rho \rangle \, \mathbf{1}(x) + \sum_{k=1}^{\infty} \lambda_k^n \, \langle \psi_k^L | \rho \rangle \, \psi_k^R(x).
\tag{2.3}
\]

### 2.2 Non-unitary intertwiner $\Lambda^{-1}$ onto the reference Hilbert space $\widehat{\mathcal K}$
Separate the invariant equilibrium subspace ($k = 0$, $\lambda_0 = 1$) from the decaying non-equilibrium subspace ($k \ge 1$, $0 < \lambda_k < 1$). Define the reference spectral Hilbert space
\[
\widehat{\mathcal K} := \mathbb C \widehat{e}_0 \oplus \ell^2(\mathbb N),
\tag{2.4}
\]
and define the non-unitary coordinate intertwiner $\Lambda^{-1} : \Phi_{\mathrm{an}} \to \widehat{\mathcal K}$ (with suitable growth weights $w_k > 0$ on $\ell^2(\mathbb N)$ matched to the analytic radius $R$ of $\Phi_{\mathrm{an}}$) by
\[
(\Lambda^{-1} \rho)_k := w_k \, \langle \psi_k^L | \rho \rangle,
\qquad k = 0, 1, 2, \dots \quad (w_0 = 1).
\tag{2.5}
\]

On $\widehat{\mathcal K}$, the intertwined one-step evolution operator $\widehat{W} := \Lambda^{-1} \mathcal P \Lambda$ acts as a **normal contraction**:
\[
(\widehat{W} \widehat{\rho})_0 = \widehat{\rho}_0,
\qquad
(\widehat{W} \widehat{\rho})_k = \lambda_k \, \widehat{\rho}_k \quad (k \ge 1),
\tag{2.6}
\]
with discrete-time generator $\Phi_{\mathrm{Prig}} := i\ln \widehat{W}$ acting diagonally by $i\ln \lambda_k$:
- for $k = 0$: $i\ln \lambda_0 = 0$ (invariant equilibrium);
- for $k \ge 1$: $i\ln \lambda_k = -i\kappa_k$ where $\kappa_k := -\ln\big[p^{k+1} + (1 - p)^{k+1}\big] > 0$, strictly in the negative imaginary half-axis!

---

## 3. Microscopic Lyapunov functional $\Omega_n$ and exact dissipation rate

Define the Prigogine Lyapunov functional on non-equilibrium deviations $\delta\rho_n := \rho_n - \langle \psi_0^L | \rho_0 \rangle \mathbf{1}$ (with $\rho_n = \mathcal P^n \rho_0$):
\[
\Omega_n := \left\| \Lambda^{-1} \delta\rho_n \right\|_{\widehat{\mathcal K}}^2
= \sum_{k=1}^{\infty} w_k^2 \left| \langle \psi_k^L | \rho_n \rangle \right|^2
= \sum_{k=1}^{\infty} \lambda_k^{2n} \, w_k^2 \left| \langle \psi_k^L | \rho_0 \rangle \right|^2.
\tag{3.1}
\]

### 3.1 Strict monotonicity and asymptotic decay rate
Because $0 < \lambda_k \le \lambda_1 < 1$ for every $k \ge 1$, the one-step Lyapunov dissipation is strictly positive for every non-equilibrium analytic state $\rho_0 \neq \mathbf{1}$:
\[
-\Delta \Omega_n := \Omega_n - \Omega_{n+1}
= \sum_{k=1}^{\infty} \left(1 - \lambda_k^2\right) \lambda_k^{2n} \, w_k^2 \left| \langle \psi_k^L | \rho_0 \rangle \right|^2 > 0,
\tag{3.2}
\]
and $\lim_{n \to \infty} \Omega_n = 0$ exponentially fast!

Specifically, for a generic analytic density with $\langle \psi_1^L | \rho_0 \rangle \neq 0$, the asymptotic exponential decay rate of the Lyapunov functional $\Omega_n$ is
\[
\lim_{n \to \infty} -\frac{1}{n}\ln \Omega_n = -2\ln \lambda_1 = 2\kappa,
\tag{3.3}
\]
where $\kappa = -\ln[p^2 + (1 - p)^2]$ is the Ruelle spectral relaxation rate from Deliverable 2A Eq. (2.3).

---

## 4. Complete comparison across Friedrichs (Stage 1) and Chaotic Map (Stage 2)

| Quantity / Property | Friedrichs Model (Stage 1 / Stage 3) | Asymmetric Expanding Map $T$ (Stage 2) |
|---|---|---|
| **Reversible vs. Dissipative Split** | Self-adjoint $H$, unitary $e^{-iHt}$ on $\mathcal H$; $\Lambda^{-1}$ on $\mathbf{\Phi}_{\mathcal L}$ gives $\Phi_{\mathrm{Prig}} = \Phi_{\mathrm{even}} + i\Phi_{\mathrm{odd}}$ | Isometric Koopman $U_T$ on $L^2([0,1))$; $\Lambda^{-1}$ on $\Phi_{\mathrm{an}}$ gives $\widehat{W} = \Lambda^{-1}\mathcal P\Lambda$ with $\operatorname{Im}(i\ln\lambda_k) \le 0$ |
| **Spectral Gap & Long-Time Tail** | Isolated resonance $z_0 = \widetilde\omega_1 - i\gamma/2$ plus gapless continuum touching $0 \implies$ $O(t^{-3})$ power-law tail | Genuine spectral gap $\kappa = -\ln[p^2+(1-p)^2] > 0$ on analytic functions $\implies$ pure exponential relaxation $e^{-\kappa n}$ |
| **Lyapunov Functional $\Omega$ Rate** | $-\frac{d\Omega}{dt} \ge 0$; leading $RR$ decay rate is $2\gamma$ (twice the amplitude rate $\gamma$), with continuum tail | $-\Delta\Omega_n > 0$; asymptotic exponential decay rate is $2\kappa$ (twice the linear correlation rate $\kappa$) |
| **Dynamical Entropy $h_{KS}$** | $h_{KS} = 0$ (no hyperbolic trajectory proliferation in 1-particle Friedrichs) | $h_{KS} = -p\ln p - (1-p)\ln(1-p) > 0$, strictly distinct from $\kappa$ when $p \neq 1/2$ |
| **Entropy-Tilted Cumulants $\psi(q)$** | $\psi_{RR}(q) = -2\gamma q$, variance $\psi_{RR}''(0) = 0$ (no stochastic trajectory fluctuations) | $\psi(q) = \ln[p^{1+q}+(1-p)^{1+q}]$, $-\psi'(0) = h_{KS}$, variance $\psi''(0) = p(1-p)[\ln\frac{p}{1-p}]^2 > 0$ |

---

## 5. Key structural lessons from Stage 2 (before Deliverable 2C / Zeta synthesis)

1. **Universal factor-of-2 relation between linear spectral relaxation and quadratic Lyapunov decay:**  
   In *both* the Friedrichs model (Stage 3) and the chaotic expanding map (Stage 2), because Prigogine's Lyapunov functional $\Omega = \|\Lambda^{-1}\delta\rho\|_{\widehat{\mathcal K}}^2$ is a **positive quadratic form** on the transformed state while the transfer/evolution operator acts **linearly** on observables/states, the leading exponential decay rate of $\Omega$ is **twice** the leading linear spectral relaxation rate ($2\gamma$ vs. $\gamma$ in Friedrichs; $2\kappa$ vs. $\kappa$ in the expanding map).
2. **Exact separation of three distinct physical quantities:**  
   Deliverable 2A and 2B prove by explicit closed-form formulas that:
   - $\kappa = -\ln[p^2 + (1-p)^2]$ governs **linear correlation / state relaxation** (and $2\kappa$ governs $\Omega_n$);
   - $h_{KS} = -p\ln p - (1-p)\ln(1-p)$ governs **mean dynamical information / trajectory entropy production** ($-\psi'(0)$);
   - $\psi''(0) = p(1-p)[\ln\frac{p}{1-p}]^2$ governs **trajectory-level fluctuation variance** (which is invisible to the quadratic norm $\Omega_n$ alone, requiring the tilted operator $\mathcal L_q$).
3. **Why hyperbolic chaos is essential for the zeta bridge:**  
   Only when hyperbolic trajectory proliferation is present (as in Deliverable 2A's expanding map, or the Gauss/geodesic flow map on $\mathrm{PSL}(2,\mathbb Z)\backslash\mathbb H$ in Mayer's transfer-operator theory) do we simultaneously get a discrete Pollicott–Ruelle resonance spectrum on analytic spaces, non-zero topological/KS entropy, and a non-trivial Fredholm determinant $\det(I - \mathcal L_s)$.

We are now ready for **Deliverable 2C** (the synthesis consolidating Stages 1 and 2 and examining how the Mayer–Selberg–Riemann spectral setup in `corrigendum_friedrichs_zeta_revised.md` connects to this unified operator picture).