---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

A PDF version is available [here](/files/cv.pdf).

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
* **TOPPO: Rethinking PPO for Multi-Task Reinforcement Learning with Critic Balancing** &nbsp; *(Jul. 2023 – Present)*
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
  * Configured remote Linux devices through FRP for an automated road patrol project.
  * Surveyed AI/CV history and frameworks for an AI science teaching project.
  * Investigated computer-generated simulation datasets for autonomous-driving algorithm testing.

* **Equity Research Intern**, Hua Chuang Securities, Industry Research Division, Shenzhen, China &nbsp; *(Jul. 2022 – Oct. 2022)*
  * Built company databases (six issuers) to support investment decisions and growth estimates.
  * Distributed Hua Chuang's research outputs to institutional clients.

Awards
======
* Scholarship, academic year 2022–2023 — Oct. 2023
* Chinese Mathematics Competitions: National 3rd Prize — Dec. 2021
* Jilin Province Mathematics Competitions: Provincial 2nd Prize — Dec. 2021

Skills
======
* **Programming languages:** Python, C, MATLAB, Wolfram Mathematica, LaTeX
* **ML frameworks:** PyTorch, Tianshou, StableBaselines3, Gymnasium, MetaWorld, WandB, scikit-learn, pandas
* **AI coding tools:** Claude Code, OpenAI Codex CLI, GitHub Copilot, Cursor
* **Systems & DevOps:** Linux server administration, Git, Docker, VMware ESXi, OpenWrt, network administration
