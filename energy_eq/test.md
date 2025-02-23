---
author:
- Wojciech Sadowski
title: Different forms of the energy equation
---

# Conservation of mass and momentum

Mass conservation law can be expressed as[^1]
$$\pdv{\rho}{t} + \pdv{\rho u_i}{x_i} = 0.
  \label{eq:mass-conserv}$$ The first term denotes the change of density
in time in an infinitesimal volume element and the second describes the
change of density due to the flux of mass ($\rho\bm{u}$) through the
boundaries of the volume element.

Momentum equation can be expressed as[^2]
$$\pdv{\rho u_i}{t} + \pdv{\rho u_i u_j}{x_j} = -\pdv{p}{x_i} + \pdv{\sigma_{ij}}{x_j} + \rho f_i.
  \label{eq:momentum-conserv}$$

## Material derivative

The material derivative $\mdv{}/{t}$ of a variable $f(\bm{x}, t)$
convected with the fluid, is defined as
$$\mdv{f}{t} = \underbrace{\pdv{f}{t}}_{I} + \underbrace{u_i \pdv{f}{x_i}}_{II}$$
where the first term ($I$) describes the observed change of $f$ due to
*real* change of $f$ with time, whereas the second term denotes the
change due to the different value of $f$ convected with the flow field.
Consider the temperature rise as illustrated in
[\[fig:material\]](#fig:material){reference-type="ref"
reference="fig:material"}. The temperature observed in a point $\bm{x}$
in the lake with unmoving water can rise due to the heating of the sun.
This would correspond to $\pdv{T}/{t}$. If the water moves and the water
upstream is hotter, then it will also be ob observed as the rise of
temperature $T$ in point $\bm{x}$, which is expressed as
$u_i\pdv{T}/{x_i}$.

::: marginfigure
:::

We want to use the following formula to convert between the conservative
and non-conservative formulations of the equations: $$\rho \mdv{f}{t} 
  = \rho \ab(\pdv{f}{t} + u_i \pdv{f}{x_i})
  = \pdv{\rho f}{t} + \pdv{\rho u_i f}{x_i}.$$ We can quickly prove that
the forms are equivalent using the product rule and continuity equation
$$\pdv{\rho f}{t} + \pdv{\rho u_i f}{x_i} 
  = \rho\pdv{f}{t} + \pdv{\rho}{t}f + \rho u_i \pdv{f}{x_i} + \pdv{\rho u_i}{x_i}f=
  \rho\mdv{f}{t} + f\ab(\pdv{\rho}{t} + \pdv{\rho u_i}{x_i})$$ The last
term on the right is of course 0 due to
[\[eq:mass-conserv\]](#eq:mass-conserv){reference-type="ref"
reference="eq:mass-conserv"}.

# Kinetic energy equation

Kinetic energy $K$ is defined as[^3] $$K = \frac{1}{2}u_i u_i.$$ If we
take any derivative of $K$, here written as $\pdv{K}/{s}$, with
$s = x_i$ or $t$, we can notice something interesting:
$$\pdv{K(u_i(s, \ldots))}{s} = \pdv{K}{u_i}\pdv{u_i}{s} = \pdv{}{u_i}\ab(\frac{1}{2}u_i^2)\pdv{u_i}{s} = u_i \pdv{u_i}{s}.$$
We just computed the derivative using the chain rule,[^4] and we will
use the same method to derive the equation for $K$. If we multiply
[\[eq:momentum-conserv\]](#eq:momentum-conserv){reference-type="ref"
reference="eq:momentum-conserv"} with $u_i$
$$u_i\pdv{\rho u_i}{t} + u_i\pdv{\rho u_i u_j}{x_j} = -u_i\pdv{p}{x_i} + u_i\pdv{\sigma_{ij}}{x_j} + \rho u_i f_i,$$
we will lead to the same situation as above, i.e., a derivative of $u_i$
times $u_i$ itself. This can be simplified now, by working backwards:
$$\begin{split}
    u_i\pdv{\rho u_i}{t} + u_i\pdv{\rho u_i u_j}{x_j} &= 
    u_i u_i\pdv{\rho}{t} + \rho u_i \pdv{u_i}{t} 
    + \rho u_j u_i \pdv{u_i}{x_j} + u_i u_i \pdv{\rho u_j}{x_j} \\
    &= u_i u_i \underbrace{\ab( \pdv{\rho}{t} + \pdv{\rho u_j}{x_j})}_{=0} + 
    \rho u_i \pdv{u_i}{t} + \rho u_j u_i \pdv{u_i}{x_j}
  \end{split}
  \label{eq:k1}$$ In the last two terms we are using the chain rule as
