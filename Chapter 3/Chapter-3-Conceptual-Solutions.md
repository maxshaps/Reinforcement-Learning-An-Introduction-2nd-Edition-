# Chapter-3-Conceptual-Solutions

## Questions And Answers
Exercise 3.2: Is the MDP framework adequate to usefully represent all goal-directed learning tasks? Can you think of any clear exceptions?

The MDP framework assumes the Markov property, namely that the state includes information about all aspects of the past agent-environment interaction that make a difference for the future.  An MDP framework is not really appropriate for a goal-directed learning task for which this Markov property is not true (e.g., where path dependency in arriving at a state also makes a difference for the future).

Another situation that might be difficult for an MDP framework would be if the goal-directed learning task had multiple goals it was trying to accomplish.  In this case, instead of the reward being being a single scalar, the reward would be a multi-component vector; in this case, the reinforcement learning scheme would probably have to invoke some additional constraint in order to perform the optimization.

Exercise 3.6: Suppose you treated pole-balancing as an episodic task but also used discounting, with all rewards zero except for -1 upon failure. What then would the return be at each time? How does this return differ from that in the discounted, continuing formulation of this task?

As discussed in the text, in the discounted, continuing task formulation, the return at each time would be related to ![$-\gamma^K$](https://render.githubusercontent.com/render/math?math=%24-%5Cgamma%5EK%24), where ![$K$](https://render.githubusercontent.com/render/math?math=%24K%24) is the number of time steps before failure.  In the discounted, episodic task formulation, the return at each time is still related to ![$-\gamma^K$](https://render.githubusercontent.com/render/math?math=%24-%5Cgamma%5EK%24), but ![$K$](https://render.githubusercontent.com/render/math?math=%24K%24) is constrained to be less than or equal to the total number of time steps of an episode ![$T$](https://render.githubusercontent.com/render/math?math=%24T%24).  Thus, the main difference is that the episodic task has a strict cap on the maximum return (which is related to ![$-\gamma^T$](https://render.githubusercontent.com/render/math?math=%24-%5Cgamma%5ET%24)).
