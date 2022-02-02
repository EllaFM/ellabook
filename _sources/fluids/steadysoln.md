# Steady Euler solutions

In this section, we derive the steady flow profiles for some classic geometries. The incompressibility condition is the simplest equation to work with, and for these simple geometries it often shows one of the flow components to be zero, so always look at the incompressibility condition first. Then we write out the components in the conservation of momentum equations. The examples given here are all ones that can be solved by hand. Some other classic flow profiles that we do not study here can be found by series solution.

## Couette flow (flow driven by a moving boundary)
In this example, we consider the motion of fluid between two horizontal planes. The lower plane is held at rest and the upper plan is moved at speed $U$ as shown. We will assume that there is no pressure gradient in the horizontal direction, so that the flow is entirely driven by viscosity. We will assume that the flow is independent of $x$ so that $\underline{v}=(u(y),v(y),0)$.

```{image} navstok_img/couette.png
:name: couette flow
:alt: Couette flow
:align: center
:scale: 100%
```

The equations of motion are:
\begin{equation}\nabla.\underline{v}=0, \quad \underline{v}.\nabla\underline{v}=-\frac{1}{\rho}\nabla p +\nu \nabla^2\underline{v}.\end{equation}
It follows from the incompressibility condition that $v$ is constant, and since $v(0)=0$ this component must be identically zero everywhere, so the conservation of momentum equations simplify to:
\begin{equation}\frac{\mathrm{d}^2 u}{\mathrm{d}y^2}=0, \quad \frac{\mathrm{d} p}{\mathrm{d} y}=0.\end{equation}
The velocity solution satisfying the no-slip condition $u(0)=0$ and $u(h)=U$ is the linear profile:
\begin{equation}\underline{v}=\left(\frac{U}{h}y,0,0\right).\end{equation}
The shear stress is constant throughout the fluid. In the downstream direction \begin{equation}\mu\left(\frac{\partial u}{\partial y}+\frac{\partial v}{\partial x}\right)=\mu\frac{U}{h}.\end{equation}
It is also possible to solve the problem for an applied pressure gradient. For example if we take a constant pressure gradient $\frac{\partial p}{\partial x}=G$ then we obtain
\begin{equation}u=\frac{U}{h}y+\frac{G}{2\mu}y(h-y)\end{equation}

Steady flow under gravity down an inclined plane
In this example, we will consider gravity driven flow down an inclined plane, with a free surface at $y=h$, as shown. We will assume that the flow is independent of $x$ so that $\underline{v}=(u(y),v(y),0)$.

```{image} navstok_img/inclined_plane.png
:name: inclined plane
:alt: flow down an inclined plane
:align: center
:scale: 100%
```


The equations of motion are:
\begin{equation}\nabla.\underline{v}=0, \quad \underline{v}.\nabla\underline{v}=-\frac{1}{\rho}\nabla p +\underline{F}+\nu \nabla^2\underline{v}.\end{equation}
It follows from the incompressibility condition that $v$ is constant, and since $v(0)=0$ this component must be identically zero everywhere.
The conservation of momentum equations simplify to:
(1) $0 = -\frac{1}{\rho}\frac{\partial p}{\partial x}+ \frac{\partial^2 u}{\partial y^2}+g\sin(\alpha)$
(2) $0 = \frac{1}{\rho}\frac{\partial p}{\partial y} - g\cos(\alpha)$
By integrating (2) we obtain $p=-\rho g y \cos(\alpha)+f(x)$ and we can find $f(x)$ by applying an atmospheric pressure condition on the free surface:
\begin{equation}p(h)=p_0, \ \forall x \qquad \Rightarrow f(x)=p_0-\rho g h\cos(\alpha).\end{equation} Therefore the pressure is independent of $x$ and equation (1) reduces to
\begin{equation}\nu \frac{\mathrm{d}^2 u}{\mathrm{d}y^2}=-g\sin(\alpha)\end{equation}
The solution satisfying the no-slip condition $u(0)=0$ and free surface stress shear "no stress" condition $u'(h)=0$ is the parabolic profile:
\begin{equation}u=\frac{g}{2\nu}y(2h-y)\sin(\alpha)\end{equation}
The velocity flux is therefore
\begin{equation}Q=\int_0^h u\mathrm{d}y=\frac{gh^3}{3\nu}\sin(\alpha)\end{equation}

