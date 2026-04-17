# NGEO316 AI for Earth and Environmental Sciences. April 2026. 

## Exercises

## Project deprecated

- Look into how noisy my data is (especially the small biotope patches). 
    - But how exactly?
    - Taking the data that is just in forest is actually a task of cleaning more than creating a feature
        - Now using biotope dissolved in a tematic way: the synthesis of the data maybe is problematic as they are 
        - Can be dissolved by contiguity
        - Can be aggregated all
        - Lets to compare all of the data and compare how sensible it is
        - [From this paper](https://www.frontiersin.org/journals/plant-science/articles/10.3389/fpls.2022.839407/full) Alpha diversity is quite difficult to predict, local scale processes that cannot be measure
        - [From this paper](https://www.sciencedirect.com/science/article/pii/S1574954125003279?via%3Dihub) CNN to work with complete data of the images not aggregation, tutorial in
        - [From this paper](https://www.researchsquare.com/article/rs-4734879/v1) Use of Swedish lidar data to predict High Conservation Vaues
     
    - Resources:
        - https://www.biodiversity.se/projects-8-1
        - 
- Also, maybe the project can be to check out the new spatial data Abigail Starkey [shared](https://business.esa.int/projects/remote-ecological-surveys-eo) from ESA business.

## Project (Mixing R and python scripts)

My Hmsc models are showing low predictive accuracy on abundance for a bunch of species, and surprisingly, it's not just the rare ones. [See here](https://github.com/cmunozr/2025_I_comparative_metrics/blob/main/experiments_log/experiments.md) Ideas to explore for project:

- Compare HMSC against [Deep Learning (DL) Maxentbased on this new paper](https://besjournals.onlinelibrary.wiley.com/doi/10.1111/2041-210x.70262)
    - I honestly prefer DL, even though I was pretty bummed a few years ago when my ANN for single joint species distribution didn't work.
    - I've actually been thinking about building a DL alternative to Hmsc since GLMMs aren't the most flexible.
    - The tricky part: how do I incorporate phylogenetic info, trait data, and, of course, random effects? Potentially this is frontier knowledge:
        - How do I control for spatial and temporal effects outside of HMSC models?
        - Could I just reuse the random effects from HMSC? Probably not.
    - For this project I can let the things basic without incorporating random effects:
        - Not between routes just inside each route (biotope)
