---
title: "Model-Based Reinforcement Learning Notes"
date: 2026-03-19
permalink: /posts/2026/03/mbrl-notes/
tags:
  - model-based reinforcement learning
  - reinforcement learning
  - notes
---

##### when the model is known: optimal control and planning

the deterministic case
the stochastic case
- open-loop: observe s1 and take a1,...,aT -- route-based
- cloased-loop: observe a st and take a at -- en-route


##### When the model is unknown: model-based reinforcement learning

- first learn the model
- then learn the policy


##### World Model

- Transformers are sample-efficient world models
	- sample efficiency is a necessary condition to bridge the gap between research and the deployment of deep RL agents in the wild
	- the best Atari agent learning in imagination is DreamerV2 (Hafner et al., 2021), although it was developed and evaluated with two hundred million frames available, far from the sample-efficient regime. Therefore, designing new world model architectures, capable of handling visually complex and partially observable environments with few samples, is key to realize their potential as surrogate training grounds.
- Dreamer系列



参考资料：
https://zhuanlan.zhihu.com/p/617887001
https://zhuanlan.zhihu.com/p/21206144773

### V0-ICML2019: Learning Latent Dynamics for Planning from Pixels
---
#### 研究背景与动机
MBRL（或基于模型的Planning）相较于MFRL的优势：
- Data efficiency
- Planning carries the promise of increasing performance just by increasing the computational budget for searching for actions
- Learned dynamics can be independent of any specific task and thus have the potential to transfer well to other tasks in the environment

现有工作在低维环境中的已经能取得较好表现，但是这些工作假设知道state和reward function。如何在**高维**的Pixel空间中准确的预测未来的动态依然是一个困难的问题，因此本文希望在紧凑的潜在空间中学习动态，用于快速planning。
#### 研究内容与核心贡献
##### Latent space planning
- 问题建模为POMDP（Partially observable Markov decision process）：agent只能观测到部分信息（一张图片，并不能揭示整个环境的状态）

