# OpenAI Gym - MountainCar: Alternative reward function for a random agent
I've started playing with OpenAI's Gym for training reinforcement learning algorithms. 

I noticed that for the mountain car environment, the reward value is simply -1 on every step until the maximum number of iterations is hit, or the termination condition is met (the cart gets to the flag). This has meant that my very simple algorithms have been unable to complete the task. It seems I'm not alone: 
https://www.reddit.com/r/learnmachinelearning/comments/63a30j/unable_to_solve_the_mountain_car_problem_from/
https://www.reddit.com/r/MachineLearning/comments/67fqv8/da3c_performs_badly_in_mountain_car/

This script shows a very simple agent that uses an alteration to the given reward function. The reward function I used was simply the value of the cart's position (i.e. the distance to the right) at each step, obtained as 'observation[0]'. The gifs below show how the agent is able to train more easily by using this altered reward function.

The agent here simply takes actions at random at each step (using a random integer to select left, right, or neutral). At the end of each episode it takes its 'total reward' as the greatest reward achieved at any step (i.e. the furthest distance it reached to the right). Then after completing n episodes, the best 'total reward' is taken, along with the actions it took on this episode.

Result with original reward: 

![gameplay video](https://github.com/JonnyEvans321/OpenAI_Gym_MountainCar/blob/master/org_reward.gif)

Result with alternative reward:

![gameplay video](https://github.com/JonnyEvans321/OpenAI_Gym_MountainCar/blob/master/alt_reward.gif)
