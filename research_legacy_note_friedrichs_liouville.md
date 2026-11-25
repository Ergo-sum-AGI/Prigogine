# Research Legacy Note

## Friedrichs Model, Liouville Spectral Organization, and the Search for a Common Framework of Dynamical Complexity and Irreversibility

**Document type:** Research handoff / living research ledger\
**Status date:** 25 November 2026\
**Status:** Exploratory; foundational derivations partly developed, not
yet fully audited\
**Canonical format:** Markdown\
**Purpose:** Preserve the state of the investigation so it can be
resumed in a new conversation without relying on chat history.

------------------------------------------------------------------------

## 0. Executive status

This investigation is exploring whether there is a common spectral
framework for dynamical complexity and thermodynamic irreversibility,
with the Ruelle transfer operator and Prigogine's non-unitary
transformation representing complementary aspects of an underlying
evolution.

The immediate mathematical testbed is the Friedrichs model. The
programme proceeds from a single-particle resonance/continuum
decomposition (Stage 1), to its Liouville-space organization (Stage 2),
and then to the construction and testing of a Prigogine-type non-unitary
transformation (Stage 3). Only after these foundations are secure should
we attempt a careful bridge to Ruelle operators, dynamical zeta
functions, Selberg theory, and ultimately questions motivated by the
Riemann hypothesis.

**Central research question**

> Does there exist a common spectral formulation of dynamical complexity
> and thermodynamic irreversibility, in which the Ruelle transfer
> operator and Prigogine's non-unitary transformation represent
> complementary aspects of the same underlying evolution?

This is a research question, not an established theorem. No conclusion
about the Riemann hypothesis follows from the work recorded here.

### Current state in one paragraph

A single-particle Friedrichs-model foundation has been developed in a
separate, user-referenced file,
`friedrichs_stage1_single_particle_foundation.md`, but that file has not
yet been supplied in the current working context for a fresh
line-by-line audit. A Stage 2 note, "Liouville Spectral Organization of
the Friedrichs Model," has been drafted in the conversation. Its right
generalized Liouville eigenoperator construction is structurally sound
conditional on Stage 1 and the stated rigged-space assumptions, but
three corrections are required before Stage 2 can be frozen: the
eigenvalues assigned to the Riesz/antidual dual generalized operators,
the angular sector for continuum--continuum eigenvalues, and the
distributional meaning of generalized-operator biorthogonality. Stage
3---the construction of the transformation (`\Lambda`{=tex}\^{-1}(L)) on
the four Liouville sectors---has not yet been carried out.

------------------------------------------------------------------------

## 1. Research discipline and standards of proof

The work should maintain explicit distinctions between:

1.  **Established operator-theoretic facts**, proved under stated
    hypotheses.
2.  **Derived identities**, whose validity depends on earlier lemmas and
    conventions.
3.  **Analytic-continuation constructions**, which require specified
    test spaces, domains, contours, and growth conditions.
4.  **Formal tensor-product lifts**, which still need topological and
    distributional justification.
5.  **Physical interpretations**, which may be useful but are not
    mathematical consequences by themselves.
6.  **Conjectures and research hypotheses**, which must never be
    presented as results.

Every substantial claim should carry its assumptions. In particular:

-   Analyticity alone does not imply the rapid decay needed for every
    contour integral or Fubini interchange.
-   A formal generalized eigenvector is not an ordinary Hilbert-space
    vector.
-   A generalized eigenoperator is not automatically Hilbert--Schmidt.
-   Completeness does not automatically imply biorthogonality.
-   A pointwise exponentially decaying spectral factor does not imply a
    uniform exponential decay bound for an integral over a continuum
    reaching threshold.
-   A formal analogy between two zeta functions is not a spectral
    identification.
-   A positive Lyapunov functional in a transformed representation is
    not, by itself, proof that all physical observables decay
    monotonically.

The investigation should prefer a smaller number of rigorously
established results over a broad but fragile unification.

------------------------------------------------------------------------

## 2. Research programme and dependency structure

### Stage 1 --- Single-particle Friedrichs foundation

**Objective:** Establish the resonance--continuum spectral resolution of
the Friedrichs Hamiltonian, including the analytic continuation,
biorthogonal generalized states, completeness, and time evolution.

Key deliverables:

-   Exact block resolvent.
-   Boundary-value jump identities and their factorization.
-   Analytic continuation and contour deformation, including the
    resonance residue.
-   Correct resonance and continuum generalized eigenvectors.
-   Biorthogonality and normalization.
-   Weak completeness / spectral resolution on a specified test space.
-   Time-evolution representation and survival amplitude.
-   Explicit hypotheses controlling threshold and infinity.

The referenced source file is
`friedrichs_stage1_single_particle_foundation.md`. **It must be supplied
in a new thread** before claiming that Stage 1 has been independently
reverified. The summaries in this handoff are not a substitute for the
source derivation.

### Stage 2 --- Liouville spectral organization

**Objective:** Lift the Stage 1 resonance--continuum decomposition to
operator space and organize the resulting generalized eigenoperators
into four sectors:

1.  resonance--resonance;
2.  resonance--continuum;
3.  continuum--resonance;
4.  continuum--continuum.

The Stage 2 draft exists in the conversation under the title "Liouville
Spectral Organization of the Friedrichs Model." It should be corrected
and then saved as `friedrichs_stage2_liouville_organization.md`.

