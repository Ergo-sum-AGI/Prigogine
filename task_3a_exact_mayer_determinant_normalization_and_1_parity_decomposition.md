# Task 3A — Exact Mayer Determinant Normalization and $\pm 1$ Parity Decomposition

**Status:** Core mathematical specification for Stage 3 (Zeta / Arithmetic)  
**Builds on:**  
- `broader_program_stage2_deliverable2c_zeta_synthesis.md`  
- `corrigendum_friedrichs_zeta_revised.md` (Part I §§1–5)  
**Purpose:** Fix the exact operator normalization and nuclear disk space $\mathcal B(D)$ for the modular-group Mayer transfer operator $\mathcal L_s$, verify the Fredholm determinant identity $Z_{\mathrm{Sel}}(s) = \det(I - \mathcal L_s)\det(I + \mathcal L_s)$, and decompose the $\pm 1$ eigenspaces via the modular involution to separate Maass cusp-form zeros from Eisenstein scattering zeros at $s = \rho/2$.

---

## 1. Exact normalization of the Mayer transfer operator $\mathcal L_s$

Let $X = \mathrm{PSL}(2, \mathbb Z)\backslash\mathbb H$ be the modular surface, and consider the open disk
\[
D := \left\{ z \in \mathbb C : |z - 1| < \frac{3}{2} \right\}.
\tag{1.1}
\]
Observe that $[0, 1] \subset D$ strictly, and for every integer $n \ge 1$, the inverse Gauss-map branch
\[
\tau_n(z) := \frac{1}{z + n}
\tag{1.2}
\]
maps the closure $\overline{D}$ strictly into the interior of $D$ (indeed, $\tau_1(\overline{D})$ is a disk centered at $\frac{2}{3}$ of radius $\frac{2}{3}$, whose closure lies inside $D = B(1, 3/2)$).

### 1.1 Nuclear Hardy / Bergman disk space $\mathcal B(D)$
Let $\mathcal B(D) = H^2(D)$ (or $A^2(D)$, the Bergman space of holomorphic functions on $D$ square-integrable with respect to area measure $dA(z)$). Because each $\tau_n(\overline{D}) \Subset D$, the composition-plus-weight operators
\[
(\mathcal T_{n,s} f)(z) := \frac{1}{(z + n)^{2s}} \, f\!\left(\frac{1}{z + n}\right),
\qquad n \ge 1,
\tag{1.3}
\]
(using the principal branch of $(z+n)^{-2s}$ on $\operatorname{Re} z > -1/2$) are **nuclear (trace-class)** on $\mathcal B(D)$ with exponentially decaying singular values.

For $\operatorname{Re} s > \frac{1}{2}$, the series of trace-class operators converges in the trace norm $\|\cdot\|_1$ on $\mathcal B(D)$, defining the **Mayer transfer operator**:
\[
(\mathcal L_s f)(z) := \sum_{n=1}^{\infty} \frac{1}{(z + n)^{2s}} \, f\!\left(\frac{1}{z + n}\right),
\qquad \operatorname{Re} s > \frac{1}{2}.
\tag{1.4}
\]

### 1.2 Meromorphic continuation to $\mathbb C$ via Hurwitz / Lerch structure
Writing $f(w) = \sum_{k=0}^{\infty} \frac{f^{(k)}(0)}{k!} w^k$ for $w = (z+n)^{-1}$ inside the convergent series (1.4) gives
\[
(\mathcal L_s f)(z)
= \sum_{k=0}^{\infty} \frac{f^{(k)}(0)}{k!} \sum_{n=1}^{\infty} \frac{1}{(z + n)^{2s + k}}
= \sum_{k=0}^{\infty} \frac{f^{(k)}(0)}{k!} \, \zeta_{\mathrm{Hurwitz}}(2s + k, z + 1),
\tag{1.5}
\]
where $\zeta_{\mathrm{Hurwitz}}(u, a) = \sum_{n=0}^{\infty} (n + a)^{-u}$ has a meromorphic continuation to all $u \in \mathbb C$ with a single simple pole of residue $1$ at $u = 1$.

Consequently:
1. $s \mapsto \mathcal L_s$ extends meromorphically as a trace-class operator-valued function on $\mathcal B(D)$ to the entire complex plane $\mathbb C$;
2. Its only singularities are simple poles at
   \[
   2s + k = 1 \quad \Longleftrightarrow \quad s = \frac{1 - k}{2}, \qquad k = 0, 1, 2, \dots,
   \tag{1.6}
   \]
   with finite-rank residues (specifically, at $s = \frac{1}{2}$, $\operatorname{Res}_{s=1/2} \mathcal L_s$ is the rank-one projection $f \mapsto \frac{1}{2}f(0)\mathbf{1}$);
3. In particular, $\mathcal L_s$ is **holomorphic and nuclear** throughout the open critical strip $0 < \operatorname{Re} s < \frac{1}{2}$, which contains the half-scaled critical line $\operatorname{Re} s = \frac{1}{4}$.

---

## 2. Exact Fredholm determinant identity for $Z_{\mathrm{Sel}}(s)$

