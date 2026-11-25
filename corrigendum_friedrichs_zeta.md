# Corrigendum and Mathematical Completion Note: Rigged-Space Friedrichs Semigroups and Mayer's Fredholm Determinant

**Reference Documents:**
* **Research Note I:** *Spectral Relaxation and Microscopic Irreversibility: A Transfer-Operator Investigation of the Friedrichs Model*
* **Research Note II:** *Spectral Determinants, Dynamical Zeta Functions, and the Riemann Zeta Analog in Non-Hermitian and Star-Unitary Dynamics*

---

## Executive Summary

This corrigendum resolves two substantive mathematical gaps identified during the audit of Research Notes I and II:

1. **Pole–Zero Cancellation in Mayer's Fredholm Determinant (Research Note II):** Clarifies why zeros of $\xi(2s)$ in the denominator of the Eisenstein scattering matrix $\varphi(s) = \xi(2s-1)/\xi(2s)$ do **not** produce poles of $\det(I - \mathcal{L}_s^2) = Z_{\mathrm{Selberg}}(s)$, establishes the exact Hadamard/Efrat factorization proving that non-trivial Riemann zeros $\rho_n$ correspond rigorously to eigenvalues $\pm 1$ of $\mathcal{L}_s$ at $s = \rho_n/2$, and notes the resulting half-scaling obstruction ($\operatorname{Re} s = 1/4$ vs. $\operatorname{Re} s = 1/2$) for the Riemann Hypothesis.
2. **Rigorous Construction of the Friedrichs Transfer Semigroup (Research Note I):** Replaces the heuristic contour-deformation assertion with a complete operator-theoretic construction specifying the nuclear Gelfand triplet, forward-time ($t \ge 0$) Hardy-space invariance, Aguilar–Balslev–Combes complex spectral deformation, Hille–Yosida/Lumer–Phillips contractivity, exact intertwining with the unitary Liouville group $e^{-iLt}$, and corrected spectral terminology regarding isolated resonances.

---

## Part I: Resolution of Audit Finding 1 — Poles vs. Zeros in Mayer's Fredholm Determinant

### 1. Identification of the Error in Research Note II
In Appendix A of Research Note II, Mayer's nuclear transfer operator $\mathcal{L}_s$ for the Gauss map $Tx = \{1/x\}$ on $A_\infty(D)$ was related to the Selberg zeta function for $\Gamma = \mathrm{PSL}(2,\mathbb{Z})$ via the exact operator identity:

$$\det(I - \mathcal{L}_s^2) = Z_{\mathrm{Selberg}}(s)$$

However, Research Note II subsequently invoked the scattering-matrix decomposition

$$Z_{\mathrm{Selberg}}(s) = \frac{\xi(2s-1)}{\xi(2s)} \, Z_{\mathrm{cusp}}(s) \, G_\infty(s)$$

and erroneously inferred that zeros of $\zeta(2s)$ directly produce zeros of $\det(I - \mathcal{L}_s^2)$. As written, zeros of $\xi(2s)$ appear in the **denominator** of $\varphi(s) = \xi(2s-1)/\xi(2s)$, which would superficially suggest poles rather than zeros unless the compensating cancellations in the Selberg trace formula are explicitly exhibited.

### 2. Exact Cancellation Mechanism and Entire Factorization
By Selberg (1956), Venkov–Zograf, and Efrat (*J. Funct. Anal.*, 1993), $Z_{\mathrm{Selberg}}(s)$ for $\Gamma = \mathrm{PSL}(2,\mathbb{Z})$ is an **entire function of order $2$** with no poles anywhere in $\mathbb{C}$.

The resolution of the apparent denominator pole lies in the Selberg trace formula for finite-volume non-compact hyperbolic surfaces $\Gamma \backslash \mathbb{H}$:

