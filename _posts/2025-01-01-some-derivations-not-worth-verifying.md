---
layout: default
title: Some CR Transport Derivations
date: 2025-01-01
---

Deriving equations and CR transport theory from Silsbee & Ivlev 2018.
## The Continuity Equation


$$
\begin{equation}
    \frac{\partial f}{\partial t} + \frac{\partial }{\partial \mu}(f\dot{\mu}) + \frac{\partial }{\partial s}(f\dot{s})= 0
\end{equation}$$
\noindent
This equation describes the conservation of the distribution function $f(\mu, s, t)$ in a 2D phase space, where $\mu$ is the cosine of the pitch angle and $s$ is the position along the magnetic field line. If we assume that $f$ is the steady state solution for the phase space distribution, then we have $\frac{\partial f}{\partial t} = 0$ and expand, which simplifies \eqref{ContinuityEqtn} to:
$$
\begin{equation}
    \dot{\mu}\frac{\partial f}{\partial \mu} + f\frac{\partial \dot{\mu}}{\partial \mu}+ \dot{s}\frac{\partial f}{\partial s} + f\frac{\partial \dot{s}}{\partial s} = 0 \hspace{8mm} (\text{Expand derivatives of products})
\end{equation}
$$

\noindent
we further simplified by the relation $\dot{s} = v\cos(\alpha) = v\mu$ representing the parallel velocity component. Similarly, conservation of the magnetic moment, allows to find an expression for $\dot{\mu}$.
$$
\begin{align}
\frac{d}{ds}\left( \frac{1-\mu^2}{B(s)}\right) = 0&  \hspace{8mm} (\text{Conservation of magnetic moment yields})\\
\frac{\partial \mu}{\partial s}= -\frac{(1-\mu^2)}{2 \mu B} \frac{\partial B}{\partial s}& \hspace{8mm} (\text{Simplifying}) \\
    \dot{\mu}  = \frac{\partial \mu}{\partial s} \dot{s} = -v(1-\mu^2)\frac{\partial \ln(\sqrt{B})}{\partial s}& \hspace{8mm} (\text{Computing time derivative with chain rule}) \\ 
    \frac{\partial \dot{\mu}}{\partial \mu} = 2v\mu \frac{\partial \ln(\sqrt{B})}{\partial s}
& \hspace{8mm} (\text{And the derivative with respect to $\mu$})
\end{align}
$$

\noindent
Substituting in \eqref{ExpandedContinuityEqtn}, we get