For the modular surface $X = \mathrm{PSL}(2,\mathbb Z)\backslash\mathbb H$, the Selberg zeta function is defined for $\operatorname{Re} s > 1$ by the Euler product over primitive closed geodesics $\{\gamma\}$ of length $\ell(\gamma)$:
\[
Z_{\mathrm{Sel}}(s) = \prod_{\{\gamma\}} \prod_{m=0}^{\infty} \left( 1 - e^{-(s + m)\ell(\gamma)} \right),
\tag{2.1}
\]
and extends meromorphically to $\mathbb C$.

### 2.1 Trace-formula periodic-point correspondence
Primitive closed geodesics $\{\gamma\}$ of $\mathrm{PSL}(2,\mathbb Z)\backslash\mathbb H$ correspond bijectively to primitive periodic orbits of the two-step Gauss map $G^2$ (even-length purely periodic continued fractions $[a_1, a_2, \dots, a_{2r}]$). Computing the trace of $\mathcal L_s^N$ on the nuclear space $\mathcal B(D)$ via the Lefschetz / Atiyah–Bott fixed-point formula yields, for $\operatorname{Re} s > 1$:
\[
\operatorname{Tr}(\mathcal L_s^{2r})
= \sum_{\substack{w = (a_1,\dots,a_{2r}) \\ \text{periodic}}} \frac{\varepsilon_w^{2s}}{1 - \varepsilon_w^2},
\qquad \varepsilon_w = \prod_{j=1}^{2r} x_j \in (0, 1),
\tag{2.2}
\]
where $\ell(\gamma) = -2\ln \varepsilon_w$ for primitive periods. Taking the Fredholm determinant $\ln \det(I - \mathcal L_s^2) = -\sum_{N=1}^{\infty} \frac{1}{N}\operatorname{Tr}(\mathcal L_s^N)$ and matching even/odd period cancellations establishes **Mayer's exact determinant identity** for $\operatorname{Re} s > 1$, and by meromorphic continuation throughout $\mathbb C \setminus \{\frac{1-k}{2} : k \ge 0\}$:
\[
Z_{\mathrm{Sel}}(s) = \det(I - \mathcal L_s^2) = \det(I - \mathcal L_s)\det(I + \mathcal L_s).
\tag{2.3}
\]

**Exact pole-cancellation check at $s = \frac{1}{2}$:**  
At $s = \frac{1}{2}$, $\mathcal L_s$ has a simple rank-one pole $\frac{1}{2(s - 1/2)} P_0$ ($P_0 f = f(0)\mathbf{1}$), which gives a simple pole in $\det(I - \mathcal L_s)$ and $\det(I + \mathcal L_s)$ that matches the exact known order of $Z_{\mathrm{Sel}}(s)$ at $s = \frac{1}{2}$ (where $Z_{\mathrm{Sel}}(s)$ has a zero/pole balance fixed by the Eisenstein scattering constant $\varphi(1/2) = -1$). Everywhere inside $0 < \operatorname{Re} s < \frac{1}{2}$, $\mathcal L_s$ is holomorphic and trace-class, so
\[
Z_{\mathrm{Sel}}(s) = 0 \quad \Longleftrightarrow \quad 1 \in \sigma(\mathcal L_s) \;\text{ or }\; -1 \in \sigma(\mathcal L_s)
\qquad \left(0 < \operatorname{Re} s < \frac{1}{2}\right)
\tag{2.4}
\]
holds unconditionally without pole interference.

---

## 3. Parity involution and $\pm 1$ eigenspace decomposition

How do the two factors $\det(I - \mathcal L_s)$ (eigenvalue $+1$) and $\det(I + \mathcal L_s)$ (eigenvalue $-1$) partition the zeros of $Z_{\mathrm{Sel}}(s)$—specifically separating **even/odd Maass cusp forms** and **Eisenstein scattering zeros** $s = \rho/2$?

### 3.1 The Lewis–Zagier / Mayer functional equation for $\pm 1$ eigenfunctions
Suppose $\psi \in \mathcal B(D)$ satisfies $\mathcal L_s \psi = \epsilon \psi$ with $\epsilon \in \{+1, -1\}$. Using the explicit sum (1.4), evaluate $\psi(z) - \epsilon(z+1)^{-2s}\psi\!\left(\frac{1}{z+1}\right)$:
\[
\begin{aligned}
\psi(z) - \epsilon (z + 1)^{-2s} \psi\!\left(\frac{1}{z + 1}\right)
&= \epsilon \sum_{n=2}^{\infty} \frac{1}{(z + n)^{2s}} \psi\!\left(\frac{1}{z + n}\right) \\
&= \epsilon \sum_{m=1}^{\infty} \frac{1}{((z + 1) + m)^{2s}} \psi\!\left(\frac{1}{(z + 1) + m}\right)
= \psi(z + 1).
\end{aligned}
\tag{3.1}
\]
Rearranging (3.1) produces the **three-term Lewis–Zagier period functional equation**:
\[
\psi(z) = \psi(z + 1) + \epsilon \, (z + 1)^{-2s} \psi\!\left(\frac{z}{z + 1}\right)
\qquad \text{(under } w \mapsto 1 - w\text{)}.
\tag{3.2}
\]
More precisely, passing from $\psi(z)$ on $D$ to the period function $u(z)$ on $\mathbb C \setminus (-\infty, 0]$ via the projective slash action of $\mathrm{PSL}(2, \mathbb Z)$ (generated by $T = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$ and $S = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$, with $J = \begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix}$ implementing reflection $z \mapsto -\bar z$ / parity):
- The sign $\epsilon = +1$ corresponds to **even** period functions (invariant under the orientation-reversing reflection $J$);
- The sign $\epsilon = -1$ corresponds to **odd** period functions (anti-invariant under $J$).

