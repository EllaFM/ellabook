---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.10.3
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Mathematical ideas

## What is a **field**?
A field is a map of a physical quantity at each point in space and time. You are probably already familiar with graphical representations of fields, in the form of weather maps showing temperature and wind velocity :

| Physical quantity      | Example notation | Type of field     |
| :---        |    :----:   |          ---: | ---: |
| Temperature | $\Phi(x,y,z,t)$       | Scalar (magnitude only)  |
| Wind velocity  | $\underline{v}(x,y,z,t)$        | Vector (magnitude and direction) |

Further examples of **scalar field** quantities are mass and pressure. A scalar field can be represented using a surface plot, or a contour plot (e.g. pressure isobars), or a colour/grayscale map. The example below shows a grayscale map of the scalar field defined by
\begin{equation}
\Phi(x,y)=x\ \mathrm{sinc}(x^2+y^2),\quad -3\leq x,y \leq 3.
\end{equation}

```{code-cell}
---
render:
  image:
    align: center
    alt: fun-fish
---
import matplotlib.pyplot as plt
import numpy as np
import matplotlib.cm as cm

x = np.linspace(-3., 3., 256)     #x coordinates arranged on [-3,3]
y = np.linspace(-3., 3., 256)     #y coordinates arranged on [-3,3]
X, Y = np.meshgrid(x, y)          #make the plot grid

Z = X * np.sinc(X ** 2 + Y ** 2)  #define the scalar field values at each point

# options to prettify the plot
fig,ax=plt.subplots(figsize=(5,5))
ax.set_title('A scalar field')
ax.axis([-3,3,-3,3])
ax.xaxis.set_ticks([]), ax.yaxis.set_ticks([])

# The "pcolormesh" function can be used to make a density plot.
ax.pcolormesh(X,Y,Z,shading='auto',cmap=cm.gray)
plt.show()
```

The most commonly encountered **vector field** quantities are velocity and force. A vector field can be represented using arrows, where the length of each arrow indicates the field strength at the point. The example below shows a plot of the vector field defined by
```{math}
:label: example_field
\underline{v}=(2x,-2y),\quad -2\leq x,y \leq 2.
```

```{code-cell}
---
render:
  image:
    align: center
---
x=np.linspace(-2, 2, 10) #x coordinates arranged on [-2,2]
y=np.linspace(-2, 2, 10) #y coordinates arranged on [-2,2]

X,Y = np.meshgrid(x, y) #make the plot grid
(U,V)=(2*X,-2*Y)        #define the vector field values at each point

# options to prettify the plot
fig,ax=plt.subplots(figsize=(5,5))
ax.set_title('A vector field')
ax.axis([-2,2,-2,2])
ax.xaxis.set_ticks([]), ax.yaxis.set_ticks([])

# The "quiver" function is used in Python to make a vector plot. It gets its name from the apparatus that
# an archer uses to carry their arrows.
ax.quiver(X,Y,U,V)
plt.show()
```

If you draw curves tangent to the arrows of a vector field, these are called "field lines". The plot below shows field line for the vector field given in the previous example, {eq}`example_field` . The field strength at each point is indicated by how close together the field lines are, assuming that the physical quantity being indicated by the field is *conserved*.

```{code-cell}
---
render:
  image:
    align: center
tags: [hide-input]
---
fig,ax=plt.subplots(figsize=(5,5))
ax.set_title('Field lines')
ax.axis([-2,2,-2,2])
ax.xaxis.set_ticks([])
ax.yaxis.set_ticks([])
#----------------------------------
start=[ #start points of selected field lines
    [-1.6,-2],[-1.1,-2],[-0.6,-2],[-0.1,-2],
    [+1.6,-2],[+1.1,-2],[+0.6,-2],[+0.1,-2],
    [-1.6,+2],[-1.1,+2],[-0.6,+2],[-0.1,+2],
    [+1.6,+2],[+1.1,+2],[+0.6,+2],[+0.1,+2]]
#----------------------------------

ax.streamplot(X,Y,U,V,start_points=start,density=10) # stream plot

plt.show()
```

In the case where the field under consideration represents velocity, the field lines are normally called "streamlines". In the sections below, we will discuss the difference between *streamlines*, *streaklines* and *particle paths*.

````{exercise}
:label: streamlinesq
Choosing a plot range that you think is suitable, produce both a vector plot and a streamline plot of the velocity field $\underline{v}=(2 y, 2 x,0)$. Describe the shape of the streamlines in words.
````

## Streamlines, streaklines, and particle paths

The terminology in this section is used to describe the motion of fluids. It is assumed that the flow velocity is represented by a field $\underline{v}(\underline{x},t)$. To illustrate the concepts, we will consider the following velocity field as an example:

```{math}
:label: examplev
\underline{v}=(1,-2te^{-t^2}).
```

Since the field used in this example has no spatial dependence, the streamlines are straight lines, with slope $-2t e^{-t^2}$. If we plot the streamlines at a particular time $t$, they indicate the instantaneous direction of motion of fluid particles at that time.  

