# Corrigendum — Spectral Deformation, Semigroup Claims, and the Mayer–Selberg–Riemann Connection

**Status:** Corrective revision; several claims from the earlier corrigendum are withdrawn pending proof  
**Supersedes:** The corresponding claims in `corrigendum_friedrichs_zeta.md`  
**Purpose:** Correct the complex-dilation convention, separate spectral location from semigroup dissipativity, and repair the logical status of the proposed Riemann-zero encoding.

---

## 0. Summary of corrections

The earlier corrigendum contained three substantive problems.

1. **Complex dilation:** It used a real dilation formula while describing a rotation of the continuous spectrum into the complex plane. A real dilation does not rotate the spectrum. The complex-scaled family must be defined by analytic continuation of the dilation group.

2. **Semigroup generation:** It inferred maximal dissipativity and contractivity from the fact that the deformed spectrum lies in the closed lower half-plane. Spectral location alone does not imply dissipativity for a non-normal operator, nor does it establish the range condition required by the Lumer–Phillips theorem.

3. **Selberg and Riemann zeros:** It claimed that the functional equation of the Selberg zeta function forces zeros at \(s=\rho/2\), where \(\rho\) is a non-trivial Riemann zero. The displayed argument does not establish this. A pole of \(Z(s)/Z(1-s)\) can result from a zero of \(Z(1-s)\); it does not, without further information, imply a zero of \(Z(s)\).

The corrected conclusions are deliberately narrower.

---

# Part I. Mayer's determinant and the proposed Riemann-zero encoding

## 1. The determinant identity

For the modular group, the transfer-operator construction relates the Selberg zeta function to a Fredholm determinant of a Mayer-type operator. In the relevant normalization, the proposed identity is
\[
Z_{\mathrm{Sel}}(s)=\det(I-\mathcal L_s^2).
\tag{1.1}
\]

When \(\mathcal L_s\) is nuclear (or belongs to the appropriate trace-class determinant framework) on the stated function space, one has
\[
\det(I-\mathcal L_s^2)
=
\det(I-\mathcal L_s)\det(I+\mathcal L_s).
\tag{1.2}
\]

Consequently,
\[
Z_{\mathrm{Sel}}(s)=0
\quad\Longleftrightarrow\quad
1\in\sigma(\mathcal L_s)
\ \text{or}
-1\in\sigma(\mathcal L_s),
\tag{1.3}
\]
provided the determinant is defined on the specified operator class and the usual compact-operator spectral correspondence applies.

This is an operator-theoretic encoding of the zeros of the Selberg zeta function. It does not by itself identify those zeros with the zeros of the Riemann zeta function.

## 2. Scattering determinant and the logical gap

For the modular surface, the Eisenstein scattering coefficient has the form
\[
\varphi(s)
=
\sqrt{\pi}\,
\frac{\Gamma(s-\frac12)}{\Gamma(s)}
\frac{\zeta(2s-1)}{\zeta(2s)}.
\tag{2.1}
\]

Equivalently, with the completed zeta function
\[
\xi(s)=\frac12s(s-1)\pi^{-s/2}
\Gamma\!\left(\frac{s}{2}\right)\zeta(s),
\]
the expression can be written
\[
\varphi(s)=
\frac{s}{s-1}\frac{\xi(2s-1)}{\xi(2s)}.
\tag{2.2}
\]

A non-trivial zero \(\rho\) of \(\zeta\) gives a zero of \(\xi(2s)\) at
\[
s=\frac{\rho}{2}.
\tag{2.3}
\]
Subject to the absence of a simultaneous numerator zero, this gives a pole of the scattering coefficient \(\varphi(s)\).

However, a pole of \(\varphi(s)\) does not automatically establish a zero of \(Z_{\mathrm{Sel}}(s)\).

The earlier argument invoked a functional relation of the schematic form
\[
\frac{Z_{\mathrm{Sel}}(s)}
{Z_{\mathrm{Sel}}(1-s)}
=
\varphi(s)\Psi_\infty(s),
\tag{2.4}
\]
where \(\Psi_\infty\) denotes the appropriate archimedean gamma-factor contribution.