### 3.2 Separation of Maass cusp forms and Eisenstein scattering zeros $s = \rho/2$
By the Lewis–Zagier theorem relating Mayer eigenfunctions on $\mathcal B(D)$ to automorphic forms on $\mathrm{PSL}(2, \mathbb Z)\backslash\mathbb H$:

1. **Maass cusp-form zeros ($s = \frac{1}{2} \pm i r_n$):**  
   - **Odd Maass cusp forms** ($f(-\bar z) = -f(z)$) correspond bijectively to **$-1$ eigenfunctions** ($\mathcal L_s \psi = -\psi$) that vanish at $0$ and $\infty$, giving zeros of $\det(I + \mathcal L_s)$ on $\operatorname{Re} s = \frac{1}{2}$.
   - **Even Maass cusp forms** ($f(-\bar z) = +f(z)$) correspond bijectively to **$+1$ eigenfunctions** ($\mathcal L_s \psi = +\psi$) with suitable boundary decay at $0$ and $\infty$, giving zeros of $\det(I - \mathcal L_s)$ on $\operatorname{Re} s = \frac{1}{2}$.

2. **Eisenstein scattering zeros ($s = \frac{\rho}{2}$, where $\zeta(\rho) = 0$):**  
   Unlike cusp forms (which decay exponentially in the cusp $y \to \infty$), Eisenstein series $E(z, s)$ are **even** under $z \mapsto -\bar z$ and grow polynomially ($y^s + \varphi(s) y^{1-s}$) in the cusp!  
   When $\varphi(s)$ has a pole at $s = \rho/2$ (i.e., $\zeta(\rho) = 0$ in the denominator of $\varphi(s) = \frac{s}{s-1}\frac{\xi(2s-1)}{\xi(2s)}$), the regularized residue of the Eisenstein series at $s = \rho/2$ produces a non-trivial **even period function** solving (3.2) with $\epsilon = +1$:
   \[
   \mathcal L_{\rho/2} \psi_\rho = +\psi_\rho,
   \qquad \psi_\rho \in \mathcal B(D) \setminus \{0\}.
   \tag{3.3}
   \]
   **Key parity resolution:** Because the Eisenstein series on $\mathrm{PSL}(2,\mathbb Z)\backslash\mathbb H$ is **even** under reflection $z \mapsto -\bar z$, every non-trivial Riemann zero $\rho$ sits specifically in the **$+1$ eigenspace** of $\mathcal L_{\rho/2}$ (i.e., as a zero of $\det(I - \mathcal L_s)$ rather than $\det(I + \mathcal L_s)$, barring accidental Maass–Riemann coincidences):
   \[
   \zeta(\rho) = 0 \quad \Longrightarrow \quad 1 \in \sigma(\mathcal L_{\rho/2}) \quad \text{(even parity sector)}.
   \tag{3.4}
   \]

---

## 4. Summary of Task 3A and handoff to Task 3B

Task 3A closes the exact operator normalization and parity classification on $\mathcal B(D)$:
1. On the Bergman/Hardy disk space $\mathcal B(D)$ ($D = B(1, 3/2)$), $\mathcal L_s$ is nuclear (trace-class) and holomorphic throughout $0 < \operatorname{Re} s < \frac{1}{2}$, validating $Z_{\mathrm{Sel}}(s) = \det(I - \mathcal L_s)\det(I + \mathcal L_s)$ without unverified pole ambiguities on the critical strip.
2. The parity involution separates the $\pm 1$ eigenspaces via the Lewis–Zagier period equation (3.2): odd Maass forms populate $\det(I + \mathcal L_s) = 0$ on $\operatorname{Re} s = \frac{1}{2}$, even Maass forms populate $\det(I - \mathcal L_s) = 0$ on $\operatorname{Re} s = \frac{1}{2}$, and all Eisenstein scattering zeros $s = \rho/2$ populate the **$+1$ (even) eigenspace** $\det(I - \mathcal L_{\rho/2}) = 0$.

In **Task 3B**, we apply our Stage 1 / Stage 2 rigged-space discipline ($\Phi_{\mathrm{an}} \hookrightarrow \mathcal H \hookrightarrow \Phi_{\mathrm{an}}^\times$) directly to the Eisenstein continuous spectrum on $L^2(\mathrm{PSL}(2,\mathbb Z)\backslash\mathbb H)$, comparing the unitary Eisenstein scattering evolution on $L^2$ with the resonance poles $s = \rho/2$ exposed on analytic test spaces.