# Introduction
Fluid dynamics is the study of flow. Since anything that flows can be thought of as a fluid, this field of study covers a tremendous range of applications, including aerodynamics, meteorology, hydraulics, oceanography, astrophysical dynamics, acoustics, hemodynamics (blood flow) and mucus flows. Principles of fluid dynamics have even been applied to the study of granular flows, such as dry sand, vehicular traffic and crowd dynamics.

Despite the vast range of applications, most of these phenomena can be examined by just three unifying principles:

* Conservation of mass
* Conservation of momentum
* Conservation of energy

For many flows (this course), we can neglect thermodynamic effects, and in that case we can also get by without conservation of energy. This chapter introduces the equations of conservation of mass and conservation of momentum.

## The continuum hypothesis

So that we can use the tools of calculus, we treat the fluid as if it were continuous in structure and we regard physical quantities as locally uniform. This also means we can treat gases and liquids in the same way, since the equations of motion are independent of the particle structure.

An illustration of the idea is shown below, applied to measurements of density. We ignore molecular fluctuations, and consider a locally averaged measure of density based on the mean free path between atoms.

<br>

```{image} fluids/navstok_img/continuum_hypothesis.png
---
name: continuum_hypothesis
alt: some alternative text
align: center
scale: 80%
---
```

<br>

In actuality, the concept of "density" does not apply very meaningfully at the microscopic level, since the density at each point is defined by either being "inside" or "outside" an atom.


```{admonition} Big idea: Conservation of mass and momentum
:class: tip
The equations governing the motion of fluids are the Navier-Stokes equations, for conservation of mass and momentum. They apply at the macroscopic level, where quantities such as the fluid velocity and density are treated as continuous.

For fluid motions that occur well below the speed of sound, the effects of compressibility can be neglected, and in that case the conservation of mass equation simplifies to the incompressibility condition $\nabla.\underline{v}=0$, where $\underline{v}$ is the velocity field.

The conservation of momentum equation represents a balance between convective acceleration, pressure forces and the diffusion of momentum to neighbouring fluid elements. A wide class of so-called "Newtonian" fluids exhibit a linear relationship between the shear stress and the velocity gradient, in which the constant of proportionality is a material quantity, called the viscosity.

By non-dimensionalising the equations of motion, we can consider motion on different length/velocity scales or in fluids of different viscosity all by varying a single parameter, called the Reynolds number $\mathrm{Re}$.
```

It is helpful to classify the study of fluids as follows:



Incompressible	Compressible
Inviscid	This course	Acoustics (high speed)
Viscous	This course in part	Research only!

### Inviscid flows

Big idea: Steady solutions
By neglecting viscosity, we obtain Euler's equation - a differential equation relating the pressure, convective acceleration and body forces. In the special case of steady (time-independent) flows we may further deduce an algebraic relationship between the pressure and velocity. The result, which is known as Bernoulli's theorem applies only on a streamline, unless the flow is irrotational - in which case it applies everywhere.
This may seem a very narrow restriction, but in this section we also show that an inviscid flow that is initially irrotational will remain so throughout the subsequent motion. The implication is that irrotational flows are more common than you might expect.


### Example: Archimides' Principle

If we take the body force to be gravity, $\underline{g}=(0,0,-g)$ and we assume that the fluid is at rest so that $\underline{u}=\underline{0}$ then from the conservation of momentum equation {eq}`consofmom5` we obtain a result for the hydrostatic pressure :
\begin{equation}\nabla p =(0,0,-g\rho)\quad \Rightarrow p=K-\rho g z,\end{equation}
where the constant $K$ is the pressure at $z=0$.
We now calculate the force due to hydrostatic pressure on a body immersed within the fluid:
\begin{equation}\underline{F}=-\int_S p\ \underline{\mathrm{d}S} = - \int_V (\nabla{p}) dV\end{equation}
Here, the minus sign is because the pressure acts inwards on the surface, in the opposite direction to the definition of the normal $\underline{\mathrm{d}S}.$ The rewriting of the surface integral as a volume integral is a consequence of one of the many corollaries of the divergence theorem.
From the result $\nabla p =(0,0,-g\rho)$ we then obtain
\begin{equation}\underline{F} = \underline{g}\int_V\rho dV\end{equation}
This tells us that there is an upward force on the body which is equal in magnitude to the weight of water displaced.

### dead
### Almost uniform rotation

In {numref}`rotfram-navstok`, the Navier-Stokes equations were presented relative to a rotating frame of reference. We will consider the case of a body of fluid that undergoes weak motion relative to a frame rotating at constant angular velocity $\underline{\Omega}.$

