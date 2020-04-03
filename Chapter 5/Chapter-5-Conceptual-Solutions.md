# Chapter-5-Conceptual-Solutions

## Questions And Answers
Exercise 5.5: Consider an MDP with a single nonterminal state and a single action that transitions back to the nonterminal state with probability ![$p$](https://render.githubusercontent.com/render/math?math=%24p%24) and transitions to the terminal state with probability ![$1-p$](https://render.githubusercontent.com/render/math?math=%241-p%24). Let the reward be +1 on all transitions, and let ![$\gamma=1$](https://render.githubusercontent.com/render/math?math=%24%5Cgamma%3D1%24). Suppose you observe one episode that lasts 10 steps, with a return of 10. What are the first-visit and every-visit estimators of the value of the nonterminal state?

The first-visit MC method estimates the value of the nonterminal state as the average of the returns following the first visit to the nonterminal state.  After visiting the nonterminal state for the first time, the episode elapses and results in a return of 10. This was the only observed episode, and so the first-visit MC method estimates the value of the nonterminal state as the average of {10}, which is just 10.

The every-visit MC method estimates the value of the nonterminal state as the average of the returns following all visits to the nonterminal state.  Following the 10th visit to the nonterminal state, a return of 1 is received; following the 9th visit to the nonterminal state, a return of 2 is received; and so on. The average of the returns following all visits to the nonterminal state is thus the average of {1, 2, 3, 4, 5, 6, 7, 8, 9, 10} = 5.5.
