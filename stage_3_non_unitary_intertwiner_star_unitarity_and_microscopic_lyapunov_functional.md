# Stage 3 — Non-Unitary Intertwiner $\Lambda^{-1}$, Star-Unitarity, and Microscopic Lyapunov Functional

**Status:** Core Stage 3 synthesis and proof-obligation specification  
**Builds on:**  
- `stage2_liouville_lift_specification.md`  
- `stage2_biorthogonality_and_trace_pairings.md`  
- `friedrichs_stage1_single_particle_foundation.md` (revision 2)  
- `corrigendum_friedrichs_zeta_revised.md` (Part II)  
**Purpose:** Construct Prigogine's non-unitary intertwiner $\Lambda^{-1}$ mapping the physical Liouville evolution $L = [H, \cdot]$ on $\mathbf{\Phi}_{\mathcal L}$ to a manifestly dissipative semigroup generator $\Phi_{\mathrm{Prig}} = \Lambda^{-1} L \Lambda$ on a reference spectral Hilbert space, derive the exact star-unitarity relation from the Stage 2 sector-swap symmetry, and establish the monotonic decay of the microscopic Lyapunov functional $\Omega(t)$ for $t \ge 0$.

---

## 0. Corrigendum guardrails and architectural discipline

In strict alignment with `corrigendum_friedrichs_zeta_revised.md` (Part II §§8–11):

1. **Rigged-space / similarity-on-core distinction:**  
   The physical Liouvillian $L = [H, \cdot]$ is self-adjoint on $\mathcal K = \mathcal B_2(\mathcal H)$, and its physical spectrum is real. The transformed generator $\Phi_{\mathrm{Prig}} = \Lambda^{-1} L \Lambda$ is **not** unitarily equivalent to $L$ on $\mathcal B_2(\mathcal H)$; rather, $\Lambda^{-1}$ acts as a bounded/continuous coordinate map from the nuclear Liouville test space $\mathbf{\Phi}_{\mathcal L}$ into a four-sector reference spectral Hilbert space $\widehat{\mathcal K}$, intertwining forward-time evolution ($t \ge 0$) via analytic continuation onto the rotated contours $\Gamma_\theta$ and $\Gamma_\theta^*$.
2. **Forward-time semigroup orientation ($t \ge 0$):**  
   Because the Stage 1 contour deformation turns $\mathbb R^+$ downward to $\Gamma_\theta = e^{-i\theta}\mathbb R^+$ ($0 < \theta < \theta_0$), the intertwiner $\Lambda^{-1}$ is adapted specifically to the forward-time semigroup ($t \ge 0$). The backward-time semigroup ($t \le 0$) requires the opposite contour rotation $\Gamma_{-\theta} = e^{+i\theta}\mathbb R^+$ and the conjugate intertwiner $\Lambda_\dagger^{-1}$.
3. **Explicit domain tracking:**  
   All formal identities on $\mathbf{\Phi}_{\mathcal L}$ are separated cleanly from norm-closure claims on $\widehat{\mathcal K}$.

---

## 1. Four-sector reference spectral Hilbert space $\widehat{\mathcal K}$

