# Explicit Derivation of the Liouville Resonance Eigenoperator $F_{z_0,z_0^*}$ in the Friedrichs Model

## 1. Analyticity Assumptions and the Holomorphic Coupling Density $J(z)$

On the single-excitation Hilbert space $\mathcal{H} = \mathbb{C}|1\rangle \oplus L^2(\mathbb{R}^+, d\omega)$, consider the Friedrichs Hamiltonian $H = H_0 + \lambda V$ with $\hbar = 1$:

$$H_0 = \omega_1 |1\rangle\langle 1| + \int_0^\infty \omega |\omega\rangle\langle\omega|\,d\omega, \qquad V = \int_0^\infty \left[V(\omega)|1\rangle\langle\omega| + V^*(\omega)|\omega\rangle\langle 1|\right] d\omega.$$

Under the weak-coupling no-bound-state condition

$$\lambda^2 \int_0^\infty \frac{|V(\omega)|^2}{\omega}\,d\omega < \omega_1,$$

with $|V(\omega)| > 0$ on $(0, \infty)$, the Hamiltonian $H$ has purely absolutely continuous spectrum $\sigma(H) = \sigma_{\mathrm{ac}}(H) = [0, \infty)$ and empty point spectrum $\sigma_{\mathrm{p}}(H) = \emptyset$.

To define generalized resonance states rigorously via analytic continuation of the resolvent $R(z) = (z - H)^{-1}$, we specify the exact analyticity class of the coupling form factor $V(\omega)$:

> **Assumption 1.1 (Analytic Form Factor on a Conjugation-Symmetric Domain):**  
> Assume $V(\omega)$ is the boundary value on $\mathbb{R}^+ = (0, \infty)$ of a function $V(z)$ holomorphic in an open complex neighborhood $\mathcal{W} \subset \mathbb{C}$ containing $(0, \infty)$ and symmetric under complex conjugation ($\mathcal{W}^* = \mathcal{W}$), with $V(\omega) \neq 0$ on $(0, \infty)$, integrability near $\omega = 0$, and rapid decay as $\omega \to \infty$. Define the **Schwarz-reflected holomorphic coupling density**:
> $$J(z) \equiv V(z)\overline{V(\bar{z})}, \qquad z \in \mathcal{W}. \tag{1}$$

For real $\omega > 0$, $J(\omega) = |V(\omega)|^2 > 0$, and $J(\bar{z}) = \overline{J(z)}$ throughout $\mathcal{W}$.

### Second-Sheet Continuation of the Dispersion Function

For $z \in \mathbb{C} \setminus [0, \infty)$, the physical-sheet dispersion function is

$$\eta(z) = z - \omega_1 - \lambda^2 \int_0^\infty \frac{J(\omega)}{z - \omega}\,d\omega. \tag{2}$$

Across the branch cut $(0, \infty)$, the boundary values $\eta(E \pm i0) = \lim_{\epsilon \downarrow 0} \eta(E \pm i\epsilon)$ satisfy the jump relation

$$\eta(E + i0) - \eta(E - i0) = +2\pi i \lambda^2 J(E), \qquad E > 0. \tag{3}$$

Consequently:
1. Continuing $\eta(z)$ analytically from the **upper half-plane** $\mathbb{C}_+$ downward across $(0, \infty)$ into $\mathcal{W}_- \equiv \mathcal{W} \cap \mathbb{C}_-$ defines the lower-sheet dispersion function $\eta_+(z)$:
   $$\eta_+(z) = \eta(z) + 2\pi i \lambda^2 J(z), \qquad z \in \mathcal{W}_-. \tag{4}$$
2. Continuing $\eta(z)$ analytically from the **lower half-plane** $\mathbb{C}_-$ upward across $(0, \infty)$ into $\mathcal{W}_+ \equiv \mathcal{W} \cap \mathbb{C}_+$ defines the upper-sheet dispersion function $\eta_-(z)$:
   $$\eta_-(z) = \eta(z) - 2\pi i \lambda^2 J(z), \qquad z \in \mathcal{W}_+. \tag{5}$$