before $$\rho u_i \pdv{u_i}{t} + \rho u_j u_i \pdv{u_i}{x_j} 
  = \rho \pdv{}{t}\ab(\frac{1}{2}u_i u_i) 
  + \rho u_j \pdv{}{x_j}\ab(\frac{1}{2}u_i u_i)
  = \rho \pdv{K}{t} + \rho u_j \pdv{K}{x_j}$$ Finally we use a standard
trick of changing between the primitive and conservative form, i.e., we
rewrite each term as
$$\rho \pdv{K}{t} = \pdv{\rho K}{t} - \pdv{\rho}{t} K,$$
$$\rho u_j \pdv{K}{x_j} = \pdv{\rho u_j K}{x_j} - \pdv{\rho u_j} K,$$
and substitute into [\[eq:k1\]](#eq:k1){reference-type="ref"
reference="eq:k1"} using
[\[eq:mass-conserv\]](#eq:mass-conserv){reference-type="ref"
reference="eq:mass-conserv"}to simplify:
$$\rho u_i \pdv{u_i}{t} + \rho u_j u_i \pdv{u_i}{x_j} = 
  \pdv{\rho K}{t} + \pdv{\rho u_j K}{x_j} - \underbrace{\ab(\pdv{\rho}{t} + \pdv{\rho u_j}{x_j})}_{=0} K
  = \pdv{\rho K}{t} + \pdv{\rho u_j K}{x_j}$$ Leading to the
conservation equation for kinetic energy
$$\pdv{\rho K}{t} + \pdv{\rho u_j K}{x_j} 
  = -u_i\pdv{p}{x_i} + u_i\pdv{\sigma_{ij}}{x_j} + \rho u_i f_i.$$

# Total energy equation

$$\odv{}{t}\ab(\text{Energy in the control volume } \Omega) = \text{Power}$$
We will call power $N$ or rate of work done per unit time. There can be
different sources of $N$:

1.  work of body forces[^5]
    $$N = \int\limits_\Omega\rho f_i u_i \d \Omega$$

2.  work of surface forces on the boundary of the control volume
    $$N = \oint\limits_S u_i\ab(-p\delta_{ij} + \sigma_{ij})n_j \d S \stackrel{\text{Green th.}}{=}
          \int\limits_\Omega \pdv{}{x_j}\ab[u_i\ab(-p\delta_{ij} + \sigma_{ij})] \d \Omega$$

3.  heat flux through the surface (can be according to Fick's law, i.e.,
    $\bm{q} = -\lambda\grad{T}$)
    $$N = \oint\limits_S - q_j n_j \d S = \int\limits_\Omega -\pdv{q_j}{x_j}\d \Omega$$

4.  balance of local point sources (e.g., due to chemical reactions)
    $$N = \int\limits_\Omega \rho Q \d \Omega$$

The total energy in $Omega$ is given as
$$\int\limits_\Omega \rho E \d \Omega 
  = \int\limits_\Omega \rho e + \frac{\rho u_i u_i}{2} \d \Omega 
  = \int\limits_\Omega \rho e + \rho K \d \Omega$$ We need to simplify
this expression
$$\odv{}{t}\ab(\text{Energy in the control volume } \Omega) = 
  \odv{}{t}\int\limits_\Omega \rho E \d \Omega,$$ and the problem is
that $\Omega$ can be potentially deformed by the fluid flow. We have to
use Reynolds Transport theorem given as stated below to achieve this.

