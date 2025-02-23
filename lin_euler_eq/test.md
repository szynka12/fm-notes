---
author:
- Wojciech Sadowski
title: Linearized Euler equations
---

# Exercise: Euler equations for isothermal flow (Laney)

Show that for isothermal flow $T=\mathrm{const.}$, the Euler equations
can be written as $$\begin{split}
    &\pdv{\rho}{t} + \pdv{\rho u}{x} = 0\\
    &\pdv{\rho u}{t} + \pdv{}{x}\ab(\rho u^2 + \rho a^2) = 0
  \end{split}$$ where the speed of sound is given as
$$a^2 = {\ab(\odv{p}{\rho})}_T = RT.$$

## Solution

In general for ideal gas $$p = (\gamma - 1) \rho e,$$ and we know that
$e = c_v T$, with $c_v=\mathrm{const.}$, so
$$p = (\gamma - 1) \rho e = c_v(\gamma - 1)\rho T.$$ Now we need to
simplify the term with pressure in the momentum equation:
$$\pdv{p}{x_i} = \pdv{}{x_i}\ab[ c_v(\gamma - 1)\rho T] = 
  c_v(\gamma - 1)T\pdv{\rho}{x_i} = {\ab(\odv{p}{\rho})}_T\pdv{\rho}{x_i}
  = \pdv{\rho a^2}{x_i}$$ We can rearrange the momentum equation to get
$$\pdv{\rho u}{t} + \pdv{}{x}\ab(\rho u^2 + \rho a^2) = 0.$$ The last
thing: the energy equation:
$$\pdv{\rho E}{t} + \pdv{\rho E u_j}{x_j}  =  -\pdv{p u_i}{x_i},$$ Let's
first simplify the tight side
$$\rho \mdv{E}{t} = \rho \mdv{}{t}\ab(c_v T + \frac{u^2}{2}) + 
 \rho \ab( \mdv{c_v T}{t} + \mdv{u^2 /2}{t} ) =
 \rho\mdv{u^2/2}{t}$$ On the right,
$$-\pdv{p u_i}{x_i} = -\pdv{}{x_i}\ab[ c_v(\gamma - 1)\rho T u_i] = 
  -a^2\pdv{\rho u_i}{x_i} = a^2\pdv{\rho}{t},$$ so we end up with
$$\rho\mdv{u^2/2}{t} = a^2\pdv{\rho}{t}$$ which just means that the
change in density has to induce the change in kinetic every of the gas.
But we notice, that between, the equation of mass conservation and newly
derived momentum we have only two variables now. So we essentially
finished our exercise, and the total (or kinetic) energy is essentially
a quantity.

# Exercise: Linearized equations of gas dynamic

Provided, that the isothermal gas is moving with a uniform velocity
$u_0$ and a subject to small disturbance $u_\star$, has corresponding
reference density $\rho_0$ and the density $\rho_\star$ associated with
the flow disturbance, show that the linearized equation of gas dynamics
for this disturbance are $$\begin{split}
    &\pdv{\rho_\star}{t} + \pdv{\rho_0u_\star}{x} = 0\\
    &\pdv{u_\star}{t} + \pdv{}{x}\ab(\rho_\star\frac{a^2}{\rho_0}) = 0.
  \end{split}\label{eq:lin-eul}$$

## Informal way

We say $u = u_0+ u_\star$ and $\rho = \rho_0+ \rho_\star$ and substitute
here: $$\begin{split}
    &\pdv{\rho}{t} + \pdv{\rho u}{x} = 0\\
    &\pdv{\rho u}{t} + \pdv{}{x}\ab(\rho u^2 + \rho a^2) = 0
  \end{split}$$ so we have $$\begin{split}
    &\pdv{\rho_0+ \rho_\star}{t} + \pdv{\ab(\rho_0+ \rho_\star) \ab(u_0+ u_\star)}{x} = 0\\
    &\pdv{\ab(\rho_0+ \rho_\star) \ab(u_0+ u_\star)}{t} + \pdv{}{x}\ab(\ab(\rho_0+ \rho_\star) {\ab(u_0+ u_\star)}^2 + \ab(\rho_0+ \rho_\star) a^2) = 0,
  \end{split}$$ and we do algebra. For the mass conservation
