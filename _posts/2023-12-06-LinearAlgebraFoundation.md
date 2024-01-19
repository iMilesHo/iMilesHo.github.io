---
layout: post
title: Linear Algebra Foundation
date: 2023-12-06 11:10:10
description: About Linear Algebra Foundation
tags: Linear Algebra
categories: posts
giscus_comments: true
related_posts: true
---

## Gradients and Hessians

Recall that a matrix $ A \in \mathbb{R}^{n \times n} $ is _symmetric_ if $ A^T = A $, that is, $ A_{ij} = A_{ji} $ for all $ i, j $. Also recall the gradient $ \nabla f(x) $ of a function $ f : \mathbb{R}^n \rightarrow \mathbb{R} $, which is the n-vector of partial derivatives

$$
\nabla f(x) = 
\begin{bmatrix}
\frac{\partial}{\partial x_1} f(x) \\
\vdots \\
\frac{\partial}{\partial x_n} f(x)
\end{bmatrix}
$$

where $ x = $

$$
\begin{bmatrix}
x_1 \\
\vdots \\
x_n
\end{bmatrix}
$$

The hessian $ \nabla^2 f(x) $ of a function $ f : \mathbb{R}^n \rightarrow \mathbb{R} $ is the $ n \times n $ symmetric matrix of twice partial derivatives,

$$
\nabla^2 f(x) = 
\begin{bmatrix}
\frac{\partial^2}{\partial x_1^2} f(x) & \frac{\partial^2}{\partial x_1 \partial x_2} f(x) & \cdots & \frac{\partial^2}{\partial x_1 \partial x_n} f(x) \\
\frac{\partial^2}{\partial x_2 \partial x_1} f(x) & \frac{\partial^2}{\partial x_2^2} f(x) & \cdots & \frac{\partial^2}{\partial x_2 \partial x_n} f(x) \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\partial^2}{\partial x_n \partial x_1} f(x) & \frac{\partial^2}{\partial x_n \partial x_2} f(x) & \cdots & \frac{\partial^2}{\partial x_n^2} f(x) \\
\end{bmatrix}
$$

1. (a) Let $ f(x) = \frac{1}{2} x^T A x + b^T x $, where $ A $ is a symmetric matrix and $ b \in \mathbb{R}^n $ is a vector. What is $ \nabla f(x) $?

2. (b) Let $ f(x) = g(h(x)) $, where $ g : \mathbb{R} \rightarrow \mathbb{R} $ is differentiable and $ h : \mathbb{R}^n \rightarrow \mathbb{R} $ is differentiable. What is $ \nabla f(x) $?

3. (c) Let $ f(x) = \frac{1}{2} x^T A x + b^T x $, where $ A $ is symmetric and $ b \in \mathbb{R}^n $ is a vector. What is $ \nabla^2 f(x) $?

