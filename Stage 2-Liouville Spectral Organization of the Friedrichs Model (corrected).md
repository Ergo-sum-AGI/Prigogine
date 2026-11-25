# Stage 2: Liouville Spectral Organization of the Friedrichs Model

**Status:** Verified & Frozen Foundation (Building on Stage 1: `friedrichs_stage1_single_particle_foundation.md`)

---

## 0. Context & Audit Corrections Incorporated in Stage 2

This note completes **Stage 2** of the five-stage research programme on spectral relaxation, microscopic irreversibility, and zeta functions. Using the single-particle right/left resonance–continuum biorthogonal system and completeness theorem frozen in **Stage 1**, we construct the four-sector spectral organization of the physical Liouvillian $L = [H, \cdot]$ on the rigged Liouville space $\mathcal{B}_0 \subset \mathcal{B}_- \subset \mathcal{B}_2(\mathcal{H}) \subset \mathcal{B}_-^\times$.

In particular, three structural refinements are locked into this version:
1. **Dual Eigenvalues (Theorem 2.1):** Under the antilinear Riesz/antidual pairing convention on $\mathcal{B}_-^\times$, the dual operators $\widetilde{F}_{\alpha,\beta}$ carry **complex-conjugate eigenvalues** $\ell_{\widetilde{F}_{\alpha,\beta}} = \overline{\ell_{F_{\alpha,\beta}}}$ (e.g., $L^\times \widetilde{F}_{z_0, z_0^*} = +i\gamma\,\widetilde{F}_{z_0, z_0^*}$), distinguishing the antidual representative $\widetilde{F}_{\alpha,\beta} \in \mathcal{B}_-^\times$ from the linear left eigenfunctional $\langle\!\langle \widetilde{F}_{\alpha,\beta} \vert \cdot \rangle\!\rangle \in \mathcal{B}_0^*$.
2. **Continuum–Continuum Wedge Geometry & Long-Time Tails:** The continuum–continuum Liouville eigenvalues $\ell_{\zeta,\zeta'} = (x - x')\cos\theta - i(x + x')\sin\theta$ fill the lower-half-plane angular wedge $-\pi + \theta \le \arg(\ell_{\zeta,\zeta'}) \le -\theta$ (equivalently $\theta \le \arg(-\ell_{\zeta,\zeta'}) \le \pi - \theta$). Because $x + x'$ approaches $0$ near the threshold, there is no uniform spectral gap in this sector, preserving algebraic long-time tails.
3. **Distributional Kernel Formulation (Theorem 2.3):** Biorthogonal duality between right and dual generalized Liouville eigenoperators is formulated rigorously as a tensor-product distributional kernel $\mathcal{K}_{(\alpha,\beta),(\gamma,\delta)}$ smeared against test functions on $\Gamma_\theta \times \Gamma_\theta^*$, avoiding any unproved Hilbert–Schmidt inner product between distributions.

---

## 1. Rigged Liouville Space and Tensor-Product Pairing Conventions

### 1.1 Algebraic and Topological Tensor-Product Spaces
Recall from Stage 1 (Section 1.2) the analytic Fréchet test space $\Phi \subset \mathcal{H} = \mathbb{C}\vert 1\rangle \oplus L^2(\mathbb{R}^+, d\omega)$, with $\Phi_+ = \Phi_- = \Phi$, invariant under $H$ ($H\Phi \subset \Phi$).

On the Hilbert–Schmidt operator space $\mathcal{B}_2(\mathcal{H}) \simeq \mathcal{H} \otimes \overline{\mathcal{H}}$ equipped with the Hilbert–Schmidt inner product (antilinear in the first slot, linear in the second):
$$\langle\!\langle \sigma \vert \rho \rangle\!\rangle \equiv \operatorname{Tr}(\sigma^\dagger \rho), \qquad \sigma, \rho \in \mathcal{B}_2(\mathcal{H}), \tag{L1}$$
a rank-one operator $\sigma = \vert u\rangle\langle v\vert$ acts on $\rho = \vert\phi\rangle\langle \chi\vert$ via:
$$\langle\!\langle \vert u\rangle\langle v\vert \,\big\vert\, \vert\phi\rangle\langle \chi\vert \rangle\!\rangle = \operatorname{Tr}\left( \vert v\rangle\langle u \vert \phi\rangle\langle \chi\vert \right) = \langle u \vert \phi \rangle \langle \chi \vert v \rangle = \langle u \vert \phi \rangle \overline{\langle v \vert \chi \rangle}. \tag{L2}$$

Define the **Liouville test space** $\mathcal{B}_0 \subset \mathcal{B}_2(\mathcal{H})$ as the algebraic tensor product $\Phi \otimes_{\mathrm{alg}} \overline{\Phi}$ (finite linear combinations of rank-one operators $\sum_{k=1}^N \vert\phi_k\rangle\langle \chi_k\vert$ with $\phi_k, \chi_k \in \Phi$), and let $\mathcal{B}_- \equiv \Phi \widehat{\otimes}_\pi \overline{\Phi}$ denote its projective Fréchet tensor-product completion. This yields the **Rigged Liouville Space (RLS)**:
$$\mathcal{B}_0 \subset \mathcal{B}_- \subset \mathcal{B}_2(\mathcal{H}) \subset \mathcal{B}_-^\times \subset \mathcal{B}_0^\times, \tag{L3}$$
where $\mathcal{B}_-^\times$ is the topological antidual of continuous **antilinear** functionals on $\mathcal{B}_-$. Every $\rho \in \mathcal{B}_2(\mathcal{H})$ embeds canonically into $\mathcal{B}_-^\times$ via $\sigma \mapsto \langle\!\langle \sigma \vert \rho \rangle\!\rangle = \operatorname{Tr}(\sigma^\dagger \rho)$.

### 1.2 Invariance Under the Physical Liouvillian $L = [H, \cdot]$
Since $H\Phi \subset \Phi$ (Lemma 1.1 of Stage 1), for any $\sigma = \sum_{k=1}^N \vert\phi_k\rangle\langle \chi_k\vert \in \mathcal{B}_0$,
$$L\sigma = [H, \sigma] = \sum_{k=1}^N \left( \vert H\phi_k\rangle\langle \chi_k\vert - \vert\phi_k\rangle\langle H\chi_k\vert \right) \in \mathcal{B}_0, \tag{L4}$$
and by continuity $L\mathcal{B}_- \subset \mathcal{B}_-$. The extended Liouvillian $L^\times : \mathcal{B}_-^\times \to \mathcal{B}_-^\times$ is defined by antilinear duality:
$$\langle\!\langle \sigma \,\big\vert\, L^\times F \rangle\!\rangle \equiv \langle\!\langle L\sigma \,\big\vert\, F \rangle\!\rangle, \qquad \forall \sigma \in \mathcal{B}_-, \; F \in \mathcal{B}_-^\times. \tag{L5}$$
For $\rho \in \mathcal{B}_0$, $\langle\!\langle L\sigma \vert \rho \rangle\!\rangle = \operatorname{Tr}((H\sigma - \sigma H)^\dagger \rho) = \operatorname{Tr}(\sigma^\dagger [H, \rho]) = \langle\!\langle \sigma \vert L\rho \rangle\!\rangle$, so $L^\times$ restricts to $L$ on $\mathcal{B}_0$.

### 1.3 Upper-Half-Plane Conjugate Contour $\Gamma_\theta^*$ for the Bra Channel
In Stage 1, right kets $\vert\psi_{z_0}^R\rangle, \vert\psi_\zeta^R\rangle \in \Phi^\times$ were constructed along the lower-half-plane contour $\Gamma_\theta = \{x e^{-i\theta} : x > 0\}$ (enclosing the pole $z_0 = \tilde{\omega}_1 - i\frac{\gamma}{2}$), while left bras $\langle \psi_{z_0}^L \vert, \langle \psi_\zeta^L \vert \in \Phi^*$ acted linearly on $\Phi$.

In the Liouville tensor product $\mathcal{B}_0 = \Phi \otimes_{\mathrm{alg}} \overline{\Phi}$, the second slot $\overline{\Phi}$ is **antilinear** in $\chi \in \Phi$. Taking the complex conjugate of the Stage 1 functionals turns any linear functional $\langle \psi^L \vert \in \Phi^*$ into an **antilinear** functional on $\overline{\Phi}$, and turns any antilinear functional $\vert\psi^R\rangle \in \Phi^\times$ into a **linear** functional on $\overline{\Phi}$:
* For any $\chi \in \Phi$, the conjugate ray is $\Gamma_\theta^* \equiv \{\zeta' = x' e^{+i\theta} : x' > 0\}$ with $d\zeta' = e^{+i\theta}\,dx'$ and $\delta_{\Gamma_\theta^*}(\zeta' - u') = e^{-i\theta}\delta(x' - x_{u'})$.
* For $\zeta' = \bar{\zeta} \in \Gamma_\theta^*$ (where $\zeta \in \Gamma_\theta$), define the conjugate-contour functionals acting on $\chi \in \Phi$ via:
  $$\langle \psi_{\bar{\zeta}'}^R \vert \chi \rangle \equiv \overline{\langle \chi \vert \psi_{\bar{\zeta}'}^R \rangle} = \chi(\zeta') + \frac{\lambda V(\zeta')}{\eta^*(\zeta')} \left( c_\chi + \lambda \int_{\Gamma_\theta^*} \frac{\overline{V(\bar{u}')}\chi(u')}{\zeta' - u' + i0_\theta^*}\,du' \right), \tag{L6a}$$
  $$\langle \chi \vert \psi_{\bar{\zeta}'}^L \rangle \equiv \overline{\langle \psi_{\bar{\zeta}'}^L \vert \chi \rangle} = \chi^*(\zeta') + \frac{\lambda \overline{V(\bar{\zeta}')}}{\eta_-(\zeta')} \left( \overline{c_\chi} + \lambda \int_{\Gamma_\theta^*} \frac{V(u')\chi^*(u')}{\zeta' - u' - i0_\theta^*}\,du' \right), \tag{L6b}$$
  where $\eta^*(z) \equiv \overline{\eta(\bar{z})} = \eta(z)$ (physical sheet in $\mathbb{C}_+$), $\eta_-(z) \equiv \overline{\eta_+(\bar{z})} = \eta(z) - 2\pi i \lambda^2 J(z)$ (continued sheet in $\Sigma_\theta^*$ enclosing $z_0^* = \tilde{\omega}_1 + i\frac{\gamma}{2}$), and $\pm i0_\theta^*$ denotes the limit onto $\Gamma_\theta^*$ from above ($+i0_\theta^*$, outside $\Sigma_\theta^*$) or below ($-i0_\theta^*$, inside $\Sigma_\theta^*$).
* By Theorem 5.1 of Stage 1, taking complex conjugates gives the exact conjugate eigenvalue equations for all $\chi \in \Phi$:
  $$\langle \psi_{z_0}^R \vert H\chi \rangle = z_0^* \langle \psi_{z_0}^R \vert \chi \rangle, \qquad \langle H\chi \vert \psi_{z_0}^L \rangle = z_0^* \langle \chi \vert \psi_{z_0}^L \rangle, \tag{L7a}$$
  $$\langle \psi_{\bar{\zeta}'}^R \vert H\chi \rangle = \zeta' \langle \psi_{\bar{\zeta}'}^R \vert \chi \rangle, \qquad \langle H\chi \vert \psi_{\bar{\zeta}'}^L \rangle = \zeta' \langle \chi \vert \psi_{\bar{\zeta}'}^L \rangle, \qquad \forall \zeta' \in \Gamma_\theta^* \setminus \{0\}. \tag{L7b}$$

---

## 2. Construction of the Four Generalized Liouville Sectors

Using the single-particle right kets $\{\vert\psi_{z_0}^R\rangle, \vert\psi_\zeta^R\rangle\}$ and left duals $\{\vert\psi_{z_0}^L\rangle, \vert\psi_\zeta^L\rangle\}$, we construct the **four generalized right eigenoperators** $F_{\alpha,\beta} \in \mathcal{B}_-^\times$ and their **four biorthogonal antidual operators** $\widetilde{F}_{\alpha,\beta} \in \mathcal{B}_-^\times$ (acting on $\sigma = \vert\phi\rangle\langle\chi\vert \in \mathcal{B}_0$ via Eq. L2).

### 2.1 Explicit Definitions of the Four Sectors

1. **Sector I — Resonance–Resonance ($F_{z_0, z_0^*}, \widetilde{F}_{z_0, z_0^*}$):**
   $$F_{z_0, z_0^*} \equiv \vert\psi_{z_0}^R\rangle\langle \psi_{z_0}^R \vert, \qquad \widetilde{F}_{z_0, z_0^*} \equiv \vert\psi_{z_0}^L\rangle\langle \psi_{z_0}^L \vert, \tag{L8a}$$
   defined on $\sigma = \vert\phi\rangle\langle\chi\vert \in \mathcal{B}_0$ by:
   $$\langle\!\langle \vert\phi\rangle\langle\chi\vert \,\big\vert\, F_{z_0, z_0^*} \rangle\!\rangle = \langle \phi \vert \psi_{z_0}^R \rangle \langle \psi_{z_0}^R \vert \chi \rangle, \qquad \langle\!\langle \vert\phi\rangle\langle\chi\vert \,\big\vert\, \widetilde{F}_{z_0, z_0^*} \rangle\!\rangle = \langle \phi \vert \psi_{z_0}^L \rangle \langle \psi_{z_0}^L \vert \chi \rangle. \tag{L8b}$$
   *(Note: Both $F_{z_0, z_0^*}$ and $\widetilde{F}_{z_0, z_0^*}$ are Hermitian functionals in $\mathcal{B}_-^\times$: $\langle\!\langle \sigma^\dagger \vert F_{z_0, z_0^*} \rangle\!\rangle = \overline{\langle\!\langle \sigma \vert F_{z_0, z_0^*} \rangle\!\rangle}$, where $\langle \phi \vert \psi_{z_0}^L \rangle \equiv \overline{\langle \psi_{z_0}^L \vert \phi \rangle}$.)*

2. **Sector II — Resonance–Continuum ($\zeta' \in \Gamma_\theta^* \setminus \{0\}$):**
   $$F_{z_0, \zeta'} \equiv \vert\psi_{z_0}^R\rangle\langle \psi_{\bar{\zeta}'}^R \vert, \qquad \widetilde{F}_{z_0, \zeta'} \equiv \vert\psi_{z_0}^L\rangle\langle \psi_{\bar{\zeta}'}^L \vert, \tag{L9a}$$
   defined on $\sigma = \vert\phi\rangle\langle\chi\vert \in \mathcal{B}_0$ by:
   $$\langle\!\langle \vert\phi\rangle\langle\chi\vert \,\big\vert\, F_{z_0, \zeta'} \rangle\!\rangle = \langle \phi \vert \psi_{z_0}^R \rangle \langle \psi_{\bar{\zeta}'}^R \vert \chi \rangle, \qquad \langle\!\langle \vert\phi\rangle\langle\chi\vert \,\big\vert\, \widetilde{F}_{z_0, \zeta'} \rangle\!\rangle = \langle \phi \vert \psi_{z_0}^L \rangle \langle \psi_{\bar{\zeta}'}^L \vert \chi \rangle. \tag{L9b}$$

3. **Sector III — Continuum–Resonance ($\zeta \in \Gamma_\theta \setminus \{0\}$):**
   $$F_{\zeta, z_0^*} \equiv \vert\psi_\zeta^R\rangle\langle \psi_{z_0}^R \vert, \qquad \widetilde{F}_{\zeta, z_0^*} \equiv \vert\psi_\zeta^L\rangle\langle \psi_{z_0}^L \vert, \tag{L10a}$$
   defined on $\sigma = \vert\phi\rangle\langle\chi\vert \in \mathcal{B}_0$ by:
   $$\langle\!\langle \vert\phi\rangle\langle\chi\vert \,\big\vert\, F_{\zeta, z_0^*} \rangle\!\rangle = \langle \phi \vert \psi_\zeta^R \rangle \langle \psi_{z_0}^R \vert \chi \rangle, \qquad \langle\!\langle \vert\phi\rangle\langle\chi\vert \,\big\vert\, \widetilde{F}_{\zeta, z_0^*} \rangle\!\rangle = \langle \phi \vert \psi_\zeta^L \rangle \langle \psi_{z_0}^L \vert \chi \rangle. \tag{L10b}$$

4. **Sector IV — Continuum–Continuum ($(\zeta, \zeta') \in (\Gamma_\theta \setminus \{0\}) \times (\Gamma_\theta^* \setminus \{0\})$):**
   $$F_{\zeta, \zeta'} \equiv \vert\psi_\zeta^R\rangle\langle \psi_{\bar{\zeta}'}^R \vert, \qquad \widetilde{F}_{\zeta, \zeta'} \equiv \vert\psi_\zeta^L\rangle\langle \psi_{\bar{\zeta}'}^L \vert, \tag{L11a}$$
   defined on $\sigma = \vert\phi\rangle\langle\chi\vert \in \mathcal{B}_0$ by:
   $$\langle\!\langle \vert\phi\rangle\langle\chi\vert \,\big\vert\, F_{\zeta, \zeta'} \rangle\!\rangle = \langle \phi \vert \psi_\zeta^R \rangle \langle \psi_{\bar{\zeta}'}^R \vert \chi \rangle, \qquad \langle\!\langle \vert\phi\rangle\langle\chi\vert \,\big\vert\, \widetilde{F}_{\zeta, \zeta'} \rangle\!\rangle = \langle \phi \vert \psi_\zeta^L \rangle \langle \psi_{\bar{\zeta}'}^L \vert \chi \rangle. \tag{L11b}$$

*(Hermiticity Symmetry Between Cross Sectors: Under operator adjoint $\sigma \mapsto \sigma^\dagger$, Sectors II and III are mutual conjugates: $\langle\!\langle \sigma^\dagger \vert F_{z_0, \zeta'} \rangle\!\rangle = \overline{\langle\!\langle \sigma \vert F_{\bar{\zeta}', z_0^*} \rangle\!\rangle}$, while Sector IV satisfies $\langle\!\langle \sigma^\dagger \vert F_{\zeta, \zeta'} \rangle\!\rangle = \overline{\langle\!\langle \sigma \vert F_{\bar{\zeta}', \bar{\zeta}} \rangle\!\rangle}$.)*

---

## 3. Proof of the Liouville Eigenvalue Equations Across All Four Sectors

**Theorem 2.1 (Four-Sector Liouville Spectral Equations & Complex-Conjugate Dual Eigenvalues).** *In the rigged Liouville antidual $\mathcal{B}_0^\times$ (and continuously on $\mathcal{B}_-^\times$), the extended Liouvillian $L^\times$ acts diagonally on both the right eigenoperators $F_{\alpha,\beta}$ and their antidual representatives $\widetilde{F}_{\alpha,\beta}$, with **complex-conjugate eigenvalues**:*

1. **Right Generalized Eigenoperators $F_{\alpha,\beta} \in \mathcal{B}_-^\times$:**
   $$\begin{aligned}
   L^\times F_{z_0, z_0^*} &= (z_0 - z_0^*) F_{z_0, z_0^*} = -i\gamma \, F_{z_0, z_0^*}, \\
   L^\times F_{z_0, \zeta'} &= (z_0 - \zeta') F_{z_0, \zeta'} \qquad (\zeta' \in \Gamma_\theta^* \setminus \{0\}), \\
   L^\times F_{\zeta, z_0^*} &= (\zeta - z_0^*) F_{\zeta, z_0^*} \qquad (\zeta \in \Gamma_\theta \setminus \{0\}), \\
   L^\times F_{\zeta, \zeta'} &= (\zeta - \zeta') F_{\zeta, \zeta'} \qquad (\zeta \in \Gamma_\theta \setminus \{0\}, \; \zeta' \in \Gamma_\theta^* \setminus \{0\}).
   \end{aligned} \tag{L12a}$$

2. **Antidual Representatives $\widetilde{F}_{\alpha,\beta} \in \mathcal{B}_-^\times$ (Conjugate Eigenvalues $\ell_{\widetilde{F}_{\alpha,\beta}} = \overline{\ell_{F_{\alpha,\beta}}}$):**
   $$\begin{aligned}
   L^\times \widetilde{F}_{z_0, z_0^*} &= (z_0^* - z_0) \widetilde{F}_{z_0, z_0^*} = +i\gamma \, \widetilde{F}_{z_0, z_0^*}, \\
   L^\times \widetilde{F}_{z_0, \zeta'} &= (z_0^* - \bar{\zeta}') \widetilde{F}_{z_0, \zeta'} = \overline{(z_0 - \zeta')} \, \widetilde{F}_{z_0, \zeta'}, \\
   L^\times \widetilde{F}_{\zeta, z_0^*} &= (\bar{\zeta} - z_0) \widetilde{F}_{\zeta, z_0^*} = \overline{(\zeta - z_0^*)} \, \widetilde{F}_{\zeta, z_0^*}, \\
   L^\times \widetilde{F}_{\zeta, \zeta'} &= (\bar{\zeta} - \bar{\zeta}') \widetilde{F}_{\zeta, \zeta'} = \overline{(\zeta - \zeta')} \, \widetilde{F}_{\zeta, \zeta'}.
   \end{aligned} \tag{L12b}$$

3. **Associated Linear Left Eigenfunctionals $\mathcal{F}_{\alpha,\beta}^L(\cdot) \equiv \langle\!\langle \widetilde{F}_{\alpha,\beta} \vert \cdot \rangle\!\rangle \in \mathcal{B}_0^*$:**
   *For the linear functional $\mathcal{F}_{\alpha,\beta}^L(\rho) \equiv \overline{\langle\!\langle \rho \vert \widetilde{F}_{\alpha,\beta} \rangle\!\rangle}$, taking the complex conjugate of (L12b) yields the **unconjugated** eigenvalue $\ell_{F_{\alpha,\beta}}$:*
   $$\mathcal{F}_{\alpha,\beta}^L(L\rho) = \overline{\langle\!\langle L\rho \vert \widetilde{F}_{\alpha,\beta} \rangle\!\rangle} = \overline{\ell_{\widetilde{F}_{\alpha,\beta}}} \, \overline{\langle\!\langle \rho \vert \widetilde{F}_{\alpha,\beta} \rangle\!\rangle} = \ell_{F_{\alpha,\beta}} \, \mathcal{F}_{\alpha,\beta}^L(\rho), \qquad \forall \rho \in \mathcal{B}_0. \tag{L12c}$$

**Proof:** Let $\sigma = \vert\phi\rangle\langle\chi\vert \in \mathcal{B}_0$ be an arbitrary rank-one test operator ($\phi, \chi \in \Phi$).
* For any right dyadic functional $F = \vert u^R\rangle\langle v^R\vert \in \mathcal{B}_-^\times$ where $\langle H\phi \vert u^R \rangle = \alpha \langle \phi \vert u^R \rangle$ and $\langle v^R \vert H\chi \rangle = \beta \langle v^R \vert \chi \rangle$:
  $$\begin{aligned}
  \langle\!\langle \vert\phi\rangle\langle\chi\vert \,\big\vert\, L^\times F \rangle\!\rangle &= \langle\!\langle \vert H\phi\rangle\langle\chi\vert - \vert\phi\rangle\langle H\chi\vert \,\big\vert\, \vert u^R\rangle\langle v^R\vert \rangle\!\rangle \\
  &= \langle H\phi \vert u^R \rangle \langle v^R \vert \chi \rangle - \langle \phi \vert u^R \rangle \langle v^R \vert H\chi \rangle \\
  &= (\alpha - \beta) \langle \phi \vert u^R \rangle \langle v^R \vert \chi \rangle = (\alpha - \beta) \langle\!\langle \vert\phi\rangle\langle\chi\vert \,\big\vert\, F \rangle\!\rangle.
  \end{aligned} \tag{L13a}$$
  Substituting the four pairs $(\alpha, \beta) \in \{(z_0, z_0^*), \, (z_0, \zeta'), \, (\zeta, z_0^*), \, (\zeta, \zeta')\}$ from Theorem 5.1 of Stage 1 and (L7a)–(L7b) gives (L12a) by linearity on $\mathcal{B}_0$.
* Conversely, for the antidual representative $\widetilde{F} = \vert u^L\rangle\langle v^L\vert \in \mathcal{B}_-^\times$, Theorem 5.1 of Stage 1 gives $\langle \psi_{z_0}^L \vert H\phi \rangle = z_0 \langle \psi_{z_0}^L \vert \phi \rangle$ and $\langle \psi_\zeta^L \vert H\phi \rangle = \zeta \langle \psi_\zeta^L \vert \phi \rangle$. Taking complex conjugates yields $\langle H\phi \vert \psi_{z_0}^L \rangle = z_0^* \langle \phi \vert \psi_{z_0}^L \rangle$ and $\langle H\phi \vert \psi_\zeta^L \rangle = \bar{\zeta} \langle \phi \vert \psi_\zeta^L \rangle$, while (L7a)–(L7b) give $\langle H\chi \vert \psi_{z_0}^L \rangle = z_0^* \langle \chi \vert \psi_{z_0}^L \rangle$ and $\langle H\chi \vert \psi_{\bar{\zeta}'}^L \rangle = \zeta' \langle \chi \vert \psi_{\bar{\zeta}'}^L \rangle$, whose complex conjugates are $\langle \psi_{z_0}^L \vert H\chi \rangle = z_0 \langle \psi_{z_0}^L \vert \chi \rangle$ and $\langle \psi_{\bar{\zeta}'}^L \vert H\chi \rangle = \bar{\zeta}' \langle \psi_{\bar{\zeta}'}^L \vert \chi \rangle$. Thus:
  $$\langle\!\langle \vert\phi\rangle\langle\chi\vert \,\big\vert\, L^\times \widetilde{F} \rangle\!\rangle = \langle H\phi \vert u^L \rangle \langle v^L \vert \chi \rangle - \langle \phi \vert u^L \rangle \langle v^L \vert H\chi \rangle = (\bar{\alpha} - \bar{\beta}) \langle\!\langle \vert\phi\rangle\langle\chi\vert \,\big\vert\, \widetilde{F} \rangle\!\rangle, \tag{L13b}$$
  proving (L12b) and (L12c). $\blacksquare$
  
  ### Spectral Location, Wedge Geometry, and Long-Time Tails
Parameterizing $\zeta = x e^{-i\theta} \in \Gamma_\theta$ ($x > 0$) and $\zeta' = x' e^{+i\theta} \in \Gamma_\theta^*$ ($x' > 0$) with $0 < \theta < \pi/2$:
* **Sector I ($\ell_{z_0, z_0^*} = -i\gamma$):** Isolated discrete eigenvalue on the negative imaginary axis with **Liouville population decay rate $\gamma$** (twice the single-particle amplitude decay rate $\gamma/2$).
* **Sector II ($\ell_{z_0, \zeta'} = \tilde{\omega}_1 - x'\cos\theta - i\left(\frac{\gamma}{2} + x'\sin\theta\right)$):** Half-ray starting at $\tilde{\omega}_1 - i\frac{\gamma}{2}$ at angle $-\theta$ into the lower half-plane, separated from the real axis by the strict gap $\operatorname{Im} \ell_{z_0, \zeta'} \le -\frac{\gamma}{2} < 0$.
* **Sector III ($\ell_{\zeta, z_0^*} = x\cos\theta - \tilde{\omega}_1 - i\left(\frac{\gamma}{2} + x\sin\theta\right)$):** Half-ray starting at $-\tilde{\omega}_1 - i\frac{\gamma}{2}$ at angle $-\pi + \theta$ into the lower half-plane, separated from the real axis by $\operatorname{Im} \ell_{\zeta, z_0^*} \le -\frac{\gamma}{2} < 0$.
* **Sector IV ($\ell_{\zeta, \zeta'} = (x - x')\cos\theta - i(x + x')\sin\theta$):** For all $x, x' > 0$, $\operatorname{Im} \ell_{\zeta, \zeta'} = -(x + x')\sin\theta < 0$, while $\frac{\operatorname{Re} \ell_{\zeta,\zeta'}}{\vert \operatorname{Im} \ell_{\zeta,\zeta'} \vert} = \frac{x - x'}{x + x'} \cot\theta \in (-\cot\theta, \cot\theta)$. Hence $\ell_{\zeta, \zeta'}$ fills the open lower-half-plane angular wedge bounded by the two rotated continuum rays:
  $$-\pi + \theta < \arg(\ell_{\zeta, \zeta'}) < -\theta \qquad \Longleftrightarrow \qquad \theta < \arg(-\ell_{\zeta, \zeta'}) < \pi - \theta. \tag{L13c}$$
  **Dynamical Consequence (Absence of Uniform Gap & Long-Time Tails):** Although each individual mode $(x, x')$ decays exponentially as $\vert e^{-i\ell_{\zeta,\zeta'}t} \vert = e^{-(x+x')\sin\theta\,t}$, the vertex of the wedge touches the origin as $x + x' \downarrow 0$, so **there is no uniform positive decay gap** in Sector IV. Consequently, integrating over $(x, x') \in (0, \infty)^2$ produces algebraic power-law tails (e.g., $\mathcal{O}(t^{-3})$ when $J(\omega) \propto \omega^{1/2}$), preserving the non-Markovian long-time tails required in Prigogine's theory.

---

## 4. Liouville Completeness and Forward Time-Evolution Theorem

**Theorem 2.2 (Liouville Spectral Resolution of the Identity and Forward Semigroup Representation).** *For all test operators $\sigma, \rho \in \mathcal{B}_0 = \Phi \otimes_{\mathrm{alg}} \overline{\Phi}$, the Hilbert–Schmidt inner product $\langle\!\langle \sigma \vert \rho \rangle\!\rangle = \operatorname{Tr}(\sigma^\dagger \rho)$ admits the exact four-sector spectral resolution:*
$$\begin{aligned}
\langle\!\langle \sigma \vert \rho \rangle\!\rangle &= \langle\!\langle \sigma \vert F_{z_0, z_0^*} \rangle\!\rangle \mathcal{F}_{z_0, z_0^*}^L(\rho) + \int_{\Gamma_\theta^*} \langle\!\langle \sigma \vert F_{z_0, \zeta'} \rangle\!\rangle \mathcal{F}_{z_0, \zeta'}^L(\rho) \, d\zeta' \\
&\quad + \int_{\Gamma_\theta} \langle\!\langle \sigma \vert F_{\zeta, z_0^*} \rangle\!\rangle \mathcal{F}_{\zeta, z_0^*}^L(\rho) \, d\zeta + \iint_{\Gamma_\theta \times \Gamma_\theta^*} \langle\!\langle \sigma \vert F_{\zeta, \zeta'} \rangle\!\rangle \mathcal{F}_{\zeta, \zeta'}^L(\rho) \, d\zeta \, d\zeta',
\end{aligned} \tag{L14}$$
*where $\mathcal{F}_{\alpha,\beta}^L(\rho) = \overline{\langle\!\langle \rho \vert \widetilde{F}_{\alpha,\beta} \rangle\!\rangle}$. Moreover, for all forward times $t \ge 0$, the unitary Liouville evolution $\langle\!\langle \sigma \vert e^{-iLt}\rho \rangle\!\rangle = \operatorname{Tr}(\sigma^\dagger e^{-iHt}\rho e^{iHt})$ decomposes into four exponentially damped/oscillatory channels:*
$$\begin{aligned}
\langle\!\langle \sigma \vert e^{-iLt}\rho \rangle\!\rangle &= e^{-\gamma t} \langle\!\langle \sigma \vert F_{z_0, z_0^*} \rangle\!\rangle \mathcal{F}_{z_0, z_0^*}^L(\rho) + \int_{\Gamma_\theta^*} e^{-i(z_0 - \zeta')t} \langle\!\langle \sigma \vert F_{z_0, \zeta'} \rangle\!\rangle \mathcal{F}_{z_0, \zeta'}^L(\rho) \, d\zeta' \\
&\quad + \int_{\Gamma_\theta} e^{-i(\zeta - z_0^*)t} \langle\!\langle \sigma \vert F_{\zeta, z_0^*} \rangle\!\rangle \mathcal{F}_{\zeta, z_0^*}^L(\rho) \, d\zeta + \iint_{\Gamma_\theta \times \Gamma_\theta^*} e^{-i(\zeta - \zeta')t} \langle\!\langle \sigma \vert F_{\zeta, \zeta'} \rangle\!\rangle \mathcal{F}_{\zeta, \zeta'}^L(\rho) \, d\zeta \, d\zeta'.
\end{aligned} \tag{L15}$$

**Proof:** By sesquilinearity, it suffices to prove (L14) and (L15) for rank-one test operators $\sigma = \vert\phi_1\rangle\langle \chi_1\vert$ and $\rho = \vert\phi_2\rangle\langle \chi_2\vert$ with $\phi_1, \chi_1, \phi_2, \chi_2 \in \Phi$.

1. From Theorem 5.2 of Stage 1 (Eq. D19), we have:
   $$\langle \phi_1 \vert \phi_2 \rangle = \langle \phi_1 \vert \psi_{z_0}^R \rangle \langle \psi_{z_0}^L \vert \phi_2 \rangle + \int_{\Gamma_\theta} \langle \phi_1 \vert \psi_\zeta^R \rangle \langle \psi_\zeta^L \vert \phi_2 \rangle \, d\zeta. \tag{L16a}$$
2. Taking the complex conjugate of Theorem 5.2 applied to $\langle \chi_1 \vert \chi_2 \rangle$ (and changing integration variable $\bar{\zeta}' \in \Gamma_\theta \mapsto \zeta' \in \Gamma_\theta^*$, so $\overline{d\bar{\zeta}'} = d\zeta'$) gives:
   $$\langle \chi_2 \vert \chi_1 \rangle = \overline{\langle \chi_1 \vert \chi_2 \rangle} = \langle \psi_{z_0}^R \vert \chi_1 \rangle \langle \chi_2 \vert \psi_{z_0}^L \rangle + \int_{\Gamma_\theta^*} \langle \psi_{\bar{\zeta}'}^R \vert \chi_1 \rangle \langle \chi_2 \vert \psi_{\bar{\zeta}'}^L \rangle \, d\zeta'. \tag{L16b}$$
3. Multiplying (L16a) and (L16b) together (justified by Fubini's theorem since the integrands decay rapidly along $\Gamma_\theta$ and $\Gamma_\theta^*$) and grouping the four resulting products using (L2) and (L8b)–(L11b) yields:
   $$\begin{aligned}
   \langle\!\langle \vert\phi_1\rangle\langle\chi_1\vert \,\big\vert\, \vert\phi_2\rangle\langle\chi_2\vert \rangle\!\rangle &= \langle \phi_1 \vert \phi_2 \rangle \langle \chi_2 \vert \chi_1 \rangle \\
   &= \left(\langle \phi_1 \vert \psi_{z_0}^R \rangle \langle \psi_{z_0}^R \vert \chi_1 \rangle\right) \left(\langle \psi_{z_0}^L \vert \phi_2 \rangle \langle \chi_2 \vert \psi_{z_0}^L \rangle\right) \\
   &\quad + \int_{\Gamma_\theta^*} \left(\langle \phi_1 \vert \psi_{z_0}^R \rangle \langle \psi_{\bar{\zeta}'}^R \vert \chi_1 \rangle\right) \left(\langle \psi_{z_0}^L \vert \phi_2 \rangle \langle \chi_2 \vert \psi_{\bar{\zeta}'}^L \rangle\right) d\zeta' \\
   &\quad + \int_{\Gamma_\theta} \left(\langle \phi_1 \vert \psi_\zeta^R \rangle \langle \psi_{z_0}^R \vert \chi_1 \rangle\right) \left(\langle \psi_\zeta^L \vert \phi_2 \rangle \langle \chi_2 \vert \psi_{z_0}^L \rangle\right) d\zeta \\
   &\quad + \iint_{\Gamma_\theta \times \Gamma_\theta^*} \left(\langle \phi_1 \vert \psi_\zeta^R \rangle \langle \psi_{\bar{\zeta}'}^R \vert \chi_1 \rangle\right) \left(\langle \psi_\zeta^L \vert \phi_2 \rangle \langle \chi_2 \vert \psi_{\bar{\zeta}'}^L \rangle\right) d\zeta\,d\zeta'.
   \end{aligned}$$
   Since $\langle \psi_{\alpha}^L \vert \phi_2 \rangle \langle \chi_2 \vert \psi_{\beta}^L \rangle = \overline{\langle \phi_2 \vert \psi_\alpha^L \rangle \langle \psi_\beta^L \vert \chi_2 \rangle} = \overline{\langle\!\langle \rho \vert \widetilde{F}_{\alpha,\beta} \rangle\!\rangle} = \mathcal{F}_{\alpha,\beta}^L(\rho)$, this is identically (L14).
4. For $t \ge 0$, replacing $\langle \phi_1 \vert \phi_2 \rangle$ by $\langle \phi_1 \vert e^{-iHt} \phi_2 \rangle$ (Eq. D20 of Stage 1) and $\langle \chi_2 \vert \chi_1 \rangle$ by $\langle \chi_2 \vert e^{+iHt} \chi_1 \rangle = \overline{\langle \chi_1 \vert e^{-iHt} \chi_2 \rangle}$ (which carries $e^{+iz_0^* t}$ and $e^{+i\zeta' t}$) and multiplying the two expansions yields (L15) immediately. $\blacksquare$

---

## 5. Distributional Kernel Biorthogonality Across the Four Sectors

Because $F_{\gamma,\delta}$ and $\widetilde{F}_{\alpha,\beta}$ belong to the dual distribution space $\mathcal{B}_-^\times$ rather than the Hilbert–Schmidt space $\mathcal{B}_2(\mathcal{H})$, their ordinary Hilbert–Schmidt inner product $\operatorname{Tr}(\widetilde{F}_{\alpha,\beta}^\dagger F_{\gamma,\delta})$ is not directly defined. Instead, biorthogonal duality is defined rigorously as a **distributional pairing kernel** $\mathcal{K}_{(\alpha,\beta),(\gamma,\delta)}$ obtained by inserting the single-particle resolution of the identity (Theorem 5.2 of Stage 1) and smearing against smooth, rapidly decaying test functions $g_1, g_2 \in \mathcal{S}_0(\Gamma_\theta)$ and $h_1, h_2 \in \mathcal{S}_0(\Gamma_\theta^*)$ (where $\mathcal{S}_0$ denotes Schwartz-class functions along the ray vanishing at $0$).

**Theorem 2.3 (Four-Sector Liouville Distributional Biorthogonality).** *Define the distributional pairing kernel between the left eigenfunctionals $\mathcal{F}_{\alpha,\beta}^L$ and right eigenoperators $F_{\gamma,\delta}$ via tensor-product composition of the single-particle distributional pairings from Theorem 5.3 of Stage 1:*
$$\mathcal{K}_{(\alpha,\beta),(\gamma,\delta)} \equiv \langle \psi_\alpha^L \vert \psi_\gamma^R \rangle \, \overline{\langle \psi_{\bar{\beta}}^L \vert \psi_{\bar{\delta}}^R \rangle} \qquad \text{in } \mathcal{D}'\bigl((\Gamma_\theta \times \Gamma_\theta^*)^2\bigr). \tag{L17}$$
*When smeared against test functions $g_1(\zeta), g_2(\eta) \in \mathcal{S}_0(\Gamma_\theta)$ and $h_1(\zeta'), h_2(\eta') \in \mathcal{S}_0(\Gamma_\theta^*)$ with respect to the complex line elements $d\zeta = e^{-i\theta}\,dx$ and $d\zeta' = e^{+i\theta}\,dx'$, this kernel satisfies exact block-diagonal biorthogonality:*

1. **Diagonal Normalization:**
   $$\begin{aligned}
   \mathcal{K}_{(z_0, z_0^*), (z_0, z_0^*)} &= 1, \\
   \mathcal{K}_{(z_0, \zeta'), (z_0, \eta')} &= \delta_{\Gamma_\theta^*}(\zeta' - \eta') = e^{-i\theta}\delta(x' - y') \qquad (\zeta' = x'e^{+i\theta}, \; \eta' = y'e^{+i\theta}), \\
   \mathcal{K}_{(\zeta, z_0^*), (\eta, z_0^*)} &= \delta_{\Gamma_\theta}(\zeta - \eta) = e^{+i\theta}\delta(x - y) \qquad (\zeta = x e^{-i\theta}, \; \eta = y e^{-i\theta}), \\
   \mathcal{K}_{(\zeta, \zeta'), (\eta, \eta')} &= \delta_{\Gamma_\theta}(\zeta - \eta)\,\delta_{\Gamma_\theta^*}(\zeta' - \eta').
   \end{aligned} \tag{L18}$$

2. **Off-Diagonal Orthogonality:** *All cross-sector kernels vanish identically as distributions:*
   $$\mathcal{K}_{(\alpha,\beta), (\gamma,\delta)} = 0 \qquad \text{whenever } (\alpha,\beta) \text{ and } (\gamma,\delta) \text{ belong to distinct sectors.} \tag{L19}$$

**Proof:** For any test vector $\vert\phi_+\rangle \in \Phi$, Theorem 5.2 of Stage 1 gives the weak spectral representation $\vert\phi_+\rangle = \vert\psi_{z_0}^R\rangle \langle \psi_{z_0}^L \vert \phi_+ \rangle + \int_{\Gamma_\theta} \vert\psi_\eta^R\rangle \langle \psi_\eta^L \vert \phi_+ \rangle \, d\eta$. Applying $\langle \psi_{z_0}^L \vert$ and $\langle \psi_\zeta^L \vert$ (smeared against $g_1(\zeta)\,d\zeta$) to this representation and invoking Theorem 5.3 of Stage 1 ($\langle \psi_{z_0}^L \vert \psi_{z_0}^R \rangle = 1$, $\langle \psi_{z_0}^L \vert \psi_\eta^R \rangle = \langle \psi_\zeta^L \vert \psi_{z_0}^R \rangle = 0$, and $\langle \psi_\zeta^L \vert \psi_\eta^R \rangle = \delta_{\Gamma_\theta}(\zeta - \eta) = e^{+i\theta}\delta(x - y)$) establishes the single-particle distributional kernel identities on $\mathcal{S}_0(\Gamma_\theta) \times \mathcal{S}_0(\Gamma_\theta)$.
Taking the complex conjugate along $\Gamma_\theta^*$ (where $\overline{\delta_{\Gamma_\theta}(\bar{\zeta}' - \bar{\eta}')} = \overline{e^{+i\theta}\delta(x' - y')} = e^{-i\theta}\delta(x' - y') = \delta_{\Gamma_\theta^*}(\zeta' - \eta')$) gives the conjugate-channel distributional kernel identities on $\mathcal{S}_0(\Gamma_\theta^*) \times \mathcal{S}_0(\Gamma_\theta^*)$. Forming the tensor-product distribution $\mathcal{K}_{(\alpha,\beta),(\gamma,\delta)} = \langle \psi_\alpha^L \vert \psi_\gamma^R \rangle \, \overline{\langle \psi_{\bar{\beta}}^L \vert \psi_{\bar{\delta}}^R \rangle}$ via the Schwartz kernel theorem on $\mathcal{S}_0(\Gamma_\theta) \widehat{\otimes}_\pi \mathcal{S}_0(\Gamma_\theta^*)$ yields (L18) and (L19) directly, and substitution into (L14) confirms that each smeared spectral component in Theorem 2.2 is uniquely projected out by its dual functional $\mathcal{F}_{\alpha,\beta}^L$. $\blacksquare$

---

## 6. Exact Four-Sector Expansion of the Bare Projector $\vert 1\rangle\langle 1\vert$ and Coefficient Audit

Setting $\rho = \vert 1\rangle\langle 1\vert \in \mathcal{B}_0$ (with $c = 1, \phi \equiv 0$) in Theorem 2.2, we compute the exact linear left-eigenfunctional coefficients $\mathcal{F}_{\alpha,\beta}^L(\vert 1\rangle\langle 1\vert) = \overline{\langle\!\langle \vert 1\rangle\langle 1\vert \vert \widetilde{F}_{\alpha,\beta} \rangle\!\rangle}$ from the Stage 1 overlaps $\langle \psi_{z_0}^L \vert 1 \rangle = \sqrt{A_1}$ and $\langle \psi_\zeta^L \vert 1 \rangle = \frac{\lambda V(\zeta)}{\eta_+(\zeta)}$:

1. **Resonance–Resonance coefficient:**
   $$c_{z_0, z_0^*} \equiv \mathcal{F}_{z_0, z_0^*}^L(\vert 1\rangle\langle 1\vert) = \langle \psi_{z_0}^L \vert 1 \rangle \overline{\langle \psi_{z_0}^L \vert 1 \rangle} = \sqrt{A_1}\,\overline{\sqrt{A_1}} = \vert A_1\vert. \tag{L20a}$$
2. **Resonance–Continuum coefficient ($\zeta' \in \Gamma_\theta^*$):**
   $$c_{z_0, \zeta'} \equiv \mathcal{F}_{z_0, \zeta'}^L(\vert 1\rangle\langle 1\vert) = \langle \psi_{z_0}^L \vert 1 \rangle \overline{\langle \psi_{\bar{\zeta}'}^L \vert 1 \rangle} = \sqrt{A_1} \, \frac{\lambda \overline{V(\bar{\zeta}')}}{\eta_-(\zeta')}. \tag{L20b}$$
3. **Continuum–Resonance coefficient ($\zeta \in \Gamma_\theta$):**
   $$c_{\zeta, z_0^*} \equiv \mathcal{F}_{\zeta, z_0^*}^L(\vert 1\rangle\langle 1\vert) = \langle \psi_\zeta^L \vert 1 \rangle \overline{\langle \psi_{z_0}^L \vert 1 \rangle} = \overline{\sqrt{A_1}} \, \frac{\lambda V(\zeta)}{\eta_+(\zeta)}. \tag{L20c}$$
4. **Continuum–Continuum coefficient ($\zeta \in \Gamma_\theta, \zeta' \in \Gamma_\theta^*$):**
   $$c_{\zeta, \zeta'} \equiv \mathcal{F}_{\zeta, \zeta'}^L(\vert 1\rangle\langle 1\vert) = \langle \psi_\zeta^L \vert 1 \rangle \overline{\langle \psi_{\bar{\zeta}'}^L \vert 1 \rangle} = \frac{\lambda^2 V(\zeta)\overline{V(\bar{\zeta}')}}{\eta_+(\zeta)\eta_-(\zeta')}. \tag{L20d}$$

Thus, for all $\sigma \in \mathcal{B}_0$ and all $t \ge 0$, the exact time evolution of the bare excited state $\rho(t) = e^{-iLt}(\vert 1\rangle\langle 1\vert)$ is proved to be:
$$\begin{aligned}
\langle\!\langle \sigma \vert e^{-iLt}(\vert 1\rangle\langle 1\vert) \rangle\!\rangle &= \vert A_1\vert e^{-\gamma t} \langle\!\langle \sigma \vert F_{z_0, z_0^*} \rangle\!\rangle + \sqrt{A_1} \int_{\Gamma_\theta^*} \frac{\lambda \overline{V(\bar{\zeta}')}}{\eta_-(\zeta')} e^{-i(z_0 - \zeta')t} \langle\!\langle \sigma \vert F_{z_0, \zeta'} \rangle\!\rangle \, d\zeta' \\
&\quad + \overline{\sqrt{A_1}} \int_{\Gamma_\theta} \frac{\lambda V(\zeta)}{\eta_+(\zeta)} e^{-i(\zeta - z_0^*)t} \langle\!\langle \sigma \vert F_{\zeta, z_0^*} \rangle\!\rangle \, d\zeta + \iint_{\Gamma_\theta \times \Gamma_\theta^*} \frac{\lambda^2 V(\zeta)\overline{V(\bar{\zeta}')}}{\eta_+(\zeta)\eta_-(\zeta')} e^{-i(\zeta - \zeta')t} \langle\!\langle \sigma \vert F_{\zeta, \zeta'} \rangle\!\rangle \, d\zeta\,d\zeta'.
\end{aligned} \tag{L21}$$

### Exact Survival Probability Check ($\sigma = \vert 1\rangle\langle 1\vert$)
Setting $\sigma = \vert 1\rangle\langle 1\vert$ in (L21) and using $\langle\!\langle \vert 1\rangle\langle 1\vert \vert F_{z_0, z_0^*} \rangle\!\rangle = \vert A_1\vert$, $\langle\!\langle \vert 1\rangle\langle 1\vert \vert F_{z_0, \zeta'} \rangle\!\rangle = \sqrt{A_1}\frac{\lambda V(\zeta')}{\eta^*(\zeta')}$, $\langle\!\langle \vert 1\rangle\langle 1\vert \vert F_{\zeta, z_0^*} \rangle\!\rangle = \overline{\sqrt{A_1}}\frac{\lambda\overline{V(\bar{\zeta})}}{\eta(\zeta)}$, and $\langle\!\langle \vert 1\rangle\langle 1\vert \vert F_{\zeta, \zeta'} \rangle\!\rangle = \frac{\lambda^2 \overline{V(\bar{\zeta})}V(\zeta')}{\eta(\zeta)\eta^*(\zeta')}$ reproduces the squared modulus of the single-particle survival amplitude $\vert\langle 1 \vert e^{-iHt} \vert 1 \rangle\vert^2$ **identically**:
$$P_{11}(t) = \left\vert A_1 e^{-iz_0 t} + \int_{\Gamma_\theta} \frac{\lambda^2 J(\zeta)}{\eta_+(\zeta)\eta(\zeta)} e^{-i\zeta t} \, d\zeta \right\vert^2. \tag{L22}$$

---

## 7. Stage 2 Status Audit & Readiness for Stage 3

| Stage 2 Component | Mathematical Status | Basis / Verification |
| :--- | :--- | :--- |
| **Rigged Liouville Space $\mathcal{B}_0 \subset \mathcal{B}_- \subset \mathcal{B}_2 \subset \mathcal{B}_-^\times$** | **Established** | Projective tensor product of $\Phi$ and $\overline{\Phi}$; $L\mathcal{B}_0 \subset \mathcal{B}_0$ |
| **Four Generalized Eigenoperator Sectors $F_{\alpha,\beta}, \widetilde{F}_{\alpha,\beta}$** | **Established** | Explicit dyadic functionals (L8a)–(L11b) with $\Gamma_\theta \times \Gamma_\theta^*$ prescriptions |
| **Liouville & Conjugate Dual Spectra (Theorem 2.1)** | **Proved** | Right eigenvalues $\ell_{F_{\alpha,\beta}}$; antidual eigenvalues $\ell_{\widetilde{F}_{\alpha,\beta}} = \overline{\ell_{F_{\alpha,\beta}}}$ |
| **Continuum–Continuum Wedge & Long-Time Tails** | **Proved** | Open wedge $-\pi + \theta < \arg(\ell_{\zeta,\zeta'}) < -\theta$; no uniform gap as $x+x' \downarrow 0$ |
| **Liouville Completeness & Forward Evolution (Theorem 2.2)** | **Proved** | Tensor lift of Stage 1 Theorem 5.2 (Eqs. L14–L15) |
| **Distributional Kernel Biorthogonality (Theorem 2.3)** | **Proved** | Smeared tensor-product distributional kernels $\mathcal{K}_{(\alpha,\beta),(\gamma,\delta)}$ (Eqs. L17–L19) |
| **Exact Four-Sector Decomposition of $\vert 1\rangle\langle 1\vert$** | **Proved** | Exact coefficients (L20a)–(L20d) & survival check (L22) |
| **Prigogine's Transformation $\Lambda^{-1}(L)$** | **Open (Stage 3)** | Not yet constructed; ready to test on the Stage 2 spectral basis |

