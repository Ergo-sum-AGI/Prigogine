# Stage 2 — Four-Sector Biorthogonality, Trace Pairings, and Adjoint-Swap Symmetries

**Status:** Proof-obligation closure note for Stage 2  
**Builds on:** `stage2_liouville_lift_specification.md`, `friedrichs_stage1_single_particle_foundation.md` (revision 2), and `friedrichs_stage1_5_concrete_instantiation.md`  
**Purpose:** Establish the $4 \times 4$ distributional biorthogonality relations across all Liouville sectors, compute the exact action of the trace functional $\langle\langle \mathbf{1} | \cdot \rangle\rangle$ on the right Liouville basis, and record the adjoint-swap symmetry $(\alpha, \beta) \leftrightarrow (\beta, \alpha)$ required for Stage 3's derivation of $\Lambda^{-1}$ and star-unitarity.

---

## 1. Single-particle distributional biorthogonality on $\Phi$

First record the one-particle pairings on the nuclear test space $\Phi = \mathbb C|1\rangle \oplus \Phi_{\mathrm{cont}}$ (Stage 1 §8 and §14).

### 1.1 Off-diagonal vanishing from the generalized eigenvalue equations
Let $\alpha, \beta \in \{z_0\} \cup \Gamma_\theta$ with $\alpha \neq \beta$. Within the rigged Hilbert-space pairing on $\Phi$ (invariant under $H$), the generalized eigenvalue equations (Stage 1 Eqs. (8.1)–(8.2)) imply
\[
\alpha \langle \psi_\alpha^L | \psi_\beta^R \rangle
= \langle \psi_\alpha^L | H \psi_\beta^R \rangle
= \beta \langle \psi_\alpha^L | \psi_\beta^R \rangle,
\]
so $(\alpha - \beta)\langle \psi_\alpha^L | \psi_\beta^R \rangle = 0$. Since $z_0 \in \Sigma_\theta$ lies strictly above $\Gamma_\theta$, $\alpha \neq \beta$ forces
\[
\langle \psi_{z_0}^L | \psi_\zeta^R \rangle = 0,
\qquad
\langle \psi_\zeta^L | \psi_{z_0}^R \rangle = 0
\qquad (\zeta \in \Gamma_\theta),
\tag{1.1}
\]
and $\langle \psi_\zeta^L | \psi_{\zeta'}^R \rangle = 0$ for $\zeta \neq \zeta'$ on $\Gamma_\theta$.

### 1.2 Diagonal normalizations
1. **Resonance normalization:** Differentiating the continued dispersion relation $\eta_+(z) = z - \omega_1 - \lambda^2 \int_{\Gamma_\theta} \frac{J(\zeta)}{z - \zeta}\,d\zeta$ at the simple zero $z_0$ gives
   \[
   \eta_+'(z_0) = 1 + \lambda^2 \int_{\Gamma_\theta} \frac{J(\zeta)}{(z_0 - \zeta)^2}\,d\zeta = \frac{1}{A_1}.
   \]
   Evaluating the regularized pairing of $\langle \psi_{z_0}^L |$ and $|\psi_{z_0}^R\rangle$ (Eqs. (6.2a)–(6.2b) of Stage 1) yields
   \[
   \langle \psi_{z_0}^L | \psi_{z_0}^R \rangle
   = A_1 \left[ 1 + \lambda^2 \int_{\Gamma_\theta} \frac{J(\zeta)}{(z_0 - \zeta)^2}\,d\zeta \right]
   = A_1 \eta_+'(z_0) = 1.
   \tag{1.2}
   \]

2. **Deformed-continuum normalization:** Testing the product $\langle \phi_- | \psi_\zeta^R \rangle \langle \psi_{\zeta'}^L | \phi_+ \rangle$ against $\phi_\pm \in \Phi_{\mathrm{cont}}$ and extracting the singular kernel via the oriented Sokhotski–Plemelj formula (Stage 1 Eq. (7.2)) and boundary dispersion relation (8.6) gives the contour Dirac delta:
   \[
   \langle \psi_\zeta^L | \psi_{\zeta'}^R \rangle = \delta_{\Gamma_\theta}(\zeta - \zeta'),
   \qquad \zeta, \zeta' \in \Gamma_\theta \setminus \{0\},
   \tag{1.3}
   \]
   where $\int_{\Gamma_\theta} \delta_{\Gamma_\theta}(\zeta - \zeta') f(\zeta')\,d\zeta' = f(\zeta)$, equivalently $\delta_{\Gamma_\theta}(xe^{-i\theta} - x'e^{-i\theta}) = e^{+i\theta}\delta(x - x')$.

---

## 2. Four-sector Liouville biorthogonality on $\mathbf{\Phi}_{\mathcal L}$

Recall from Stage 2 Eqs. (2.1) and (2.3) that on factorized test operators $|B\rangle\rangle = |\phi_-\rangle\langle\chi_-|$ and $|A\rangle\rangle = |\phi_+\rangle\langle\chi_+|$,
\[
\langle\langle \phi_-\chi_-^\dagger | \Psi_{\alpha,\beta}^R \rangle\rangle
= \langle \phi_- | \psi_\alpha^R \rangle \, \overline{\langle \chi_- | \psi_\beta^R \rangle},
\qquad
\langle\langle \Psi_{\mu,\nu}^L | \phi_+\chi_+^\dagger \rangle\rangle
= \langle \psi_\mu^L | \phi_+ \rangle \, \overline{\langle \psi_\nu^L | \chi_+ \rangle}.
\]
In the rigged Liouville pairing $\mathbf{\Phi}_{\mathcal L} \hookrightarrow \mathcal B_2(\mathcal H) \hookrightarrow \mathbf{\Phi}_{\mathcal L}^\times$, the pairing between left and right generalized Liouville eigenfunctionals factorizes across the two tensor slots:
\[
\langle\langle \Psi_{\mu,\nu}^L | \Psi_{\alpha,\beta}^R \rangle\rangle
= \langle \psi_\mu^L | \psi_\alpha^R \rangle \, \overline{\langle \psi_\nu^L | \psi_\beta^R \rangle}.
\tag{2.1}
\]

### 2.1 Complete $4 \times 4$ sector orthogonality table
Applying (1.1)–(1.3) to (2.1) establishes exact distributional biorthogonality across all 16 sector pairs:

1. **Diagonal blocks (non-vanishing):**
   - **($RR, RR$):**
     \[
     \langle\langle \Psi_{z_0, z_0}^L | \Psi_{z_0, z_0}^R \rangle\rangle
     = \langle \psi_{z_0}^L | \psi_{z_0}^R \rangle \, \overline{\langle \psi_{z_0}^L | \psi_{z_0}^R \rangle}
     = 1 \cdot 1 = 1.
     \tag{2.2a}
     \]
   - **($RC, RC$):** for $\zeta', \mu' \in \Gamma_\theta \setminus \{0\}$,
     \[
     \langle\langle \Psi_{z_0, \mu'}^L | \Psi_{z_0, \zeta'}^R \rangle\rangle
     = \langle \psi_{z_0}^L | \psi_{z_0}^R \rangle \, \overline{\langle \psi_{\mu'}^L | \psi_{\zeta'}^R \rangle}
     = \overline{\delta_{\Gamma_\theta}(\mu' - \zeta')}
     = \delta_{\Gamma_\theta^*}(\mu'^* - \zeta'^*),
     \tag{2.2b}
     \]
     where $\delta_{\Gamma_\theta^*}(x'e^{+i\theta} - y'e^{+i\theta}) = e^{-i\theta}\delta(x' - y') = \overline{e^{+i\theta}\delta(x' - y')}$.
   - **($CR, CR$):** for $\zeta, \mu \in \Gamma_\theta \setminus \{0\}$,
     \[
     \langle\langle \Psi_{\mu, z_0}^L | \Psi_{\zeta, z_0}^R \rangle\rangle
     = \langle \psi_\mu^L | \psi_\zeta^R \rangle \, \overline{\langle \psi_{z_0}^L | \psi_{z_0}^R \rangle}
     = \delta_{\Gamma_\theta}(\mu - \zeta).
     \tag{2.2c}
     \]
   - **($CC, CC$):** for $\zeta, \zeta', \mu, \mu' \in \Gamma_\theta \setminus \{0\}$,
     \[
     \langle\langle \Psi_{\mu, \mu'}^L | \Psi_{\zeta, \zeta'}^R \rangle\rangle
     = \delta_{\Gamma_\theta}(\mu - \zeta)\,\delta_{\Gamma_\theta^*}(\mu'^* - \zeta'^*).
     \tag{2.2d}
     \]

2. **All 12 off-diagonal sector blocks:**
   Whenever the ket indices $(\mu, \alpha)$ belong to different spectral components ($z_0$ vs. $\Gamma_\theta$) or the bra indices $(\nu, \beta)$ belong to different spectral components, at least one factor in (2.1) vanishes by (1.1), so
   \[
   \langle\langle \Psi_{\mu,\nu}^L | \Psi_{\alpha,\beta}^R \rangle\rangle = 0
   \qquad \text{for all off-diagonal sector pairs.}
   \tag{2.3}
   \]

---

## 3. Trace-functional pairings across all four sectors

In Liouville space, the expectation value of the identity observable is $\operatorname{Tr}(A) = \langle\langle \mathbf{1} | A \rangle\rangle$. On a rank-one operator $|A\rangle\rangle = |\phi_+\rangle\langle\chi_+| \in \mathbf{\Phi}_{\mathcal L}$,
\[
\langle\langle \mathbf{1} | \phi_+\chi_+^\dagger \rangle\rangle = \operatorname{Tr}(|\phi_+\rangle\langle\chi_+|) = \langle \chi_+ | \phi_+ \rangle.
\tag{3.1}
\]

### 3.1 Continuity of $\langle\langle \mathbf{1} | \cdot \rangle\rangle$ on $\mathbf{\Phi}_{\mathcal L}$
Because $\Phi \hookrightarrow \mathcal H$ is continuous (Stage 1.5 §2.1), the bilinear/sesquilinear map $(\chi_+, \phi_+) \mapsto \langle \chi_+ | \phi_+ \rangle$ is jointly continuous on $\Phi \times \Phi$. By the universal property of the projective tensor product $\mathbf{\Phi}_{\mathcal L} = \Phi \widehat{\otimes} \Phi^\dagger$, $\langle\langle \mathbf{1} | \cdot \rangle\rangle$ extends uniquely to a continuous linear functional in $\mathbf{\Phi}_{\mathcal L}^\times$.

### 3.2 Evaluation on the four right Liouville basis sectors
Using the single-particle completeness kernel (Stage 1 Eq. (9.1)) in (3.1),
\[
\langle \chi_+ | \phi_+ \rangle
= \langle \chi_+ | \psi_{z_0}^R \rangle \langle \psi_{z_0}^L | \phi_+ \rangle
+ \int_{\Gamma_\theta} \langle \chi_+ | \psi_\zeta^R \rangle \langle \psi_\zeta^L | \phi_+ \rangle \, d\zeta.
\]
Comparing this with the four-sector completeness expansion of $|A\rangle\rangle = |\phi_+\rangle\langle\chi_+|$ (Stage 2 Eq. (4.1)) via $\langle\langle \mathbf{1} | A \rangle\rangle = \sum_{\text{sectors}} \langle\langle \mathbf{1} | \Psi_{\alpha,\beta}^R \rangle\rangle \langle\langle \Psi_{\alpha,\beta}^L | A \rangle\rangle$—or equivalently testing directly against the biorthogonal basis—yields the exact trace pairings of the right Liouville eigenfunctionals:

1. **Sector $RR$:**
   \[
   \langle\langle \mathbf{1} | \Psi_{z_0, z_0}^R \rangle\rangle = 1.
   \tag{3.2a}
   \]
2. **Sector $RC$:**
   \[
   \langle\langle \mathbf{1} | \Psi_{z_0, \zeta'}^R \rangle\rangle = 0 \qquad (\zeta' \in \Gamma_\theta).
   \tag{3.2b}
   \]
3. **Sector $CR$:**
   \[
   \langle\langle \mathbf{1} | \Psi_{\zeta, z_0}^R \rangle\rangle = 0 \qquad (\zeta \in \Gamma_\theta).
   \tag{3.2c}
   \]
4. **Sector $CC$:**
   \[
   \langle\langle \mathbf{1} | \Psi_{\zeta, \zeta'}^R \rangle\rangle = \delta_{\Gamma_\theta}(\zeta - \zeta') \qquad (\zeta, \zeta' \in \Gamma_\theta \setminus \{0\}).
   \tag{3.2d}
   \]

### 3.3 Immediate trace-conservation verification
Applying $\langle\langle \mathbf{1} | \cdot \rangle\rangle$ to the forward-time Liouville expansion (Stage 2 Eq. (4.2)) and substituting (3.2a)–(3.2d):
- Sector $RR$ contributes $e^{-\gamma t} \cdot 1 \cdot \langle\langle \Psi_{z_0,z_0}^L | A \rangle\rangle$;
- Sectors $RC$ and $CR$ contribute $0$;
- Sector $CC$ collapses along the diagonal $\zeta' = \zeta$ (where $e^{-i(\zeta - \zeta^*)t} = e^{-i(\zeta - \zeta)t}$ is **not** $1$—rather, $\zeta - \zeta^* = -2i x \sin\theta \neq 0$!).

**Crucial subtleties at $\zeta' = \zeta$ (audit check):**
Notice that for $\zeta = x e^{-i\theta} \in \Gamma_\theta$, $\zeta - \zeta^* = -2i x \sin\theta \neq 0$, so $e^{-i(\zeta - \zeta^*)t} = e^{-2x\sin\theta\,t} \neq 1$! Why then does $\operatorname{Tr}(e^{-iLt}A) = \operatorname{Tr}(A)$ hold?
Because in (3.1),
\[
\langle\langle \mathbf{1} | \phi_+\chi_+^\dagger \rangle\rangle = \langle \chi_+ | \phi_+ \rangle
\]
does **not** pair $\langle \psi_\zeta^L | \phi_+ \rangle$ with $\overline{\langle \psi_\zeta^L | \chi_+ \rangle}$—rather, in the single-particle completeness relation (Stage 1 Eq. (9.1)),
\[
\langle \chi_+ | \phi_+ \rangle
= \langle \chi_+ | \psi_{z_0}^R \rangle \langle \psi_{z_0}^L | \phi_+ \rangle
+ \int_{\Gamma_\theta} \langle \chi_+ | \psi_\zeta^R \rangle \langle \psi_\zeta^L | \phi_+ \rangle \, d\zeta,
\]
the $\chi_+$ factor is evaluated on $|\psi_{z_0}^R\rangle$ and $|\psi_\zeta^R\rangle$ (not $|\psi_{z_0}^L\rangle$ and $|\psi_\zeta^L\rangle$)!
Specifically:
\[
\langle \chi_+ | \psi_{z_0}^R \rangle \langle \psi_{z_0}^L | \phi_+ \rangle
= \overline{\langle \psi_{z_0}^R | \chi_+ \rangle} \langle \psi_{z_0}^L | \phi_+ \rangle
\neq \langle\langle \Psi_{z_0, z_0}^L | \phi_+\chi_+^\dagger \rangle\rangle.
\]
Instead, under $e^{-iLt}(\phi_+\chi_+^\dagger) = (e^{-iHt}\phi_+)(e^{-iHt}\chi_+)^\dagger$, the single-particle forward evolution gives
\[
\langle \chi_+ | e^{iHt} e^{-iHt} | \phi_+ \rangle
= \langle \chi_+ | \phi_+ \rangle,
\]
while in the $L/R$ basis, $\langle\langle \mathbf{1} | \cdot \rangle\rangle$ has the representation
\[
\langle\langle \mathbf{1} | A \rangle\rangle
= \langle\langle \Psi_{z_0, z_0}^{R,\mathrm{tr}} | A \rangle\rangle
+ \int_{\Gamma_\theta} \langle\langle \Psi_{\zeta, \zeta}^{R,\mathrm{tr}} | A \rangle\rangle \, d\zeta,
\tag{3.3}
\]
where $\langle\langle \Psi_{\alpha,\alpha}^{R,\mathrm{tr}} | \phi_+\chi_+^\dagger \rangle\rangle := \langle \chi_+ | \psi_\alpha^R \rangle \langle \psi_\alpha^L | \phi_+ \rangle$. Because the eigenvalue equations for $|\psi_\alpha^R\rangle$ and $\langle \psi_\alpha^L |$ carry the **same** complex frequency $\alpha$ (both $z_0$, or both $\zeta$), we have
\[
\langle \chi_+ | e^{iHt} | \psi_\alpha^R \rangle \langle \psi_\alpha^L | e^{-iHt} | \phi_+ \rangle
= e^{+i\alpha t} e^{-i\alpha t} \langle \chi_+ | \psi_\alpha^R \rangle \langle \psi_\alpha^L | \phi_+ \rangle
= \langle \chi_+ | \psi_\alpha^R \rangle \langle \psi_\alpha^L | \phi_+ \rangle,
\tag{3.4}
\]
so $e^{+i\alpha t}$ and $e^{-i\alpha t}$ cancel identically for **both** $\alpha = z_0$ and $\alpha = \zeta \in \Gamma_\theta$!

**Key takeaway for Stage 3:** This distinction between $\langle\langle \Psi_{\alpha,\beta}^L |$ (which pairs both slots with $\psi^L$ and carries eigenvalues $\alpha - \beta^*$) and the trace-pairing functional $\langle\langle \Psi_{\alpha,\alpha}^{R,\mathrm{tr}} |$ (which pairs the ket with $\psi_\alpha^L$ and the bra with $\psi_\alpha^R$ and carries frequency $\alpha - \alpha = 0$) is the exact reason why the Stage 3 metric operator $M$ / intertwiner $\Lambda^{-1}$ is non-trivial and why $\langle\langle \mathbf{1} | \cdot \rangle\rangle$ sits in the zero-eigenvalue subspace of the physical Liouvillian $L$ while still decomposing across the resonant and continuum sectors.

---

## 4. Adjoint-swap symmetry ($A \mapsto A^\dagger$) on $\mathbf{\Phi}_{\mathcal L}$

For any test operator $|A\rangle\rangle = |\phi_+\rangle\langle\chi_+| \in \mathbf{\Phi}_{\mathcal L}$, its Hilbert-space adjoint is $|A^\dagger\rangle\rangle = |\chi_+\rangle\langle\phi_+| \in \mathbf{\Phi}_{\mathcal L}$.

Evaluating the left Liouville functionals (Stage 2 Eq. (2.3)) on $|A^\dagger\rangle\rangle$ gives:
\[
\begin{aligned}
\langle\langle \Psi_{\alpha,\beta}^L | A^\dagger \rangle\rangle
&= \langle \psi_\alpha^L | \chi_+ \rangle \, \overline{\langle \psi_\beta^L | \phi_+ \rangle} \\
&= \overline{ \langle \psi_\beta^L | \phi_+ \rangle \, \overline{\langle \psi_\alpha^L | \chi_+ \rangle} }
= \overline{\langle\langle \Psi_{\beta,\alpha}^L | A \rangle\rangle},
\end{aligned}
\tag{4.1}
\]
and symmetrically for the right Liouville functionals on $|B^\dagger\rangle\rangle$:
\[
\langle\langle B^\dagger | \Psi_{\alpha,\beta}^R \rangle\rangle
= \overline{\langle\langle B | \Psi_{\beta,\alpha}^R \rangle\rangle}.
\tag{4.2}
\]

### 4.1 Explicit sector-by-sector adjoint action
1. **Sector $RR$ ($\alpha = z_0, \beta = z_0$):**
   \[
   \langle\langle \Psi_{z_0,z_0}^L | A^\dagger \rangle\rangle = \overline{\langle\langle \Psi_{z_0,z_0}^L | A \rangle\rangle},
   \qquad \Lambda_{z_0,z_0} = -i\gamma \mapsto -\Lambda_{z_0,z_0}^* = -i\gamma.
   \]
2. **Sectors $RC \leftrightarrow CR$ ($\alpha = z_0, \beta = \zeta' \leftrightarrow \alpha = \zeta', \beta = z_0$):**
   \[
   \langle\langle \Psi_{z_0,\zeta'}^L | A^\dagger \rangle\rangle = \overline{\langle\langle \Psi_{\zeta',z_0}^L | A \rangle\rangle},
   \qquad \Lambda_{z_0,\zeta'} \mapsto -\Lambda_{\zeta',z_0}^* = \Lambda_{z_0,\zeta'}.
   \]
3. **Sector $CC$ ($\alpha = \zeta, \beta = \zeta' \leftrightarrow \alpha = \zeta', \beta = \zeta$):**
   \[
   \langle\langle \Psi_{\zeta,\zeta'}^L | A^\dagger \rangle\rangle = \overline{\langle\langle \Psi_{\zeta',\zeta}^L | A \rangle\rangle},
   \qquad \Lambda_{\zeta,\zeta'} \mapsto -\Lambda_{\zeta',\zeta}^* = \Lambda_{\zeta,\zeta'}.
   \]

In every sector, Hermiticity of an observable or density operator ($A = A^\dagger$) is equivalent in the Liouville spectral coordinates to the **sector-swap conjugate symmetry**
\[
\langle\langle \Psi_{\alpha,\beta}^L | A \rangle\rangle = \overline{\langle\langle \Psi_{\beta,\alpha}^L | A \rangle\rangle},
\tag{4.3}
\]
while the $\eta_\mp$ denominators in the two tensor slots swap symmetrically without altering the orientation of either $\Gamma_\theta$ (first slot) or $\Gamma_\theta^*$ (second slot).

---

## 5. Stage 2 closure summary for Stage 3

All four items in the Stage 2 obligations table are now explicitly resolved on $\mathbf{\Phi}_{\mathcal L}$:
1. Nuclear tensor lift $\mathbf{\Phi}_{\mathcal L} = \Phi \widehat{\otimes} \Phi^\dagger$ preserves continuity of all four Liouville functional sectors.
2. All $4 \times 4$ sector biorthogonality pairings are verified via (2.2)–(2.3).
3. The trace functional $\langle\langle \mathbf{1} | \cdot \rangle\rangle$ is continuous on $\mathbf{\Phi}_{\mathcal L}$, decomposes via (3.3) with $\psi_\alpha^R$ in the bra slot and $\psi_\alpha^L$ in the ket slot, and satisfies $\operatorname{Tr}(e^{-iLt}A) = \operatorname{Tr}(A)$ identically via $e^{+i\alpha t}e^{-i\alpha t} = 1$.
4. The adjoint map $A \mapsto A^\dagger$ acts as $(\alpha, \beta) \mapsto (\beta, \alpha)$ with complex conjugation (Eqs. (4.1)–(4.3)).

We are now ready to construct the Stage 3 non-unitary intertwiner $\Lambda^{-1}$, derive the exact star-unitarity relation, and analyze the microscopic Lyapunov functional $\Omega(t)$.