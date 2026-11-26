# Concrete Form-Factor Verification — Spectral Purity, Dominated Convergence, and $L^2$ Contour Bounds

**Status:** Explicit model-level proof discharge for Stages 1, 1.5, 2, and 3  
**Builds on:**  
- `friedrichs_stage1_single_particle_foundation.md` (revision 2)  
- `friedrichs_stage1_5_concrete_instantiation.md`  
- `stage2_liouville_lift_specification.md`  
- `stage3_lambda_intertwiner_star_unitarity_lyapunov.md`  
**Purpose:** Discharge the three remaining model-level proof obligations listed at the end of Stage 3 on an explicit, analytically tractable form factor $V(\omega)$, proving spectral purity (no bound states or embedded eigenvalues), large-arc/dominated-convergence bounds for contour deformation and completeness, and $L^2(\Gamma_\theta)$ / $L^2(\Gamma_\theta^*)$ integrability of $\Lambda^{-1}(\mathbf{\Phi}_{\mathcal L})$.

---

## 1. Benchmark model: Fractional-power Gaussian/exponential cutoff form factor

Choose a discrete mode energy $\omega_1 > 0$, deformation angle parameters $0 < \theta < \theta_0 < \pi/2$, sector opening $\delta \in (\theta_0, \pi/2)$, and consider the form factor
\[
V(z) = v_0 \, z^\alpha \, e^{-\kappa z^2},
\qquad v_0 > 0, \quad \alpha > 0, \quad \kappa > 0,
\tag{1.1}
\]
evaluated along the principal branch of $z^\alpha$ on the cut plane $\mathbb C \setminus (-\infty, 0]$, which contains the closed sector $\overline{\mathcal S_\delta} = \{z \in \mathbb C : |\arg z| \le \delta\}$ (with $V(0) = 0$).

### 1.1 Verification of Stage 1.5 admissibility assumptions
1. **Holomorphy and reflection symmetry:** On $\mathcal S_\delta$, $z^\alpha$ and $e^{-\kappa z^2}$ are holomorphic, and $V$ extends continuously to $\overline{\mathcal S_\delta}$. For $z \in \mathcal S_\delta$,
   \[
   V^*(z) := \overline{V(\bar z)} = v_0 \, z^\alpha \, e^{-\kappa z^2} = V(z),
   \]
   and on $\mathbb R^+$, $J(\omega) = V(\omega)V^*(\omega) = v_0^2 \omega^{2\alpha} e^{-2\kappa\omega^2}$.
2. **Threshold behavior:** For $z \in \overline{\mathcal S_\delta}$ with $|z| \le 1$, $|e^{-\kappa z^2}| \le e^{\kappa \cos(2\delta)} \le e^\kappa$, so
   \[
   |V(z)| \le v_0 e^\kappa |z|^\alpha,
   \qquad J(z) = O(|z|^{2\alpha}) \quad (|z| \to 0).
   \]
3. **High-energy decay in $\overline{\mathcal S_\delta}$:** For $z = r e^{i\varphi} \in \overline{\mathcal S_\delta}$ ($|\varphi| \le \delta < \pi/2$),
   \[
   \operatorname{Re}(z^2) = r^2 \cos(2\varphi) \ge r^2 \cos(2\delta) > 0,
   \]
   so $|e^{-\kappa z^2}| \le e^{-\kappa \cos(2\delta) r^2}$. Thus $V$ decays super-exponentially in every direction of $\overline{\mathcal S_\delta}$ and belongs to $\Phi_{\mathrm{cont}}$ (as well as $L^2(\mathbb R^+)$).

---

## 2. Obligation 1: Spectral purity (no bound states, no embedded eigenvalues)

### 2.1 Absence of negative-energy eigenvalues
From Stage 1 Eq. (1.4), for $z < 0$ (where $|V(\omega)|^2 = v_0^2 \omega^{2\alpha} e^{-2\kappa\omega^2}$),
\[
\eta(z) = z - \omega_1 - \lambda^2 v_0^2 \int_0^\infty \frac{\omega^{2\alpha} e^{-2\kappa\omega^2}}{z - \omega}\,d\omega.
\]
Evaluate the threshold integral at $z = 0^-$:
\[
I_0 := \int_0^\infty \frac{|V(\omega)|^2}{\omega}\,d\omega
= v_0^2 \int_0^\infty \omega^{2\alpha - 1} e^{-2\kappa\omega^2}\,d\omega
= \frac{v_0^2}{2} (2\kappa)^{-\alpha} \Gamma(\alpha) < \infty
\qquad (\alpha > 0).
\]
Hence, whenever the weak-to-moderate coupling condition
\[
\lambda^2 < \frac{2\omega_1 (2\kappa)^\alpha}{v_0^2 \Gamma(\alpha)}
\tag{2.1}
\]
holds, we have $\eta(0^-) < 0$ and $\eta'(z) > 0$ for all $z < 0$, with $\eta(z) \to -\infty$ as $z \to -\infty$. Thus $H$ has **no negative-energy eigenvalues**.