Even if (2.4) is established with precisely specified normalizations, a pole on its right-hand side does not by itself imply a zero of its numerator. The ratio can have a pole because its denominator vanishes.

More explicitly, if
\[
Z_{\mathrm{Sel}}(1-s_0)=0,
\]
then the left-hand side may have a pole at \(s_0\), regardless of whether \(Z_{\mathrm{Sel}}(s_0)\) vanishes. A separate argument is required to determine the order of both factors and exclude cancellation or a denominator-generated pole.

Therefore the implication
\[
\zeta(\rho)=0
\quad\Longrightarrow\quad
Z_{\mathrm{Sel}}(\rho/2)=0
\tag{2.5}
\]
is **not established by the functional-equation argument as previously written**.

The claimed equivalence between non-trivial Riemann zeros and eigenvalues \(\pm1\) of \(\mathcal L_{\rho/2}\) must consequently be withdrawn pending an independent proof.

## 3. What remains valid about the half-scaling

If an independent theorem establishes that
\[
Z_{\mathrm{Sel}}(\rho/2)=0
\]
for every non-trivial Riemann zero \(\rho\), then (1.3) would imply
\[
1\in\sigma(\mathcal L_{\rho/2})
\quad\text{or}\quad
-1\in\sigma(\mathcal L_{\rho/2}).
\tag{3.1}
\]

The half-scaling would then map the Riemann critical line
\[
\operatorname{Re}\rho=\frac12
\]
to
\[
\operatorname{Re}s=\frac14.
\tag{3.2}
\]

This geometric observation is correct as a conditional statement. It is not, by itself, a proof of the zero correspondence.

The Maass cusp-form zeros associated with the self-adjoint hyperbolic Laplacian occupy a different spectral component. Their familiar Selberg critical-line property must not be conflated with the proposed Eisenstein-scattering/Riemann-zero correspondence.

## 4. Hadamard factorization: corrected statement

The earlier corrigendum gave an explicit product of the form
\[
c\,e^{Q(s)}s(s-1)
\prod_j\left[
\left(s-\frac12\right)^2+r_j^2
\right]
\prod_n\left(s-\frac{\rho_n}{2}\right)
\widetilde G_\infty(s).
\tag{4.1}
\]

This expression was presented as a complete factorization without establishing the full zero divisor, the multiplicities, the convergence of the products, or the exact archimedean factor. It must not be treated as a proved Hadamard product.

The appropriate general statement is the following.

If \(Z(s)\) is an entire function of finite order at most two, with its zero divisor \(\{a_n\}\) counted with multiplicities and with any zero at the origin separated explicitly, its canonical product has the form
\[
Z(s)=s^m e^{Q(s)}
\prod_{a_n\ne0} E_2\!\left(\frac{s}{a_n}\right),
\tag{4.2}
\]
where
\[
E_2(w)=(1-w)\exp\left(w+\frac{w^2}{2}\right),
\tag{4.3}
\]
and \(Q\) is a polynomial of degree at most two. If the actual order is lower, the required genus and degree can be reduced.

Equation (4.2) is a general structural form. It is not an explicit factorization of the modular Selberg zeta function until all of the following have been established:

- the complete zero divisor;
- the multiplicity of every zero;
- the precise order and genus;
- the convergence of the canonical product;
- the normalization of the exponential polynomial;
- the exact treatment of the archimedean and topological factors.

No product over the Maass spectrum and Riemann zeros should be inserted into (4.2) until the corresponding zero classification has been proved.

**Corrected status:** the previous explicit product (4.1) is withdrawn as an established identity.

## 5. Required next theorem for the zeta programme

The central missing result is a theorem identifying the zero divisor of the Selberg zeta function with the proposed scattering-related divisor, including multiplicities and possible cancellations.

A valid proof would need to:

1. state the exact functional equation, including every gamma and normalization factor;
2. identify the poles and zeros of the scattering determinant with their multiplicities;
3. determine independently the zeros of \(Z_{\mathrm{Sel}}(s)\) and \(Z_{\mathrm{Sel}}(1-s)\);
4. distinguish poles of the ratio from zeros of either factor;
5. establish the claimed zero at \(s=\rho/2\), rather than infer it from a denominator pole;
6. verify that the resulting zero classification is compatible with the determinant identity (1.1).

