# Microscopic Theory of Irreversible Processes

**Authors:** I. Prigogine, F. Mayné, C. George, and M. de Haan  
**Affiliation:** Faculté des Sciences, Université Libre de Bruxelles, 1050 Bruxelles, Belgium; and Center for Statistical Mechanics and Thermodynamics, The University of Texas at Austin, Austin, Texas 78712  
**Contributed by:** I. Prigogine, June 20, 1977  
**Citation:** *Proc. Natl. Acad. Sci. USA*, Vol. 74, No. 10, pp. 4152–4156, October 1977 (Physics)

---

### ABSTRACT

A new formulation of the microscopic theory of irreversible processes is presented. Both Poincaré's and Gibbs–Einstein's points of view are incorporated: the dynamical evolution is expressed in terms of a contractive semi-group instead of a unitary group, without any stochastic assumption or "coarse graining." The transformation from the unitary group to the contractive semi-group is obtained by means of a nonunitary transformation that leads to a Liapounov function, which represents a microscopic model for entropy. The relation between entropy and particle lifetimes is illustrated on the Friedrichs model in second quantization. The conceptual significance of this new formulation is discussed.

---

## 1. Introduction

Traditional approaches to the microscopic interpretation of the second law of thermodynamics—be they Boltzmann-like equations, master equations, or "coarse graining"—introduce supplementary assumptions to the equations of classical or quantum mechanics (1). Moreover, the validity of such equations is restricted to simple limiting cases, as in the weak coupling limit. Modern developments in both equilibrium and nonequilibrium statistical mechanics make it imperative that we be able to go beyond such approximations. An example is provided by the so-called long tails in hydrodynamics, which cannot be understood without taking into account the detailed dynamical correlations between particles (2). A related problem is that of the meaning of entropy at the microscopic level.

In previous papers we have suggested a new point of view (3–5) that provides a formulation of the second law of thermodynamics directly in terms of dynamical concepts without any appeal to "coarse graining" or stochastic hypotheses.

We start from the evolution equation for the distribution function in phase space or the density operator $\rho$:

$$i\frac{\partial \rho}{\partial t} = L\rho \tag{1.1}$$

where $L$ is the Liouville operator, a superoperator defined in terms of the Poisson bracket $i\{H, \}$ in classical mechanics or the commutator $[H, ]$ in quantum mechanics. Notice that the sign of the right-hand side of **[1.1]** is the opposite of that used in some of our earlier publications (3–5) (so that here $L$ and $H$ have the same spectrum).

Any universal functional $\Omega$ of $\rho$, such as the Gibbs entropy $-k \int \rho \ln \rho \, d\Gamma$ (or $-k \int \rho^2 \, d\Gamma$), satisfies under general conditions:

$$\frac{d\Omega}{dt} = 0 \tag{1.2}$$

The basic question is: Can we find some functional $\Omega$ of $\rho$ that would play the role of a Liapounov function, i.e., such that:

$$\Omega = \operatorname{Tr} \rho^+ M \rho > 0 \tag{1.3}$$

and

$$\frac{d\Omega}{dt} \le 0 \tag{1.4}$$

We have restricted our attention to functionals that are quadratic in $\rho$, because in the transformed representation introduced below, $\Omega$ takes a universal form (see **[1.6]**). Notice that the trace implies an integration over phase space in classical mechanics or summation over diagonal elements in quantum mechanics.

If we could find such a functional, we could reconcile the second law of thermodynamics with dynamics! We call $M$ the microscopic "entropy superoperator." It is immediately obvious that not all dynamical systems admit a nontrivial entropy superoperator ($M \ne \text{unit operator}$). As shown in Section 2, a necessary condition is that the spectrum of $L$ is continuous. Even then, the existence of $M$ implies properties such as Poincaré's nonintegrability (1, 3–5). Notice that if $M$ exists, it is not unique. However, all possible operators $M$ share common properties that will be studied elsewhere.

