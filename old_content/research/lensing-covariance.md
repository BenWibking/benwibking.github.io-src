Title: Covariance of the two-point function and 'bad' integrals
Date: 2017-01-21
Category: Research
Summary: Sometimes integrals diverge because of physics; or, how to properly compute covariance matrices in cosmology.

If the galaxy and matter fields are Gaussian, then the projected two-point galaxy clustering covariance is:
$$Cov(r_i,r_j) = A_W \int_{0}^{\infty} \frac{dk\, k}{2 \pi} J_0(k r_i) J_0(k r_j) \left(P(k) + \frac{1}{n_g}\right)^2$$

where $A_W$ is the survey window function.

Except this integral is not well defined!

If $r_i \ne r_j$, then the shot noise term ($1/n_g$) causes the integrand to oscillate without decay as $k \rightarrow \infty$.  This divergence can be resolved, however, by averaging over oscillations in the asymptotic region.  If one doesn't do this, then the worst that can happen is that additional noise (typically on the order of a few percent) will be introduced into the numerical result. (This will produce spurious eigenvalues in the covariance matrix and will lead to a completely unreasonable *inverse* covariance matrix, however, but that is the topic of another blog post!)

The truly disastrous problem happens when evaluating the diagonal elements of the covariance matrix where $r_i = r_j$.  Then we can use an asymptotic expansion of $J_0$ to write:

$$J_0(k r) = \sqrt{\frac{\pi}{k r}} \cos(kr - \pi/4) + ...$$

and then the shot noise contribution to the integral is proportional to

$$\int_{0}^{\infty} J_0(k r_i) J_0(k r_j) k dk = $$

$$Cov(r_i,r_j) = A_W \int_{0}^{\infty} \frac{dk\, k}{2 \pi} \left( \int_{r_i}^{r_{i+1}} J_0(k r_i) \, dr_i \right) \left( \int_{r_j}^{r_{j+1}} J_0(k r_j) \, dr_j \right) \left(P(k) + \frac{1}{n_g}\right)^2$$




