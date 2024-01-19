---
layout: post
title: ANN Backpropagation Process
date: 2023-11-01 22:10:10
description: About ANN Backpropagation Process
tags: MechineLearning
categories: posts
giscus_comments: true
related_posts: true
---


Backpropagation is a supervised learning algorithm used for training artificial neural networks (ANNs), including multilayer perceptrons (MLPs). It employs the chain rule of calculus to efficiently compute gradients of the loss function with respect to the weights of the network, which are then used to update the weights.

Here’s a simplified breakdown of how backpropagation works in a neural network:

### 1. **Forward Pass:**
   - Input is passed through the network.
   - Each layer applies weights, biases and activation functions.
   - The final output is compared with the target using a loss function to calculate the error.

### 2. **Backward Pass (Backpropagation):**
   - Calculate the gradient of the loss function with respect to each weight by propagating the gradient backward through the network from the output layer to the input layer.
   - Update the weights using a method such as gradient descent.

### Example: Simplified Calculation Process in a MLP

Let's consider a simple neural network with one hidden layer. Suppose we have:

- Input \(x\)
- Weights from input to hidden layer \(w_1\)
- Weights from hidden to output layer \(w_2\)
- Activation functions \(f\) for the hidden layer and \(g\) for the output layer

#### Forward Pass:

1. Calculate net input to the hidden layer:
   \[
   z_1 = w_1 \cdot x + b_1
   \]
2. Apply activation function:
   \[
   h = f(z_1)
   \]
3. Calculate net input to the output layer:
   \[
   z_2 = w_2 \cdot h + b_2
   \]
4. Apply activation function to get the final output:
   \[
   y = g(z_2)
   \]

#### Backward Pass:

1. Calculate the derivative of the loss function \(L\) with respect to the output:
   \[
   \frac{\partial L}{\partial y} = 2(y - \text{target})
   \]
2. Calculate the gradient with respect to the weights \(w_2\) between hidden and output layers:
   \[
   \frac{\partial L}{\partial w_2} = \frac{\partial L}{\partial y} \cdot \frac{\partial y}{\partial z_2} \cdot \frac{\partial z_2}{\partial w_2} = \frac{\partial L}{\partial y} \cdot g'(z_2) \cdot h
   \]
3. Calculate the gradient with respect to the weights \(w_1\) between input and hidden layers:
   \[
   \frac{\partial L}{\partial w_1} = \frac{\partial L}{\partial y} \cdot \frac{\partial y}{\partial z_2} \cdot \frac{\partial z_2}{\partial h} \cdot \frac{\partial h}{\partial z_1} \cdot \frac{\partial z_1}{\partial w_1} = \frac{\partial L}{\partial y} \cdot g'(z_2) \cdot w_2 \cdot f'(z_1) \cdot x
   \]
4. Update the weights \(w_1\) and \(w_2\) using the calculated gradients, typically using a method like gradient descent:
   \[
   w_1 = w_1 - \eta \frac{\partial L}{\partial w_1}
   \]
   \[
   w_2 = w_2 - \eta \frac{\partial L}{\partial w_2}
   \]

   Here, \(\eta\) is the learning rate, a hyperparameter you choose to control the size of the steps taken during optimization.


5. The gradient with respect to the output layer bias, \(b_2\), is:
   \[
   \frac{\partial L}{\partial b_2} = \frac{\partial L}{\partial y} \cdot \frac{\partial y}{\partial z_2} = \frac{\partial L}{\partial y} \cdot g'(z_2)
   \]
   
6. The gradient with respect to the hidden layer bias, \(b_1\), is:
   \[
   \frac{\partial L}{\partial b_1} = \frac{\partial L}{\partial y} \cdot \frac{\partial y}{\partial z_2} \cdot \frac{\partial z_2}{\partial h} \cdot \frac{\partial h}{\partial z_1} = \frac{\partial L}{\partial y} \cdot g'(z_2) \cdot w_2 \cdot f'(z_1)
   \]
   
7. Update the biases using the gradients:
   \[
   b_1 = b_1 - \eta \frac{\partial L}{\partial b_1}
   \]
   \[
   b_2 = b_2 - \eta \frac{\partial L}{\partial b_2}
   \]

Note that when you're calculating the gradients with respect to the biases, you're essentially asking, "How does the loss change as I adjust the bias?" The reason you don't see \(x\) or \(h\) in the gradient formulas for biases is that the derivative of a bias (being an additive term) with respect to itself is 1. 

Including biases in the neural network allows the network to better fit the data by allowing flexibility in adjusting the activations. Without biases, the neuron's output would always be forced to go through the origin (0,0) in the input-output space, which would greatly limit the representational power of the network.

In this way, by repeatedly applying the backpropagation algorithm, the neural network learns to adjust its weights to minimize the error between its predictions and the actual target values, thus training the model. Note that this example is greatly simplified for illustration; real-world neural networks typically involve many more layers and neurons, and various additional considerations such as batch processing, regularization, and various optimization algorithms.