::: theorem
**Theorem 1** (Reynolds transport theorem, RTT). *Given:*

(i) *a material volume $\Omega$, whose shape and position are varying
    with time, i.e. $\Omega = \Omega(t)$;*

(ii) *an extensive variable $\Phi = \Phi(t)$ with its intensive
     counterpart $\phi = \phi(t, \bm{x})$ defined inside the material
     volume.*

*The total derivative of $\Phi$ with respect to time can be formulated
as: $$\odv{\Phi}{t} = \odv{}{t} \int\limits_{\Omega(t)} \phi \d \Omega
        = \int\limits_{\Omega(t)} \mdv{\phi}{t} + \phi \div{\bm{v}} \d \Omega$$*
:::

The theorem in proved below. We can rephrase it slightly and use it
$$\odv{}{t}\int\limits_\Omega \rho E \d \Omega 
  = \int\limits_\Omega \rho \mdv{E}{t} \d \Omega.$$

All the expressions are integrals in $\Omega$. We can drop the
integration as the only way they are equal is if the integrated are
equal to each other. So we end up having
$$\rho\mdv{E}{t} = -\pdv{pu_i}{x_i} + \pdv{u_i\sigma_{ij}}{x_j} - \pdv{q_i}{x_i} + \rho\ab(u_i f_i + Q),$$
which is the equation for total energy.

# Internal energy equation

We subtract the kinetic energy equation from the total energy equation.
Make the exercise yourself. Expand the terms $\pdv{p u_i}{x_i}$ and
$\pdv{\sigma_{ij}u_i}{x_j}$. The final equation is
$$\rho\mdv{e}{t} = -p\pdv{u_i}{x_i} + \sigma_{ij}\pdv{u_i}{x_j} - \pdv{q_i}{x_i} + \rho Q.$$
Note no work of body forces.

## Enthalpy equation

Enthalpy is
$$h = e + \frac{p}{\rho} \rightarrow e = h - \frac{p}{\rho}$$ so
$$\rho\mdv{e}{t} = \pdv{\rho (h - p/\rho)}{t} + \pdv{\rho u_i (h - p/\rho)}{x_i} =
  \rho\mdv{h}{t} - \mdv{p}{t}$$ If we substitute into internal energy we
get
$$\rho\mdv{h}{t} = \mdv{p}{t} -p\pdv{u_i}{x_i} + \sigma_{ij}\pdv{u_i}{x_j} - \pdv{q_i}{x_i} + \rho Q.$$

## Total enthalpy

We have to add the kinetic energy equation. Interesting stuff is
happening only on right side. Summing both equations $$\begin{split}
    \rho\mdv{H}{t} &= \underbrace{-\pdv{p}{t} + \pdv{p u_i}{x_i}}_{\mdv{p}/{t}} 
    -p\pdv{ u_i}{x_i} - \pdv{p}{x_i}u_i + u_i\pdv{\sigma_{ij}}{x_j} + \sigma_{ij}\pdv{u_i}{x_j} - \pdv{q_i}{x_i}
    + \rho\ab(u_i f_i + Q)\\
    &= \pdv{p}{t} + \pdv{u_i \sigma_{ij}}{x_j} - \pdv{q_i}{x_i}
    + \rho\ab(u_i f_i + Q)
  \end{split}$$

# Proof or Reynolds transform theorem (extra material)

#### Material volume

Special integration region $\Omega$ defined as a parcel of fluid with
such boundaries that there is no flux of selected intensive property
through them.

#### Index notation and Levi-Civita symbol

Index notation, or Einstein notation simplifies greatly multi variable
calculus and relies on two rules:

1.  Any vector variable can be represented as symbol with an index. For
    example, velocity $\bm{v}$, a vector having generally three
    components, can be simply written as $v_i$. Index $i$ is the so
    called **free index**. The letter does not matter, i.e. $i$ can be
    replaced with $\alpha$ or whatever.

