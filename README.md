# FinTech-using-the-AI-Gym-RL-Trading-Algorithms

I am using the AI-Gym environment provided by OpenAI to enforce several learning and control algorithms. AI Gym is a toolkit that exposes a series of high-level function calls to common environment simulations used to benchmark RL algorithms. In this Project to I am investigating at least two trading algorithms for a given data collected about the stocks of a given company.

There are five important steps in a sequence,
1. Install and import dependencies
2. Using Marketwatch GME Data
3. Building environment
4. Building proper environment and training the dataset
5. Evaluation

Overview:

1. Install and Import dependencies
We first install both the GPU version and tensorflow version 1.15.0. The next
installation is stable-baselines which gives various algorithms for reinforced
learning (RL) followed by gym-anytrading which sets up the training environment
and finally gym which provides us with an open AI gym which is the base where
gym-anytrading is built on.

Once the installation is complete, we need to import other dependencies needed for
the project. First we need to import gym and gym_anytrading which will set up the
open AI gym environment. This helps us to train the system to learn how to trade.
After this we need to set up the reinforced learning environment containing the
algorithms required for the project. We import the dummy vector environment
which is a wrapper which re wraps the whole trading environment. Then we import
the A2C algorithm which we need for our reinforced learning. Followed by some
processing libraries that we need such as numpy, pandas and matplotlib.

2. Using Marketwatch GME Data

In this step, the GME dataset which is being used is imported by adding the correct
path and reading it we need to set it up for trading. Post this we use pandas and the
date is changed to date time function to make it work with the gym-anytrading
environment. Then we overwrite the existing date column and enter the converted
format. After the overwrite is complete we need to set it as an index and pass it into
the trading environment. We use frame_bound to set the part of the data set we
need to use making sure the initial value matches with the window size for the
bounded frame.

3. Building Environment

The environment which initializes the environment is reset and then tested for total
rewards and the total profits randomly. We visualize the outcome using matplotlib,
this helps us visualize the plot of the outcome which is given in the Output1
screenshot.

4. Building proper Environment and Training the data set
First step is to wrap the dataset in the dummy vector environment. We have to
include the window size and the bounded frame again within the dummy
environment.
After we have made the environment we write the A2C algorithm to train our data
set where we use multilayer perceptron lstm policy which is a deep neural network
that has a lstm layer which allows neural network to retain information to learn
about previous history and try to predict the next outcome. Then this shows our
train dataset and how it looks with all the relevant information. In the outcome
values closer to 1 is better. We can stop the model if we want when we get a value
closer to 1.

5. Evaluation
We finally test out the model and check its performance by creating a new
environment to perform the test on. Here we change the data time frame to test the
performance to overlap with the training sets to compare its performance by
specifying the actions to let us know whether to buy, sell or hold instead of random
actions. We also reshape it using numpy to work with a non vectorized
environment. Then we pass the observation through a predictive function, this
enables the model to predict the outcome along with the actions that we need to
take.
After the output is generated we can decide what action to take according to the
predicted outcome.