Note that $\eta_-(\bar{z}) = \overline{\eta_+(z)}$ for all $z \in \mathcal{W}_-$.

For sufficiently small $\lambda > 0$, Rouché's theorem applied around $z = \omega_1 > 0$ guarantees a unique simple zero $z_0 \in \mathcal{W}_-$ of $\eta_+(z)$ and its complex-conjugate simple zero $z_0^* \in \mathcal{W}_+$ of $\eta_-(z)$:

$$\eta_+(z_0) = 0, \qquad \eta_-(z_0^*) = 0, \qquad z_0 = \tilde{\omega}_1 - i\frac{\gamma}{2}, \qquad z_0^* = \tilde{\omega}_1 + i\frac{\gamma}{2}, \qquad \gamma > 0. \tag{6}$$

The residues of the continued inverse dispersion functions $\eta_+(z)^{-1}$ at $z_0$ and $\eta_-(z)^{-1}$ at $z_0^*$ are:

$$A_1 \equiv \operatorname{Res}_{z=z_0} \frac{1}{\eta_+(z)} = \frac{1}{\eta_+'(z_0)}, \qquad A_1^* = \operatorname{Res}_{z=z_0^*} \frac{1}{\eta_-(z)} = \frac{1}{\eta_-'(z_0^*)}. \tag{7}$$

---

## 2. Spectral Representation of $H$ and Generalized Resonance Vectors

### 2.1 Spectral Resolution of the Resolvent

The outgoing ($+$) and incoming ($-$) Lippmann–Schwinger scattering eigenstates of $H$ (continuum-normalized via $\langle \psi_\omega^\pm | \psi_{\omega'}^\pm \rangle = \delta(\omega - \omega')$) are:

