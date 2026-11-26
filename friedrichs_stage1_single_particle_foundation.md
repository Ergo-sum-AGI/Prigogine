# friedrichs_stage1_single_particle_foundation.md
# Stage 1 — Single-Particle Friedrichs Model: Resolvent, Resonance Continuation, and Spectral Resolution

**Status:** Reconstructed foundation; proof audit in progress (revision 2)
**Source:** `friedrichs_biorthogonal_completeness_note3.md` and the associated Friedrichs-model derivations
**Role in the research programme:** Establish the one-particle spectral structure on which the Liouville-space construction in Stage 2 is built.

---

## 0. Scope and proof-status convention

This document reconstructs the single-particle foundation of the Friedrichs-model programme. It separates:

- **Derived:** follows from the displayed definitions and calculations, subject to the stated domain assumptions.
- **Conditional:** follows if an explicitly stated spectral or analytic hypothesis holds.
- **To prove:** asserted in the source material, but not yet established by a complete argument here.
- **Not part of Stage 1:** belongs to the subsequent Liouville-space or Prigogine-transformation analysis.

The central objective is to obtain a resonance-plus-deformed-continuum representation of the physical resolvent and, under suitable hypotheses, of forward-time matrix elements.

Stage 1 does **not** construct Prigogine's transformation \(\Lambda^{-1}\), prove star-unitarity, or establish a Lyapunov functional.

## 1. Friedrichs Hamiltonian and physical Hilbert space

Let
\[
\mathcal H=\mathbb C|1\rangle\oplus L^2(\mathbb R^+,d\omega),
\qquad \hbar=1.
\]

A vector is written
\[
|\psi\rangle=c|1\rangle+\int_0^\infty
\psi(\omega)|\omega\rangle\,d\omega.
\]

The inner product is antilinear in its first argument:
\[
\langle\phi|\psi\rangle
=\overline{c_\phi}c_\psi+
\int_0^\infty\overline{\phi(\omega)}
\psi(\omega)\,d\omega.
\tag{1.1}
\]

The Hamiltonian is
\[
H=H_0+\lambda V
=
\begin{pmatrix}
\omega_1&\lambda\langle V|\\
\lambda|V\rangle&M_\omega
\end{pmatrix},
\tag{1.2}
\]
where
\[
(M_\omega\psi)(\omega)=\omega\psi(\omega),
\]
and
\[
H\begin{pmatrix}c\\\psi(\omega)\end{pmatrix}
=
\begin{pmatrix}
\omega_1c+\lambda\displaystyle\int_0^\infty
\overline{V(\omega)}\psi(\omega)\,d\omega\\[5pt]
\omega\psi(\omega)+\lambda V(\omega)c
\end{pmatrix}.
\tag{1.3}
\]

Assume \(V\in L^2(\mathbb R^+)\), so the off-diagonal coupling is bounded, and take the natural domain
\[
D(H)=\mathbb C\oplus
\{\psi\in L^2(\mathbb R^+):\omega\psi(\omega)\in L^2(\mathbb R^+)\}.
\]
Then \(H\) is self-adjoint as a bounded self-adjoint perturbation of \(H_0\).

### 1.1 No-bound-state condition

Define
\[
\eta(z)=z-\omega_1-\lambda^2
\int_0^\infty\frac{|V(\omega)|^2}{z-\omega}\,d\omega,
\qquad z\notin[0,\infty).
\tag{1.4}
\]

A useful sufficient condition excluding a negative-energy eigenvalue is
\[
\lambda^2\int_0^\infty
\frac{|V(\omega)|^2}{\omega}\,d\omega<\omega_1.
\tag{1.5}
\]
Indeed, for \(z<0\),
\[
\eta'(z)=1+\lambda^2\int_0^\infty
\frac{|V(\omega)|^2}{(z-\omega)^2}\,d\omega>0,
\]
while
\[
\eta(0^-)
=-\omega_1+\lambda^2\int_0^\infty
\frac{|V(\omega)|^2}{\omega}\,d\omega<0.
\]
Since \(\eta(z)\to-\infty\) as \(z\to-\infty\), no negative real zero occurs.