Because $M$ is a positive superoperator, it can be factored as the product of a superoperator $\Lambda^{-1}$ and its hermitian conjugate:

$$M = (\Lambda^{-1})^+ \Lambda^{-1} \tag{1.5}$$

Eq. **[1.3]** then takes the simple universal form:

$$\Omega = \operatorname{Tr} \tilde{\rho}^+ \tilde{\rho} \quad \text{with} \quad \tilde{\rho} = \Lambda^{-1}\rho \tag{1.6}$$

Notice that $\Lambda^{-1}$ is necessarily a nonunitary transformation; otherwise, $M$ would reduce to the unit operator and **[1.4]** could not be satisfied. In the $\tilde{\rho}$ representation, if the inverse transformation $\Lambda$ exists, the equation of motion **[1.1]** becomes:

$$i\frac{\partial \tilde{\rho}}{\partial t} = \Phi \tilde{\rho} \tag{1.7}$$

with

$$\Phi = \Lambda^{-1} L \Lambda \tag{1.8}$$

We shall see in Section 2 that **[1.7]** describes a contractive semi-group (for $t > 0$ or $t < 0$ according to the choice of $\Lambda$).

In this way we incorporate both Poincaré's and Gibbs–Einstein's points of view! In accordance with Poincaré's views (6), we perform a change of representation, here in the space of density matrices (or distribution functions), which is the natural space used in the Gibbs–Einstein ensemble description of classical and quantum mechanics.

Because $\Lambda$ is nonunitary, the new representation $\tilde{\rho}$ is not equivalent to the original representation $\rho$. The dynamical group **[1.1]** is transformed into a contractive semi-group **[1.7]** (at least in a restricted subspace of functions $\rho$). The equivalence between the dynamic group and the semi-group description can therefore only be valid on a subset of the states (see Sections 3 and 4).

In this paper, we shall first briefly formulate the general requirements on the Liapounov function **[1.3]**, then illustrate the method by using a simple example taken from quantum field theory—the Friedrichs model in second quantization. Finally, in Section 4, we comment on the conceptual significance of this new formulation of the second law of thermodynamics.

---

## 2. General Requirements on the Liapounov Function

Using the formal solution of **[1.1]**, $\rho(t) = e^{-iLt}\rho(0)$, we write **[1.3]** and **[1.4]** in the form:

$$\Omega(t) = \operatorname{Tr}\left[\rho^+(0) e^{iLt} M e^{-iLt} \rho(0)\right] > 0 \tag{2.1}$$

and

$$\frac{d\Omega}{dt} = -\operatorname{Tr}\left[\rho^+(0) e^{iLt} i(ML - LM) e^{-iLt} \rho(0)\right] \le 0 \tag{2.2}$$

It is immediately apparent that $M$ cannot commute with $L$; $M$ is not a constant of the motion. If $L$ has a discrete spectrum (as in the case of a system enclosed in a finite volume), the operators $L$ and $M$ can be simultaneously diagonalized in the representation in which $L$ is diagonal, and **[2.2]** cannot be satisfied. A continuous spectrum is therefore a necessary condition for the existence of a nontrivial $M$.

Let us define the superoperator $D$:

$$D \equiv i(ML - LM) \ge 0 \tag{2.3}$$

which represents the microscopic **entropy production**.

Using **[1.6]** and **[1.8]**, we may write **[2.2]** in the $\tilde{\rho}$ representation as:

$$\frac{d\Omega}{dt} = -\operatorname{Tr}\left[\tilde{\rho}^+(0) e^{i\Phi^+ t} i(\Phi - \Phi^+) e^{-i\Phi t} \tilde{\rho}(0)\right] \le 0 \tag{2.4}$$

Therefore, $\Phi$ cannot be hermitian and must satisfy the inequality:

$$i(\Phi - \Phi^+) \ge 0 \tag{2.5}$$

Let us consider an observable $A$. Its average value $\langle A \rangle$ should be independent of the representation used, provided that $\rho$ and $A$ belong to the domain of $\Lambda^{-1}$ and $\Lambda$ (see Section 3):

