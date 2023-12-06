---
layout: post
title: "Linear Algebra Foundation"
date: 2023-12-06 01:29
category: Math Foundations
---


To find the gradient $\nabla f(x)$ of the function $f(x) = \frac{1}{2}x^T A x + b^T x$, we can apply the rules of matrix calculus. The function $f(x)$ is a quadratic form plus a linear term.

Given that $A$ is symmetric, we can use the following rules of matrix calculus for a vector $x$ and symmetric matrix $A$:

1. The derivative of $x^T A x$ with respect to $x$ is $Ax + A^T x$, but since $A$ is symmetric, $A = A^T$, so this simplifies to $2Ax$.
2. The derivative of $b^T x$ with respect to $x$ is $b$.

So, applying these rules to our function $f(x)$:

$$
\nabla f(x) = \nabla \left(\frac{1}{2}x^T A x\right) + \nabla (b^T x) \\
            = \frac{1}{2} (2Ax) + b \\
            = Ax + b
$$

Therefore, the gradient $\nabla f(x)$ is $Ax + b$.

Now, if you're looking to compute the Hessian $\nabla^2 f(x)$ of $f(x)$, which is the matrix of second-order partial derivatives, it becomes even simpler in this case. Since the first term is a quadratic form and the second is a linear term, the second derivative of the linear term with respect to $x$ is zero, and the second derivative of the quadratic form $\frac{1}{2}x^T A x$ with respect to $x$ is just the matrix $A$ itself because the derivative of $Ax$ with respect to $x$ is $A$.

So, the Hessian $\nabla^2 f(x)$ is simply $A$.
