---
layout: post
title: "Linear Algebra Foundation based Homework Problems - Eigenvectors, eigenvalues, and the spectral theorem"
date: 2023-12-07 22:00
category: Eigenvectors, eigenvalues, and the spectral theorem
---

## Eigenvectors, eigenvalues, and the spectral theorem

### 3. [0 points] Eigenvectors, eigenvalues, and the spectral theorem

The eigenvalues of an \( n \times n \) matrix \( A \in \mathbb{R}^{n \times n} \) are the roots of the characteristic polynomial \( p_A(\lambda) = \text{det}(\lambda I - A) \), which may (in general) be complex. They are also defined as the values \( \lambda \in \mathbb{C} \) for which there exists a vector \( x \in \mathbb{C}^n \) such that \( Ax = \lambda x \). We call such a pair \( (x, \lambda) \) an eigenvector, eigenvalue pair. In this question, use the notation \( \text{diag}(\lambda_1, \ldots, \lambda_n) \) to denote the diagonal matrix with diagonal entries \( \lambda_1, \ldots, \lambda_n \), that is,

\[ \text{diag}(\lambda_1, \ldots, \lambda_n) = \begin{pmatrix}
\lambda_1 & 0 & \cdots & 0 \\
0 & \lambda_2 & \cdots & 0 \\
0 & 0 & \ddots & \vdots \\
\vdots & \vdots & & \vdots \\
0 & 0 & \cdots & \lambda_n
\end{pmatrix} \]

(a) Suppose that the matrix \( A \in \mathbb{R}^{n \times n} \) is diagonalizable, that is, \( A = T\Lambda T^{-1} \) for an invertible matrix \( T \in \mathbb{R}^{n \times n} \), where \( \Lambda = \text{diag}(\lambda_1, \ldots, \lambda_n) \) is diagonal. Use the notation \( t^{(i)} \) for the columns of \( T \), so that \( T = [t^{(1)} \cdots t^{(n)}] \), where \( t^{(i)} \in \mathbb{R}^n \). Show that \( A t^{(i)} = \lambda_i t^{(i)} \), so that the eigenvalues/eigenvector pairs of \( A \) are \( (t^{(i)}, \lambda_i) \).

A matrix \( U \in \mathbb{R}^{n \times n} \) is orthogonal if \( U^TU = I \). The spectral theorem, perhaps one of the most important theorems in linear algebra, states that if \( A \in \mathbb{R}^{n \times n} \) is symmetric, that is, \( A = A^T \), then \( A \) is diagonalizable by a real orthogonal matrix. That is, there are a diagonal matrix \( \Lambda \in \mathbb{R}^{n \times n} \) and orthogonal matrix \( U \in \mathbb{R}^{n \times n} \) such that \( U^T AU = \Lambda \), or equivalently,

\[ A = U\Lambda U^T \].

Let \( \lambda_i = \Lambda(i) \) denote the \( i \)th eigenvalue of \( A \).

(b) Let \( A \) be symmetric. Show that if \( U = [u^{(1)} \cdots u^{(n)}] \) is orthogonal, where \( u^{(i)} \in \mathbb{R}^n \) and \( A = U\Lambda U^T \), then \( u^{(i)} \) is an eigenvector of \( A \) and \( Au^{(i)} = \lambda_i u^{(i)} \), where \( \Lambda = \text{diag}(\lambda_1, \ldots, \lambda_n) \).

(c) Show that if \( A \) is PSD, then \( \lambda_i(A) \geq 0 \) for each \( i \).
