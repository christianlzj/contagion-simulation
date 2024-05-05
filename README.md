# **Contagion**

The goal is to model the state of the system represented by
>$\vec{x}(t)=\begin{bmatrix}S(t) \\ I(t) \\ R(t)\end{bmatrix},$

where $S(t)$, $I(t)$, and $R(t)$ represent the fractions of the population who are susceptible, infected, or recovered, respectively, at time $t$.

Additionally, assume that no one is born or dies from the disease, and a person can only be infected by the disease once. Thus,
>$0 \le S, I, R \le 1$ and $S+I+R=1.$

The state $\vec{x}$ evolves as an ODE, $D\vec{x}=\vec{f}(\vec{x})$, where
>$\vec{f}(\vec{x})=\begin{bmatrix} -\tau S(t)I(t) \\ \tau S(t)I(t) - \frac{I(t)}{\kappa} \\ \frac{I(t)}{\kappa} \end{bmatrix}.$

$\tau \ge 0$ measures how quickly the disease spreads (higher values corresponding to faster spread), while $\kappa > 0$ measures how long it takes an infected person to recover (higher values corresonding to longer recovery times).


## Summary

One can observe that decreasing the value of $\tau$ from 0.8 to 0.4 significantly reduces the peak of infection, $I(t)$. This is intuitive, as a slower spreading disease would not reach as much of the population as a quickly spreading disease would, as it would be more likely for the recovery rate to overtake the infection rate. The decreased value of $\tau$ also led to a later peak and longer stopping time. This can also be explained by intuition. Since the recovery rate scales off the magnitude of infection, a slower infection rate will also slow the uptick of the recovery rate.

Increasing the value of $\kappa$ from 4 to 8 increased both the peak magnitude of infection as well as the stopping time of the simulation. Since a higher $\kappa$ means a slower recovery time, $\kappa$ affects how quickly the recovery rate would be able to catch up to the infection rate. Early in the simulation, the infection rate increases relatively uncontested by the recovery rate, and thus is able to reach a higher peak. At the peak, the recovery rate is at its highest and the magnitude of infection falls relatively quickly. However, once $I(t)$ reaches small values, the recovery rate, which is positively correlated with $I(t)$, is even smaller. Thus, at small magnitudes of infection, the recovery rate is very slow, thus taking a longer time to pass the stopping threshold of $I(t)<10^{-4}$.

However, these trends might not apply for all values of $\tau$ and $\kappa$. One can imagine that a very slow spreading disease (low $\tau$) paired with very quick recovery time (low $\kappa$) might not exhibit a peak at all. Rather, the magnitude of infection might simply decrease from its initial condition, leading to a very quick stopping time.


## Public Policy Interpretation

When discussing the severity of an epidemic, there are two metrics we can measure it by: the total percentage of the population that will be affected by the disease (the “magnitude” of infection), and the time it will take for herd immunity to nullify its spreadability (the “stopping time” of the epidemic). These metrics do not always come hand in hand —  in some cases, decreasing the stopping time might increase the magnitude of infection. Thus, to prioritize public health and minimize the impact of the epidemic on the population, policy should be focused on reducing the magnitude of infection. There are two ways in which to do this: reducing how quickly the disease spreads and reducing the recovery time. While increasing funding towards vaccine and medication research would certainly aid with both goals, public policy can also affect our progress. Promoting masks, social distancing, and regular testing can reduce the rate of spread, while allowing students and workers to take sick time off would promote recovery speeds while minimizing contact between infected and susceptible individuals.