$$\langle A \rangle = \operatorname{Tr} A^+ \rho = \operatorname{Tr} \tilde{A}^+ \tilde{\rho} \tag{2.6}$$

Using **[1.6]**, we obtain:

$$A = (\Lambda^{-1})^+ \tilde{A} \tag{2.7}$$

Next, we consider the time evolution of $A$ in the Heisenberg-like representation:

$$i\frac{dA}{dt} = -LA \tag{2.8}$$

Comparing **[2.8]** with **[1.1]**, we see that $L$ has been replaced by $-L$. This is in fact the origin of the $L$-$t$ symmetry that is present in classical and quantum mechanics: if we change $t \to -t$ and $L \to -L$, the equations **[1.1]** and **[2.8]** remain invariant.

In contrast, phenomenological equations that describe irreversible processes break this $L$-$t$ symmetry.[^1] To introduce $L$-$t$ symmetry breaking, we require that the change of representation defined by $\Lambda(L)$ when acting on $\rho$ corresponds to $\Lambda(-L)$ when acting on $A$. Therefore, from **[2.7]** we have:

$$\left(\Lambda^{-1}(L)\right)^+ = \Lambda(-L) \tag{2.9}$$

or

$$\Lambda(L)\Lambda^+(-L) = 1 \tag{2.10}$$

This is a very important relation; it is a natural extension of the concept of unitarity, which we call **starunitarity** (3–5). Using the notation:

$$\Lambda^* \equiv \Lambda^+(-L) \tag{2.11}$$

Eq. **[1.8]** takes the form $\Phi = \Lambda^* L \Lambda$. It is immediately verified that $i\Phi$ is **starhermitian**, i.e.,

$$(i\Phi)^* \equiv \left[i\Phi(-L)\right]^+ = i\Phi \tag{2.12}$$

This allows us to decompose $i\Phi$ into two parts, one even (superscript $e$) and the other odd (superscript $o$) with respect to $L$-inversion ($L \to -L$):

$$i\Phi = (i\Phi)^e + (i\Phi)^o \tag{2.13}$$

Because of **[2.12]**, $(i\Phi)^e$ is hermitian and $(i\Phi)^o$ is antihermitian. Furthermore, **[2.5]** implies:

$$(i\Phi)^e \ge 0 \tag{2.14}$$

Equation **[1.7]** therefore becomes:

$$\frac{\partial \tilde{\rho}}{\partial t} = -\left[(i\Phi)^o + (i\Phi)^e\right]\tilde{\rho} \tag{2.15}$$

The evolution operator splits into two parts: a reversible part $(i\Phi)^o$ (which changes sign when $L \to -L$) and an irreversible part $(i\Phi)^e$ (which remains invariant when $L \to -L$).

It is very interesting to verify these properties on a concrete example, the Friedrichs model, which is well known for its simplicity and has already been studied in this context in a previous paper (7).

---

## 3. Example: The Friedrichs Model

We consider the Friedrichs model in second quantization (8). The Hamiltonian is:

$$H = \omega_1 a_1^+ a_1 + \sum_k \omega_k a_k^+ a_k + \lambda \sum_k \left(V_k a_1^+ a_k + V_k^{\mathrm{cc}} a_k^+ a_1\right) \tag{3.1}$$

