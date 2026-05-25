# Randomly Generated Points in 3D

Let $X_r$ be a random variable representing the radial coordinate of a point uniformly distributed within a spherical shell ([annulus](https://stackoverflow.com/questions/67285924/random-uniform-3d-distribution-of-points-inside-a-spherical-shell-of-inner-and-o)) bounded by inner radius $r$ and outer radius $R$. Then, the transformed variable

$$\frac{X_r^3 - r^3}{R^3 - r^3} \sim Uniform(0,1)$$

The random variables that map the angular coordinates ($X_{\phi}$ and $X_{\theta}$) will also have interesting relations with the uniform distribution, that will allow to sample uniformly points within an annulus or $\textcolor{orange}{sphere}$. It is the sphere, a special case for the annulus with $r=0$, our current interest.

The interest now, is to justify this result.
- [Wolfram proof](https://mathworld.wolfram.com/RandomNumber.html)
- [Stack](https://stackoverflow.com/questions/5408276/sampling-uniformly-distributed-random-points-inside-a-spherical-volume#)
- [?????](https://docs.openmc.org/en/v0.8.0/methods/physics.html#:~:text=We%20first%20need%20to%20uniformly,%5B0%2C2%CF%80)

# Probability Integral Transform

[Wiki](https://en.wikipedia.org/wiki/Probability_integral_transform)
Suppose that a random variable $X$ has a continuous distribution for which the cumulative distribution function (CDF) is $F_X$ . Then the random variable $Y$ defined as

$$Y := F_X(X),$$

has a standard uniform distribution.
# Inverse Transform Sampling method

[StackExchange approach to the theorem](https://stackoverflow.com/questions/2106503/pseudorandom-number-generator-exponential-distribution/2106568#2106568)

Assume you have a desired PDF $F(x)$ continuous and normalized in the interval  $x\in[a,b]$. One can integrate to obtain a CDF:

$$C(y) = \int_a^y F(x)dx$$

Then, if $C(y)$ is invertible, we can obtain $C^{-1}$, such that if evaluated in a Uniformly distributed variable $Z\sim Uniform(0,1)$, we can get:

$$x_i = C^{-1}(z_i)$$

## Radial Coordinate $r$

In my case, I want $F(x)$ must be proportional to the square of the radius, since the element $dx dy dz = r^2 \sin(\theta) dr d\theta d\phi$. So we propose $F(r) = C r^2$ 

Normalization condition leads to:

$$\int_0^R F(r)dr = 1 \hspace{2cm}\rm yields\hspace{2cm} C = \frac{3}{R^3}$$

We can calculate the Cumulative Density Function (CDF) $C(r)$

$$C(r) = \int_0^r \frac{3r'^2}{R^3}dr' = \frac{r^3}{R^3}$$

But, it is our intention to have CDF that is uniform. So, we end up with $C(r) \sim U(0,1)$, where we denote a uniform random variable as $U_1(0,1) = Uniform(0,1)$.
Inverting the function leads to (renaming $r\to X_r$)

$$X_r = R \sqrt[3]{U_1(0,1)}$$

Which denotes the distribution of $r$ in terms of a uniform random variable.

## Azimuthal Coordinate $\theta$

Now, the azimuthal coordinate behaves weirdly. As mentioned previously, its distribution is influenced by a non-linear function (a sine function). We can see this behavior in the volume differential $dV = dx dy dz = r^2 \sin(\theta) dr d\theta d\phi$. To bypass non-linearity, we will desired for the $z$ coordinate, to be uniform.

In this case, $F(\theta) = \sin(\theta)$, so we repeat our previous procedure:

$$\int_0^{\pi} C \sin(\theta)d\theta = 1 \hspace{2cm}\rm yields\hspace{2cm} C = \frac{1}{2}$$

$$C(r) = \int_0^{\theta} \frac{1}{2}\sin(\theta')d\theta' = \frac{1}{2}(1 - \cos(\theta))$$

Therefore, the distribution is 

$$\frac{1}{2}(1 - \cos(\theta)) = U_2(0,1)$$

and since cosine is a pair function, we can change sign in the argument into 

$$X_{\theta} = \arccos(2U_2(0,1)-1)$$.

## Polar Coordinate $\phi$

The polar coordinate is distributed in the interval $\phi \in [0,2\pi]$. In this very special case, the volume differential has no dependence on the polar coordinate. This makes our assumption for the PDF very simple. 

$$\int_0^{2\pi} Cd\phi = 1 \hspace{2cm}\rm yields\hspace{2cm} C = \frac{1}{2\pi}$$

$$C(r) = \int_0^{\phi} \frac{1}{2\pi}d\phi = \frac{\phi}{2\pi}$$

Therefore, the distribution is 

$$X_{\phi} = 2\pi U_3(0,1)$$

# Cartesian Coordinates

It is a transitive condition, that all points in space generate in the triplet $\{(r,\phi,\theta)\}$, being uniformly distributed, must map into a uniformly distributed set in cartesian coordinates as $\{(x,y,z)\}$. Therefore, we simply use the spherical transformation relations between cartesian and spherical coordinates.

$$x = r\sin(\theta)\cos(\phi)$$

$$y = r\sin(\theta)\sin(\phi)$$

$$z = r\cos(\theta)$$

Then it follows that the distribution of triplets (x,y,z) uniformly inside of a sphere follows the relations,

$$x = R \sqrt[3]{U_1(0,1)} \sqrt{1-(2U_2(0,1)-1)^2}\cos(2\pi U_3(0,1))$$

$$y = R \sqrt[3]{U_1(0,1)}\sqrt{1-(2U_2(0,1)-1)^2}\sin(2\pi U_3(0,1))$$

$$z = R(2U_2(0,1)-1) \sqrt[3]{U_1(0,1)}$$

# Testing

Of all three, its harder to visualize how $r$ is distributed.
We can observe that it almost linearly scales with distance, which makes sense. It is intuitive to think that at $r=0$ we wont find any point, and that the amount of points in $r = 1$ and $r=2$ differs by an amount proportional to the increment in $\frac{2^2}{1^2} = 4$.

In the case of $\theta$, the distribution is weighted by a sine function, this leads to the curve to follow a similar shape. Also, the symmetric characteristics of the z coordinate, which is distributed based on $z=r\cos(\theta)$ must closely depict the PDF of $r$. 

Other ways to make sure that $(x,y,z)$ triples are uniformly spaced is to make a projection on an arbitrary plane. 

# Open Questions

Is there an objective way to prove that this distributions are uniform?

- P-Value Testing: Hypothesis is that our distro of $(x,y,z)$ is uniform within the sphere

In this case, my hypothesis is that if $\vec{r}=(x,y,z)$ is uniformly distributed, then its mean would be $\vec{r}=(\vec{a}+\vec{b})/2$, which in this case, would be zero.

Null Hypothesis: $H_0: \vec{\mu} = \vec{0}$ corresponds to the mean being zero
Hypothesis: $H_a: \vec{\mu} \neq \vec{0}$ corresponds to the mean being different from zero

At $95 \%$ confidence level, is there evidence to discard null hypothesis? $C = 0.95$ therefore $\alpha = 0.05$.

## Hypothesis

Confidence $H_0$ is true if $p \geq \alpha$ then fail to reject null $H_0$
Rejection    $H_0$ is false If $p < \alpha$ then reject null $H_0$

Whether the **true mean of your 3D point distribution is significantly different from zero**. This is broken down into three separate tests, one for each coordinate (x, y, and z).

- **Null Hypothesis ($H_0​$):** The true mean of the coordinate (x, y, or z) is equal to zero.
- **Alternative Hypothesis ($H_a$​):** The true mean of the coordinate (x, y, or z) is not equal to zero.
## Decision Rule

Using a **95% confidence level**, which means your **significance level (α) is 0.05**.

- **If the p-value is less than α (0.05):** You **reject** the null hypothesis (H0​). This means there's statistically significant evidence to conclude that the true mean of that coordinate is _not_ zero.
    
- **If the p-value is greater than or equal to α (0.05):** You **fail to reject** the null hypothesis (H0​). This means there's not enough statistically significant evidence to conclude that the true mean of that coordinate is different from zero. Data is consistent with the mean being zero.
    
$$\langle x \rangle = 0.0016644368090123485 \hspace{3cm} std=0.4470375116957907$$
$$\langle y \rangle = 0.005189300765255616 \hspace{3cm} std= 0.44705389214425956$$
$$\langle z \rangle = 0.002096455858892037 \hspace{3cm} std=0.4505343490644678$$

This means that we have to turn a normal distribution into a standard to evaluate p-value

$$Z_1 = \frac{0.0016644368090123485- 0}{(0.4470375116957907))/\sqrt{10,000}} = 0.37232230$$

$$Z_2 = \frac{0.00518930076525561-0}{( 0.44705389214425956))/\sqrt{10,000}} = 1.16078775$$

$$Z_3 = \frac{0.002096455858892037 -0}{(0.4505343490644678))/\sqrt{10,000}} = 0.46533036$$

The **two-tailed p-values** for the Z-scores are:

- For $Z_1​=0.37232230$: The two-tailed p-value is approximately $0.7094$

- For $Z_2​=1.16078775$: The two-tailed p-value is approximately $0.2458$

- For $Z_3​=0.46533036$: The two-tailed p-value is approximately $0.6418$

Since p-value is greater than $\alpha$, then we don't have enough statistical to reject the null hypothesis.

---

# Math Test

Inline math example: $e^{i\pi} + 1 = 0$.

Display math example:

$$
\int_0^1 x^2 \,dx = \frac{1}{3}
$$

# This post...

was made from a note I made and develope in obsidian because for some reason, it didn't sit right with me the procedure to generate uniform random points inside a sphere. Now I know how to do it, which is nice.

Since p-value is greater than $\alpha$, then we don't have enough statistical to reject the null hypothesis.

