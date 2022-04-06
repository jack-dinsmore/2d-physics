# Review of Lagrangian Mechanics

Lagrangian Mechanics is a method for deriving equations of motion from a simpler quantity known as the *Lagrange density*. It will turn out that, while equations of motion can be complicated, the Lagrange density usually turns out to be about as simple as it possibly could be given certain constraints, which makes it an attractive formulation for us to use.<<There are lots of other advantages to Lagrangian mechanics, such as Noether's theorem and the fact that Lagrangians don't use messy vectors. But these won't be relevant to us, so I leave that discussion to other authors.>>

Suppose we have some variable $x$ which evolves over time as a function $x(t)$ from time $t_0$ to $t_1$. This function is called a *path* (though note it's technically a path through time, not space). For every possible path, we define an *action* $S[x(t)]$ which is a number we use to label the path. This action is defined as 
~intro:lagrangian
$$S[x(t)] = \int_{t_0}^{t_1} dt\ L(x, \dot x, t)$$
where $L$ called the *Lagrangian* which controls all the physical properties of the system. We'll write $L$ explicitly later. The Lagrangian only a function of $x$ and $\dot x$ because if $\ddot x$ were included, then the associated equation of motion would include a $d^3 x /dt^3$ term (to see this requires [variational calculus]{introduction/variations}). As we discussed in [the introduction]{introduction/_toc}, this never happens in our Universe.

For now, you can think of action loosely as some kind of "total resistance" encountered over the path (though it's not electrical resistance). Then the form of equation [intro:lagrangian] makes more sense; we can think of $L$ as the "resistance"-per-time, so that the integral adds the "resistance" over the path to get the total.

## Principle of Least Action

To turn equation [intro:lagrangian] into an equation of motion in classical mechanics, we make a physical law: _the path that the particle follows is the path with the lowest action_. This is called the *Principle of Least Action*, and it's an intuitive statement if you're thinking of action as measuring some kind of "resistance". Say you're walking through a field. You might try to take a path that has the fewest brambles and the least mud &emdash; i.e., the one with the least resistance. <<Similarly, a ray of light travels through air, water, glass, and the boundaries between them by a similar property, where the true path minimizes the _time_ the ray spends in transit. This property of light (called Fermat's principle) was one of the motivators for the principle of least action.>>

Using an important equation known as the Euler-Lagrange equation, you can work out the equations of motion from the action.<<This equation is derived in [this section]]{introduction/variations}, in case you want to see it.>> You can think of this equation as one that takes $L$ from equation [intro:lagrangian] and turns it into an equation for $\ddot{x}$, which is an equation of motion.

Miraculously, all equations of motion can be derived from a specific definition of a Lagrangian. Even more amazing is that this Lagrangian is usually very simple, often the simplest it could possibly be while following some required properties which are discussed in the [section on symmetries]{lagrange:symmetries}.



## Example: Newtonian Mechanics

The Classical Lagrangian (i.e., the Lagrangian that reproduces Newtonian mechanics) is 
~lagrange:classical
$$L = K-V$$
where $K$ is the kinetic energy (think $m \dot x^2/2$, which is also written $p^2/(2m)$ where $p$ is the momentum) and $V$ is the potential energy. Note the minus sign! That means that even though $L$ has units of energy, it is not actually the total energy of the particle and is not conserved. 

Why? I've seen a few ways of justifying this formula, but none are very satisfying. One way is to prove that it reproduces Newton's second law $F=ma$. Another way is to calculate the action directly for some known path, like a ball falling in a vacuum, and prove that it's minimal. If you have seen special relativity, you might recognize the pattern of a term having to do with momentum ($K$) minus a term having to do with energy ($V$) as like the norm of a four-vector (which is a three-vector in 2D). But I don't know any other justifications.

As an example, for two particles acting under gravity, the Lagrangian is 
$$L=\frac{m_1\dot {\bm x}_1^2}{2}+\frac{m_2\dot {\bm x}_2^2}{2}+\frac{Gm_1m_2}{|\bm x_1-\bm x_2|}.$$
If a third particle is added, we add its kinetic energy as well, along with two potential energies (one for each of the two particles already in the system). In Newtonian mechanics, this formula would be represented as four $\bm F=m \bm a$ equations (two particles times two dimensions) instead of one, and if we add more particles, we quickly get much more complexity. This is a hint as to the benefit of Lagrangian mechanics.


## Lagrange density

The Lagrangian of equation [lagrange:classical] works very well for a few particles. But what about a large ensemble of particles very close together, like a fluid? In this case, we use a *Lagrangian density*. 

The first step is to promote our variable $x(t)$ from the previous section into an ensemble of variables, representing an ensemble of particles all over space. There are two ways to do this: one is to track each particle individually and write $x(t)$ for each. Another is to look at a fixed volume of space, which particles pass in and out of, and track the properties of the particles in the space. It will be much simpler to use the second option for our purposes. The next question is: what properties do we need to track?

