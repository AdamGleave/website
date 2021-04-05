---
abstract: For many tasks, the reward function is inaccessible to introspection or too complex to be specified procedurally, and must instead be learned from user data. Prior work has evaluated learned reward functions by evaluating policies optimized for the learned reward. However, this method cannot distinguish between the learned reward function failing to reflect user preferences and the policy optimization process failing to optimize the learned reward. Moreover, this method can only tell us about behavior in the evaluation environment, but the reward may incentivize very different behavior in even a slightly different deployment environment. To address these problems, we introduce the Equivalent-Policy Invariant Comparison (EPIC) distance to quantify the difference between two reward functions directly, without a policy optimization step. We prove EPIC is invariant on an equivalence class of reward functions that always induce the same optimal policy. Furthermore, we find EPIC can be efficiently approximated and is more robust than baselines to the choice of coverage distribution. Finally, we show that EPIC distance bounds the regret of optimal policies even under different transition dynamics, and we confirm empirically that it predicts policy training success. Our source code is available at https://github.com/HumanCompatibleAI/evaluating-rewards/.
abstract_short: ' '
authors: [AdamGleave, MichaelDennis, ShaneLegg, StuartRussell, JanLeike]
date: '2021-04-03'
highlight: true
image_preview: ''
math: false
publication: ICLR
publication_types: ['4']
selected: false
title: Quantifying Differences in Reward Functions
url_code: https://github.com/HumanCompatibleAI/evaluating-rewards/
url_pdf: https://arxiv.org/pdf/2006.13900.pdf
url_dataset: ''
url_project: ''
url_slides: ''
url_video: ''
---