### 2.2 Absence of embedded eigenvalues and singular continuous spectrum on $[0, \infty)$
For $\omega > 0$, the imaginary part of the upper boundary value $\eta(\omega + i0)$ is
\[
\operatorname{Im}\eta(\omega + i0) = \pi \lambda^2 J(\omega) = \pi \lambda^2 v_0^2 \omega^{2\alpha} e^{-2\kappa\omega^2}.
\]
Because $J(\omega) > 0$ for all $\omega > 0$ and $V$ is real-analytic on $(0, \infty)$ with super-exponential decay, the Friedrichs–Mourre / limiting absorption principle holds on $(0, \infty)$: $\eta(\omega \pm i0) \neq 0$ for every $\omega > 0$ and every $\lambda \neq 0$. Consequently, $H$ has **no embedded eigenvalues** in $(0, \infty)$, **no singular continuous spectrum**, and purely absolutely continuous spectrum equal to $[0, \infty)$ under (2.1).

---

## 3. Obligation 2: Large-arc decay and dominated convergence for completeness

Let $|\phi_\pm\rangle = c_\pm|1\rangle + \int_0^\infty \phi_\pm(\omega)|\omega\rangle\,d\omega \in \Phi$. Because $\phi_\pm \in \Phi_{\mathrm{cont}}$ are holomorphic in $\mathcal S_\delta$ and decay rapidly (at least as $(1+|z|)^{-m}$ for all $m \ge 0$), consider the matrix element $\langle \phi_- | R(z) | \phi_+ \rangle$ in the upper half-plane $\operatorname{Im} z > 0$:
\[
\langle \phi_- | R(z) | \phi_+ \rangle
= \int_0^\infty \frac{\phi_-^*(\omega)\phi_+(\omega)}{z - \omega}\,d\omega
+ \frac{\mathcal A_-(z;\phi_-)\mathcal A_+(z;\phi_+)}{\eta(z)}.
\tag{3.1}
\]

### 3.1 Large-arc bound ($|z| = R \to \infty$, $0 \le \arg z \le \pi$)
On the upper semicircle $z = R e^{i\vartheta}$ ($0 \le \vartheta \le \pi$, $R$ large):
1. Since $\operatorname{Im} z = R\sin\vartheta \ge 0$ and $\omega \ge 0$, for $\vartheta \in [\epsilon, \pi - \epsilon]$ we have $|z - \omega| \ge R\sin\epsilon$, while for $\vartheta$ near $0$ or $\pi$ we have $|z - \omega| \ge R|\sin\vartheta|$ or $|R - \omega|$. Using $\sup_{\omega \ge 0} |\phi_-^*(\omega)\phi_+(\omega)|(1+\omega)^4 \le C_{\phi}\|\phi_-\|_{2,0}\|\phi_+\|_{2,0}$, we obtain
   \[
   \left| \int_0^\infty \frac{\phi_-^*(\omega)\phi_+(\omega)}{z - \omega}\,d\omega \right|
   \le \frac{C_1}{|z|} \quad (|z| \to \infty).
   \]
2. In $\mathcal A_-(z;\phi_-)$ and $\mathcal A_+(z;\phi_+)$, the Cauchy integrals are $O(|z|^{-1})$, while $\eta(z) = z - \omega_1 - \lambda^2 \int_0^\infty \frac{J(\omega)}{z-\omega}\,d\omega = z(1 + O(|z|^{-2}))$. Thus
   \[
   \left| \frac{\mathcal A_-(z;\phi_-)\mathcal A_+(z;\phi_+)}{\eta(z)} \right|
   \le \frac{C_2}{|z|} \quad (|z| \to \infty).
   \]
Hence $\langle \phi_- | R(z) | \phi_+ \rangle = O(|z|^{-1})$ uniformly in $\arg z \in [0, \pi]$, so the large-arc integral over the upper semicircle vanishes as $R \to \infty$.

### 3.2 Dominated-convergence majorant as $z = iy \to i\infty$ ($y > 0$)
For $z = iy$ ($y \ge 1$), write the deformed-continuum integrand from Stage 1 Eq. (5.4) along $\zeta = x e^{-i\theta}$ ($x > 0$, $d\zeta = e^{-i\theta}dx$):
\[
F_y(x)
:= \frac{iy}{iy - x e^{-i\theta}} \, \frac{1}{2\pi i} \langle \phi_- | [R(xe^{-i\theta}) - R_+(xe^{-i\theta})] | \phi_+ \rangle e^{-i\theta}.
\]
Because $\zeta = x e^{-i\theta}$ lies in the fourth quadrant ($-\theta < 0$), for every $y \ge 1$ and $x > 0$:
\[
|iy - x e^{-i\theta}|^2
= (x\cos\theta)^2 + (y + x\sin\theta)^2
\ge y^2 + x^2,
\]
so the geometric factor satisfies the uniform bound independent of $y \ge 1$:
\[
\left| \frac{iy}{iy - x e^{-i\theta}} \right|
\le \frac{y}{\sqrt{y^2 + x^2}} \le 1.
\tag{3.2}
\]
Meanwhile, the jump density $g_{\mathrm{jump}}(x) := \frac{1}{2\pi i}\langle \phi_- | [R(xe^{-i\theta}) - R_+(xe^{-i\theta})] | \phi_+ \rangle$ belongs to $L^1((0,\infty), dx)$ because:
- near $x = 0$, $J(xe^{-i\theta}) = O(x^{2\alpha})$ with $\alpha > 0$ and $\eta_\mp(0) = -\omega_1 - \lambda^2 \int_0^\infty \frac{J(\omega)}{-\omega}\,d\omega \neq 0$;
- as $x \to \infty$, $\phi_-^*(xe^{-i\theta})\phi_+(xe^{-i\theta})$ and $V(xe^{-i\theta})$ decay super-exponentially ($O(e^{-c x^2})$).