This argument excludes negative-energy roots. Exclusion of embedded eigenvalues and singular continuous spectrum requires the relevant regularity and spectral hypotheses; it is not a consequence of (1.5) alone.

For the resonance analysis below, assume that the physical spectrum is purely absolutely continuous on \([0,\infty)\), with no point spectrum. This is a spectral hypothesis to be verified for the chosen form factor and parameter regime.

## 2. Exact resolvent

For \(z\notin[0,\infty)\), the Schur-complement formula gives
\[
R(z)=(z-H)^{-1}
=
\begin{pmatrix}
\eta(z)^{-1}
&
\displaystyle\frac{\lambda}{\eta(z)}
\langle V|(z-M_\omega)^{-1}\\[7pt]
\displaystyle\frac{\lambda}{\eta(z)}
(z-M_\omega)^{-1}|V\rangle
&
\displaystyle(z-M_\omega)^{-1}
+\frac{\lambda^2}{\eta(z)}
(z-M_\omega)^{-1}|V\rangle
\langle V|(z-M_\omega)^{-1}
\end{pmatrix}.
\tag{2.1}
\]

In particular,
\[
\langle1|R(z)|1\rangle=\frac1{\eta(z)}.
\tag{2.2}
\]

For test vectors
\[
|\phi_\pm\rangle=c_\pm|1\rangle+
\int_0^\infty\phi_\pm(\omega)|\omega\rangle\,d\omega,
\]
write
\[
\phi_-^*(z)=\overline{\phi_-(\bar z)}.
\]
Then
\[
\langle\phi_-|R(z)|\phi_+\rangle
=
\int_0^\infty
\frac{\phi_-^*(\omega)\phi_+(\omega)}{z-\omega}\,d\omega
+\frac{\mathcal A_-(z;\phi_-)\mathcal A_+(z;\phi_+)}
{\eta(z)},
\tag{2.3}
\]
where
\[
\mathcal A_-(z;\phi_-)
=\overline{c_-}
+\lambda\int_0^\infty
\frac{V(\omega)\phi_-^*(\omega)}{z-\omega}\,d\omega,
\tag{2.4a}
\]
and
\[
\mathcal A_+(z;\phi_+)
=c_+
+\lambda\int_0^\infty
\frac{\overline{V(\omega)}\phi_+(\omega)}{z-\omega}\,d\omega.
\tag{2.4b}
\]

These expressions follow directly from the four blocks of (2.1). They fix the conjugation conventions used throughout the rest of this document.

## 3. Boundary values and second-sheet continuation

Assume that \(V\) admits a holomorphic continuation to a sector
\[
\mathcal W=\{z\ne0:|\arg z|<\theta_0\},
\]
and define the reflected analytic density
\[
J(z)=V(z)\overline{V(\bar z)}.
\tag{3.1}
\]
On the positive real axis,
\[
J(\omega)=|V(\omega)|^2.
\]

For a sufficiently regular function \(f\),
\[
C(z)=\int_0^\infty\frac{f(\omega)}{z-\omega}\,d\omega
\]
has boundary jump
\[
C(E+i0)-C(E-i0)=-2\pi i f(E).
\tag{3.2}
\]

Consequently,
\[
\eta(E+i0)-\eta(E-i0)
=2\pi i\lambda^2J(E).
\tag{3.3}
\]

The continuation from the upper half-plane through the positive real axis into a lower sector is
\[
\eta_+(z)=\eta(z)+2\pi i\lambda^2J(z).
\tag{3.4}
\]
The sign is positive because the Cauchy integral in (1.4) occurs with a minus sign.

