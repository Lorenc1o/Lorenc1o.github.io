---
layout: post
title:  "Willmore Surfaces"
date:   2023-05-15
categories: Mathematics
usemathjax: true
toc:
    -
        title: Introduction
        url: '#introduction'
    -
        title: History
        url: '#history'
    -
        title: The Willmore functional
        url: '#the-willmore-functional'
    -
        title: The Willmore conjecture
        url: '#the-willmore-conjecture'
    -
        title: Conformal invariance
        url: '#conformal-invariance'
    -
        title: First variation formula
        url: '#first-variation'
    -
        title: References
        url: '#references'
lang: en
---
# Willmore Surfaces

## Introduction {#introduction}

I did my Mathematics Bachelor Thesis about Willmore Surfaces. I will try to explain the main ideas of the thesis in this post.

Firstly, we will see a bit of history of these surfaces. Secondly, I will explain what the Willmore functional, \\(W\\), is. Then, I will visit some of the most important results about Willmore surfaces. Finally, I will explain the main results of my thesis, which are the invariance of the Willmore functional under conformal transformations of the space and the derivation of the first variation of the Willmore functional, using basic tools of differential geometry in the three-dimensional Euclidean space, \\(\\mathbb{R}^3\\).

If you are interested in the topic, you can read the [full thesis](https://github.com/Lorenc1o/Math_Info_UniversityNotes/blob/main/Mathematics/TFG/TFG_WillmoreSurfaces.pdf), its accompanying [presentation](https://github.com/Lorenc1o/Math_Info_UniversityNotes/blob/main/Mathematics/TFG/Presentacion_TFG_Willmore.pdf) or [poster](https://github.com/Lorenc1o/Math_Info_UniversityNotes/blob/main/Mathematics/TFG/Poster_willmore_v2.pdf). Note that they are in Spanish.

## History {#history}

Willmore surfaces have been a subject of significant interest since their inception in 1965 when Willmore published his influential article Note on embedded surfaces [^1]. He defined a functional, later named after him, given by \\[\\tau(S)=\\frac{1}{2\\pi}\\int_{S}H^2dS\\], where \\(S\\) is a closed orientable regular surface of Euclidean space and \\(dS\\) its area element, with \\(H\\) denoting the mean curvature of \\(S\\). Willmore aimed to find the relationship between this functional and the Euler characteristic, \\(\\mathcal X(S)\\), hoping to discover a relation akin to the Gauss-Bonnet theorem. Although such a relation was not established, Willmore managed to extract properties of \(\\tau(S)\) knowing the value of \\(\\mathcal X(S)\\). For example, he proved that for a sphere of radius \\(r>0\\), \\[\\tau(\\mathbb{S}^2(r))=2\\], which is the infimum (and minimum) of \\(\\tau\\) for all possible surfaces \\(S\\) with \\(\\mathcal{X}(\\mathcal{S})=2\\).

The functional was later generally defined as \\[W(S) = \\int_{S}H^2dS\\], effectively multiplying Willmore's original functional by \\(2\\pi\\). The study of both functionals is equivalent when it comes to finding surfaces that minimize them. Another alternative definition is \\[W(S) = \\int_{S}(H^2-K)dS\\], where \\(K\\) is the Gaussian curvature of the surface at each point. This functional is also equivalent to the previous ones, as the Gauss-Bonnet theorem means that only a constant term is being added. After finding the absolute minimum of \\(W\\), Willmore attempted to reach a similar result for surfaces with Euler characteristic \\(\\mathcal{X}(S)=0\\), such as surfaces that are homeomorphic to a torus. While he didn't achieve this, he characterized the minimum of \\(\\tau\\) among all tori of revolution, leading to what became known as the Willmore conjecture. This conjecture was eventually proven by Marques and Neves in 2014, almost 50 years after it was first stated [^2].

## The Willmore functional {#the-willmore-functional}

The <span style="color:red">Willmore functional</span> of a orientable, compact and regular surface, \\(S\\), is defined as:
\\[\\int_S H^2 dS,\\]
where \\(H\\) is the mean curvature of \\(S\\) and \\(dS\\) is the area element of \\(S\\).

Then, we define a <span style="color:red">Willmore surface</span> as a surface that is a critical point of the Willmore functional.

The first interesting result that we can get is the following Theorem:

**Theorem 1.** If \\(S\\) is an orientable, compact and regular surface, then
\\[W(S)\\geq4\\pi,\\]
with equality if and only if \\(S\\) is a sphere.

We can outline[^3] the proof of this theorem as follows:

<span style="color:grey">
First, 
\\[W(S)=\\int_S H^2 dS\\geq\\int_{S^+} H^2 dS,\\]
where \\(S^+\\) is the part of \\(S\\) where \\(K\\) is positive.
</span>
<span style="color:grey">
Then, it is well known that
\\[H^2-K=\\frac{(k_1-k_2)^2}{4}\\geq0,\\]
where \\(k_1\\) and \\(k_2\\) are the principal curvatures of \\(S\\). This implies that \\(H^2\\geq K\\).
</span>
<span style="color:grey">
Now, we can combine the two previous inequalities to get
\\[W(S)\\geq\\int_{S^+} K dS=\\text{area}(N(S^+)),\\]
where \\(N(\\cdot)\\) is the Gauss map of \\(S\\). Since \\(S\\) is compact, it can be proven that \\(N(S^+)\\) is a surjective.
</span>
<span style="color:grey">
Therefore
\\[W(S)\\geq\\text{area}(N(S^+))\\geq\\text{area}(\\mathbb{S}^2)=4\\pi.\\]
The equality holds if and only if \\(H^2=K\\), which implies that \\(k_1=k_2\\), i.e. \\(S\\) is a sphere, since it is the only surface with constant principal curvatures that is compact.
</span>

Since Willmore was interested in the relationship between the Euler characteristic and the Willmore functional, he explored the behavior of the functional with different families of surfaces. For instance, it can be proven that, for the torus of revolution with inner radius \\(r\\) and outer radius \\(R\\), the Willmore functional is given by
\\[W(\\mathbb{T}(r,R))=\\frac{\\pi^2}{a\sqrt{1-a^2}},\\]
where \\(a=\\frac{r}{R}\\). This implies that the minimum of the functional is \\(2\\pi^2\\) and it is achieved when \\(a=\\frac{1}{\\sqrt{2}}\\), i.e. when \\(R=\\sqrt{2}\cdot r\\).

<img src="/assets/images/willmore/torus.png" alt="A torus of revolution." width="200" class="centered-image">

## The Willmore conjecture {#the-willmore-conjecture}

After finding the minimum of the Willmore functional among all tori of revolution, Willmore also studied a more general family of tori: the <span style="color:red">generalized tori</span>. There are surfaces that are obtained by taking a tube around a closed curve in \\(\\mathbb{R}^3\\). The generalized tori are the surfaces that are homeomorphic to a torus. 

<img src="/assets/images/willmore/generalized-torus.png" alt="A generalized torus." width="200" class="centered-image">

He found out that the Willmore functional of any generalized torus is at least \\(2\\pi^2\\). This led him to conjecture that the minimum of the Willmore functional among all surfaces with Euler characteristic \\(\\mathcal{X}(S)=0\\) is \\(2\\pi^2\\). This is known as the Willmore conjecture:

**Willmore conjecture (1965).** If \\(S\\) is an orientable, compact and regular surface with Euler characteristic \\(\\mathcal{X}(S)=0\\) (equivalently, its genus is \\(g(S)=1\\)), then 
\\[W(S)\\geq2\\pi^2,\\]
with equality if and only if \\(S\\) is a torus of revolution with inner radius \\(r\\) and outer radius \\(R=\\sqrt{2}\\cdot r\\).

The proof of this result evaded mathematicians until 2014, when Marques and Neves proved it[^2] using advanced techniques from geometric measure theory.

## The conformal invariance of the Willmore functional {#conformal-invariance}

Let \\(W_1,W_2\\) be open and connected sets in the Euclidean space. Then, a <span style="color:red">conformal transformation</span> is a function \\(\\Phi:W_1\\to W_2\\) if, for all \\(p\\in W_1\\), \\(d\\Phi_p\\) is a linear conformal map. More concretely, this means that exists a differentiable function \\(\\lambda:W_1\\to\\mathbb{R}\setminus\\{0\\}\\) such that
\\[\\left\\langle d\\Phi_p(v),d\\Phi_p(w)\\right\\rangle=\\lambda(p)^2\\left\\langle v,w\\right\\rangle,\\]
for all \\(v,w\\in\\mathbb{R}^3\\) and \\(p\\in W_1\\). The function \\(\\lambda\\) is called the <span style="color:red">conformal factor</span> of \\(\\Phi\\).

It can be proven that this definition is equivalent to say that a conformal transformation is a function that preserves angles between curves.

The Liouville theorem[^4] states that every injective conformal transformation between two open and connected sets in \\(\\mathbb{R}^3\\) is a composition of rigid motions, inversions and homotheties.

Using this fact and some differential geometry, we proved[^3] the following theorem:

**Theorem 2.** Let \\(S\\) be an orientable, compact and regular surface and \\(\\Phi:S\\to\\mathbb{R}^3\\) a conformal and injective transformation. Then \\S'=\Phi(S)\\ is also an orientable, compact and regular surface and the Willmore functional is invariant under conformal transformations, i.e. \\(W(S)=W(S')\\).

