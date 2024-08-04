---
title: "Welcome to Computational Imaging"
mathjax: true
layout: post
---
This post presents the image formation process from an information  perspective. Image formation is mathematically expressed as a linear combination of the eigenfunctions of an imaging system, with each eigenfunction being multiplied by a specific weighting factor. This weighting factor depends on the choice of basis functions and the properties of the object, such as frequency, complexity, and spatial extent. This post explores how the information content of an object signal is modified as it traverses the imaging system and, therefore, provides an intuition to develop a computational imaging system. 

An imaging system functions as an operator that maps object information from the object space to the end user in the form of an image. For a linear shift-invariant (LSI) imaging system, it is always possible to decompose the object information into elementary stimuli, each producing a specific response according to the imaging system. Due to the linearity property, the total response can be determined by taking the linear combination of the responses of the elementary stimuli. For example, an object signal  $g(x)$ can be expressed as a discrete linear combination of the system's basis functions $\psi(x)$ as follows:

  $$  g(x) = \sum_{n\in N} G(n) \psi(x) $$

Here, $N$ is a discrete index set (e.g. $Z$ , $N$ ,($Z$ x $Z$), ($N$ x $Z$ ), etc.) which will be different depending on the application. The function $\psi(x)$ represents the basis function, which is expressed as the complex exponential $e^{(i2\pi nx)}$ in the Fourier series representation of the object. The weighted function $G(n)$, representing the Fourier coefficients, can be calculated through the orthogonal projection of the object information onto the complex conjugate of these harmonics, as shown by:

  $$ G(n) = \int_{0}^{1} g(x)e^{-i2\pi n x} dx $$
   $$ = \langle g(x), \psi^*(x)\rangle$$

These basis functions are also the eigenfunctions of the linear shift-invariant (LSI) system. Consequently, the basis functions pass through the imaging system without any alteration in their functional form, albeit with an additional multiplicative factor representing the system's eigenvalue. The coefficient of the final image is therefore expressed as $G_{im}(n) = H(n) G(n)$. The function $H(n)$ , which can be complex, is known as the system's transfer function and represents the continuum of the system's eigenvalues. The image can be determined by interpolating the coefficients with the eigenfunction as 

  $$ g_{im}(x) = \sum_{n\in N} G_{im}(n) \psi(x) = \sum_{n\in N} H(n) G(n) \psi(x)$$

Thus, a system can influence both the phase and amplitude properties of the input object signal. As the basis functions traverse the system, their weighting factors are modified by the system's transfer function. Thus, the final image obtained is essentially a linear combination of these altered basis functions. For a bandlimited system (with a rectangular aperture), these basis functions can vary and are known as prolate spheroidal wavefunctions. \par
To modify the optical system, one can either alter the system's basis or its transfer function. The former approach is referred to as illumination diversity, whereas the latter pertains to synthetic aperture imaging. In this study, we have employed the latter approach and modified our optical setup by adjusting the system's transfer function. This adjustment influences the eigenfunction that propagates through the system, consequently impacting the system's information capacity. The detailed implications of these modifications are elaborated in the subsequent chapter.

