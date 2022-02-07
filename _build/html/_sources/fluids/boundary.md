# Asymptotic analysis

EARLY DRAFT: UNDER CONSTRUCTION

## Stokes' paradox
Consider a cylinder placed into an oncoming highly viscous 2D fluid flow of velocity $U$, as shown in the image below. This type of flow is known as Hele-Shaw flow.
<br>

```{image} navstok_img/hele-shaw.png
---
name: Hele-Shaw
alt: Hele-Shaw
align: center
scale: 80%
---
```
<br>

If we define the following ratio, where $a$ is the diameter of the cylinder, then the effect of inertia will apparently be negligible near to the cylinder:

\begin{equation}\mathrm{Re}=\frac{Ua}{\nu}.\end{equation}

However, away from the boundary the characteristic length scale associated with changes in velocity is larger, as the flow becomes more and more uniform. Therefore the effects of inertia are more important in the outer flow regions. In fact, if the effects of inertia are neglected away from the surface of the sphere then the mathematical equations are ill-posed and it becomes impossible to satisfy appropriate boundary conditions for the far-field. This is known as Stokes' paradox.

The paradox can be resolved by taking a different approximation away from the boundary, that includes inertial terms; and blending or "matching" the expressions obtained from the inner and outer layers of fluid. The mathematics required to do this is known as matched asymptotics.

Within each layer, variables in the full non-dimensional NS equations are related to powers of the $\mathrm{Re}$ by scaling arguments based on physical assumptions, such as the distance to a boundary. The different scalings used in each layer result in the balancing of different physical effects in the equations.

We will not study the techniques of matched asymptotics as it is a very involved subject, which is often first encountered in graduate level courses. Although the history of matched asymptotics is strongly associated with fluid dynamics, it has wide applications to areas including quantum mechanics.


## D'Alembert's paradox
Consider a cylinder placed into an oncoming flow, which is at high speed. Early experimenters and mathematicians did not have the techniques of high speed photography available to them, and there was disagreement about what happens at the fluid boundary. Many believed that fluid particles would "stick" to the boundary and transfer momentum, whilst others believed that the flow would move smoothly past the boundary.

Neither approach fitted well with the equations of motion. On one hand, transfer of momentum within the fluid requires viscosity, and it would be impossible to satisfy the no-slip condition at the boundary if these effects were neglected. On the other hand, it is plain from scaling arguments that for high speed flows of low viscosity fluid such as air the effects of viscosity should be much less important than inertia.

We will also see in {numref}`dalembert-paradox` that ignoring the no slip condition results in D’Alembert’s paradox of zero drag, and zero lift - meaning that aeroplanes would never fly!

The difficulty was eventually understood by Prandtl (1904), who reasoned for the existence of a narrow region called a boundary layer, in which the horizontal velocity increases rapidly in the direction away from the plate. In this region, viscous terms are comparable in magnitude to inertial terms, and act to decelerate the flow at the surface by diffusion of momentum. The viscous solution is then matched to the inviscid solution at the edge of the boundary layer to form a composite solution that is valid throughout the entire flow field. Matched asymptotics again!

An illustration of the concept of a boundary layer is provided below. The image comes from [this paper](https://doi.org/10.1063/1.2169443) about the history of boundary layer theory, which I think is written in a way that is fairly accessible to undergraduate physicists.

<br>

```{image} navstok_img/prandtl_bl.gif
---
name: shear_layer
alt: boundary layer
align: center
scale: 40%
---
```
<br>

## Transition to turbulence
A key feature of interest to mathematicians and engineers is the development of models that can account for laminar-turbulent transition. A laminar flow is an orderly flow characterised by fluid layers moving smoothly past one another, whilst a turbulent state is characterised by disordered, chaotic motion occurring a "cascade" of length scales.

A good understanding of the features of the conditions that lead to turbulence could help with engineers learn to control transition. For an example discussion, see [this video [2:30-8:05]](https://www.youtube.com/watch?v=GMmNKUlXXDs). Sometimes the desire may be to facilitate turbulence, for instance as an efficient mechanism of heat transfer or a means of achieving liquid-jet breakup in fuel injection systems. Conversely, in aerodynamic applications turbulent skin-friction drag can be as much as ten times that of laminar flow at the same Reynolds number, and accounts for 50% of the total drag experienced by a subsonic aircraft. This means that any reduction in turbulence offers huge potential for fuel savings as well as reduction of greenhouse gases and other pollutants.

### Example: pipe flow

An example of laminar-turbulent transition is illustrated in [this video example](https://www.youtube.com/watch?v=CAM-ubZIdFg). In the experiment, fluid under carefully controlled conditions is ran through a pipe. Dye is injected into the flow to create streaklines and the speed of the fluid is gradually increased, which is seen to result in a turbulent state. The pipe flow experiment is a classic, which was studied by Osborne Reynolds. He conducted experiments similar to the one shown, with more rudimentary apparatus, and he also developed the mathematical theory of laminar-turbulent transition in pipe flows.

The mathematical theory begins by first solving the equations of motion for steady flow in a pipe $U(r)$, where $r$ is the radial coordinate. The flow velocity is found to follow a parabolic flow profile.

It is then assumed that the steady flow is subjected to some small amplitude disturbances (perturbations) in the manner
 \begin{equation}\underline{u}=(U(y),0,0)+\epsilon\hat{\underline{u}},\end{equation}

where $\epsilon$ is a small parameter and $\hat{\underline{u}}$ are motions of the sort you considered when you solved the wave equation. These additional terms represent tiny background fluid motions such as vibrations, or disturbances created at the point where dye is injected into the flow or where the fluid enters the pipe.

We solve the equations of motion for the combined motion and determine what happens to the amplitude of the waves. This is called a perturbation theory. We want to establish if the perturbations are amplified or damped, with assumption that amplified perturbations will eventually become large enough to trigger a nonlinear cascade (instability).

The results of the linear theory for pipe flow suggest that the flow should remain stable up to very large Reynolds numbers, meaning for flow speeds that are very fast. However, very carefully controlled experiments have indicated that a turbulent state in pipe flows occurs at much lower Reynolds numbers than what the linear theory predicts, suggesting that a nonlinear theory is required.