Taking $U$ and $L$ to be characteristic length and velocity scales of the motion allows us to compare the size of the inertial term relative to the Coriolis term:

 \begin{equation}\frac{|\underline{u}.\nabla\underline{u}|}{|\underline{\Omega}\times\underline{u}|}\sim \frac{U^2/L}{\Omega U} = \frac{U}{L\Omega}.\end{equation}

If this ratio is much smaller than one then the inertial term can be neglected to a first approximation. We will also suppose that viscous effects may be neglected in the interior of the fluid (i.e. away from any boundaries). The equations of motion then simplify to

\begin{align}\frac{\partial \underline{u}}{\partial t}+2(\underline{\Omega}\times\underline{u})&=-\frac{1}{\rho}\nabla p_R,\\
\nabla.\underline{u}&=0,\end{align}

where $p_R$ denotes the reduced pressure.

Taking the angular velocity to be $\underline{\Omega}=(0,0,\Omega)$ and denoting the velocity by $\underline{u}=(u,v,w)$ gives the following scalar (component) form:

\begin{equation*}
\frac{\partial u}{\partial t} -2\Omega v= -\frac{1}{\rho}\frac{\partial p_R}{\partial x}, \qquad
\frac{\partial v}{\partial t} +2\Omega u= -\frac{1}{\rho}\frac{\partial p_R}{\partial y}, \qquad
\frac{\partial w}{\partial t} = -\frac{1}{\rho}\frac{\partial p_R}{\partial z},
\end{equation*}
\begin{equation*}
\frac{\partial u}{\partial x}+\frac{\partial v}{\partial y}+\frac{\partial w}{\partial z} =0
\end{equation*}

The pressure may be eliminated between the first two momentum equations by cross-differentiation to give:

\begin{equation*}\frac{\partial}{\partial t}\left(\frac{\partial v}{\partial x}-\frac{\partial u}{\partial y}\right)+2\Omega\left(\frac{\partial u}{\partial x}+\frac{\partial v}{\partial y}\right)=0.
\end{equation*}

The first term  in this is the time derivative of the vorticity, and the second term can be simplified using the mass equation to finally obtain
\begin{equation}\frac{\partial \omega}{\partial t}=2\Omega \frac{\partial w}{\partial z}\end{equation}

### More dead

The result given in {numref}`bucket-exercise` can be rearranged to obtain an expression for the pressure at each point in the fluid:

\begin{equation}p=p_0+\rho g z - \frac{\rho \omega^2}{2}r^2, \qquad r^2=x^2+y^2\end{equation}

The radial pressure gradient is found to be $\frac{\partial p}{\partial r}=\rho\omega^2 r$, which varies linearly towards the centre. This pressure gradient balances the centrifugal acceleration so that the streamlines remain circular.

## Shallow water results
The shallow water dispersion relation is given by
\begin{equation}c^2=gh\end{equation}
The result implies that the peak of a wave will travel faster than the base of the wave, which leads to steepening of the wave profile and ultimately wave breaking, which occurs near to the shoreline. Notice that in shallow water the result for the phase-velocity does not depend on the wavelength. Shallow-water gravity waves are non-dispersive.

## Exercises
4. For deep water waves:
(a) Calculate the total energy (per unit length in the $y$-direction) in one wavelength:
\begin{equation}E=\frac{1}{2}\rho\int_{x_0}^{x_0+\lambda}\int_{-\infty}^0|\nabla\phi|^2\mathrm{d}z\mathrm{d}x+\int_{x_0}^{x_0+\lambda}\int_0^{\eta}\rho g z\mathrm{d}z\mathrm{d}x.\end{equation}
Deduce that the average wave energy per unit length in the $x$-direction is $\bar{E}=\frac{1}{2}\rho g A^2$, where $A$ is the amplitude of the free surface displacement.
(b) From the linearised unsteady Bernoulli equation, the pressure perturbation caused by the presence of the waves is $p_1=-\rho \frac{\partial \phi}{\partial t}$. The rate at which those pressure perturbations do work on a unit element dy in the direction dx is given by $p_1\frac{\mathrm{d}x}{\mathrm{d}t}\mathrm{d}y$. Therefore, the average rate at which energy is transferred across a vertical section of the fluid is given by
\begin{equation}\bar{P}=\frac{1}{\lambda}\int_{x_0}^{x_0+\lambda}\int_{z=-\infty}^{z=0} p_1 u\mathrm{d}z\mathrm{d}x=-\frac{\rho}{\lambda}\int_{x_0}^{x_0+\lambda}\int_{z=-\infty}^{z=0} \frac{\partial \phi}{\partial t}\frac{\partial \phi}{\partial x}\mathrm{d}z\mathrm{d}x.\end{equation}
 Calculate this integral, and show that $\bar{P}=\bar{E} c_g$, where $c_g$ is the group velocity. The result implies that energy is transported at the group velocity.