For the two factors in (2.4), the Cauchy integrals occur with a plus sign. Their continued forms therefore acquire a minus residue term:
\[
\mathcal A_-^{\mathrm{cont}}(z;\phi_-)
=
\overline{c_-}
+\lambda\int_0^\infty
\frac{V(\omega)\phi_-^*(\omega)}{z-\omega}\,d\omega
-2\pi i\lambda V(z)\phi_-^*(z),
\tag{3.5a}
\]
\[
\mathcal A_+^{\mathrm{cont}}(z;\phi_+)
=
c_+
+\lambda\int_0^\infty
\frac{\overline{V(\omega)}\phi_+(\omega)}{z-\omega}\,d\omega
-2\pi i\lambda\overline{V(\bar z)}\phi_+(z).
\tag{3.5b}
\]

Choose \(0<\theta<\theta_0\) such that the simple resonance zero
\[
z_0=\widetilde\omega_1-\frac{i\gamma}{2}
\tag{3.6}
\]
lies in
\[
\Sigma_\theta=\{z:-\theta<\arg z<0\}.
\]
Let
\[
\Gamma_\theta=e^{-i\theta}\mathbb R^+
\]
be oriented from zero to infinity. The two boundary values of analytic functions across \(\Gamma_\theta\) are denoted
\[
f_\mp(\zeta)=f(\zeta\mp i0_\theta),
\qquad \zeta\in\Gamma_\theta,
\tag{3.7}
\]
where \(i0_\theta\) denotes the boundary value relative to the oriented ray \(\Gamma_\theta\) (see Section 7 for the explicit prescription and the oriented Sokhotski–Plemelj identity).

Under sufficient analyticity and decay to justify contour deformation, (3.5) can be written as
\[
\mathcal A_-^{\mathrm{cont}}(z;\phi_-)
=
\overline{c_-}
+\lambda\int_{\Gamma_\theta}
\frac{V(\zeta)\phi_-^*(\zeta)}{z-\zeta}\,d\zeta,
\tag{3.8a}
\]
\[
\mathcal A_+^{\mathrm{cont}}(z;\phi_+)
=
c_+
+\lambda\int_{\Gamma_\theta}
\frac{\overline{V(\bar\zeta)}\phi_+(\zeta)}
{z-\zeta}\,d\zeta.
\tag{3.8b}
\]

Likewise,
\[
\eta_+(z)=z-\omega_1-
\lambda^2\int_{\Gamma_\theta}
\frac{J(\zeta)}{z-\zeta}\,d\zeta.
\tag{3.9}
\]

The equalities (3.8)–(3.9) require the contour to avoid the evaluation point and the relevant integrands to satisfy the necessary threshold and large-arc bounds.

## 4. Resonance pole and weak-coupling width

