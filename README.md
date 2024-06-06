# Deep Q-Learning for Geometry Dash
---
This project a CNN learn to play Geometry Dash using Deep Q-Learning. 

## Requirements
---
Use the requirements.txt to install all the dependencies. You will also need to use an NVIDIA GPU, and CUDA (as well as pytorh-cuda), as it is necessary to process the information fast enough to decide in "real time".

## Architecture
---
This project consists of the following structures:
- `Capture screen`: a function that takes a screenshot of the game, and transforms it into a tensor.
- `Bounty`: analyzing the screenshot, decide if the character is still alive, or has crashed or terminated, so that it gives or subtracts points.
- `CNN`: analyzing the screenshot, predict if jump or not.
- `Policy`: using a e-greedy policy.
- `Deep Q-Learning`: during the training phase, the weights of the model will be updated based on the reward obtained, every 32 (configurable) screenshots or minibatches. This involves using a replay buffer to store state transitions, which are then sampled in minibatches to update the network weights via backpropagation. The update frequency and size of the minibatches can be configured based on performance and computational constraints.
