# Research Note III: Biorthogonal Resonance–Continuum Spectral Resolution and Liouville Sector Decomposition in the Friedrichs Model

## 0. Context and Summary of Preceding Research Steps

This document consolidates the exact mathematical progression established across the preceding research notes and audit refinements:

1. **Exact Hilbert-Space Friedrichs Resolvent (Research Note I & Section 2 Audit):**
   On the single-excitation Hilbert space $\mathcal{H} = \mathbb{C}|1\rangle \oplus L^2(\mathbb{R}^+, d\omega)$ ($\hbar = 1$), the Hamiltonian $H = H_0 + \lambda V$ acts on vectors $|\psi\rangle = c|1\rangle + \int_0^\infty \psi(\omega)|\omega\rangle\,d\omega$ via
   $$H\begin{pmatrix} c \\ \psi(\omega) \end{pmatrix} = \begin{pmatrix} \omega_1 c + \lambda \displaystyle\int_0^\infty \overline{V(\omega)}\psi(\omega)\,d\omega \\[6pt] \omega\psi(\omega) + \lambda V(\omega)c \end{pmatrix}.$$
   Under the weak-coupling no-bound-state condition $\lambda^2 \int_0^\infty \omega^{-1}|V(\omega)|^2\,d\omega < \omega_1$ with $|V(\omega)| > 0$ on $(0, \infty)$, $H$ has purely absolutely continuous spectrum $\sigma(H) = \sigma_{\mathrm{ac}}(H) = [0, \infty)$. For $z \in \mathbb{C} \setminus [0, \infty)$, the exact discrete-channel resolvent matrix element is $\langle 1 | (z - H)^{-1} | 1 \rangle = \eta(z)^{-1}$, governed by the dispersion function
   $$\eta(z) = z - \omega_1 - \lambda^2 \int_0^\infty \frac{|V(\omega)|^2}{z - \omega}\,d\omega.$$

