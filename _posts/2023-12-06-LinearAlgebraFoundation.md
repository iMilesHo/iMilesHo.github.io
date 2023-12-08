---
layout: post
title: "Linear Algebra Foundation"
date: 2023-12-06 01:29
category: Linear Algebra Foundations based Problems 
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

#### Step-by-step solution:
1. By the chain rule for gradients, the gradient of $ f $ with respect to $ x $ is the product of the derivative of $ g $ with respect to $ h(x) $ and the gradient of $ h $ with respect to $ x $:

   $$
   \nabla f(x) = g'(h(x)) \cdot \nabla h(x)
   $$

   where $ g'(h(x)) $ is a scalar and $ \nabla h(x) $ is a vector.

### Problem 1(c) Solution

Given $ f(x) = \frac{1}{2} x^T A x + b^T x $, where $ A $ is symmetric and $ b \in \mathbb{R}^n $ is a vector, find the Hessian $ \nabla^2 f(x) $.

#### Step-by-step solution:
1. We have already calculated $ \nabla f(x) = Ax + b $ in problem 1(a).
2. Now, to find the Hessian, we differentiate the gradient $ \nabla f(x) $ with respect to $ x $ again.
3. The derivative of $ Ax $ with respect to $ x $ is $ A $ since $ A $ is constant with respect to $ x $.
4. The derivative of $ b $ with respect to $ x $ is zero since $ b $ does not depend on $ x $.

   Combining these results, we get:

   $$
   \nabla^2 f(x) = A
   $$

### Problem 1(d) Solution

Find the gradient $ \nabla f(x) $ and the Hessian $ \nabla^2 f(x) $ of the function $ f(x) = g(a^T x) $, where $ g: \mathbb{R} \rightarrow \mathbb{R} $ is continuously differentiable and $ a \in \mathbb{R}^n $ is a vector.

#### Step-by-step solution:
1. To find $ \nabla f(x) $, we apply the chain rule as in problem 1(b):

   $$
   \nabla f(x) = g'(a^T x) \cdot a
   $$

2. To find $ \nabla^2 f(x) $, we differentiate $ \nabla f(x) $ with respect to $ x $ again, taking into account that $ g'(a^T x) $ is a function of $ x $:

   $$
   \nabla^2 f(x) = g''(a^T x) \cdot aa^T
   $$

   where $ g''(a^T x) $ is the second derivative of $ g $ with respect to its argument, evaluated at $ a^T x $, and is a scalar.

