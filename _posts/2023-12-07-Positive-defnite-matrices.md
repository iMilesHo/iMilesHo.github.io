---
layout: post
title: Linear Algebra Foundation based Homework Problems - Positive defnite matrices
date: 2023-12-07 19:10:10
description: About Linear Algebra Foundation
tags: Math
categories: posts
giscus_comments: true
related_posts: true
---

## Positive Definite Matrices

A matrix $ A \in \mathbb{R}^{n \times n} $ is **positive semi-definite (PSD)**, denoted $ A \succeq 0 $, if $ A = A^T $ and $ x^T A x \geq 0 $ for all $ x \in \mathbb{R}^n $. A matrix $ A $ is **positive definite**, denoted $ A \succ 0 $, if $ A = A^T $ and $ x^T A x > 0 $ for all $ x \neq 0 $, that is, all non-zero vectors $ x $. The simplest example of a positive definite matrix is the identity $ I $ (the diagonal matrix with 1s on the diagonal and 0s elsewhere), which satisfies $ x^T I x = \|x\|^2 = \sum_{i=1}^{n} x_i^2 $.

(a) Let $ z \in \mathbb{R}^n $ be an n-vector. Show that $ A = zz^T $ is positive semidefinite.

(b) Let $ z \in \mathbb{R}^n $ be a non-zero n-vector. Let $ A = zz^T $. What is the null-space of $ A $? What is the rank of $ A $?

(c) Let $ A \in \mathbb{R}^{n \times n} $ be positive semidefinite and $ B \in \mathbb{R}^{m \times n} $ be arbitrary, where $ m, n \in \mathbb{N} $. Is $ BAB^T $ PSD? If so, prove it. If not, give a counterexample with explicit $ A, B $.



## Solutions

### Problem 2(a)
To solve problem (a), we need to show that the matrix $ A = zz^T $ is positive semidefinite (PSD). A matrix $ A $ is positive semidefinite if, for any vector $ x \in \mathbb{R}^n $, the following condition is satisfied:

$$ x^T A x \geq 0 $$

Here are the steps to show that $ A = zz^T $ is PSD:

1. **Apply the definition**: For any vector $ x $, we need to consider $ x^T A x $ and show that this is always greater than or equal to 0.

2. **Substitute $ A $ with $ zz^T $**: We have $ x^T A x = x^T (zz^T) x $.

3. **Use matrix multiplication**: Remember that matrix multiplication is associative, so we can rearrange the multiplication as $ (x^T z)(z^T x) $.

4. **Recognize the dot product**: The term $ (x^T z) $ is a dot product of $ x $ and $ z $, which gives a scalar. Let's denote it as $ c $, so $ c = x^T z $ and $ c $ is a real number since it's a scalar.

5. **Express $ c $ as a scalar multiplication**: We now have $ c(z^T x) $, which is the same as $ c^2 $ because $ z^T x $ will also give the same dot product as $ x^T z $.

6. **Conclude the proof**: We know that $ c^2 $ is always non-negative for any real number $ c $, and hence $ x^T A x = c^2 \geq 0 $.

So, we have shown that for any vector $ x $, $ x^T A x $ is always non-negative, hence $ A = zz^T $ is positive semidefinite.

### Problem 2(b)

Problem (b) asks for the null-space and the rank of the matrix $ A = zz^T $, where $ z $ is a non-zero $ n $-vector.

Here's how to solve it:

1. **Null-space**: The null-space (or kernel) of $ A $ consists of all vectors $ x $ such that $ Ax = 0 $. So we need to solve $ zz^T x = 0 $ for $ x $.

   Since $ z $ is non-zero, $ zz^T $ is a rank-1 matrix (because each row is a multiple of $ z $), and the only vector that gets mapped to the zero vector by $ zz^T $ is a vector orthogonal to $ z $. Therefore, the null-space is the set of all vectors that are orthogonal to $ z $.

2. **Rank**: The rank of a matrix is the dimension of the column space (the space spanned by its columns). Since $ A = zz^T $ has each column as a multiple of $ z $, and $ z $ is non-zero, the column space is the line through $ z $ (and the origin). Therefore, the rank of $ A $ is 1, because there is only one linearly independent column in $ A $.

So the null-space of $ A $ is the $ (n-1) $-dimensional subspace of $ \mathbb{R}^n $ orthogonal to $ z $, and the rank of $ A $ is 1.

### Problem 2(c)

To solve problem (c), we are asked to determine if the matrix $ BAB^T $ is positive semidefinite (PSD) given that $ A $ is PSD and $ B $ is arbitrary, where $ A \in \mathbb{R}^{n \times n} $ and $ B \in \mathbb{R}^{m \times n} $.

Here's how to approach the problem:

1. **Use the definition of a PSD matrix**: A matrix $ C $ is PSD if for any vector $ x $, $ x^T C x \geq 0 $.

2. **Apply this definition to $ BAB^T $**: Let $ y $ be any vector in $ \mathbb{R}^m $, then we need to show that $ y^T (BAB^T) y \geq 0 $.

3. **Expand using matrix multiplication**: The expression becomes $ y^T BAB^T y $.

4. **Rearrange the expression**: Since matrix multiplication is associative, we can write this as $ (B^T y)^T A (B^T y) $.

5. **Recognize that $ B^T y $ is a vector in $ \mathbb{R}^n $**: Let's denote $ z = B^T y $, which is a valid vector in $ \mathbb{R}^n $ since $ B $ has $ n $ columns.

6. **Apply the fact that $ A $ is PSD**: Since $ A $ is PSD, it follows that for any vector $ z $, $ z^T A z \geq 0 $.

7. **Conclude the proof**: Since $ z = B^T y $ and $ z^T A z \geq 0 $ for any $ y $, we can conclude that $ y^T (BAB^T) y = (B^T y)^T A (B^T y) \geq 0 $ for any $ y $. Thus, $ BAB^T $ is PSD.

So, regardless of what $ B $ is, as long as $ A $ is PSD, the matrix $ BAB^T $ will also be PSD. This is because the product $ z^T A z $ will always be non-negative due to the properties of $ A $, and $ z $ is simply the result of transforming $ y $ by $ B^T $, which does not affect the non-negativity of $ z^T A z $.
