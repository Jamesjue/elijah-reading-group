---
layout: post
title: "[computer vision] Understanding Deep Image Representations by Inverting Them"
comments: true
description: "CVPR2015"
keywords: "inverting CNN, interpretability"
author: Ziqiang Feng
---

> [PDF](https://www.cv-foundation.org/openaccess/content_cvpr_2015/app/3B_081_ext.pdf)

## Summary
CNNs, as well as classic computer vision features (e.g., SIFT, HOG), 
extracts some form of **representations** from images.
In terms of SIFT, it's the SIFT key points.
In terms of CNN, it's the activation maps of different layers.
This paper tries to reconstruct the original image from these representations
(i.e., *inverting* the transformation).
Such reconstruction provides insight into what the algorithm is looking for in an image.

## Formulating reconstruction as a gradient-descent-able optimization problem

The paper formulates the reconstruction problem as an end-to-end optimization problem.
It adjusts the pixel values of the reconstructed image (**x**) to minimize an objective function.

Expected, the objective function is 

*(loss = l_2 distance of representation) + (regularization = natural image prior)*

Usually, there are more than one "good" reconstructed images due to the non-convexity of the problem.
It initializes the input with different seeds to obtain different samples.

This formulation treats the algorithm (CNN, SIFT, HOG) mostly as a black box.
The only requirement is that the transformation needs to be **differentiable**,
so that it can use gradient descent.

### Implementing SIFT and HOG as DNN

The paper describes how we can implement SIFT and HOG in the form of DNN
so that they become **differentiable**, amenable to gradient descent.
Refer to the paper for details.

## Observations

### CNN

Reconstruction from early layers in CNN yields images that look photometrically similar
to the original image.

Reconstruction from higher layers in CNN yields images that repeat "import parts" of
the object or composite them in a different way.

#### Reconstructing from a smaller spatial region

The natural image prior drives the input pixels that reside outside 
the receptive field of the selected region to become "blank".

#### Reconstructing from a subset of channels

Inverting a subset of channels from AlexNet shows some channels focus on shape
while other focus on color.
The same observation was also reported in the original AlexNet paper.