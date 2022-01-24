# Continuous_Control_using_Reinforcement_Learning

This repository presents a solution to the Unity "Reacher" environment based upon a Deep Deterministic Policy Gradient approach.

# Environment
The environment is a simulated set of 20 robot arms, where the objective is to mainitain the position of each arm in the target location.  The reward function is +0.1 per time step in which the arm is at the target location, 0 when it is anywhere else.  The observation space has 33 variables for position, rotations, velocities, and angular velocities for each robot arm.  The action space is a set of four real numbers [-1, +1] corresponding to the torques applied at each of two joints on the arm.  The environment is considered "solved" when the 100 episode average score over all 20 arms is above 30.0.

# Getting Started 
This section was copied from https://github.com/kimkevin711/drlp2_continuouscontrol/blob/master/README.md because it's the same for all of us & there's no point in reinventing the wheel.

1. Download the environment from one of the links below.  You need only select the environment that matches your operating system:

    - **_Version 1: One (1) Agent_**
        - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip)
        - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
        - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
        - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)

    - **_Version 2: Twenty (20) Agents_**
        - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
        - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)
        - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
        - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip) (version 1) or [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux_NoVis.zip) (version 2) to obtain the "headless" version of the environment.  You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)

2. Place the file in the DRLND GitHub repository, in the `p2_continuous-control/` folder, and unzip (or decompress) the file. 

# Using the Notebook
Once you have the environment set up, follow the main notebook, Continuous_Control.ipynb, in this repository.  Control the version number by changing the relevant term, v, in the hyperparameter cell.  The training loop automatically creates a saved agent file when done training, with a pather name dependent on the version number and how many training episodes it has undergone.  In addition, the training loop outputs an entry in a JSON file storing the version number, the path to the saved agent file, the set of hyperparameters used to train it, and the final individual episode score, as well as the number of seconds it took to train it.  
A word of caution: an Agent can be partially trained and then restarted by initializing an agent with a filename pointing to a saved agent, but Agent will be using the *new* hyperparameters *including the version number*, hyperparameters are only saved in the JSON, NOT in the .tar file.  This means if you want to use multiple sets of hyperparameters consecutively on the same Agent you can, but you will have to be careful & deliberate about bookkeeping.  It wouldn't be that much more work to automate the bookkeeping to enable more creative & expansive agent testing, but I have not done so at this time.

