# Stage 1.5 — Nuclear Test-Space Specification and Distributional Obligations

**Status:** Draft specification for proof-obligation audit (Stage 1 $\to$ Stage 2 bridge)  
**Prerequisite:** `friedrichs_stage1_single_particle_foundation.md` (revision 2) and accompanying block-by-block jump note  
**Purpose:** Specify a concrete test-space framework and distributional rules to turn the formal identities of Stage 1 (resolvent jump factorization, generalized eigenvalue equations, contour boundary limits, completeness, and biorthogonality) into controlled mathematical statements.

---

## 0. Scope and orientation reminder

Stage 1 establishes the algebraic structure of the single-particle Friedrichs resolvent, second-sheet dispersion function $\eta_+$, resonance pole $z_0$, and deformed-continuum functionals along the ray
\[
\Gamma_\theta = e^{-i\theta}\mathbb R^+, \qquad 0 < \theta < \theta_0.
\]

**Orientation reminder for downstream lifting ($\eta_\mp$):** In the corrected Stage 1 pairings (Eqs. (7.4a)–(7.4b) and (10.2)), the right continuum functional carries $\overline{V(\bar\zeta)}/\eta_-(\zeta)$ (lower boundary value across $\Gamma_\theta$) while the left continuum functional carries $V(\zeta)/\eta_+(\zeta)$ (upper boundary value across $\Gamma_\theta$). This orientation is fixed by the bra/ket reflection conventions and the jump identity (7.5); any Stage 2 tensor or antidual lift to Liouville space must preserve this assignment rather than assuming a naive "right = upper, left = lower" correspondence.

---

## 1. Candidate nuclear test-space architecture

To pair smoothly with generalized eigenfunctionals (rigged Hilbert space / Gelfand triple structure) while permitting analytic continuation into a sector and contour deformation onto $\Gamma_\theta$, a test space $\Phi$ for the one-particle sector $\mathcal H = \mathbb C|1\rangle \oplus L^2(\mathbb R^+, d\omega)$ should satisfy:

1. **Continuous and dense embedding:**
   \[
   \Phi \hookrightarrow \mathcal H \hookrightarrow \Phi^\times,
   \]
   with $\Phi$ equipped with a countable family of Hilbertian or seminorms making $\Phi$ a countably Hilbert nuclear (Fréchet nuclear) space, and $\Phi^\times$ its topological antidual (or dual, depending on sesquilinear vs. bilinear pairing conventions—kept explicit below).

2. **Direct-sum compatibility:**
   \[
   \Phi = \mathbb C|1\rangle \oplus \Phi_{\mathrm{cont}},
   \]
   where $\Phi_{\mathrm{cont}}$ is a nuclear space of functions on $\mathbb R^+$ admitting holomorphic extension to a sector containing $\overline{\Sigma_\theta}$ (up to $\Gamma_\theta$, with controlled boundary behavior).

