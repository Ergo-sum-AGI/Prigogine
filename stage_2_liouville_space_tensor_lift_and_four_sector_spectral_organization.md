# Stage 2 — Liouville-Space Tensor Lift and Four-Sector Spectral Organization

**Status:** Reconstructed foundation and proof-obligation specification (Stage 1 / 1.5 $\to$ Stage 2)  
**Builds on:**  
- `friedrichs_stage1_single_particle_foundation.md` (revision 2)  
- `friedrichs_stage1_5_concrete_instantiation.md`  
- `establish_continuum_resolvent_jump.md`  
- `corrigendum_friedrichs_zeta_revised.md` (Part II)  
**Purpose:** Lift the corrected single-particle resonance and deformed-continuum functionals to the rigged Liouville space, establish the four-sector spectral decomposition (resonance–resonance, resonance–continuum, continuum–resonance, continuum–continuum), and isolate the exact domain and analytic-continuation conditions required before Stage 3's Prigogine transformation $\Lambda^{-1}$.

---

## 0. Corrigendum guardrails and orientation lock-in

To maintain strict mathematical discipline in the transition from single-particle vectors to density operators, Stage 2 enforces three structural guardrails:

1. **Orientation lock-in ($\eta_\mp$ and $\Gamma_\theta^*$):**  
   In Stage 1 (Eqs. (7.4a)–(7.4b)), on the forward-rotated ray $\Gamma_\theta = e^{-i\theta}\mathbb R^+$, the right functional $\langle \phi_- | \psi_\zeta^R \rangle$ carries $\overline{V(\bar\zeta)}/\eta_-(\zeta)$ (lower ray boundary value $-i0_\theta$), while the left functional $\langle \psi_\zeta^L | \phi_+ \rangle$ carries $V(\zeta)/\eta_+(\zeta)$ (upper ray boundary value $+i0_\theta$).  
   When lifting to Liouville space (acting on operators $|\phi_+\rangle\langle\chi_+|$), the bra factor involves complex conjugation of eigenvalues and contours:
   \[
   z_0 \longmapsto z_0^* = \widetilde\omega_1 + \frac{i\gamma}{2},
   \qquad
   \Gamma_\theta = e^{-i\theta}\mathbb R^+ \longmapsto \Gamma_\theta^* = e^{+i\theta}\mathbb R^+.
   \]
   Every conjugate pairing in the bra tensor slot must track the complex-conjugated boundary prescription so that the Liouville eigenvalue differences $z_\alpha - z_\beta^*$ carry the correct dissipative sign ($\operatorname{Im}(z_\alpha - z_\beta^*) \le 0$ for forward time $t \ge 0$).

2. **Conditional semigroup and norm discipline (Corrigendum §8–§10):**  
   Stage 2 constructs the *matrix-element / weak spectral expansion* of forward-time Liouville evolution $\langle\langle \Phi_- | e^{-iLt} | \Phi_+ \rangle\rangle$ on the rigged Liouville test space. It does **not** assume that $e^{-iH_\theta t}$ is a Hilbert-space contraction semigroup without a separate Lumer–Phillips verification, nor does it conflate isolated resonance eigenvalues of a deformed generator with non-real eigenvalues of the physical self-adjoint Liouvillian $L = [H, \cdot]$.

3. **Boundary with Stage 3:**  
   Stage 2 supplies the biorthogonal four-sector Liouville basis, completeness identity, and forward-time spectral expansion on analytic observables/states. Construction of the non-unitary intertwiner $\Lambda^{-1}$, verification of star-unitarity, and proof of Lyapunov monotonicity belong to Stage 3.

---

## 1. Physical Liouville space and rigged Liouville test space