Assume \(\eta_+\) has a simple zero at \(z_0\):
\[
\eta_+(z_0)=0,\qquad \eta_+'(z_0)\ne0.
\tag{4.1}
\]
Define the residue
\[
A_1=\frac1{\eta_+'(z_0)}.
\tag{4.2}
\]

At weak coupling, the resonance position is determined perturbatively by the zero of \(\eta_+\). To leading nontrivial order,
\[
\gamma=
2\pi\lambda^2|V(\widetilde\omega_1)|^2
+O(\lambda^4),
\tag{4.3}
\]
subject to the smoothness and non-degeneracy assumptions needed for the perturbative expansion.

Equation (4.3) is the Fermi golden rule width. It is a weak-coupling approximation, not an exact identity at finite coupling.

## 5. Contour-deformed resolvent representation

Assume the physical resolvent has the required boundary values and the analytic continuation \(R_+(z)\) exists in the deformation sector with a simple pole at \(z_0\).

Stone's formula gives
\[
R(E+i0)-R(E-i0)
=-2\pi i\,\delta(E-H).
\tag{5.1}
\]
In a generalized scattering representation, the density can be written
\[
\delta(E-H)=|\psi_E^+\rangle\langle\psi_E^+|,
\tag{5.2}
\]
with the normalization convention fixed by the spectral measure.

For \(z\) in the upper half-plane,
\[
\langle\phi_-|R(z)|\phi_+\rangle
=
\frac1{2\pi i}\int_0^\infty
\frac{\langle\phi_-|
[R(E-i0)-R_+(E+i0)]|\phi_+\rangle}{z-E}\,dE.
\tag{5.3}
\]

Deforming the continued upper-boundary contribution from \(\mathbb R^+\) to \(\Gamma_\theta\) crosses the pole \(z_0\). With the orientation in (3.8), the result is
\[
\begin{aligned}
\langle\phi_-|R(z)|\phi_+\rangle
={}&
\frac{\operatorname{Res}_{w=z_0}
\langle\phi_-|R_+(w)|\phi_+\rangle}{z-z_0}\\
&+\frac1{2\pi i}\int_{\Gamma_\theta}
\frac{\langle\phi_-|[R(\zeta)-R_+(\zeta)]|\phi_+\rangle}
{z-\zeta}\,d\zeta.
\end{aligned}
\tag{5.4}
\]

This is the central contour-deformed resolvent identity. Its rigorous use requires:
1. meromorphic continuation of the relevant matrix elements;
2. a simple pole at \(z_0\), with no other enclosed singularities;
3. vanishing of the large-arc contribution;
4. local integrability at the threshold;
5. convergence of the deformed-continuum integral.

## 6. Resonance generalized functionals

The residue of (2.3), using the continued factors, factorizes:
\[
\operatorname{Res}_{w=z_0}
\langle\phi_-|R_+(w)|\phi_+\rangle
=
A_1\,
\mathcal A_-^{\mathrm{cont}}(z_0;\phi_-)
\mathcal A_+^{\mathrm{cont}}(z_0;\phi_+).
\tag{6.1}
\]

Choose a branch of \(\sqrt{A_1}\). Define the right resonance functional by
\[
\langle\phi_-|\psi_{z_0}^R\rangle
=
\sqrt{A_1}\left[
\overline{c_-}
+\lambda\int_{\Gamma_\theta}
\frac{V(\zeta)\phi_-^*(\zeta)}
{z_0-\zeta}\,d\zeta
\right],
\tag{6.2a}
\]
and the analytic left functional by
\[
\langle\psi_{z_0}^L|\phi_+\rangle
=
\sqrt{A_1}\left[
c_+
+\lambda\int_{\Gamma_\theta}
\frac{\overline{V(\bar\zeta)}\phi_+(\zeta)}
{z_0-\zeta}\,d\zeta
\right].
\tag{6.2b}
\]

These are continuous functionals on suitable analytic test spaces if the corresponding contour integrals are controlled by their defining seminorms.

The analytic left functional is not the Hilbert adjoint of the right resonance functional. Its analytic eigenvalue convention is \(z_0\); the Hilbert-adjoint functional carries \(z_0^*\). This distinction is essential in the later Liouville construction.

## 7. Deformed-continuum functionals

For \(\zeta\in\Gamma_\theta\setminus\{0\}\), let
\[
\eta_-(\zeta)=\eta(\zeta-i0_\theta),
\qquad
\eta_+(\zeta)=\eta(\zeta+i0_\theta)
\tag{7.1}
\]
denote the lower and upper boundary values relative to the oriented ray \(\Gamma_\theta\). Here \(i0_\theta\) denotes the boundary value relative to \(\Gamma_\theta\): parameterising \(\zeta=xe^{-i\theta}\) with \(x>0\),
\[
\frac{1}{\zeta-\zeta'-i0_\theta}\pm\frac{1}{\zeta-\zeta'+i0_\theta}
=\mathcal P\int_{\Gamma_\theta}\frac{d\zeta'}{\zeta-\zeta'}\mp i\pi\,\delta_{\Gamma_\theta}(\zeta-\zeta'),
\tag{7.2}
\]
with \(\delta_{\Gamma_\theta}\) the contour delta defined by \(\int_{\Gamma_\theta}\delta_{\Gamma_\theta}(\zeta-\zeta')f(\zeta')\,d\zeta'=f(\zeta)\), equivalently \(e^{+i\theta}\delta(x-x')\) in the radial variable.

The source note proposes the resolvent jump factorization
\[
\frac1{2\pi i}
\langle\phi_-|[R(\zeta)-R_+(\zeta)]|\phi_+\rangle
=
\langle\phi_-|\psi_\zeta^R\rangle
\langle\psi_\zeta^L|\phi_+\rangle,
\tag{7.3}
\]
for \(\zeta\in\Gamma_\theta\setminus\{0\}\), where the two resolvent boundary values are \(R(\zeta)=R(\zeta-i0_\theta)\) and \(R_+(\zeta)=R(\zeta+i0_\theta)\).

The corrected deformed-continuum functionals are
\[
\begin{aligned}
\langle\phi_-|\psi_\zeta^R\rangle
={}&\phi_-^*(\zeta)
+\frac{\lambda\overline{V(\bar\zeta)}}{\eta_-(\zeta)}
\left[
\overline{c_-}
+\lambda\int_{\Gamma_\theta}
\frac{V(\zeta')\phi_-^*(\zeta')}
{\zeta-\zeta'-i0_\theta}\,d\zeta'
\right],
\end{aligned}
\tag{7.4a}
\]
and
\[
\begin{aligned}
\langle\psi_\zeta^L|\phi_+\rangle
={}&\phi_+(\zeta)
+\frac{\lambda V(\zeta)}{\eta_+(\zeta)}
\left[
c_+
+\lambda\int_{\Gamma_\theta}
\frac{\overline{V(\bar\zeta')}\phi_+(\zeta')}
{\zeta-\zeta'+i0_\theta}\,d\zeta'
\right].
\end{aligned}
\tag{7.4b}
\]

**Proof status: to prove (factorization).** While the conjugation pairing and \(\eta_\mp(\zeta)\) denominator assignments in (7.4a)–(7.4b) are uniquely forced by the generalized eigenvalue equations (see Section 8), the resolvent jump factorization (7.3) is a logically distinct statement. It must be derived directly by substituting all four blocks of the resolvent (2.1), taking the two boundary values on the deformed contour, and verifying the resulting kernel—including the contour delta distributions and their Jacobians—rather than inferring it by analogy with the real-axis Lippmann–Schwinger formula.

A block-by-block verification of (7.3) from the corrected expressions (7.4) is carried out in the accompanying note `To establish the continuum resolvent jump.txt`; the key algebraic mechanism is that the discrete-sector jump
\[
\frac{1}{\eta_-(\zeta)}-\frac{1}{\eta_+(\zeta)}
=\frac{2\pi i\lambda^2J(\zeta)}{\eta_-(\zeta)\eta_+(\zeta)}
\tag{7.5}
\]
supplies the numerator that lets the four blocks reassemble into the rank-one product in (7.4). Had the coupling factors \(V(\zeta)\) and \(\overline{V(\bar\zeta)}\) been assigned to the opposite functionals, the cross-terms in the discrete–continuum and continuum–discrete blocks would have mismatched the numerator of (7.5) and factorization would fail.

## 8. Generalized eigenvalue equations

The intended right and analytic-left eigenvalue relations are
\[
\langle H\phi_-|\psi_{z_0}^R\rangle
=z_0\langle\phi_-|\psi_{z_0}^R\rangle,
\tag{8.1a}
\]
\[
\langle\psi_{z_0}^L|H\phi_+\rangle
=z_0\langle\psi_{z_0}^L|\phi_+\rangle,
\tag{8.1b}
\]
and, for \(\zeta\in\Gamma_\theta\),
\[
\langle H\phi_-|\psi_\zeta^R\rangle
=\zeta\langle\phi_-|\psi_\zeta^R\rangle,
\tag{8.2a}
\]
\[
\langle\psi_\zeta^L|H\phi_+\rangle
=\zeta\langle\psi_\zeta^L|\phi_+\rangle.
\tag{8.2b}
\]

For the resonance functional, the algebra uses
\[
\frac{\zeta'}{z_0-\zeta'}
=-1+\frac{z_0}{z_0-\zeta'}
\tag{8.3}
\]
and the continued dispersion relation
\[
z_0-\omega_1
-\lambda^2\int_{\Gamma_\theta}
\frac{J(\zeta')}{z_0-\zeta'}\,d\zeta'
=\eta_+(z_0)=0.
\tag{8.4}
\]

For the continuum functionals (7.4a)–(7.4b), testing against \(H\phi_-\) (with bra-side Schwarz reflection \(\overline{(H\phi_-)(\bar\zeta)}=\zeta\phi_-^*(\zeta)+\lambda\overline{V(\bar\zeta)}\,\overline{c_-}\)) and \(H\phi_+\) (with ket-side action \((H\phi_+)(\zeta)=\zeta\phi_+(\zeta)+\lambda V(\zeta)c_+\)) uses the boundary identity
\[
\frac{\zeta'}{\zeta-\zeta'\mp i0_\theta}
=-1+\frac{\zeta}{\zeta-\zeta'\mp i0_\theta},
\tag{8.5}
\]
together with the contour boundary dispersion relations
\[
\zeta-\omega_1
-\lambda^2\int_{\Gamma_\theta}
\frac{J(\zeta')}{\zeta-\zeta'\mp i0_\theta}\,d\zeta'
=\eta_\mp(\zeta).
\tag{8.6}
\]
In (8.2a), the inhomogeneous \(\overline{c_-}\) terms cancel precisely because the prefactor \(\lambda\overline{V(\bar\zeta)}/\eta_-(\zeta)\) pairs the reflected coupling with \(\eta_-(\zeta)\); symmetrically, in (8.2b), the \(c_+\) terms cancel because \(\lambda V(\zeta)/\eta_+(\zeta)\) pairs the unreflected coupling with \(\eta_+(\zeta)\).

**Proof status.** Both the resonance (8.1) and continuum (8.2) eigenvalue equations reduce directly to the algebraic identities (8.3)–(8.6) once the analytic test-space domain invariance under \(H\) and contour boundary operations are justified. Note that the eigenvalue equations fix the *pairings* in (7.4); they do not by themselves establish the factorization (7.3), which remains a separate obligation (Section 7).

## 9. Completeness and forward-time representation

The intended weak completeness relation is
\[
\begin{aligned}
\langle\phi_-|\phi_+\rangle
={}&
\langle\phi_-|\psi_{z_0}^R\rangle
\langle\psi_{z_0}^L|\phi_+\rangle\\
&+\int_{\Gamma_\theta}
\langle\phi_-|\psi_\zeta^R\rangle
\langle\psi_\zeta^L|\phi_+\rangle\,d\zeta.
\end{aligned}
\tag{9.1}
\]

If (5.4) and (7.3) hold, this follows formally by multiplying the resolvent representation by \(z\) and taking \(z=iy\), \(y\to+\infty\), using
\[
iy\,R(iy)\longrightarrow I
\]
strongly on the physical Hilbert space.

The limit on the contour side requires a dominated-convergence argument. In particular, it requires:
- local integrability at \(\zeta=0\);
- sufficient decay at infinity;
- a bound permitting the limit to pass through the contour integral;
- control of any boundary distributions in (7.4).

Thus (9.1) is a **conditional completeness theorem** until those estimates are supplied.

Under the same conditions, the intended forward-time expansion is
\[
\begin{aligned}
\langle\phi_-|e^{-iHt}|\phi_+\rangle
={}&e^{-iz_0t}
\langle\phi_-|\psi_{z_0}^R\rangle
\langle\psi_{z_0}^L|\phi_+\rangle\\
&+\int_{\Gamma_\theta}e^{-i\zeta t}
\langle\phi_-|\psi_\zeta^R\rangle
\langle\psi_\zeta^L|\phi_+\rangle\,d\zeta,
\qquad t\ge0.
\end{aligned}
\tag{9.2}
\]

The restriction \(t\ge0\) is consistent with the downward contour: for \(\zeta=xe^{-i\theta}\),
\[
|e^{-i\zeta t}|=e^{-x\sin\theta\,t}\le1.
\tag{9.3}
\]

The resonance term decays as \(e^{-\gamma t/2}\) at the amplitude level. The continuum term need not have a uniform exponential decay rate because the rotated continuum reaches the threshold at zero.

## 10. Bare-state sum rule

The bare state \(|1\rangle\) has \(c=1\) and vanishing continuum component. Evaluating (6.2) and the corrected continuum functionals (7.4) on \(|1\rangle\) gives
\[
\langle1|\psi_{z_0}^R\rangle=\sqrt{A_1},
\qquad
\langle\psi_{z_0}^L|1\rangle=\sqrt{A_1},
\tag{10.1}
\]
\[
\langle1|\psi_\zeta^R\rangle
=\frac{\lambda\overline{V(\bar\zeta)}}{\eta_-(\zeta)},
\qquad
\langle\psi_\zeta^L|1\rangle
=\frac{\lambda V(\zeta)}{\eta_+(\zeta)}.
\tag{10.2}
\]

If completeness (9.1) is established, then
\[
1=A_1+
\int_{\Gamma_\theta}
\frac{\lambda^2J(\zeta)}
{\eta_-(\zeta)\eta_+(\zeta)}\,d\zeta.
\tag{10.3}
\]

This is the bare-state spectral sum rule. It serves as a normalization and consistency check on the contour deformation.

Note that in (10.2) the continuum functionals of \(|1\rangle\) carry the *same* \(\eta_\mp\) denominators and coupling factors as in (7.4). This is the non-trivial consequence of the corrected pairings: the pre-correction version would have given \(\langle1|\psi_\zeta^R\rangle=\lambda V(\zeta)/\eta_+(\zeta)\), which is *not* the correct value and is incompatible with (7.5).

## 11. Threshold and large-energy estimates

A representative sufficient threshold hypothesis is
\[
J(xe^{-i\theta})=O(x^{2\alpha}),
\qquad \alpha>0,
\tag{11.1}
\]
together with
\[
\eta(0^-)=-\omega_1+
\lambda^2\int_0^\infty\frac{|V(\omega)|^2}{\omega}\,d\omega<0.
\tag{11.2}
\]

If the continued dispersion function is continuous at the threshold, then
\[
\eta_+(0)=\eta(0^-)\ne0.
\tag{11.3}
\]
Consequently, \(\eta^{-1}\) and \(\eta_+^{-1}\) are bounded in a sufficiently small threshold neighbourhood.

If the analytic test functions are bounded there, the local factors in the single-continuum integrands are integrable under (11.1). Double-contour integrals require the corresponding product estimates.

These threshold bounds do not replace the large-energy estimates. The latter must be stated for the actual integrands in (3.8), (7.4), and (9.1), and must be strong enough to justify contour deformation, Fubini/Tonelli interchange where used, and dominated convergence.

## 12. Weak-coupling threshold tails

Suppose, for illustration,
\[
J(\omega)\sim C\omega^{1/2}
\quad(\omega\downarrow0),
\tag{12.1}
\]
and the relevant denominators have finite nonzero limits at threshold. Then a single-continuum spectral weight of the form
\[
w(\omega)=
\frac{\lambda^2J(\omega)}
{\eta_-(\omega)\eta_+(\omega)}
\]
has leading behaviour \(w(\omega)\sim c\omega^{1/2}\). (Here \(\eta_\mp(\omega)=\eta(\omega\mp i0)\) are the real-axis boundary values; on the positive real axis the notation coincides with (7.1) restricted to \(\theta=0\).)

The endpoint contribution to a Fourier/Laplace integral therefore behaves, under the usual smoothness and non-cancellation conditions, as
\[
\int_0^\infty \omega^{1/2}e^{-i\omega t}\,d\omega
=O(t^{-3/2}).
\tag{12.2}
\]

This is an amplitude-level tail. The corresponding squared amplitude is of order \(t^{-3}\). A double-continuum Liouville contribution with two independent threshold weights of order \(\omega^{1/2}\) has a product tail of order \(t^{-3}\), provided the factorization and integrability assumptions hold.

The absence of a uniform spectral gap explains why a uniform exponential estimate is unavailable; it does not by itself establish the precise power law. The endpoint asymptotics establish that exponent.

## 13. Explicit boundary between Stage 1 and Stage 2

The one-particle construction above supplies:
- a resonance functional and a deformed-continuum family;
- a candidate biorthogonal spectral resolution;
- the bare-state sum rule;
- the data required for a tensor lift.

It does **not** by itself prove the Liouville-space completeness relation, distributional biorthogonality of all four sectors, or the existence of a Prigogine transformation.

The Liouville lift must separately specify:
1. the rigged Liouville test space and its topology;
2. the tensor-product/antidual construction;
3. the distributional meaning of continuum–continuum pairings;
4. the conjugate-contour orientation and Jacobian factors;
5. the domain on which the lifted resolution reconstructs a Hilbert–Schmidt operator.

The construction of \(\Lambda^{-1}\), its inverse, star-unitarity, the induced metric, and Lyapunov monotonicity are subsequent Stage 3 questions.

---

## 14. Outstanding proof obligations

| Item | Required verification |
|---|---|
| Spectral hypothesis | Establish absence of point and singular-continuous spectrum for the chosen form factor and coupling regime. |
| Analytic test space | Specify a dense nuclear space invariant under the operations used, with continuity of all evaluation and contour functionals. |
| Continuation | Prove the boundary-jump signs and analytic continuation for every factor in the matrix-element resolvent. |
| Contour deformation | Establish large-arc decay and threshold integrability for the actual integrands. |
| Continuum jump factorization | Derive (7.3) directly from all four resolvent blocks and the corrected functionals (7.4), including the \(i0_\theta\) distributions and Jacobians; the block-by-block computation in `To establish the continuum resolvent jump.txt` is the proposed proof, pending test-space justification. |
| Generalized eigenvalue equations | Continuum calculation now reduces to (8.3)–(8.6); the remaining obligation is the analytic test-space domain invariance. |
| Completeness | Prove the dominated-convergence bound needed to pass \(z=iy\to i\infty\) through the deformed-continuum integral. |
| Biorthogonality | Derive the distributional relations independently of completeness. The off-diagonal vanishing follows from the eigenvalue equations (8.1)–(8.2); the diagonal normalization \(\langle\psi_{z_0}^L|\psi_{z_0}^R\rangle=1\) and \(\langle\psi_\zeta^L|\psi_{\zeta'}^R\rangle=\delta_{\Gamma_\theta}(\zeta-\zeta')\) are conditional on the nuclear test space and should be verified in the test-space pairing, not inferred from (9.1) alone. |
| Bare-state sum rule | Verify (10.3) after the preceding completeness proof is complete. |

**Stage 1 conclusion:** The exact Friedrichs resolvent, its second-sheet dispersion function, and the resonance residue provide a sound starting point. The resonance-plus-continuum expansion is a promising and structurally appropriate representation. The corrected functionals (7.4) remove an algebraic inconsistency that would otherwise have prevented the generalized eigenvalue equations (8.2) from holding; the explicit block-by-block computation in `To establish the continuum resolvent jump.txt` supplies the resolvent jump factorization (7.3) with the corrected pairing. Full theorem-level status still depends on completing the endpoint estimates, the distributional completeness/biorthogonality proofs, and the specification of the nuclear test space.