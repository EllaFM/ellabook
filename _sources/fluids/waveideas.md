# Group velocity


A useful trigonometric identity

\begin{align}\cos(\alpha)+\cos(\beta)&=\cos\left(\frac{\alpha-\beta}{2}+\frac{\alpha+\beta}{2}\right)+\cos\left(\frac{\alpha-\beta}{2}-\frac{\alpha+\beta}{2}\right)\\&=\cos\left(\frac{\alpha-\beta}{2}\right)\cos\left(\frac{\alpha+\beta}{2}\right)-\sin\left(\frac{\alpha-\beta}{2}\right)\sin\left(\frac{\alpha+\beta}{2}\right)\\&+\cos\left(\frac{\alpha-\beta}{2}\right)\cos\left(\frac{\alpha+\beta}{2}\right)+\sin\left(\frac{\alpha-\beta}{2}\right)\sin\left(\frac{\alpha+\beta}{2}\right)\\&=2\cos\left(\frac{\alpha-\beta}{2}\right)\cos\left(\frac{\alpha+\beta}{2}\right)\end{align}



Superposition of two harmonic waves
For two harmonic waves with similar frequencies and wavenumbers:

\begin{align}\phi(x,t)&=A\cos(k_1 x-\omega_1 t)+A\cos(k_2x -\omega_2 t)\\&=2A\cos\left(\frac{k_1-k_2}{2}x-\frac{\omega_1-\omega_2}{2}t\right)\cos\left(\frac{k_1+k_2}{2}x-\frac{\omega_1+\omega_2}{2}t\right)\end{align}

The first cosine is called the "envelope wave". It has a small frequency and wavenumber in comparison to the second cosine. It's velocity, called the group velocity is given by

\begin{equation}c_g=\frac{\omega_1-\omega_2}{k_1-k_2}=\frac{\Delta\omega}{\Delta k}.\end{equation}

The second cosine is called the "carrier wave". It's velocity called the phase velocity is

\begin{equation}c_p=\frac{\omega_1+\omega_2}{k_1+k_2}.\end{equation}

In the following illustration, the envelope has a wavelength ten times that of the carrier wave, and a velocity twice that of the carrier wave. The wavetrain propagates to the right with amplitude modulation. The unmodulated carrier wave is shown in blue for comparison.

Since the envelope wave here is travelling faster than the carrier wave, an observer would see waves appearing at the back of the wavetrain and disappearing at the front.

```{image} navstok_img/train1.gif
:name: a wavetrain
:alt: a wavetrain
:align: center
:scale: 100%
```

In the following illustration, the velocity ratios and wavelengths are the same as in the previous example, but the direction of the carrier wave is opposite to the direction of the envelope wave.

```{image} navstok_img/train2.gif
:name: another wavetrain
:alt: another wavetrain
:align: center
:scale: 100%
```

In the following example, the envelope wave travels at half the speed of the carrier wave. An observer would see waves appearing at the front of the wavetrain and disappearing at the back.

```{image} navstok_img/train3.gif
:name: yet another wavetrain
:alt: yet another wavetrain
:align: center
:scale: 100%
```



Motion of a wave packet
We now repeat the above analysis, but for a packet of waves, each having a different amplitude:

\begin{equation}\phi(x,t)=\int_{-\infty}^{\infty}A(k)e^{i(kx-\omega(k)t)}\mathrm{d}k\end{equation}

We will assume that the wavepacket is almost monochromatic, meaning closely centred around a single frequency. The amplitude function $A(k)$ might be a sharply peaked Gaussian, for example. This allows the frequency to be linearised around the central frequency $\omega_0$:

\begin{equation}\omega(k)\simeq \omega_0+(k-k_0)c_{g0}, \qquad c_{g0}=\frac{\mathrm{d}\omega}{\mathrm{d}k}\biggr|_{k=k_0}\end{equation}

This allows the wavepacket to be rewritten in linearised form

\begin{equation}\phi(x,t)=e^{i(k_0 x-\omega t)}\int_{-\infty}^{\infty}A(k)e^{i(k-k_0)(x-c_{g0}t)}\mathrm{d}k.\end{equation}

Again, we see that the result consists of a monochromatic "carrier wave", that travels with velocity $c_{p0}$ and an envelope that travels with velocity $c_{g0}$, where

\begin{equation}c_{p0}=\frac{\omega_0}{k_0}, \qquad  c_{g0}=\frac{\mathrm{d}\omega}{\mathrm{d}k}\biggr|_{k=k_0}.\end{equation}
