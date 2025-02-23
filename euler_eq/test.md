---
author:
- Wojciech Sadowski
title: "Notes: Euler equations & linear hyperbolic systems"
---

# Euler equations

The Euler equations in conservative differential form (strong form):

$$\begin{split}
    &\pdv{\rho}{t} + \pdv{\rho u_i}{x_i} = 0,\\
    &\pdv{\rho u_i}{t} + \pdv{\rho u_i u_j}{x_j} 
      = -\pdv{p}{x_i} + f_i,\\
    &\pdv{\rho E}{t} + \pdv{\rho E u_j}{x_j} 
      =  -\pdv{u_i p}{x_i} + \rho f_i u_i + Q
  \end{split}
  \label{eq:euler}

$$


In the integral (weak) form (the integrals taken in some volume $V$ with
boundary $S$): 

$$
\begin{split}
    &\pdv{}{t}\int\limits_V \rho dd V 
      + \oint\limits_S\rho u_i n_i dd S = 0,\\
    &\pdv{}{t}\int\limits_V \rho u_i dd V 
      + \oint\limits_S ( \rho u_i u_j n_j + p n_i) dd S
      = \int\limits_V f_i dd V,\\
    &\pdv{}{t}\int\limits_V \rho E dd V 
      + \oint\limits_S (\rho E + p)  u_j n_j dd S
      = \int\limits_V ( Q + \rho f_i u_i) dd V
  \end{split}
  \label{eq:euler-integral}

$$
 We have four unknowns $\rho, \bm{u}, E, p$
(we assume that $f = Q = 0$ or are known) but we have only three
equations. For an ideal gas, we can write: 

$$
p = \rho e (\gamma - 1) 
  \rightarrow 
  e = \frac{p}{\rho (\gamma - 1)},

$$
 where
$\gamma = c_p / c_v = 1.4$. Total energy $E$ is equal to
$E = e + \bm{u}\cdot\bm{u}/2$.

Introducing the vector of conservative variables $\mathcal{U}$

$$\mathcal{U} = \left[
    \begin{array}{c}
      \rho\\
      \rho \bm{u}\\
      \rho E
    \end{array} \right],

$$
 the advective flux $\mathcal{F}_\mathrm{adv}$

$$\mathcal{F}_\mathrm{adv} = \left[
    \begin{array}{c}
      \rho \bm{u}\\
      \rho \bm{u}\otimes\bm{u} + p \bm{I}\\
      (\rho E  + p) \bm{u}
    \end{array} \right],

$$
 and sources $\mathcal{Q}$

$$\mathcal{Q} = \left[
    \begin{array}{c}
      0\\
      \bm{f}\\
      Q + \rho \bm{u}\cdot\bm{f}
    \end{array} \right],

$$
 we can write both in symbolic form

$$\pdv{\mathcal{U}}{t} + ddiv\mathcal{F}_\mathrm{adv} = \mathcal{Q},

$$

or 

$$
\pdv{}{t} \int\limits_V \mathcal{U} dd V 
  + \oint\limits_S \mathcal{F}_\mathrm{adv}\cdot \bm{n} dd S
  = \int\limits_V \mathcal{Q} dd V.

$$


# Euler equations in 1D


$$\begin{split}
    &\pdv{\rho}{t} + \pdv{\rho u}{x} = 0,\\
    &\pdv{\rho u}{t} + \pdv{\rho u^2}{x} 
      = -\pdv{p}{x} ,\\
    &\pdv{\rho E}{t} + \pdv{\rho E u}{x} 
      =  -\pdv{up}{x} 
  \end{split}
  \label{eq:euler1d}

$$


Introducing the vector of conservative variables $\mathcal{U}$

$$\mathcal{U} = \left[
    \begin{array}{c}
      \rho\\
      \rho u\\
      \rho E
    \end{array} \right],

$$
 the advective flux $\mathcal{F}_\mathrm{adv}$

$$\mathcal{F}_\mathrm{adv}(\mathcal{U}) = \left[
    \begin{array}{c}
      \rho u\\
      \rho u^2 + p \\
      (\rho E  + p) u
    \end{array} \right],