$$
\begin{align*}
v\mu \frac{\partial f}{\partial s} + f \left( -v \frac{(1-\mu^2)}{\mu} \frac{\partial \ln(\sqrt{B})}{\partial s} \right)
+ \left( -v(1-\mu^2)\frac{\partial \ln(\sqrt{B})}{\partial s} \right) \frac{\partial f}{\partial \mu} + f \left( 2v\mu \frac{\partial \ln(\sqrt{B})}{\partial s} \right) = 0
\end{align*}
$$
\noindent
Rearranging and grouping terms:
$$
\begin{align*}
v\mu \frac{\partial f}{\partial s} - v(1-\mu^2)\frac{\partial \ln(\sqrt{B})}{\partial s}\frac{\partial f}{\partial \mu}+ vf \frac{\partial \ln(\sqrt{B})}{\partial s} \left[ -\frac{(1-\mu^2)}{\mu} + 2\mu \right] = 0
\end{align*}
$$
\noindent
The bracketed term simplifies to
$$\begin{equation*}
\frac{-(1-\mu^2) + 2\mu^2}{\mu} = \frac{-1+\mu^2+2\mu^2}{\mu} = \frac{3\mu^2-1}{\mu}  
\end{equation*}
$$
\noindent
So we obtain:
$$\begin{equation}
v\mu \frac{\partial f}{\partial s} - v(1-\mu^2)\frac{\partial \ln(\sqrt{B})}{\partial s}\frac{\partial f}{\partial \mu} + vf \frac{\partial \ln(\sqrt{B})}{\partial s} \left( \frac{3\mu^2 - 1}{\mu} \right) = 0 
\end{equation}
$$
\noindent
To account for the focusing term, we define a new distribution function $g = Bf$. And express the derivatives of $f$ in terms of $g$:
$$\begin{align*}
\frac{\partial f}{\partial s} &= \frac{\partial}{\partial s}\left(\frac{g}{B}\right) = \frac{1}{B}\frac{\partial g}{\partial s} - \frac{g}{B^2}\frac{\partial B}{\partial s} \\
\frac{\partial f}{\partial \mu} &= \frac{\partial}{\partial \mu}\left(\frac{g}{B}\right) = \frac{1}{B}\frac{\partial g}{\partial \mu}
\end{align*}
$$
Substitute and multiply the entire equation by $B/v$:
$$\begin{align*}
\mu \left( \frac{\partial g}{\partial s} - \frac{g}{B}\frac{\partial B}{\partial s} \right) - (1-\mu^2)\frac{\partial \ln(\sqrt{B})}{\partial s}\frac{\partial g}{\partial \mu}+ g \frac{\partial \ln(\sqrt{B})}{\partial s} \left( \frac{3\mu^2 - 1}{\mu} \right) = 0
\end{align*}
$$\noindent
Recall that $\frac{\partial \ln(\sqrt{B})}{\partial s} =\frac{1}{2B}\frac{\partial B}{\partial s}$. Substituting this:
$$\begin{align*}
\mu \frac{\partial g}{\partial s} - \mu g \left( 2\frac{\partial \ln(\sqrt{B})}{\partial s} \right) - (1-\mu^2)\frac{\partial \ln(\sqrt{B})}{\partial s}\frac{\partial g}{\partial \mu}+ g \frac{\partial \ln(\sqrt{B})}{\partial s} \left( \frac{3\mu^2 - 1}{\mu} \right) = 0
\end{align*}
$$\noindent
Group terms with $\frac{\partial \ln(\sqrt{B})}{\partial s}$:
$$
\mu \frac{\partial g}{\partial s} - \frac{\partial \ln(\sqrt{B})}{\partial s} \left[ 2\mu g + (1-\mu^2)\frac{\partial g}{\partial \mu} - g \frac{3\mu^2 - 1}{\mu} \right] = 0
$$
\noindent
Again the bracketed term simplifies to:
$$\begin{align*}
2\mu g - g \frac{3\mu^2 - 1}{\mu} + (1-\mu^2)\frac{\partial g}{\partial \mu} &= g \left( 2\mu - \frac{3\mu^2 - 1}{\mu} \right) + (1-\mu^2)\frac{\partial g}{\partial \mu} \\
&= g \left( \frac{2\mu^2 - 3\mu^2 + 1}{\mu} \right) + (1-\mu^2)\frac{\partial g}{\partial \mu} \\
&= g \left( \frac{1 - \mu^2}{\mu} \right) + (1-\mu^2)\frac{\partial g}{\partial \mu} \\
&= (1-\mu^2) \left( \frac{g}{\mu} + \frac{\partial g}{\partial \mu} \right) \\
&= (1-\mu^2) \frac{1}{\mu} \left( g + \mu \frac{\partial g}{\partial \mu} \right) \\
&= (1-\mu^2) \frac{1}{\mu} \frac{\partial (\mu g)}{\partial \mu}
\end{align*}
$$
\noindent
the differential equation for $g$ is:
$$\begin{equation*}
\mu^2 \frac{\partial g}{\partial s} - \frac{\partial \ln(\sqrt{B})}{\partial s} (1-\mu^2)  \frac{\partial (\mu g)}{\partial \mu} = 0
\end{equation*}
$$\noindent
Let's now substitute $\psi = \mu g$ into the equation for $g$. And we note, that we are working on phase space, such that partial derivatives between phase space coordinates are taken considering other coordinates constant. In Thermodynamics this is made obvious by using the notation $\left(\frac{\partial U}{\partial T} \right)_{N,P}$, which means \textit{the partial derivative of the internal energy, holding $N, P$ as constants},
$$    \mu \frac{\partial g}{\partial s} = \mu \frac{\partial}{\partial s}\left(\frac{\psi}{\mu}\right) = \mu \left( \frac{1}{\mu} \frac{\partial \psi}{\partial s} \right) = \frac{\partial \psi}{\partial s}
  $$