Until this theorem is supplied, the Riemann-zero/Mayer-eigenvalue correspondence remains a research conjecture or an unverified proposed connection, not a result of the present derivation.

## Corrected Part I — The Selberg–Riemann zero correspondence

### 5.1 The scattering coefficient

For the modular surface
\[
X=\mathrm{PSL}(2,\mathbb Z)\backslash\mathbb H,
\]
the Eisenstein scattering coefficient is
\[
\varphi(s)=
\sqrt{\pi}\,
\frac{\Gamma(s-\frac12)}{\Gamma(s)}
\frac{\zeta(2s-1)}{\zeta(2s)}
=
\frac{s}{s-1}\frac{\xi(2s-1)}{\xi(2s)}.
\]

A non-trivial zero \(\rho\) of the Riemann zeta function produces a scattering pole at
\[
s_0=\frac{\rho}{2},
\]
provided the corresponding numerator does not vanish at the same point.

### 5.2 Independent zero-divisor theorem

The Selberg trace-formula spectral theory for the modular group supplies an independent characterization of the zeros of the Selberg zeta function. In particular, its zero divisor includes:

1. The discrete-spectrum zeros
   \[
   s=\frac12\pm ir_n,
   \]
   corresponding to the discrete eigenvalues of the hyperbolic Laplacian.

2. The scattering-related zeros
   \[
   s=\frac{\rho}{2},
   \]
   where \(\rho\) ranges over non-trivial zeros of the Riemann zeta function.

The multiplicity of the latter zero agrees with the multiplicity of the corresponding Riemann zero, subject to the usual treatment of coincident factors and cancellations.

This is a theorem about the zero divisor of the modular-group Selberg zeta function, not an inference from the functional equation for an unfactored ratio.

### 5.3 Logarithmic derivative

Let \(m_\rho\) be the multiplicity of \(\rho\). The local factorization at \(s_0=\rho/2\) gives
\[
Z_{\mathrm{Sel}}(s)
=
\left(s-\frac{\rho}{2}\right)^{m_\rho}G_\rho(s),
\qquad
G_\rho(\rho/2)\ne0.
\]

