---
abstract: Language models can learn a range of capabilities from unsupervised training on text corpora. However, to solve a particular problem (such as text summarization) it is typically necessary to fine-tune them on a task-specific dataset. It is often easier for humans to choose between options than to provide labeled data, and prior work has achieved state-of-the-art performance by training a reward model from such preference comparisons. However, collecting a large preference comparison dataset is still expensive—and the learned reward models are unreliable out-of-distribution. We seek to address these problems via uncertainty estimation, which can improve sample efficiency and robustness using active learning and risk-averse reinforcement learning (RL). Specifically, we use bootstrap aggregating (bagging) to train an ensemble of reward models differing in the initialization of their final layer. Ensembles have proved successful in prior applications of active learning, but we find that in our setting ensemble active learning does not outperform random sampling. Further experiments show that while the aggregate predictions are well-calibrated, the ensemble’s estimated epistemic uncertainty is only weakly correlated with model error. We suspect this is because the ensemble members are fine-tuned from a single model and so are similar to one another.  This suggests current pre-training methods will need to be modified to support uncertainty estimation, e.g. by training multiple language models. 
abstract_short: ' '
authors: [AdamGleave, GeoffreyIrving]
date: '2022-03-15'
highlight: false
image_preview: ''
math: false
publication: arXiv 
publication_types: ['3']
selected: false
title: Uncertainty Estimation for Language Reward Models 
url_pdf: https://arxiv.org/pdf/2203.07472.pdf 
url_dataset: ''
url_project: ''
url_slides: '' 
url_video: ''
---

