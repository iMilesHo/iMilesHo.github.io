---
layout: post
title: The Activation Functions in Deep Learning
date: 2024-01-18 12:10:10
description: About AWS Sign-In
tags: DeepLearning
categories: posts
giscus_comments: true
related_posts: true
---

# The Activation Functions in Deep Learning

## What is Activation Functions?

Activation functions are mathematical equations that determine the output of a neural network. The function is attached to each neuron in the network, and determines whether it should be activated (“fired”) or not, based on whether each neuron’s input is relevant for the model’s prediction.

Activation functions also help normalize the output of each neuron to a range between 1 and 0 or between -1 and 1.

## Why do we need Activation Functions?

In short, activation functions are what introduce non-linearity to neural networks. Their main purpose is to convert an input signal of a node in a neural network to an output signal. That output signal now is used as an input in the next layer in the stack. So that means without activation functions, our neural network would only be able to learn linear relationships.

## Types of Activation Functions

### Softmax

The softmax function is a more generalized logistic activation function which is used for multiclass classification. 




