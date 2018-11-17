<img src="https://user-images.githubusercontent.com/10624937/42135623-e770e354-7d12-11e8-998d-29fc74429ca2.gif">

# DRL - Multi-Agent DDPG w/Prioritized Experience Replay - Tennis Collaboration

This implements the same Unity environment "Tennis" as in <a href="http://github.com/PHRABAL/DRL-Tennis">this repo</a>, but with Prioritized Experience Replay (PER).

In the previous implementation, the past experiences of the agents were collected and held in memory for them to randomly draw from during training. With PER, the experiences drawn are not random, but rather based on a prioritization scheme. This scheme  places more importance on experiences that make the most impact on training, namely experiences that produce results that diverge the most from the expected result.

Two new variables - alpha and beta - are introduced with PER. Alpha controls the level of prioritization used when drawing samples from memory and beta controls how much importance to give an experience's relative priority when updating the neural network weights during back propagation.

I did not find PER particularly effective in the Tennis MADDPG implementation. It achieved approximately the same results as the standard replay buffer used in the original implementation.