### 1.1 Hilbert–Schmidt Liouville space
Let $\mathcal H = \mathbb C|1\rangle \oplus L^2(\mathbb R^+, d\omega)$. The physical Liouville Hilbert space is the space of Hilbert–Schmidt operators
\[
\mathcal K = \mathcal B_2(\mathcal H) \cong \mathcal H \otimes \mathcal H^\dagger,
\]
equipped with the Hilbert–Schmidt inner product (antilinear in the first argument, linear in the second):
\[
\langle\langle A | B \rangle\rangle = \operatorname{Tr}(A^\dagger B).
\tag{1.1}
\]
On rank-one operators $|A\rangle\rangle = |\phi_+\rangle\langle\chi_+|$ and $|B\rangle\rangle = |\phi_-\rangle\langle\chi_-|$,
\[
\langle\langle B | A \rangle\rangle
= \operatorname{Tr}\!\left( |\chi_-\rangle\langle\phi_-| \, |\phi_+\rangle\langle\chi_+| \right)
= \langle\phi_-|\phi_+\rangle \, \langle\chi_+|\chi_-\rangle
= \langle\phi_-|\phi_+\rangle \, \overline{\langle\chi_-|\chi_+\rangle}.
\tag{1.2}
\]

The physical Liouville superoperator is
\[
L \rho = [H, \rho] = H\rho - \rho H,
\tag{1.3}
\]
which is self-adjoint on its natural domain $D(L) \subset \mathcal B_2(\mathcal H)$ and generates the unitary group $\mathcal U_t(\rho) = e^{-iLt}\rho = e^{-iHt}\rho e^{iHt}$.

### 1.2 Nuclear Liouville test space $\mathbf{\Phi}_{\mathcal L}$
Using the countably Hilbert nuclear space $\Phi = \mathbb C|1\rangle \oplus \Phi_{\mathrm{cont}}$ constructed in Stage 1.5, define the projective (equivalently injective, by nuclearity of $\Phi$) tensor product
\[
\mathbf{\Phi}_{\mathcal L} = \Phi \widehat{\otimes} \Phi^\dagger,
\tag{1.4}
\]
consisting of trace-class / Hilbert–Schmidt operators whose integral kernels in the direct-sum basis $(|1\rangle, |\omega\rangle)$ belong to the corresponding tensor products of $\mathbb C$ and $\Phi_{\mathrm{cont}}$ (with antilinear/conjugate-analytic dependence in the second tensor slot).

Because $\Phi$ is nuclear and embeds densely and continuously into $\mathcal H$, $\mathbf{\Phi}_{\mathcal L}$ is a nuclear Fréchet space forming a Liouville Gelfand triple:
\[
\mathbf{\Phi}_{\mathcal L} \hookrightarrow \mathcal B_2(\mathcal H) \hookrightarrow \mathbf{\Phi}_{\mathcal L}^\times.
\tag{1.5}
\]
Moreover, invariance of $\Phi$ under $H$ (Stage 1.5 §4) implies invariance of $\mathbf{\Phi}_{\mathcal L}$ under $L = [H, \cdot]$.

---

## 2. Lifted left and right Liouville functionals (four sectors)

To lift the Stage 1 biorthogonal system
\[
\left\{ |\psi_{z_0}^R\rangle, \; |\psi_\zeta^R\rangle_{\zeta \in \Gamma_\theta} \right\}
\quad\text{and}\quad
\left\{ \langle\psi_{z_0}^L|, \; \langle\psi_\zeta^L|_{\zeta \in \Gamma_\theta} \right\}
\]
to $\mathbf{\Phi}_{\mathcal L}^\times$, evaluate on factorized test operators $|B\rangle\rangle = |\phi_-\rangle\langle\chi_-| \in \mathbf{\Phi}_{\mathcal L}$ (in the first, antilinear slot of $\langle\langle \cdot | \cdot \rangle\rangle$) and $|A\rangle\rangle = |\phi_+\rangle\langle\chi_+| \in \mathbf{\Phi}_{\mathcal L}$ (in the second, linear slot), and extend by nuclear bilinearity/sesquilinearity.