Let's look at a small volume at position $x$. (Note, this $x$ is a position. It's a label which is constant, not a variable which evolves as a function of time). The particles within the volume have some velocity per unit volume $\bm v$ and mass density $\rho$ which we need to keep track of. They will also sometimes collide and push off each other, and we encode this interaction in another parameter called the pressure per unit volume $p$. Each of these is different at different positions $x$, so we label each by the value of $x$ and time $t$ we're looking at: $\bm v(x,t)$, $\rho(x, t)$, and $p(x, t)$.

These variables, which evolve as a function of time, are what we want equations of motion for. Equations of motion which will tell us how $\bm v$ evolves as a function of time at every position $x$. Variables of this time, which are defined at every position $x$, are called *fields*.

The Lagrange density $\mathcal{L}$ for some arbitrary field $\phi$ is
$$L = \int_\text{all space} d^3 x\ \mathcal{L}(\phi, \dot \phi, \nabla \phi, t).$$
If you have multiple fields, the extra fields and their derivatives are just added as arguments of $\mathcal{L}$. Note that since $\phi$ is now a function of position as well as time, we needed to include the position derivative $\nabla \phi$ as well as the time derivative $\dot \phi$. The volume integral is what makes this a Lagrange *density*. In the case of our fluid with its four fields, $\mathcal{L}$
$$L=\int_\text{all space} d^3 x\ \left(\frac{1}{2}\rho \bm v^2 - V(\rho, \dot \rho, p)\right)$$
where $V$ is a potential energy density.<<See [this link](https://www.jstor.org/stable/2397248?seq=6) if you want to see what $V$ actually is.>> See the similarity between this Lagrangian and equation [lagrangian:classical]? The first term is the kinetic energy per unit volume (kinetic energy density), and we that the potential energy is subtracted.

It will turn out that all the fundamental Lagrangians we look at will describe _fields_, not single variables like $x(t)$, which is why we bring up this density.

The action, written in terms of the Lagrange density, is
$$S = \int_{-\infty}^\infty dt \int_\text{all space} d^3x \ \mathcal{L} = \int_\text{spacetime} dt d^3 x\  \mathcal{L}.$$

### Lagrange density properties

We should point out a couple facts about $\mathcal{L}$ before moving on.

1. Suppose we introduce a four-vector $\tilde x$ (a three-vector in 2D) which has time in the zeroth component and position in the other components. (If you don't recognize four-vectors, see [this introduction]{gravity/sr}.) Then $dt d^3 x = d^4 \tilde x$ and $\phi(x, t) = \phi(\tilde x)$. Also, $\dot \phi$ and $\nabla \phi$ can be combined into $\partial_\mu \phi$. Thus,
$$S=\int_\text{spacetime} d^4 \tilde x\ \mathcal{L}(\phi, \partial_\mu \phi)$$
which is much simpler.
1. Multiple values of $\mathcal{L}$ lead to the same action. Specifically, you can add the divergence of some function $\partial_\nu f^\nu(\phi, \partial_\mu \phi)$ to the Lagrange density and it will not affect the action because the divergence theorem states that 
$$\int_\text{spacetime} d^4 \tilde x \ \partial_\nu f^\nu = \oint_\text{spacetime boundary} d^3 \tilde x\  n_\nu f^\nu$$
where $n_\nu$ is the normal vector to the spacetime boundary. But we usually have $f \rightarrow 0$ at the spacetime boundary, so this is just zero.


~lagrange:symmetries
## Symmetries of spacetime and how they constrain the action

### The Poincare Group

Let's assume, without any justification, that you can move the fields $\phi$ over spacetime and the equations of motion do not change. In practice, this is true. You can translate or rotate your frame of reference, which is equivalent to moving $\phi$ over spacetime, and the laws of physics do not change. But in this section we're interested in all possible ways that $\phi$ could move over spacetime, so that we can choose from a large set of possibilities for our new 2D theory.

If the laws of physics remain the same under such a transformation, then that the action must not change, because otherwise the minimum action would change and the path followed by particles would change.<<Strictly speaking, it is possible to change action without changing the location of minimum action; for example, we could multiply action by an overall constant, or only change the non-minimum parts of action. But we usually ignore this detail>> Such transformations which leave the actions invariant are called *symmetries of spacetime*

Let's call the transformed spacetime labels $\tilde y$. Then, by change of variables,
$$S = \int d^4 \tilde x\ \mathcal{L}(\phi(\tilde x), \partial_\mu \phi(\tilde x)) = \int d^4 \tilde y\ |J(\tilde y)|\mathcal{L}(\phi(\tilde y), \partial_\mu \phi(\tilde y))$$
where $J$ is Jacobian of the transformation. We did not write the limits of integration, which is common when the integral is taken over all spacetime like here. If $J$ depends on the coordinates, this transformation is very complicated. But if $J$ is constant (e.g., one), then we just see that the integral of the Lagrange density in old coordinates equal to the integral in new coordinates, which means the Lagrangians are equal up to a divergence by the divergence theorem.

Suppose the $\mathcal{L}$ we chose enforces this equality, so that this transformation $\tilde x \rightarrow \tilde y$ does indeed not change the equations of motion. Let's study the kinds of transformations in greater detail.

We can choose to look only at transformations which are very small and apply in a very small region of space, so that $\tilde y$ is near $\tilde x$. (We can build up larger transformations by making a series of small ones one after another.) Small transformations like this are infinitesimal and linear (see my [linear algebra review]{introduction/algebra}), so that they can be written as 
$$\tilde y^\mu = {A^\mu}_\nu \tilde x^\nu + b^\mu$$
using [Einstein summation convention]{gravity/sr}, where $A$ is near the identity and $b$ is small. The requirement that the Jacobian determinant is one is just $\det A=1$.<<Technically, it's just that $|\det A| = 1$. But $A$ is near the identity, which has determinant 1.>>

We quickly see that $b^\mu$ is allowed to be anything and $|J|$ will be unaffected. Therefore, if $\tilde x \rightarrow \tilde y=\tilde x^\mu + b^\mu$ is a symmetry of the action, then $\mathcal{L}$ must be invariant up to a total derivative under the transformation. Happily, this transformation by $b$ is a translation, which is in fact a symmetry of our Universe!

What about $A$? In general, we can decompose $A$ into a symmetric and antisymmetric part 
$${A^\mu}_\nu = \delta^\mu_\nu+\sigma^\mu_\nu+{\omega^\mu}_\nu=\Sigma\Omega=\Omega\Sigma$$
where $\sigma$ is an infinitesimal symmetric matrix, $\omega$ is anti-symmetric, and $\Sigma$ is the matrix $\Sigma^\mu_\nu=\delta^\mu_\nu+\sigma^\mu_\nu$, and ditto for $\Omega$. Both $\Sigma$ and $\Omega$ have determinant one, so that their eigenvalues (of which there are three because we are in 2 spatial dimensions plus one temporal dimension) multiply to one.

We want $A$ to be real, so that for every $\lambda \in \mathbb{C}$ which is an eigenvalue of $\Omega$, $\lambda^*$ is also an eigenvalue. It follows that $\Omega$ has eigenvalues 1, $\lambda$, and $\lambda^*$ with $|\lambda|=1$. These matrices are the rotations.

All the eigenvalues of $\Sigma$ are real because $\Sigma$ is Hermitian. If one of the eigenvalues is one, then the other two are $\lambda$ and $\lambda^{-1}$. Thus, $A$ will stretch vectors along one axis, squeeze them along another, and keep all those along the unity-eigenvector fixed. This is where the physical interpretation comes in. Suppose the unity-eigenvector points between the time and $x$ axes (meaning it is a speed, indicating how far a particle goes in how much time). Then a shift on any small vector or difference in vectors along this direction is preserved by this transformation. This is just a highly mathematical statement that the speed of light is constant in all reference frames.

We've seen then that the available spacetime symmetries are translations, $\Omega$, and $\Sigma$. In our Universe, however, only some of these are actual symmetries of the action. Physics appears to meticulously keep space and time separated; it never rotates or boosts a spatial unit vector into time. For that reason, the unity-eigenvector of $\Omega$ must point along the time unit axis, and the unity-eigenvector of $\Sigma$ must point between space and time. Together, the possible $\Omega$ and $\Sigma$ and their products are known as the Lorentz group, and combined with translations they are the Poincare group, which are the symmetries of spacetime.

### Constraints on Action

Translational and boost invariance each impose constraints on how $\mathcal{L}(\phi, \partial_\mu \phi, \tilde x)$ can depend on its arguments. First of all, translational invariance implies that the Lagrangian can be made not to depend on $\tilde x$, so we remove $\tilde x$. Boost invariance enforces that $\partial_\mu$ must be contracted with another three-vector so that the two transform like a scalar. One option is self-contraction:
$\partial_\mu \phi \partial^\mu \phi$ or a Laplacian: $\partial_\mu \partial^\mu \phi$, but the Dirac equation (as we will later see) uses $\gamma^\mu \partial_\mu \phi$ where $\gamma$ is a different three-vector.

Given these constraints on the action, the Lagrange density is often extremely simple. The free space classical Lagrangian, for instance (equation [lagrange:classical] without $V$) is $m \dot x^2/2$. Translation invariance prevents the appearance of $x$, and rotation invariance prevents the appearance of $\dot x$ alone. So $\dot x^2$ appears, and the rest is a constant which is specific to the system being studied.

## External Resources

* [Wikipedia entry on Lagrangian Mechanics](https://en.wikipedia.org/wiki/Lagrangian_mechanics)
* For a more advanced textbook on Classical Mechanics, which I learned from in college, try "Classical Mechanics" by Goldstein, Poole, and Safko.