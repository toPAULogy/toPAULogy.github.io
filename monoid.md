---
layout: default
title: Monoidal structures in locally covariant QFT
---
### 1 &emsp; Monoidal structures in locally covariant QFT

Monoidal categories and functors are ubiquitous in physics as it formalises the notion of systems and processes. It is notably used in many formalisms of quantum field theory, such as functorial field theory and factorisation algebras. I will discuss them in the context of locally covariant quantum field theory as in [Rejzner (2016)](https://link.springer.com/book/10.1007/978-3-319-25901-7).. For the sake of brevity, I will only define *strict* monoidal categories and functors, even though the examples I will work through later are not strict. 

**Definition 1.1** (Strict monoidal category). A strict monoidal category is a category equipped with 

- an associative bifunctor 

$$\square : B\times B\rightarrow B,$$

- and a left and right unit of the bifunctor $e$

$$e\square x = x = x\square e \quad \forall x\in\operatorname{Obj}(B).$$

**A strict monoidal category generalises the notion of a tensor product on vector spaces. In the same way that the tensor product takes in two vector spaces and outputs a third. $e$ corresponds to $\mathbb{K}$, the one dimensional vector space that acts as the unit element for $\mathbf{Vec}^\otimes$. In a non-strict monoidal category, the identities hold only up to isomorphism.** 

In algebraic quantum field theory algebras of observables are assigned to regions of Minkowski space. Locally covariant quantum field theory generalises this to globally hyperbolic spacetimes. 

**Definition 1.2** ($\mathbf{Loc}$). A category $\mathbf{Loc}$ has

- $\operatorname{Obj}(\mathbf{Loc})$: globally hyperbolic, oriented, time oriented spacetimes, $\mathcal{M}=(M,g)$,
- $\operatorname{Hom}(\mathbf{Loc})$: orientation, time orientation and causality preserving isometric embeddings, $\chi: \mathcal{M}\rightarrow \mathcal{N}$.

An embedding $\chi$ is causality preserving if for a causal curve, $\gamma: [a,b]\rightarrow \mathcal{N}$, if its endpoints are in $\chi(\mathcal{M})$, then the entire curve lies in $\chi(\mathcal{M})$. 

The composition of embeddings is associative and the composition of two isometries is an isometry so we need only check whether the composition of maps $\chi_1:\mathcal{M}\rightarrow \mathcal{N}$ and $\chi_2:\mathcal{N}\rightarrow \mathcal{O}$, $\chi = \chi_2\circ \chi_1: \mathcal{M}\rightarrow \mathcal{O}$, preserves causality to see if it will define a new morphism. 

We want to show that for a curve $\gamma: [a,b]\rightarrow \mathcal{O}$ with endpoints in $\chi_2\circ \chi_1 (\mathcal{M})$ the entire curve lies in $\chi_2\circ \chi_1 (\mathcal{M})$. As $\chi_2\in \operatorname{Hom}(\mathbf{Loc})$, we can define a new curve as the preimage of $\gamma(t)$ under $\chi_2$ 

$$\gamma^\prime=\chi_2^{-1}[\gamma]: [a,b]\rightarrow \mathcal{N}.$$

As the $\gamma(a),\gamma(b)\in\chi_2\circ \chi_1 (\mathcal{M})$, the endpoints of $\gamma^\prime$ are in $\chi_1 (\mathcal{M})$. Because $\chi_1\in \operatorname{Hom}(\mathbf{Loc})$, we must have $\gamma^\prime(t)\in \chi_1(\mathcal{M})$ for all $t\in (a,b)$. This implies that $\gamma(t)\in \chi_2\circ\chi_1(\mathcal{M})$ for all $t\in (a,b)$. So $\chi = \chi_2\circ\chi_1\in \operatorname{Hom}(\mathbf{Loc})$. 

We can extend $\mathbf{Loc}$ to a monoidal category $\mathbf{Loc}^\sqcup$ by taking the disjoint union as the monoidal product and the empty set as the unit element. The disjoint union is associative up to natural isomorphism

$$\mathcal{M}_1\sqcup (\mathcal{M}_2\sqcup \mathcal{M}_3)\cong( \mathcal{M}_1\sqcup \mathcal{M}_2)\sqcup \mathcal{M}_3\quad \forall \mathcal{M}_1, \mathcal{M}_2, \mathcal{M}_3\in \operatorname{Obj}(\mathbf{Loc}),$$

and the disjoint union of the null set provides a left and right unit up to isomorphism

$$\emptyset\sqcup \mathcal{M} \cong \mathcal{M} \cong \mathcal{M} \sqcup\emptyset.$$

**We require that for morphisms of $\mathbf{Loc}^\sqcup$, $\chi: \mathcal{M}_1\sqcup \cdots \sqcup \mathcal{M}_n\rightarrow \mathcal{M}$, the sub spacetimes $\chi(\mathcal{M}_i), \chi(\mathcal{M}_j)$ be causally disjoint for $i\neq j$, i.e., there exists no causal curve in $\mathcal{M}$ connecting the two sub regions.** 

Generally, the algebra of observables for a given region will be a $*$-algebra (potentially with extra structure). 

**Definition 1.3** ($\mathbf{Obs}$). The category of observables has

- $\operatorname{Obj}(\mathbf{Obs})$: unital $*$-algebras.
- $\operatorname{Hom}(\mathbf{Obs})$: unit preserving, injective $*$-homomorphisms.

These are algebra homomorphisms, $\varphi:\mathcal{A}\rightarrow \mathcal{B}$, with the additional properties

- $\varphi(\mathbb{1}_\mathcal{A}) = \mathbb{1}_\mathcal{B}$,
- $\varphi(A^*) = \varphi(A)^*$.

This is easily equipped with the familiar tensor product on vector spaces and its unit element is also the complex numbers. (This requires more care when dealing with $C^*$-algebras.)

The final notion we require is a functor between these categories, $\mathfrak{A}:\mathbf{Loc}\rightarrow \mathbf{Obs}$, that respects their monoidal structure. 

**Definition 1.4** (Strict monoidal functor). A functor between monoidal categories that respects their monoidal structures. For the functor $\mathfrak{A}$ defined above, this is the requirement that

- $$\mathfrak{A}(\mathcal{M}\sqcup \mathcal{M}^\prime)=\mathfrak{A}(\mathcal{M})\otimes\mathfrak{A}(\mathcal{M}^\prime),$$
- $$\mathfrak{A}_{\chi\sqcup\chi^\prime}=\mathfrak{A}_\chi \otimes \mathfrak{A}_{\chi^\prime},$$
- $$\mathfrak{A}(\emptyset)=\mathbb{C}.$$
This functor is a model of a locally covariant quantum field theory.

**To do**: create figures, fix sections in bold, add section on quantum fields in this model.