# Deliverable 2A — Ruelle Transfer Operator, Spectral Gap, and Tilted Cumulants on an Asymmetric Expanding Map

**Status:** Exact benchmark calculation for Stage 2 of the broader research program  
**Builds on:** `broader_program_stage2_chaotic_dynamical_testbed.md` and `spectral_relaxation_vs_mep_friedrichs.md`  
**Purpose:** Compute in closed form the Perron–Frobenius spectrum, spectral relaxation rate $\kappa$, Kolmogorov–Sinai entropy $h_{KS}$, entropy-production tilted transfer operator $\mathcal L_q$, scaled cumulant-generating function $\psi(q)$, and fluctuation variance $\psi''(0) > 0$ on a concrete chaotic expanding map.

---

## 1. The benchmark chaotic system: Asymmetric two-branch expanding circle map

Fix an asymmetry parameter $p \in (0, 1)$ with $p \neq \frac{1}{2}$, and partition the unit circle $S^1 = [0, 1) / \sim$ into two intervals:
\[
I_0 = [0, p), \qquad I_1 = [p, 1).
\tag{1.1}
\]
Define the piecewise-linear expanding map $T : S^1 \to S^1$ by
\[
T(x) = \begin{cases}
\dfrac{x}{p}, & x \in I_0 = [0, p), \\[8pt]
\dfrac{x - p}{1 - p}, & x \in I_1 = [p, 1).
\end{cases}
\tag{1.2}
\]

### 1.1 Fundamental dynamical invariants
1. **Uniform expansion and Markov partition:** Both branches map $I_0$ and $I_1$ bijectively onto $[0, 1)$ with constant expansion rates
   \[
   |T'(x)| = \begin{cases}
   p^{-1} > 1, & x \in I_0, \\
   (1 - p)^{-1} > 1, & x \in I_1.
   \end{cases}
   \tag{1.3}
   \]
   The partition $\mathcal P = \{I_0, I_1\}$ is a generating Bernoulli / Markov partition: symbolic itineraries $(s_0, s_1, \dots) \in \{0, 1\}^{\mathbb N_0}$ with $s_k = \mathbf{1}_{I_1}(T^k x)$ are independent and identically distributed under Lebesgue measure $dx$ with weights $(p, 1 - p)$.
2. **Invariant SRB / Lebesgue measure and Kolmogorov–Sinai entropy ($h_{KS}$):**  
   Lebesgue measure $\mu = dx$ is the unique absolutely continuous invariant probability measure (SRB measure). By Pesin's formula,
   \[
   h_{KS}(T, \mu)
   = \int_0^1 \ln |T'(x)| \, dx
   = -p \ln p - (1 - p) \ln(1 - p) > 0,
   \tag{1.4}
   \]
   while the topological entropy is $h_{\mathrm{top}}(T) = \ln 2$.

---

## 2. Perron–Frobenius operator $\mathcal P$ and spectral relaxation rate $\kappa$

