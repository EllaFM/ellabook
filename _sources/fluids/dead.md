# dead

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

### Dead: Almost uniform rotation

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