$$
 we can write both in symbolic form

$$\pdv{\mathcal{U}}{t} + \pdv{\mathcal{F}_\mathrm{adv}(\mathcal{U})}{x} 
  = 0.

$$


# Quasi-linear form

Using the chain rule, we can linearize each of the equations. The mass
conservation 

$$
\begin{split}
    \pdv{\rho}{t} + \pdv{\mathcal{F}_\mathrm{adv}^\rho(\mathcal{U})}{x} 
    &= \pdv{\rho}{t} 
    + \pdv{\mathcal{F}_\mathrm{adv}^\rho(\mathcal{U})}{\mathcal{U}}\pdv{\mathcal{U}}{x}\\
    &= \pdv{\rho}{t} + \pdv{\mathcal{F}_\mathrm{adv}^\rho}{\rho}\pdv{\rho}{x} 
    + \pdv{\mathcal{F}_\mathrm{adv}^\rho}{\rho u}\pdv{\rho u}{x} 
    + \pdv{\mathcal{F}_\mathrm{adv}^\rho}{\rho E}\pdv{\rho E}{x} \\
    &= \pdv{\rho}{t} + (1)\pdv{\rho u}{x} = 0
  \end{split}

$$


For momentum 

$$
\begin{split}
    \mathcal{F}_\mathrm{adv}^{\rho u} 
    &= \rho u^2 + p = \rho u^2 + (\gamma-1)\rho e 
    =  \rho u^2 + (\gamma-1)\rho (E - u^2/2) \\
    &= \frac{\mathcal{U}_2^2}{\mathcal{U}_1} + (\gamma - 1)(\mathcal{U}_3 - \frac{\mathcal{U}_2^2}{2\mathcal{U}_1} )
    = (3-\gamma)\frac{\mathcal{U}_2^2}{2\mathcal{U}_1}  +(\gamma - 1)\mathcal{U}_3\\
    &= (3-\gamma)\frac{{(\rho u)}^2}{\rho} + (\gamma - 1)\rho E   
  \end{split}

$$
 so 

$$
\begin{split}
    \pdv{\rho u }{t} &+ \pdv{\mathcal{F}_\mathrm{adv}^{\rho u}(\mathcal{U})}{x} 
    = \pdv{\rho u}{t} + \pdv{\mathcal{F}_\mathrm{adv}^{\rho u}(\mathcal{U})}{\mathcal{U}}\pdv{\mathcal{U}}{x} \\
    &=  \pdv{\rho u}{t} 
    + \pdv{\mathcal{F}_\mathrm{adv}^{\rho u}}{\rho }\pdv{\rho }{x} 
    + \pdv{\mathcal{F}_\mathrm{adv}^{\rho u}}{\rho u}\pdv{\rho u}{x} 
    + \pdv{\mathcal{F}_\mathrm{adv}^{\rho u}}{\rho E}\pdv{\rho E}{x} \\
    &=  \pdv{\rho u}{t} 
    + \frac{ \gamma - 3 }{2} \frac{{(\rho u)}^2}{\rho^2} \pdv{\rho }{x} 
    + [\frac{2\rho u }{\rho} - (\gamma -1)\frac{\rho u}{\rho} ]\pdv{\rho u}{x} + (\gamma - 1)\pdv{\rho E}{x}\\
    & = \pdv{\rho u}{t} + \frac{ \gamma - 3 }{2}u^2\pdv{\rho }{x} 
    + (3 - \gamma)u\pdv{\rho u}{x}
    + (\gamma - 1 )\pdv{\rho E}{x}
    = 0
  \end{split}

$$
 For energy 

$$
\begin{split}
    \mathcal{F}_\mathrm{adv}^{\rho E} 
    &= \rho u E + p u = \rho u E + (\gamma-1)\rho e u
    = \rho u E + (\gamma-1)\rho(E - u^2/2)u \\
    &= \rho u E + (\gamma - 1 )\rho u E -(\gamma -1)\rho u^3/2
    = \gamma\rho u E -\frac{\gamma-1}{2} \rho u^3\\
    &= \gamma\frac{(\rho u)(\rho E)}{\rho} -\frac{\gamma-1}{2}\frac{{(\rho u)}^3}{\rho^2}
  \end{split}