### Stage 3 --- Prigogine transformation and irreversibility

**Objective:** Construct a candidate (`\Lambda`{=tex}\^{-1}(L)) on the
four Liouville sectors, then test independently:

-   star-unitarity;
-   existence and domain of the transformed generator;
-   positivity of the metric (M);
-   positivity of the Lyapunov-production operator (D);
-   monotonicity of the resulting quadratic functional;
-   compatibility with the original unitary dynamics and the relevant
    restricted classes of states/observables.

Do not assume that a formal diagonal multiplier on generalized
eigenoperators automatically defines a closed or bounded operator on the
physical Liouville space.

### Stage 4 --- Dynamical systems and transfer operators

**Objective:** Investigate whether the spectral and irreversible
structures found in the Friedrichs model have a meaningful analogue in
Ruelle transfer-operator theory.

Possible objects:

-   Ruelle transfer operators and their resonances;
-   pressure and entropy;
-   tilted transfer operators for entropy production;
-   dynamical zeta functions and periodic-orbit expansions;
-   possible relations between spectral gaps, correlation decay, and
    Lyapunov functionals.

This stage must identify a precise mathematical correspondence, not
merely a shared vocabulary.

### Stage 5 --- Zeta functions and the RH-motivated direction

**Objective:** Examine structural links among dynamical zeta functions,
Selberg zeta, scattering determinants, and the Riemann zeta function.

The known analogies are useful sources of hypotheses, but no direct
identification with the nontrivial zeros of the Riemann zeta function
has been established here. Any RH-related claim must be separated from
the Friedrichs/Prigogine results and subjected to its own proof audit.

------------------------------------------------------------------------

## 3. Stage 1: Friedrichs model --- current reference framework

### 3.1 Hilbert space and Hamiltonian

The working Hilbert space is

\[ `\mathcal `{=tex}H = `\mathbb `{=tex}C
\|1`\rangle `{=tex}`\oplus `{=tex}L^2(`\mathbb `{=tex}R^+,d`\omega`{=tex}).
\]

The Hamiltonian is represented as

\[ H =
```{=tex}
\begin{pmatrix}
\omega_1 & \lambda\langle V|\\
\lambda|V\rangle & M_\omega
\end{pmatrix}
```
, \]

where (M\_`\omega`{=tex}) is multiplication by (`\omega`{=tex}),
(`\lambda`{=tex}) is the coupling, and (V) is the form factor.

The scalar denominator is

\[ `\eta`{=tex}(z)=z-`\omega`{=tex}\_1-`\lambda`{=tex}\^2
`\int`{=tex}\_0\^`\infty `{=tex}`\frac{|V(\omega)|^2}{z-\omega}`{=tex},d`\omega`{=tex}.
\]

For analytic continuation, the reflected density is written

\[ J(z)=V(z)`\overline{V(\bar z)}`{=tex}. \]

Under the contour convention used in the project, the continued
denominator is

\[
`\eta`{=tex}\_+(z)=`\eta`{=tex}(z)+2`\pi `{=tex}i`\lambda`{=tex}\^2J(z).
\]

This sign convention is important and must be checked against the exact
Stage 1 derivation whenever the source file is reintroduced.

A simple resonance is denoted

\[ z_0=`\widetilde`{=tex}`\omega`{=tex}\_1-`\frac{i\gamma}{2}`{=tex},
`\qquad`{=tex} A_1=`\frac{1}{\eta_+'(z_0)}`{=tex}. \]

At weak coupling, the familiar leading-order width is

\[
`\gamma=2`{=tex}`\pi`{=tex}`\lambda`{=tex}\^2\|V(`\widetilde`{=tex}`\omega`{=tex}\_1)\|^2+O(`\lambda`{=tex}^4).
\]

This is a weak-coupling approximation, not an exact formula for
arbitrary coupling.

### 3.2 Exact block resolvent

The working block-resolvent identity is

\[ R(z)=
```{=tex}
\begin{pmatrix}
\eta(z)^{-1}
&
\frac{\lambda}{\eta(z)}
\langle V|(z-M_\omega)^{-1}\\[4pt]
\frac{\lambda}{\eta(z)}
(z-M_\omega)^{-1}|V\rangle
&
(z-M_\omega)^{-1}
+\frac{\lambda^2}{\eta(z)}
(z-M_\omega)^{-1}|V\rangle
\langle V|(z-M_\omega)^{-1}
\end{pmatrix}
```
. \]

For a Cauchy transform

\[
C(z)=`\int`{=tex}\_0\^`\infty`{=tex}`\frac{f(\omega)}{z-\omega}`{=tex},d`\omega`{=tex},
\]

the boundary jump convention is

\[ C(E+i0)-C(E-i0)=-2`\pi `{=tex}i f(E). \]

With the minus sign in the definition of (`\eta`{=tex}), continuation of
the upper boundary value into the lower half-plane adds
(+2`\pi `{=tex}i`\lambda`{=tex}\^2J(z)) to (`\eta`{=tex}).

Stone's formula is used in the convention

\[ R(E+i0)-R(E-i0)=-2`\pi `{=tex}i,`\delta`{=tex}(E-H). \]

The exact D15-type continuum jump factorization is a critical Stage 1
proof obligation. It should be rechecked block by block from the
resolvent, not inferred from a real-axis scattering formula.