2.  Repeated index implies summation over full range of this index. This
    means that, if a term like $a_i b_j c_j$ is encountered, it can be
    expanded into
    $$a_i b_j c_j = a_i b_1 c_1 + a_i b_2 c_2 + a_i b_3 c_3 =
          \sum\limits_{j=1,2,3} a_i b_j c_j.$$ Therefore, we can say
    that the sum sign $\Sigma$ is \"implicit\". The index $i$ remained a
    free index in the above expression. This means that a version for
    each spatial dimension can be obtained by setting $i$ to a chosen
    index.

The Levi-Civita symbol, $%
  \ensuremath{\varepsilon_{{i}{j}{k}}}$, is a helpful permutation symbol
defined in a following way: $$\varepsilon_{ijk} = \begin{cases}
         +1 & \text{if } (i,j,k) \text{ is } (1,2,3), (2,3,1), \text{ or } (3,1,2), \\
         -1 & \text{if } (i,j,k) \text{ is } (3,2,1), (1,3,2), \text{ or } (2,1,3), \\
    \;\;\,0 & \text{if } i = j, \text{ or } j = k, \text{ or } k = i
\end{cases}$$

#### Transforming material volume to reference configuration

The integration region is usually the function of time,
$\Omega = \Omega(t)$. The reference configuration of $\Omega(t)$,
denoted as $\Omega^0$, is not time independent. Assuming that
transformation $\Omega^0 \rightarrow \Omega$ is invertable, we can
change the integration region to the reference configuration by writing:
$$d\Omega(t) = J(t)d\Omega^0,
  \label{eq::jacobian_relation}$$ where $J$ denotes a Jacobian of the
transformation.

#### Defining the Jacobian

The trajectory of a point $\bm{x}$ laying inside the parcel $\Omega$ is
a function of time and the initial configuration $\bm{x}^0$:
$$\bm{x} = \bm{x}(t, \bm{x}^0)
  \label{eq::trajectory}$$ In the above, we have assumed that for a
given point it is possible to find its reference configuration, that is
inverse function $\bm{x}^0 = \bm{x}^0(t, \bm{x})$ exists. The necessary
and sufficient condition for invertability is the non-vanishing
Jacobian, which can be given as: $$\label{eq::jacobian}
  J = \det\pdv{x_i}{x^0_j} 
  = %
  \ensuremath{\varepsilon_{{i}{j}{k}}}
 \pdv{x_1}{x^0_i}\pdv{x_2}{x^0_j}\pdv{x_3}{x^0_k}$$

#### Time derivative of intensive variable, substantial derivative

Total time derivative of an intensive property $d \phi / d t$ (also
called substantial derivative, denoted $D\phi/Dt$) can be formulated in
the following way. We assume that trajectory of each point inside a
fluid can be described as in
[\[eq::trajectory\]](#eq::trajectory){reference-type="autoref"
reference="eq::trajectory"} and we use the chain rule:
$$\mdv{\phi}{t} \equiv \odv{}{\phi}{t}  
  =  \odv{}{t}f\ab(\bm{x}\ab(t,\bm{x}^0))
  = \pdv{\phi}{t} + \odv{x_i}{t} \pdv{\phi}{x_i}
  = \pdv{\phi}{t} + \ab(\odv{\bm{x}}{t} \cdot \grad )\phi$$ Since the
time derivative of the trajectory $d\bm{x} / dt$ is equal to the fluids
velocity $\bm{v}$ by definition, the above reduces to:
$$\mdv{\phi}{t} \equiv \odv{\phi}{t} 
  = \pdv{\phi}{t} + (\bm{v} \cdot \grad) \phi$$

#### Material derivative of the Jacobian