## The first variation of the Willmore functional {#first-variation}

In the final chapter, we studied the first variation of the Willmore functional. Variational methods are a powerful tool in geometry, since they allow us to find critical points of a functional by studying the behavior of the functional when the surface is slightly perturbed.

After lots (really lots!) of computations, we derived the following formula for the first variation of the Willmore functional:
\\[w'(0)=\int_R\varphi(\\Delta H+2H(H^2-2K))dS,\\]
where \\(\\varphi\\) is the scaling function of the normal variation of the surface and \\(R\\) is the region enclosed by the surface in which the variation is defined with compact support, i.e. \\(\\varphi=0\\) outside \\(R\\). Also, \\(H\\) and \\(K\\) are the mean and Gaussian curvatures of the surface, respectively, and \\(\\Delta\\) is the Laplacian operator. Finally, \\(w(t)\\) is the Willmore functional of the surface \\(S_t\\) obtained by perturbing the surface \\(S\\) in the direction of the normal vector field \\(\\nu\\) with scaling function \\(\\varphi\\), i.e. \\(S_t=S+t\\varphi\\nu\\).

If the previous paragraph is a bit obscure to you, don't worry! The important thing is that we derived a formula that every critical point of the Willmore functional must satisfy. With this formula, we were able to derive the Euler-Lagrange equation of the Willmore functional, which is a partial differential equation that every critical point of the Willmore functional must satisfy:

**Theorem 3.** Let \\(S\\) be a regular surface. Then, \\(S\\) is a critical point of the Willmore functional if and only if it satisfies the following partial differential equation:
\\[\\Delta H+2H(H^2-2K)=0.\\]

Note that we removed the adjective 'compact' from the previous theorem. This is because this theorem allows us to redefine the concept of Willmore Surface to the whole space of regular surfaces, not only compact ones. This is a very important result, since it allows us to study the Willmore functional in a more general setting.

For instance, we proved the three following results:

**Theorem 4.** Totally umbilical surfaces are Willmore surfaces.

<span style="color:grey">
Totally umbilical surfaces verify \\(H^2-K=0\\), so the right part of the equation is zero. The \\(\\Delta H\\) term is also zero, since \\(H\\) is constant. Therefore, the equation is satisfied.
</span>

**Corollary** Planes are Willmore surfaces under the new definition, but not under the old one, since they are not compact.

**Theorem 5.** Pieces of sphere are the only Willmore surfaces with constant non-zero mean curvature.

<span style="color:grey">
Suppose \\(S\\) is a Willmore surface with \\(H\\neq0\\), then \\(\Delta H = 0\\) and the equation becomes \\(H(H^2-2K)=0\\). Since \\(H\\neq0\\), we have that \\(H^2-2K=0\\), so \\(S\\) is totally umbilical. Therefore, \\(S\\) is a piece of sphere since \\(H\\neq0\\).


## References {#references}

[^1]: T. J. Willmore, Note on embedded surfaces, An. St. Univ. Iasi 11 (1965), 493-496.
[^2]: F. C. Marques and A. Neves, Min-max theory and the Willmore conjecture, Ann. of Math. (2) 179 (2014), no. 2, 683-782. [arXiv](https://arxiv.org/abs/1202.6036)
[^3]: For more details, you can see my [thesis](https://github.com/Lorenc1o/Math_Info_UniversityNotes/blob/main/Mathematics/TFG/TFG_WillmoreSurfaces.pdf).
[^4]: Mirjam Soeten. Conformal maps and the theorem of Liouville. Bachelor's Thesis, Rijksuniversiteit Groningen, 2013. [link](https://fse.studenttheses.ub.rug.nl/9888/1/Scriptiegoed.pdf)