3. **Concrete model choice (to be tailored to $V$):**
   A standard template is a weighted analytic / Gevrey / rapid-decay space on a sector $\mathcal S_\delta = \{z \in \mathbb C : |\arg z| < \delta\}$ with $\delta > \theta_0$, controlled by norms such as
   \[
   \|\psi\|_{m,k} = \sup_{z \in \overline{\mathcal S_\delta}} (1 + |z|)^m (1 + |z|^{-1})^k \left( |\psi(z)| + |\psi'(z)| \right)
   \quad \text{or weighted } L^2 / W^{s,2} \text{ norms along rays } e^{-i\alpha}\mathbb R^+.
   \]
   The exact weight growth at $\infty$ and behavior at $0$ must be chosen so that:
   - $\Phi_{\mathrm{cont}}$ is dense in $L^2(\mathbb R^+)$ with continuous inclusion;
   - the form factor $V$ and its analytic continuation have compatible regularity and decay so that all integrals in Stage 1 converge absolutely and continuously in the test-space topology.

---

## 2. Pairing conventions and reflection map

Stage 1 uses:
- a sesquilinear Hilbert inner product $\langle \phi | \psi \rangle$, antilinear in the first slot and linear in the second;
- the reflected function $\phi_-^*(z) = \overline{\phi_-(\bar z)}$.

When extending evaluation functionals $\langle \phi_- | \psi_\zeta^R \rangle$ and $\langle \psi_\zeta^L | \phi_+ \rangle$ to $\Phi$:

- **Right functional $\langle \phi_- | \psi_\zeta^R \rangle$:** linear in $\phi_- \in \Phi$ (as a functional on the first slot of the pairing) and antilinear/holomorphic in $\zeta$ as specified by (7.4a). Its continuity requires showing that for each fixed $\zeta \in \Gamma_\theta \setminus \{0\}$ (and uniformly on compact subsets of $\Gamma_\theta \setminus \{0\}$), the map $\phi_- \mapsto \langle \phi_- | \psi_\zeta^R \rangle$ is continuous in the topology of $\Phi$.
- **Left functional $\langle \psi_\zeta^L | \phi_+ \rangle$:** linear in $\phi_+ \in \Phi$ (second slot of the pairing), with continuity in $\phi_+ \in \Phi$ for $\zeta \in \Gamma_\theta \setminus \{0\}$.

---

## 3. Core proof obligations for Stage 1.5

### 3.1 Domain invariance under $H$ and boundary operations
- Show that $\Phi$ is invariant (or maps continuously into a slightly larger controlled space) under $H$ and under the operations appearing in the generalized eigenvalue equations (Eqs. (8.1)–(8.6)), including the bra-side Schwarz reflection identity for $H\phi_-$ and the ket-side action on $\phi_+$.
- Verify that the algebraic rearrangements (8.3) and (8.5) and the boundary dispersion relations (8.4) and (8.6) hold for the integrals defining the functionals on $\Phi$.

### 3.2 Distributional boundary limits and Jacobians on $\Gamma_\theta$
- Parameterize $\Gamma_\theta$ by $\zeta = x e^{-i\theta}$ ($x > 0$), so $d\zeta = e^{-i\theta}\,dx$ and the contour delta satisfies
  \[
  \int_{\Gamma_\theta} \delta_{\Gamma_\theta}(\zeta - \zeta') f(\zeta')\,d\zeta' = f(\zeta), \qquad \delta_{\Gamma_\theta}(xe^{-i\theta} - x'e^{-i\theta}) = e^{+i\theta}\delta(x - x').
  \]
- Justify applying the oriented Sokhotski–Plemelj identity (7.2) to the Cauchy integrals in the four resolvent blocks of (2.1) and to $\eta_\mp(\zeta)^{-1}$ when deriving the resolvent jump factorization (7.3) in the accompanying block-by-block calculation (`To establish the continuum resolvent jump.txt`).
- Confirm that interchanging boundary limits $\pm i0_\theta$ with contour/parameter integrals is valid on $\Phi$ without unverified boundary or endpoint singularities.

### 3.3 Contour deformation, completeness, and biorthogonality
- **Contour deformation (Section 5):** Prove large-arc decay and threshold integrability so that deforming the upper-half-plane contour integral (5.3) to $\Gamma_\theta$ plus the residue at $z_0$ (5.4) is justified on $\Phi$.
- **Completeness (Section 9):** Establish a dominated-convergence or uniform majorant bound as $z = iy \to i\infty$ in $z\langle \phi_- | R(z) | \phi_+ \rangle$ to pass the limit through the $\Gamma_\theta$ integral and derive (9.1) and forward-time expansion (9.2) for $t \ge 0$.
- **Biorthogonality (Section 14):** Derive off-diagonal vanishing from the generalized eigenvalue equations (8.1)–(8.2) and compute the diagonal pairings $\langle \psi_{z_0}^L | \psi_{z_0}^R \rangle = 1$ and $\langle \psi_\zeta^L | \psi_{\zeta'}^R \rangle = \delta_{\Gamma_\theta}(\zeta - \zeta')$ directly within the nuclear test-space pairing rather than reading them off from (9.1).
- **Bare-state sum rule (Section 10):** Confirm (10.3) once completeness (9.1) and the corrected continuum evaluations (10.2) are established.

---

## 4. Readiness criteria for Stage 2

Stage 1.5 is ready to feed into Stage 2 when:
1. A concrete nuclear space $\Phi$ compatible with $V$ and $\Gamma_\theta$ is written down;
2. Continuity of $\langle \cdot | \psi_{z_0}^R \rangle$, $\langle \psi_{z_0}^L | \cdot \rangle$, $\langle \cdot | \psi_\zeta^R \rangle$, and $\langle \psi_\zeta^L | \cdot \rangle$ on $\Phi$ is proved;
3. The jump factorization (7.3), eigenvalue equations (8.1)–(8.2), completeness (9.1), and distributional biorthogonality are established on $\Phi$ with explicit hypotheses.