### 3.3 Earlier Stage 1 derivation history

A prior block-by-block derivation was summarized as follows:

1.  Exact proof of the continuum jump identity (referred to as D15) from
    the four resolvent blocks.
2.  Contour deformation of the relevant Cauchy integral.
3.  The residue contribution \[
    2`\pi `{=tex}i`\lambda`{=tex}`\overline{V(\bar\zeta)}`{=tex}`\phi`{=tex}*+(`\zeta`{=tex})
    \] combines with (`\phi`{=tex}*+(`\zeta`{=tex})) to produce the
    factor (`\eta`{=tex}\_+(`\zeta`{=tex})/`\eta`{=tex}(`\zeta`{=tex})).
4.  This yields corrected E16a/E16b expressions, the
    (`\theta`{=tex}`\to0`{=tex}) physical scattering projection, and a
    bare-state sum rule E18.

The exact E16a/E16b and the full statements of the completeness and
biorthogonality theorems are not reproduced in this handoff. They must
be recovered from the Stage 1 source file before a detailed audit.

### 3.4 Spectral assumptions still requiring explicit verification

A condition of the form

\[
`\lambda`{=tex}\^2`\int`{=tex}\_0^`\infty `{=tex}`\omega`{=tex}^{-1}\|V(`\omega`{=tex})\|\^2,d`\omega`{=tex}\<`\omega`{=tex}\_1
\]

may help exclude a negative-energy bound state in the relevant setting.
It does **not**, by itself and without further hypotheses, establish the
absence of all embedded or threshold eigenvalues. The spectral
assumptions must explicitly address:

-   regularity and decay of (V);
-   threshold behavior near (`\omega=0`{=tex});
-   possible embedded eigenvalues;
-   zeros of the physical and continued denominators;
-   the number and simplicity of resonance poles in the deformation
    region;
-   large-energy bounds;
-   the precise test-function class on which the weak resolution holds.

------------------------------------------------------------------------

## 4. Stage 2: Liouville-space construction

### 4.1 Operator Hilbert space and rigged structure

The Hilbert--Schmidt space is

\[ `\mathcal `{=tex}B_2(`\mathcal `{=tex}H)`\simeq`{=tex}
`\mathcal `{=tex}H`\otimes`{=tex}`\overline{\mathcal H}`{=tex}, \]

with pairing

\[
`\langle`{=tex}!`\langle`{=tex}`\sigma`{=tex}\|`\rho`{=tex}`\rangle`{=tex}!`\rangle`{=tex}
=`\operatorname{Tr}`{=tex}(`\sigma`{=tex}\^`\dagger`{=tex}`\rho`{=tex}).
\]

For dyads,

\[ `\left`{=tex}`\langle`{=tex}!`\left`{=tex}`\langle`{=tex}
\|u`\rangle`{=tex}`\langle `{=tex}v\| ,`\middle`{=tex}\|,
\|`\phi`{=tex}`\rangle`{=tex}`\langle`{=tex}`\chi`{=tex}\|
`\right`{=tex}`\rangle`{=tex}!`\right`{=tex}`\rangle`{=tex} =
`\langle `{=tex}u\|`\phi`{=tex}`\rangle`{=tex}`\langle`{=tex}`\chi`{=tex}\|v`\rangle`{=tex}
=
`\langle `{=tex}u\|`\phi`{=tex}`\rangle`{=tex}`\overline{\langle v|\chi\rangle}`{=tex}.
\]

The proposed test spaces are

\[
`\mathcal `{=tex}B_0=`\Phi`{=tex}`\otimes`{=tex}*{`\rm alg`{=tex}}`\bar`{=tex}`\Phi`{=tex},
`\qquad`{=tex}
`\mathcal `{=tex}B*-=`\Phi`{=tex}`\widehat`{=tex}`\otimes`{=tex}\_`\pi`{=tex}`\bar`{=tex}`\Phi`{=tex},
\]

and the proposed rigged Liouville-space chain is

\[
`\mathcal `{=tex}B_0`\subset`{=tex}`\mathcal `{=tex}B\_-`\subset`{=tex}`\mathcal `{=tex}B_2
`\subset`{=tex}`\mathcal `{=tex}B\_-^`\times`{=tex}`\subset`{=tex}`\mathcal `{=tex}B_0^`\times`{=tex}.
\]

The Liouville operator is

\[ L=\[H,`\cdot`{=tex}\]. \]

On a dyad,

\[ L(\|u`\rangle`{=tex}`\langle `{=tex}v\|)
=\|Hu`\rangle`{=tex}`\langle `{=tex}v\|-\|u`\rangle`{=tex}`\langle `{=tex}Hv\|.
\]

The proposed antidual action is

\[
`\langle`{=tex}!`\langle`{=tex}`\sigma`{=tex}\|L\^`\times `{=tex}F`\rangle`{=tex}!`\rangle`{=tex}
=
`\langle`{=tex}!`\langle `{=tex}L`\sigma`{=tex}\|F`\rangle`{=tex}!`\rangle`{=tex}.
\]

For ordinary Hilbert--Schmidt operators, this is compatible with the
usual commutator action under suitable domain and trace assumptions. The
continuity of (L) on the chosen test space and the exact meaning of the
duals must be established rather than assumed.

### 4.2 Contours and conjugate functionals

The lower contour is

