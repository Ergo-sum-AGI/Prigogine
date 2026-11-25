# Microscopic Theory of Irreversible Processes — Equation-Level Reference

**Authors:** I. Prigogine, F. Mayné, C. George, and M. de Haan  
**Publication:** *Proc. Natl. Acad. Sci. USA*, Vol. 74, No. 10, pp. 4152–4156, October 1977  
**Subject Classification:** Physics (Friedrichs model / Statistical mechanics / Nonequilibrium entropy)

---

## 1. Introduction: Dynamical Representation & Liapounov Functionals

### Liouville–von Neumann Equation
The time evolution of the phase-space distribution function or quantum density operator $\rho$ is governed by:

$$i\frac{\partial \rho}{\partial t} = L\rho \tag{1.1}$$

where $L$ is the Liouville superoperator, defined classically via the Poisson bracket $i\{H, \cdot\}$ or quantum-mechanically via the commutator $[H, \cdot]$ with the Hamiltonian $H$.

### Invariance of Universal Functionals
Under general conditions, any universal functional $\Omega$ of $\rho$ (such as the Gibbs entropy $-k \int \rho \ln \rho \, d\Gamma$ or $-k \int \rho^2 \, d\Gamma$) remains constant in time:

$$\frac{d\Omega}{dt} = 0 \tag{1.2}$$

### Quadratic Liapounov Functional
To reconcile reversible dynamics with the second law without arbitrary coarse-graining, a positive quadratic functional of $\rho$ is introduced:

$$\Omega = \operatorname{Tr} \rho^+ M \rho > 0 \tag{1.3}$$

subject to the nonincreasing time-derivative condition:

$$\frac{d\Omega}{dt} \le 0 \tag{1.4}$$

where $M$ is a positive microscopic "entropy superoperator" that requires a continuous spectrum for $L$.

### Factorization & Transformed Representation
Because $M$ is positive, it can be factored in terms of a nonunitary superoperator $\Lambda^{-1}$ and its hermitian conjugate:

$$M = (\Lambda^{-1})^+ \Lambda^{-1} \tag{1.5}$$

Substituting Eq. (1.5) into Eq. (1.3) yields a universal quadratic form in the transformed representation $\tilde{\rho}$:

$$\Omega = \operatorname{Tr} \tilde{\rho}^+ \tilde{\rho} \quad \text{with} \quad \tilde{\rho} = \Lambda^{-1}\rho \tag{1.6}$$

### Contractive Semi-Group Evolution
Assuming the inverse transformation $\Lambda$ exists, $\tilde{\rho}$ obeys a contractive semi-group equation of motion:

$$i\frac{\partial \tilde{\rho}}{\partial t} = \Phi \tilde{\rho} \tag{1.7}$$

with the transformed evolution generator:

$$\Phi = \Lambda^{-1} L \Lambda \tag{1.8}$$

---

## 2. General Requirements on the Liapounov Functional

### Explicit Time Dependence & Entropy Production Superoperator
Using the formal solution $\rho(t) = e^{-iLt}\rho(0)$, the Liapounov functional and its time derivative read:

$$\Omega(t) = \operatorname{Tr}\left[\rho^+(0) e^{iLt} M e^{-iLt} \rho(0)\right] > 0 \tag{2.1}$$

$$\frac{d\Omega}{dt} = -\operatorname{Tr}\left[\rho^+(0) e^{iLt} i(ML - LM) e^{-iLt} \rho(0)\right] \le 0 \tag{2.2}$$

Thus $M$ cannot commute with $L$, and the superoperator

$$D \equiv i(ML - LM) \ge 0 \tag{2.3}$$

represents the microscopic **entropy production**.

### Dissipativity Condition in the $\tilde{\rho}$ Representation
Applying Eqs. (1.6) and (1.8) transforms the entropy production rate into:

$$\frac{d\Omega}{dt} = -\operatorname{Tr}\left[\tilde{\rho}^+(0) e^{i\Phi^+ t} i(\Phi - \Phi^+) e^{-i\Phi t} \tilde{\rho}(0)\right] \le 0 \tag{2.4}$$

which requires $\Phi$ to be nonhermitian and satisfy:

$$i(\Phi - \Phi^+) \ge 0 \tag{2.5}$$

### Invariance of Expectation Values
For observables $A$ and states $\rho$ in the appropriate domain, expectation values must remain invariant under the change of representation:

