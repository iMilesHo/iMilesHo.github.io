---
layout: post
title: "Linear Algebra Foundation"
date: 2023-12-06 01:29
category: Linear Algebra Foundations based Problems 
---

# Linear Algebra Foundations based Problems
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
