# Introduction

Physics is supposed to be motivated by experiments. It is a science after all! However, since our universe is (on observable scales) 3D, we cannot base our investigation on any evidence. Instead, we'll take the laws of physics which have been rigorously proven for 3D, adjust them to apply to a 2D world in a way that I think is most sensible, and assess the consequences.

For that reason, what we're doing here is not really physics. It's not even unique; I might make different choices than you when it comes to shifting physical laws from 3D to 2D, and neither of us has to be right or wrong. Instead, we should view this blob as describing one _possible_ 2D universe. It is still useful as an example of what Flatland might look like, but not the only one.

## Going from 3D to 2D

To change a physical law from 2D to 3D, we will take the same approach in all cases. Let me first define the problem.

All of physics can be represented by variables and equations of motion. The variables control observables (e.g., the positions of planets orbiting the sun or the momentum and position operators of quantum mechanics) and the equations describe how the observables change over time (e.g., Newton's laws or the Scrodinger equation). 

The variables encode information about the dimension of space. For instance, a location $\bm r$ is a vector with three components, one for each dimension. So our first step will be change all three-dimensional variables to two-dimensional variables.<<This is a little more complicated than it might seem, because some equations of motions have cross products in them, and cross products don't work on 2D vectors. Examples are torque ($\bm tau = \bm r \times \bm F$), and the force experienced by a particle in a magnetic field (\bm F = q\bm v \times \bm B). Fortunately this will not be a problem for us because both $\bm B$ and $\bm \tau$ are derived from other, more fundamental variables which _can_ be truncated to two spatial dimensions.>> So much for that step.

Altering the equations of motion is a little harder. In 3D physics, all equations of motion can be written as 
~intro:eom
$$f(x(t), \dot x(t), \ddot x(t)) = 0$$
for a variable $x(t)$ which undergoes rate of change $dx/dt=\dot{x}(t)$ and acceleration $d^2 x/dt^2=\ddot{x}(t)$, and $f$ is some function. (See the [review of calculus]{introduction/calculus} if you don't recognize this notation.)<<This might be an unfamiliar form, and it may take some getting used to. As an example, notice that Newton's second law $F=ma$ is of this form, since $a=\ddot{x}$ by definition, and so we can write $F-m\ddot x = 0$)>>

The fact that the $d^3x/dt^3$ does not appear in equation [intro:eom] is not mathematically guaranteed; it is simply a fact we have observed in the last few centuries of physics research. One could argue that it is not an accident that this _third_ derivative of position is redundant for a _three_-dimensional universe, and that for a _two_-dimensional universe the _second_ derivative would be redundant. We do not accept this argument, however, because it would make our toy 2D universe so different from our universe that it would be hard to go much further.

Miraculously, all of the laws we observe in our universe can be derived from a given *Lagrange Density* via the *Principle of Least Action*. If you are curious how this works, see [this section]{introduction/lagrange}. To move these 3D laws to 2D, we will just keep the same Lagrange density (perhaps with a slight change) and re-derive the equations of motion.

## Resources for you

* [Review of linear algebra]{introduction/algebra}
* [Review of calculus]{introduction/calculus}