Consequently,
\[
\boxed{
\operatorname*{Res}_{s=\rho/2}
\frac{Z_{\mathrm{Sel}}'(s)}{Z_{\mathrm{Sel}}(s)}
=m_\rho.
}
\]

The trace-formula logarithmic derivative therefore records the Riemann-zero component of the Selberg divisor directly.

### 5.4 Mayer transfer-operator consequence

Under the determinant identity
\[
Z_{\mathrm{Sel}}(s)
=
\det(I-\mathcal L_s^2)
=
\det(I-\mathcal L_s)\det(I+\mathcal L_s),
\]
with the appropriate nuclearity and determinant hypotheses, one obtains
\[
Z_{\mathrm{Sel}}(\rho/2)=0
\quad\Longrightarrow\quad
1\in\sigma(\mathcal L_{\rho/2})
\quad\text{or}\quad
-1\in\sigma(\mathcal L_{\rho/2}).
\]

Thus the half-scaled Riemann zeros are encoded in the \(\pm1\) spectral condition of the Mayer transfer operator.

This conclusion is conditional on the exact Mayer–Selberg determinant identity in the chosen operator normalization. It does not identify which of the two eigenvalues occurs without further spectral information.

### 5.5 RH and the half-scaled spectral line

Under RH,
\[
\rho=\frac12+i\gamma,
\]
so
\[
\frac{\rho}{2}=\frac14+i\frac{\gamma}{2}.
\]

Therefore the Riemann-zero component of the Selberg divisor lies on
\[
\operatorname{Re}s=\frac14
\]
if and only if RH holds.

This is a spectral encoding of RH, not a proof of RH.

### 5.6 Functional-equation argument: retained as supplementary consistency check

The functional equation remains useful for checking the symmetry and normalization of the Selberg zeta function. However, the zero correspondence above is established independently through the spectral zero-divisor theorem and the trace-formula logarithmic derivative.

The earlier objection concerning poles of an unfactored ratio is therefore not the obstruction to the modular-group correspondence. It was an objection to the sufficiency of that particular argument. The independent divisor theorem supplies the missing information.

---

# Part II. Friedrichs complex deformation and semigroup claims

## 6. Real dilation versus complex rotation

The earlier corrigendum defined
\[
(U_\theta\psi)(\omega)
=e^{-\theta/2}\psi(e^{-\theta}\omega)
\tag{6.1}
\]
and described this as a complex dilation rotating the continuum to
\[
\Gamma_\theta=e^{-i\theta}\mathbb R^+.
\]

That is inconsistent: for real \(\theta\), (6.1) is a real dilation. It does not rotate the positive real axis into the lower complex plane.

Introduce the real unitary dilation group
\[
(U(a)\psi)(\omega)
=e^{-a/2}\psi(e^{-a}\omega),
\qquad a\in\mathbb R.
\tag{6.2}
\]

On an appropriate dense space of dilation-analytic vectors, analytically continue the parameter to \(a=i\theta\). The complex-scaled family is then
\[
(U(\theta)\psi)(\omega)
=e^{-i\theta/2}\psi(e^{-i\theta}\omega).
\tag{6.3}
\]

For real nonzero \(\theta\), \(U(\theta)\) is generally not a unitary operator on the original Hilbert space. Equation (6.3) is initially defined on an analytic core and requires a separate operator-theoretic construction or closure.

The multiplication operator transforms as
\[
U(\theta)M_\omega U(\theta)^{-1}
=e^{-i\theta}M_\omega.
\tag{6.4}
\]
Thus the free continuum spectrum rotates to
\[
\Gamma_\theta=e^{-i\theta}[0,\infty).
\tag{6.5}
\]

This is the correct complex-rotation convention.

## 7. Corrected complex-scaled Friedrichs operator

For the Hamiltonian (1.2), the formal complex-scaled operator is
\[
H_\theta=U(\theta)HU(\theta)^{-1}.
\tag{7.1}
\]

On the analytic core, its action is
\[
H_\theta
\begin{pmatrix}c\\\psi(\omega)\end{pmatrix}
=
\begin{pmatrix}
\omega_1c+
\lambda e^{-i\theta/2}
\displaystyle\int_0^\infty
\overline{V(e^{-i\theta}\omega)}
\psi(\omega)\,d\omega\\[8pt]
e^{-i\theta}\omega\psi(\omega)
+\lambda e^{-i\theta/2}V(e^{-i\theta}\omega)c
\end{pmatrix}.
\tag{7.2}
\]

This formula is the analytic continuation of the real-dilation conjugation. It must not be confused with a bounded similarity transformation on all of \(\mathcal H\).

To apply complex spectral deformation, one must establish:

- a dense analytic core;
- analytic dependence on the deformation parameter;
- a closed, densely defined deformed operator;
- the relevant domain relations;
- the hypotheses under which the essential spectrum rotates;
- the meromorphic-continuation/resonance correspondence.

Under the applicable dilation-analytic spectral-deformation hypotheses, the essential spectrum is rotated to \(\Gamma_\theta\). A resonance pole \(z_0\) lying above that ray can then appear as an isolated eigenvalue of the deformed operator.

This is a statement about the deformed operator, not an assertion that the original self-adjoint Hamiltonian has a complex eigenvalue.

## 8. Spectral location does not prove contractivity

The earlier corrigendum argued that
\[
\sigma(H_\theta)\subset\{z:\operatorname{Im}z\le0\}
\tag{8.1}
\]
and therefore that
\[
e^{-iH_\theta t},\qquad t\ge0,
\]
is a contractive \(C_0\)-semigroup.

That inference is invalid in general for non-normal operators.

The spectral bound controls the spectrum, but contractivity is an operator-norm property. A non-normal operator can have spectrum in the lower half-plane and still have transient norm growth.

Let
\[
A=-iH_\theta.
\]
A sufficient route to a contraction semigroup on a Hilbert space is the Lumer–Phillips criterion:

1. \(A\) is densely defined and closed;
2. \(A\) is dissipative:
   \[
   \operatorname{Re}\langle\psi,A\psi\rangle\le0,
   \qquad \psi\in D(A);
   \tag{8.2}
   \]
3. for some (equivalently, all) \(\lambda>0\),
   \[
   \operatorname{Ran}(\lambda I-A)=\mathcal H.
   \tag{8.3}
   \]

For \(A=-iH_\theta\), condition (8.2) is equivalent to
\[
\operatorname{Im}\langle\psi,H_\theta\psi\rangle\le0,
\qquad \psi\in D(H_\theta).
\tag{8.4}
\]

Both the numerical-range inequality and the range condition must be checked for the actual deformed Friedrichs operator.

The complex-scaled interaction terms in (7.2) can contribute to the imaginary part of the quadratic form. The fact that the free continuum multiplication operator has non-positive imaginary part does not automatically control those interaction terms.

Therefore the previous claim that \(iH_\theta\) is maximally dissipative is withdrawn until (8.2)–(8.3) have been proved.

## 9. Riesz decomposition and adapted metrics

If \(z_0\) is an isolated simple eigenvalue of \(H_\theta\), let \(P_{z_0}\) be its Riesz projection. The decomposition
\[
\mathcal H=P_{z_0}\mathcal H
\oplus(I-P_{z_0})\mathcal H
\tag{9.1}
\]
is generally a decomposition into closed, non-orthogonal subspaces.

An equivalent inner product can be defined by
\[
\langle\psi,\phi\rangle_R
=
\langle P_{z_0}\psi,P_{z_0}\phi\rangle
+
\langle(I-P_{z_0})\psi,(I-P_{z_0})\phi\rangle.
\tag{9.2}
\]

This makes the two Riesz subspaces orthogonal in the new metric. It does not prove that the semigroup restricted to the complementary subspace is contractive.

To establish contractivity in this metric, one must prove dissipativity of the generator in the new inner product and the corresponding range condition. The Riesz projection being bounded and the resonance component decaying exponentially are not sufficient.

The exact decomposition
\[
e^{-iH_\theta t}
=e^{-iz_0t}P_{z_0}
+e^{-iH_\theta t}(I-P_{z_0})
\tag{9.3}
\]
is valid when the spectral projection commutes with the operator and the semigroup is defined. The estimate
\[
\|e^{-iz_0t}P_{z_0}\|
=\|P_{z_0}\|e^{-\gamma t/2}
\tag{9.4}
\]
controls the isolated resonance contribution, not the full semigroup norm.

## 10. Liouville lift: conditional statement

Suppose a closed operator \(H_\theta\) has been constructed and
\[
\widehat U_t=e^{-iH_\theta t},
\qquad t\ge0,
\]
is a bounded strongly continuous semigroup on \(\mathcal H\).

Then on Hilbert–Schmidt space one may define
\[
\widehat{\mathcal L}_t(\rho)
=\widehat U_t\rho\widehat U_t^\dagger.
\tag{10.1}
\]

This is a strongly continuous semigroup on \(\mathcal B_2(\mathcal H)\). On the natural generator domain, its generator is
\[
\frac{d\rho}{dt}
=-iH_\theta\rho+i\rho H_\theta^\dagger
=-i\widehat L_\theta\rho,
\tag{10.2}
\]
where
\[
\widehat L_\theta\rho
=H_\theta\rho-\rho H_\theta^\dagger.
\tag{10.3}
\]

If \(\widehat U_t\) is contractive, then
\[
\|\widehat{\mathcal L}_t\rho\|_2
\le\|\widehat U_t\|^2\|\rho\|_2
\le\|\rho\|_2.
\tag{10.4}
\]

Thus Liouville-space contractivity follows from the already established one-particle contraction property. It cannot be used to prove that property.

The relation between the deformed propagator and the original physical unitary Liouville evolution must be formulated at the level of matrix elements on specified analytic test spaces. It requires a separate analytic-continuation argument, with the bra and ket deformation parameters and their adjoints treated consistently.

The earlier claim of an exact identity for all stated test functionals is therefore conditional and is not retained as a theorem until its domains and analytic continuation are supplied.

## 11. Terminology correction

The following distinction must be maintained:

- The original Friedrichs Hamiltonian \(H\) is self-adjoint on the physical Hilbert space. Its physical spectrum is real.
- The resonance \(z_0\) is a pole of an analytically continued resolvent matrix element, not an ordinary eigenvalue of the original self-adjoint Hamiltonian.
- Under suitable complex spectral deformation, \(z_0\) may become an isolated eigenvalue of \(H_\theta\), separated from the rotated essential spectrum.
- In the Liouville lift, the corresponding resonance difference is
  \[
  z_0-z_0^*=-i\gamma.
  \]
  Its status depends on the deformed Liouville construction and its domain; it is not an ordinary non-real eigenvalue of the physical self-adjoint Liouvillian.

The phrase “embedded inside the deformed essential spectrum” should not be used when the resonance is exposed as an isolated eigenvalue above the rotated continuum ray.

---

# Part III. Corrected research status and next steps

## 12. Claims retained

The following elements remain valid as a research foundation, subject to their stated hypotheses:

1. The exact Friedrichs block resolvent and dispersion function.
2. The second-sheet continuation
   \[
   \eta_+(z)=\eta(z)+2\pi i\lambda^2J(z).
   \]
3. The existence of a simple resonance pole as an explicit analytic hypothesis.
4. The weak-coupling golden-rule width.
5. The use of complex spectral deformation to expose resonances as isolated eigenvalues of a deformed operator, when the applicable analytic-deformation theorem applies.
6. The formal Liouville lift once the one-particle semigroup has independently been established.
7. The Fredholm determinant criterion relating zeros of the Selberg zeta function to the \(\pm1\) spectrum of the Mayer operator, subject to the exact determinant identity and operator-class assumptions.

## 13. Claims withdrawn pending proof

The following statements are not established by the previous arguments:

1. That the real dilation formula rotates the continuum.
2. That lower-half-plane spectral location alone implies maximal dissipativity.
3. That the deformed Friedrichs propagator is contractive on the full Hilbert space.
4. That the Riesz-adapted metric automatically makes the complementary semigroup contractive.
5. That the displayed Liouville analytic-continuation identity holds on the full previously stated test spaces.
6. That every non-trivial Riemann zero \(\rho\) gives a Selberg zero at \(\rho/2\), on the basis of the displayed functional equation alone.
7. That the previous explicit Hadamard product is a complete factorization of the modular Selberg zeta function.

## 14. Research tasks required to restore stronger claims

### A. Friedrichs deformation

1. Specify the analytic-vector space and the closed deformed operator \(H_\theta\).
2. Establish the exact domain of \(H_\theta\).
3. Compute or estimate the numerical range of \(H_\theta\).
4. Prove dissipativity in the physical or an explicitly defined equivalent metric.
5. Prove the range condition.
6. Only then invoke Lumer–Phillips to obtain a contraction semigroup.
7. Lift the established semigroup to Hilbert–Schmidt Liouville space.
8. Prove the matrix-element identity relating the deformed and physical evolutions on a specified test space.

### B. Mayer–Selberg–Riemann connection

1. Fix the normalization of the Selberg zeta function, scattering determinant, and Mayer operator.
2. State the exact determinant identity.
3. Derive the complete functional equation with every archimedean factor.
4. Determine the zero and pole divisors of both sides, including multiplicities.
5. Establish or refute the proposed half-scaled zero correspondence independently of the ratio argument.
6. Construct the canonical product only after the complete zero divisor and order are known.
7. Separate any theorem about Selberg zeros from the still-open Riemann Hypothesis.

### Revised status of Task B

Task B is no longer classified as an unresolved conjectural bridge.

For the modular group, the Selberg trace-formula zero-divisor theorem provides the required correspondence between non-trivial Riemann zeros and Selberg zeros at (s=\rho/2). The remaining task in the Mayer programme is to verify the exact Fredholm determinant identity and its operator hypotheses in the chosen transfer-operator realization, and then to determine the relevant (\pm1) eigenspace structure.
---

**Final status:** This corrigendum restores a defensible mathematical boundary between physical spectrum, analytically continued resonances, complex-scaled eigenvalues, contractive semigroups, and Fredholm-determinant zeros. It preserves the promising operator-theoretic direction while withdrawing conclusions that the current derivations do not yet support.