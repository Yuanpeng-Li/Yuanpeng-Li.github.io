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
* **Ph.D. in Statistics**, University of California, Irvine — Sep. 2024 – Present
* **B.S. in Mathematics and Applied Mathematics**, Jilin University — Aug. 2020 – Jul. 2024

Manuscripts
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

Research experience
======
* **Probe-FairGRPO: Multi-Objective RL Fine-Tuning for LLM Post-Training** &nbsp; *(May 2026 – Present)*
  * Graduate Researcher, UC Irvine. Brings fair-gradient combination (FairGrad) into LLM post-training by reframing multi-reward GRPO fine-tuning (correctness / format / length rewards) as multi-task RL.
  * A lightweight gradient *probe* builds a per-reward K×K Gram matrix (over lm-head / last layers / LoRA) to cheaply estimate inter-objective gradient conflict; a FairGrad solver turns it into adaptive per-reward weights that down-weight conflicting and up-weight aligned objectives.
  * Clipping each reward's GRPO loss independently before weighting lets a single scalar backward preserve the exact weighted gradient under PPO/GRPO clipping (unit-test-verified against the biased mix-then-clip alternative).
  * Reproducible stack: framework-agnostic CPU core (65 unit tests) + a verl 0.8 / vLLM / FSDP adapter; experiments configured on Qwen2.5-0.5B/7B and Llama-3.1-8B-Instruct over GSM8K / DAPO-Math training with AIME / MATH-500 / OlympiadBench / AMC23 / GPQA evaluation. *(Method and training stack in place; comparative results pending.)*

* **TOPPO: Rethinking PPO for Multi-Task Reinforcement Learning with Critic Balancing** &nbsp; *(Jul. 2023 – Apr. 2026)*
  * First author. Advisors: Prof. [Annie Qu](https://qu.pstat.ucsb.edu/), Prof. [Rui Miao](https://rui-miao.github.io/) (corresponding). University of California, Irvine.
  * Diagnosed critic-side gradient ill-conditioning as a previously overlooked bottleneck of PPO in multi-task reinforcement learning, where tail tasks stall while easy tasks dominate value-function updates.
  * Designed *Critic Balancing* for PPO — per-task PopArt value normalization, pre-activation LayerNorm in the critic body, and per-side gradient combiners (PCGrad / CAGrad / FairGrad chosen independently for actor and critic) — to recondition gradients without enlarging the model.
  * On Meta-World+ MT50, surpassed published SAC- and ARS-family baselines on both mean and worst-*k* tail-task success while using up to 22.7× fewer parameters and substantially fewer environment steps.

Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

Internship experience
======
* **AI Research Intern**, Synkrotron, Xi'an, China &nbsp; *(Dec. 2022 – Jan. 2023)*
  * Configured remote Linux devices (via FRP) for an automated road-patrol pipeline and studied computer-generated simulation datasets to improve real-world autonomous-driving test performance.

Awards
======
* Scholarship, academic year 2022–2023 — Oct. 2023
* Chinese Mathematics Competitions: National 3rd Prize — Dec. 2021
* Jilin Province Mathematics Competitions: Provincial 2nd Prize — Dec. 2021

Skills
======
* **LLM post-training & RL:** PyTorch, Hugging Face Transformers, vLLM, verl, FSDP, PPO/GRPO, RLHF/RLAIF, LoRA/PEFT
* **Agent & retrieval tooling:** Model Context Protocol (MCP), RAG, BM25, vector search, Claude Code Plugin, Pyodide
* **Infra & engineering:** Python, C, Git, Docker, Linux, SLURM, Ray, W&B, uv, pytest, remote-cluster training
