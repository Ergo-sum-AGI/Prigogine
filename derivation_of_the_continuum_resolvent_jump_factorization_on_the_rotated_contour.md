# Derivation of the Continuum Resolvent Jump Factorization on the Rotated Contour

**Status:** Complete algebraic and test-space derivation for Stage 1 / Stage 1.5  
**Target identity:** Eq. (7.3) of `friedrichs_stage1_single_particle_foundation.md` (revision 2)  
**Test-space context:** $\Phi = \mathbb C|1\rangle \oplus \Phi_{\mathrm{cont}}$ from `friedrichs_stage1_5_concrete_instantiation.md`  
**Purpose:** Establish the rank-one factorization of the resolvent discontinuity across $\Gamma_\theta = e^{-i\theta}\mathbb R^+$ directly from the four blocks of $R(z) = (z-H)^{-1}$, confirming the exact $\eta_\mp(\zeta)$ denominators, coupling conjugations, and contour delta factors.

---

## 1. Setup: Deformed resolvent matrix elements and ray boundary values

Let $\Gamma_\theta = e^{-i\theta}\mathbb R^+$ ($0 < \theta < \theta_0$) be oriented from $0$ to $\infty$, parameterized by $\zeta = x e^{-i\theta}$ with $x > 0$ and $d\zeta = e^{-i\theta}\,dx$.

For test vectors
\[
|\phi_\pm\rangle = c_\pm|1\rangle + \int_0^\infty \phi_\pm(\omega)|\omega\rangle\,d\omega \in \Phi,
\qquad \phi_-^*(z) = \overline{\phi_-(\bar z)},
\]
analytic continuation of the four blocks of the exact Friedrichs resolvent (Eqs. (2.1)–(2.4)) from the upper half-plane through $\mathbb R^+$ into the sector $\Sigma_\theta = \{z : -\theta < \arg z < 0\}$ gives, for $z$ near $\Gamma_\theta$:
\[
\langle\phi_-|R_{\mathrm{def}}(z)|\phi_+\rangle
= \mathcal M_{11}(z) + \mathcal M_{1c}(z) + \mathcal M_{c1}(z) + \mathcal M_{cc}(z),
\tag{1.1}
\]
where the four block contributions along the deformed contour $\Gamma_\theta$ are:

1. **Discrete–discrete block ($11$):**
   \[
   \mathcal M_{11}(z) = \frac{\overline{c_-}\,c_+}{\eta_{\mathrm{def}}(z)},
   \tag{1.2a}
   \]