Substituting these into the equation for $g$:
$$\begin{equation}
\mu\frac{\partial \psi}{\partial s} - \frac{\partial \ln(\sqrt{B})}{\partial s}(1-\mu^2)  \frac{\partial \psi}{\partial \mu} = 0
\end{equation}
$$
Such that $\psi$ is related to the phase space distribution function by the expression $f = B\mu \psi(s,\mu)$. The resulting equation, renaming the unknown function $\psi$ back to $f$ is:
$$\begin{equation}
\mu\frac{\partial f}{\partial s} - \frac{\partial \ln(\sqrt{B})}{\partial s}(1-\mu^2)  \frac{\partial f}{\partial \mu} = 0
\end{equation}
$$This differential equation does not account for energy losses by interactions with matter (The nature of this interactions will be discussed in further sections). This can be accounted by adding up a term in the continuity equation involving the energy.
$$\begin{equation}
v\mu\frac{\partial f}{\partial s} - v\frac{\partial \ln(\sqrt{B})}{\partial s}(1-\mu^2)  \frac{\partial f}{\partial \mu} + \frac{\partial }{\partial p} (f \dot{p})= 0
\end{equation}
$$Substituing $j(\mu,s,E) = v(E) f(\mu,s,E)$, in which the relation between momentum and energy is given by $dE = v dp$, and $\dot{p} = -n_g(s)L(E)$

$$\begin{equation}
\mu\frac{\partial j}{\partial s} - \frac{\partial \ln(\sqrt{B})}{\partial s}(1-\mu^2)  \frac{\partial j}{\partial \mu}  -n_g \frac{\partial }{\partial E} (jL)= 0
\end{equation}
$$
Somehow this can be simplified to the following

$$\begin{equation}
\frac{\hat{\mu}}{n_g}\frac{\partial j}{\partial s} - \frac{\partial }{\partial E} (jL)= 0
\end{equation}
$$
or by the relation $\partial N = n_g\partial s$,
$$\begin{equation*}
\hat{\mu}\frac{\partial j}{\partial N} - \frac{\partial }{\partial E} (jL)= 0
\end{equation*}
$$It must be pointed, that equation \eqref{fluxequation} can be used as long as no substantial energy losses occur as a result of scattering of CRs. This is, as long as the diffusion term in the equations remains negligible\cite{Morfill1976}. Energy losses are a result of small instant reductions caused by individual collisions with gas particles, subsequently causing the Larmor radius to decrease. 
\noindent
We also point out that the relation between $j(\mu,s,E)$ and the number of particles per unit volume and unit energy is,
$$
\begin{equation}
    \mathcal{N}(E,s) = \frac{4\pi}{v}j(E,s,\mu)
\end{equation}
$$
This note explores magnetic focusing and mirroring, two effects crucial to understanding cosmic ray propagation in molecular clouds. These effects are mathematically described, highlighting how they can counteract each other.

---

## Focusing and mirroring

In this section, we explore two effects relevant to the propagation of cosmic rays through molecular clouds: \textit{magnetic focusing} and \textit{magnetic mirroring}. These two effects are the core of our paper, since the paper is about how these two effects cancel each other under certain conditions. It is helpful to be able to find a way to describe them mathematically.

We begin with the assumption that the distribution of cosmic rays (CRs) is initially isotropic in the interstellar medium and that there are no significant energy losses during propagation. Liouville’s theorem gives us a consequence of this (see Section 4.3): the phase-space density of CRs is conserved, which implies that the distribution function $f(\mu, s) = f_i(\mu_i)$ is preserved along their trajectories, where $\mu = \cos\alpha$ is the cosine of the pitch angle $\alpha$ and $s$ is the distance along the magnetic field line.
### Focusing and Flux Tubes

The figure below illustrates a flux tube bounded by cross-sectional areas $A_1$ and $A_2$, through which cosmic rays travel along magnetic field lines. Since cosmic rays are charged particles, their motion is constrained to follow the magnetic field lines. Where the magnetic field is stronger, the density of field lines is higher, and therefore more CRs are guided into those regions. This gives rise to magnetic focusing, which leads to:

$$
n(s) \propto B(s),
$$

where $n(s)$ is the local number density of CRs and $B(s)$ is the magnetic field strength at position $s$.

The particle flux at position $s$ is given by:

$$
F(s) = n(s)\, v\, \mu,
$$

where $v$ is the speed of the particles and $\mu = \cos\alpha$ is the pitch angle cosine. Because the total number of particles is conserved, the flux at each cross-section must satisfy:

$$
A_1 F_1 = A_2 F_2.
$$

Magnetic flux conservation implies:

$$
B_1 A_1 = B_2 A_2 \quad \Rightarrow \quad A_1 = \frac{B_2}{B_1} A_2.
$$

Substituting this into the flux equality gives:

$$
\frac{F_1}{B_1} = \frac{F_2}{B_2}.
$$

Using $F(s) = n(s) v \mu$, we can write:

