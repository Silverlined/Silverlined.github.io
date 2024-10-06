---
author: unknown
sitemap: false
---
## ELI5: Wavelet Transform

A Fourier transform provides us with a way to represent a signal that varies in amplitude over time by essentially decomposing it into a sum of a large or even infinite number of sines (or cosines) with differing frequencies and phase information. For signals that are periodic and with frequency content that doesn't change much over time, this can be a convenient way to represent the signal. But one unfortunate thing about Fourier transforms is that if you have a signal that only repeats once or twice, the number of sines you need to represent it with whatever degree of accuracy is required is often quite large.

The wavelet transform takes the same concept as the Fourier transform, but instead of representing the signal as a sum of sine functions, it represents the signal as a sum of wavelet functions. These functions are defined to be finite in time. That is, they have a non-zero amplitude only for some finite window around the origin. Outside of that window, they have a zero amplitude. The signal is then, loosely speaking, compared (by convolution) to a number of different versions of the wavelet function, which differ in time width, as the wavelet function is moved across the signal from time equals 0 to the end of the signal. In some ways, you can think of a wavelet transform as a more general Fourier transform, which uses functions that don't have to be shaped like sines to determine the frequency content of a signal.

![](https://raw.githubusercontent.com/Silverlined/silverlined.github.io/main/res/wavelet.png)

Some significant advantages for the wavelet transform are when the signal has spectral content that changes significantly over time, and when the signal has near-instantaneous changes in time. These characteristics can be difficult to represent, especially with a smaller amount of data, by Fourier transform. Another advantage is that if you are looking for a signal with added noise and you know what it's supposed to look like, you can use a wavelet that looks like that to identify what frequency you're seeing the signal at and separate it from the noise quite easily.