However, since the flow velocity is time-dependent, the direction of the streamlines changes at each instant. Therefore the streamlines do not show the paths traced by each fluid particle, as demonstrated in the animation below.

In the animation, selected particles are tracked as they move through the flow. It can be seen that particles starting from the same point at different times generally do not follow the same trajectories. At each instant in time, the particles move tangent to the changing vector field.

In this example, the velocity approaches a constant value $(1,0)$ as $t$ increases. Since the evolved velocity field is "steady" (time-independent) the particle paths and streamlines for this flow eventually coincide.

<br>

```{image} navstok_img/particles.gif
---
name: particles
alt: alternative description
align: center
scale: 80%
---
```
<br>

### Particle paths
A particle path is the trajectory traced by a single particle of fluid starting at a given position $\underline{x_0}$. According to the definition of velocity, we can find these paths by solving the problem

\begin{equation}\frac{\mathrm{d}\underline{x}}{\mathrm{d}t}=\underline{v}(\underline{x},t), \quad \underline{x}(t_0)=\underline{x}_0.\end{equation}

**Example:**

Find the trajectories of particles in flow {eq}`examplev` at varying times $t_0$ from the point $\underline{x}_0=(1,1)$.

We can solve

\begin{equation}\frac{\mathrm{d}x}{\mathrm{d}t}=1, \quad \frac{\mathrm{d}y}{\mathrm{d}t}=-2te^{-t^2}, \quad x(t_0)=1,\ y(t_0)=1\end{equation}

to obtain

\begin{equation}\biggr(x,y\biggr)= \left(t-t_0+1,e^{-t^2}-e^{-t_0^2}+1\right).\end{equation}

````{exercise}
:label: ex-ppaths
Find the particle paths for the flow $\underline{v}=(\alpha,\beta t,0)$, where $\alpha, \beta$ are positive constants. Describe the shape of your solutions.
````

### Streamlines
A streamline is a curve that is parallel to the velocity field at a given, **fixed time** $t$ and passes through a given point $\underline{x}_0$. Streamlines can be thought of as snapshots of the velocity field.

If we parameterise the streamline by $\underline{x}(s)=(x(s),y(s)_,z(s))$, then we will have

\begin{equation}\frac{\mathrm{d}\underline{x}}{\mathrm{d}s}=\underline{v}(\underline{x},t), \quad \underline{x}(0)=\underline{x}_0 \quad \text{(constant $t$)}.\end{equation}

**Example:**

Find the streamlines of particles in flow {eq}`examplev` at varying times $t_0$ from the point $\underline{x}_0=(1,1)$.

### Some heading

Note that if the flow is not steady then the streamlines do NOT coincide with the particle paths, since each snapshot will look different.


### Streaklines
A streakline is the locus of all particles that have passed through a given point $\underline{x}_0$. This is what we see when we inject smoke or dye into a moving fluid. We can find streaklines by solving the particle path problem for a range of release times $t_0$. We may plot the result at a given time $t$.



The animation below shows a sequence of particles injected into the fluid at intervals. The dynamic vector field is also shown on the plot. Due to the changing vector field, the particles follow different trajectories depending on the time of release. The $(x,y)$ trajectory of a particle released at time $t_0$ is given above. The set of particles together define a streakline.

particle trajectories





The evolved velocity field is approximately steady, so after some time has elapsed the streaklines, pathlines and streamlines approximately coincide.

The following animation shows how the streakline for dye injected at $(1,1)$ evolves over the first five seconds. On the same plot the pathline for a particle released at $t=-$ is plotted. The animation was produced in Python.

streakline



Exercises



3. Consider a two-dimensional unsteady flow given by $\underline{v}=(3 x/t^2, -2 y/t^2,0)$.

(i) Show that the velocity field is irrotational and calculate its divergence.

(ii) Since the velocity field is irrotational, it can be derived from a potential $\phi(x,y)$. Find an expression for this function.

(iii) In which direction do the contours of the potential function $\phi$ lie in relation to the velocity field?

(iv) Calculate the equations of the streamlines and show that for this example the streamlines and particle paths are the same.



4. For the steady flow $\underline{v}=(2x,3y,-5z)$, compute the trajectories of particles starting on the ring $x=\cos(\theta)$, $y=\sin(\theta)$, $z=1$.

Show that the flow is both irrotational and solenoidal, and describe the motion of the fluid particles in words.

````{exercise}
:label: pot-fun
Some velocity fields, called *potential fields*, may be defined as the gradient of a scalar potential function $\phi(x,y,z)$. For example, the gravitational field $\underline{g}=(0,0,-g)$ can be made to satisfy $\underline{g}=\nabla\phi$ by taking $\phi=-gz$. You will learn about potential fields later in this course.

Consider a two-dimensional velocity field $\underline{v}=(u,v)$, which is defined by a potential function
```{math}
\phi=x e^{-x^2-y^2}.
```
Produce a vector plot of this field on the range $-2\leq x,y \leq 2$.
````