## Plane Poiseuille flow
In this example, we will consider flow between two parallel planes driven by a constant pressure gradient $\frac{\partial p}{\partial x}=-k$. We will assume that the flow is independent of $x$ so that $\underline{v}=(u(y),v(y),0)$.
\begin{equation}\frac{}{}\end{equation}

```{image} navstok_img/plane_poiseuille.png
:name: plane Poiseuille flow
:alt: plane Poiseuille flow
:align: center
:scale: 100%
```

The equations of motion are:
\begin{equation}\nabla.\underline{v}=0, \quad \underline{v}.\nabla\underline{v}=-\frac{1}{\rho}\nabla p +\underline{F}+\nu \nabla^2\underline{v}.\end{equation}
It follows from the incompressibility condition that $v$ is constant, and since $v(0)=0$ this component must be identically zero everywhere.
The conservation of momentum equations simplify to:
\begin{equation}\frac{\mathrm{d}^2 u}{\mathrm{d}y^2}=-\frac{k}{\mu}, \quad \frac{\partial p}{\partial y}=0.\end{equation}
The velocity solution satisfying the no-slip conditions $u(0)=0$ and $u(h)=0$ is the parabolic profile:
\begin{equation}\underline{v}=\left(\frac{k y}{2\mu}(h-y),0,0\right).\end{equation}
The mass flux is given by
\begin{equation}Q=\int_0^h \left(\frac{kyh}{2\mu}-\frac{ky^2}{2\mu}\right)\mathrm{d}y=\frac{kh^3}{12\mu}.\end{equation}


```{exercise} Poiseuille pipe flow
Viscous fluid flows along a pipe of circular cross-section $r=a$ under a constant pressure gradient
\begin{equation}P=-\frac{\mathrm{d}p}{\mathrm{d}z}\end{equation}
Show that the steady flow profile in cylindrical coordinate $(r,\theta, z)$ satisfies
\begin{equation}v_z=\frac{P}{4\mu}(a^2-r^2), \quad v_r=v_\theta=0.\end{equation}
Poiseuille flows are named after the physician who first studied the problem in connection with blood flow. Their instability at high Reynolds numbers constitutes one of the most important problems of fluid dynamics.

Hints:

You will need to work in cylindrical coordinates, taking $\underline{v}=(v_r,v_{\theta},v_z)$. The Navier-Stokes equations in cylindrical coordinates are give in the box below. It is clear from the flow geometry that $v_{\theta}=0$, and that $v_r,v_z$ are independent of $\theta$. You may also assume that $v_r,v_z$ are independent of the downstream position $z$. The incompressibility then shows that $v_r=0$. Only the third conservation of momentum equation is required.

Navier-Stokes in cylindrical coordinates
Conservation of momentum:
\begin{align}\frac{\partial v_r}{\partial t}+(\underline{v}.\nabla)v_r-\frac{v_{\theta}^2}{r} &=-\frac{1}{\rho}\frac{\partial p}{\partial r}+\nu\left(\nabla^2 v_r-\frac{v_r}{r^2}-\frac{2}{r^2}\frac{\partial v_{\theta}}{\partial \theta}\right)\\ \frac{\partial v_{\theta}}{\partial t}+(\underline{v}.\nabla)v_{\theta}+\frac{v_r v_{\theta}}{r}&=-\frac{1}{\rho r}\frac{\partial p}{\partial \theta}+\nu\left(\nabla^2v_{\theta}+\frac{2}{r^2}\frac{\partial v_r}{\partial \theta}-\frac{v_{\theta}}{r^2}\right)\\ \frac{\partial v_z}{\partial t}+(\underline{v}.\nabla)v_z&=-\frac{1}{\rho}\frac{\partial p}{\partial z}+\nu\nabla^2 v_z \end{align}
Incompressibility:
\begin{equation}\frac{1}{r}\frac{\partial}{\partial r}(r v_r)+\frac{1}{r}\frac{\partial v_{\theta}}{\partial \theta}+\frac{\partial v_z}{\partial z}=0\end{equation}
where
\begin{equation}\underline{v}.\nabla = v_r\frac{\partial}{\partial r}+\frac{v_{\theta}}{\partial \theta}+v_z\frac{\partial}{\partial z}\end{equation}
\begin{equation}\nabla^2=\frac{1}{r}\frac{\partial}{\partial r}\left(r\frac{\partial}{\partial r}\right)+\frac{1}{r^2}\frac{\partial^2}{\partial \theta^2}+\frac{\partial^2}{\partial z^2}\end{equation}
```
