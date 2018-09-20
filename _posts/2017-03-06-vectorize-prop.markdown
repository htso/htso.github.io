---
layout: default
title:  "Some interesting properties of vectorization"
date:   2017-03-06 12:34:08 -0700
categories: tensor
---

{% include post-title.html %}

In the previous post, I introduce a procedure that turns a matrix into a vector. It's just stacking the column to form a longer vector. Naturally, you'd ask what properties of the matrix are preserved in its "linear" incarnation. 

The first property that carries over to its vector form is its norm. It's totally intuitive but still worth stating.


> Proposition 1 : For any matrix $$M$$,
>
> $$
> \|M\|_{F} = \|v\|_2
> $$ 
>
> where $$v = vec(M)$$, the subscript $$F$$ stands for the Frobenius norm.


A direct corollary of this is the following statement, which is a little bit less intuitive, but still just a consequence of the Prop 1.

> Proposition 2 : If matrix M has rank 1, then
>
> $$
>  \|v\|_2 = \sigma_1, \lambda \in \gamma
> $$
>
> where $$\sigma_1$$ is the largest and the only non-zero singular value of $$M$$.

To understand this statement, I like to visualize it this way. In the vector space that $$v$$ lives in, which is a higher dimension space than the column space of $$M$$, there is a nice regularity there. No matter how the matrix is chosen, as long as it is rank-1, the vector must lie on the ball with a radius equal to the singular value of $$M$$.




