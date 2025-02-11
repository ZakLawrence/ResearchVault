---
tags:
  - Stats
---
These are a special case of [[Moment of a distribution]] with $g(x) = e^{ikx}$ which is the [[Fourier transformation]] of the [[Probability density function]]

$$\phi(k) = \int\limits_{-\infty}^{\infty}e^{ikx}f(x)dx $$

The p.d.f can be obtained from the characteristic function by a **inverse Fourier Transformation**

$$f(x) = \frac{1}{2\pi}\int\limits_{-\infty}^{\infty} \phi(x)e^{-ikx}dk $$

the [[Moment of a distribution]] can be generated from the characteristic function. Taking the [[Taylor expansion]] of $e^{ikx}$

$$e^{ikx} = \sum\limits_{n=0}^{\infty}\frac{(ikx)^n}{n!}x^n$$
$$\phi(k) = \sum\limits_{n=0}^{\infty}\int\limits_{-\infty}^{\infty}\frac{(ikx)^n}{n!}x^nf(x)dx = \sum\limits_{n=0}^{\infty}\frac{(ik)^n}{n!}\int\limits_{-\infty}^{\infty}x^nf(x)dx =\sum\limits_{n=0}^{\infty}\frac{(ik)^n}{n!} <x^n> $$

From this the moments of the distribution can be extracted from the characteristic function. 
$$\frac{d^m}{dk^m}\phi(k)\rvert_{k=0} = i^m<x^m>$$

[[Applications of Characteristic functions]]