$$
 so 

$$
\begin{split}
    \pdv{\rho E }{t} &+ \pdv{\mathcal{F}_\mathrm{adv}^{\rho E}(\mathcal{U})}{x} 
    = \pdv{\rho E}{t} + \pdv{\mathcal{F}_\mathrm{adv}^{\rho E}(\mathcal{U})}{\mathcal{U}}\pdv{\mathcal{U}}{x} \\
    &=  \pdv{\rho E}{t} 
    + \pdv{\mathcal{F}_\mathrm{adv}^{\rho E}}{\rho }\pdv{\rho }{x} 
    + \pdv{\mathcal{F}_\mathrm{adv}^{\rho E}}{\rho u}\pdv{\rho u}{x} 
    + \pdv{\mathcal{F}_\mathrm{adv}^{\rho E}}{\rho E}\pdv{\rho E}{x} \\
    &=  \pdv{\rho E}{t} 
    + [-\gamma\frac{(\rho u)(\rho E)}{\rho^2} + (\gamma-1)\frac{{(\rho u)}^3}{\rho^3} ]\pdv{\rho}{x} \\
    &+ [\gamma\frac{\rho E}{\rho} - \frac{3}{2}(\gamma-1)\frac{{(\rho u)}^2}{\rho^2}]\pdv{\rho u}{x} 
    + \gamma\frac{\rho u}{\rho} \pdv{\rho E}{\rho} \\
    &=  \pdv{\rho E}{t} + [(\gamma -1)u^3-\gamma u E ]\pdv{\rho}{x}
    + [\gamma E - \frac{3}{2}(\gamma -1)u^2]\pdv{\rho u}{x}
    + \gamma u\pdv{\rho E}{\rho}
  \end{split}

$$
 All of this hard work, let us express our system of
equations as

$$\pdv{\mathcal{U}}{t} + \mathcal{A}(\mathcal{U})\pdv{\mathcal{U}}{x} = \bm{0}

$$

or 

$$
\pdv{}{t}\left[
    \begin{array}{c}
      \rho\\
      \rho \bm{u}\\
      \rho E
    \end{array} \right] +
    [\begin{array}{ccc}
      \pdv{\mathcal{F}_\mathrm{adv}^\rho}/{\rho}
      & \pdv{\mathcal{F}_\mathrm{adv}^\rho}/{\rho u}
      & \pdv{\mathcal{F}_\mathrm{adv}^\rho}/{\rho E} \\
      \pdv{\mathcal{F}_\mathrm{adv}^{\rho u}}/{\rho }
      & \pdv{\mathcal{F}_\mathrm{adv}^{\rho u}}/{\rho u}
      & \pdv{\mathcal{F}_\mathrm{adv}^{\rho u}}/{\rho E} \\
      \pdv{\mathcal{F}_\mathrm{adv}^{\rho E}}/{\rho } 
      & \pdv{\mathcal{F}_\mathrm{adv}^{\rho E}}/{\rho u}
      & \pdv{\mathcal{F}_\mathrm{adv}^{\rho E}}/{\rho E}
    \end{array}]
    \left[
   \begin{array}{c}
      \pdv{\rho}/{x}\\
      \pdv{\rho u}/{x}\\
      \pdv{\rho E}/{x}
    \end{array} \right]
  = \bm{0}.

$$


The matrix $\mathcal{A}$ 

$$
\mathcal{A}(\mathcal{U}) =  \left[
    \begin{array}{ccc}
      0 & 1 & 0 \\
      ddfrac{\gamma -3}{2}u^2 & (3 - \gamma)u & \gamma - 1\\
      -\gamma u E + (\gamma -1)u^3 & \gamma E - ddfrac{3(\gamma -1)}{2}u^2 & \gamma u
    \end{array} \right]