$$\pdv{\rho_0}{t} + \pdv{\rho_\star}{t} + \pdv{\rho_0u_0}{x} + \pdv{\rho_0u_\star}{x} + \pdv{\rho_\star u_0}{x} + \pdv{\rho_\star u_\star}{x}= 0.$$
We can directly remove all the terms involving only the derivatives of
$\rho_0$ and $u_0$, so we are left with:
$$\pdv{\rho_\star}{t} + \pdv{\rho_0u_\star}{x} + \pdv{\rho_\star u_0}{x} + \pdv{\rho_\star u_\star}{x}= 0.$$
Since both $\rho_\star$ and $u_\star$ are disturbances, and we know that
they are small, we can simply neglect the last term on the left side, as
the product $\rho_\star u_\star$ will be small. So we are left with
$$\pdv{\rho_\star}{t} + \pdv{\rho_0u_\star}{x} + \pdv{\rho_\star u_0}{x} = 0.$$
The momentum equation will be more tedious. The time derivative we treat
in the same way
$$\pdv{\rho u}{t} = \pdv{\rho_\star u_0}{t} + \pdv{\rho_0u_\star}{t},$$
but the convection term is more of a mess,

::: fullwidth
$$\begin{split}
    \pdv{}{x}\ab(\rho u^2 + \rho a^2) = 
    \pdv{}{x}\ab( \rho_0u_0^2 + 2\rho_0u_0u_\star+ \rho_0u_\star^2  + \rho_\star u_0^2 + 2\rho_\star u_0u_\star+ \rho_\star u_\star^2 + \rho_0a^2 + \rho_\star a^2),
  \end{split}$$
:::

from which we remove all products of $\star$ quantities and all
derivatives of constant terms $$\pdv{}{x}\ab(\rho u^2 + \rho a^2) = 
  \pdv{}{x}\ab(  2\rho_0u_0u_\star+ \rho_\star u_0^2 + \rho_\star u_0^2  + \rho_\star a^2),$$
So we are left with
$$\pdv{\rho_\star u_0}{t} + \pdv{\rho_0u_\star}{t} + \pdv{}{x}\ab(  2\rho_0u_0u_\star+ \rho_\star u_0^2 + \rho_\star a^2) = 0.$$
Finally, we can make the following observation. If the fluid moves with
the uniform velocity $u_0$, we can write our equations in a coordinate
system moving with velocity equal to $u_0$. This will correspond to
setting $u_0=0$ in our equations![^1] We can introduce this to be left
with: $$\begin{split}
    &\pdv{\rho_\star}{t} + \pdv{\rho_0u_\star}{x} = 0\\
    &\pdv{\rho_0u_\star}{t} + \pdv{\rho_\star a^2}{x} = 0.
  \end{split}$$ To get the form from the problem statement, simply
divide the last equation by constant $\rho_0$.

## Formal way

Try it yourself:

1.  Write your equations as a vector valued function of $u_0$ and
    $\rho_0$,: $$\mathcal{F}(u_0, \rho_0) = \ab[
            \begin{array}{c}
              \pdv{\rho_0}/{t} + \pdv{\rho_0u_0}/{x} \\
              \pdv{\rho_0u_0}/{t} + \pdv{\ab(\rho_0u_0^2 +\rho_0a^2 )}/{x}
            \end{array}
          ]$$

2.  Linearize the equations by computing the generalized derivative
    $$\lim_{\epsilon \to 0} \frac{
            \mathcal{F}(u_0+ \epsilon u_\star, \rho_0+ \epsilon \rho_\star)
            - \mathcal{F}(u_0, \rho_0)}{\epsilon}.$$ This is the
    equation for a to your original equation, but it is parameterized by
    the reference values $u_0$ and $\rho_0$ that you haven't picked yet.

3.  Assume that the values are constant and $u_0=0$, to get the final
    solution.

For example for the continuity we will have: $$\begin{split}
    &\lim_{\epsilon \to 0}\frac{1}{\epsilon}\ab[
      \pdv{\rho_0+ \epsilon \rho_\star- \rho_0}{t} + \pdv{\rho_0u_0+ \epsilon\rho_0u_0+ \epsilon \rho_\star u_0+ \epsilon^2\rho_\star u_\star- \rho_0u_0}{x}]=\\
    &\lim_{\epsilon \to 0}\frac{1}{\epsilon}\ab[
      \pdv{ \epsilon \rho_\star}{t} + \pdv{ \epsilon\rho_0u_0+ \epsilon \rho_\star u_0+ \epsilon^2\rho_\star u_\star}{x}] =\\
    & \lim_{\epsilon \to 0}\pdv{ \rho_\star}{t} + \pdv{ \rho_0u_0+ \rho_\star u_0+ \epsilon\rho_\star u_\star}{x} =\pdv{ \rho_\star}{t} + \pdv{ \rho_0u_0+ \rho_\star u_0}{x}
  \end{split}$$

