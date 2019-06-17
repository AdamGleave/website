+++
title = "Adversarial Policies: Attacking Deep Reinforcement Learning"
date = "2019-06-14"
authors = ["Adam Gleave", "Michael Dennis", "Neel Kant", "Cody Wild", "Sergey Levine", "Stuart Russell"]
publication_types = ["1"]
# Publication name and optional abbreviated version.
publication = "Security and Privacy of Machine Learning Workshop at ICML"

# Abstract and optional shortened version.
abstract = "Deep reinforcement learning (RL) policies are known to be vulnerable to adversarial perturbations to their observations, similar to adversarial examples for classifiers. However, an attacker is not usually able to directly modify another agent's observations. This might lead one to wonder: is it possible to attack an RL agent simply by choosing an adversarial policy acting in a multi-agent environment so as to create natural observations that are adversarial? We demonstrate the existence of adversarial policies in zero-sum games between simulated humanoid robots with proprioceptive observations, against state-of-the-art victims trained via self-play to be robust to opponents. The adversarial policies reliably win against the victims but generate seemingly random and uncoordinated behavior. We find that these policies are more successful in high-dimensional environments, and induce substantially different activations in the victim policy network than when the victim plays against a normal opponent. Videos are available at this http URL."
abstract_short = " "
math = false
highlight = false 
image_preview = ""
selected = false 
url_code = "https://github.com/HumanCompatibleAI/adversarial-policies"
url_dataset = ""
url_project = "https://adversarialpolicies.github.io"
url_slides = "https://docs.google.com/presentation/d/1FgnomI1_iKMrOFZA3DGSKtvdJS-aCBhSN6rgz7TKERs/edit?usp=sharing"
url_video = ""

[[url_custom]]
name = "Paper"
url = "https://arxiv.org/abs/1905.10615"

[[url_custom]]
name = "BiBTeX"
url = "/papers/2019-adversarial-policies.bib"

+++