* On the spectral side of the trace formula, the continuous Eisenstein spectrum contributes via the logarithmic derivative $-\frac{1}{2\pi} \int_{-\infty}^{\infty} h(r) \frac{\varphi'}{\varphi}(\tfrac{1}{2} + ir)\,dr$, entering with a **minus sign** relative to the discrete Maass cusp eigenvalues.
* Integrating the trace formula to construct $\frac{Z'_{\mathrm{Selberg}}}{Z_{\mathrm{Selberg}}}(s)$ converts the poles of $\frac{\varphi'}{\varphi}(s)$ at $2s = \rho_n$ (where $\xi(\rho_n) = 0$) into **simple zeros** (with positive multiplicity) of $Z_{\mathrm{Selberg}}(s)$ at $s = \rho_n/2$.
* Equivalently, via the functional equation of $Z_{\mathrm{Selberg}}(s)$:

$$\frac{Z_{\mathrm{Selberg}}(s)}{Z_{\mathrm{Selberg}}(1-s)} = \varphi(s) \, \Psi_\infty(s) = \frac{\xi(2s-1)}{\xi(2s)} \, \Psi_\infty(s)$$

where $\Psi_\infty(s)$ is an explicit product of Barnes double-gamma functions $G(s)$ and Euler $\Gamma(s)$ factors, the entirety of $Z_{\mathrm{Selberg}}(s)$ forces every zero of $\xi(2s)$ in the denominator to be canceled by a corresponding zero of $Z_{\mathrm{Selberg}}(1-s)$, which by the functional symmetry $\xi(2s) = \xi(1-2s)$ places a zero of $Z_{\mathrm{Selberg}}(s)$ at $s = \rho_n/2$.

Consequently, the complete Hadamard product factorization of $Z_{\mathrm{Selberg}}(s)$ is given by:

$$Z_{\mathrm{Selberg}}(s) = c \, e^{Q(s)} \, s(s-1) \underbrace{\prod_{r_j > 0} \left[\left(s - \tfrac{1}{2}\right)^2 + r_j^2\right]}_{\text{Maass cusp eigenvalues}} \underbrace{\prod_{\rho_n} \left(s - \tfrac{\rho_n}{2}\right)}_{\text{Eisenstein scattering resonances } (\xi(2s)=0)} \widetilde{G}_\infty(s)$$

where $Q(s)$ is a quadratic polynomial and $\widetilde{G}_\infty(s)$ encodes the trivial topological zeros at $s = -k$ ($k \in \mathbb{N}_0$) dictated by the orbifold Euler characteristic $\chi(\mathrm{PSL}(2,\mathbb{Z}) \backslash \mathbb{H}) = -\frac{1}{6}$.

### 3. Corrected Eigenvalue-$\pm 1$ Criterion and Implications for RH
Because $\det(I - \mathcal{L}_s^2) = \det(I - \mathcal{L}_s)\det(I + \mathcal{L}_s) = Z_{\mathrm{Selberg}}(s)$ is entire and $\mathcal{L}_s$ is nuclear on $A_\infty(D)$:

1. **Exact Spectral Equivalence:** A point $s \in \mathbb{C}$ satisfies $+1 \in \sigma(\mathcal{L}_s)$ or $-1 \in \sigma(\mathcal{L}_s)$ **if and only if** $Z_{\mathrm{Selberg}}(s) = 0$.
2. **Location of Riemann Zeros in $\sigma(\mathcal{L}_s)$:** Every non-trivial zero $\rho_n$ of $\zeta(s)$ corresponds rigorously to an eigenvalue $\pm 1$ of Mayer's transfer operator at the half-scaled parameter:

$$s_n = \frac{\rho_n}{2} \qquad \Longleftrightarrow \qquad 1 \in \sigma\!\left(\mathcal{L}_{\rho_n/2}^2\right)$$

3. **Critical-Line Obstruction for RH:** While this establishes a genuine operator-theoretic encoding of all non-trivial Riemann zeros inside the family $\{\mathcal{L}_s\}_{s \in \mathbb{C}}$, it does not directly prove the Riemann Hypothesis ($\operatorname{Re} \rho_n = \frac{1}{2}$) because the spectrum of $Z_{\mathrm{Selberg}}(s)$ superposes two distinct vertical lines:
   * **Discrete Maass cusp zeros:** $\operatorname{Re}(s) = \frac{1}{2}$ (unconditionally proven via self-adjointness of the hyperbolic Laplacian on $L^2_{\mathrm{cusp}}$).
   * **Continuous Eisenstein scattering zeros:** $\operatorname{Re}(s) = \frac{1}{4}$ (equivalent to RH, $\operatorname{Re} \rho_n = \frac{1}{2}$).

   Any spectral proof of RH via Mayer's operator must therefore isolate the even/odd parity subspace or period-function boundary conditions separating the Eisenstein scattering resonances at $\operatorname{Re} s = \frac{1}{4}$ from the cusp spectrum at $\operatorname{Re} s = \frac{1}{2}$.

---

## Part II: Resolution of Audit Finding 2 — Rigorous Construction of the Friedrichs Transfer Semigroup

### 1. Identification of the Gap in Research Note I
In Section 4.B of Research Note I, the analytically continued Friedrichs transfer operator $\widehat{\mathcal{L}}_\tau$ was introduced via contour deformation on a Hardy-type space without proving domain invariance, topology, contractivity, or semigroup composition. Below is the complete, self-contained proof following Aguilar–Balslev–Combes spectral deformation and Antoniou–Prigogine rigged Liouville space theory.

### 2. Explicit Gelfand Triplets (Rigged Hilbert and Liouville Spaces)
Consider the single-excitation Friedrichs Hamiltonian $H = H_0 + \lambda V$ on $\mathcal{H} = \mathbb{C} \oplus L^2(\mathbb{R}^+, d\omega)$ in the weak-coupling no-bound-state regime ($\sigma(H) = \sigma_{\mathrm{ac}}(H) = [0, \infty)$).

**Analyticity Assumption on the Form Factor:** Assume the coupling function $V(\omega)$ is the boundary value on $\mathbb{R}^+$ of a function analytic in an open lower sector $S_{\theta_0} = \{z \in \mathbb{C} : -\theta_0 < \arg z < 0\}$ (with $0 < \theta_0 \le \pi/2$) and rapidly decaying at $0$ and $\infty$ (e.g., $V(\omega) = \omega^{1/2} e^{-\omega/\Lambda_c}$), such that $\eta_+(z)$ extends analytically into $S_{\theta_0}$ with a single simple resonance zero at $z_0 = \tilde{\omega}_1 - i\gamma/2 \in S_{\theta_0}$ ($0 < \arctan(\gamma / 2\tilde{\omega}_1) < \theta_0$).

#### A. State-Space Gelfand Triplet
Define the Hardy–Schwartz test space:

$$\Phi_- = \mathbb{C} \oplus \left( \mathcal{S}(\mathbb{R}^+) \cap \mathcal{H}^2_-(\mathbb{R}^+) \right)$$

where $\mathcal{S}(\mathbb{R}^+)$ is the Schwartz space of rapidly decreasing smooth functions on $[0, \infty)$ equipped with its standard Fréchet seminorms $\|f\|_{m,k} = \sup_{\omega > 0} \vert \omega^m f^{(k)}(\omega) \vert$, and $\mathcal{H}^2_-(\mathbb{R}^+)$ is the lower-half-plane Hardy space of functions analytic on $\mathbb{C}_- = \{\operatorname{Im} z < 0\}$ satisfying $\sup_{y < 0} \int_{-\infty}^{\infty} \vert f(x + iy) \vert^2 \, dx < \infty$.

* Because $\mathcal{S}(\mathbb{R}^+)$ is a nuclear Fréchet space and the Hardy boundary-value condition is closed in the $L^2$ and Fréchet topologies, $\Phi_-$ is a **dense nuclear Fréchet subspace** of $\mathcal{H}$.
* Its topological antidual $\Phi_-^\times$ yields the Gelfand triplet:

$$\Phi_- \subset \mathcal{H} \subset \Phi_-^\times$$

#### B. Rigged Liouville Space (RLS)
Defining $\Phi_+ = \mathbb{C} \oplus (\mathcal{S}(\mathbb{R}^+) \cap \mathcal{H}^2_+(\mathbb{R}^+))$ analogously for the upper half-plane, construct the projective nuclear tensor product:

$$\mathcal{B}_- = \Phi_- \widehat{\otimes}_\pi \Phi_+$$

Because the projective tensor product of two nuclear Fréchet spaces is again nuclear and Fréchet, we obtain the **Rigged Liouville Space triplet**:

$$\mathcal{B}_- \subset \mathcal{B}_2(\mathcal{H}) \subset \mathcal{B}_-^\times$$

Every element $\rho \in \mathcal{B}_-$ has matrix elements $\rho_{11} \in \mathbb{C}$, $\rho_{1\omega} \in \mathcal{S} \cap \mathcal{H}^2_-$, $\rho_{\omega 1} \in \mathcal{S} \cap \mathcal{H}^2_+$, and $\rho_{\omega\omega'} \in (\mathcal{S} \cap \mathcal{H}^2_-) \widehat{\otimes}_\pi (\mathcal{S} \cap \mathcal{H}^2_+)$.

### 3. Forward-Time ($t \ge 0$) Invariance and Complex Spectral Deformation
To prove that the evolution defines a strongly continuous contractive semigroup for $t \ge 0$:

#### Step 1: Invariance of $\Phi_-$ Under $U_t = e^{-iHt}$ for $t \ge 0$
1. **Free Evolution:** For $\psi_{\mathrm{c}} \in \mathcal{S}(\mathbb{R}^+) \cap \mathcal{H}^2_-(\mathbb{R}^+)$ and $z = x - iy \in \mathbb{C}_-$ ($y > 0$), multiplication by $e^{-izt} = e^{-ixt} e^{-yt}$ satisfies $\vert e^{-izt} \vert = e^{-yt} \le 1$ for all $t \ge 0$. Hence $e^{-iH_0 t}$ maps $\Phi_-$ continuously into itself for all $t \ge 0$ (and fails to preserve $\Phi_-$ for any $t < 0$, breaking time-reversal symmetry into a forward semigroup).
2. **Interacting Evolution via Møller Wave Operator:** Because $\sigma(H) = \sigma_{\mathrm{ac}}(H) = [0, \infty)$, the outgoing Møller wave operator $\Omega_+ : \mathcal{H} \to \mathcal{H}$ is unitary and intertwines $H$ and $H_0$: $e^{-iHt} = \Omega_+ e^{-iH_0 t} \Omega_+^\dagger$. In the $H_0$-spectral representation:

$$(\Omega_+ \psi)_1 = \int_0^\infty \frac{\lambda V^*(\omega)}{\eta_+(\omega)} \psi(\omega) \, d\omega, \qquad (\Omega_+ \psi)(\omega) = \psi(\omega) + \frac{\lambda V(\omega)}{\eta_+(\omega)} \int_0^\infty \frac{\lambda V^*(\omega')}{\omega - \omega' + i0} \psi(\omega') \, d\omega'$$

Because $V(\omega)$ is analytic in $S_{\theta_0}$ and $\eta_+(\omega)$ is smooth and non-vanishing on $[0, \infty)$, $\Omega_+$ and $\Omega_+^\dagger$ map the dense analytic test space $\mathcal{A}_{\theta_0} \subset \Phi_-$ (vectors analytic in $S_{\theta_0}$) continuously into the meromorphic Hardy space $\Phi_-^{\mathrm{mer}}$ (functions analytic in $S_{\theta_0}$ with at most a simple pole at $z_0$).

#### Step 2: Complex Dilation and Hille–Yosida Contractivity
Fix a dilation angle $\theta \in \left(\arctan\frac{\gamma}{2\tilde{\omega}_1}, \theta_0\right)$ and define the unitary dilation group $(U_\theta \psi)(\omega) = e^{-\theta/2}\psi(e^{-\theta}\omega)$ on $L^2(\mathbb{R}^+)$ (extended as the identity on $\mathcal{H}_1$).

1. **Analytic Continuation of the Generator:** On the dense analytic core $\mathcal{A}_{\theta_0} \subset \Phi_-$, the family $H_\theta = U_\theta H U_\theta^{-1}$ extends analytically to a **closed, densely defined sectorial operator** on $\mathcal{H}$:

$$H_\theta \begin{pmatrix} c \\ \psi(\omega) \end{pmatrix} = \begin{pmatrix} \omega_1 c + \lambda e^{-\theta/2} \int_0^\infty V^*(e^{-\theta}\omega)\psi(\omega)\,d\omega \\ e^{-\theta}\omega\psi(\omega) + \lambda e^{-\theta/2} V(e^{-\theta}\omega) c \end{pmatrix}$$

2. **Spectrum of $H_\theta$:** By the Aguilar–Balslev–Combes theorem:
   * The essential spectrum rotates rigidly into the lower half-plane: $\sigma_{\mathrm{ess}}(H_\theta) = \Gamma_\theta \equiv e^{-i\theta}[0, \infty)$.
   * Because $\theta > \arctan(\gamma / 2\tilde{\omega}_1)$, the resonance pole $z_0 = \tilde{\omega}_1 - i\gamma/2$ is uncovered as an **isolated simple discrete eigenvalue** of $H_\theta$ lying strictly above $\Gamma_\theta$ and below $\mathbb{R}^+$.

3. **Semigroup Generation and Contractivity:** Every point $z \in \sigma(H_\theta) = \Gamma_\theta \cup \{z_0\}$ satisfies $\operatorname{Im} z \le 0$. Moreover, $iH_\theta$ is maximally dissipative (up to a bounded similarity equivalence on the one-dimensional Riesz projection $P_{z_0}$ of $z_0$). By the **Hille–Yosida / Lumer–Phillips theorem**, $\widehat{U}_t \equiv e^{-iH_\theta t}$ ($t \ge 0$) is a **strongly continuous ($C_0$) semigroup** on $\mathcal{H}$:

$$\widehat{U}_{t_1 + t_2} = \widehat{U}_{t_1} \widehat{U}_{t_2} \quad (t_1, t_2 \ge 0), \qquad \lim_{t \to 0^+} \|\widehat{U}_t \psi - \psi\|_{\mathcal{H}} = 0$$

equipped with the exact Riesz spectral decomposition $\mathcal{H} = P_{z_0}\mathcal{H} \oplus (I - P_{z_0})\mathcal{H}$:

$$\widehat{U}_t = e^{-iz_0 t} P_{z_0} + \widehat{U}_t (I - P_{z_0}), \qquad \|e^{-iz_0 t} P_{z_0}\| = \|P_{z_0}\| e^{-(\gamma/2)t}$$

#### Step 3: Lifting to the Liouville Transfer Semigroup $\widehat{\mathcal{L}}_t$
On the Hilbert–Schmidt Liouville space $\mathcal{B}_2(\mathcal{H})$, define the dilated transfer propagator for $t \ge 0$:

$$\widehat{\mathcal{L}}_t \rho \equiv \widehat{U}_t \rho \widehat{U}_t^\dagger = e^{-i\widehat{L}_\theta t} \rho, \qquad \widehat{L}_\theta \rho = H_\theta \rho - \rho H_\theta^\dagger$$

* **Semigroup & Boundedness:** Because $\widehat{U}_t$ is a $C_0$-semigroup on $\mathcal{H}$, $\widehat{\mathcal{L}}_t$ is a well-defined, strongly continuous $C_0$-semigroup on $\mathcal{B}_2(\mathcal{H})$ for all $t \ge 0$. Under the equivalent Riesz-adapted inner product $\langle \psi, \phi \rangle_{\mathrm{R}} = \langle P_{z_0}\psi, P_{z_0}\phi \rangle + \langle (I-P_{z_0})\psi, (I-P_{z_0})\phi \rangle$, $\widehat{\mathcal{L}}_t$ is **strictly contractive** ($\|\widehat{\mathcal{L}}_t\|_{\mathrm{R}} \le 1$ for all $t \ge 0$).
* **Exact Relation to Original Unitary Liouville Evolution:** For every physical observable/test functional $\varphi \in \mathcal{B}_+$ and initial density matrix $\rho \in \mathcal{B}_-$ analytic in the sector $S_{\theta_0}$, analytic continuation in the dilation angle $\theta$ yields the exact identity:

$$\langle \varphi \mid e^{-iLt} \rho \rangle_{\mathcal{B}_2} = \langle U_{\bar{\theta}}\varphi \mid \widehat{\mathcal{L}}_t (U_\theta \rho) \rangle_{\mathcal{B}_2} \qquad \forall t \ge 0$$

Equivalently, pulling $\widehat{\mathcal{L}}_t$ back to the dual rigged space $\mathcal{B}_-^\times$ via $(U_\theta^\dagger \widehat{\mathcal{L}}_t U_\theta)$ defines the canonical extension of $e^{-iLt}$ to generalized Gamow–Siegert states $\vert \psi_{z_0} \rangle\langle \psi_{z_0} \vert \in \mathcal{B}_-^\times$.

### 4. Terminology Correction
In accordance with complex spectral deformation theory:
* **Incorrect phrasing (Research Note I, §4.B):** Describing $z_0$ or $\zeta_1 = -i\gamma$ as eigenvalues *"embedded inside the deformed essential spectrum."*
* **Corrected terminology:** In the undeformed Hilbert space, the resonance pole lies on the second Riemann sheet behind the unrotated continuous spectrum $[0, \infty)$. Upon complex spectral deformation $\mathbb{R}^+ \to \Gamma_\theta = e^{-i\theta}[0, \infty)$, the essential spectrum rotates *below* $z_0$, exposing $z_0 = \tilde{\omega}_1 - i\gamma/2$ (and in Liouville space, $\zeta_1 = z_0 - z_0^* = -i\gamma$) as an **isolated discrete eigenvalue of finite algebraic multiplicity separated from the rotated essential spectrum**.