4. (d) Let $ f(x) = g(a^T x) $, where $ g : \mathbb{R} \rightarrow \mathbb{R} $ is continuously differentiable and $ a \in \mathbb{R}^n $ is a vector. What are $ \nabla f(x) $ and $ \nabla^2 f(x) $? (*Hint: your expression for $ \nabla^2 f(x) $ may have as few as 11 symbols, including ' and parentheses.*)


## Solutions

### Problem 1(a)

We want to find the gradient $ \nabla f(x) $ of the function $ f(x) = \frac{1}{2} x^T A x + b^T x $, where $ A $ is a symmetric matrix and $ b \in \mathbb{R}^n $ is a vector.

1. **Differentiate $ \frac{1}{2} x^T A x $**:

   The derivative of the quadratic form $ x^T A x $ with respect to $ x $ is $ Ax + A^T x $. Since $ A $ is symmetric ($ A = A^T $), this simplifies to $ 2Ax $. The coefficient $ \frac{1}{2} $ in front of $ x^T A x $ will cancel the 2 from the derivative, resulting in:

   $$
   \frac{\partial}{\partial x} \left(\frac{1}{2} x^T A x\right) = Ax
   $$

2. **Differentiate $ b^T x $**:

   The gradient of the linear form $ b^T x $ with respect to $ x $ is $ b $, because the derivative of each component $ b_i x_i $ with respect to $ x_i $ is just $ b_i $:

   $$
   \frac{\partial}{\partial x} (b^T x) = b
   $$

3. **Combine the results**:

   The gradient $ \nabla f(x) $ is the sum of the gradients of $ \frac{1}{2} x^T A x $ and $ b^T x $:

   $$
   \nabla f(x) = Ax + b
   $$

Thus, the gradient $ \nabla f(x) $ of the function $ f(x) $ is $ Ax + b $.

### Problem 1(b) Solution

Find the gradient $ \nabla f(x) $ of the function $ f(x) = g(h(x)) $, where $ g: \mathbb{R} \rightarrow \mathbb{R} $ is differentiable and $ h: \mathbb{R}^n \rightarrow \mathbb{R} $ is differentiable.

1. By the chain rule for gradients, the gradient of $ f $ with respect to $ x $ is the product of the derivative of $ g $ with respect to $ h(x) $ and the gradient of $ h $ with respect to $ x $:

   $$
   \nabla f(x) = g'(h(x)) \cdot \nabla h(x)
   $$

   where $ g'(h(x)) $ is a scalar and $ \nabla h(x) $ is a vector.

### Problem 1(c) Solution

Given $ f(x) = \frac{1}{2} x^T A x + b^T x $, where $ A $ is symmetric and $ b \in \mathbb{R}^n $ is a vector, find the Hessian $ \nabla^2 f(x) $.

1. We have already calculated $ \nabla f(x) = Ax + b $ in problem 1(a).
2. Now, to find the Hessian, we differentiate the gradient $ \nabla f(x) $ with respect to $ x $ again.
3. The derivative of $ Ax $ with respect to $ x $ is $ A $ since $ A $ is constant with respect to $ x $.
4. The derivative of $ b $ with respect to $ x $ is zero since $ b $ does not depend on $ x $.

   Combining these results, we get:

   $$
   \nabla^2 f(x) = A
   $$

### Problem 1(d) Solution

To solve problem 1(d), we need to find the gradient $ \nabla f(\mathbf{x}) $ and the Hessian $ \nabla^2 f(\mathbf{x}) $ of the function $ f(\mathbf{x}) = g(a^T \mathbf{x}) $, where $ g: \mathbb{R} \rightarrow \mathbb{R} $ is continuously differentiable and $ a \in \mathbb{R}^n $ is a vector.

#### Finding the Gradient $ \nabla f(\mathbf{x}) $:

The gradient of a scalar function is a vector of its first partial derivatives. Here, we use the chain rule:

1. **Apply the chain rule**:
   $ f(\mathbf{x}) = g(u) $ with $ u = a^T \mathbf{x} $. The derivative of $ f $ with respect to $ x_i $ is:
   $$
   \frac{\partial f}{\partial x_i} = \frac{\partial g}{\partial u} \cdot \frac{\partial u}{\partial x_i}
   $$
   where $ \frac{\partial u}{\partial x_i} = a_i $.

2. **Compute the gradient**:
   $$
   \nabla f(\mathbf{x}) = \left[ \begin{array}{c}
   \frac{\partial g}{\partial u} a_1 \\
   \vdots \\
   \frac{\partial g}{\partial u} a_n
   \end{array} \right]
   $$
   Factoring out $ \frac{\partial g}{\partial u} $:
   $$
   \nabla f(\mathbf{x}) = g'(a^T \mathbf{x}) \cdot a
   $$

#### Finding the Hessian $ \nabla^2 f(\mathbf{x}) $:

The Hessian is a square matrix of second partial derivatives.

1. **Use the product rule**:
   For the second derivatives, we differentiate $ g'(a^T \mathbf{x}) \cdot a $ again with respect to $ x $.

2. **Compute the Hessian**:
   Each element $ (i, j) $ of the Hessian is:
   $$
   \frac{\partial^2 f}{\partial x_i \partial x_j} = a_i \cdot g''(a^T \mathbf{x}) \cdot a_j
   $$
   Thus, the Hessian matrix is:
   $$
   \nabla^2 f(\mathbf{x}) = g''(a^T \mathbf{x}) \cdot a a^T
   $$

The gradient is a vector in the direction of $ a $ scaled by $ g' $, and the Hessian is an outer product of $ a $ with itself, scaled by $ g'' $.
