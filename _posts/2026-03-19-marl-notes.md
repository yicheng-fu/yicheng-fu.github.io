---
title: "Multi-Agent Reinforcement Learning Notes"
date: 2026-03-19
permalink: /posts/2026/03/marl-notes/
tags:
  - multi-agent reinforcement learning
  - reinforcement learning
  - notes
---

## Survey

**Multiagent Systems: A Survey from a Machine Learning Perspective. Autonomous Robotics. 2000.**
- 8 Reasons to use MAS: some domains require it, parallelism, robustness, scalability, simpler programming, to study intelligence, geographic distribution, cost effectiveness
- Homogeneous Agents：相同的目标、领域知识、可执行动作、策略
- homogeneous non-communicating agents（sec 4）
	- 反应式（reactive）无内部状态、无记忆、无推理，输入直接映射输出；慎思式（Deliberative）有状态、会预测、会搜索、会规划
	- 给智能体**全局信息**未必更好。若所有智能体都看到全局，会同时冲向最优资源，造成冲突。只给局部视野，反而自然分散、更协调。（Ignorance is Bliss）
	- 建模其他智能体状态，不需要建模太深，知道刚刚好就行
	- 无通信下如何影响他人
	- future：学习 “赋能他人”；学习预测其他智能体的感知与状态
- heterogeneous non-communicating agents（sec 5）
	- Benevolence（善意）vs. competitiveness（对抗）：即使自私智能体，反复交互后也会出现合作
	- Stable vs. evolving agents
	- Modeling of others’ goals, actions, and knowledge
	- Resource management
	- Social conventions（社会惯例）：即使不交流，也会共同选择“惯例”
	- Roles：角色分工
	- future：竞争场景的credit assignment；学习能和团队配合的行为；准确预测他人行为；动态角色学习
- homogeneous communicating agents（sec 6）
	- Distributed sensing
	- Communication content
	- future：What and when to communicate
- heterogeneous communicating agents（sec 7）
	- Understanding each other：采用相同通信语言
	- Planning communicative acts
	- Benevolence vs. competitiveness
	- Negotiation
	- Resource management (schedule coordination)
	- Commitment/decommitment
	- Collaborative localization：协同定位
	- Changing shape and size
	- future：Evolving language；Effects of speech acts on global dynamics；Communication utility and truthfulness；Commitment utility


**A survey and critique of multiagent deep reinforcement learning. AAMAS. 2019.**
- category (sec 3)
	- Analysis of emergent behaviors：用常见的MARL算法分析涌现行为
	- learning communication：通过protocol分享信息，包括RIAL、DIAL、CommNet
	- learning cooperation：多智能体合作，包括Parameter sharing、MADDPG、FTW、COMA、VDN、QMIX

