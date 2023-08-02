---
abstract: We attack the state-of-the-art Go-playing AI system KataGo by training adversarial policies that play against frozen KataGo victims. Our attack achieves a >99% win rate when KataGo uses no tree search, and a >97% win rate when KataGo uses enough search to be superhuman. We train our adversaries with a modified KataGo implementation, using less than 14% of the compute used to train the original KataGo. Notably, our adversaries do not win by learning to play Go better than KataGo -- in fact, our adversaries are easily beaten by human amateurs. Instead, our adversaries win by tricking KataGo into making serious blunders. Our attack transfers zero-shot to other superhuman Go-playing AIs, and is interpretable to the extent that human experts can successfully implement it, without algorithmic assistance, to consistently beat superhuman AIs. Our results demonstrate that even superhuman AI systems may harbor surprising failure modes. Example games are available at https://goattack.far.ai/
abstract_short: ' '
authors: [TonyWang, AdamGleave, NoraBelrose, TomTseng, JosephMiller, MichaelDennis, YawenDuan, ViktorPogrebniak, SergeyLevine, StuartRussell]
date: '2022-11-01'
highlight: false
image_preview: ''
math: false
publication: International Conference on Machine Learning (ICML)
publication_short: ICML
publication_types: ['1']
selected: false
title: Adversarial Policies Beat Superhuman Go AIs
url_code: "https://github.com/AlignmentResearch/go_attack"
url_pdf: https://arxiv.org/pdf/2211.00241.pdf
url_dataset: ''
url_project: https://goattack.far.ai/
url_slides: '' 
url_video: ''
---

