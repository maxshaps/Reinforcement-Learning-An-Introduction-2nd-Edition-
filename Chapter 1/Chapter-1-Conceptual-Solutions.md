# Chapter-1-Conceptual-Solutions

## Questions And Answers
Exercise 1.1 (Self-Play): Suppose, instead of playing against a random opponent, the reinforcement learning algorithm described above played against itself, with both sides learning. What do you think would happen in this case? Would it learn a different policy for selecting moves?

The reinforcement learning algorithm might learn a style of gameplay that can defeat an adaptive opponent.  The reinforcement algorithm might also learn a style of gameplay in which both opponents cooperate in order to facilitate winning.  Ideally, the learning process would find the former equilibrium. 

Exercise 1.2 (Symmetries): Many tic-tac-toe positions appear different but are really the same because of symmetries. How might we amend the learning process described above to take advantage of this? In what ways would this change improve the learning process? Now think again. Suppose the opponent did not take advantage of symmetries. In that case, should we? Is it true, then, that symmetrically equivalent positions should necessarily have the same value?

Mapping states/actions onto their symmetrical partners decreases the dimension of available states and actions, which decreases the mathematical complexity in finding the optimal gameplay policy and increases our confidence that the solution learned by the reinforcement algorithm is optimal.

In the event of an opponent who did not take advantage of symmetry, the reinforcement learning algorithm should likewise eschew enforcing symmetry; the long-run performance of the reinforcement learning algorithm is maximized when the learning is done against a realistic opponent.

Exercise 1.3 (Greedy Play): Suppose the reinforcement learning player was greedy, that is, it always played the move that brought it to the position that it rated the best. Might it learn to play better, or worse, than a nongreedy player? What problems might occur?

In general, the greedy reinforcement learning player will play worse than a nongreedy player because, by virtue of being greedy, the greedy player will not explore all possible actions and therefore fail to find untested actions that result in higher long-term rewards.

Exercise 1.4 (Learning from Exploration): Suppose learning updates occurred after all moves, including exploratory moves. If the step-size parameter is appropriately reduced over time (but not the tendency to explore), then the state values would converge to a different set of probabilities. What (conceptually) are the two sets of probabilities computed when we do, and when we do not, learn from exploratory moves? Assuming that we do continue to make exploratory moves, which set of probabilities might be better to learn? Which would result in more wins?

If we learn from exploratory moves, then the probabilities sampled for learning reflect the entire state/action space.  If we do not learn from exploratory moves, then the probabilities sampled for learning only reflect the known state/action space.  If the reinforcement learning algorithm is initialized with zero knowledge of the state/action space, then failing to learn from exploratory moves results in an algorithm that is effectively random.  Better play is expected from the reinforcement learning algorithm that learns from exploratory moves.

Exercise 1.5 (Other Improvements): Can you think of other ways to improve the reinforcement learning player? Can you think of any better way to solve the tic-tac-toe problem as posed?

Learning might be expedited by initializing the reinforcement algorithm with state/action pairs derived from real gameplay or experts.
