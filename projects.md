---
layout: page
title: "Projects"
permalink: /projects/
lang: en
toc:
    -
        title: Transformers Model: State of the Art
        url: '#transformers'
    -
        title: EMJMD BDMA
        url: '#bdma'
    -
        title: Optimising Garbage Collection Routing
        url: '#garbage'
    -
        title: Modelling Species Interactions and Its Applications to FOREX Market Prediction
        url: '#forex'
    -
        title: BSc Math & CS
        url: '#mathcs'
---
Here is a list of some of my projects. For more details, visit the linked pages.

# Transformers Model: State of the Art {#transformers}

For our course, Big Data Seminars, we had to conduct a literature review on a topic related to Big Data. My partner, [Luis A. León](https://github.com/Action52), and I decided to conduct a literature review on the Transformers model, which is a state of the art model in Natural Language Processing.

For a detailed information, visit the [dedicated page](https://Lorenc1o.github.io/transformer_models_SoE/). There, you will find the report, the poster and a Jupyter notebook demoing the use of pre-trained models for text classification.

# Erasmus Mundus Joint Master's Degree in Big Data Management and Analytics (EMJMD BDMA) {#bdma}

I was granted an Erasmus Mundus Joint Master's Degree scholarship by the European Commission to study the Big Data Management and Analytics Master's Degree, coordinated by the [Université Libre de Bruxelles](https://www.ulb.be/). 

The different course notes and projects that I have developed can be found in the dedicated page to the [BDMA notes](https://Lorenc1o.github.io/BDMA_Notes).

# Optimising Garbage Collection Routing {#garbage}

As a University project, for the course Mathematical Modelling, my group and I developed a mathematical model to optimise the garbage collection routing in my town, Cehegín, Spain, in collaboration with the town hall. 

The model was developed in AMPL and solved using Gurobi. We needed to take some decisions regarding the model, since the data collected by the town hall was not enough to develop a complete model. For example, we needed to decide the amount of garbage in each container, which was not known. We decided to take the maximum amount of garbage that each container could hold, and then we would optimise the number of containers needed to collect all the garbage, therefore working with a very pessimistic scenario. In addition, the town hall only tracks the street where each container is located, but not the exact position. Therefore, we needed to decide the position of each container in the street. 

With all these decisions, we managed to develop a model that optimised the kilometers needed to collect all the garbage, reducing them by 10% compared to the current routing, assuming the pessimistic scenario.

The report can be found [here](https://github.com/Lorenc1o/Math_Info_UniversityNotes/blob/main/Mathematics/5th-year/Modelling_Lab/Optimisation/Group_Assignment/GARBAGECOLLECTION.pdf).

# Modelling Species Interactions and Its Applications to FOREX Market Prediction {#forex}

As part of the same course, Mathematical Modelling, my group and I studied the applicability of different models that are used to model species interactions to the FOREX market. We studied the applicability of the Lotka-Volterra model, its generalisation, and the Logistic model. In addition, we developed discrete versions of the models, due to the nature of the economic variables and the decreased computational cost of the discrete models.

For each discrete model, we managed to make suitable transformation to the data, so that the models could be fitted as a linear regression. 

Regarding the application of the models to the FOREX market, the idea was that the money supply of a country could be modelled as a species, and somehow the money supply of a country would interact with the money supply of another country. Therefore, we could model the money supply of different countries as species, and use the predicted values of the models as input to more general models to predict the FOREX market.

To assess this idea, we used the data of the money supply of the US, the European Union and Switzerland. The results were very good as a preliminary assessment, but more data and more countries would be needed to make a more accurate assessment. The full report can be found [here](https://github.com/Lorenc1o/Math_Info_UniversityNotes/blob/main/Mathematics/5th-year/Modelling_Lab/Analysis/Group_Assignment/LabMod___Analisis__G7.pdf).

# Double Bachelor's Degree in Mathematics and Computer Science {#mathcs}

I studied at the University of Murcia, Spain, a double bachelor's degree in Mathematics and Computer Science. It is a 5-years degree, awarding both degrees at the end of the studies. I finished the degree in 2022 and during the studies I developed several course notes and projects, which can be found in my repository dedicated to the [Double Bachelor's Degree in Mathematics and Computer Science](https://github.com/Lorenc1o/Math_Info_UniversityNotes). For more details, visit [the dedicated page](https://lorenc1o.github.io/Math_Info_UniversityNotes/index.html).