$$
\frac{n(s) \mu(s)}{B(s)} = \frac{n_i \mu_i}{B_i}.
$$

Solving for $n(s)$ gives:

$$
n(s) = \frac{n_i \mu_i B(s)}{B_i \mu(s)}.
$$

To connect this with the distribution function $f(\mu, s)$, we recall that the number density is the integral of the distribution over all pitch angles (from $-1 <\mu <1$, since those values account for the pitch angles from $ 0 <\alpha<\pi/2$):

$$
n(s) = \int_{-1}^{1} f(\mu, s) \, d\mu.
$$

Due to Liouville’s theorem, this is conserved along trajectories, so:

$$
n_i = \int_{-1}^{1} f(\mu_i)\, d\mu_i.
$$
If the source distribution is isotropic, then $f(\mu_i) = \text{const}.$ Let $ f(\mu_i) = C$, where $C$ is a constant. Then, we can solve the integral explicitly:
$$
n_i = \int_{-1}^{1} C\, d\mu_i
$$
$$
n_i = C [\mu_i]_{-1}^{1}
$$
$$
n_i = C (1 - (-1))
$$
$$
n_i = 2C
$$
Therefore, solving for $C$, we find:
$$
f(\mu_i) = C = \frac{n_i}{2}
$$
## Mirroring and Adiabatic Invariants

While magnetic focusing causes CRs to be guided into regions of stronger $B$, the mirror effect can counteract this focusing. The underlying physics is that CRs spiral along field lines due to the Lorentz force:
$$
\vec{F} = q \vec{v} \times \vec{B}.
$$

This motion defines a pitch angle $\alpha$ between the particle’s velocity vector and the magnetic field. A key quantity that remains invariant in slowly varying magnetic fields is the magnetic moment (first adiabatic invariant):

$$
\mu_{\text{mag}} = \frac{m v_\perp^2}{2B} = \text{const},
$$

where $v_\perp = v \sin\alpha$ is the velocity component perpendicular to the magnetic field.

The conservation of the adiabatic invariant, $\mu_{\text{mag}}$, can be understood intuitively by considering the motion of a charged particle in a magnetic field that changes slowly over time or space. The term "slowly" (or adiabatically) implies that the magnetic field does not change significantly over the course of a single cyclotron gyration of the particle.

Under these conditions, the particle completes many cyclotron orbits before the magnetic field changes significantly. Over each orbit, the magnetic flux ($\Phi$) enclosed by the particle's circular path remains approximately constant. This is because the particle's orbit effectively "adjusts" to the slowly changing field, maintaining a constant flux through its loop. As the particle moves into regions of stronger magnetic field, its perpendicular kinetic energy ($E_\perp = \frac{1}{2}mv_\perp^2$) must increase to maintain the approximate constancy of the magnetic moment. Since the total kinetic energy $E = \frac{1}{2}mv^2$ is conserved in a static magnetic field (as the Lorentz force does no work), an increase in $E_\perp$ implies a decrease in the parallel kinetic energy ($E_\parallel = \frac{1}{2}mv_\parallel^2$), leading to a reduction in parallel velocity. This continuous deceleration of the parallel motion as the particle enters stronger fields eventually causes it to reflect if the field becomes sufficiently strong, as explained by the mirror effect.

This relationship is a direct consequence of the conservation of the magnetic moment, the first adiabatic invariant. From the principles of classical mechanics, adiabatic invariants are quantities that remain constant during slow changes in the parameters of a system. For a charged particle spiraling in a magnetic field, the magnetic moment, $\mu_{\text{mag}}$, is proportional to the action integral $J$ associated with the periodic gyromotion. The action integral for a closed orbit is given by $J = \oint p \, dq$. For the cyclotron motion, where the particle completes an orbit in the plane perpendicular to the magnetic field, the action integral can be expressed as:
$$
\begin{equation}
    J = \oint p_{\perp} \, dl_{\perp}
\end{equation}$$
where $dl_{\perp}$ is an element of length along the perpendicular circular orbit. For a circular orbit, $dl_{\perp} = r_L d\theta$. since the radius, $r_L = \frac{mv_\perp}{|q|B}$, we get for the action to be
$$
J = \oint  (mv_\perp)\frac{mv_\perp}{|q|B} d\theta = 2\pi\frac{m^2v^2_\perp}{|q|B}
$$


For a more thorough derivation and explanation of this in the context of plasma physics, you can refer to "Introduction to Plasma Physics and Controlled Fusion" by F. F. Chen. Hence, the action $J$ is proportional to $\frac{m^2 v_\perp^2}{|q|B}$:


