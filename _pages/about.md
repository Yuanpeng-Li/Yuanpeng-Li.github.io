---
permalink: /
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am a second-year Ph.D. student in Statistics at UC Irvine, advised by Prof. [Annie Qu](https://qu.pstat.ucsb.edu/) and Prof. [Rui Miao](https://rui-miao.github.io/). I received my B.S. in Mathematics and Applied Mathematics from Jilin University in 2024.

My research is in **reinforcement learning** — especially **multi-task RL** — and **large language models**. I'm drawn to understanding why standard methods quietly break down in these settings, and to designing principled, lightweight fixes.

My recent first-author work, *TOPPO* (under review), diagnoses critic-side gradient ill-conditioning as a previously overlooked bottleneck of PPO in multi-task RL and introduces *Critic Balancing* — per-task PopArt value normalization, pre-activation LayerNorm in the critic body, and per-side gradient combiners (PCGrad / CAGrad / FairGrad chosen independently for actor and critic) — surpassing published SAC- and ARS-family baselines on Meta-World+ MT50 with up to 22.7× fewer parameters.

Since May 2026 I have also begun an early-stage second direction: **multi-objective reinforcement learning for LLM post-training** (*Probe-FairGRPO*). The project recasts multi-reward GRPO fine-tuning as multi-task RL, combining a lightweight gradient-conflict probe with FairGrad-style weighting to adaptively balance reward objectives by down-weighting conflicts and up-weighting alignment.

Outside of research, I serve as a graduate teaching assistant at UCI (STATS 7, 67, 110, 120C, 205P), and I enjoy building practical tooling — for example, [`gradescope-mcp`](https://github.com/Yuanpeng-Li/gradescope-mcp), an open-source MCP server that exposes 34 grading and course-management tools to AI assistants under a human-approved "preview-first" write protocol, and [StudyGround](https://github.com/Yuanpeng-Li/StudyGround), a Claude Code plugin for AI-assisted self-study.
