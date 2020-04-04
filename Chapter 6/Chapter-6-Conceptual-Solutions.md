# Chapter-6-Conceptual-Solutions

## Questions And Answers
Exercise 6.3: From the results shown in the left graph of the random walk example it appears that the first episode results in a change
in only ![$V(A)$](https://render.githubusercontent.com/render/math?math=%24V(A)%24). What does this tell you about what happened on the first episode? Why was only the estimate for this one state changed?
By exactly how much was it changed?

For the MRP considered here, ![$V(S_t)$](https://render.githubusercontent.com/render/math?math=%24V(S_t)%24) is initialized to 0.5 for all nonterminal states, the task is undiscounted (i.e., ![$\gamma = 1$](https://render.githubusercontent.com/render/math?math=%24%5Cgamma%20%3D%201%24)),
the constant step-size parameter ![$\alpha = 0.1$](https://render.githubusercontent.com/render/math?math=%24%5Calpha%20%3D%200.1%24), and the only non-zero reward is +1 for episodes which terminate on the extreme right.

To answer what happened on the first episode, consider the TD(0) update rule given by equation (6.2):
![$V(S_t) \leftarrow V(S_t) + \alpha \left\[ R_{t+1} + \gamma V(S_{t+1}) - V(S_t) \right\]$](https://render.githubusercontent.com/render/math?math=%24V(S_t)%20%5Cleftarrow%20V(S_t)%20%2B%20%5Calpha%20%5Cleft%5B%20R_%7Bt%2B1%7D%20%2B%20%5Cgamma%20V(S_%7Bt%2B1%7D)%20-%20V(S_t)%20%5Cright%5D%24).  For all state transitions between nonterminal
states during the first episode, ![$R_{t+1} = 0$](https://render.githubusercontent.com/render/math?math=%24R_%7Bt%2B1%7D%20%3D%200%24) and ![$\gamma V(S_{t+1}) - V(S_t) = (1)0.5 - 0.5 = 0$](https://render.githubusercontent.com/render/math?math=%24%5Cgamma%20V(S_%7Bt%2B1%7D)%20-%20V(S_t)%20%3D%20(1)0.5%20-%200.5%20%3D%200%24), and thus the TD(0) update leaves the value function estimates for
those states unchanged.  The only exception is for ![$V(A)$](https://render.githubusercontent.com/render/math?math=%24V(A)%24); for the final step in the episode in which the agent transitions from state ![$A$](https://render.githubusercontent.com/render/math?math=%24A%24)
to the terminal state by moving left, the agent transitions from a state with ![$V(A)=0.5$](https://render.githubusercontent.com/render/math?math=%24V(A)%3D0.5%24) to a state with ![$V(\textrm{Terminal})=0$](https://render.githubusercontent.com/render/math?math=%24V(%5Ctextrm%7BTerminal%7D)%3D0%24) and
receives a reward of 0.  The TD(0) update for ![$V(A)$](https://render.githubusercontent.com/render/math?math=%24V(A)%24) then becomes
![$V(A) \leftarrow V(A) + \alpha \left\[ R_{t+1} + \gamma V(\textrm{Terminal}) - V(A) \right\] = 0.5 + (0.1) \left\[ 0 + (1)(0) - 0.5 \right\] = 0.45$](https://render.githubusercontent.com/render/math?math=%24V(A)%20%5Cleftarrow%20V(A)%20%2B%20%5Calpha%20%5Cleft%5B%20R_%7Bt%2B1%7D%20%2B%20%5Cgamma%20V(%5Ctextrm%7BTerminal%7D)%20-%20V(A)%20%5Cright%5D%20%3D%200.5%20%2B%20(0.1)%20%5Cleft%5B%200%20%2B%20(1)(0)%20-%200.5%20%5Cright%5D%20%3D%200.45%24),
in agreement with the figure.

Exercise 6.4: The specific results shown in the right graph of the random walk example are dependent on the value of the step-size parameter, ![$\alpha$](https://render.githubusercontent.com/render/math?math=%24%5Calpha%24). Do you think the conclusions about which algorithm is better would be affected if a wider range of ![$\alpha$](https://render.githubusercontent.com/render/math?math=%24%5Calpha%24) values were used? Is there a different, fixed value of ![$\alpha$](https://render.githubusercontent.com/render/math?math=%24%5Calpha%24) at which either algorithm would have performed
significantly better than shown? Why or why not?

For any fixed policy and a constant step-size parameter ![$\alpha$](https://render.githubusercontent.com/render/math?math=%24%5Calpha%24), TD(0) is only guaranteed to converge to the true value function values if ![$\alpha$](https://render.githubusercontent.com/render/math?math=%24%5Calpha%24) is sufficiently small.  I would guess that for very large ![$\alpha$](https://render.githubusercontent.com/render/math?math=%24%5Calpha%24) values, TD(0) may have convergence issues and thus underperform constant-![$\alpha$](https://render.githubusercontent.com/render/math?math=%24%5Calpha%24) MC.