The Jacobian arises most often while changing the integration region
from $\Omega(t)$ to $\Omega^0$ according to
[\[eq::jacobian_relation\]](#eq::jacobian_relation){reference-type="autoref"
reference="eq::jacobian_relation"}. The closed expression for the time
derivative of the Jacobian must be found for the proof or RTT. Starting
from the definition of the Jacobian
determinant [\[eq::jacobian\]](#eq::jacobian){reference-type="autoref"
reference="eq::jacobian"}, and distributing the derivative:
$$\begin{aligned}
  \odv{}{J}{t} = \odv{}{t} \ab(%
  \ensuremath{\varepsilon_{{i}{j}{k}}}
 
  \pdv{x_1}{x^0_i} \pdv{x_2}{x^0_j} \pdv{x_3}{x^0_k})
  &= %
  \ensuremath{\varepsilon_{{i}{j}{k}}}
 \odv{}{t} \ab( \pdv{x_1}{x^0_i} ) 
    \pdv{x_2}{x^0_j} \pdv{x_3}{x^0_k} \\
  &+ %
  \ensuremath{\varepsilon_{{i}{j}{k}}}
 \pdv{x_1}{x^0_i} 
    \odv{}{t} \ab( \pdv{x_2}{x^0_j})  \pdv{x_3}{x^0_k} 
  + %
  \ensuremath{\varepsilon_{{i}{j}{k}}}
 \pdv{x_1}{x^0_i} 
    \pdv{x_2}{x^0_j} \odv{}{t} \ab( \pdv{x_3}{x^0_k} )  \end{aligned}$$
In the above, differentiation with respect to time and reference
configuration coordinates commute (the order of differentiation can be
freely changed), resulting in velocity components:
$$\odv{}{t} \ab( \pdv{x_\alpha}{x^0_\beta} )
  = \pdv{v_\alpha}{x^0_\beta}
  = \pdv{v_\alpha}{x_\gamma} \pdv{x_\gamma}{x^0_\beta}$$ We also insert
additional differentiation for the sake of further derivation.

By inserting the above into the formula for the Jacobian derivative and
simplifying, we get final formula for the $\d  J/\d  t$. Taking only one
of the terms as an example and expanding summation over $\gamma$:
$$\begin{split}
    & %
  \ensuremath{\varepsilon_{{i}{j}{k}}}
 \odv{}{t} \ab( \pdv{x_1}{x^0_i} ) 
      \pdv{x_2}{x^0_j} \pdv{x_3}{x^0_k}
    = \pdv{v_1}{x_\gamma} %
  \ensuremath{\varepsilon_{{i}{j}{k}}}
 \pdv{x_\gamma}{x^0_i}\pdv{x_2}{x^0_j}
      \pdv{x_3}{x^0_k} =\\
    & \pdv{v_1}{x_1} %
  \ensuremath{\varepsilon_{{i}{j}{k}}}
 \pdv{x_1}{x^0_i}\pdv{x_2}{x^0_j} \pdv{x_3}{x^0_k} + 
    \pdv{v_1}{x_2} %
  \ensuremath{\varepsilon_{{i}{j}{k}}}
 \pdv{x_2}{x^0_i}\pdv{x_2}{x^0_j} \pdv{x_3}{x^0_k} +
    \pdv{v_1}{x_3} %
  \ensuremath{\varepsilon_{{i}{j}{k}}}
 \pdv{x_3}{x^0_i}\pdv{x_2}{x^0_j} \pdv{x_3}{x^0_k}
  \end{split}$$ Both terms on the right with repeated index in
numerators will be equal to zero because of the definition of $%
  \ensuremath{\varepsilon_{{i}{j}{k}}}$. They will be repeated two
times, once positive and once negative, for example: $$\pdv{v_1}{x_2} %
  \ensuremath{\varepsilon_{{i}{j}{k}}}
 
  \pdv{x_2}{x^0_i}\pdv{x_2}{x^0_j} \pdv{x_3}{x^0_k} = \dots
  \pdv{v_1}{x_2} 
  \pdv{x_2}{x^0_1}\pdv{x_2}{x^0_2} \pdv{x_3}{x^0_3} + \dots 
  - \pdv{v_1}{x_2} 
  \pdv{x_2}{x^0_2}\pdv{x_2}{x^0_1} \pdv{x_3}{x^0_3} + \dots$$ The terms
