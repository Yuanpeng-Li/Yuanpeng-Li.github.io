---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

PDF: [English](/files/cv_en.pdf) &nbsp;·&nbsp; [中文 (Chinese)](/files/cv_zh.pdf)

Education
======
* **University of California, Irvine**, Irvine, CA &nbsp; *Sep. 2024 – May 2028 (expected)*
  * *Doctor of Philosophy (PhD) in Statistics; Advisors: Prof. [Annie Qu](https://qu.pstat.ucsb.edu/), Prof. [Rui Miao](https://rui-miao.github.io/)*
* **Jilin University – School of Mathematics**, Changchun, China &nbsp; *Aug. 2020 – Jun. 2024*
  * *B.S. in Mathematics and Applied Mathematics*

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

Research experience
======
* **[TOPPO: Rethinking PPO for Multi-Task RL with Critic Balancing](https://arxiv.org/abs/2605.11473)** \[[code](https://github.com/NAIVlab/TOPPO)\], Irvine, CA &nbsp; *Apr. 2026*
  * *First author; accepted at NeurIPS 2026; Advisors: Prof. Annie Qu, Prof. Rui Miao*
  * Identified ill-conditioned critic gradients as the key bottleneck in multi-task PPO: easy tasks dominate the critic and hard tasks stall.
  * Proposed Critic Balancing (per-task PopArt, LayerNorm critic, FairGrad on the critic, PCGrad on the actor), proved that FairGrad's α=1 update is unchanged by positive per-task gradient rescaling, and developed a projected Newton solver 83× faster than SciPy.
  * Set a new state of the art on Meta-World+ MT50 (90.9% mean, 56.5% worst-10-task success) over the strongest baseline, ARS-LN-1024 (85.7%, 43.3%), with 22.7× fewer parameters, reaching the baseline's final mean in 28% of the steps.
  * Extended Critic Balancing to a two-objective AMP humanoid task, cutting motion-style FID by 76%.

* **Scaling TOPPO to Large Models: VLA and LLM RL**, Irvine, CA &nbsp; *Sep. 2026*
  * *Advisors: Prof. Annie Qu, Prof. Rui Miao*
  * Set up RL fine-tuning of a 3.3B π<sub>0</sub> VLA model with RLinf, and built a GRPO/PPO pipeline for LLMs on verl, vLLM and FSDP2, with a Nemotron-3-Super-120B judge self-hosted on vLLM as the reward model.
  * Standard whole-network gradient surgery gave no clear gain on π<sub>0</sub> or LLMs, which led to the block-wise study below.

* **Block-Wise Gradient Balancing for Deep Multi-Task Networks**, Irvine, CA &nbsp; *Ongoing*
  * *Advisors: Prof. Annie Qu, Prof. Rui Miao*
  * Benchmarked 26 multi-task gradient methods in one PyTorch trainer, reproducing published NYUv2, CelebA and QM9 results.
  * Found that a few small early layers carry most of the gradient, so the whole-network Gram matrix FairGrad uses to weight tasks mostly reflects them; yet on QM9 the energy targets' gradients differ only in the final readout layer, which this matrix barely sees.
  * Proposed a norm-induced block kernel that balances each module's contribution to FairGrad's task weights. On a QM9 graph transformer it cut Δm% (average gap to single-task models) from 27.7 to 9.6.

* **Runtime-Aware HPC Job Scheduling**, Irvine, CA &nbsp; *Ongoing*
  * *With Prof. Rui Miao*
  * Wrote slurmsim, a Python/C Slurm simulator matching real Slurm's job start order and 99.9% of sampled priorities exactly.
  * Set each job's `--time-min`, which backfill plans with, from a Kaplan–Meier runtime estimate, keeping the user's limit as the hard cap; mean turnaround fell 8–18% in simulation and 8% in a national-lab trace replay, with almost no extra timeouts.

Projects
======
* **[RunFleet](https://github.com/Yuanpeng-Li/runfleet)** & **[Run-Skills](https://github.com/NAIVlab/run-skills)** \| *Python, Bash, Slurm, MCP*
  * Built a terminal dashboard for jobs and GPUs across Slurm clusters over SSH, plus skills that let coding agents submit jobs.
* **[Gradescope MCP](https://github.com/Yuanpeng-Li/gradescope-mcp)** \| *Python, MCP, uv*
  * Built an MCP server that lets AI agents grade and edit Gradescope rubrics; every write is previewed and approved by a person.

Teaching
======
* **Graduate Teaching Assistant**, UC Irvine Statistics *(Sep. 2024 – Present)*: STATS 7, 67, 110, 120C, 205P.

Awards
======
* UC Irvine Statistics **Graduate Travel Award**, $2,500 (2026)
* Chinese Mathematics Competitions **National 3rd Prize** (2021)

Skills
======
* **Methods:** Reinforcement learning (PPO, GRPO), RLHF/RLAIF, multi-task learning (PCGrad, FairGrad, MGDA), LoRA/PEFT
* **ML Frameworks & Tooling:** PyTorch, Hugging Face, vLLM, verl, FSDP, RLinf; MCP servers, Claude Code / Codex skills
* **Infra & Engineering:** Python, C, Git, Docker, Linux, Slurm, Ray, W&B, uv, pytest