# Exercise: Compute the flux Jacobian of equation for flow disturbance

We are working with [\[eq:lin-eul\]](#eq:lin-eul){reference-type="ref"
reference="eq:lin-eul"}, written now in matrix form $$\pdv{}{t}
  \begin{bmatrix}
    \rho_\star\\ u_\star
  \end{bmatrix}
  + \pdv{}{x} \begin{bmatrix}
    \rho_0u_\star\\ a^2 \rho_\star/ \rho_0
  \end{bmatrix} = \bm{0}$$ The variables are $$\bm{U} = \begin{bmatrix}
    \rho_\star\\ u_\star
  \end{bmatrix}$$ and the flux function is: $$\bm{F} = \begin{bmatrix}
    \rho_0u_\star\\ a^2 \rho_\star/ \rho_0
  \end{bmatrix}$$ We know that we are looking for the form: $$\pdv{}{t}
  \begin{bmatrix}
    \rho_\star\\ u_\star
  \end{bmatrix}
  + \pdv{\bm{F}}{\bm{u}}\pdv{}{x} \begin{bmatrix}
    \rho_\star\\ u_\star
  \end{bmatrix} = \bm{0}$$ Which is given as
$$\pdv{\bm{F}}{\bm{u}}\pdv{}{x} = \begin{bmatrix}
    0         & \rho_0\\ 
    a^2 / \rho_0& 0
  \end{bmatrix}$$

# Exercise: Diagonalize the Jacobian

The eigenvalue problem is given as $$\bm{A}\bm{k} = \lambda \bm{k}$$
$$\bm{A}\bm{k} - \lambda \bm{k} = \bm{0}$$
$$\ab(\bm{A} - \lambda \bm{I})\bm{k} = \bm{0}$$ Equation has a non-zero
solution if and only if the determinant of the matrix
$\bm{A} - \lambda \bm{I}$ is zero.
$$\det \ab(\bm{A} - \lambda \bm{I}) =\det \begin{bmatrix}
    -\lambda        & \rho_0\\ 
    a^2 / \rho_0& -\lambda
  \end{bmatrix} = \lambda^2 - a^2 = \ab(\lambda - a)\ab(\lambda + a) = 0$$
The diagonal matrix is equal to $$\bm{\Lambda} = \begin{bmatrix}
    -a  & 0 \\ 
    0  & a
  \end{bmatrix}$$

# Exercise: Compute eigenvectors

$$\bm{A}\bm{k}^i = \lambda^i \bm{k}^i$$ or in full $$\begin{bmatrix}
    -\lambda^i & \rho_0\\ 
    a^2 / \rho_0& -\lambda^i
  \end{bmatrix}
  \begin{bmatrix}
    k^i_1\\ 
    k^i_2
  \end{bmatrix} = \bm{0}$$ so if we write the actual equations for
$\lambda = -a$ $$\begin{split}
    a k_1 + \rho_0k_2 &= 0  \stackrel{\times a/\rho_0}{\rightarrow}  a^2/\rho_0k_1 + a k_2 = 0 \\
    a^2/\rho_0k_1 + a k_2 &= 0
  \end{split}$$ The equations are identical, so we will look for
parametric solution. It is clear that the solution is of the form
$$k^1 = \alpha\begin{bmatrix}
    1\\ 
    -a/\rho_0
  \end{bmatrix}$$ where $\alpha$ is the parameter. The second vector
similarly is: $$k^2 = \alpha\begin{bmatrix}
    1\\ 
    a/\rho_0
  \end{bmatrix}$$ We can pick $\alpha = \rho_0$, so our vectors are:
$$k^1 = \begin{bmatrix}
    \rho_0\\ 
    -a
  \end{bmatrix},\quad
  k^2 = \begin{bmatrix}
    \rho_0\\ 
    a
  \end{bmatrix}.$$

# Exercise: Is the system hyperbolic?

Yes, real eigenvalues, two different eigenvectors.

# Exercise: Derive the characteristic form

# Exercise: Derive the initial condition in terms of characteristic variables

# Exercise: Derive the solution in terms of decoupled characteristics

# Exercise: Compute the solution in terms of original variables

[^1]: Euler equations should be invariant to Galilean coordinate change,
    prove it!