$$
 is the Jacobian of the system of equations.
This is the non-conservative form of the Euler equations. Based on
$\mathcal{A}$ it can be proven that Euler equations are in fact
hyperbolic ($\mathcal{A}$ has real eigenvalues and independent
eigenvectors).

# Primitive variables

In the similar manner we can get the primitive form, i.e., expressed
using the primitive variables $\mathcal{P}$: 

$$
\mathcal{P}= \left[
    \begin{array}{c}
      \rho\\
      u \\
      p
    \end{array}
  \right].

$$
 We can simply make a change of variables using the chain
rule,

$$\pdv{\mathcal{U}}{t} = \pdv{\mathcal{U}}{\mathcal{P}}\pdv{\mathcal{P}}{t} = 
  [
    \begin{array}{ccc}
      \pdv{\rho  }/{\rho} & \pdv{\rho  }/{u} & \pdv{\rho  }/{p}\\
      \pdv{\rho u}/{\rho} & \pdv{\rho u}/{u} & \pdv{\rho u}/{p}\\
      \pdv{\rho E}/{\rho} & \pdv{\rho E}/{u} & \pdv{\rho E}/{p}
    \end{array}
  ] \pdv{\mathcal{P}}{t} = \mathcal{K}\pdv{\mathcal{P}}{t}

$$
 We only
need to clarify the transformation of energy into pressure

$$\rho E = \rho e + \rho u^2/2 = \frac{p}{\gamma -1 } + \rho u^2/2,

$$

From that we have

$$\pdv{\rho E}{\rho} = \pdv{}{\rho}(\frac{p}{\gamma -1 } + \rho u^2/2)
  = \frac{u^2}{2},

$$


$$\pdv{\rho E}{u} = \pdv{}{u}(\frac{p}{\gamma -1 } + \rho u^2/2)
  = \rho u,

$$
 and finally

$$\pdv{\rho E}{p} = \pdv{}{p}(\frac{p}{\gamma -1 } + \rho u^2/2)
  = \frac{1}{\gamma -1}.

$$


The Jacobian of variable change $\pdv{\mathcal{U}}/{\mathcal{P}}$ can be
easily computed 

$$
\pdv{\mathcal{U}}{\mathcal{P}} = 
  [
    \begin{array}{ccc}
      1 & 0 & 0\\
      u & \rho & 0\\
      u^2/2 & \rho u & 1/(\gamma -1)
    \end{array}
  ]

$$
 and inserted into our original equation:

$$\mathcal{K}\pdv{\mathcal{P}}{t} + \mathcal{A}(\mathcal{U})\mathcal{K}\pdv{\mathcal{P}}{x} = \bm{0}.

$$

Is $\mathcal{K}$ invertible? It is a lower triangular matrix so

$$ddet \mathcal{K}= \frac{\rho}{\gamma - 1} > 0

$$
 and

$$\mathcal{K}^{-1} = [
    \begin{array}{ccc}
      1 & 0 & 0\\
      -u/\rho & 1/\rho & 0\\
      (\gamma -1)u^2/2 & u(1 - \gamma)& (\gamma -1)
    \end{array}
  ]

$$
 We know that $\mathcal{K}^{-1}\mathcal{K}= \bm{I}$, so we can
multiply the equations from left side by $\mathcal{K}^{-1}$ and get the
following form:

$$\pdv{\mathcal{P}}{t} + \mathcal{K}^{-1}\mathcal{A}(\mathcal{U})\mathcal{K}\pdv{\mathcal{P}}{x} = \bm{0}.

$$

The matrix
$\mathcal{A}(\mathcal{P}) = \mathcal{K}^{-1}\mathcal{A}(\mathcal{U})\mathcal{K}$
is given as[^1] 

$$
\mathcal{A}(\mathcal{P}) = [
    \begin{array}{ccc}
      u & \rho & 0\\
      0 & u & 1/\rho\\
      0 & \rho a^2 & u
    \end{array}
  ],

$$
 where $a = \sqrt{\gamma p /\rho}$ is the speed of sound. The