\[ `\Gamma`{=tex}\_`\theta`{=tex}={xe\^{-i`\theta`{=tex}}:x\>0}, \]

and the conjugate upper contour is

\[ `\Gamma`{=tex}\_`\theta`{=tex}\^\*={x'e\^{i`\theta`{=tex}}:x'\>0}. \]

The conjugate functionals are constructed using reflected analytic
functions, schematically

\[ `\eta`{=tex}\^\*(z)=`\overline{\eta(\bar z)}`{=tex}, `\qquad`{=tex}
`\eta`{=tex}\_-(z)=`\overline{\eta_+(\bar z)}`{=tex}. \]

The exact definitions of the functionals labelled L6a/L6b and their
eigenfunctional relations L7a/L7b belong to the Stage 2 source draft and
should be copied verbatim into the frozen Stage 2 note. Their
conjugation conventions determine the dual eigenvalue issue below.

### 4.3 Four generalized Liouville sectors

The right generalized eigenoperators are organized as

\[ F\_{z_0,z_0\^\*}
=\|`\psi`{=tex}*{z_0}\^R`\rangle`{=tex}`\langle`{=tex}`\psi`{=tex}*{z_0}\^R\|,
\]

\[ F\_{z_0,`\zeta`{=tex}'}
=\|`\psi`{=tex}*{z_0}\^R`\rangle`{=tex}`\langle`{=tex}`\psi`{=tex}*{`\bar`{=tex}`\zeta`{=tex}'}\^R\|,
\]

\[ F\_{`\zeta`{=tex},z_0\^\*}
=\|`\psi`{=tex}*`\zeta`{=tex}\^R`\rangle`{=tex}`\langle`{=tex}`\psi`{=tex}*{z_0}\^R\|,
\]

\[ F\_{`\zeta`{=tex},`\zeta`{=tex}'}
=\|`\psi`{=tex}*`\zeta`{=tex}\^R`\rangle`{=tex}`\langle`{=tex}`\psi`{=tex}*{`\bar`{=tex}`\zeta`{=tex}'}\^R\|.
\]

Here (`\zeta`{=tex}`\in`{=tex}`\Gamma`{=tex}*`\theta`{=tex}) and
(`\zeta`{=tex}'`\in`{=tex}`\Gamma`{=tex}*`\theta`{=tex}\^\*). The
corresponding dual generalized objects in the draft are formed using
left generalized eigenvectors.

For a dyadic generalized eigenoperator with first spectral label
(`\alpha`{=tex}) and second spectral label (`\beta`{=tex}), the
right-sector eigenvalue is

\[
`\ell`{=tex}\_{`\alpha`{=tex},`\beta`{=tex}}=`\alpha`{=tex}-`\beta`{=tex},
\]

subject to the precise conjugate-contour labeling used for the second
factor.

The four right-sector eigenvalues stated in the draft are

\[ -i`\gamma`{=tex},`\qquad`{=tex} z_0-`\zeta`{=tex}',`\qquad`{=tex}
`\zeta`{=tex}-z_0\^\*,`\qquad`{=tex} `\zeta`{=tex}-`\zeta`{=tex}'. \]

The derivation is based on

\[
```{=tex}
\begin{aligned}
\langle\!\langle|\phi\rangle\langle\chi|
|L^\times F\rangle\!\rangle
={}&
\langle H\phi|u^R\rangle\langle v^R|\chi\rangle\\
&-\langle\phi|u^R\rangle\langle v^R|H\chi\rangle,
\end{aligned}
```
\]

which factorizes into the difference of the two single-particle spectral
labels when the Stage 1 generalized eigenfunctional relations apply.

### 4.4 Required correction 1: dual generalized eigenoperator eigenvalues

The Stage 2 draft claims that the left/dual generalized operators have
the same eigenvalues as their right counterparts. Under the stated
Riesz/antidual convention and the conjugated left eigenfunctional
relations, that is not correct in general.

For example, for the resonance--resonance sector,

\[ F\_{z_0,z_0\^\*}
=\|`\psi`{=tex}*{z_0}\^R`\rangle`{=tex}`\langle`{=tex}`\psi`{=tex}*{z_0}\^R\|
\]

has eigenvalue

\[ z_0-z_0\^\*=-i`\gamma`{=tex}. \]

But for the proposed dual representative

\[ `\widetilde `{=tex}F\_{z_0,z_0\^\*}
=\|`\psi`{=tex}*{z_0}\^L`\rangle`{=tex}`\langle`{=tex}`\psi`{=tex}*{z_0}\^L\|,
\]

the conjugated left eigenfunctional relations give

\[ L^`\times`{=tex}`\widetilde `{=tex}F\_{z_0,z_0^*}
=(z_0\^*-z_0)`\widetilde `{=tex}F\_{z_0,z_0\^*}
=+i`\gamma`{=tex},`\widetilde `{=tex}F\_{z_0,z_0\^*}. \]

More generally, with these conventions,

\[ `\ell`{=tex}*{`\widetilde `{=tex}F*{`\alpha`{=tex},`\beta`{=tex}}}
=`\overline{\ell_{F_{\alpha,\beta}}}`{=tex}, \]

rather than equality. This is not necessarily a defect: it reflects the
distinction between the dual eigenfunctional and its Riesz
representative. The corrected theorem must state precisely which object
is a right generalized eigenvector, which is a left eigenfunctional, and
which is the Hilbert-space/Riesz representative of that functional. The
four sectors should all be checked, not just the resonance--resonance
example.

### 4.5 Required correction 2: continuum--continuum spectral wedge

For

\[ `\zeta`{=tex}=xe\^{-i`\theta`{=tex}}, `\qquad`{=tex}
`\zeta`{=tex}'=x'e\^{i`\theta`{=tex}}, \]

the continuum--continuum eigenvalue is

\[ `\ell`{=tex}\_{`\zeta`{=tex},`\zeta`{=tex}'}
=(x-x')`\cos`{=tex}`\theta`{=tex}-i(x+x')`\sin`{=tex}`\theta`{=tex}. \]

For (x,x'\>0), it lies in the lower half-plane. The angular range stated
in the Stage 2 draft,
(-`\theta`{=tex}`\leq`{=tex}`\arg`{=tex}(-`\ell`{=tex})`\leq`{=tex}`\theta`{=tex}),
is incorrect.

The correct range is

\[
`\theta`{=tex}`\leq`{=tex}`\arg`{=tex}(-`\ell`{=tex})`\leq`{=tex}`\pi`{=tex}-`\theta`{=tex},
\]

or equivalently

\[
-`\pi`{=tex}+`\theta`{=tex}`\leq`{=tex}`\arg`{=tex}(`\ell`{=tex})`\leq`{=tex}-`\theta`{=tex}.
\]

Also,

\[ \|e\^{-i`\ell `{=tex}t}\| =e\^{-(x+x')`\sin`{=tex}`\theta`{=tex},t}.
\]

There is no uniform positive decay gap because (x+x') can approach zero.
Therefore, although each fixed continuum--continuum spectral component
has a decaying factor for (t\>0), the integrated continuum contribution
need not have a uniform exponential decay rate. Threshold behavior can
produce long-time tails.

### 4.6 Completeness and forward-time expansion

The Stage 2 completeness claim is a tensor-product lift of the Stage 1
weak resolution, using the lower contour for one factor and the
conjugate upper contour for the other. This is structurally reasonable,
but the proof must explicitly establish:

-   the tensor-product test space and its topology;
-   continuity of the lifted maps;
-   convergence of each contour integral;
-   the hypotheses for interchanging integrations (including any
    Fubini/Tonelli step);
-   the distributional meaning of the resulting identity;
-   the domain on which the forward-time representation holds.

A statement that rapid decay justifies Fubini is insufficient unless the
relevant seminorm estimates and decay bounds have actually been proved.

The formal time factor is

\[ e\^{-i(`\alpha`{=tex}-`\beta`{=tex})t}. \]

The unitary evolution of the full physical system and a resonance
expansion with decaying terms are not contradictory: the latter is a
representation on a restricted analytic test space after contour
deformation. It must not be mistaken for a global contraction of the
original unitary dynamics.

### 4.7 Required correction 3: generalized-operator biorthogonality

The Stage 2 draft writes generalized biorthogonality relations using
pairings that resemble Hilbert--Schmidt inner products or traces.
However, the generalized (F) and (`\widetilde `{=tex}F) are not
automatically elements of (`\mathcal `{=tex}B_2). Their ordinary
Hilbert--Schmidt pairing is therefore not automatically defined.

The safe formulation is as a **distributional kernel identity** obtained
by tensoring the Stage 1 single-particle biorthogonal pairings and
smearing against test functions on

\[
`\Gamma`{=tex}*`\theta`{=tex}`\times`{=tex}`\Gamma`{=tex}*`\theta`{=tex}\^\*.
\]

The contour delta conventions in the draft are

\[
`\delta`{=tex}*{`\Gamma`{=tex}*`\theta`{=tex}\^\*}(`\zeta`{=tex}'-`\eta`{=tex}')
=e\^{-i`\theta`{=tex}}`\delta`{=tex}(x'-y'), \]

\[
`\delta`{=tex}*{`\Gamma`{=tex}*`\theta`{=tex}}(`\zeta`{=tex}-`\eta`{=tex})
=e\^{i`\theta`{=tex}}`\delta`{=tex}(x-y'), \]

with the intended real-coordinate interpretation to be checked carefully
(the second delta should use the real coordinate associated with the
second contour variable). These factors are consistent with the contour
measures

\[ d`\zeta`{=tex}=e\^{-i`\theta`{=tex}}dx, `\qquad`{=tex}
d`\zeta`{=tex}'=e\^{i`\theta`{=tex}}dx', \]

provided the delta distributions are defined relative to those measures.
The frozen note should state the convention explicitly and verify it by
testing against smooth compactly supported functions.

Do not write an unqualified trace or Hilbert--Schmidt inner product
between generalized operators unless its distributional extension has
been defined.

### 4.8 Bare-projector expansion and survival amplitude

The Stage 2 draft gives the following sector coefficients for the bare
projector expansion:

\[ c\_{z_0,z_0\^\*}=\|A_1\|, \]

\[ c\_{z_0,`\zeta`{=tex}'} =`\sqrt{A_1}`{=tex},
`\frac{\lambda\overline{V(\bar\zeta')}}{\eta_-(\zeta')}`{=tex}, \]

\[ c\_{`\zeta`{=tex},z_0\^\*} =`\overline{\sqrt{A_1}}`{=tex},
`\frac{\lambda V(\zeta)}{\eta_+(\zeta)}`{=tex}, \]

\[ c\_{`\zeta`{=tex},`\zeta`{=tex}'} =
`\frac{\lambda^2V(\zeta)\overline{V(\bar\zeta')}}`{=tex}
{`\eta`{=tex}*+(`\zeta`{=tex})`\eta`{=tex}*-(`\zeta`{=tex}')}. \]

These coefficients must be checked directly against the exact Stage 1
overlap formulas and branch conventions before the note is frozen. In
particular, the square-root phase convention for (A_1), reflected form
factors, and (`\eta`{=tex}\_`\pm`{=tex}) must be consistent.

The survival probability is written as

\[ P\_{11}(t)= `\left`{=tex}\| A_1e\^{-iz_0t} +
`\int`{=tex}*{`\Gamma`{=tex}*`\theta`{=tex}}
`\frac{\lambda^2J(\zeta)}`{=tex}
{`\eta`{=tex}\_+(`\zeta`{=tex})`\eta`{=tex}(`\zeta`{=tex})}
e\^{-i`\zeta `{=tex}t},d`\zeta`{=tex} `\right`{=tex}\|\^2. \]

This too is conditional on the Stage 1 derivation and must be rechecked
before being treated as a frozen result.

------------------------------------------------------------------------

## 5. Stage 3: Prigogine-type transformation --- planned construction

### 5.1 Conceptual starting point

The relevant historical reference is:

I. Prigogine, F. Mayné, C. George, and M. de Haan, "Microscopic theory
of irreversible processes," *Proceedings of the National Academy of
Sciences* **74**(10), 4152--4156 (1977).

The paper develops a non-unitary transformation in Liouville space,
associated with a positive quadratic Lyapunov functional and an
irreversible semigroup representation. In the paper's notation, the
transformation is (A); the present project has used (`\Lambda`{=tex}) as
a working symbol. These should not be silently conflated without
matching definitions and conventions.

The key structural expressions in the historical framework include

\[ M=(A^{-1})^`\dagger `{=tex}A\^{-1}, \]

and a positivity condition of the form

\[ D=i(ML-LM)`\geq0`{=tex}, \]

with the transformed generator related to (A\^{-1}LA). The paper also
formulates a star-unitarity relation, in its own conventions, of the
form

\[ (A^{-1}(L))^`\dagger`{=tex}=A(-L), `\qquad`{=tex}
A(L)A\^`\dagger`{=tex}(-L)=1. \]

The exact meaning of the argument (L), adjoints, and domains must be
taken from the original construction, not inferred from notation alone.

### 5.2 Candidate tests

For a candidate (`\Lambda`{=tex}\^{-1}(L)), the following are separate
obligations:

1.  **Definition:** Give the action on each of the four Liouville
    sectors, including continuum labels.
2.  **Well-definedness:** Establish that the action maps the chosen test
    space or a specified dense domain into an appropriate space.
3.  **Star-unitarity:** Test the exact relation
    (`\Lambda`{=tex}^{-1}(L)=`\Lambda`{=tex}^`\dagger`{=tex}(-L)) (or
    the conventionally equivalent form) on a common invariant domain.
4.  **Metric:** Define \[
    M=(`\Lambda`{=tex}^{-1})^`\dagger`{=tex}`\Lambda`{=tex}\^{-1} \]
    with a precise adjoint and prove or disprove (M`\geq0`{=tex}).
5.  **Lyapunov production:** Define \[ D=i(ML-LM) \] and test positivity
    as a quadratic-form statement on a specified domain.
6.  **Monotonicity:** Derive the time derivative of the candidate
    quadratic functional and verify its sign, including boundary terms
    and domain assumptions.
7.  **Physical interpretation:** Identify exactly which states and
    observables retain equivalence with the original dynamics. Do not
    claim equivalence for all states/observables unless proved.

A diagonal multiplier on generalized eigenoperators may be a useful
formal ansatz, but it is not yet an operator construction. Its
growth/decay along the continuum labels, behavior near threshold,
inverse, and adjoint all matter.

### 5.3 Immediate Stage 3 task

After Stage 2 is corrected and frozen, construct the candidate
(`\Lambda`{=tex}\^{-1}(L)) sector by sector and test star-unitarity
first. Then test metric positivity and Lyapunov monotonicity
independently. A failure of one condition must not be hidden by a
successful formal check of another.

------------------------------------------------------------------------

## 6. Ruelle operators, entropy, and dynamical zeta functions --- research hypotheses

### 6.1 Ruelle transfer operator

For a suitable map (T) and potential (`\phi`{=tex}), a standard transfer
operator is

\[ (`\mathcal `{=tex}L\_`\phi `{=tex}f)(x) =
`\sum`{=tex}\_{Ty=x}e\^{`\phi`{=tex}(y)}f(y). \]

The pressure is

\[ P(T,`\phi`{=tex}) = `\sup`{=tex}\_`\mu`{=tex} `\left[
h_\mu(T)+\int\phi\,d\mu
\right]`{=tex}, \]

where the supremum is over an appropriate class of invariant probability
measures.

Transfer-operator spectra can encode correlation decay, periodic-orbit
data, and thermodynamic formalism under suitable dynamical and
functional-analytic hypotheses. The precise Banach/Hilbert spaces and
spectral properties depend strongly on the system.

### 6.2 Entropy-production tilting

A possible object is a tilted transfer operator such as

\[ (`\mathcal `{=tex}L_q f)(x) =
`\sum`{=tex}\_{Ty=x}e\^{-q`\sigma`{=tex}(y)}f(y), \]

where (`\sigma`{=tex}) is an entropy-production observable. Its leading
spectral data can generate a scaled cumulant-generating function,
schematically

\[ `\psi`{=tex}(q) = `\lim`{=tex}\_{t`\to`{=tex}`\infty`{=tex}}
`\frac`{=tex}1t`\log`{=tex}
`\left`{=tex}`\langle `{=tex}e\^{-q`\Sigma`{=tex}\_t}`\right`{=tex}`\rangle`{=tex}.
\]

This is a possible bridge to irreversible dynamics, but it is not
automatically equivalent to Prigogine's quadratic Lyapunov functional.
The two constructions must be compared mathematically, including their
state spaces, observables, positivity notions, and time evolution.

### 6.3 Dynamical zeta functions

A schematic dynamical zeta function is

\[ `\zeta`{=tex}*D(s) = `\prod`{=tex}*{`\gamma`{=tex}}
`\left`{=tex}(1-e^{-sT\_`\gamma`{=tex}}`\right`{=tex})^{-1}, \]

where (`\gamma`{=tex}) runs over primitive periodic orbits and
(T\_`\gamma`{=tex}) denotes their periods.

There is a structural analogy between this Euler product and the Euler
product for the Riemann zeta function:

-   primitive periodic orbits correspond formally to prime labels;
-   orbit periods correspond formally to logarithms of primes;
-   repetitions of primitive orbits correspond to prime powers.

This is an analogy of product structure. It does not establish that
primes are literal periodic orbits of a known dynamical system, nor does
it establish a direct identification of the two spectra.

### 6.4 Selberg zeta and transfer-operator determinants

A standard schematic relation in suitable settings is

\[ Z\_{`\rm Sel`{=tex}}(s) = `\det`{=tex}(I-`\mathcal `{=tex}L_s\^2) =
`\det`{=tex}(I-`\mathcal `{=tex}L_s)`\det`{=tex}(I+`\mathcal `{=tex}L_s).
\]

The exact operator, determinant class, normalization, and domain depend
on the particular dynamical/geometric construction. These details are
essential.

For the modular surface, the scattering coefficient has been written in
the working notes as

\[ `\varphi`{=tex}(s) = `\sqrt{\pi}`{=tex},
`\frac{\Gamma(s-\frac12)}{\Gamma(s)}`{=tex}
`\frac{\zeta(2s-1)}{\zeta(2s)}`{=tex} =
`\frac{s}{s-1}`{=tex}`\frac{\xi(2s-1)}{\xi(2s)}`{=tex}. \]

The scaling in the scattering variable matters: a statement about a
critical line in (s) is not interchangeable with a statement about the
usual Riemann variable. The scattering-associated Selberg zeros and the
Maass cusp-form zeros belong to distinct spectral sectors. Any proposed
RH reformulation must keep those sectors separate.

Earlier work on a proposed Hadamard-product argument identified a likely
incompleteness: an entire function of order two requires the appropriate
canonical Weierstrass factors. This point should be re-audited from the
actual derivation before reuse.

------------------------------------------------------------------------

## 7. Historical context and novelty caution

The Prigogine--Mayné--George--de Haan 1977 PNAS paper is a direct
historical reference for microscopic irreversibility through a
non-unitary Liouville-space transformation and a positive Lyapunov
functional. It includes a Friedrichs-model discussion.

There is also prior literature connecting Kolmogorov--Sinai entropy,
relative entropy production in non-unitary formalisms, and macroscopic
entropy production in model systems (including a 1987 study of a
one-dimensional hard-point gas, noted in the earlier research
conversation).

Therefore, the broad idea of relating dynamical entropy and irreversible
non-unitary representations is not automatically novel. A novelty claim
would require a literature review and, more importantly, a precise
statement of what the present framework adds---for example, a new
operator-level correspondence, a new positivity theorem, a new spectral
decomposition, or a demonstrably new link to a class of dynamical zeta
functions.

------------------------------------------------------------------------

## 8. Open questions and proof-obligation register

### Stage 1

-   [ ] Re-open and audit
    `friedrichs_stage1_single_particle_foundation.md` line by line.
-   [ ] Verify the exact resolvent block identities and all
    boundary-value signs.
-   [ ] Verify the D15 jump factorization independently for all four
    blocks.
-   [ ] Verify the contour deformation and resonance residue signs.
-   [ ] Recover the exact E16a/E16b expressions and verify their
    denominators and prescriptions.
-   [ ] Prove the stated biorthogonality relations with explicit
    normalization.
-   [ ] Prove weak completeness on the stated test space.
-   [ ] Supply threshold and infinity estimates justifying convergence
    and limiting operations.
-   [ ] State assumptions excluding unwanted point spectrum and
    establish that they are sufficient.

### Stage 2

-   [ ] Correct the dual generalized eigenoperator eigenvalues in all
    four sectors.
-   [ ] State the distinction between left eigenfunctionals and Riesz
    representatives.
-   [ ] Correct the continuum--continuum angular sector.
-   [ ] State explicitly that there is no uniform continuum decay gap at
    threshold.
-   [ ] Define generalized-operator biorthogonality as a distributional
    kernel pairing.
-   [ ] Verify contour delta normalizations by test-function smearing.
-   [ ] Justify tensor-product completeness and all Fubini/interchange
    steps.
-   [ ] Recheck bare-projector coefficients against Stage 1.
-   [ ] Recheck the survival-amplitude formula and its contour
    prescriptions.
-   [ ] Freeze a corrected standalone Stage 2 note only after these
    checks.

### Stage 3

-   [ ] Fix notation by mapping the project's (`\Lambda`{=tex}) to the
    historical (A) convention.
-   [ ] Define the candidate (`\Lambda`{=tex}\^{-1}(L)) on all four
    sectors.
-   [ ] Specify the common invariant domain and the relevant dual
    pairing.
-   [ ] Test star-unitarity.
-   [ ] Define and test the metric (M).
-   [ ] Prove or disprove positivity of (M).
-   [ ] Define (D=i(ML-LM)) as a quadratic form and test positivity.
-   [ ] Derive Lyapunov monotonicity, including domain and boundary
    terms.
-   [ ] Identify the restricted state/observable class for which
    physical equivalence holds.

### Later stages

-   [ ] Identify a precise correspondence between the Friedrichs
    Liouville generator and a Ruelle transfer operator, if one exists.
-   [ ] Distinguish spectral resonances from Ruelle--Pollicott
    resonances.
-   [ ] Compare Prigogine's quadratic Lyapunov functional with
    entropy-production generating functions without assuming
    equivalence.
-   [ ] Establish exact hypotheses for any determinant or dynamical-zeta
    identity.
-   [ ] Keep the modular scattering sector distinct from cusp-form
    spectral data.
-   [ ] Re-audit every RH-related inference independently.

------------------------------------------------------------------------

## 9. Restart protocol for a new conversation

When resuming this project in a new thread:

1.  **Attach this research legacy note.**
2.  **Attach `friedrichs_stage1_single_particle_foundation.md`.** Do not
    ask the assistant to reconstruct it from memory.
3.  If available, attach the original Stage 2 draft, including the exact
    L6/L7 functional definitions and L14--L21 formulas.
4.  Ask for a source-grounded audit, not a general summary.
5.  Require the assistant to classify each claim as:
    -   verified from supplied derivation;
    -   valid conditional on named assumptions;
    -   formally plausible but not yet justified;
    -   incorrect and requiring correction;
    -   unresolved because source material is missing.
6.  Resume with the Stage 2 corrections listed in Section 8. Do not
    begin Stage 3 until the Stage 2 definitions and pairings are
    unambiguous.
7.  Preserve each frozen stage as a separate versioned file. Never
    overwrite a prior derivation without recording what changed and why.

### Suggested opening prompt for the next thread

> We are continuing a multi-stage mathematical research project. Read
> the attached research legacy note and the Stage 1 source file before
> responding. Treat the legacy note as a map of the project, not as
> proof of its claims. First reconstruct the definitions, conventions,
> assumptions, and dependency structure. Then audit the outstanding
> Stage 1 and Stage 2 proof obligations. Do not proceed to Stage 3 until
> the four-sector Liouville construction, dual eigenvalue conventions,
> continuum spectral geometry, and distributional biorthogonality are
> mathematically consistent. Clearly distinguish proved results,
> conditional results, formal constructions, and conjectures.

------------------------------------------------------------------------

## 10. Source and artifact register

  ---------------------------------------------------------------------------------------------------
  Artifact / source                                   Status                  Role
  --------------------------------------------------- ----------------------- -----------------------
  `friedrichs_stage1_single_particle_foundation.md`   Referenced by user; not Primary Stage 1
                                                      present in this handoff derivation; must be
                                                                              attached for audit

  "Liouville Spectral Organization of the Friedrichs  Draft supplied in       Stage 2 source;
  Model"                                              conversation            requires corrections
                                                                              listed above

  Prigogine et al., PNAS 74 (1977), 4152--4156        Historical reference    Non-unitary Liouville
                                                      identified              transformation and
                                                                              Lyapunov functional

  Ruelle transfer-operator / thermodynamic formalism  Research direction, not Possible
  literature                                          yet systematically      dynamical-complexity
                                                      reviewed in this        bridge
                                                      project                 

  Selberg / modular scattering / dynamical zeta       Background direction,   Possible zeta-function
  literature                                          prior partial analysis  connection; requires
                                                                              independent proofs
  ---------------------------------------------------------------------------------------------------

------------------------------------------------------------------------

## 11. Final epistemic status

At the point this note is written:

-   The project has a coherent sequence of mathematical tasks.
-   The Friedrichs model provides a concrete setting in which resonance
    decay, continuum contributions, and Liouville-space spectral
    organization can be studied.
-   The Stage 2 right-sector construction is a plausible tensor lift of
    the Stage 1 decomposition, conditional on the rigged-space framework
    and Stage 1 estimates.
-   The current Stage 2 draft contains specific correctable errors and
    omissions; it is **not yet frozen**.
-   No candidate Prigogine transformation has yet been rigorously
    constructed on the four sectors.
-   No common Ruelle--Prigogine spectral formulation has been
    established.
-   No conclusion about the Riemann hypothesis has been obtained.

The correct next move is conservative and concrete: recover the Stage 1
source, correct and freeze Stage 2, and only then construct and test the
Stage 3 transformation.
