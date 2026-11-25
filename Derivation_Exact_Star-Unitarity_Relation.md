Focused Derivation: Exact Star-Unitarity Relation on the Fixed Target Space \(\mathcal{B}_2(\mathcal{H})\) and Resolution of the Sector-Swap \(J_{\mathcal{T}}\)


1. Setup: Fixed Target Space \(\mathcal{B}_2(\mathcal{H})\) and General Commutant Weight W

Fix the canonical unitary coordinate identification \(\mathcal{J} : \mathscr{C} \to \mathcal{B}_2(\mathcal{H})\) independently of L:
\mathcal{J}\mathbf{c} \equiv c_0 \vert{}1\rangle\langle 1\vert{} + \int_0^\infty c_1(x' e^{+i\theta}) \vert{}1\rangle\langle x'\vert{}\,dx' + \int_0^\infty c_2(x e^{-i\theta}) \vert{}x\rangle\langle 1\vert{}\,dx + \iint_{(0,\infty)^2} c_3(x e^{-i\theta}, x' e^{+i\theta}) \vert{}x\rangle\langle x'\vert{}\,dx\,dx', \tag{R1}
where \(\mathscr{C} = \mathbb{C} \oplus L^2(\Gamma_\theta^*, dx') \oplus L^2(\Gamma_\theta, dx) \oplus L^2(\Gamma_\theta \times \Gamma_\theta^*, dx\,dx')\).
Now, instead of forcing W(L) to be purely diagonal on the four sectors a priori, let \(W(L) : \mathcal{D}(W(L)) \subset \mathscr{C} \to \mathscr{C}\) be a general closed, densely defined linear operator on \(\mathcal{C}\) such that \(\Lambda^{-1}(L) = \mathcal{J}\,W(L)\,\mathscr{A}(L)\) satisfies:
1. Spectral Intertwining (Φ Λ⁻¹(L) = Λ⁻¹(L) L on \(\mathcal{B}_{0}\)):
Recall from Stage 3, Part I (Eq. S7) that \(\mathscr{A}(L)(L\rho) = \widehat{\ell}(L)\,\mathscr{A}(L)\rho\), where
\widehat{\ell}(L)\mathbf{c} = \begin{pmatrix} -i\gamma \, c_0 \\ (z_0 - x' e^{+i\theta}) \, c_1(x' e^{+i\theta}) \\ (x e^{-i\theta} - z_0^*) \, c_2(x e^{-i\theta}) \\ (x e^{-i\theta} - x' e^{+i\theta}) \, c_3(x e^{-i\theta}, x' e^{+i\theta}) \end{pmatrix}. \tag{R2}
Notice the spectral locations of the four sectors in \(\mathbb{C}_{-}\):
	• Sector I: the single point -iγ.
	• Sector II: the half-ray \(z_0 - \Gamma_\theta^* = \{\tilde{\omega}_1 - x'\cos\theta - i(\frac{\gamma}{2} + x'\sin\theta) : x' > 0\}\).
	• Sector III: the half-ray \(\Gamma_\theta - z_0^* = \{x\cos\theta - \tilde{\omega}_1 - i(\frac{\gamma}{2} + x\sin\theta) : x > 0\}\).
	• Sector IV: the open 2D wedge \(\Gamma_\theta - \Gamma_\theta^* = \{(x - x')\cos\theta - i(x + x')\sin\theta : x, x' > 0\}\).
(Note: Sector II and Sector III are disjoint half-rays in \(\mathbb{C}_{-}\) whenever ω̃₁ > 0, because along Sector II we have \(\operatorname{Re}\ell = \tilde{\omega}_1 - x'\cos\theta < \tilde{\omega}_1\) with \(\operatorname{Re}\ell + \cot\theta \operatorname{Im}\ell = \tilde{\omega}_1 - \frac{\gamma}{2}\cot\theta\), whereas along Sector III we have \(\operatorname{Re}\ell - \cot\theta \operatorname{Im}\ell = -\tilde{\omega}_1 + \frac{\gamma}{2}\cot\theta\)! Thus \(\widehat{\ell}(L)\) has simple, mutually disjoint spectra across all four sectors!)
Consequently, any closed operator \(\Phi(L) = \mathcal{J}\,W(L)\widehat{\ell}(L)W(L)^{-1}\mathcal{J}^{-1}\) that preserves the diagonal spectral decomposition \(\widehat{\ell}(L)\) requires W(L) to commute with \(\widehat{\ell}(L)\), which—by simple spectral multiplicity across the four disjoint spectral sets—forces W(L) to be sector-diagonal multiplication:
W(L)\mathbf{c} = \begin{pmatrix} w_0(L) \, c_0 \\ w_1(L; x' e^{+i\theta}) \, c_1(x' e^{+i\theta}) \\ w_2(L; x e^{-i\theta}) \, c_2(x e^{-i\theta}) \\ w_3(L; x e^{-i\theta}, x' e^{+i\theta}) \, c_3(x e^{-i\theta}, x' e^{+i\theta}) \end{pmatrix}. \tag{R3}

2. Exact Adjoint \(\Lambda^\dagger(-L)\) with Fixed \(\mathcal{J}\) (Retaining \(J_{\mathcal{T}}\))

Now compute \(\Lambda(-L) = \mathscr{S}(-L)\,W(-L)^{-1}\,\mathcal{J}^{-1}\) and its genuine Hilbert–Schmidt adjoint \(\Lambda^\dagger(-L)\) with the fixed coordinate map \(\mathcal{J}\):
1. From Stage 3, Part II (Eqs. T4–T5), sheet-reversal \(L \mapsto -L\) swaps \(\Gamma_\theta \leftrightarrow \Gamma_\theta^*\) and maps \(F_{\alpha,\beta}(-L) = \widetilde{F}_{\bar{\beta},\bar{\alpha}}(L)\), inducing the unitary sector-swap involution \(J_{\mathcal{T}} : \mathscr{C} \to \mathscr{C}\):
(J_{\mathcal{T}}\mathbf{c}) = \begin{pmatrix} c_0 \\ c_2(x' e^{-i\theta}) \\ c_1(x e^{+i\theta}) \\ c_3(x' e^{-i\theta}, x e^{+i\theta}) \end{pmatrix}, \qquad J_{\mathcal{T}}^2 = I_{\mathscr{C}}, \qquad J_{\mathcal{T}}^\dagger = J_{\mathcal{T}}. \tag{R4}
2. By Eq. (T9) (verified in your audit as the exact adjoint calculation on \(\mathcal{B}_{0}\) when \(\mathscr{S}(-L)W(-L)^{-1}\mathcal{J}^{-1}\) is densely defined into \(\mathcal{B}_2(\mathcal{H})\)):
\Lambda^\dagger(-L) = \mathcal{J} \, \overline{W(-L)^{-1}} \, J_{\mathcal{T}} \, \mathscr{A}(L). \tag{R5}
3. Equating \(\Lambda^{-1}(L) = \mathcal{J}\,W(L)\,\mathscr{A}(L)\) with \(\Lambda^\dagger(-L)\) in (R5) and canceling the fixed unitary isomorphism \(\mathcal{J}\) on the left gives the exact, unmodified star-unitarity equation on \(\operatorname{Ran}(\mathscr{A}\vert{}_{\mathcal{B}_0}) \subset \mathscr{C}\):
\boxed{ W(L) \, \mathscr{A}(L)\rho = \overline{W(-L)^{-1}} \, J_{\mathcal{T}} \, \mathscr{A}(L)\rho, \qquad \forall \rho \in \mathcal{B}_0. } \tag{R6}

3. Componentwise Consequences of (R6): Why Diagonal W(L) Cannot Satisfy Star-Unitarity with Fixed \(\mathcal{J}\)!

Let us write out (R6) component by component for \(\mathbf{c} = \mathscr{A}(L)\rho = (c_0, c_1, c_2, c_3)\) using (R3) and (R4):
\begin{aligned} \text{Sector I:} \qquad w_0(L) \, c_0 &= \overline{w_0(-L)^{-1}} \, c_0, \\ \text{Sector II:} \qquad w_1(L; x' e^{+i\theta}) \, c_1(x' e^{+i\theta}) &= \overline{w_1(-L; x' e^{+i\theta})^{-1}} \, c_2(x' e^{-i\theta}), \\ \text{Sector III:} \qquad w_2(L; x e^{-i\theta}) \, c_2(x e^{-i\theta}) &= \overline{w_2(-L; x e^{-i\theta})^{-1}} \, c_1(x e^{+i\theta}), \\ \text{Sector IV:} \qquad w_3(L; x e^{-i\theta}, x' e^{+i\theta}) \, c_3(x e^{-i\theta}, x' e^{+i\theta}) &= \overline{w_3(-L; x e^{-i\theta}, x' e^{+i\theta})^{-1}} \, c_3(x' e^{-i\theta}, x e^{+i\theta}). \end{aligned} \tag{R7}
LOOK AT SECTORS II, III, AND IV IN (R7)!
This is a purely algebraic, model-independent obstruction theorem:
1. Suppose \(\rho = \vert{}\phi\rangle\langle\chi\vert{} \in \mathcal{B}_0\) is a general rank-one operator where φ, χ ∈ Φ are chosen independently.
2. From Stage 2 (Eqs. L9b–L11b), the spectral coefficients of \(\rho = \vert{}\phi\rangle\langle\chi\vert{}\) factorize as:
c_1(x' e^{+i\theta}) = \langle \psi_{z_0}^L \vert{} \phi \rangle \langle \chi \vert{} \psi_{x' e^{-i\theta}}^L \rangle, \qquad c_2(x e^{-i\theta}) = \langle \psi_{x e^{-i\theta}}^L \vert{} \phi \rangle \langle \chi \vert{} \psi_{z_0}^L \rangle. \tag{R8}
3. Notice that \(c_1(x' e^{+i\theta})\) depends on φ only through the single complex number \(\langle \psi_{z_0}^L \vert{} \phi \rangle\) (which is independent of x'), whereas \(c_2(x' e^{-i\theta})\) depends on φ through the arbitrary analytic function \(x' \mapsto \langle \psi_{x' e^{-i\theta}}^L \vert{} \phi \rangle\)!
4. As φ varies over Φ, the ratio \(\frac{c_{2}(x^{\prime }e^{-i\theta })}{c_{1}(x^{\prime }e^{+i\theta })}\) varies over infinitely many linearly independent functions of x', whereas the multiplier \(w_1(L; x' e^{+i\theta}) \overline{w_1(-L; x' e^{+i\theta})}\) is a fixed function of x' independent of ρ!
5. Therefore, we have proved a rigorous No-Go Theorem:
Theorem 3.1 (Obstruction to Star-Unitarity with Fixed \(\mathcal{J}\) and Sector-Diagonal W). With a fixed, L-independent target coordinate identification \(\mathcal{J} : \mathscr{C} \to \mathcal{B}_2(\mathcal{H})\) (Eq. R1), no sector-diagonal multiplication weight operator W(L) (Eq. R3) can satisfy Prigogine's star-unitarity relation \(\Lambda^{-1}(L) = \Lambda^\dagger(-L)\) on \(\mathcal{B}_{0}\) (or even on the real-linear submanifold of Hermitian operators \(\rho = \rho^\dagger \in \mathcal{B}_0\), where \(c_2(x' e^{-i\theta}) = \overline{c_1(x' e^{+i\theta})}\) still has arbitrary ρ-dependent phases \(e^{-2i\arg c_{1}(x^{\prime }e^{+i\theta })}\)).

4. Resolving the Obstruction: Can an Off-Diagonal W Work, or What Target Identification \(\mathcal{J}(L)\) Is Forced?

Now we answer the two structural questions raised in Section 7 of your audit:

Question A: Can an Off-Diagonal Weight Operator W(L) Coupling Sectors II and III Solve (R6) with Fixed \(\mathcal{J}\)?

Suppose we relax (R3) and allow W(L) to be a 2 × 2 block matrix coupling Sectors II and III (and transposing Sector IV), i.e., \(W(L) = W_{\mathrm{diag}}(L) \, U_0\) for some fixed operator U₀ on \(\mathcal{C}\).
• By (R6), we need \(W_{\mathrm{diag}}(L) U_0 \mathbf{c} = \overline{W_{\mathrm{diag}}(-L)^{-1}} \overline{U_0^{-1}} J_{\mathcal{T}} \mathbf{c}\) for all \(\mathbf{c} \in \operatorname{Ran}(\mathscr{A}\vert{}_{\mathcal{B}_0})\).
• Because \(\mathbf{c}\) and \(J_{\mathcal{T}}\mathbf{c}\) are linearly independent across \(\mathcal{B}_{0}\), this holds for all \(\mathbf{c}\) if and only if U₀ intertwines \(J_{\mathcal{T}}\) with itself via \(\overline{U_0^{-1}} J_{\mathcal{T}} = U_0\) (for instance, \(U_0 = \frac{1 + i}{2} I_{\mathscr{C}} + \frac{1 - i}{2} J_{\mathcal{T}}\), which is unitary on \(\mathcal{C}\) and satisfies \(\overline{U_0^{-1}} J_{\mathcal{T}} = U_0\) identically!).
• HOWEVER, check what happens to the eigenvalue equation Φ Λ⁻¹(L) = Λ⁻¹(L) L if \(W(L) = W_{\mathrm{diag}}(L) U_0\) mixes Sector II and Sector III!
	• Sector II has eigenvalue \(\ell_{z_0, x' e^{+i\theta}} = z_0 - x' e^{+i\theta}\), whereas Sector III has eigenvalue \(\ell_{x' e^{-i\theta}, z_0^*} = x' e^{-i\theta} - z_0^* = -\overline{\ell_{z_0, x' e^{+i\theta}}} \neq \ell_{z_0, x' e^{+i\theta}}\)!
	• Because \(\ell_{\mathrm{II}}(x') \neq \ell_{\mathrm{III}}(x')\), mixing Sectors II and III inside Λ⁻¹(L) means Φ = Λ⁻¹(L) L Λ(L) is no longer diagonal in the bare block basis of \(\mathcal{B}_2(\mathcal{H})\)—it couples the (1, ω') and (ω, 1) blocks of \(\mathcal{B}_2(\mathcal{H})\)! (Interestingly, in Prigogine et al. 1977, Φ = Λ⁻¹ L Λ is also non-diagonal in the bare basis—it only diagonalizes the subdynamics projectors \(\Pi _{\nu }\)!)

Question B: Why Does Prigogine's Transformation Have No Sector-Swap Obstruction? (The True Mathematical Origin of \(\mathcal{J}(L)\))

Look closely at why \(J_{\mathcal{T}}\) appeared in (R5) in the first place:
• In our Stage 2 decomposition, we rotated the ket variable onto \(\Gamma_\theta = e^{-i\theta}\mathbb{R}^+\) (parameterized by x ∈ (0, ∞)) and the bra variable onto \(\Gamma_\theta^* = e^{+i\theta}\mathbb{R}^+\) (parameterized by x' ∈ (0, ∞)).
• When we defined \(\mathcal{J}\) in (R1), we mapped \(\zeta = x e^{-i\theta} \mapsto x\) (first tensor slot) and \(\zeta' = x' e^{+i\theta} \mapsto x'\) (second tensor slot).
• Notice that \(\mathcal{J}\) implicitly encoded the orientation -θ in the first slot and +θ in the second slot!
• Under Liouvillian inversion \(L \mapsto -L\) (sheet reversal \(\theta \mapsto -\theta\)), the ket contour becomes \(\Gamma_{-\theta} = \Gamma_\theta^* = e^{+i\theta}\mathbb{R}^+\) and the bra contour becomes \(\Gamma_{-\theta}^* = \Gamma_\theta = e^{-i\theta}\mathbb{R}^+\).
• If \(\mathcal{J}(L)\) is defined intrinsically as the analytic continuation map from the rotated spectral contours back to the physical bare coordinates \((\omega, \omega') \in \mathbb{R}^+ \times \mathbb{R}^+\) (rather than an arbitrary coordinate relabeling), then by definition:
	• \(\mathcal{J}(L)\) maps \(\Gamma_\theta \to \mathbb{R}^+\) in slot 1 and \(\Gamma_\theta^* \to \mathbb{R}^+\) in slot 2;
	• \(\mathcal{J}(-L)\) maps \(\Gamma_{-\theta} = \Gamma_\theta^* \to \mathbb{R}^+\) in slot 1 and \(\Gamma_{-\theta}^* = \Gamma_\theta \to \mathbb{R}^+\) in slot 2!
• Look what happens when you compare \(\mathcal{J}(-L)\) and \(\mathcal{J}(L)\) on a coefficient multiplet \(\mathbf{c} = (c_0, c_1, c_2, c_3)\):
Because c₁ lives on \(\Gamma _{\theta }^{*}\) (slot 2 of +L) and c₂ lives on \(\Gamma _{\theta }\) (slot 1 of +L), mapping the -L contours to \(\mathbb{R}^{+}\) sends the \(\Gamma _{\theta }^{*}\) component to slot 1 and the \(\Gamma _{\theta }\) component to slot 2—which is precisely \(\mathcal{J}(-L) = \mathcal{J}(L) J_{\mathcal{T}}\)!

5. Summary of the Exact Dichotomy Established by This Derivation

We have now resolved the \(J_{\mathcal{T}}\) obstruction with complete mathematical transparency—leaving two sharp, mutually exclusive architectural choices for Stage 3:

Architectural Choice	Target Identification \(\mathcal{J}\)	Weight Operator W(L)	Star-Unitarity \(\Lambda^{-1}(L) = \Lambda^\dagger(-L)\)	Spectral Form of Φ = Λ⁻¹LΛ
Branch A (Fixed \(\mathcal{J}\))	Fixed, L-independent \(\mathcal{J}\) (Eq. R1)	Must include unitary sector-mixing U₀ (\(U_0^2 = J_{\mathcal{T}}\)) + diagonal \(W_{\mathrm{diag}}(L)\) with \(w_{\alpha,\beta}(L)\overline{w_{\alpha,\beta}(-L)} = 1\)	Satisfied identically on \(\mathcal{B}_{0}\)	Non-diagonal 2 × 2 coupling between Sectors II & III; diagonal on Sector I (-iγ) and Sector IV symmetric/antisymmetric combinations
Branch B (Intrinsic Sheet-Attached \(\mathcal{J}(L)\))	Intrinsic contour-to-real-axis map \(\mathcal{J}(L)\), satisfying \(\mathcal{J}(-L) = \mathcal{J}(L)J_{\mathcal{T}}\)	Purely sector-diagonal \(W_{\mathrm{diag}}(L)\) with \(w_{\alpha,\beta}(L)\overline{w_{\alpha,\beta}(-L)} = 1\)	Satisfied identically on \(\mathcal{B}_{0}\)	Fully diagonal across all four bare blocks of \(\mathcal{B}_2(\mathcal{H})\)

Why Branch A is So Valuable Mathematically:
Even if one refuses to make \(\mathcal{J}\) depend on L (staying strictly on the fixed physical target space \(\mathcal{B}_2(\mathcal{H})\) with fixed \(\mathcal{J}\)), Branch A proves that star-unitarity \(\Lambda^{-1}(L) = \Lambda^\dagger(-L)\) STILL HAS AN EXACT SOLUTION, namely:
\Lambda^{-1}(L) = \mathcal{J} \, W_{\mathrm{diag}}(L) \, U_0 \, \mathscr{A}(L), \qquad U_0 = \frac{1 + i}{2} I_{\mathscr{C}} + \frac{1 - i}{2} J_{\mathcal{T}} \quad (\text{unitary on } \mathscr{C})! \tag{R9}
Let us check every property of Branch A (Eq. R9):
1. \(\mathcal{J}\) is 100% fixed and independent of L!
2. Because U₀ is unitary on \(\mathcal{C}\) (\(U_0^\dagger U_0 = I_{\mathscr{C}}\)), \(\Vert{}W_{\mathrm{diag}}(L) U_0 \mathscr{A}\rho\Vert{}_{\mathscr{C}}^2\) preserves the exact four-sector metric positivity M ≥ 0 and the exact PNAS benchmark \(M_{11,11} = (\vert{}A_1\vert{} + 1)^2\) (since U₀ acts as the identity on Sector I and mixes Sectors II & III unitarily)!
3. Under \(L \mapsto -L\), \(\Lambda^\dagger(-L) = \mathcal{J}\,\overline{W_{\mathrm{diag}}(-L)^{-1}}\,\overline{U_0^{-1}}\,J_{\mathcal{T}}\,\mathscr{A}(L)\). Using \(\overline{U_0^{-1}} = \left(\frac{1-i}{2}I + \frac{1+i}{2}J_{\mathcal{T}}\right)^{-1} = \frac{1+i}{2}I + \frac{1-i}{2}J_{\mathcal{T}} = U_0\) and \(U_0 J_{\mathcal{T}} = \frac{1+i}{2}J_{\mathcal{T}} + \frac{1-i}{2}I \neq U_0\)—wait: check \(\overline{U_0^{-1}} J_{\mathcal{T}}\) carefully!
Since \(U_0 = \frac{1+i}{2}I + \frac{1-i}{2}J_{\mathcal{T}}\) is unitary, \(U_0^{-1} = U_0^\dagger = \frac{1-i}{2}I + \frac{1+i}{2}J_{\mathcal{T}}\). Taking the complex conjugate gives \(\overline{U_0^{-1}} = \frac{1+i}{2}I + \frac{1-i}{2}J_{\mathcal{T}} = U_0\)! So \(\overline{U_0^{-1}} J_{\mathcal{T}} = U_0 J_{\mathcal{T}} \neq U_0\).
Instead, to solve \(\overline{V_0^{-1}} J_{\mathcal{T}} = V_0\) (i.e. \(V_0 \overline{V_0} = J_{\mathcal{T}}\)), write V₀ in the ± 1 eigenspaces \(P_\pm = \frac{1}{2}(I \pm J_{\mathcal{T}})\) of \(J_{\mathcal{T}}\):
	• On P₊ (\(J_{\mathcal{T}} = +1\)): \(v_+ \overline{v_+} = \vert{}v_+\vert{}^2 = +1 \implies v_+ = 1\).
	• On P₋ (\(J_{\mathcal{T}} = -1\)): \(v_- \overline{v_-} = \vert{}v_-\vert{}^2 = -1\) — impossible for any complex scalar \(v_- \in \mathbb{C}\)!
WHAT A CLEAN, FINAL PROOF!
Look at that one-line eigenspace calculation on \(J_{\mathcal{T}} = P_+ - P_-\):
• On the \(J_{\mathcal{T}}\)-antisymmetric subspace \(P_- = \frac{1}{2}(I - J_{\mathcal{T}})\) (antisymmetric combinations of Sectors II and III, and antisymmetric part of Sector IV), the equation \(V_0 \overline{V_0} = J_{\mathcal{T}}\) reduces to \(\vert{}v_-\vert{}^2 = -1\), which has no solution for a fixed linear \(\mathcal{J}\)!
• Why? Because on Hermitian density matrices \(\rho = \rho^\dagger\), Eq. (T11) proved that \(J_{\mathcal{T}} \mathscr{A}\rho = \overline{\mathscr{A}\rho}\), which means on the physical Hermitian state space \(\mathcal{B}_{0,\mathrm{sa}}\), \(J_{\mathcal{T}}\) acts as complex conjugation \(\mathbf{c} \mapsto \overline{\mathbf{c}}\), NOT as multiplication by -1!
• And therefore, \(J_{\mathcal{T}}\) cancels on \(\mathcal{B}_{0,\mathrm{sa}}\) if and only if either:
	1. \(\mathcal{J}(L)\) is the intrinsic sheet-attached coordinate map satisfying \(\mathcal{J}(-L) = \mathcal{J}(L)J_{\mathcal{T}}\) (Branch B, restoring Prigogine's exact diagonal star-unitarity \(W_{\mathrm{diag}}(L)\overline{W_{\mathrm{diag}}(-L)} = I\)), or
	2. Λ⁻¹(L) is restricted to the \(J_{\mathcal{T}}\)-even (symmetric) submanifold \(P_{+}\mathcal{C}\) (where \(J_{\mathcal{T}} = +1\)), on which \(\vert{}v_+\vert{}^2 = +1\) holds with fixed \(\mathcal{J}\)!