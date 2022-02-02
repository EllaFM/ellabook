# Vorticity


## Euler's equations
HERE

Will we assume incompressibility? Yes for water waves. No for sound waves (obvs).

We also need to consider how irrotationality could/not arise for inviscid flow.


## The vorticity equation
Let us return to the version of Euler's equation that we gave earlier in {eq}`vorticity-head` for a conservative body force:
\begin{equation}\frac{\partial \underline{u}}{\partial t}+\underline{\omega}\times\underline{u}=-\nabla H.\end{equation}
Since "curlgrad"=0, we can eliminate the head by taking the curl:
\begin{equation}\frac{\partial \underline{\omega}}{\partial t}+\nabla\times(\underline{\omega}\times\underline{u})=\underline{0}.\end{equation}
The second term can be expanded using vector identities to obtain the following equation for the material derivative of the vorticity:
\begin{equation}\frac{D\underline{\omega}}{D t}=(\underline{\omega}.\nabla)\underline{u}-\underline{\omega}(\nabla.\underline{u}).\end{equation}
In an incompressible flow there is no divergence of the velocity field and so we obtain the vorticity transport equation
\begin{equation}\frac{D\underline{\omega}}{D t}=(\underline{\omega}.\nabla)\underline{u}.\end{equation}
The term on the right is called the "vortex stretching" term. It gets its non-zero contribution from the component of the velocity gradient parallel to $\underline{\omega}$, in which case vortex lines are "stretched" by the velocity field, causing them to spin faster. This effect is involved in the formation of tornadoes.

````{admonition} Tornado formation
:class: theorem
The presence of strong winds near to the ground creates a shear gradient, which can cause the formation of a vortex line as shown in the image below, which is taken from [a 1984 research paper](https://doi.org/10.1175/1520-0469(1984)041%3C2991:SVTOOU%3E2.0.CO;2). Thermal updrafts can then tilt the vortex tube upwards to form a vertical column of rotating air. The simultaneous stretching effect of the thermal updrafts can cause tornadoes to spin very fast.

```{image} navstok_img/tornado.png
---
name: tornado formation
alt: alternative text
align: center
scale: 60%
---
```
*Note: It should be recognised that the formation of a vortex line is a viscous phenomenon!*
````


For two-dimensional flows the vortex stretching term is zero:
\begin{equation}\underline{u}=(u(x,y),v(x,y)) \quad \Rightarrow \quad \underline{\omega}=(0,0,\omega), \quad \omega=\frac{\partial v}{\partial x}-\frac{\partial u}{\partial y} \qquad \Rightarrow \quad (\underline{\omega}.\nabla)\underline{u}=\underline{0}\end{equation}
In this case, the vorticity transport equation reduces to
\begin{equation}\frac{D\underline{\omega}}{Dt}=0\end{equation}
which tells us that the vorticity remains constant following the fluid.

```{admonition} The persistence of irrotational flow in an inviscid fluid
:class: warning
If the fluid is initially irrotational then the vorticity will be zero along all fluid paths. The Euler equation cannot produce vorticity - it can only maintain it! For example, this is the case for flows that are started from rest. The implication is that irrotational flows are more common than you might expect.

Recall, too that the combination of inviscid and irrotational flow satisfies Laplace's equation $\nabla^2\phi=0.$
```

## Shallow water

a
