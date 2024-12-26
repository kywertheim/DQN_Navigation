# Project details

I completed this guided programming exercise as a part of the Udacity course titled Value-Based Methods, a component of the Udacity nanodegree titled Deep Reinforcement Learning.

The code in this respository trains an agent to navigate an environment and collect bananas. The environment comprises a 37-dimensional state space and a four-dimensional action space. The state includes the agent's velocity and its ray-based perception of objects around its forward direction. There are four actions, which are moving forward, moving backward, turning left, and turning right. When an action takes the agent to a state where it collects a yellow banana, a reward of +1 is provided. If a blue banana is collected, a reward of -1 is provided.

The code trains the agent to select the best action in each state with the objective of collecting as many yellow bananas as possible while avoiding blue bananas. This learning task is episodic with a maximum number of transitions (time steps) in one episode. The user defines this maximum number and rewards accumulate over an episode to give an episodic score. Solving the environment means the trained agent can achieve an average score of at least 13 over 100 consecutive episodes.

# Getting Started

I completed the project in the Project Workspace provided by Udacity. To set up the environment on your own machine, you need to follow the instructions [here]([https://pages.github.com/](https://github.com/udacity/deep-reinforcement-learning/tree/master/p1_navigation#getting-started)). They are reproduced here.

1. Clone the Course GitHub repository and set up your Python environment. PyTorch, the ML-Agents toolkit, and a few more Python packages are required to complete the project. These steps can be completed by following the instructions [here](https://github.com/udacity/Value-based-methods#dependencies).

2. The environment is similar to the Banana Collector environment on the Unity ML-Agents GitHub page, but you don't need to download/install Unity because the environment can be downloaded from the links below. However, you need to select the link that matches your operating system: [Linux](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip), [Mac OSX](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip), [Windows (32-bit)](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip), and [Windows (64-bit)](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip). If you are a Windows user, the ML-Agents toolkit supports Windows 10.

3. Place the environment file in the `p1_navigation/` directory in the DRLND GitHub repository.
  
4. Unzip (or decompress) the environment file in the directory.

# Instructions

1. First, replace the `Navigation.ipynb` file in the `p1_navigation/` directory with the file with the same name in this GitHub repository. Second, download the `dqn_agent_variant.py` and `model.py` files from this GitHub repository and add them to the `p1_navigation/` directory.

2. Open the `Navigation.ipynb` file. It's a Jupyter notebook.

3. Update the PATH env var by modifying the first code cell in the notebook, reproduced here.

```
# Step 1. Update the PATH env var. 
import os
os.environ['PATH'] = f"{os.environ['PATH']}:/home/student/.local/bin"
os.environ['PATH'] = f"{os.environ['PATH']}:/opt/conda/lib/python3.10/site-packages"
os.environ['PROTOCOL_BUFFERS_PYTHON_IMPLEMENTATION'] = 'python'
```

4. The first few sections of the Jupyter notebook are exploratory.

5. In Section four, you train the agent. You can change the hyperparameters by providing different arguments for the function parameters, reproduced here. `n_episodes` is the maximum number of episodes before training ends, `max_t` is the maximum number of time steps (transitions) in one episode, `eps_start` is the starting probability of exploration (epsilon-greedy policy), `eps_end` is the minimum probability of exploration, and `eps_decay` is the multiplicative decay rate used to reduce the probability at the end of an episode.

```
scores, scores_window_mean = dqn(n_episodes=2000, max_t=300, eps_start=0.10, eps_end=0.01, eps_decay=0.987)
```  