$$\langle A \rangle = \operatorname{Tr} A^+ \rho = \operatorname{Tr} \tilde{A}^+ \tilde{\rho} \tag{2.6}$$

Combined with Eq. (1.6), this determines the observable transformation:

$$A = (\Lambda^{-1})^+ \tilde{A} \tag{2.7}$$

### $L$-$t$ Symmetry Breaking & Starunitarity
In the Heisenberg-like picture, observables evolve according to:

$$i\frac{dA}{dt} = -LA \tag{2.8}$$

which differs from Eq. (1.1) by $L$-inversion ($L \to -L$). Requiring $\Lambda(L)$ on $\rho$ to correspond to $\Lambda(-L)$ on $A$ yields:

$$\left(\Lambda^{-1}(L)\right)^+ = \Lambda(-L) \tag{2.9}$$

or equivalently the **starunitarity** condition:

$$\Lambda(L)\Lambda^+(-L) = 1 \tag{2.10}$$

Using the star-conjugation notation:

$$\Lambda^* \equiv \Lambda^+(-L) \tag{2.11}$$

the generator $i\Phi$ is **starhermitian**:

$$(i\Phi)^* \equiv \left[i\Phi(-L)\right]^+ = i\Phi \tag{2.12}$$

### Decomposition into Reversible and Irreversible Generators
Starhermiticity allows $i\Phi$ to be decomposed into an even, hermitian part (superscript $e$) and an odd, antihermitian part (superscript $o$) under $L$-inversion:

$$i\Phi = (i\Phi)^e + (i\Phi)^o \tag{2.13}$$

where the dissipativity condition Eq. (2.5) becomes:

$$(i\Phi)^e \ge 0 \tag{2.14}$$

Consequently, the microscopic equation of motion Eq. (1.7) splits explicitly into reversible and irreversible components:

$$\frac{\partial \tilde{\rho}}{\partial t} = -\left[(i\Phi)^o + (i\Phi)^e\right]\tilde{\rho} \tag{2.15}$$

*(Note: In the footnote on p. 4153, the phenomenological one-particle relaxation equation illustrating broken $L$-$t$ symmetry is given as $\frac{\partial f}{\partial t} + v\frac{\partial f}{\partial x} = -\frac{f - f^0}{\tau}$ with $\tau > 0$.)*

---

## 3. Example: The Friedrichs Model

### Second-Quantized Hamiltonian
In second quantization, the Friedrichs model Hamiltonian describing a discrete state coupled to a field continuum is:

$$H = \omega_1 a_1^+ a_1 + \sum_k \omega_k a_k^+ a_k + \lambda \sum_k \left(V_k a_1^+ a_k + V_k^{\mathrm{cc}} a_k^+ a_1\right) \tag{3.1}$$

In the infinite-volume limit ($L^3 \to \infty$), $\omega_k$ forms a continuous spectrum $(0, \infty)$ with $\omega_1 > 0$ embedded in the continuum and no bound state. Matrix elements scale with volume $L^3$ as:
* $\rho_{11}, A_{11}, A_{kk} \sim \mathcal{O}(1)$
* $\rho_{1k}, A_{1k} \sim \mathcal{O}(L^{-3/2})$
* $\rho_{kk}, \rho_{kk'}, A_{kk'} \sim \mathcal{O}(L^{-3})$

### Green's Function & Dispersion Equation
The Green's function of particle $1$ is defined by:

$$\left(\frac{1}{z - H}\right)_{11} \equiv \frac{1}{\eta(z)} \tag{3.2}$$

where the dispersion function $\eta(z)$ is:

$$\eta(z) = z - \omega_1 - \sum_k \frac{|V_k|^2}{z - \omega_k} \tag{3.3}$$

In the infinite-volume limit, analytic continuations $\eta^+(z)^{-1}$ and $\eta^-(z)^{-1}$ across the positive real cut possess conjugate poles at $\omega_1 + \zeta$ and $\omega_1 + \zeta^{\mathrm{cc}}$ with residues $\mathcal{A}_1$ and $\mathcal{A}_1^{\mathrm{cc}}$.

### Exponential Modes & Cauchy Integrals
Each element of $\tilde{\rho}(t)$ contributing to $\Omega(t)$ evolves exponentially as:

$$e^{(ia + b)t} \quad (a, b \in \mathbb{R}, \; b \le 0) \tag{3.4}$$