2. **Discrete–continuum block ($1c$):**
   \[
   \mathcal M_{1c}(z) = \frac{\lambda\,\overline{c_-}}{\eta_{\mathrm{def}}(z)}\,I_+(z;\phi_+),
   \qquad
   I_+(z;\phi_+) = \int_{\Gamma_\theta} \frac{\overline{V(\bar\zeta')}\,\phi_+(\zeta')}{z - \zeta'}\,d\zeta',
   \tag{1.2b}
   \]

3. **Continuum–discrete block ($c1$):**
   \[
   \mathcal M_{c1}(z) = \frac{\lambda\,c_+}{\eta_{\mathrm{def}}(z)}\,I_-(z;\phi_-),
   \qquad
   I_-(z;\phi_-) = \int_{\Gamma_\theta} \frac{V(\zeta')\,\phi_-^*(\zeta')}{z - \zeta'}\,d\zeta',
   \tag{1.2c}
   \]

4. **Continuum–continuum block ($cc$):**
   \[
   \mathcal M_{cc}(z)
   = \int_{\Gamma_\theta} \frac{\phi_-^*(\zeta')\,\phi_+(\zeta')}{z - \zeta'}\,d\zeta'
   + \frac{\lambda^2}{\eta_{\mathrm{def}}(z)}\,I_-(z;\phi_-)\,I_+(z;\phi_+),
   \tag{1.2d}
   \]
where $\eta_{\mathrm{def}}(z)$ denotes the deformed dispersion function
\[
\eta_{\mathrm{def}}(z) = z - \omega_1 - \lambda^2 \int_{\Gamma_\theta} \frac{J(\zeta')}{z - \zeta'}\,d\zeta',
\qquad J(\zeta') = V(\zeta')\overline{V(\bar\zeta')}.
\tag{1.3}
\]

### 1.1 Oriented ray boundary notation ($\mp i0_\theta$)
For $\zeta \in \Gamma_\theta \setminus \{0\}$, the two boundary values across $\Gamma_\theta$ are defined by $f_\mp(\zeta) = f(\zeta \mp i0_\theta)$:
- $z = \zeta - i0_\theta$ approaches $\Gamma_\theta$ from the lower/right side (the original sheet $R(\zeta)$);
- $z = \zeta + i0_\theta$ approaches $\Gamma_\theta$ from the upper/left side (the analytically continued sheet $R_+(\zeta)$).

On $\Phi$, because $\phi_\pm \in \Phi_{\mathrm{cont}}$ and $V$ are holomorphic in $\mathcal S_\delta \supset \Gamma_\theta$ and decay rapidly at infinity, the oriented Sokhotski–Plemelj identity applies to any smooth rapid-decay integrand $g(\zeta')$ along $\Gamma_\theta$:
\[
\int_{\Gamma_\theta} \frac{g(\zeta')}{\zeta - \zeta' \mp i0_\theta}\,d\zeta'
= \mathcal P \int_{\Gamma_\theta} \frac{g(\zeta')}{\zeta - \zeta'}\,d\zeta' \pm i\pi\,g(\zeta).
\tag{1.4}
\]
In particular, subtracting the $+i0_\theta$ limit from the $-i0_\theta$ limit gives the fundamental contour jump identity:
\[
\int_{\Gamma_\theta} \frac{g(\zeta')}{\zeta - \zeta' - i0_\theta}\,d\zeta'
- \int_{\Gamma_\theta} \frac{g(\zeta')}{\zeta - \zeta' + i0_\theta}\,d\zeta'
= 2\pi i\,g(\zeta).
\tag{1.5}
\]

---

## 2. Boundary values of $\eta_{\mathrm{def}}(z)$ and $I_\pm(z)$ across $\Gamma_\theta$

Applying (1.4) to the dispersion integral in (1.3) yields
\[
\eta_\mp(\zeta)
= \eta_{\mathrm{def}}(\zeta \mp i0_\theta)
= \zeta - \omega_1 - \lambda^2 \mathcal P \int_{\Gamma_\theta} \frac{J(\zeta')}{\zeta - \zeta'}\,d\zeta'
\mp i\pi \lambda^2 J(\zeta).
\tag{2.1}
\]
Subtracting $\eta_+(\zeta)$ from $\eta_-(\zeta)$ gives
\[
\eta_+(\zeta) - \eta_-(\zeta) = 2\pi i \lambda^2 J(\zeta),
\]
and therefore, away from any zeros of $\eta_\mp(\zeta)$ on $\Gamma_\theta \setminus \{0\}$,
\[
\frac{1}{\eta_-(\zeta)} - \frac{1}{\eta_+(\zeta)}
= \frac{\eta_+(\zeta) - \eta_-(\zeta)}{\eta_-(\zeta)\eta_+(\zeta)}
= \frac{2\pi i \lambda^2 J(\zeta)}{\eta_-(\zeta)\eta_+(\zeta)}.
\tag{2.2}
\]

Similarly, denote the boundary values of $I_\pm(z;\phi_\pm)$ by
\[
I_{\pm,\mp}(\zeta) = I_\pm(\zeta \mp i0_\theta; \phi_\pm)
= \int_{\Gamma_\theta} \frac{g_\pm(\zeta')}{\zeta - \zeta' \mp i0_\theta}\,d\zeta',
\tag{2.3}
\]
where $g_-(\zeta') = V(\zeta')\phi_-^*(\zeta')$ and $g_+(\zeta') = \overline{V(\bar\zeta')}\phi_+(\zeta')$. By (1.5),
\[
I_{-,-}(\zeta) - I_{-,+}(\zeta) = 2\pi i\,V(\zeta)\phi_-^*(\zeta),
\tag{2.4a}
\]
\[
I_{+,-}(\zeta) - I_{+,+}(\zeta) = 2\pi i\,\overline{V(\bar\zeta)}\phi_+(\zeta).
\tag{2.4b}
\]

---

## 3. Block-by-block jump evaluation

We now compute
\[
\Delta \mathcal M_{ab}(\zeta)
:= \mathcal M_{ab}(\zeta - i0_\theta) - \mathcal M_{ab}(\zeta + i0_\theta)
\]
for each of the four blocks in (1.2).

### 3.1 Discrete–discrete block ($\Delta \mathcal M_{11}$)
From (1.2a) and (2.2):
\[
\Delta \mathcal M_{11}(\zeta)
= \overline{c_-}\,c_+ \left( \frac{1}{\eta_-(\zeta)} - \frac{1}{\eta_+(\zeta)} \right)
= 2\pi i \left[
\frac{\lambda \overline{V(\bar\zeta)}}{\eta_-(\zeta)}\overline{c_-}
\cdot
\frac{\lambda V(\zeta)}{\eta_+(\zeta)}c_+
\right],
\tag{3.1}
\]
using $J(\zeta) = V(\zeta)\overline{V(\bar\zeta)}$.

### 3.2 Discrete–continuum block ($\Delta \mathcal M_{1c}$)
From (1.2b), add and subtract $\frac{1}{\eta_-(\zeta)}I_{+,+}(\zeta)$:
\[
\begin{aligned}
\Delta \mathcal M_{1c}(\zeta)
&= \lambda \overline{c_-} \left( \frac{I_{+,-}(\zeta)}{\eta_-(\zeta)} - \frac{I_{+,+}(\zeta)}{\eta_+(\zeta)} \right) \\
&= \lambda \overline{c_-} \left[
\frac{I_{+,-}(\zeta) - I_{+,+}(\zeta)}{\eta_-(\zeta)}
+ \left( \frac{1}{\eta_-(\zeta)} - \frac{1}{\eta_+(\zeta)} \right) I_{+,+}(\zeta)
\right].
\end{aligned}
\]
Substituting (2.4b) and (2.2) into this expression gives
\[
\begin{aligned}
\Delta \mathcal M_{1c}(\zeta)
&= 2\pi i \lambda \overline{c_-} \left[
\frac{\overline{V(\bar\zeta)}\,\phi_+(\zeta)}{\eta_-(\zeta)}
+ \frac{\lambda^2 V(\zeta)\overline{V(\bar\zeta)}}{\eta_-(\zeta)\eta_+(\zeta)}\,I_{+,+}(\zeta)
\right] \\
&= 2\pi i \left[
\frac{\lambda \overline{V(\bar\zeta)}}{\eta_-(\zeta)}\overline{c_-}
\left( \phi_+(\zeta) + \frac{\lambda V(\zeta)}{\eta_+(\zeta)}\,I_{+,+}(\zeta) \right)
\right].
\end{aligned}
\tag{3.2}
\]

### 3.3 Continuum–discrete block ($\Delta \mathcal M_{c1}$)
From (1.2c), add and subtract $\frac{1}{\eta_+(\zeta)}I_{-,-}(\zeta)$:
\[
\begin{aligned}
\Delta \mathcal M_{c1}(\zeta)
&= \lambda c_+ \left( \frac{I_{-,-}(\zeta)}{\eta_-(\zeta)} - \frac{I_{-,+}(\zeta)}{\eta_+(\zeta)} \right) \\
&= \lambda c_+ \left[
\left( \frac{1}{\eta_-(\zeta)} - \frac{1}{\eta_+(\zeta)} \right) I_{-,-}(\zeta)
+ \frac{I_{-,-}(\zeta) - I_{-,+}(\zeta)}{\eta_+(\zeta)}
\right].
\end{aligned}
\]
Substituting (2.2) and (2.4a) yields
\[
\begin{aligned}
\Delta \mathcal M_{c1}(\zeta)
&= 2\pi i \lambda c_+ \left[
\frac{\lambda^2 V(\zeta)\overline{V(\bar\zeta)}}{\eta_-(\zeta)\eta_+(\zeta)}\,I_{-,-}(\zeta)
+ \frac{V(\zeta)\phi_-^*(\zeta)}{\eta_+(\zeta)}
\right] \\
&= 2\pi i \left[
\left( \phi_-^*(\zeta) + \frac{\lambda \overline{V(\bar\zeta)}}{\eta_-(\zeta)}\,I_{-,-}(\zeta) \right)
\frac{\lambda V(\zeta)}{\eta_+(\zeta)}c_+
\right].
\end{aligned}
\tag{3.3}
\]

### 3.4 Continuum–continuum block ($\Delta \mathcal M_{cc}$)
From (1.2d), split $\Delta \mathcal M_{cc}(\zeta) = \Delta \mathcal M_{cc}^{(0)}(\zeta) + \Delta \mathcal M_{cc}^{(\lambda)}(\zeta)$.

First, by (1.5) applied to $g(\zeta') = \phi_-^*(\zeta')\phi_+(\zeta')$:
\[
\Delta \mathcal M_{cc}^{(0)}(\zeta)
= \int_{\Gamma_\theta} \frac{\phi_-^*(\zeta')\phi_+(\zeta')}{\zeta - \zeta' - i0_\theta}\,d\zeta'
- \int_{\Gamma_\theta} \frac{\phi_-^*(\zeta')\phi_+(\zeta')}{\zeta - \zeta' + i0_\theta}\,d\zeta'
= 2\pi i\,\phi_-^*(\zeta)\phi_+(\zeta).
\tag{3.4a}
\]

Second, for the interaction term $\Delta \mathcal M_{cc}^{(\lambda)}(\zeta)$, telescope across the three factors:
\[
\begin{aligned}
\frac{I_{-,-}(\zeta)I_{+,-}(\zeta)}{\eta_-(\zeta)}
- \frac{I_{-,+}(\zeta)I_{+,+}(\zeta)}{\eta_+(\zeta)}
={}& \frac{I_{-,-}(\zeta) - I_{-,+}(\zeta)}{\eta_+(\zeta)}\,I_{+,+}(\zeta) \\
&+ I_{-,-}(\zeta)\,\frac{I_{+,-}(\zeta) - I_{+,+}(\zeta)}{\eta_-(\zeta)} \\
&+ I_{-,-}(\zeta)\left(\frac{1}{\eta_-(\zeta)} - \frac{1}{\eta_+(\zeta)}\right)I_{+,+}(\zeta).
\end{aligned}
\]
Multiplying by $\lambda^2$ and inserting (2.4a), (2.4b), and (2.2) gives
\[
\begin{aligned}
\Delta \mathcal M_{cc}^{(\lambda)}(\zeta)
&= 2\pi i \left[
\phi_-^*(\zeta)\,\frac{\lambda V(\zeta)}{\eta_+(\zeta)}I_{+,+}(\zeta)
+ \frac{\lambda \overline{V(\bar\zeta)}}{\eta_-(\zeta)}I_{-,-}(\zeta)\,\phi_+(\zeta)
+ \frac{\lambda \overline{V(\bar\zeta)}}{\eta_-(\zeta)}I_{-,-}(\zeta)\cdot
  \frac{\lambda V(\zeta)}{\eta_+(\zeta)}I_{+,+}(\zeta)
\right].
\end{aligned}
\tag{3.4b}
\]

---

## 4. Assembly into the rank-one factorization (7.3)

Summing (3.1), (3.2), (3.3), (3.4a), and (3.4b) and dividing by $2\pi i$:
\[
\begin{aligned}
\frac{1}{2\pi i} \langle\phi_-|[R(\zeta) - R_+(\zeta)]|\phi_+\rangle
={}& \left(
\phi_-^*(\zeta)
+ \frac{\lambda\overline{V(\bar\zeta)}}{\eta_-(\zeta)}
\left[ \overline{c_-} + \lambda I_{-,-}(\zeta) \right]
\right) \\
&\times \left(
\phi_+(\zeta)
+ \frac{\lambda V(\zeta)}{\eta_+(\zeta)}
\left[ c_+ + \lambda I_{+,+}(\zeta) \right]
\right).
\end{aligned}
\tag{4.1}
\]

Recalling the definitions of $I_{-,-}(\zeta)$ and $I_{+,+}(\zeta)$ from (2.3) and (1.2b)–(1.2c), the two factors on the right-hand side of (4.1) are identically the corrected deformed-continuum functionals of Stage 1 (Eqs. (7.4a)–(7.4b)):
\[
\langle\phi_-|\psi_\zeta^R\rangle
= \phi_-^*(\zeta)
+ \frac{\lambda\overline{V(\bar\zeta)}}{\eta_-(\zeta)}
\left[
\overline{c_-}
+ \lambda \int_{\Gamma_\theta} \frac{V(\zeta')\phi_-^*(\zeta')}{\zeta - \zeta' - i0_\theta}\,d\zeta'
\right],
\tag{4.2a}
\]
\[
\langle\psi_\zeta^L|\phi_+\rangle
= \phi_+(\zeta)
+ \frac{\lambda V(\zeta)}{\eta_+(\zeta)}
\left[
c_+
+ \lambda \int_{\Gamma_\theta} \frac{\overline{V(\bar\zeta')}\phi_+(\zeta')}{\zeta - \zeta' + i0_\theta}\,d\zeta'
\right].
\tag{4.2b}
\]

Hence, for every $\zeta \in \Gamma_\theta \setminus \{0\}$ away from zeros of $\eta_\mp(\zeta)$ and for all $|\phi_\pm\rangle \in \Phi$,
\[
\frac{1}{2\pi i}\langle\phi_-|[R(\zeta) - R_+(\zeta)]|\phi_+\rangle
= \langle\phi_-|\psi_\zeta^R\rangle \langle\psi_\zeta^L|\phi_+\rangle.
\tag{4.3}
\]

---

## 5. Verification summary and implications for Stage 2

1. **Exactness of the rank-one structure:** All nine cross-terms generated by expanding $\langle\phi_-|\psi_\zeta^R\rangle\langle\psi_\zeta^L|\phi_+\rangle$ match the four resolvent block jumps term for term, with no residual distributional remainder on $\Gamma_\theta \setminus \{0\}$.
2. **Orientation lock-in for Stage 2:** The derivation confirms that $\langle\phi_-|\psi_\zeta^R\rangle$ strictly carries the lower ray boundary value $\eta_-(\zeta)^{-1}$ and $-i0_\theta$ Cauchy prescription, while $\langle\psi_\zeta^L|\phi_+\rangle$ strictly carries the upper ray boundary value $\eta_+(\zeta)^{-1}$ and $+i0_\theta$ Cauchy prescription. Any Stage 2 Liouville lift (constructing forward-time Liouville functionals $\langle\langle \Phi_- | \Psi_{\zeta,\zeta'}^R \rangle\rangle$ and $\langle\langle \Psi_{\zeta,\zeta'}^L | \Phi_+ \rangle\rangle$) must preserve this pairing orientation across both ket and bra tensor factors.