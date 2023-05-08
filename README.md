# Grokking Deep Reinforcement Learning

**Note:** At the moment, only running the code from the [docker](https://github.com/docker/docker-ce) container (below) is supported. Docker allows for creating a single environment that is more likely to work on all systems. Basically, I install and configure all packages for you, except docker itself, and you just run the code on a tested environment. 

To install docker, I recommend a web search for "installing docker on \<your os here>". For running the code on a GPU, you have to additionally install [nvidia-docker](https://github.com/NVIDIA/nvidia-docker). NVIDIA Docker allows for using a host's GPUs inside docker containers. After you have docker (and nvidia-docker if using a GPU) installed, follow the three steps below. 

## Running the code
  0. Clone this repo:  
  `git clone --depth 1 https://github.com/JaninaPa/rl_course_dhbw-ma.git && cd gdrl`
  1. Pull the gdrl image with:  
  `docker pull mimoralea/gdrl:v0.14`
  2. Spin up a container:
     - On Mac or Linux:  
     `docker run -it --rm -p 8888:8888 -v "$PWD"/notebooks/:/mnt/notebooks/ mimoralea/gdrl:v0.14` 
     - On Windows:  
     `docker run -it --rm -p 8888:8888 -v %CD%/notebooks/:/mnt/notebooks/ mimoralea/gdrl:v0.14`
     - NOTE: Use `nvidia-docker` or add `--gpus all` after `--rm` to the command, if you are using a GPU.
  3. Open a browser and go to the URL shown in the terminal (likely to be: http://localhost:8888). The password is: `gdrl`

## About the lecture

### Book's website

https://www.manning.com/books/grokking-deep-reinforcement-learning

### Helpful package documentations

https://www.gymlibrary.dev/ (NOTE: This code uses an older version of the OpenAI Gym framework. The recent version is documented under https://gymnasium.farama.org/)
https://pytorch.org/docs/stable/index.html 

### Table of content

  1. [Introduction to deep reinforcement learning](#1-introduction-to-deep-reinforcement-learning)
  2. [Mathematical foundation](#2-mathematical-foundations-of-reinforcement-learning)
  3. [Exploration vs. exploitation](#3-exploration-vs-exploitation)
  4. [Policy evaluation](#4-policy-evaluation)
  5. [Policy improvement](#5-policy-improvement)
  6. [Optimization and model-based methods](#6-optimization-and-model-based-reinforcement-learning)
  7. [Value-based deep reinforcement learning](#7-value-based-deep-reinforcement-learning)
  8. [Policy-gradient and actor-critic methods](#8-policy-gradient-and-actor-critic-reinforcement-learning)
  9. [Course reflection](#-course-reflection)

### Detailed table of content

#### 1. Introduction to deep reinforcement learning
- \(No Notebook\)
      
#### 2. Mathematical foundations of reinforcement learning
- \([Notebook](/notebooks/chapter_02/chapter-02.ipynb)\)
  - Implementations of several MDPs: 
    - Bandit Walk
    - Bandit Slippery Walk
    - Slippery Walk Three
    - Random Walk
    - Russell and Norvig's Gridworld from AIMA
    - FrozenLake
    - FrozenLake8x8
- \([Notebook](/notebooks/chapter_03/chapter-03.ipynb)\) 
    - Policy Evaluation
    - Policy Improvement
    - Policy Iteration
    - Value Iteration
   
#### 3. Exploration vs. exploitation
- \([Notebook](/notebooks/chapter_04/chapter-04.ipynb)\)
  - Implementations of exploration strategies for bandit problems:
    - Random
    - Greedy
    - E-greedy
    - E-greedy with linearly decaying epsilon
    - E-greedy with exponentially decaying epsilon
    - Optimistic initialization
    - SoftMax
    - Upper Confidence Bound
    - Bayesian
    
#### 4. Policy evaluation
- \([Notebook](/notebooks/chapter_05/chapter-05.ipynb)\)
  - Implementation of algorithms that solve the prediction problem (policy estimation):
    - On-policy first-visit Monte-Carlo prediction
    - On-policy every-visit Monte-Carlo prediction
    - Temporal-Difference prediction (TD)
    - n-step Temporal-Difference prediction (n-step TD)
    - TD(λ)
#### 5. Policy improvement
- \([Notebook](/notebooks/chapter_06/chapter-06.ipynb)\)
  - Implementation of algorithms that solve the control problem (policy improvement):
    - On-policy first-visit Monte-Carlo control
    - On-policy every-visit Monte-Carlo control
    - On-policy TD control: SARSA
    - Off-policy TD control: Q-Learning
    - Double Q-Learning
#### 6. Optimization and model-based reinforcement learning
- \([Notebook](/notebooks/chapter_07/chapter-07.ipynb)\)
  - Implementation of more effective and efficient reinforcement learning algorithms:
    - SARSA(λ) with replacing traces
    - SARSA(λ) with accumulating traces
    - Q(λ) with replacing traces
    - Q(λ) with accumulating traces
    - Dyna-Q
    - Trajectory Sampling
#### 7. Value-based deep reinforcement learning
- \([Livebook](https://livebook.manning.com/book/grokking-deep-reinforcement-learning/chapter-8)\)
- \([Notebook](/notebooks/chapter_08/chapter-08.ipynb)\)
  - Implementation of a value-based deep reinforcement learning baseline:
    - Neural Fitted Q-iteration (NFQ)
- \([Notebook](/notebooks/chapter_09/chapter-09.ipynb)\)
  - Implementation of "classic" value-based deep reinforcement learning methods:
    - Deep Q-Networks (DQN)
    - Double Deep Q-Networks (DDQN)
- \([Notebook](/notebooks/chapter_10/chapter-10.ipynb)\)
  - Implementation of main improvements for value-based deep reinforcement learning methods:
    - Dueling Deep Q-Networks (Dueling DQN)
    - Prioritized Experience Replay (PER)
#### 8. Policy-gradient and actor-critic reinforcement learning
- \([Notebook](/notebooks/chapter_11/chapter-11.ipynb)\)
  - Implementation of classic policy-based and actor-critic deep reinforcement learning methods:
    - Policy Gradients without value function and Monte-Carlo returns (REINFORCE)
    - Policy Gradients with value function baseline trained with Monte-Carlo returns (VPG)  
    - Asynchronous Advantage Actor-Critic (A3C)
    - Generalized Advantage Estimation (GAE)
    - \[Synchronous\] Advantage Actor-Critic (A2C)
- \([Notebook](/notebooks/chapter_12/chapter-12.ipynb)\)
  - Implementation of advanced actor-critic methods:
    - Deep Deterministic Policy Gradient (DDPG)
    - Twin Delayed Deep Deterministic Policy Gradient (TD3)
    - Soft Actor-Critic (SAC)
    - Proximal Policy Optimization (PPO)
#### 9. Course reflection
- \(No Notebook\)
