---
layout: default
title: Test
---
I'm going to discuss monoidal functors in relation to locally covariant quantum field theory. For the sake of brevity, I will only define strict monoidal categories and functors even though the examples I will work through later are not strict. I would be happy to discuss this after the presentation. 

A (strict) monoidal category generalises the notion of a tensor product on vector spaces. In the same way that the tensor product takes in two vector spaces and outputs a third, a monoidal category is a category equipped with 
- an associative bifunctor $$\square : B\times B\rightarrow B.$$
- a left and right unit $e$ of the bifunctor$$e\square x = x = x\square e \quad \forall x\in \operatorname{Obj}(B).$$
$e$ corresponds to $\mathbb{K}$, the one dimensional vector space that acts as the unit element for $\mathbf{Vec}^\otimes$. In a non-strict monoidal category, the identities hold only up to isomorphism. 

In algebraic quantum field theory one assigns algebras of observables to regions of Minkowski space. Locally covariant quantum field theory generalises this to globally hyperbolic spacetimes using monoidal categories. $\mathbf{Loc}$ is a category with
- $\operatorname{Obj}(\mathbf{Loc})$: globally hyperbolic, oriented, time oriented spacetimes, $\mathcal{M}=(M,g)$.
- $\operatorname{Hom}(\mathbf{Loc})$: Isometric, causality preserving embeddings, i.e., for an embedding, $\chi: \mathcal{M}\rightarrow \mathcal{N}$, if the endpoints of a causal curve, $\gamma$, lie in $\chi(\mathcal{M})$, then the entire curve lies in $\chi(\mathcal{M})$. 
Embeddings are associative and the composition of two isometries is an isometry. We need to check whether the composition of maps $\chi_1:\mathcal{M}\rightarrow \mathcal{N}$ and $\chi_2:\mathcal{N}\rightarrow \mathcal{O}$, $\chi = \chi_2\circ \chi_1: \mathcal{M}\rightarrow \mathcal{O}$, preserves causality to see if it will define a new morphism. 


As $\chi_2\in \operatorname{Hom}(\mathbf{Loc})$, we can define a new curve with the preimage of $\chi_2$, $\gamma^\prime=\chi_2^{-1}[\gamma]: [a,b]\rightarrow \mathcal{N}$. If the endpoints of $\gamma$ are in $\chi_2\circ \chi_1 (\mathcal{M})$ in $\mathcal{O}$, then the endpoints of $\gamma^\prime$ are in $\chi_1 (\mathcal{M})$. As $\chi_1\in \operatorname{Hom}(\mathbf{Loc})$, we must have $\gamma^\prime(t)\in \chi_1(\mathcal{M})$ for all $t\in ]a,b[$ implying that $\gamma(t)\in \chi_2\circ\chi_1(\mathcal{M})$ for all $t\in ]a,b[$. So $\chi = \chi_2\circ\chi_1\in \operatorname{Hom}(\mathbf{Loc})$.

We can extend $\mathbf{Loc}$ to a monoidal category $\mathbf{Loc}^\sqcup$ by taking the disjoint union as a bifunctor and the empty set as the unit element. The disjoint union is associative up to natural isomorphism$$\mathcal{M}_1\sqcup (\mathcal{M}_2\sqcup \mathcal{M}_3)\cong( \mathcal{M}_1\sqcup \mathcal{M}_2)\sqcup \mathcal{M}_3\quad \forall \mathcal{M}_1, \mathcal{M}_2, \mathcal{M}_3\in \operatorname{Obj}(\mathbf{Loc}),$$and the disjoint union of the null set provides a left and right unit up to isomorphism$$\emptyset\sqcup \mathcal{M} \cong \mathcal{M} \cong \mathcal{M} \sqcup\emptyset.$$We require that for morphisms of $\mathbf{Loc}^\sqcup$, $\chi: \mathcal{M}_1\sqcup \cdots \sqcup \mathcal{M}_n\rightarrow \mathcal{M}$, the sub spacetimes $\chi(\mathcal{M}_i), \chi(\mathcal{M}_j)$ be causally disjoint for $i\neq j$, i.e., there exists no causal curve in $\mathcal{M}$ connecting the two sub regions. 

Generally, the algebra of observables for a given region will be a $*$-algebra (potentially with extra structure). We define the category of observables $\mathbf{Obs}$ as
- $\operatorname{Obj}(\mathbf{Obs})$: unital $*$-algebras.
- $\operatorname{Hom}(\mathbf{Obs})$: unit preserving, injective $*$-homomorphisms. 
This is easily equipped with the familiar tensor product on vector spaces and its unit element is also the complex numbers.

The final notion we require to define our model is that of a (strict) monoidal functor. This is simply a functor between monoidal categories that respects their monoidal structures. For a locally covariant quantum field theory, $\mathfrak{A}:\mathbf{Loc}\rightarrow \mathbf{Obs}$, this is the requirement that$$\mathfrak{A}(\mathcal{M}\sqcup \mathcal{M}^\prime)=\mathfrak{A}(\mathcal{M})\otimes\mathfrak{A}(\mathcal{M}^\prime),$$$$\mathfrak{A}_{\chi\sqcup\chi^\prime}=\mathfrak{A}_\chi \otimes \mathfrak{A}_{\chi^\prime},$$$$\mathfrak{A}(\emptyset)=\mathbb{C}.$$

