# NGEO316 AI for Earth and Environmental Sciences. April 2026. 

## Exercises

## Project (Mixing R and python scripts)

My Hmsc models are showing low accuracy for a bunch of species, and surprisingly, it's not just the rare ones. [See here](https://github.com/cmunozr/2025_I_comparative_metrics/blob/main/experiments_log/experiments.md) Ideas to explore for project:
    - Look into how noisy my data is (especially the small biotope patches).
        * But how exactly? 
    - Compare HMSC against RF, XGBoost, and Deep Learning (DL) [maybe with maximum entropy [based on this new paper](https://besjournals.onlinelibrary.wiley.com/doi/10.1111/2041-210x.70262)
        - I honestly prefer DL, even though I was pretty bummed a few years ago when my ANN for single joint species distribution didn't work.
        - I've actually been thinking about building a DL alternative to Hmsc since GLMMs aren't the most flexible. The tricky part: how do I incorporate phylogenetic info, trait data, and, of course, random effects? Potentially this is frontier knowledge.
        - How do I control for spatial and temporal effects outside of HMSC models?
            - Could I just reuse the random effects from HMSC? Probably not.
        - For this project I can let the things basic without incorporating random effects between routes just inside each route (biotope)
    - Also, maybe the prohject can be to check out the new spatial data Abigail Starkey [shared](https://business.esa.int/projects/remote-ecological-surveys-eo) from ESA business.