This Hamiltonian describes a discrete state coupled to a field. In the infinite-volume limit ($L^3 \to \infty$), $\omega_k$ corresponds to a continuous spectrum ranging from $0$ to $\infty$, and $\omega_1 > 0$ is embedded in the continuum. We assume that there is no bound state. The density matrix $\rho$ has matrix elements $\rho_{11}$, $\rho_{1k}$, $\rho_{kk}$, and $\rho_{kk'}$ (the index $1$ refers to the discrete state, and $k$ to the continuum). Let us note the volume dependence of the matrix elements of $\rho$ and of an observable $A$: $\rho_{11}$, $A_{11}$, and $A_{kk}$ are $O(1)$; $\rho_{1k}$ and $A_{1k}$ are $O(L^{-3/2})$; and $\rho_{kk}$, $\rho_{kk'}$, and $A_{kk'}$ are $O(L^{-3})$ (9).

We define the Green's function of particle $1$ as:

$$\left(\frac{1}{z - H}\right)_{11} \equiv \frac{1}{\eta(z)} \tag{3.2}$$

with

$$\eta(z) = z - \omega_1 - \sum_k \frac{|V_k|^2}{z - \omega_k} \tag{3.3}$$

In the infinite-volume limit, the functions $\eta^+(z)^{-1}$ and $\eta^-(z)^{-1}$, which are defined as the analytic continuations of $\eta(z)^{-1}$ across the positive real axis from the upper and lower half-planes, respectively, have simple poles at $\omega_1 + \zeta$ and $\omega_1 + \zeta^{\mathrm{cc}}$ with residues $\mathcal{A}_1$ and $\mathcal{A}_1^{\mathrm{cc}}$ (9).

We shall not go into the details of the calculations here; they will be published elsewhere (M. de Haan, C. George, and F. Mayné, unpublished data). In a previous paper (7), the transformation $\Lambda$ was constructed for the Friedrichs model in first quantization. For our present purposes we must go to second quantization, because the observables $A$ have diagonal elements $A_{kk}$ of order $O(1)$ that do not vanish in the infinite-volume limit (in contrast to first quantization). In the infinite-volume limit, both $\rho$ and $A$ are functions of the continuous variables $\omega_k$ (for example, $\rho_{1k}$ becomes $\rho_1(k)$).

Let us summarize the main results:
1. It is possible to construct a starunitary transformation $\Lambda$ satisfying **[2.10]** and the dissipativity condition **[2.5]**. Note that $\Lambda$ depends explicitly on the Green's function $\eta(z)$ and its analytic continuations.
2. In the $\tilde{\rho}$ representation, the evolution operator $\Phi$ yields a contractive semi-group for $t > 0$. Each element of $\tilde{\rho}(t)$ that contributes to $\Omega(t)$ decreases exponentially in time according to:

$$e^{(ia + b)t} \quad (a, b \text{ real}, \; b \le 0) \tag{3.4}$$

3. The construction of $\tilde{\rho}$ and $\tilde{A}$ in the infinite-volume limit involves integrals of the Cauchy type, such as:

$$\int_0^\infty \frac{V(k)\rho_1(k)}{z + \omega_1 - \omega_k} \, dk \tag{3.5}$$

evaluated for $\operatorname{Im} z > 0$ and analytically continued into the lower half-plane. This implies that the functions $\rho_1(k)$, $\rho(k, k')$, $A_1(k)$, and $A(k, k')$ must satisfy certain smoothness and analyticity conditions (such as Cauchy integrality). In other words, the transformation $\Lambda^{-1}$ and $\Lambda$ are defined only on a **restricted class of states $\rho(0)$ and observables $A$**. This restriction is essential: if we took a single classical trajectory (represented by a $\delta$-function in phase space), it would not belong to the domain of $\Lambda^{-1}$, and no irreversible behavior could be derived for it! Irreversibility appears only for a class of distributions (or density matrices) that are sufficiently smooth.

4. Let us now evaluate the Liapounov function **[1.6]** for the Friedrichs model. In terms of the matrix elements of $\tilde{\rho}(t)$, we have:

$$\Omega(t) = \tilde{\rho}_{11}(t)^2 + 2\sum_k |\tilde{\rho}_{k1}(t)|^2 + \sum_{kk'} |\tilde{\rho}_{kk'}(t)|^2 \tag{3.6}$$

Using the exact time evolution of $\tilde{\rho}(t)$ given by **[1.7]**, one finds:

$$\Omega(t) = e^{-2i(\zeta - \zeta^{\mathrm{cc}})t} u_1 + 2e^{-i(\zeta - \zeta^{\mathrm{cc}})t} u_2 + u_3 \tag{3.7}$$

where $u_1, u_2, u_3$ are positive quantities determined by the initial state $\rho(0)$ (note that $\operatorname{Im} \zeta < 0$, so $-i(\zeta - \zeta^{\mathrm{cc}}) < 0$).

For example, if at $t = 0$ the system is in the pure "bare" particle state ($\rho_{11}(0) = 1$, all other elements zero), we obtain:

$$u_1 = \mathcal{A}_1 \mathcal{A}_1^{\mathrm{cc}} \tag{3.8}$$

$$u_2 = \left(\mathcal{A}_1 \mathcal{A}_1^{\mathrm{cc}}\right)^{1/2} \tag{3.9}$$

$$u_3 = 1 \tag{3.10}$$

Substituting **[3.8]–[3.10]** into **[3.7]** gives:

$$\Omega(t) = \left(|\mathcal{A}_1| e^{-\gamma t} + 1\right)^2 \tag{3.11}$$

where $\gamma = i(\zeta - \zeta^{\mathrm{cc}}) > 0$ is the inverse lifetime of the unstable particle ($\tau = \gamma^{-1}$). Thus, $\Omega(t)$ decreases monotonically from $(|\mathcal{A}_1| + 1)^2$ at $t = 0$ to its equilibrium value $1$ as $t \to \infty$!

5. Notice that while $\Omega(t)$ decays purely exponentially in the Friedrichs model, the average value $\langle A \rangle = \operatorname{Tr} \tilde{A}^+ \tilde{\rho}(t)$ contains terms of the form $\sum_k \tilde{\rho}_{1k}(t)\tilde{A}_{k1}$, which in the infinite-volume limit become integrals of the type:

$$\int_0^\infty e^{-i(\omega_1 + \zeta - \omega_k)t} f(k) \, dk \tag{3.12}$$

For large $t$, the asymptotic behavior of such integrals is determined by the behavior of the integrand near $k = 0$ (the threshold of the continuous spectrum). This leads to **nonexponential decay** (for instance, power-law tails) at very long times, in complete agreement with the known deviations from exponential decay in quantum mechanics (10) and with hydrodynamic long tails when the damping depends on the wave number $k$ (e.g., $\gamma_k \propto k^2$).

6. Finally, let us examine the matrix element $M_{11,11}$ of the entropy superoperator $M = (\Lambda^{-1})^+ \Lambda^{-1}$:

$$M_{11,11} = |\mathcal{A}_1|^2 + 2|\mathcal{A}_1| + 1 = \left(|\mathcal{A}_1| + 1\right)^2 \tag{3.13}$$

It is remarkable that in the weak coupling limit ($\lambda \to 0$), $|\mathcal{A}_1| \to 1$, so $M_{11,11} \to 4$. On the other hand, if we were to expand $\Lambda^{-1}$ in powers of $\lambda$ and compute $(\Lambda^{-1})^+ \Lambda^{-1}$ term by term, the zeroth-order term would be $1$, while higher-order terms would diverge! This shows clearly that $M$ and $\Lambda^{-1}$ cannot be obtained by naive perturbation theory; a partial resummation (analytic continuation) is essential to capture the irreversible behavior.

Furthermore, the inverse lifetime $\gamma$ is directly related to the commutator of $L$ and $M$:

$$\left[(i\Phi)^e\right]_{11,11} = \gamma = \Lambda^+_{11,\dots} [LM - ML]_{\dots, 11} \tag{3.14}$$

(where the dots denote summation over intermediate indices). Thus, the lifetime of an unstable particle has a direct thermodynamic interpretation in terms of microscopic entropy production!

---

## 4. Duality of Dynamic Description

Let us conclude with a few general remarks on the conceptual significance of this approach.

First, in our formulation, there is no need to make a sharp distinction between pure states and mixtures in the $\tilde{\rho}$ representation. In quantum mechanics, a pure state is characterized by the idempotency condition $\rho^2 = \rho$. Because $\Lambda$ is a nonunitary superoperator that does not factorize into the product of two operators acting separately on the left and right of $\rho$ (i.e., $\Lambda \rho \ne U \rho U^+$), the condition $\rho^2 = \rho$ is not preserved by $\Lambda^{-1}$: even if $\rho(0)$ is a pure state, $\tilde{\rho}(t)$ does not satisfy $\tilde{\rho}^2 = \tilde{\rho}$. Of course, if we transform back from $\tilde{\rho}(t)$ to $\rho(t) = \Lambda \tilde{\rho}(t)$ at any finite time $t > 0$, we recover the exact Schrödinger (or Liouville) evolution, which preserves pure states ($\rho(t)^2 = \rho(t)$). However, in the $\tilde{\rho}$ representation, both pure states and mixtures evolve toward the same asymptotic equilibrium state $\tilde{\rho}_{\mathrm{st}}$ (which satisfies $\Phi \tilde{\rho}_{\mathrm{st}} = 0$) that acts as an attractor.

Second, traditional kinetic equations (such as the Boltzmann equation or Pauli master equation) deal only with the diagonal elements of the density matrix in some unperturbed representation and neglect off-diagonal elements (correlations). In our theory, the superoperator $\Lambda^{-1}$ mixes diagonal and off-diagonal elements of $\rho$: even if $\rho(0)$ is diagonal, $\tilde{\rho}(0) = \Lambda^{-1}\rho(0)$ contains off-diagonal components, and vice versa. This mixing is essential for describing the dynamical correlations that give rise to nonexponential behavior and long tails.

Third, the transition from the reversible group **[1.1]** to the contractive semi-group **[1.7]** involves a restriction on the class of admissible states and observables (as we saw in Section 3 with the Cauchy analyticity conditions). Just as macroscopic dissipative equations (such as the diffusion or Fourier heat equation) "forget" initial conditions as time progresses, the semi-group **[1.7]** describes the forgetting of initial conditions at the microscopic level within the appropriate domain of states and observables.

In summary, the second law of thermodynamics appears here not as an approximation or an ad hoc addition to mechanics, but as an exact dynamical property—a **duality of dynamic description**—that emerges when we pass via a starunitary transformation from the unitary group of reversible mechanics to the contractive semi-group of irreversible thermodynamics.

---

### Footnotes

[^1]: For example, in the one-particle phenomenological equation $\frac{\partial f}{\partial t} + v\frac{\partial f}{\partial x} = -\frac{f - f^0}{\tau}$ ($\tau > 0$), if we invert $t \to -t$ and $v \to -v$, the left-hand side changes sign while the right-hand side does not.

---

### References

1. Prigogine, I. (1962) *Non-Equilibrium Statistical Mechanics* (Wiley-Interscience, New York).
2. Résibois, P. & De Leener, M. (1977) *Classical Kinetic Theory of Fluids* (Wiley-Interscience, New York).
3. Prigogine, I., George, C., Henin, F. & Rosenfeld, L. (1973) *Chem. Scr.* **4**, 5–32.
4. George, C., Prigogine, I. & Rosenfeld, L. (1972) *K. Dan. Vidensk. Selsk. Mat.-Fys. Medd.* **38**, no. 12, 1–44.
5. Prigogine, I. & Grecos, A. P. (1977) in *75 Jahre Quantentheorie* (Akademie-Verlag, Berlin), in press.
6. Poincaré, H. (1892) *Les Méthodes Nouvelles de la Mécanique Céleste* (Gauthier-Villars, Paris), Vol. 1.
7. Grecos, A. P. & Prigogine, I. (1972) *Physica* **59**, 77–96.
8. Friedrichs, K. O. (1948) *Commun. Pure Appl. Math.* **1**, 361–406.
9. Grecos, A., Guo, T. & Guo, W. (1975) *Physica* **80A**, 421–446.
10. Khalfin, L. A. (1958) *Sov. Phys. JETP* **6**, 1053–1063.