# Non-dimensionalisation

EARLY DRAFT: UNDER CONSTRUCTION

We may introduce non-dimensional variables using a characteristic length scale $L$, velocity $U$, time $T$, pressure $P$ and body force $g$:

\begin{equation}\underline{x}_*=\frac{\underline{x}}{L}, \quad \underline{u}_*=\frac{\underline{u}}{U}, \quad t_*=\frac{t}{T}, \quad p_*=\frac{p}{P}, \quad \underline{F}_*=\frac{\underline{F}}{g}\end{equation}

Making these substitutions gives:

\begin{equation}\frac{L}{TU}\frac{\partial\underline{u}_*}{\partial t_*}+\underline{u_*}.\nabla_* \underline{u_*}=-\frac{P}{\rho U^2}\nabla p_* + \frac{\nu}{U L} \Delta_*\underline{u_*}+\frac{gL}{U^2}\underline{F}_*,\end{equation}

The following dimensionless parameters now appear in the normalized momentum equation:

| Name   | Value   | Measurement ratio   |
| --- | --- | --- |
| **Strouhal number** | $\mathrm{St}=\frac{L}{TU}$   | $~\frac{\text{local acceleration}}{\text{convective acceleration}}$ |
| **Reynolds number** | $\mathrm{Re}=\frac{UL}{\nu}$ | $~\frac{\text{inertia}}{\text{viscous effects}}$ |
| **Froude number**   | $\mathrm{Fr}=\frac{U^2}{gL}$ | $~\frac{\text{inertia}}{\text{body force}}$|

If any of these quantities is large/small then we may construct an approximate solution by neglecting relevant terms in the equation.






### Viscous flows

The body force was neglected and it was assumed that the scales of local acceleration, inertia and pressure are comparable so that the following non-dimensionalisations of time and velocity are sensible:

\begin{equation}p=\frac{p_*}{\rho U^2}, \quad t=\frac{U t_*}{L}.\end{equation}

We obtain the equation below. The asterisks can dropped, because from now on we will always work with dimensionless quantities:

\begin{equation}\frac{\partial\underline{u}}{\partial t}+\underline{u}.\nabla \underline{u}=-\nabla p + \mathrm{Re}^{-1} \nabla^2\underline{u}\end{equation}

The choice of characteristic length and velocity scales is somewhat arbitrary, but should be done to ensure that the physical quantities are $\mathcal{O}(1)$ or smaller. The characteristic length scale should be chosen as a typical distance over which the fluid velocity changes by an amount of order $U$.

Defining a characteristic length scale is not always easy, though fortunately practices have been established (at least for classical geometries) through years of study and enhanced understanding about flows. For instance, in the case of developed fluid flow through a pipe or channel the relevant characteristic length scale is the diameter of the enclosure. For unconfined flows, such as the flow of oncoming fluid over a flat plate it is more challenging to define a suitable length scale. We may, in that case, define the Reynolds number based on some fixed downstream reference distance from the leading edge of the plate that is applicable to the region of interest.




## Stub
Written out in full, these equations are

\begin{align}\frac{\partial u_x}{\partial t}+u_x\frac{\partial u_x}{\partial x}+u_y\frac{\partial u_x}{\partial y}+u_z\frac{\partial u_x}{\partial z}&=-\frac{\partial p}{\partial x}+\mathrm{Re}^{-1}\left(\frac{\partial^2 u_x}{\partial x^2}+\frac{\partial^2 u_x}{\partial y^2}+\frac{\partial^2 u_x}{\partial z^2}\right)\\\frac{\partial u_y}{\partial t}+u_x\frac{\partial u_y}{\partial x}+u_y\frac{\partial u_y}{\partial y}+u_z\frac{\partial u_y}{\partial z}&=-\frac{\partial p}{\partial y}+\mathrm{Re}^{-1}\left(\frac{\partial^2 u_y}{\partial x^2}+\frac{\partial^2 u_y}{\partial y^2}+\frac{\partial^2 u_y}{\partial z^2}\right)\\\frac{\partial u_z}{\partial t}+u_x\frac{\partial u_z}{\partial x}+u_y\frac{\partial u_z}{\partial y}+u_z\frac{\partial u_z}{\partial z}&=-\frac{\partial p}{\partial z}+\mathrm{Re}^{-1}\left(\frac{\partial^2 u_z}{\partial x^2}+\frac{\partial^2 u_z}{\partial y^2}+\frac{\partial^2 u_z}{\partial z^2}\right)\\\frac{\partial u_x}{\partial x}+\frac{\partial u_y}{\partial y}+\frac{\partial u_z}{\partial z}&=0\end{align} (fullnavstok)