$$|\psi_\omega^\pm\rangle = |\omega\rangle + \frac{\lambda V(\omega)}{\eta(\omega \pm i0)} \left( |1\rangle + \int_0^\infty \frac{\lambda \overline{V(\omega')}}{\omega - \omega' \pm i0} |\omega'\rangle \, d\omega' \right), \qquad \omega > 0. \tag{8}$$

Since $\sigma(H) = \sigma_{\mathrm{ac}}(H) = [0, \infty)$, the physical resolvent $R(z) = (z - H)^{-1}$ has the exact spectral representation on $\mathcal{H}$ for all $z \in \mathbb{C} \setminus [0, \infty)$:

$$R(z) = \int_0^\infty \frac{|\psi_\omega^+\rangle\langle\psi_\omega^+|}{z - \omega} \, d\omega = \int_0^\infty \frac{|\psi_\omega^-\rangle\langle\psi_\omega^-|}{z - \omega} \, d\omega. \tag{9}$$

Let $\Phi_\pm \subset \mathcal{H}$ denote the dense test spaces of vectors $|\phi\rangle = c|1\rangle + \int_0^\infty \phi(\omega)|\omega\rangle\,d\omega$ whose continuum components $\phi(\omega)$ extend holomorphically into $\mathcal{W}_\pm$ with rapid decay at infinity, forming the Gelfand triplets

$$\Phi_\pm \subset \mathcal{H} \subset \Phi_\pm^\times,$$

where $\Phi_\pm^\times$ is the topological antidual (the space of continuous antilinear functionals on $\Phi_\pm$).

### 2.2 Analytic Continuation of Matrix Elements $\langle \phi_- | R(z) | \phi_+ \rangle$

Take $|\phi_-\rangle \in \Phi_-$ and $|\phi_+\rangle \in \Phi_+$. Using the exact block resolvent of $H$, the matrix element $\langle \phi_- | R(z) | \phi_+ \rangle$ for $\operatorname{Im} z > 0$ reads:

$$\langle \phi_- | R(z) | \phi_+ \rangle = \int_0^\infty \frac{\overline{\phi_-(\bar{\omega})}\phi_+(\omega)}{z - \omega}\,d\omega + \frac{1}{\eta(z)} \left( \overline{c_-} + \lambda \int_0^\infty \frac{V(\omega)\overline{\phi_-(\bar{\omega})}}{z - \omega}\,d\omega \right) \left( c_+ + \lambda \int_0^\infty \frac{\overline{V(\omega')}\phi_+(\omega')}{z - \omega'}\,d\omega' \right). \tag{10}$$

Analytically continuing $\langle \phi_- | R(z) | \phi_+ \rangle$ from $\mathbb{C}_+$ downward across $(0, \infty)$ into $\mathcal{W}_-$:
- The first integral $\int_0^\infty \frac{\overline{\phi_-(\bar{\omega})}\phi_+(\omega)}{z - \omega}\,d\omega$ continues to $\int_0^\infty \frac{\overline{\phi_-(\bar{\omega})}\phi_+(\omega)}{z - \omega}\,d\omega + 2\pi i \overline{\phi_-(\bar{z})}\phi_+(z)$, which is **holomorphic** in $\mathcal{W}_-$ (no pole at $z_0$).
- In the second term, $\eta(z)^{-1}$ continues to $\eta_+(z)^{-1}$, which possesses a **simple pole at $z = z_0 \in \mathcal{W}_-$** with residue $A_1 = [\eta_+'(z_0)]^{-1}$.
- The two Cauchy-integral factors continue across $(0, \infty)$ into $\mathcal{W}_-$ by adding their respective $2\pi i$-residues at $\omega = z$:
  $$\mathcal{C}_-(z; \phi_-) \equiv \overline{c_-} + \lambda \int_0^\infty \frac{V(\omega)\overline{\phi_-(\bar{\omega})}}{z - \omega}\,d\omega + 2\pi i \lambda V(z)\overline{\phi_-(\bar{z})}, \tag{11a}$$
  $$\mathcal{C}_+(z; \phi_+) \equiv c_+ + \lambda \int_0^\infty \frac{\overline{V(\omega')}\phi_+(\omega')}{z - \omega'}\,d\omega' + 2\pi i \lambda \overline{V(\bar{z})}\phi_+(z). \tag{11b}$$

### 2.3 Extraction of the Right and Left Gamow–Siegert Resonance Vectors

Taking the residue at $z = z_0 \in \mathcal{W}_-$ of the analytically continued resolvent matrix element $\langle \phi_- | R_+(z) | \phi_+ \rangle$ yields a **rank-one residue operator**:

$$\operatorname{Res}_{z = z_0} \langle \phi_- | R_+(z) | \phi_+ \rangle = A_1 \, \mathcal{C}_-(z_0; \phi_-) \, \mathcal{C}_+(z_0; \phi_+) \equiv \langle \phi_- | \psi_{z_0} \rangle \langle \tilde{\psi}_{z_0} | \phi_+ \rangle. \tag{12}$$

Reading off the functionals $|\psi_{z_0}\rangle \in \Phi_-^\times$ and $\langle \tilde{\psi}_{z_0}| \in \Phi_+^\times$ from (11a)–(11b) gives the **exact generalized outgoing resonance vector** $|\psi_{z_0}\rangle$ and its **dual left resonance covector** $\langle \tilde{\psi}_{z_0}|$:

$$|\psi_{z_0}\rangle = \sqrt{A_1} \left( |1\rangle + \int_0^\infty \frac{\lambda \overline{V(\omega)}}{(z_0 - \omega)_+} |\omega\rangle \, d\omega \right) \in \Phi_-^\times, \tag{13a}$$

$$\langle \tilde{\psi}_{z_0}| = \sqrt{A_1} \left( \langle 1| + \int_0^\infty \frac{\lambda V(\omega)}{(z_0 - \omega)_+} \langle\omega| \, d\omega \right) \in \Phi_+^\times, \tag{13b}$$

where the subscript $(z_0 - \omega)_+$ denotes the deformed contour passing **below** $z_0 \in \mathbb{C}_-$ (equivalently, adding the residue term $2\pi i \lambda \overline{V(\bar{z}_0)}\delta(\omega - z_0)$ in the pairing with test functions).

Analogously, continuing $\langle \phi_+ | R(z) | \phi_- \rangle$ from $\mathbb{C}_-$ upward across $(0, \infty)$ into $\mathcal{W}_+$ isolates the pole at $z = z_0^* \in \mathcal{W}_+$ with residue $A_1^* = [\eta_-'(z_0^*)]^{-1}$, defining the **incoming resonance vector** $|\psi_{z_0^*}\rangle \in \Phi_+^\times$ and its dual $\langle \tilde{\psi}_{z_0^*}| \in \Phi_-^\times$:

$$|\psi_{z_0^*}\rangle = \sqrt{A_1^*} \left( |1\rangle + \int_0^\infty \frac{\lambda \overline{V(\omega)}}{(z_0^* - \omega)_-} |\omega\rangle \, d\omega \right) \in \Phi_+^\times, \tag{14a}$$

$$\langle \tilde{\psi}_{z_0^*}| = \sqrt{A_1^*} \left( \langle 1| + \int_0^\infty \frac{\lambda V(\omega)}{(z_0^* - \omega)_-} \langle\omega| \, d\omega \right) \in \Phi_-^\times, \tag{14b}$$

where $(z_0^* - \omega)_-$ passes **above** $z_0^* \in \mathbb{C}_+$.

> **Lemma 2.1 (Exact Eigenvalue and Biorthogonal Normalization Relations):**
> 1. **Generalized Eigenvalue Equations:** On the dual spaces $\Phi_-^\times$ and $\Phi_+^\times$, the extended Hamiltonians $H^\times$ satisfy:
>    $$H^\times |\psi_{z_0}\rangle = z_0 |\psi_{z_0}\rangle, \qquad \langle \tilde{\psi}_{z_0}| H = z_0 \langle \tilde{\psi}_{z_0}|, \qquad H^\times |\psi_{z_0^*}\rangle = z_0^* |\psi_{z_0^*}\rangle, \qquad \langle \tilde{\psi}_{z_0^*}| H = z_0^* \langle \tilde{\psi}_{z_0^*}|. \tag{15}$$
>    *Proof:* Evaluating $(z_0 - H^\times)|\psi_{z_0}\rangle$ yields the discrete component $\sqrt{A_1}\bigl[(z_0 - \omega_1) - \lambda^2 \int_0^\infty \frac{J(\omega)}{(z_0 - \omega)_+}\,d\omega\bigr] = \sqrt{A_1}\,\eta_+(z_0) = 0$, while the continuum component is $\sqrt{A_1}\bigl[(z_0 - \omega)\frac{\lambda \overline{V(\omega)}}{(z_0 - \omega)_+} - \lambda \overline{V(\omega)}\bigr] = 0$ as a functional on $\Phi_-$.
> 2. **Exact Biorthogonal Normalization:** Evaluating the duality pairing $\langle \tilde{\psi}_{z_0} | \psi_{z_0} \rangle$ (defined via the residue of $R_+(z)$ at $z_0$) gives:
>    $$\langle \tilde{\psi}_{z_0} | \psi_{z_0} \rangle = A_1 \left[ 1 + \lambda^2 \int_0^\infty \frac{J(\omega)}{(z_0 - \omega)_+^2} \, d\omega \right] = A_1 \, \eta_+'(z_0) = 1, \qquad \langle \tilde{\psi}_{z_0^*} | \psi_{z_0^*} \rangle = A_1^* \, \eta_-'(z_0^*) = 1. \tag{16}$$
> 3. **Overlaps with the Bare State $|1\rangle$:** Because $|1\rangle \in \Phi_- \cap \Phi_+$, its pairings with all four resonance functionals are finite and exact:
>    $$\langle 1 | \psi_{z_0} \rangle = \sqrt{A_1}, \qquad \langle \tilde{\psi}_{z_0} | 1 \rangle = \sqrt{A_1}, \qquad \langle 1 | \psi_{z_0^*} \rangle = \sqrt{A_1^*}, \qquad \langle \tilde{\psi}_{z_0^*} | 1 \rangle = \sqrt{A_1^*}. \tag{17}$$

---

## 3. Construction of the Liouville Resonance Eigenoperator $F_{z_0,z_0^*}$

Now lift the rigged Hilbert space to the **rigged Liouville space** $\mathcal{B}_- \subset \mathcal{B}_2(\mathcal{H}) \subset \mathcal{B}_-^\times$, where $\mathcal{B}_- \equiv \Phi_- \widehat{\otimes}_\pi \Phi_+$ consists of trace-class test operators $\sigma = \sum c_{ij} |\phi_{-,i}\rangle\langle \phi_{+,j}|$ (analytic in $\mathcal{W}_-$ in the ket variable and in $\mathcal{W}_+$ in the bra variable).

### 3.1 Definition of $F_{z_0,z_0^*}$ and Its Dual $\widetilde{F}_{z_0,z_0^*}$

To obtain a **Hermitian** Liouville density mode with eigenvalue $z_0 - z_0^* = -i\gamma$, we must pair the outgoing ket $|\psi_{z_0}\rangle \in \Phi_-^\times$ with its **own adjoint bra** $\langle \psi_{z_0}| \in (\Phi_+^\times)^*$ (note that pairing $|\psi_{z_0}\rangle$ with $\langle \psi_{z_0^*}|$ would yield eigenvalue $z_0 - (z_0^*)^* = 0$, whereas $\langle \psi_{z_0}|$ carries the conjugated eigenvalue $\overline{z_0} = z_0^*$):

$$F_{z_0,z_0^*} \equiv |\psi_{z_0}\rangle \langle \psi_{z_0}| \in \mathcal{B}_-^\times. \tag{18}$$

Correspondingly, define its **biorthogonal dual eigenoperator** $\widetilde{F}_{z_0,z_0^*} \in \mathcal{B}_+^\times$ (where $\mathcal{B}_+ = \Phi_+ \widehat{\otimes}_\pi \Phi_-$) by:

$$\widetilde{F}_{z_0,z_0^*} \equiv |\tilde{\psi}_{z_0}\rangle \langle \tilde{\psi}_{z_0}| \in \mathcal{B}_+^\times. \tag{19}$$

Under the Liouville duality pairing $\langle\!\langle \sigma | F_{z_0,z_0^*} \rangle\!\rangle \equiv \operatorname{Tr}(\sigma^\dagger F_{z_0,z_0^*})$, the action on any factorized test operator $\sigma = |\phi_-\rangle\langle \phi_+| \in \mathcal{B}_-$ is:

$$\langle\!\langle |\phi_-\rangle\langle\phi_+| \,\big|\, F_{z_0,z_0^*} \rangle\!\rangle = \langle \phi_- | \psi_{z_0} \rangle \langle \psi_{z_0} | \phi_+ \rangle = |A_1| \, \mathcal{C}_-(z_0; \phi_-) \, \overline{\mathcal{C}_-(z_0; \phi_+)}, \tag{20}$$

and the biorthogonal pairing between $\widetilde{F}_{z_0,z_0^*}$ and $F_{z_0,z_0^*}$ is normalized to unity:

$$\langle\!\langle \widetilde{F}_{z_0,z_0^*} \,\big|\, F_{z_0,z_0^*} \rangle\!\rangle = \langle \tilde{\psi}_{z_0} | \psi_{z_0} \rangle \langle \psi_{z_0} | \tilde{\psi}_{z_0} \rangle = 1 \cdot 1 = 1. \tag{21}$$

### 3.2 Proof of the Liouville Eigenvalue Equation

For any $\sigma \in \mathcal{B}_-$, the extended Liouvillian $L^\times : \mathcal{B}_-^\times \to \mathcal{B}_-^\times$ is defined by duality from $L\sigma = [H, \sigma]$:

$$\langle\!\langle \sigma \,\big|\, L^\times F_{z_0,z_0^*} \rangle\!\rangle \equiv \langle\!\langle L\sigma \,\big|\, F_{z_0,z_0^*} \rangle\!\rangle = \langle\!\langle H\sigma - \sigma H \,\big|\, |\psi_{z_0}\rangle\langle\psi_{z_0}| \rangle\!\rangle. \tag{22}$$

Evaluating on $\sigma = |\phi_-\rangle\langle\phi_+|$ and using Lemma 2.1 (Eq. 15) together with $\langle \psi_{z_0} | H\phi_+ \rangle = \overline{\langle H\phi_+ | \psi_{z_0} \rangle} = \overline{z_0} \langle \psi_{z_0} | \phi_+ \rangle = z_0^* \langle \psi_{z_0} | \phi_+ \rangle$:

$$\begin{aligned}
\langle\!\langle |\phi_-\rangle\langle\phi_+| \,\big|\, L^\times F_{z_0,z_0^*} \rangle\!\rangle &= \langle H\phi_- | \psi_{z_0} \rangle \langle \psi_{z_0} | \phi_+ \rangle - \langle \phi_- | \psi_{z_0} \rangle \langle \psi_{z_0} | H\phi_+ \rangle \\
&= (z_0 - z_0^*) \langle \phi_- | \psi_{z_0} \rangle \langle \psi_{z_0} | \phi_+ \rangle = -i\gamma \, \langle\!\langle |\phi_-\rangle\langle\phi_+| \,\big|\, F_{z_0,z_0^*} \rangle\!\rangle.
\end{aligned} \tag{23}$$

Because finite sums of factorized operators $|\phi_-\rangle\langle\phi_+|$ are dense in $\mathcal{B}_- = \Phi_- \widehat{\otimes}_\pi \Phi_+$, we obtain the exact eigenvalue equation in $\mathcal{B}_-^\times$:

$$L^\times F_{z_0,z_0^*} = (z_0 - z_0^*) F_{z_0,z_0^*} = -i\gamma \, F_{z_0,z_0^*}, \qquad F_{z_0,z_0^*} = |\psi_{z_0}\rangle\langle\psi_{z_0}| = F_{z_0,z_0^*}^\dagger. \tag{24}$$

If $\Lambda^{-1}$ is an intertwining operator satisfying $\Phi \Lambda^{-1} = \Lambda^{-1} L^\times$ on a domain containing $F_{z_0,z_0^*}$, applying $\Lambda^{-1}$ to (24) yields:

$$\Phi \left(\Lambda^{-1} F_{z_0,z_0^*}\right) = \Lambda^{-1} L^\times F_{z_0,z_0^*} = (z_0 - z_0^*) \left(\Lambda^{-1} F_{z_0,z_0^*}\right). \tag{25}$$

---

## 4. Decisive Comparison: Is $F_{z_0,z_0^*}$ the Bare Projector $|1\rangle\langle 1|$?

### 4.1 Exact Decomposition in Physical Liouville Space

1. **Distinctness in $\mathcal{B}_-^\times$:**  
   The bare excited-state projector $|1\rangle\langle 1|$ belongs to $\mathcal{B}_- \subset \mathcal{B}_2(\mathcal{H})$, whereas $F_{z_0,z_0^*} = |\psi_{z_0}\rangle\langle\psi_{z_0}|$ belongs strictly to the dual distribution space $\mathcal{B}_-^\times \setminus \mathcal{B}_2(\mathcal{H})$. Expanding $|1\rangle\langle 1|$ in the biorthogonal resonance + deformed-continuum decomposition of $\mathcal{B}_-^\times$ via (17) and (21) gives:
   $$|1\rangle\langle 1| = \langle\!\langle \widetilde{F}_{z_0,z_0^*} \,\big|\, |1\rangle\langle 1| \rangle\!\rangle \, F_{z_0,z_0^*} + \rho_{\mathrm{cut}}, \tag{26}$$
   where the exact projection coefficient is computed from (17):
   $$\langle\!\langle \widetilde{F}_{z_0,z_0^*} \,\big|\, |1\rangle\langle 1| \rangle\!\rangle = \langle \tilde{\psi}_{z_0} | 1 \rangle \langle 1 | \tilde{\psi}_{z_0} \rangle = \sqrt{A_1}\,\sqrt{A_1^*} = |A_1| \neq 1 \quad (\text{for } \lambda \neq 0), \tag{27}$$
   and $\rho_{\mathrm{cut}} \in \mathcal{B}_-^\times$ is the non-zero continuous background component supported along the deformed cut ($\langle\!\langle \widetilde{F}_{z_0,z_0^*} | \rho_{\mathrm{cut}} \rangle\!\rangle = 0$). **Thus, in physical Liouville space, $|1\rangle\langle 1| \neq F_{z_0,z_0^*}$.**

2. **How Prigogine's Transformed Representation Connects Them:**  
   In Prigogine et al. (1977, Eqs. 3.6–3.8), $\Lambda^{-1} : \mathcal{D}(\Lambda^{-1}) \subset \mathcal{B}_-^\times \to \mathcal{B}_2(\mathcal{H})$ is constructed as a **biorthogonal basis transformation** mapping the generalized Gamow–continuum eigenbasis $\{F_{z_0,z_0^*}, F_{z_0,\omega'}, F_{\omega,z_0^*}, F_{\omega,\omega'}\}$ of $L^\times$ in $\mathcal{B}_-^\times$ onto the canonical bare basis $\{|1\rangle\langle 1|, |1\rangle\langle\omega'|, |\omega\rangle\langle 1|, |\omega\rangle\langle\omega'|\}$ of $\mathcal{B}_2(\mathcal{H})$:
   $$\Lambda^{-1} F_{z_0,z_0^*} = |1\rangle\langle 1|. \tag{28}$$
   Under this basis identification, applying $\Lambda^{-1}$ to (26) produces $\tilde{\rho}(0) = \Lambda^{-1}(|1\rangle\langle 1|) = |A_1|\,|1\rangle\langle 1| + \tilde{\rho}_{\mathrm{bg}}(0)$, while substituting (28) into (25) yields **deductively**:
   $$\Phi(|1\rangle\langle 1|) = \Phi \Lambda^{-1} F_{z_0,z_0^*} = \Lambda^{-1} L^\times F_{z_0,z_0^*} = -i\gamma |1\rangle\langle 1| \implies \left[(i\Phi)^e\right]_{11,11} = \gamma. \tag{29}$$

### 4.2 Summary of What Is Proved vs. What Remains Open

| Statement | Logical Status |
| :--- | :--- |
| $L^\times F_{z_0,z_0^*} = -i\gamma F_{z_0,z_0^*}$ with $F_{z_0,z_0^*} = |\psi_{z_0}\rangle\langle\psi_{z_0}| \in \mathcal{B}_-^\times$ | **Proved** directly from the spectral representation of $H$ and analytic continuation of $R(z)$. |
| $\langle\!\langle \widetilde{F}_{z_0,z_0^*} | F_{z_0,z_0^*} \rangle\!\rangle = 1$ and $|1\rangle\langle 1| = |A_1| F_{z_0,z_0^*} + \rho_{\mathrm{cut}}$ | **Proved** via residue calculus and biorthogonal pairing; shows $|1\rangle\langle 1| \neq F_{z_0,z_0^*}$ physically. |
| $\Phi(|1\rangle\langle 1|) = -i\gamma |1\rangle\langle 1|$ and $[(i\Phi)^e]_{11,11} = \gamma$ | **Conditional** on establishing the complete biorthogonal basis map $\Lambda^{-1}$ sending $F_{z_0,z_0^*} \mapsto |1\rangle\langle 1|$ and satisfying $\Lambda^{-1}(L) = \Lambda^\dagger(-L)$. |