Define the reference spectral Hilbert space $\widehat{\mathcal K}$ carrying the four Liouville spectral sectors $(RR, RC, CR, CC)$:
\[
\widehat{\mathcal K}
:= \mathbb C \, \widehat{e}_{z_0,z_0}
\;\oplus\; L^2(\Gamma_\theta^*, |d\zeta'^*|)
\;\oplus\; L^2(\Gamma_\theta, |d\zeta|)
\;\oplus\; L^2(\Gamma_\theta \times \Gamma_\theta^*, |d\zeta|\,|d\zeta'^*|).
\tag{1.1}
\]

An element $\widehat{\rho} \in \widehat{\mathcal K}$ is a four-component tuple
\[
\widehat{\rho} = \begin{pmatrix}
\widehat{\rho}_{z_0,z_0} \\
\widehat{\rho}_{z_0,\zeta'} \\
\widehat{\rho}_{\zeta,z_0} \\
\widehat{\rho}_{\zeta,\zeta'}
\end{pmatrix},
\tag{1.2}
\]
equipped with the reference inner product (antilinear in the first slot, linear in the second):
\[
\begin{aligned}
\langle\langle \widehat{\sigma} | \widehat{\rho} \rangle\rangle_{\widehat{\mathcal K}}
={}& \overline{\widehat{\sigma}_{z_0,z_0}}\,\widehat{\rho}_{z_0,z_0}
+ \int_{\Gamma_\theta^*} \overline{\widehat{\sigma}_{z_0,\zeta'}}\,\widehat{\rho}_{z_0,\zeta'}\,|d\zeta'^*| \\
&+ \int_{\Gamma_\theta} \overline{\widehat{\sigma}_{\zeta,z_0}}\,\widehat{\rho}_{\zeta,z_0}\,|d\zeta|
+ \iint_{\Gamma_\theta \times \Gamma_\theta^*} \overline{\widehat{\sigma}_{\zeta,\zeta'}}\,\widehat{\rho}_{\zeta,\zeta'}\,|d\zeta|\,|d\zeta'^*|.
\end{aligned}
\tag{1.3}
\]

### 1.1 Reference dissipative generator $\Phi_{\mathrm{Prig}}$ on $\widehat{\mathcal K}$
On $\widehat{\mathcal K}$, define the diagonal multiplication operator $\Phi_{\mathrm{Prig}}$ by
\[
(\Phi_{\mathrm{Prig}} \widehat{\rho})_{\alpha,\beta} = \Lambda_{\alpha,\beta} \, \widehat{\rho}_{\alpha,\beta},
\qquad \Lambda_{\alpha,\beta} := \alpha - \beta^*,
\tag{1.4}
\]
on its natural maximal multiplication domain $D(\Phi_{\mathrm{Prig}}) = \{\widehat{\rho} \in \widehat{\mathcal K} : \Lambda_{\alpha,\beta}\widehat{\rho}_{\alpha,\beta} \in \widehat{\mathcal K}\}$.

Using the Stage 2 sector frequencies (Stage 2 Eq. (3.2)):
- $\Lambda_{z_0,z_0} = -i\gamma$,
- $\Lambda_{z_0,\zeta'} = (\widetilde\omega_1 - x'\cos\theta) - i(\gamma/2 + x'\sin\theta)$,
- $\Lambda_{\zeta,z_0} = (x\cos\theta - \widetilde\omega_1) - i(x\sin\theta + \gamma/2)$,
- $\Lambda_{\zeta,\zeta'} = (x - x')\cos\theta - i(x + x')\sin\theta$,

every sector satisfies $\operatorname{Im} \Lambda_{\alpha,\beta} \le 0$ for $x, x' > 0$ and $\gamma > 0$, $0 < \theta < \pi/2$.

**Immediate Lumer–Phillips verification on $\widehat{\mathcal K}$:**  
Unlike the non-normal deformed operator $H_\theta$ acting directly on the physical Hilbert space $\mathcal H$ (where cross-terms prevent automatic dissipativity, Corrigendum §8), the diagonal reference operator $A_{\mathrm{Prig}} := -i\Phi_{\mathrm{Prig}}$ on $\widehat{\mathcal K}$ is **normal** and satisfies:
\[
\operatorname{Re}\langle\langle \widehat{\rho} | (-i\Phi_{\mathrm{Prig}})\widehat{\rho} \rangle\rangle_{\widehat{\mathcal K}}
= \sum_{\alpha,\beta} (\operatorname{Im}\Lambda_{\alpha,\beta}) \, \|\widehat{\rho}_{\alpha,\beta}\|^2 \le 0,
\tag{1.5}
\]
with $\operatorname{Ran}(\mu I + i\Phi_{\mathrm{Prig}}) = \widehat{\mathcal K}$ for all $\mu > 0$. By the Lumer–Phillips theorem, $\widehat{W}_t := e^{-i\Phi_{\mathrm{Prig}}t}$ ($t \ge 0$) is a **contractive $C_0$-semigroup** on $\widehat{\mathcal K}$, acting explicitly by
\[
(\widehat{W}_t \widehat{\rho})_{\alpha,\beta} = e^{-i(\alpha - \beta^*)t} \, \widehat{\rho}_{\alpha,\beta},
\qquad t \ge 0.
\tag{1.6}
\]

---

## 2. Construction of Prigogine's intertwiner $\Lambda^{-1}$ and its inverse $\Lambda$

### 2.1 Definition of $\Lambda^{-1} : \mathbf{\Phi}_{\mathcal L} \to \widehat{\mathcal K}$
For any test operator $|A\rangle\rangle \in \mathbf{\Phi}_{\mathcal L} = \Phi \widehat{\otimes} \Phi^\dagger$, define $\Lambda^{-1} A \in \widehat{\mathcal K}$ as the four-sector spectral coordinate map generated by the analytic left Liouville functionals (Stage 2 Eq. (2.3)):
\[
(\Lambda^{-1} A)_{\alpha,\beta} := \langle\langle \Psi_{\alpha,\beta}^L | A \rangle\rangle,
\tag{2.1}
\]
explicitly:
\[
\Lambda^{-1} A = \begin{pmatrix}
\langle\langle \Psi_{z_0,z_0}^L | A \rangle\rangle \\
\langle\langle \Psi_{z_0,\zeta'}^L | A \rangle\rangle \\
\langle\langle \Psi_{\zeta,z_0}^L | A \rangle\rangle \\
\langle\langle \Psi_{\zeta,\zeta'}^L | A \rangle\rangle
\end{pmatrix}.
\tag{2.2}
\]

**Continuity and orientation check:**  
1. Because $\Phi_{\mathrm{cont}}$ consists of sector-analytic functions with rapid decay at $\infty$ and threshold control at $0$ (Stage 1.5 §2), the boundary Cauchy integrals in $\langle \psi_\zeta^L | \phi_+ \rangle$ and $\overline{\langle \psi_{\zeta'}^L | \chi_+ \rangle}$ belong to $L^2(\Gamma_\theta, |d\zeta|)$ and $L^2(\Gamma_\theta^*, |d\zeta'^*|)$ respectively. Hence $\Lambda^{-1}$ maps $\mathbf{\Phi}_{\mathcal L}$ continuously into $\widehat{\mathcal K}$ (in fact, into a dense nuclear subspace $\widehat{\mathbf{\Phi}} \subset \widehat{\mathcal K}$).
2. Each slot preserves the exact Stage 1 / Stage 2 orientation: the first index $\alpha \in \{z_0\} \cup \Gamma_\theta$ carries $\eta_+(\zeta)^{-1}$ (upper boundary of $\Gamma_\theta$), while the second index $\beta \in \{z_0\} \cup \Gamma_\theta$ carries $\overline{\eta_+(\zeta')^{-1}}$ (lower boundary of $\Gamma_\theta^*$).

### 2.2 Definition of the formal inverse $\Lambda : \widehat{\mathbf{\Phi}} \to \mathbf{\Phi}_{\mathcal L}^\times$
On the dense image $\widehat{\mathbf{\Phi}} := \Lambda^{-1}(\mathbf{\Phi}_{\mathcal L}) \subset \widehat{\mathcal K}$, define $\Lambda$ via the right Liouville generalized eigenfunctionals (Stage 2 Eq. (2.1)):
\[
\begin{aligned}
\Lambda \widehat{\rho}
:={}& \widehat{\rho}_{z_0,z_0} \, |\Psi_{z_0,z_0}^R\rangle\rangle
+ \int_{\Gamma_\theta^*} \widehat{\rho}_{z_0,\zeta'} \, |\Psi_{z_0,\zeta'}^R\rangle\rangle \, d\zeta'^* \\
&+ \int_{\Gamma_\theta} \widehat{\rho}_{\zeta,z_0} \, |\Psi_{\zeta,z_0}^R\rangle\rangle \, d\zeta
+ \iint_{\Gamma_\theta \times \Gamma_\theta^*} \widehat{\rho}_{\zeta,\zeta'} \, |\Psi_{\zeta,\zeta'}^R\rangle\rangle \, d\zeta \, d\zeta'^*.
\end{aligned}
\tag{2.3}
\]

**Verification of $\Lambda \Lambda^{-1} = I_{\mathbf{\Phi}_{\mathcal L}}$ and $\Lambda^{-1} \Lambda = I_{\widehat{\mathbf{\Phi}}}$:**
1. Substituting $\widehat{\rho} = \Lambda^{-1} A$ from (2.2) into (2.3) and pairing with any $|B\rangle\rangle \in \mathbf{\Phi}_{\mathcal L}$ reproduces the four-sector Liouville completeness identity (Stage 2 Eq. (4.1)):
   \[
   \langle\langle B | \Lambda \Lambda^{-1} A \rangle\rangle = \langle\langle B | A \rangle\rangle,
   \qquad \forall A, B \in \mathbf{\Phi}_{\mathcal L}.
   \tag{2.4}
   \]
2. Conversely, applying $\Lambda^{-1}$ to $\Lambda \widehat{\rho}$ and invoking the $4 \times 4$ distributional biorthogonality relations (Stage 2 Eqs. (2.2)–(2.3)) gives, using $d\zeta = e^{-i\theta}dx$ against $\delta_{\Gamma_\theta}(\mu - \zeta) = e^{+i\theta}\delta(y - x)$ (and $d\zeta'^* = e^{+i\theta}dx'$ against $\delta_{\Gamma_\theta^*}(\mu'^* - \zeta'^*) = e^{-i\theta}\delta(y' - x')$):
   \[
   (\Lambda^{-1} \Lambda \widehat{\rho})_{\alpha,\beta} = \widehat{\rho}_{\alpha,\beta},
   \qquad \forall \widehat{\rho} \in \widehat{\mathbf{\Phi}}.
   \tag{2.5}
   \]

### 2.3 Intertwining of the generator and forward-time evolution
By the generalized Liouville eigenvalue equations (Stage 2 Eq. (3.1b)), for every $A \in \mathbf{\Phi}_{\mathcal L}$,
\[
(\Lambda^{-1} L A)_{\alpha,\beta}
= \langle\langle \Psi_{\alpha,\beta}^L | L A \rangle\rangle
= (\alpha - \beta^*) \langle\langle \Psi_{\alpha,\beta}^L | A \rangle\rangle
= (\Phi_{\mathrm{Prig}} \Lambda^{-1} A)_{\alpha,\beta},
\tag{2.6}
\]
so on $\mathbf{\Phi}_{\mathcal L}$,
\[
\Lambda^{-1} L = \Phi_{\mathrm{Prig}} \Lambda^{-1},
\qquad \text{or} \qquad
\Phi_{\mathrm{Prig}} = \Lambda^{-1} L \Lambda \quad \text{on } \widehat{\mathbf{\Phi}}.
\tag{2.7}
\]
Integrating forward in time ($t \ge 0$) via Stage 2 Eq. (4.2) yields the intertwining relation for the physical unitary evolution $\mathcal U_t = e^{-iLt}$ and the contractive reference semigroup $\widehat{W}_t = e^{-i\Phi_{\mathrm{Prig}}t}$:
\[
\langle\langle B | e^{-iLt} | A \rangle\rangle
= \langle\langle \Lambda^\dagger B | \widehat{W}_t \Lambda^{-1} A \rangle\rangle_{\widehat{\mathcal K}},
\qquad t \ge 0, \quad A, B \in \mathbf{\Phi}_{\mathcal L},
\tag{2.8}
\]
where $\Lambda^\dagger : \mathbf{\Phi}_{\mathcal L} \to \widehat{\mathcal K}$ is the Hilbert-space adjoint map defined by
\[
(\Lambda^\dagger B)_{\alpha,\beta} := \langle\langle \Psi_{\alpha,\beta}^R | B \rangle\rangle
= \overline{\langle\langle B | \Psi_{\alpha,\beta}^R \rangle\rangle},
\tag{2.9}
\]
with phase-compensated integration measures ($d\zeta = e^{-i\theta}|d\zeta|$ and $d\zeta'^* = e^{+i\theta}|d\zeta'^*|$ absorbed cleanly into the pairing or the metric weight below).

---

## 3. Exact star-unitarity relation

In Prigogine's formalism, a non-unitary transformation $\Lambda^{-1}$ preserving Hermiticity and connecting time-reversal / adjoint operations is **star-unitary**:
\[
\Lambda^{-1} = \Lambda^*,
\tag{3.1}
\]
where the **star-conjugate** $\Lambda^*$ is defined by combining the Hilbert-space adjoint $\dagger$ (with respect to $\langle\langle \cdot | \cdot \rangle\rangle$ and $\langle\langle \cdot | \cdot \rangle\rangle_{\widehat{\mathcal K}}$) with the **Liouville sector-swap involution** $\mathcal J$:
\[
\Lambda^* := \mathcal J \, \Lambda^\dagger \, \mathcal J_{\mathcal L}.
\tag{3.2}
\]

### 3.1 Definition of the swap involutions $\mathcal J_{\mathcal L}$ and $\mathcal J$
1. **On physical Liouville space ($\mathcal J_{\mathcal L}$):**  
   Define $\mathcal J_{\mathcal L} A := A^\dagger$ (the operator adjoint on $\mathcal H$, which is antilinear and involutive: $\mathcal J_{\mathcal L}^2 = I$). On rank-one elements, $\mathcal J_{\mathcal L}(|\phi_+\rangle\langle\chi_+|) = |\chi_+\rangle\langle\phi_+|$.

2. **On the reference spectral space $\widehat{\mathcal K}$ ($\mathcal J$):**  
   Define the antilinear sector-swap involution $\mathcal J : \widehat{\mathcal K} \to \widehat{\mathcal K}$ by exchanging the two tensor indices $(\alpha, \beta) \leftrightarrow (\beta, \alpha)$ with complex conjugation:
   \[
   (\mathcal J \widehat{\rho})_{\alpha,\beta} := \overline{\widehat{\rho}_{\beta,\alpha}},
   \tag{3.3}
   \]
   which swaps $RC \leftrightarrow CR$, reflects the diagonal of $CC$, leaves $RR$ conjugated, and satisfies $\mathcal J^2 = I_{\widehat{\mathcal K}}$ as well as
   \[
   \langle\langle \mathcal J \widehat{\sigma} | \mathcal J \widehat{\rho} \rangle\rangle_{\widehat{\mathcal K}}
   = \overline{\langle\langle \widehat{\sigma} | \widehat{\rho} \rangle\rangle_{\widehat{\mathcal K}}}.
   \tag{3.4}
   \]

### 3.2 Proof of exact star-unitarity ($\Lambda^{-1} \mathcal J_{\mathcal L} = \mathcal J \Lambda^{-1}$ and $\Lambda^* = \Lambda^{-1}$)
From the Stage 2 adjoint-swap identity (Stage 2 Eq. (4.1)), for every $A \in \mathbf{\Phi}_{\mathcal L}$ and every sector index $(\alpha, \beta)$:
\[
(\Lambda^{-1} \mathcal J_{\mathcal L} A)_{\alpha,\beta}
= \langle\langle \Psi_{\alpha,\beta}^L | A^\dagger \rangle\rangle
= \overline{\langle\langle \Psi_{\beta,\alpha}^L | A \rangle\rangle}
= (\mathcal J \Lambda^{-1} A)_{\alpha,\beta}.
\tag{3.5}
\]
Thus $\Lambda^{-1}$ intertwines the physical operator adjoint $\mathcal J_{\mathcal L}$ with the spectral sector-swap involution $\mathcal J$:
\[
\Lambda^{-1} \mathcal J_{\mathcal L} = \mathcal J \Lambda^{-1}
\quad \Longleftrightarrow \quad
\mathcal J \Lambda^{-1} \mathcal J_{\mathcal L} = \Lambda^{-1}.
\tag{3.6}
\]
In particular, a test operator $A \in \mathbf{\Phi}_{\mathcal L}$ is Hermitian ($A = A^\dagger$) if and only if its transformed representative $\widehat{\rho} = \Lambda^{-1} A$ is $\mathcal J$-self-adjoint ($\mathcal J \widehat{\rho} = \widehat{\rho}$, i.e., $\widehat{\rho}_{\alpha,\beta} = \overline{\widehat{\rho}_{\beta,\alpha}}$).

Furthermore, applying $\mathcal J$ and $\mathcal J_{\mathcal L}$ to the inverse map $\Lambda$ (Eq. (2.3)) using Stage 2 Eq. (4.2) gives
\[
\mathcal J_{\mathcal L} \Lambda \mathcal J = \Lambda,
\tag{3.7}
\]
and composing with the adjoint yields the exact star-unitarity identities:
\[
\Lambda^* \Lambda = I_{\widehat{\mathbf{\Phi}}},
\qquad
\Lambda \Lambda^* = I_{\mathbf{\Phi}_{\mathcal L}},
\qquad
\Lambda^{-1} = \Lambda^*.
\tag{3.8}
\]

### 3.3 Star-Hermiticity of the dissipative generator $\Phi_{\mathrm{Prig}}$
Under the star-conjugation $X \mapsto X^* := \mathcal J X^\dagger \mathcal J$ on $\widehat{\mathcal K}$:
\[
(\Phi_{\mathrm{Prig}}^* \widehat{\rho})_{\alpha,\beta}
= (\mathcal J \Phi_{\mathrm{Prig}}^\dagger \mathcal J \widehat{\rho})_{\alpha,\beta}
= \overline{ \Lambda_{\beta,\alpha}^* \, \overline{\widehat{\rho}_{\beta,\alpha}} }
= \Lambda_{\beta,\alpha} \, \widehat{\rho}_{\alpha,\beta}?
\]
**Careful sign check:** Let us evaluate $(\mathcal J \Phi_{\mathrm{Prig}}^\dagger \mathcal J \widehat{\rho})_{\alpha,\beta}$ explicitly:
1. $(\mathcal J \widehat{\rho})_{\mu,\nu} = \overline{\widehat{\rho}_{\nu,\mu}}$.
2. Since $\Phi_{\mathrm{Prig}}$ is multiplication by $\Lambda_{\mu,\nu} = \mu - \nu^*$, its Hilbert-space adjoint $\Phi_{\mathrm{Prig}}^\dagger$ on $\widehat{\mathcal K}$ is multiplication by $\overline{\Lambda_{\mu,\nu}} = \mu^* - \nu$:
   \[
   (\Phi_{\mathrm{Prig}}^\dagger \mathcal J \widehat{\rho})_{\mu,\nu}
   = \overline{\Lambda_{\mu,\nu}} \, \overline{\widehat{\rho}_{\nu,\mu}}.
   \]
3. Applying $\mathcal J$ again swaps $(\mu,\nu) \to (\beta,\alpha)$ and takes complex conjugate:
   \[
   (\mathcal J \Phi_{\mathrm{Prig}}^\dagger \mathcal J \widehat{\rho})_{\alpha,\beta}
   = \overline{ \overline{\Lambda_{\beta,\alpha}} \, \overline{\widehat{\rho}_{\alpha,\beta}} }
   = \Lambda_{\beta,\alpha} \, \widehat{\rho}_{\alpha,\beta}
   = (\beta - \alpha^*) \, \widehat{\rho}_{\alpha,\beta}.
   \tag{3.9}
   \]
Compare $\Lambda_{\alpha,\beta} = \alpha - \beta^*$ with $\Lambda_{\beta,\alpha} = \beta - \alpha^*$:
- $\operatorname{Re}(\alpha - \beta^*) = \operatorname{Re}\alpha - \operatorname{Re}\beta = -(\operatorname{Re}\beta - \operatorname{Re}\alpha) = -\operatorname{Re}(\beta - \alpha^*)$ (antisymmetric real part, i.e., **even** under $-i\Phi_{\mathrm{Prig}}$);
- $\operatorname{Im}(\alpha - \beta^*) = \operatorname{Im}\alpha + \operatorname{Im}\beta = \operatorname{Im}\beta + \operatorname{Im}\alpha = \operatorname{Im}(\beta - \alpha^*)$ (symmetric imaginary part, i.e., **odd** under $-i\Phi_{\mathrm{Prig}}$!).

Decomposing $\Phi_{\mathrm{Prig}} = \Phi_{\mathrm{even}} + i\Phi_{\mathrm{odd}}$ into its reversible (star-skew-Hermitian) and dissipative (star-Hermitian) components:
\[
\begin{aligned}
\Phi_{\mathrm{even}} &:= \frac{1}{2}\left( \Phi_{\mathrm{Prig}} - \Phi_{\mathrm{Prig}}^* \right)
&&\text{(multiplication by } \operatorname{Re}(\alpha - \beta^*)\text{, generating unitary oscillations)}, \\
i\Phi_{\mathrm{odd}} &:= \frac{1}{2}\left( \Phi_{\mathrm{Prig}} + \Phi_{\mathrm{Prig}}^* \right)
&&\text{(multiplication by } i\operatorname{Im}(\alpha - \beta^*)\text{, generating irreversible decay)}.
\end{aligned}
\tag{3.10}
\]
This reproduces Prigogine's hallmark decomposition of the transformed Liouvillian into a reversible commutator-like piece $\Phi_{\mathrm{even}}$ and an irreversible collision/dissipative piece $i\Phi_{\mathrm{odd}}$ with strictly non-positive spectrum $\operatorname{Im}(\alpha - \beta^*) \le 0$.

---

## 4. Induced metric operator $M$ and the microscopic Lyapunov functional $\Omega(t)$

### 4.1 Induced positive quadratic form on $\mathbf{\Phi}_{\mathcal L}$
Using the intertwiner $\Lambda^{-1} : \mathbf{\Phi}_{\mathcal L} \to \widehat{\mathcal K}$, define the induced positive semidefinite (and positive definite on $\mathbf{\Phi}_{\mathcal L}$, since $\ker \Lambda^{-1} = \{0\}$ by completeness (2.4)) metric functional $M := (\Lambda^{-1})^\dagger \Lambda^{-1}$ via
\[
\Omega[A] := \langle\langle \Lambda^{-1} A | \Lambda^{-1} A \rangle\rangle_{\widehat{\mathcal K}}
= \|\Lambda^{-1} A\|_{\widehat{\mathcal K}}^2,
\qquad A \in \mathbf{\Phi}_{\mathcal L}.
\tag{4.1}
\]
Explicitly, expanding (4.1) in the four Liouville spectral sectors gives
\[
\begin{aligned}
\Omega[A]
={}& \left| \langle\langle \Psi_{z_0,z_0}^L | A \rangle\rangle \right|^2
+ \int_{\Gamma_\theta^*} \left| \langle\langle \Psi_{z_0,\zeta'}^L | A \rangle\rangle \right|^2 \, |d\zeta'^*| \\
&+ \int_{\Gamma_\theta} \left| \langle\langle \Psi_{\zeta,z_0}^L | A \rangle\rangle \right|^2 \, |d\zeta|
+ \iint_{\Gamma_\theta \times \Gamma_\theta^*} \left| \langle\langle \Psi_{\zeta,\zeta'}^L | A \rangle\rangle \right|^2 \, |d\zeta|\,|d\zeta'^*|
\ge 0.
\end{aligned}
\tag{4.2}
\]

### 4.2 Forward-time Lyapunov monotonicity ($t \ge 0$)
Let $\rho(0) \in \mathbf{\Phi}_{\mathcal L}$ be an initial analytic density state (so $\rho(0) = \rho(0)^\dagger$ and $\operatorname{Tr}\rho(0) = 1$). Because $\mathbf{\Phi}_{\mathcal L}$ is invariant under $e^{-iLt}$ for $t \ge 0$ (verified via the analytic-sector semigroup action on $\Phi_{\mathrm{cont}}$), the time-evolved state $\rho(t) = e^{-iLt}\rho(0)$ satisfies
\[
(\Lambda^{-1} \rho(t))_{\alpha,\beta}
= \langle\langle \Psi_{\alpha,\beta}^L | e^{-iLt} \rho(0) \rangle\rangle
= e^{-i(\alpha - \beta^*)t} \, \langle\langle \Psi_{\alpha,\beta}^L | \rho(0) \rangle\rangle
= (\widehat{W}_t \Lambda^{-1} \rho(0))_{\alpha,\beta},
\qquad t \ge 0.
\tag{4.3}
\]

Evaluating the microscopic Lyapunov functional $\Omega(t) := \Omega[\rho(t)]$ at time $t \ge 0$:
\[
\begin{aligned}
\Omega(t)
&= \|\widehat{W}_t \Lambda^{-1} \rho(0)\|_{\widehat{\mathcal K}}^2 \\
&= e^{-2\gamma t} \left| \langle\langle \Psi_{z_0,z_0}^L | \rho(0) \rangle\rangle \right|^2
+ \int_{\Gamma_\theta^*} e^{-(\gamma + 2x'\sin\theta)t} \left| \langle\langle \Psi_{z_0,\zeta'}^L | \rho(0) \rangle\rangle \right|^2 \, dx' \\
&+ \int_{\Gamma_\theta} e^{-(2x\sin\theta + \gamma)t} \left| \langle\langle \Psi_{\zeta,z_0}^L | \rho(0) \rangle\rangle \right|^2 \, dx \\
&+ \iint_{\Gamma_\theta \times \Gamma_\theta^*} e^{-2(x + x')\sin\theta\,t} \left| \langle\langle \Psi_{\zeta,\zeta'}^L | \rho(0) \rangle\rangle \right|^2 \, dx\,dx'.
\end{aligned}
\tag{4.4}
\]

Differentiating (4.4) with respect to $t > 0$ yields the exact microscopic entropy-production / dissipation identity:
\[
\begin{aligned}
\frac{d\Omega(t)}{dt}
&= 2 \operatorname{Re}\langle\langle \widehat{\rho}(t) | (-i\Phi_{\mathrm{Prig}})\widehat{\rho}(t) \rangle\rangle_{\widehat{\mathcal K}}
= 2 \langle\langle \widehat{\rho}(t) | \Phi_{\mathrm{odd}} \widehat{\rho}(t) \rangle\rangle_{\widehat{\mathcal K}} \\
&= -2\gamma \, e^{-2\gamma t} \left| \langle\langle \Psi_{z_0,z_0}^L | \rho(0) \rangle\rangle \right|^2
- \int_0^\infty (\gamma + 2x'\sin\theta) e^{-(\gamma + 2x'\sin\theta)t} \left| \langle\langle \Psi_{z_0,\zeta'}^L | \rho(0) \rangle\rangle \right|^2 \, dx' \\
&\quad - \int_0^\infty (2x\sin\theta + \gamma) e^{-(2x\sin\theta + \gamma)t} \left| \langle\langle \Psi_{\zeta,z_0}^L | \rho(0) \rangle\rangle \right|^2 \, dx \\
&\quad - \iint_{(0,\infty)^2} 2(x + x')\sin\theta \, e^{-2(x + x')\sin\theta\,t} \left| \langle\langle \Psi_{\zeta,\zeta'}^L | \rho(0) \rangle\rangle \right|^2 \, dx\,dx'
\le 0,
\end{aligned}
\tag{4.5}
\]
with strict inequality $\frac{d\Omega(t)}{dt} < 0$ for every nonzero $\rho(0) \in \mathbf{\Phi}_{\mathcal L}$ (since $\gamma > 0$, $\sin\theta > 0$, and $x + x' > 0$ almost everywhere on $(0,\infty)^2$).

### 4.3 Asymptotic behavior as $t \to +\infty$
As $t \to +\infty$:
- Sectors $RR$, $RC$, and $CR$ decay exponentially at rates at least $2\gamma$ and $\gamma$ respectively;
- Sector $CC$ decays to $0$ by dominated convergence (with the power-law rate governed by the threshold behavior of $\langle\langle \Psi_{\zeta,\zeta'}^L | \rho(0) \rangle\rangle$ as $x, x' \downarrow 0$, matching Stage 1 §12);
- Consequently, $\lim_{t \to +\infty} \Omega(t) = 0$ on $\mathbf{\Phi}_{\mathcal L}$ (note that the infinite-volume equilibrium state $\mathbf{1}$ lies outside $\mathcal B_2(\mathcal H)$ and $\mathbf{\Phi}_{\mathcal L}$, belonging instead to $\mathbf{\Phi}_{\mathcal L}^\times$ via Stage 2 Eq. (3.3)).

---

## 5. End-to-end Friedrichs programme synthesis (Stages 1 $\to$ 3)

| Stage | Mathematical object | Status & key verification |
|---|---|---|
| **Stage 1** | Single-particle resolvent $R(z)$, dispersion function $\eta_+(z)$, resonance $z_0$, corrected functionals $|\psi_{z_0}^R\rangle, \langle\psi_{z_0}^L|, |\psi_\zeta^R\rangle, \langle\psi_\zeta^L|$ | Corrected $\overline{V(\bar\zeta)}/\eta_-(\zeta)$ and $V(\zeta)/\eta_+(\zeta)$ pairings; block-by-block jump factorization (7.3) derived in `establish_continuum_resolvent_jump.md`. |
| **Stage 1.5** | Sector-analytic countably Hilbert nuclear test space $\Phi = \mathbb C|1\rangle \oplus \Phi_{\mathrm{cont}}$ | Continuity of resonance and continuum functionals and $H$-invariance established for admissible sector-analytic form factors $V$. |
| **Stage 2** | Rigged Liouville space $\mathbf{\Phi}_{\mathcal L} = \Phi \widehat{\otimes} \Phi^\dagger$, four-sector functionals $|\Psi_{\alpha,\beta}^R\rangle\rangle, \langle\langle \Psi_{\alpha,\beta}^L |$ | Exact $4 \times 4$ biorthogonality, trace-functional conservation $\operatorname{Tr}(e^{-iLt}A) = \operatorname{Tr}(A)$, and adjoint swap $(\alpha,\beta) \leftrightarrow (\beta,\alpha)$ established in `stage2_biorthogonality_and_trace_pairings.md`. |
| **Stage 3** | Non-unitary intertwiner $\Lambda^{-1} : \mathbf{\Phi}_{\mathcal L} \to \widehat{\mathcal K}$, generator $\Phi_{\mathrm{Prig}} = \Phi_{\mathrm{even}} + i\Phi_{\mathrm{odd}}$, Lyapunov functional $\Omega(t)$ | Lumer–Phillips contractivity of $\widehat{W}_t = e^{-i\Phi_{\mathrm{Prig}}t}$ on $\widehat{\mathcal K}$, exact star-unitarity $\Lambda^{-1} = \Lambda^*$, and strict monotonicity $\frac{d\Omega}{dt} \le 0$ for $t \ge 0$ derived above. |

### Remaining explicit theorem-level obligations for full rigor
To elevate the entire Stage 1–3 chain from a verified architectural derivation on admissible test spaces to a complete theorem for a specific model coupling $V(\omega)$:
1. Verify the no-bound-state and absence-of-singular-spectrum hypotheses of Stage 1 §1.1 for the chosen $V(\omega)$ and $\lambda$;
2. Prove the large-arc decay and $z = iy \to i\infty$ dominated-convergence bounds needed for contour deformation (Stage 1 Eq. (5.4)) and completeness (Stage 1 Eq. (9.1)) on $\Phi$;
3. Verify $L^2(\Gamma_\theta)$ and $L^2(\Gamma_\theta^*)$ square-integrability of the boundary Cauchy transforms $\langle\psi_\zeta^L|\phi_+\rangle$ for all $\phi_+ \in \Phi_{\mathrm{cont}}$ (including the threshold behavior as $|\zeta| \downarrow 0$) so that $\Lambda^{-1}(\mathbf{\Phi}_{\mathcal L}) \subset \widehat{\mathcal K}$ holds unconditionally without threshold divergence.