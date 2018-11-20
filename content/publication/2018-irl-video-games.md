+++
title = "Inverse Reinforcement Learning for Video Games"
date = "2018-11-20"
authors = ["Aaron Tucker", "Adam Gleave", "Stuart Russell"]
publication_types = ["1"]
# Publication name and optional abbreviated version.
publication = "Deep Reinforcement Learning Workshop at NeurIPS"
publication_short = "DeepRL Workshop at NeurIPS"

# Abstract and optional shortened version.
abstract = "Deep reinforcement learning achieves superhuman performance in a range of video game environments, but requires that a designer manually specify a reward function. It is often easier to provide demonstrations of a target behavior than to design a reward function describing that behavior. Inverse reinforcement learning (IRL) algorithms can infer a reward from demonstrations in low-dimensional continuous control environments, but there has been little work on applying IRL to high-dimensional video games. In our CNN-AIRL baseline, we modify the state-of-the-art adversarial IRL (AIRL) algorithm to use CNNs for the generator and discriminator. To stabilize training, we normalize the reward and increase the size of the discriminator training dataset. We additionally learn a low-dimensional state representation using a novel autoencoder architecture tuned for video game environments. This embedding is used as input to the reward network, improving the sample efficiency of expert demonstrations. Our method achieves high-level performance on the simple Catcher video game, substantially outperforming the CNN-AIRL baseline. We also score points on the Enduro Atari racing game, but do not match expert performance, highlighting the need for further work."
abstract_short = " "
math = false
highlight = false 
image_preview = ""
selected = false
url_code = "https://github.com/HumanCompatibleAI/atari-irl/"
url_dataset = ""
url_project = ""
url_slides = "" 
url_video = ""

[[url_custom]]
name = "Paper"
url = "https://arxiv.org/abs/1810.10593"

[[url_custom]]
name = "BiBTeX"
url = "/papers/2018-irl-video-games.bib"

+++