2. **Second-Sheet Resonance Pole and Golden Rule Decay Width:**
   Defining the Schwarz-reflected holomorphic coupling density $J(z) = V(z)\overline{V(\bar{z})}$, the boundary jump across $(0, \infty)$ is $\eta(E + i0) - \eta(E - i0) = 2\pi i \lambda^2 J(E)$. Continuing $\eta(z)$ from the upper half-plane $\mathbb{C}_+$ downward across $(0, \infty)$ into $\mathbb{C}_-$ gives $\eta_+(z) = \eta(z) + 2\pi i \lambda^2 J(z)$, which admits a simple resonance zero at $z_0 = \tilde{\omega}_1 - i\frac{\gamma}{2}$ with residue $A_1 = [\eta_+'(z_0)]^{-1}$ and Fermi Golden Rule width $\gamma = 2\pi\lambda^2 |V(\tilde{\omega}_1)|^2 + \mathcal{O}(\lambda^4)$.

3. **Distinction Between Physical Liouville Space and Prigogine's Transformed Representation:**
   - On the Hilbert–Schmidt space $\mathcal{B}_2(\mathcal{H})$, the bare Liouvillian $L\rho = [H, \rho]$ is self-adjoint with purely continuous spectrum $\sigma(L) = (-\infty, \infty)$ and generates a unitary group $e^{-iLt}$.
   - In a rigged Liouville space $\mathcal{B}_- \subset \mathcal{B}_2(\mathcal{H}) \subset \mathcal{B}_-^\times$, the extended Liouvillian $L^\times$ admits a rank-one Hermitian generalized resonance eigenoperator $F_{z_0, z_0^*} = |\psi_{z_0}^R\rangle\langle \psi_{z_0}^R|$ satisfying $L^\times F_{z_0, z_0^*} = (z_0 - z_0^*)F_{z_0, z_0^*} = -i\gamma F_{z_0, z_0^*}$.
   - Crucially, $|1\rangle\langle 1| \neq F_{z_0, z_0^*}$ in physical space. Proving that Prigogine's transformation $\Lambda^{-1}$ maps $F_{z_0, z_0^*} \mapsto |1\rangle\langle 1|$, satisfies star-unitarity $\Lambda^{-1}(L) = \Lambda^\dagger(-L)$, and reproduces $[(i\Phi)^e]_{11,11} = \gamma$ (Eq. 3.14 of Prigogine et al., 1977) requires first constructing the **complete right/left biorthogonal resonance-plus-continuum system** and proving its completeness relation from the analytically continued resolvent.

4. **Parallel Audit Status for Mayer's Transfer Operator $\mathcal{L}_s$ and $\zeta(s)$:**
   For the modular group, $Z_{\mathrm{Sel}}(s) = \det(I - \mathcal{L}_s^2) = 0 \iff \pm 1 \in \sigma(\mathcal{L}_s)$. While the Chang–Mayer period function $\psi_s(z)$ realizes the $+1$ eigenspace at $s = \rho_n / 2$ (where $\zeta(2s) = 0$), the half-scaling maps the Riemann critical line $\operatorname{Re}\rho_n = \frac{1}{2}$ to $\operatorname{Re} s = \frac{1}{4}$, distinct from the Maass cusp-form zeros on $\operatorname{Re} s = \frac{1}{2}$.

---

## 1. Rigged Hilbert Space and Explicit Pairing Conventions

Fix the physical inner product on $\mathcal{H} = \mathbb{C}|1\rangle \oplus L^2(\mathbb{R}^+, d\omega)$ (antilinear in the first argument, linear in the second):
$$\langle \phi | \psi \rangle = \overline{c_\phi} c_\psi + \int_0^\infty \overline{\phi(\omega)}\psi(\omega)\,d\omega, \qquad |\phi\rangle = \begin{pmatrix} c_\phi \\ \phi(\omega) \end{pmatrix}, \quad |\psi\rangle = \begin{pmatrix} c_\psi \\ \psi(\omega) \end{pmatrix}. \tag{D1}$$

### Analyticity Sector and Test Spaces $\Phi_\pm$
Assume $V(\omega)$ is the restriction to $\mathbb{R}^+ = (0, \infty)$ of a function $V(z)$ holomorphic in a sector $\mathcal{W} = \{z \in \mathbb{C} \setminus \{0\} : |\arg z| < \theta_0\}$ ($\theta_0 > 0$), with $V(\omega) > 0$ on $(0, \infty)$, rapid decay as $|z| \to \infty$ in $\mathcal{W}$, and $V(\omega) = \mathcal{O}(\omega^\alpha)$ ($\alpha > 0$) as $\omega \downarrow 0$. Define the Schwarz-reflected holomorphic coupling density:
$$J(z) \equiv V(z)\overline{V(\bar{z})}, \qquad z \in \mathcal{W}, \qquad J(\omega) = |V(\omega)|^2 \quad (\omega > 0). \tag{D2}$$
Fix an angle $\theta \in (0, \theta_0)$ such that the simple resonance zero $z_0 = \tilde{\omega}_1 - i\frac{\gamma}{2}$ of $\eta_+(z)$ satisfies $-\theta < \arg z_0 < 0$, and define the rotated contour ray:
$$\Gamma_\theta \equiv \left\{ \zeta = r e^{-i\theta} : r \in [0, \infty) \right\} \subset \mathcal{W}_- \cup \{0\}, \tag{D3}$$
oriented from $0$ to $\infty e^{-i\theta}$. The pole $z_0$ lies strictly inside the open sector $\Sigma_\theta \equiv \{z \in \mathbb{C} : -\theta < \arg z < 0\}$ bounded above by $\mathbb{R}^+$ and below by $\Gamma_\theta$.

Define the dense analytic test spaces $\Phi_\pm \subset \mathcal{H}$:
- $\Phi_+$ consists of vectors $|\phi_+\rangle = c_+|1\rangle + \int_0^\infty \phi_+(\omega)|\omega\rangle\,d\omega$ whose continuum component $\phi_+(z)$ extends holomorphically to $\{z : -\theta_0 < \arg z < \theta_0\}$ with rapid decay as $|z| \to \infty$ in every closed subsector.
- $\Phi_- \equiv \Phi_+$ (symmetric test space), so for any $|\phi_-\rangle \in \Phi_-$, the reflected function $\phi_-^*(z) \equiv \overline{\phi_-(\bar{z})}$ is also holomorphic on $\{z : -\theta_0 < \arg z < \theta_0\}$ with rapid decay.

Let $\Phi_-^\times$ denote the antidual of $\Phi_-$ (continuous antilinear functionals $|\phi_-\rangle \mapsto \langle \phi_- | F \rangle$), and $(\Phi_+)^*$ denote the dual of $\Phi_+$ (continuous linear functionals $|\phi_+\rangle \mapsto \langle G | \phi_+ \rangle$).

---

## 2. Corrected Resolvent Matrix Element and Second-Sheet Continuation

From the exact block resolvent of $H$ (with off-diagonal blocks $R_{1\omega}(z) = \frac{\lambda V(\omega)}{\eta(z)(z-\omega)}$ and $R_{\omega 1}(z) = \frac{\lambda \overline{V(\omega)}}{\eta(z)(z-\omega)}$), for any $|\phi_-\rangle \in \Phi_-$, $|\phi_+\rangle \in \Phi_+$, and $z \in \mathbb{C} \setminus [0, \infty)$, the physical resolvent matrix element is:
$$\langle \phi_- | R(z) | \phi_+ \rangle = \int_0^\infty \frac{\phi_-^*(\omega)\phi_+(\omega)}{z - \omega}\,d\omega + \frac{1}{\eta(z)} \, \mathcal{A}_-(z; \phi_-) \, \mathcal{A}_+(z; \phi_+), \tag{D4}$$
where $\phi_-^*(z) = \overline{\phi_-(\bar{z})}$, and the physical-sheet Cauchy factors are:
$$\mathcal{A}_-(z; \phi_-) \equiv \overline{c_-} + \lambda \int_0^\infty \frac{V(\omega)\phi_-^*(\omega)}{z - \omega}\,d\omega, \qquad \mathcal{A}_+(z; \phi_+) \equiv c_+ + \lambda \int_0^\infty \frac{\overline{V(\omega')}\phi_+(\omega')}{z - \omega'}\,d\omega'. \tag{D5}$$

### Analytic Continuation Across $(0, \infty)$ into $\Sigma_\theta$
For a Cauchy integral $C(z) = \int_0^\infty \frac{f(\omega)}{z-\omega}\,d\omega$, the boundary jump is $C(E + i0) - C(E - i0) = -2\pi i f(E)$, so continuing $C(z)$ from $\mathbb{C}_+$ downward across $(0, \infty)$ into $\Sigma_\theta$ yields $C^{\mathrm{cont}}(z) = C_{\mathrm{phys}}(z) - 2\pi i f(z)$ (with a **minus** sign):

1. In $\eta(z) = z - \omega_1 - \lambda^2 \int_0^\infty \frac{J(\omega)}{z-\omega}\,d\omega$, the minus sign in front of $\lambda^2$ produces a **plus** sign:
   $$\eta_+(z) = \eta(z) + 2\pi i \lambda^2 J(z), \qquad z \in \Sigma_\theta. \tag{D6}$$
2. In $\mathcal{A}_-(z; \phi_-)$ and $\mathcal{A}_+(z; \phi_+)$, the $\lambda$-integrals carry a plus sign, so their analytic continuations across $(0, \infty)$ into $\Sigma_\theta$ carry a **minus** sign, which coincides identically with deforming the contour from $\mathbb{R}^+$ downward to $\Gamma_\theta$ (crossing $z \in \Sigma_\theta$ clockwise):
   $$\mathcal{A}_-^{\mathrm{cont}}(z; \phi_-) = \overline{c_-} + \lambda \int_0^\infty \frac{V(\omega)\phi_-^*(\omega)}{z - \omega}\,d\omega - 2\pi i \lambda V(z)\phi_-^*(z) = \overline{c_-} + \lambda \int_{\Gamma_\theta} \frac{V(\zeta)\phi_-^*(\zeta)}{z - \zeta}\,d\zeta, \tag{D7a}$$
   $$\mathcal{A}_+^{\mathrm{cont}}(z; \phi_+) = c_+ + \lambda \int_0^\infty \frac{\overline{V(\omega')}\phi_+(\omega')}{z - \omega'}\,d\omega' - 2\pi i \lambda \overline{V(\bar{z})}\phi_+(z) = c_+ + \lambda \int_{\Gamma_\theta} \frac{\overline{V(\bar{\zeta})}\phi_+(\zeta)}{z - \zeta}\,d\zeta, \tag{D7b}$$
   valid for all $z$ lying strictly above $\Gamma_\theta$ (including $z = z_0 \in \Sigma_\theta$).
3. Similarly, for all $z$ strictly above $\Gamma_\theta$, $\eta_+(z)$ is written purely as a contour integral along $\Gamma_\theta$:
   $$\eta_+(z) = z - \omega_1 - \lambda^2 \int_{\Gamma_\theta} \frac{J(\zeta)}{z - \zeta}\,d\zeta, \qquad -\theta < \arg z < \pi. \tag{D8}$$

---

## 3. Exact Contour-Deformed Spectral Representation of $R(z)$

For $E > 0$, Stone's jump formula gives:
$$R(E + i0) - R(E - i0) = -2\pi i \, |\psi_E^+\rangle\langle\psi_E^+|. \tag{D9}$$
Since $R(w)$ for $\operatorname{Im} w > 0$ continues meromorphically across $(0, \infty)$ into $\Sigma_\theta$ as $R_+(w)$ (with a single simple pole at $w = z_0$), we have $R(E + i0) = R_+(E + i0)$ for $E > 0$. For any $z \in \mathbb{C}_+$, Stone's representation gives:
$$\langle \phi_- | R(z) | \phi_+ \rangle = \frac{1}{2\pi i} \int_0^\infty \frac{\langle \phi_- | \bigl[R(E - i0) - R_+(E + i0)\bigr] | \phi_+ \rangle}{z - E} \, dE. \tag{D10}$$
Deforming the contour of the $R_+$ integral downward from $\mathbb{R}^+$ to $\Gamma_\theta = e^{-i\theta}\mathbb{R}^+$ encircles the simple pole $w = z_0 \in \Sigma_\theta$ clockwise (while $z \in \mathbb{C}_+$ lies outside $\Sigma_\theta$ and the arc at infinity vanishes):
$$\frac{1}{2\pi i} \int_0^\infty \frac{\langle \phi_- | R_+(E + i0) | \phi_+ \rangle}{z - E} \, dE = \frac{1}{2\pi i} \int_{\Gamma_\theta} \frac{\langle \phi_- | R_+(\zeta) | \phi_+ \rangle}{z - \zeta} \, d\zeta - \frac{\operatorname{Res}_{w = z_0} \langle \phi_- | R_+(w) | \phi_+ \rangle}{z - z_0}. \tag{D11}$$
Meanwhile, $R(w)$ is holomorphic throughout $\mathbb{C}_-$, so the $R(E - i0)$ integral deforms directly from $\mathbb{R}^+$ to $\Gamma_\theta$ with no enclosed poles. Combining both terms gives the **exact contour-deformed resolvent identity** for all $z \in \mathbb{C}_+$:
$$\langle \phi_- | R(z) | \phi_+ \rangle = \frac{\operatorname{Res}_{w = z_0} \langle \phi_- | R_+(w) | \phi_+ \rangle}{z - z_0} + \frac{1}{2\pi i} \int_{\Gamma_\theta} \frac{\langle \phi_- | \bigl[R(\zeta) - R_+(\zeta)\bigr] | \phi_+ \rangle}{z - \zeta} \, d\zeta. \tag{D12}$$

---

## 4. Explicit Right and Left Generalized Eigenvectors ($R$ and $L$ System)

### 4.1 Resonance Right Ket $|\psi_{z_0}^R\rangle$ and Left Bra $\langle \psi_{z_0}^L |$
From (D4), (D7a), and (D7b), the residue of $\langle \phi_- | R_+(w) | \phi_+ \rangle$ at $w = z_0$ factorizes into a rank-one kernel:
$$\operatorname{Res}_{w = z_0} \langle \phi_- | R_+(w) | \phi_+ \rangle = A_1 \, \mathcal{A}_-^{\mathrm{cont}}(z_0; \phi_-) \, \mathcal{A}_+^{\mathrm{cont}}(z_0; \phi_+), \qquad A_1 = \frac{1}{\eta_+'(z_0)}. \tag{D13}$$
Fixing a branch of $\sqrt{A_1}$, we define the **right resonance generalized ket** $|\psi_{z_0}^R\rangle \in \Phi_-^\times$ and the **left resonance generalized bra** $\langle \psi_{z_0}^L | \in (\Phi_+)^*$ explicitly by their action on $\Phi_-$ and $\Phi_+$:
$$\langle \phi_- | \psi_{z_0}^R \rangle \equiv \sqrt{A_1} \left( \overline{c_-} + \lambda \int_{\Gamma_\theta} \frac{V(\zeta)\phi_-^*(\zeta)}{z_0 - \zeta} \, d\zeta \right), \qquad \forall |\phi_-\rangle \in \Phi_-, \tag{D14a}$$
$$\langle \psi_{z_0}^L | \phi_+ \rangle \equiv \sqrt{A_1} \left( c_+ + \lambda \int_{\Gamma_\theta} \frac{\overline{V(\bar{\zeta})}\phi_+(\zeta)}{z_0 - \zeta} \, d\zeta \right), \qquad \forall |\phi_+\rangle \in \Phi_+. \tag{D14b}$$
*(Note: $\langle \psi_{z_0}^L |$ is the transpose/analytic left dual functional with the **same** eigenvalue $z_0$, satisfying $\langle \psi_{z_0}^L | \phi_+ \rangle = \langle \phi_+^* | \psi_{z_0}^R \rangle$, whereas the Hilbert adjoint $\langle \psi_{z_0}^R |$ carries the complex-conjugate eigenvalue $z_0^*$.)*

### 4.2 Deformed-Continuum Right Ket $|\psi_\zeta^R\rangle$ and Left Bra $\langle \psi_\zeta^L |$ for $\zeta \in \Gamma_\theta$
Evaluating the jump $\frac{1}{2\pi i}\langle \phi_- | [R(\zeta) - R_+(\zeta)] | \phi_+ \rangle$ for $\zeta \in \Gamma_\theta \setminus \{0\}$ (the analytic continuation of the Lippmann–Schwinger jump (D9) from $\mathbb{R}^+$ to $\Gamma_\theta$) yields:
$$\frac{1}{2\pi i} \langle \phi_- | \bigl[R(\zeta) - R_+(\zeta)\bigr] | \phi_+ \rangle = \langle \phi_- | \psi_\zeta^R \rangle \langle \psi_\zeta^L | \phi_+ \rangle, \qquad \zeta \in \Gamma_\theta \setminus \{0\}, \tag{D15}$$
where the **deformed-continuum right ket** $|\psi_\zeta^R\rangle \in \Phi_-^\times$ and **left bra** $\langle \psi_\zeta^L | \in (\Phi_+)^*$ are defined for $\zeta \in \Gamma_\theta \setminus \{0\}$ by:
$$\langle \phi_- | \psi_\zeta^R \rangle \equiv \phi_-^*(\zeta) + \frac{\lambda V(\zeta)}{\eta_+(\zeta)} \left( \overline{c_-} + \lambda \int_{\Gamma_\theta} \frac{V(\zeta')\phi_-^*(\zeta')}{\zeta - \zeta' - i0_\theta} \, d\zeta' \right), \qquad \forall |\phi_-\rangle \in \Phi_-, \tag{D16a}$$
$$\langle \psi_\zeta^L | \phi_+ \rangle \equiv \phi_+(\zeta) + \frac{\lambda \overline{V(\bar{\zeta})}}{\eta(\zeta)} \left( c_+ + \lambda \int_{\Gamma_\theta} \frac{\overline{V(\bar{\zeta}')}\phi_+(\zeta')}{\zeta - \zeta' + i0_\theta} \, d\zeta' \right), \qquad \forall |\phi_+\rangle \in \Phi_+, \tag{D16b}$$
where $\zeta - \zeta' \pm i0_\theta$ denotes the boundary value approaching $\Gamma_\theta$ from above ($+i0_\theta$, inside $\Sigma_\theta$) or below ($-i0_\theta$).

---

## 5. Generalized Eigenvalue Equations, Completeness, and Biorthogonality

### Theorem 5.1 (Generalized Eigenvalue Equations)
On the rigged spaces $\Phi_-^\times$ and $(\Phi_+)^*$, the extended Hamiltonians satisfy:
1. **Resonance sector:**
   $$\langle H\phi_- | \psi_{z_0}^R \rangle = z_0 \langle \phi_- | \psi_{z_0}^R \rangle \quad (\forall |\phi_-\rangle \in \Phi_-), \qquad \langle \psi_{z_0}^L | H\phi_+ \rangle = z_0 \langle \psi_{z_0}^L | \phi_+ \rangle \quad (\forall |\phi_+\rangle \in \Phi_+). \tag{D17}$$
2. **Deformed-continuum sector ($\zeta \in \Gamma_\theta \setminus \{0\}$):**
   $$\langle H\phi_- | \psi_\zeta^R \rangle = \zeta \langle \phi_- | \psi_\zeta^R \rangle \quad (\forall |\phi_-\rangle \in \Phi_-), \qquad \langle \psi_\zeta^L | H\phi_+ \rangle = \zeta \langle \psi_\zeta^L | \phi_+ \rangle \quad (\forall |\phi_+\rangle \in \Phi_+). \tag{D18}$$

*Proof Sketch:* Substituting $(H\phi_-)_1 = \omega_1 c_- + \lambda \int_0^\infty \overline{V(\omega)}\phi_-(\omega)\,d\omega$ and $(H\phi_-)(\omega) = \omega\phi_-(\omega) + \lambda V(\omega)c_-$ into (D14a), deforming the $\mathbb{R}^+$-integral to $\Gamma_\theta$, and applying $\frac{\zeta'}{z_0 - \zeta'} = -1 + \frac{z_0}{z_0 - \zeta'}$ leaves the discrete coefficient $\omega_1 + \lambda^2 \int_{\Gamma_\theta} \frac{J(\zeta')}{z_0 - \zeta'}\,d\zeta' = z_0 - \eta_+(z_0) = z_0$ by (D8) and $\eta_+(z_0) = 0$. The same algebraic identity using $\frac{\zeta'}{\zeta - \zeta' \mp i0_\theta} = -1 + \frac{\zeta}{\zeta - \zeta' \mp i0_\theta}$ proves (D18). $\blacksquare$

### Theorem 5.2 (Single-Particle Completeness Relation)
For all test vectors $|\phi_-\rangle \in \Phi_-$ and $|\phi_+\rangle \in \Phi_+$, the physical inner product $\langle \phi_- | \phi_+ \rangle$ admits the exact resonance-plus-deformed-continuum spectral resolution:
$$\langle \phi_- | \phi_+ \rangle = \langle \phi_- | \psi_{z_0}^R \rangle \langle \psi_{z_0}^L | \phi_+ \rangle + \int_{\Gamma_\theta} \langle \phi_- | \psi_\zeta^R \rangle \langle \psi_\zeta^L | \phi_+ \rangle \, d\zeta, \tag{D19}$$
and for all $t \ge 0$, the forward time evolution $\langle \phi_- | e^{-iHt} | \phi_+ \rangle$ decomposes as:
$$\langle \phi_- | e^{-iHt} | \phi_+ \rangle = e^{-iz_0 t} \langle \phi_- | \psi_{z_0}^R \rangle \langle \psi_{z_0}^L | \phi_+ \rangle + \int_{\Gamma_\theta} e^{-i\zeta t} \langle \phi_- | \psi_\zeta^R \rangle \langle \psi_\zeta^L | \phi_+ \rangle \, d\zeta. \tag{D20}$$

*Proof:* Substituting (D13) and (D15) into (D12) gives, for all $z \in \mathbb{C}_+$:
$$\langle \phi_- | R(z) | \phi_+ \rangle = \frac{\langle \phi_- | \psi_{z_0}^R \rangle \langle \psi_{z_0}^L | \phi_+ \rangle}{z - z_0} + \int_{\Gamma_\theta} \frac{\langle \phi_- | \psi_\zeta^R \rangle \langle \psi_\zeta^L | \phi_+ \rangle}{z - \zeta} \, d\zeta. \tag{D21}$$
Multiplying (D21) by $z = iy$ and taking $y \to +\infty$ via dominated convergence yields $\lim_{y \to +\infty} iy\langle \phi_- | R(iy) | \phi_+ \rangle = \langle \phi_- | \phi_+ \rangle$ on the left and (D19) on the right. Applying Stone's Laplace formula for $t \ge 0$ yields (D20). $\blacksquare$

### Theorem 5.3 (Biorthogonality Relations)
The right and left generalized eigenvectors satisfy exact biorthogonality in the distributional sense along $\Gamma_\theta$:
$$\langle \psi_{z_0}^L | \psi_{z_0}^R \rangle = 1, \qquad \langle \psi_{z_0}^L | \psi_\zeta^R \rangle = 0, \qquad \langle \psi_\zeta^L | \psi_{z_0}^R \rangle = 0, \qquad \langle \psi_\zeta^L | \psi_{\zeta'}^R \rangle = \delta_{\Gamma_\theta}(\zeta - \zeta'), \tag{D22}$$
with the resonance normalization verified directly from (D14a)–(D14b) and (D8):
$$\langle \psi_{z_0}^L | \psi_{z_0}^R \rangle = A_1 \left[ 1 + \lambda^2 \int_{\Gamma_\theta} \frac{J(\zeta)}{(z_0 - \zeta)^2} \, d\zeta \right] = A_1 \, \eta_+'(z_0) = 1. \tag{D23}$$

---

## 6. Bare State Decomposition and Four-Sector Liouville Tensor Lift

### 6.1 Exact Decomposition of the Bare State $|1\rangle$
Because $|1\rangle \in \Phi_- \cap \Phi_+$ ($c = 1$, $\phi(\omega) \equiv 0$), evaluating (D14a)–(D16b) on $|1\rangle$ gives:
$$\langle 1 | \psi_{z_0}^R \rangle = \sqrt{A_1}, \qquad \langle \psi_{z_0}^L | 1 \rangle = \sqrt{A_1}, \qquad \langle 1 | \psi_\zeta^R \rangle = \frac{\lambda V(\zeta)}{\eta_+(\zeta)}, \qquad \langle \psi_\zeta^L | 1 \rangle = \frac{\lambda \overline{V(\bar{\zeta})}}{\eta(\zeta)}. \tag{D24}$$
Setting $|\phi_-\rangle = |\phi_+\rangle = |1\rangle$ in Theorem 5.2 yields the exact spectral sum rule:
$$1 = \langle 1 | 1 \rangle = A_1 + \int_{\Gamma_\theta} \frac{\lambda^2 J(\zeta)}{\eta_+(\zeta)\eta(\zeta)} \, d\zeta. \tag{D25}$$

### 6.2 Four-Sector Liouville Eigenoperator Basis and Expansion of $|1\rangle\langle 1|$
Taking the tensor product of the right decomposition on $\Phi_-$ with the Hilbert-adjoint of the left decomposition on $\Phi_+$ (along the conjugate contour $\Gamma_\theta^* = e^{+i\theta}\mathbb{R}^+ \subset \mathbb{C}_+$) defines the four rigorous Liouville eigenoperator sectors in $\mathcal{B}_-^\times$:

1. **Resonance–Resonance Sector:**
   $$F_{z_0, z_0^*} = |\psi_{z_0}^R\rangle \langle \psi_{z_0}^R |, \qquad \widetilde{F}_{z_0, z_0^*} = |\psi_{z_0}^L\rangle \langle \psi_{z_0}^L |, \qquad L^\times F_{z_0, z_0^*} = (z_0 - z_0^*) F_{z_0, z_0^*} = -i\gamma \, F_{z_0, z_0^*}, \tag{D26a}$$
   satisfying $\langle\!\langle \widetilde{F}_{z_0, z_0^*} | F_{z_0, z_0^*} \rangle\!\rangle = 1$ and exact bare-projector overlap:
   $$\langle\!\langle \widetilde{F}_{z_0, z_0^*} \,\big|\, |1\rangle\langle 1| \rangle\!\rangle = \langle \psi_{z_0}^L | 1 \rangle \overline{\langle \psi_{z_0}^L | 1 \rangle} = \sqrt{A_1}\,\overline{\sqrt{A_1}} = |A_1|. \tag{D26b}$$
2. **Resonance–Continuum Cross Sector ($\zeta' \in \Gamma_\theta^*$):**
   $$F_{z_0, \zeta'} = |\psi_{z_0}^R\rangle \langle \psi_{\bar{\zeta}'}^R |, \qquad \widetilde{F}_{z_0, \zeta'} = |\psi_{z_0}^L\rangle \langle \psi_{\bar{\zeta}'}^L |, \qquad L^\times F_{z_0, \zeta'} = (z_0 - \zeta') F_{z_0, \zeta'}. \tag{D26c}$$
3. **Continuum–Resonance Cross Sector ($\zeta \in \Gamma_\theta$):**
   $$F_{\zeta, z_0^*} = |\psi_\zeta^R\rangle \langle \psi_{z_0}^R |, \qquad \widetilde{F}_{\zeta, z_0^*} = |\psi_\zeta^L\rangle \langle \psi_{z_0}^L |, \qquad L^\times F_{\zeta, z_0^*} = (\zeta - z_0^*) F_{\zeta, z_0^*}. \tag{D26d}$$
4. **Continuum–Continuum Sector ($\zeta \in \Gamma_\theta, \; \zeta' \in \Gamma_\theta^*$):**
   $$F_{\zeta, \zeta'} = |\psi_\zeta^R\rangle \langle \psi_{\bar{\zeta}'}^R |, \qquad \widetilde{F}_{\zeta, \zeta'} = |\psi_\zeta^L\rangle \langle \psi_{\bar{\zeta}'}^L |, \qquad L^\times F_{\zeta, \zeta'} = (\zeta - \zeta') F_{\zeta, \zeta'}. \tag{D26e}$$

Finally, taking the tensor product of Theorem 5.2 with its adjoint proves the **exact Liouville completeness expansion** of the bare projector $|1\rangle\langle 1|$ in $\mathcal{B}_-^\times$:
$$|1\rangle\langle 1| = |A_1| \, F_{z_0, z_0^*} + \sqrt{A_1} \int_{\Gamma_\theta^*} \frac{\lambda V(\zeta')}{\eta^*(\zeta')} F_{z_0, \zeta'} \, d\zeta' + \overline{\sqrt{A_1}} \int_{\Gamma_\theta} \frac{\lambda \overline{V(\bar{\zeta})}}{\eta(\zeta)} F_{\zeta, z_0^*} \, d\zeta + \iint_{\Gamma_\theta \times \Gamma_\theta^*} \frac{\lambda^2 \overline{V(\bar{\zeta})}V(\zeta')}{\eta(\zeta)\eta^*(\zeta')} F_{\zeta, \zeta'} \, d\zeta\,d\zeta'. \tag{D27}$$
This rigorously establishes the exact cut-remainder decomposition $|1\rangle\langle 1| = |A_1| F_{z_0, z_0^*} + \rho_{\mathrm{cut}}$ and provides the complete four-sector eigenoperator basis required to construct and test Prigogine's transformation $\Lambda^{-1}$ and star-unitarity $\Lambda^{-1}(L) = \Lambda^\dagger(-L)$.
