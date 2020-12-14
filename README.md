[![Netlify Status](https://api.netlify.com/api/v1/badges/a187899e-5596-4db3-9a9c-9f47556815db/deploy-status)](https://app.netlify.com/sites/gleave/deploys)
[![CircleCI](https://circleci.com/gh/HumanCompatibleAI/adversarial-policies.svg?style=svg)](https://circleci.com/gh/AdamGleave/website)

Some good docs:
https://sourcethemes.com/academic/post/getting-started/
https://sourcethemes.com/academic/post/managing-content/
https://sourcethemes.com/academic/post/widgets/

Note there's also an example website bundled with the template; you've deleted a lot of the files (since they weren't necessary for your current needs), may be worth consulting. This is in themes/academic/exampleSite.

You need to run `git submodule update --init --recursive` the first time you clone this repository. You will also need to `snap install hugo --channel=extended`. Then just run ./view.sh to preview.
