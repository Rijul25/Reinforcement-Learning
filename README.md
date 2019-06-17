# Reinforcement-Learning
Developing Algorithms to play games such as Cartpole , Mountain car.

Reinforcement learning is an area of Machine Learning. Reinforcement. It is about taking suitable action to maximize reward in a particular situation. It is employed by various software and machines to find the best possible behavior or path it should take in a specific situation.

## Main points in Reinforcement learning –
1.Input: The input should be an initial state from which the model will start
2.Output: There are many possible output as there are variety of solution to a particular problem
3.Training: The training is based upon the input, The model will return a state and the user will decide to reward or punish the model based on its output.
4.The model keeps continues to learn.
5.The best solution is decided based on the maximum reward.

# Installing Gym
## pip install gym

### Gym is a toolkit for developing and comparing reinforcement learning algorithms. It supports teaching agents everything from walking to playing games like Pong or Pinball.

Gym is a toolkit for developing and comparing reinforcement learning algorithms. It supports teaching agents everything from walking to playing games like Pong or Pinball.

## You can install Gym by cloning
https://github.com/openai/gym

You'll be able to run a few environments right away:

### algorithmic
### toy_text
### classic_control (you'll need pyglet to render though)


# Playing games using your DQN Agent
import gym
env = gym.make("CartPole-v1")
observation = env.reset()
for _ in range(1000):
  env.render()
  action = env.action_space.sample() # your agent here (this takes random actions)
  observation, reward, done, info = env.step(action)

  if done:
    observation = env.reset()
env.close()


### To train your own DQN Agent you need to follow the following steps:-

1. Create your agent
 __init__(self,state_size,action_size,game='Catrpole-v0')
 
 state_size   :  number of variables representing the state of the environment.
                if None, then automatically gets the value depending upon the environment.
 action_size  :  total number of possible actions that the agent can take.
                if None, then automatically gets the value depending upon the environment.
 max_steps    :  maximum allowed steps in an episode of the game.
 game         :  name of the game environment to be loaded from the gym module.
 
 2. Train the agent
 def train_agent(self,n_episodes=1000,batch_size=32,load_prev_best=True)
 
 n_episodes     :  no. of episodes to be played.
 render         :  whether to render and display the game or not.
 batch_size     :  no. of samples to be taken from agent's memory to train the NN after each episode.
 load_prev_best :  True : loads the previous best model saved .
                   False : Does nothing.
                   
 3. Remember the previos state 
 It takes the following parameters
 self,state,action,reward,next_state,done.
 #### state = current state we are in
 #### action = 0 or 1 
 #### reward = reward after each action has taken on a given state
 #### next_state = reaching state s1 using a1 action on state s0
 #### done = True or false depending whether we have completed the game or not.
 