Because this action $J$ is conserved in a slowly varying magnetic field, and $m$ (particle mass) and $|q|$ (charge magnitude) are constants, it follows that the quantity $\frac{m^2 v_\perp^2}{|q|B}$ must also be a constant along the particle's trajectory. Thus, for an initial state (subscript $i$) and a final state (subscript $f$):
$$
\frac{m^2 v_{\perp i}^2}{|q|B_i} = \frac{m^2 v_{\perp f}^2}{|q|B_f}.
$$
Since $m$ and $|q|$ are constants, they cancel out from both sides:
$$
\frac{v_{\perp i}^2}{B_i} = \frac{v_{\perp f}^2}{B_f}.
$$
Now, substituting the perpendicular velocity component $v_\perp = v \sin\alpha$ (where $v$ is the total speed of the particle):
$$
\frac{(v \sin\alpha_i)^2}{B_i} = \frac{(v \sin\alpha_f)^2}{B_f}.
$$
As the particle's total kinetic energy $E = \frac{1}{2}mv^2$ is conserved in a static magnetic field (because the Lorentz force does no work), its total speed $v$ is constant throughout the trajectory. Therefore, $v^2$ cancels from both sides, leading to the fundamental conservation law:
$$
\frac{\sin^2 \alpha_i}{B_i} = \frac{\sin^2 \alpha_f}{B_f}.
$$
Conventionally, we denote the final position as $s$, so this relation becomes:
$$
\frac{\sin^2 \alpha(s)}{B(s)} = \frac{\sin^2 \alpha_i}{B_i}.
$$
This conservation is a fundamental result in plasma physics and charged particle dynamics. For a comprehensive and highly rigorous treatment of adiabatic invariants, including their mathematical foundations, one may read the Landau and Lifshitz's Mechanics book.

### Mirror Condition and Pitch Angle

This allows us to define the **mirror condition**. A particle reverses its direction (mirrors) when its pitch angle reaches $\alpha = \pi/2$ (i.e., its velocity component parallel to the magnetic field becomes zero, $v_\parallel = 0$, and thus $\mu = \cos(\pi/2) = 0$). At the mirror point, let the magnetic field strength be $B_m$. From the conservation of the magnetic moment:

$$
\frac{\sin^2 \alpha_i}{B_i} = \frac{\sin^2 (\pi/2)}{B_m} = \frac{1}{B_m}.
$$

Solving for $\sin^2 \alpha_i$:

$$
\sin^2 \alpha_i = \frac{B_i}{B_m}.
$$

This means a particle will mirror if its initial pitch angle $\alpha_i$ satisfies $\sin^2 \alpha_i \ge B_i/B_m$. The minimum initial pitch angle for mirroring is given by:

$$
\alpha_i = \arcsin\left( \sqrt{\frac{B_i}{B_m}} \right).
$$

Expressing the conservation of magnetic moment in terms of $\mu = \cos\alpha$:
Since $\sin^2\alpha = 1 - \cos^2\alpha = 1 - \mu^2$, we have:

$$
\frac{1 - \mu^2(s)}{B(s)} = \frac{1 - \mu_i^2}{B_i}.
$$

Solving for $\mu(s)$:

$$
\mu^2(s) = 1 - \frac{B(s)}{B_i}(1 - \mu_i^2).
$$
Taking the square root, we get:
$$
\mu(s) = \pm\sqrt{1 - \frac{B(s)}{B_i}(1 - \mu_i^2)}.
$$

Setting $\mu(s) = 0$ at the mirror point ($B(s) = B_m$), we recover the mirror point condition in terms of $\mu_i$:

$$
0 = 1 - \frac{B_m}{B_i}(1 - \mu_i^2),
$$
$$
\frac{B_m}{B_i}(1 - \mu_i^2) = 1,
$$
$$
1 - \mu_i^2 = \frac{B_i}{B_m},
$$
$$
\mu_i^2 = 1 - \frac{B_i}{B_m}.
$$
Thus, the condition on the initial pitch angle cosine for mirroring is:
$$
\mu_i = \sqrt{1 - \frac{B_i}{B_m}}.
$$

This derivation shows how, in the presence of an increasing magnetic field, CRs with certain pitch angles will reflect (mirror) back along their path, opposing the focusing effect. These two competing effects can, under certain conditions, cancel each other out, preserving the cosmic ray density across regions of varying magnetic field strength.