Therefore $|F_y(x)| \le |g_{\mathrm{jump}}(x)| \in L^1((0,\infty), dx)$ for all $y \ge 1$. Since $\lim_{y \to +\infty} \frac{iy}{iy - x e^{-i\theta}} = 1$ pointwise for every $x > 0$, Lebesgue's dominated convergence theorem applies directly and proves the completeness relation (Stage 1 Eq. (9.1)):
\[
\lim_{y \to +\infty} iy\,\langle \phi_- | R(iy) | \phi_+ \rangle
= \langle \phi_- | \psi_{z_0}^R \rangle \langle \psi_{z_0}^L | \phi_+ \rangle
+ \int_{\Gamma_\theta} \langle \phi_- | \psi_\zeta^R \rangle \langle \psi_\zeta^L | \phi_+ \rangle \, d\zeta
= \langle \phi_- | \phi_+ \rangle.
\tag{3.3}
\]

---

## 4. Obligation 3: $L^2(\Gamma_\theta)$ and $L^2(\Gamma_\theta^*)$ integrability of $\Lambda^{-1}(\mathbf{\Phi}_{\mathcal L})$

To ensure that $\Lambda^{-1} A \in \widehat{\mathcal K}$ for every $A \in \mathbf{\Phi}_{\mathcal L}$ (Stage 3 §2.1), we verify that for any $\phi_+ \in \Phi_{\mathrm{cont}}$, the function $\zeta \mapsto \langle \psi_\zeta^L | \phi_+ \rangle$ belongs to $L^2(\Gamma_\theta, |d\zeta|)$ (and symmetrically for $\phi_- \in \Phi_{\mathrm{cont}}$ on $\Gamma_\theta^*$).

From Stage 1 Eq. (7.4b) (with $c_+ = 0$):
\[
\langle \psi_\zeta^L | \phi_+ \rangle
= \phi_+(\zeta)
+ \frac{\lambda V(\zeta)}{\eta_+(\zeta)}
\left[
\lambda \int_{\Gamma_\theta} \frac{V(\zeta')\phi_+(\zeta')}{\zeta - \zeta' + i0_\theta}\,d\zeta'
\right],
\qquad \zeta = x e^{-i\theta} \quad (x > 0).
\tag{4.1}
\]

1. **At large $x$ ($x \to \infty$):** $\phi_+(xe^{-i\theta})$ and $V(xe^{-i\theta})$ decay super-exponentially ($O(e^{-c x^2})$), while $|\eta_+(xe^{-i\theta})| \sim x$ is bounded below away from zeros, and the Cauchy integral is bounded in $x$. Thus the tail is rapidly square-integrable on $[1, \infty)$.
2. **Near the threshold $x \downarrow 0$:** Because $\eta_+(0) \neq 0$ under (2.1) and $|V(xe^{-i\theta})| \le C x^\alpha$ ($\alpha > 0$), we have
   \[
   \left| \frac{\lambda V(xe^{-i\theta})}{\eta_+(xe^{-i\theta})} \right| \le C' x^\alpha \quad (0 < x \le 1).
   \]
   Moreover, for $\phi_+ \in \Phi_{\mathrm{cont}}$, $\phi_+$ is bounded near $0$ and $x \mapsto \int_0^\infty \frac{V(x'e^{-i\theta})\phi_+(x'e^{-i\theta})}{x - x' + i0}\,dx'$ is continuous/bounded near $x = 0$ (since $V(x'e^{-i\theta}) = O(x'^\alpha)$ is integrable at $0$ and rapid-decay at $\infty$). Thus $\langle \psi_{xe^{-i\theta}}^L | \phi_+ \rangle$ is bounded near $x = 0$ and decays super-exponentially as $x \to \infty$:
   \[
   \int_{\Gamma_\theta} \left| \langle \psi_\zeta^L | \phi_+ \rangle \right|^2 |d\zeta|
   = \int_0^\infty \left| \langle \psi_{xe^{-i\theta}}^L | \phi_+ \rangle \right|^2 dx < \infty.
   \tag{4.2}
   \]

By nuclearity of $\mathbf{\Phi}_{\mathcal L} = \Phi \widehat{\otimes} \Phi^\dagger$, this establishes $\Lambda^{-1}(\mathbf{\Phi}_{\mathcal L}) \subset \widehat{\mathcal K}$ continuously, completing the model-level proof audit for Stages 1–3.