### 2.1 Right Liouville eigenfunctionals $|\Psi_{\alpha,\beta}^R\rangle\rangle$
For a ket index $\alpha \in \{z_0\} \cup \Gamma_\theta$ and a bra index $\beta \in \{z_0\} \cup \Gamma_\theta$, define the right Liouville generalized functional by
\[
\langle\langle \phi_-\chi_-^\dagger | \Psi_{\alpha,\beta}^R \rangle\rangle
:= \langle\phi_-|\psi_\alpha^R\rangle \, \overline{\langle\chi_-|\psi_\beta^R\rangle}.
\tag{2.1}
\]
Explicitly, this partitions the Liouville generalized right basis into four sectors:
1. **Resonance–Resonance ($RR$):**
   \[
   \langle\langle \phi_-\chi_-^\dagger | \Psi_{z_0, z_0}^R \rangle\rangle
   = \langle\phi_-|\psi_{z_0}^R\rangle \, \overline{\langle\chi_-|\psi_{z_0}^R\rangle}.
   \tag{2.2a}
   \]
2. **Resonance–Continuum ($RC$):** for $\zeta' \in \Gamma_\theta$,
   \[
   \langle\langle \phi_-\chi_-^\dagger | \Psi_{z_0, \zeta'}^R \rangle\rangle
   = \langle\phi_-|\psi_{z_0}^R\rangle \, \overline{\langle\chi_-|\psi_{\zeta'}^R\rangle}.
   \tag{2.2b}
   \]
3. **Continuum–Resonance ($CR$):** for $\zeta \in \Gamma_\theta$,
   \[
   \langle\langle \phi_-\chi_-^\dagger | \Psi_{\zeta, z_0}^R \rangle\rangle
   = \langle\phi_-|\psi_\zeta^R\rangle \, \overline{\langle\chi_-|\psi_{z_0}^R\rangle}.
   \tag{2.2c}
   \]
4. **Continuum–Continuum ($CC$):** for $(\zeta, \zeta') \in \Gamma_\theta \times \Gamma_\theta$,
   \[
   \langle\langle \phi_-\chi_-^\dagger | \Psi_{\zeta, \zeta'}^R \rangle\rangle
   = \langle\phi_-|\psi_\zeta^R\rangle \, \overline{\langle\chi_-|\psi_{\zeta'}^R\rangle}.
   \tag{2.2d}
   \]

**Orientation check on the bra slot:** Because $\overline{\langle\chi_-|\psi_{\zeta'}^R\rangle}$ conjugates Eq. (7.4a) of Stage 1, its denominator is $\overline{\eta_-(\zeta')} = \eta_+^{\mathrm{conj}}(\zeta'^*)$ (the boundary value from the upper/left side of the reflected ray $\Gamma_\theta^* = e^{+i\theta}\mathbb R^+$), paired with $V(\zeta')$.

### 2.2 Analytic Left Liouville eigenfunctionals $\langle\langle\Psi_{\alpha,\beta}^L|$
Symmetrically, for $\alpha, \beta \in \{z_0\} \cup \Gamma_\theta$, define the left Liouville generalized functional by
\[
\langle\langle \Psi_{\alpha,\beta}^L | \phi_+\chi_+^\dagger \rangle\rangle
:= \langle\psi_\alpha^L|\phi_+\rangle \, \overline{\langle\psi_\beta^L|\chi_+\rangle},
\tag{2.3}
\]
yielding the four left sectors $\langle\langle\Psi_{z_0,z_0}^L|$, $\langle\langle\Psi_{z_0,\zeta'}^L|$, $\langle\langle\Psi_{\zeta,z_0}^L|$, and $\langle\langle\Psi_{\zeta,\zeta'}^L|$.

By continuity of the single-particle functionals on $\Phi$ (Stage 1.5 §3) and the nuclearity of $\mathbf{\Phi}_{\mathcal L} = \Phi \widehat{\otimes} \Phi^\dagger$, every functional in (2.1) and (2.3) extends uniquely to a continuous functional on $\mathbf{\Phi}_{\mathcal L}$.

---

## 3. Generalized Liouville eigenvalue equations

Let $L = [H, \cdot]$ act on $|B\rangle\rangle = |\phi_-\rangle\langle\chi_-| \in \mathbf{\Phi}_{\mathcal L}$ as
\[
L(|\phi_-\rangle\langle\chi_-|) = |H\phi_-\rangle\langle\chi_-| - |\phi_-\rangle\langle H\chi_-|,
\]
and likewise on $|A\rangle\rangle = |\phi_+\rangle\langle\chi_+| \in \mathbf{\Phi}_{\mathcal L}$.

Applying the Stage 1 generalized eigenvalue equations (Eqs. (8.1)–(8.2)) to each tensor factor gives:
\[
\langle\langle L B | \Psi_{\alpha,\beta}^R \rangle\rangle
= \langle H\phi_-|\psi_\alpha^R\rangle \overline{\langle\chi_-|\psi_\beta^R\rangle}
- \langle\phi_-|\psi_\alpha^R\rangle \overline{\langle H\chi_-|\psi_\beta^R\rangle}
= (\alpha - \beta^*) \langle\langle B | \Psi_{\alpha,\beta}^R \rangle\rangle,
\tag{3.1a}
\]
\[
\langle\langle \Psi_{\alpha,\beta}^L | L A \rangle\rangle
= \langle\psi_\alpha^L|H\phi_+\rangle \overline{\langle\psi_\beta^L|\chi_+\rangle}
- \langle\psi_\alpha^L|\phi_+\rangle \overline{\langle\psi_\beta^L|H\chi_+\rangle}
= (\alpha - \beta^*) \langle\langle \Psi_{\alpha,\beta}^L | A \rangle\rangle,
\tag{3.1b}
\]
for every $\alpha, \beta \in \{z_0\} \cup \Gamma_\theta$.

### 3.1 Four-sector Liouville eigenvalue spectrum
Denoting $\Lambda_{\alpha,\beta} := \alpha - \beta^*$, the four sectors carry the generalized Liouville eigenvalues:

1. **Sector $RR$ ($\alpha = z_0, \beta = z_0$):**
   \[
   \Lambda_{z_0, z_0} = z_0 - z_0^* = -i\gamma,
   \tag{3.2a}
   \]
   a pure imaginary dissipative pole governing the exponential decay $e^{-i\Lambda_{z_0,z_0}t} = e^{-\gamma t}$ of the resonant state population.

2. **Sector $RC$ ($\alpha = z_0, \beta = \zeta' = x'e^{-i\theta}$):**
   \[
   \Lambda_{z_0, \zeta'} = z_0 - \zeta'^* = \left(\widetilde\omega_1 - x'\cos\theta\right) - i\left(\frac{\gamma}{2} + x'\sin\theta\right),
   \tag{3.2b}
   \]
   lying strictly in the lower half-plane with $\operatorname{Im}\Lambda_{z_0,\zeta'} \le -\gamma/2$.

3. **Sector $CR$ ($\alpha = \zeta = x e^{-i\theta}, \beta = z_0$):**
   \[
   \Lambda_{\zeta, z_0} = \zeta - z_0^* = \left(x\cos\theta - \widetilde\omega_1\right) - i\left(x\sin\theta + \frac{\gamma}{2}\right),
   \tag{3.2c}
   \]
   symmetric to Sector $RC$ under reflection across the imaginary axis, also with $\operatorname{Im}\Lambda_{\zeta,z_0} \le -\gamma/2$.

4. **Sector $CC$ ($\alpha = \zeta = x e^{-i\theta}, \beta = \zeta' = x'e^{-i\theta}$):**
   \[
   \Lambda_{\zeta, \zeta'} = \zeta - \zeta'^* = (x - x')\cos\theta - i(x + x')\sin\theta,
   \tag{3.2d}
   \]
   spanning a sectorial wedge in the closed lower half-plane whose vertex touches the origin as $x, x' \downarrow 0$ (producing the algebraic $O(t^{-3})$ threshold tail identified in Stage 1 §12).

---

## 4. Four-sector completeness and forward-time Liouville expansion

### 4.1 Liouville completeness on $\mathbf{\Phi}_{\mathcal L}$
Assuming the single-particle completeness theorem (Stage 1 Eq. (9.1)) holds on $\Phi$ with the required dominated-convergence bounds, taking the product of (9.1) for $\langle\phi_-|\phi_+\rangle$ and the complex conjugate of (9.1) for $\overline{\langle\chi_-|\chi_+\rangle} = \langle\chi_+|\chi_-\rangle$ yields the four-sector Liouville resolution of the identity on factorized elements (and hence on $\mathbf{\Phi}_{\mathcal L}$ by nuclearity):
\[
\begin{aligned}
\langle\langle B | A \rangle\rangle
={}& \langle\langle B | \Psi_{z_0,z_0}^R \rangle\rangle \langle\langle \Psi_{z_0,z_0}^L | A \rangle\rangle \\
&+ \int_{\Gamma_\theta^*} \langle\langle B | \Psi_{z_0,\zeta'}^R \rangle\rangle \langle\langle \Psi_{z_0,\zeta'}^L | A \rangle\rangle \, d\zeta'^* \\
&+ \int_{\Gamma_\theta} \langle\langle B | \Psi_{\zeta,z_0}^R \rangle\rangle \langle\langle \Psi_{\zeta,z_0}^L | A \rangle\rangle \, d\zeta \\
&+ \iint_{\Gamma_\theta \times \Gamma_\theta^*} \langle\langle B | \Psi_{\zeta,\zeta'}^R \rangle\rangle \langle\langle \Psi_{\zeta,\zeta'}^L | A \rangle\rangle \, d\zeta \, d\zeta'^*.
\end{aligned}
\tag{4.1}
\]

**Jacobian and contour orientation note:** Along $\zeta = x e^{-i\theta}$ and $\zeta'^* = x' e^{+i\theta}$ ($x, x' > 0$),
\[
d\zeta = e^{-i\theta}\,dx, \qquad d\zeta'^* = e^{+i\theta}\,dx', \qquad d\zeta\,d\zeta'^* = dx\,dx',
\]
so the phase factors $e^{-i\theta}$ and $e^{+i\theta}$ cancel identically in the double-continuum measure $d\zeta\,d\zeta'^*$.

### 4.2 Forward-time Liouville representation ($t \ge 0$)
For $t \ge 0$, combining the forward-time single-particle expansion (Stage 1 Eq. (9.2)) for $e^{-iHt}|\phi_+\rangle$ with the backward/conjugate expansion for $\langle\chi_+|e^{iHt}$ gives the weak spectral representation of Liouville evolution on $\mathbf{\Phi}_{\mathcal L}$:
\[
\begin{aligned}
\langle\langle B | e^{-iLt} | A \rangle\rangle
={}& e^{-\gamma t} \, \langle\langle B | \Psi_{z_0,z_0}^R \rangle\rangle \langle\langle \Psi_{z_0,z_0}^L | A \rangle\rangle \\
&+ \int_{\Gamma_\theta^*} e^{-i(z_0 - \zeta'^*)t} \, \langle\langle B | \Psi_{z_0,\zeta'}^R \rangle\rangle \langle\langle \Psi_{z_0,\zeta'}^L | A \rangle\rangle \, d\zeta'^* \\
&+ \int_{\Gamma_\theta} e^{-i(\zeta - z_0^*)t} \, \langle\langle B | \Psi_{\zeta,z_0}^R \rangle\rangle \langle\langle \Psi_{\zeta,z_0}^L | A \rangle\rangle \, d\zeta \\
&+ \iint_{\Gamma_\theta \times \Gamma_\theta^*} e^{-i(\zeta - \zeta'^*)t} \, \langle\langle B | \Psi_{\zeta,\zeta'}^R \rangle\rangle \langle\langle \Psi_{\zeta,\zeta'}^L | A \rangle\rangle \, d\zeta \, d\zeta'^*,
\qquad t \ge 0.
\end{aligned}
\tag{4.2}
\]

### 4.3 Bare-state population decay and trace preservation check
Testing (4.2) on the bare-state projector $|A\rangle\rangle = |B\rangle\rangle = |1\rangle\langle 1|$ using Stage 1 Eq. (10.1)–(10.2) gives the survival probability of the discrete state:
\[
P_1(t) = \langle\langle 1,1 | e^{-iLt} | 1,1 \rangle\rangle
= \left| A_1 e^{-iz_0 t} + \int_{\Gamma_\theta} \frac{\lambda^2 J(\zeta)}{\eta_-(\zeta)\eta_+(\zeta)} e^{-i\zeta t}\,d\zeta \right|^2,
\qquad t \ge 0,
\tag{4.3}
\]
which reproduces $|A_1|^2 e^{-\gamma t}$ as the pure-resonance $RR$ contribution, exponentially damped cross-terms from $RC$ and $CR$, and an $O(t^{-3})$ non-Markovian threshold tail from Sector $CC$ (when $J(\omega) \sim C\omega^{1/2}$).

Similarly, pairing (4.2) with the identity functional $\langle\langle \mathbf{1} | \cdot \rangle\rangle = \operatorname{Tr}(\cdot)$ (extended to $\mathbf{\Phi}_{\mathcal L}$ via the single-particle completeness kernel) yields the trace-conservation identity
\[
\operatorname{Tr}(e^{-iLt} A) = \operatorname{Tr}(A), \qquad t \ge 0,
\tag{4.4}
\]
providing an immediate consistency check on the relative phases and Jacobians across all four sectors.

---

## 5. Stage 2 proof obligations and handoff to Stage 3

Before proceeding to Stage 3 (construction of $\Lambda^{-1}$, star-unitarity, and the Lyapunov functional $\Omega(t)$), the following Stage 2 obligations are tracked explicitly:

| Item | Required verification |
|---|---|
| Nuclear tensor lift | Confirm that continuity of the single-particle functionals on $\Phi$ (Stage 1.5 §3) lifts via $\mathbf{\Phi}_{\mathcal L} = \Phi \widehat{\otimes} \Phi^\dagger$ without unverified cross-norm blowup. |
| Four-sector biorthogonality | Verify distributional biorthogonality across all $4 \times 4$ sector pairs—specifically $\langle\langle \Psi_{z_0,z_0}^L | \Psi_{z_0,z_0}^R \rangle\rangle = 1$, mixed-sector vanishing, and $\langle\langle \Psi_{\zeta,\zeta'}^L | \Psi_{\mu,\mu'}^R \rangle\rangle = \delta_{\Gamma_\theta}(\zeta - \mu)\delta_{\Gamma_\theta^*}(\zeta'^* - \mu'^*)$—directly from the single-particle test-space pairings. |
| Trace-functional pairing | Verify that $\operatorname{Tr}(\cdot)$ defines a continuous functional on $\mathbf{\Phi}_{\mathcal L}$ and compute its action on $|\Psi_{\alpha,\beta}^R\rangle\rangle$ across all four sectors (needed in Stage 3 to verify trace preservation under $\Lambda^{-1}$). |
| Sector-swap & adjoint symmetry | Track how operator adjoint $A \mapsto A^\dagger$ exchanges the two tensor slots $(\alpha, \beta) \leftrightarrow (\beta, \alpha)$ and exchanges $\Gamma_\theta \leftrightarrow \Gamma_\theta^*$ together with the $\eta_\mp$ denominators—the direct input to Stage 3's star-unitarity relation. |