matrix form can be expanded to 

$$
\begin{split} 
    \pdv{\rho}{t} &+ u\pdv{\rho}{x} + \rho\pdv{u}{x} = 0\\
    \pdv{u}{t}    &+ u\pdv{u}{x} + \frac{1}{\rho}\pdv{p}{x} = 0 \\
    \pdv{p}{t}    &+ \rho a^2 \pdv{u}{x} + u\pdv{p}{x} = 0.
  \end{split}

$$


## Entropy equation

If we consider entropy $S = p/\rho^\gamma$ we can compute

$$\pdv{S}{t} = \frac{1}{\rho^\gamma}\pdv{p}{t} + \pdv{\rho^{-\gamma}}{t}p 
  = \frac{1}{\rho^\gamma}\pdv{p}{t} - \gamma p \rho^{-\gamma - 1}\pdv{\rho}{t}
  = \frac{1}{\rho^\gamma}(\pdv{p}{t} - \frac{\gamma p}{\rho}\pdv{\rho}{t})

$$

which can be further simplified using the speed of sound and and
equation in the primitive form and substitute the substantial
derivatives: 

$$
\begin{split}
    \frac{1}{\rho^\gamma}(\pdv{p}{t} - a^2\pdv{\rho}{t})
    & = \frac{1}{\rho^\gamma}[-\rho a^2 \pdv{u}{x} - u\pdv{p}{x} + a^2(u\pdv{\rho}{x} + \rho\pdv{u}{x}) ]\\
    & = \frac{-u}{\rho^\gamma}( \pdv{p}{x} - a^2\pdv{\rho}{x} ) = -u\pdv{S}{x}
  \end{split}

$$
 Equating one to the other gives us the equation for
entropy that is valid in smooth regions of the flow

$$\pdv{S}{t} + u\pdv{S}{x} = \mdv{S}{t}=0,

$$
 which implies that entropy
remains constant along the flow paths.

# General linear system

A general linear system is given as

$$\pdv{\bm{u}}{t} + \bm{A}\pdv{\bm{u}}{x} = \bm{0}, \quad \bm{u} = {[u_1 ddots u_n]}^T,

$$

where the flux Jacobian $\bm{A}$ is constant, has $n$ distinct real
eigenvalues $\lambda_i$ and $n$ linearly independent eigenvectors
$\bm{k}_i$.

## Diagonalization

If we solve the eigenvalue problem $\bm{A}\bm{k}
-\lambda\bm{k} =\bm{0}$, we can create a matrix
$\bm{K}=[\bm{k}_1 ddots
\bm{k}_n]$. Then the coefficient matrix $\bm{A}$ can be expressed as

$$\bm{A} = \bm{K}\bm{\Lambda}\bm{K}^{-1},\quad 
  \bm{\Lambda} = [
    \begin{array}{ccc} 
      \lambda_1 &        & \\
               & dddots & \\
               &        &  \lambda_n
    \end{array}].

$$


## Characteristic variables

We can also introduce new set of variables $\bm{w} = \bm{K}\bm{u}$, and
substitute it into our equation leading to

$$\pdv{\bm{w}}{t} + \bm{\Lambda}\pdv{\bm{w}}{x} = \bm{0}.

$$
 This is a
decoupled system![^2] We also see, that $\bm{w}_i$ is the coefficient of
$i$-th eigenvector when $\bm{u}$ is represented in the basis of
eigenvectors

$$\bm{u}(x,t) = \bm{K}\bm{w} = [\bm{k}_1 ddots \bm{k}_n]{[w_1 ddots w_n]}^T=
  \sum\limits_i^n w_i(x,t)\bm{k}_i

$$
 If we know the initial condition to
$\bm{u} = \bm{u}^{(0)}$, we can transform it as well, and then solve
each of the equations separately using the method of characteristics:

$$\bm{u}(x,t) = \sum\limits_i^n w^{(0)}_i(x-\lambda_i t)\bm{k}_i.

$$


[^1]: Check that and send it to me!

[^2]: $\bm\Lambda$ is diagonal.