on the right cancel each other out. In the above, we shown only
$(i,j,k) = (1,2,3)$ and $(2,1,3)$. Thanks to that, and using the
original Jacobian definition,
i.e. [\[eq::jacobian\]](#eq::jacobian){reference-type="autoref"
reference="eq::jacobian"}, we can simplify first of the terms: $$%
  \ensuremath{\varepsilon_{{i}{j}{k}}}
 \odv{}{t} \ab( \pdv{x_1}{x^0_i} ) \pdv{x_2}{x^0_j} 
  \pdv{x_3}{x^0_k}
  = \pdv{v_1}{x_1} %
  \ensuremath{\varepsilon_{{i}{j}{k}}}
 \pdv{x_1}{x^0_i}\pdv{x_2}{x^0_j} 
  \pdv{x_3}{x^0_k}
  = \pdv{v_1}{x_1} J$$ Treating indices $2$ and $3$ the same way, the
final formula for the time derivative of the Jacobian looks as follows:
$$\odv{J}{t}  = \pdv{v_i}{x_i} J = \ab(\div\bm{v})J
  \label{eq::ddt_J}$$

::: proof
*Proof.* The integral of $\phi$ can be expressed in reference
configuration $\Omega^0$, assuming that $\Omega(t) = J(t)\Omega^0$:
$$\odv{}{t} \int\limits_{\Omega(t)} \phi(t, \bm{x}) \d{\Omega} = 
    \odv{}{t} \int\limits_{\Omega^0} \phi(t, \bm{x^0})J(t) \d{\Omega^0}$$
Since $\Omega_0$ is time independent, the derivative can be moved under
the integral:
$$\odv{}{t} \int\limits_{\Omega(t)} \phi(t, \bm{x}) \d{\Omega} = 
    \int\limits_{\Omega^0} \odv{}{t}[\phi(t, \bm{x^0})J(t)] \d{\Omega^0} =
    \int\limits_{\Omega^0} \mdv{\phi}{t}J + \phi\odv{}{J}{t} \d{\Omega^0}$$
Note the presence of substantial derivative; the intensive quantity is
transported by the fluid. Factoring the Jacobian out of the terms under
the integral, we can return to the original integration region
$$\int\limits_{\Omega^0} \mdv{\phi}{t}J + \phi\odv{}{J}{t} \d{\Omega^0} = 
    \int\limits_{\Omega^0} \ab[\mdv{\phi}{t} + J^{-1}\phi\odv{J}{t}]J \d{\Omega^0} = 
    \int\limits_{\Omega(t)} \mdv{\phi}{t} + J^{-1}\phi\odv{J}{t} \d{\Omega}.$$
The final formula is obtained by plugging in the time derivative of the
Jacobian [\[eq::ddt_J\]](#eq::ddt_J){reference-type="autoref"
reference="eq::ddt_J"}:
$$\int\limits_{\Omega(t)} \mdv{\phi}{t} + J^{-1}\phi\odv{}{J}{t} \d{\Omega}
    = \int\limits_{\Omega(t)} \mdv{\phi}{t} + \phi \div\bm{v} \d{\Omega}$$ ◻
:::

[^1]: Meaning of the symbols

    $\rho$

    :   density

    $\bm{u}$

    :   velocity vector

    $u_i$

    :   $i$-th component of $\bm{u}$

    $\bm{x}$

    :   spatial coordinate

    $t$

    :   time

[^2]: Meaning of the symbols

    $p$

    :   pressure

    $\bm{\sigma}$

    :   viscous stress tensor

    $\bm{f}$

    :   body force (e.g., gravity)

[^3]: The operation of multiplication of two vectors (variables with one
    index) with the same index repeated is a dot product, i.e.,
    $u_i u_i \equiv \bm{u}\bm{\cdot}\bm{u}$.

[^4]: $\odv{f(g(x))}{x} = \odv{f}{g}\odv{g}{x}$

[^5]: Meaning of symbols:

    $\Omega$

    :   arbitrary control volume

    $S$

    :   surface of the volume

    $\bm{n}$, $n_i$

    :   normal of the surface

    $\bm{q}$, $q_i$

    :   heat flux

    T

    :   temperature