For any observable or density $f \in L^1([0, 1))$, the Perron–Frobenius operator $(\mathcal P f)(x) = \sum_{Ty = x} \frac{f(y)}{|T'(y)|}$ acts explicitly as
\[
(\mathcal P f)(x) = p \, f(px) + (1 - p) \, f\big(p + (1 - p)x\big).
\tag{2.1}
\]

### 2.1 Exact eigenvalues and eigenfunctions on polynomials / analytic functions
Restrict $\mathcal P$ to the Banach space of real-analytic functions $\mathcal A_\rho$ on a complex neighborhood of $[0, 1]$ (or the space of polynomials $\mathbb R[x]$). Because $\mathcal P$ maps polynomials of degree $k$ to polynomials of degree $k$:
- **Degree $k = 0$:** $\mathcal P(1) = p \cdot 1 + (1 - p) \cdot 1 = 1$, so the leading eigenvalue is
  \[
  \lambda_0 = 1, \qquad h_0(x) = 1.
  \tag{2.2a}
  \]
- **Degree $k \ge 1$:** Applying $\mathcal P$ to $x^k$ gives
  \[
  \mathcal P(x^k)
  = p (px)^k + (1 - p)\big(p + (1 - p)x\big)^k
  = \big[ p^{k+1} + (1 - p)^{k+1} \big] x^k + (\text{lower-degree terms}).
  \]
  Thus $\mathcal P$ is upper-triangular in the monomial basis $\{1, x, x^2, \dots\}$ with exact discrete eigenvalues (Pollicott–Ruelle resonances on $\mathcal A_\rho$):
  \[
  \lambda_k = p^{k+1} + (1 - p)^{k+1}, \qquad k = 0, 1, 2, \dots
  \tag{2.2b}
  \]
  In particular, the subleading eigenvalue ($k = 1$) is
  \[
  \lambda_1 = p^2 + (1 - p)^2 = 1 - 2p(1 - p) \in \left[\frac{1}{2}, 1\right),
  \tag{2.2c}
  \]
  with right eigenfunction $h_1(x) = x - \frac{1}{2}$ (indeed, $\mathcal P(x - \frac{1}{2}) = [p^2 + (1 - p)^2](x - \frac{1}{2})$).

### 2.2 Spectral relaxation rate $\kappa$ vs. $h_{KS}$
On $\mathcal A_\rho$, $\mathcal P$ has a genuine spectral gap separating $\lambda_0 = 1$ from the rest of the spectrum:
\[
\kappa = -\ln \left| \frac{\lambda_1}{\lambda_0} \right| = -\ln \big[ p^2 + (1 - p)^2 \big] > 0.
\tag{2.3}
\]
Comparing (1.4) and (2.3) immediately settles Question 1 / Question 2 for this model:
- Both $h_{KS}$ and $\kappa$ are strictly positive and maximize at the symmetric point $p = \frac{1}{2}$ (where $h_{KS} = \ln 2$ and $\kappa = \ln 2$).
- Away from $p = \frac{1}{2}$, they are distinct functions of $p$: e.g., as $p \downarrow 0$, $h_{KS} \sim -p\ln p$ whereas $\kappa \sim 2p$. Thus $\kappa$ (Rényi-2 / $L^2$ correlation decay rate) and $h_{KS}$ (Shannon / Rényi-1 trajectory information rate) are structurally related but algebraically distinct.

---

## 3. Local entropy production $\sigma(x)$ and the tilted transfer operator $\mathcal L_q$

To equip the map with a non-trivial physical/thermodynamic entropy production observable along trajectories, introduce the **local Jacobian / information-production observable** (or driven branch-asymmetry current):
\[
\sigma(x) := \ln |T'(x)| - h_{KS}
= \begin{cases}
-\ln p - h_{KS}, & x \in I_0, \\
-\ln(1 - p) - h_{KS}, & x \in I_1,
\end{cases}
\tag{3.1}
\]
or, to keep raw positivity with mean $h_{KS}$, consider the uncentered local expansion rate $\widetilde\sigma(x) = \ln|T'(x)| > 0$ (whose mean is $h_{KS}$), and also a driven current observable $j(x) = +J_0$ on $I_0$ and $-J_1$ on $I_1$. We compute the exact tilted spectrum for $\widetilde\sigma(x) = \ln|T'(x)|$ (which ties trajectory expansion directly to Rényi entropies and multifractal thermodynamics).

### 3.1 Exact spectrum of the tilted Ruelle operator $\mathcal L_q$
Define the tilted Perron–Frobenius / Ruelle transfer operator for $q \in \mathbb R$:
\[
(\mathcal L_q f)(x)
:= \sum_{y \in T^{-1}(x)} \frac{e^{-q \widetilde\sigma(y)}}{|T'(y)|} f(y)
= \sum_{y \in T^{-1}(x)} |T'(y)|^{-(1 + q)} f(y).
\tag{3.2}
\]
Explicitly, on the two branches of (1.2):
\[
(\mathcal L_q f)(x)
= p^{1 + q} f(px) + (1 - p)^{1 + q} f\big(p + (1 - p)x\big).
\tag{3.3}
\]

Acting on polynomials / analytic functions $\mathcal A_\rho$, $\mathcal L_q$ is again upper-triangular in $\{1, x, x^2, \dots\}$ with exact eigenvalues:
\[
\lambda_k(q) = p^{k + 1 + q} + (1 - p)^{k + 1 + q},
\qquad k = 0, 1, 2, \dots
\tag{3.4}
\]
In particular, the leading eigenvalue ($k = 0$, eigenfunction $h_0(x) = 1$) is
\[
\lambda_0(q) = p^{1 + q} + (1 - p)^{1 + q} > 0,
\tag{3.5a}
\]
and the subleading eigenvalue ($k = 1$, eigenfunction $h_1(x) = x - \frac{p^{1+q}(1-p) + (1-p)^{1+q}(1+p)}{2\lambda_0(q)}$) satisfies
\[
\frac{\lambda_1(q)}{\lambda_0(q)} = \frac{p^{2+q} + (1-p)^{2+q}}{p^{1+q} + (1-p)^{1+q}} < 1,
\tag{3.5b}
\]
giving a strictly positive tilted spectral gap $\kappa(q) = -\ln[\lambda_1(q)/\lambda_0(q)] > 0$ for every $q \in \mathbb R$.

---

## 4. Scaled cumulant-generating function $\psi(q)$ and fluctuation cumulants

For $\Sigma_n[x] = \sum_{k=0}^{n-1} \ln|T'(T^k x)|$, the scaled cumulant-generating function is given directly by the leading tilted eigenvalue (3.5a):
\[
\psi(q)
= \lim_{n \to \infty} \frac{1}{n} \ln \int_0^1 e^{-q \Sigma_n[x]} \, dx
= \ln \lambda_0(q)
= \ln \Big[ p^{1+q} + (1 - p)^{1+q} \Big].
\tag{4.1}
\]

Differentiating $\psi(q)$ at $q = 0$ yields the exact statistical cumulants:

1. **First cumulant (mean production rate = $h_{KS}$):**
   \[
   -\psi'(0)
   = -\left. \frac{p^{1+q}\ln p + (1 - p)^{1+q}\ln(1 - p)}{p^{1+q} + (1 - p)^{1+q}} \right|_{q=0}
   = -p \ln p - (1 - p) \ln(1 - p)
   = h_{KS} > 0.
   \tag{4.2}
   \]

2. **Second cumulant (asymptotic trajectory fluctuation variance):**
   \[
   \psi''(0)
   = \operatorname{Var}_\mu(\ln|T'|)
   = p(1 - p) \left[ \ln\!\left(\frac{p}{1 - p}\right) \right]^2 > 0
   \qquad \left(p \neq \frac{1}{2}\right).
   \tag{4.3}
   \]

3. **Gallavotti–Cohen / fluctuation symmetry on the centered current $\sigma(x) = \ln|T'(x)| - h_{KS}$:**  
   For the centered observable $\Sigma_n^{(0)}[x] = \Sigma_n[x] - n h_{KS}$, the cumulant-generating function is $\psi_0(q) = \psi(q) + q h_{KS}$, which is strictly convex ($\psi_0''(q) > 0$ for $p \neq 1/2$) and satisfies $\psi_0(0) = 0$, $\psi_0'(0) = 0$, governing large deviations of trajectory entropy production via Legendre transform $I(s) = \sup_q [-qs - \psi_0(q)]$.

---

## 5. Summary of Deliverable 2A findings for Deliverable 2B

Unlike the single-resonance Friedrichs sector (where $\psi_{RR}''(0) = 0$ and the continuum touches the threshold without a spectral gap), the asymmetric expanding map exhibits simultaneously:
- Strictly positive Kolmogorov–Sinai entropy $h_{KS} = -p\ln p - (1-p)\ln(1-p) > 0$;
- A discrete Pollicott–Ruelle spectrum $\lambda_k = p^{k+1} + (1-p)^{k+1}$ on analytic observables with spectral relaxation rate $\kappa = -\ln[p^2 + (1-p)^2] > 0$;
- Non-trivial trajectory fluctuations $\psi''(0) = p(1-p)[\ln(p/(1-p))]^2 > 0$ when $p \neq 1/2$.

In **Deliverable 2B**, we construct the rigged-space non-unitary intertwiner $\Lambda^{-1}$ and Prigogine Lyapunov functional $\Omega_n$ on this exact same map $T$ and compare them directly against $\kappa$, $h_{KS}$, and $\psi(q)$.