Constructing $\tilde{\rho}$ in the infinite-volume limit involves Cauchy-type integrals evaluated for $\operatorname{Im} z > 0$ and analytically continued into the lower half-plane:

$$\int_0^\infty \frac{V(k)\rho_1(k)}{z + \omega_1 - \omega_k} \, dk \tag{3.5}$$

which restricts admissible states $\rho(0)$ and observables $A$ to smooth functions satisfying Cauchy integrality (excluding single classical delta-function trajectories).

### Evaluation of the Liapounov Functional & Lifetime
In the Friedrichs model, the Liapounov functional Eq. (1.6) expands in matrix elements as:

$$\Omega(t) = \tilde{\rho}_{11}(t)^2 + 2\sum_k |\tilde{\rho}_{k1}(t)|^2 + \sum_{kk'} |\tilde{\rho}_{kk'}(t)|^2 \tag{3.6}$$

which evaluates to:

$$\Omega(t) = e^{-2i(\zeta - \zeta^{\mathrm{cc}})t} u_1 + 2e^{-i(\zeta - \zeta^{\mathrm{cc}})t} u_2 + u_3 \tag{3.7}$$

with $u_1, u_2, u_3 > 0$. For an initial pure "bare" particle state ($\rho_{11}(0) = 1$, all other components zero):

$$u_1 = \mathcal{A}_1 \mathcal{A}_1^{\mathrm{cc}} \tag{3.8}$$

$$u_2 = \left(\mathcal{A}_1 \mathcal{A}_1^{\mathrm{cc}}\right)^{1/2} \tag{3.9}$$

$$u_3 = 1 \tag{3.10}$$

yielding the exact exponential decay of $\Omega(t)$:

$$\Omega(t) = \left(|\mathcal{A}_1| e^{-\gamma t} + 1\right)^2 \tag{3.11}$$

where $\gamma = i(\zeta - \zeta^{\mathrm{cc}})$ is the inverse particle lifetime ($\tau = \gamma^{-1}$).

### Nonexponential Expectation Values & Long Tails
Unlike $\Omega(t)$, expectation values $\langle A \rangle$ contain terms such as $\sum_k \tilde{\rho}_{1k}(t)\tilde{A}_{k1}$, leading to integrals of the form:

$$\int_0^\infty e^{-i(\omega_1 + \zeta - \omega_k)t} f(k) \, dk \tag{3.12}$$

whose asymptotic time dependence is governed by small-$k$ behavior, producing nonexponential decay and hydrodynamic "long tails" when damping scales as $k^2$.

### Perturbative Non-Commutativity & Lifetime Commutator Relation
The matrix element $M_{11,11}$ of the entropy superoperator is:

$$M_{11,11} = |\mathcal{A}_1|^2 + 2|\mathcal{A}_1| + 1 = \left(|\mathcal{A}_1| + 1\right)^2 \tag{3.13}$$

*(Note: In the weak-coupling limit $\lambda \to 0$, $M_{11,11} \to 4$, whereas $(\Lambda^{-1})^+ \Lambda^{-1}$ expanded term-by-term in $\lambda$ yields $1$ at zeroth order with divergent higher-order terms, demonstrating the necessity of partial resummation.)*

Finally, the inverse lifetime $\gamma$ is directly tied to the commutator of $L$ and $M$:

$$\left[(i\Phi)^e\right]_{11,11} = \gamma = \Lambda^+_{11,\dots} [LM - ML]_{\dots, 11} \tag{3.14}$$

---

## 4. Duality of Dynamic Description

Key structural relations highlighted in the concluding discussion:
* **Pure States vs. Mixtures:** The idempotency condition for pure states, $\rho^2 = \rho$, is not preserved in the transformed representation $\tilde{\rho} = \Lambda^{-1}\rho$ because $\Lambda$ is nonunitary and nonfactorizable. At any finite time $t > 0$, transforming back to $\rho(t)$ recovers a pure state, whereas the asymptotic attractor state $\tilde{\rho}_{\mathrm{st}}$ satisfies:

$$\Phi \tilde{\rho} = 0$$

* **Correlations:** Because $L$ and $M$ cannot be simultaneously diagonalized (Eq. 2.2), $\Lambda^{-1}$ mixes diagonal ($\rho_0$) and off-diagonal correlation components of $\rho$, capturing memory effects and long-time tails neglected by Boltzmann-type master equations.
