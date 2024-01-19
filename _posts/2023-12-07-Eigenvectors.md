---
layout: post
title: Linear Algebra Foundation based Homework Problems - Eigenvectors, eigenvalues, and the spectral theorem
date: 2023-12-07 11:10:10
description: About Linear Algebra Foundation
tags: Linear Algebra Eigenvalues Eigenvectors Spectral Theorem
categories: posts
giscus_comments: true
related_posts: true
---

# Understanding Eigenvalues, Eigenvectors, and the Spectral Theorem

## The Fascinating World of Linear Algebra

Linear algebra is a fundamental area of mathematics with vast applications in fields like physics, engineering, computer science, and beyond. One of the core concepts in linear algebra is the idea of eigenvalues and eigenvectors, which comes into play when dealing with linear transformations and matrices. These concepts are deeply connected to the Spectral Theorem, which provides insight into the structure of matrices and the transformations they represent.

### What are Eigenvalues and Eigenvectors?

To dive into this topic, let's consider the eigenvalues of an $ n 	imes n $ matrix $ A $ with real entries. These eigenvalues are the roots of the characteristic polynomial $ p_A(\lambda) = \text{det}(\lambda I - A) $, which can be complex. They're defined as the values $ \lambda \in \mathbb{C} $ for which there exists a vector $ x \in \mathbb{C}^n $ such that $ Ax = \lambda x $. Such a pair ($ x, \lambda $) is known as an eigenvector, eigenvalue pair.

### The Spectral Theorem

The Spectral Theorem is a fascinating result that tells us that every real symmetric matrix can be diagonalized by an orthogonal matrix. That is, we can find a matrix $ T $ such that $ T^{-1}AT $ is a diagonal matrix. This theorem is particularly useful because it allows us to understand the matrix $ A $ in terms of its eigenvalues and eigenvectors.

### The Problem at Hand

Consider the following problem, which provides a fantastic application of the concepts we've just discussed:

*Suppose that the matrix $ A \in \mathbb{R}^{n \times n} $ is diagonalizable, that is, $ A = T\text{diag}(\lambda_1, \ldots, \lambda_n)T^{-1} $ for an invertible matrix $ T $, where $ \text{diag}(\lambda_1, \ldots, \lambda_n) $ is diagonal. Using the notation $ t^{(i)} $ for the columns of $ T $, show that $ At^{(i)} = \lambda_i t^{(i)} $, so that the eigenvalues/eigenvector pairs of $ A $ are $ (t^{(i)}, \lambda_i) $.*

### The Proof

The problem asks us to prove that each column of $ T $ is an eigenvector of $ A $ corresponding to the eigenvalue on the diagonal of $ \text{diag}(\lambda_1, \ldots, \lambda_n) $. Here’s how we can prove this assertion:

1. We start with the equation $ A = T\text{diag}(\lambda_1, \ldots, \lambda_n)T^{-1} $.
2. Multiplying both sides by $ T $, we get $ AT = T\text{diag}(\lambda_1, \ldots, \lambda_n) $.
3. This equation implies that each column $ t^{(i)} $ of $ T $ is scaled by the corresponding $ \lambda_i $.
4. It follows that $ At^{(i)} = \lambda_i t^{(i)} $ for each column $ t^{(i)} $, proving that $ t^{(i)} $ is an eigenvector of $ A $ with eigenvalue $ \lambda_i $.

## Spectral Theorem and Symmetric Matrices

A matrix $U \in \mathbb{R}^{n 	imes n}$ is orthogonal if $U^TU = I$. The spectral theorem, perhaps one of the most important theorems in linear algebra, states that if $A \in \mathbb{R}^{n 	imes n}$ is symmetric, that is, $A = A^T$, then $A$ is diagonalizable by a real orthogonal matrix. That is, there are a diagonal matrix $\Lambda \in \mathbb{R}^{n 	imes n}$ and orthogonal matrix $U \in \mathbb{R}^{n 	imes n}$ such that $U^TAU = \Lambda$, or, equivalently, $A = U\Lambda U^T$.

Let $\lambda_i = \lambda_i(A)$ denote the ith eigenvalue of $A$.

### Problem Statement

(b) Let $A$ be symmetric. Show that if $U = [u^{(1)} \ldots u^{(n)}]$ is orthogonal, where $u^{(i)} \in \mathbb{R}^n$ and $A = U\Lambda U^T$, then $u^{(i)}$ is an eigenvector of $A$ and $Au^{(i)} = \lambda_iu^{(i)}$, where $\Lambda = 	ext{diag}(\lambda_1, \ldots, \lambda_n)$.

### Answer

If $U$ is orthogonal, then $U^{-1} = U^T$.

$$
\begin{align*}
AU &= U\Lambda U^TU \\
&= U\Lambda U^{-1}U \\
&= U\Lambda \\
&= AU
\end{align*}
$$

(because $\Lambda$ is a diagonal matrix)

## Positive Semi-Definite Matrices and Eigenvalues

Understanding the nature of positive semi-definite (PSD) matrices is crucial in various domains of mathematics and applied sciences. These matrices have the characteristic that they do not produce negative outputs when applied to quadratic forms.

### Problem Statement

(c) Show that if $ A $ is PSD, then $ \lambda_i(A) \geq 0 $ for each $ i $.

### Solution

Given that $ A $ is a PSD matrix, this implies for any vector $ x $, $ x^TAx \geq 0 $.

Considering the spectral decomposition of $ A $, where $ A = U\Lambda U^T $ and $ U $ is an orthogonal matrix, we can express the quadratic form $ x^TAx $ using this decomposition:

$$
\begin{align*}
x^TAx &= x^T U\Lambda U^T x \\
&= (U^Tx)^T \Lambda (U^Tx) \\
&= y^T\Lambda y \\
&= \sum_{i=1}^{n} \lambda_i y_i^2
\end{align*}
$$

Here, we let $ y = U^Tx $. Since $ U $ is orthogonal, $ y $ is simply the vector $ x $ represented in the basis of eigenvectors of $ A $. The expression $ y^T\Lambda y $ sums the products of each eigenvalue $ \lambda_i $ with the square of the $ i $-th component of $ y $.

For $ A $ being PSD, it must hold that $ x^TAx \geq 0 $ for every $ x $. This implies $ \sum_{i=1}^{n} \lambda_i y_i^2 \geq 0 $ for every $ y $, and since $ y_i^2 \geq 0 $, each eigenvalue $ \lambda_i $ must be non-negative to ensure the sum is non-negative.

Therefore, it is proven that $ \lambda_i \geq 0 $ for each $ i $, confirming that all eigenvalues of a PSD matrix are non-negative.