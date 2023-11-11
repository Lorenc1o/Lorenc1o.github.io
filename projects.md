---
layout: page
title: "Projects"
permalink: /projects/
lang: en
---
Here is a list of some of my projects. For more details, visit the linked pages.

<div class="category-title">Research Projects</div>
<div class="project-title" onclick="toggleProject('transformers-content')">
    Transformer Models: State of the Art
</div>
<div id="transformers-content" class="project-content">
    For our course, Big Data Seminars, we had to conduct a literature review on a topic related to Big Data. My partner, <a href="https://github.com/Action52">Luis A. León</a>, and I decided to conduct a literature review on the Transformer models, which are behind the state-of-art models in Natural Language Processing and more generally, sequence modelling. <br><br>

    For a detailed information, visit the <a href="https://Lorenc1o.github.io/transformer_models_SoE/">dedicated page</a>. There, you will find the report, the poster and a Jupyter notebook demoing the use of pre-trained models for text classification.
</div>

<div class="project-title" onclick="toggleProject('FEM')">
    <b>BSc Thesis</b>: A Finite Element Model to Study the Deformations of the Mammary Tissues
</div>
<div id="FEM" class="project-content">
    To complete my Bachelor's Degree in Computer Science and Engineering, I had to conduct a Bachelor's Thesis. I decided to conduct it in the field of Computational Models for Medicine, and I developed a Finite Element Model and C++ module to study the deformations of the mammary tissues. <br><br>
    The problem is that mammograms are done with the woman standing up, while she is laying down at the time of the surgery. Therefore, the position of the breast changes, and the surgeon needs to take this into account. The idea was to develop a model that could predict the deformations of the breast, so that the surgeon can have a better idea of where the tumour should be, minimising the amount of tissue that needs to be removed. <br><br>
    The project was conducted under the supervision of <a href="https://dis.um.es/~ginesgm/">Ginés García Mateos</a>, and the full report can be found <a href="https://lorenc1o.github.io/Math_Info_UniversityNotes/comp_sci/tfg/TFG_FEM.pdf">here</a> (it is in Spanish).<br><br>
    The project was done in the frame of the 'Beca de Colaboración' of the University of Murcia, awarded by the Spanish Ministry of Education.<br><br>
    The grade was 9.9/10 with honours (top 5% of the theses).
</div>

<div class="project-title" onclick="toggleProject('Willmore')">
   <b>BSc Thesis</b>: Willmore Surfaces in the Euclidean Space
</div>
<div id="Willmore" class="project-content">
    To complete my Bachelor's Degree in Mathematics, I had to conduct a Bachelor's Thesis. I decided to conduct it in the field of Differential Geometry, and more concretely, I studied Willmore surfaces in the Euclidean space. <br><br>
    The Willmore energy is a functional that is defined on surfaces, and it is a generalisation of the area. The Willmore conjecture states that the Willmore energy of a surface is bounded from below by a constant, and that this constant is only achieved by the round sphere. <br><br>
    In this project, I studied the properties of the Willmore functional, and proved different results using the differential geometry tools that are learnt in the Bachelor's Degree, with the objective of making this advanced topic accessible to undergraduate students. <br><br>
    I studied results such as the Conformal Invariance of the Willmore functional or the First Variation of the Willmore functional, and delved into how Willmore got to his conjecture by studying the functional in the space of generalized tori. <br><br>
    The project was conducted under the supervision of <a href="https://webs.um.es/ljalias/miwiki/doku.php">Luis J. Alías</a>, and the full report can be found <a href="https://lorenc1o.github.io/Math_Info_UniversityNotes/mathematics/tfg/TFG_WillmoreSurfaces.pdf">here</a> (it is in Spanish).<br><br>
    The grade was 9.8/10 with honours (top 5% of the theses).
</div>

<div class="category-title">Applied Projects</div>

<div class="project-title" onclick="toggleProject('AI-social-network')">
    BWave: an AI-powered social network
</div>
<div id="AI-social-network" class="project-content">
    For our second semester of the BDMA Master's Degree, we had to develop a joint project for several courses.
    It consisted on thinking about a data-related startup, and creating a proof of concept for it. We decided to create a social network, BWave, that would use AI to recommend content to the users. <br><br>
    If you want to knoe more about the project, visit the <a href="https://aliabusaleh.github.io/bdma-upc-bdm-bwave/index.html">dedicated page</a>.
</div>

<div class="project-title" onclick="toggleProject('garbage-content')">
    Optimising Garbage Collection Routing
</div>
<div id="garbage-content" class="project-content">
    As a University project, for the course Mathematical Modelling, my group and I developed a mathematical model to optimise the garbage collection routing in my town, Cehegín, Spain, in collaboration with the town hall.<br><br>

    The model was developed in AMPL and solved using Gurobi. We needed to take some decisions regarding the model, since the data collected by the town hall was not enough to develop a complete model. For example, we needed to decide the amount of garbage in each container, which was not known. We decided to take the maximum amount of garbage that each container could hold, and then we would optimise the number of containers needed to collect all the garbage, therefore working with a very pessimistic scenario. In addition, the town hall only tracks the street where each container is located, but not the exact position. Therefore, we needed to decide the position of each container in the street.<br><br>

    With all these decisions, we managed to develop a model that optimised the kilometers needed to collect all the garbage, reducing them by 10% compared to the current routing, assuming the pessimistic scenario.<br><br>

    The report can be found <a href="https://github.com/Lorenc1o/Math_Info_UniversityNotes/blob/main/Mathematics/5th-year/Modelling_Lab/Optimisation/Group_Assignment/GARBAGECOLLECTION.pdf">here</a>.
</div>

<div class="project-title" onclick="toggleProject('forex-content')">
    Modelling Species Interactions and Its Applications to FOREX Market Prediction
</div>
<div id="forex-content" class="project-content">
    As part of the same course, Mathematical Modelling, my group and I studied the applicability of different models that are used to model species interactions to the FOREX market. We studied the applicability of the Lotka-Volterra model, its generalisation, and the Logistic model. In addition, we developed discrete versions of the models, due to the nature of the economic variables and the decreased computational cost of the discrete models.<br><br>

    For each discrete model, we managed to make suitable transformation to the data, so that the models could be fitted as a linear regression. <br><br>

    Regarding the application of the models to the FOREX market, the idea was that the money supply of a country could be modelled as a species, and somehow the money supply of a country would interact with the money supply of another country. Therefore, we could model the money supply of different countries as species, and use the predicted values of the models as input to more general models to predict the FOREX market.<br><br>

    To assess this idea, we used the data of the money supply of the US, the European Union and Switzerland. The results were very good as a preliminary assessment, but more data and more countries would be needed to make a more accurate assessment. The full report can be found <a href="https://github.com/Lorenc1o/Math_Info_UniversityNotes/blob/main/Mathematics/5th-year/Modelling_Lab/Analysis/Group_Assignment/LabMod___Analisis__G7.pdf">here</a>.
</div>

<div class="category-title">Education</div>
<div class="project-title" onclick="toggleProject('bdma-content')">
    Erasmus Mundus Joint Master's Degree in Big Data Management and Analytics (EMJMD BDMA)
</div>
<div id="bdma-content" class="project-content">
    I was granted an Erasmus Mundus Joint Master's Degree scholarship by the European Commission to study the Big Data Management and Analytics Master's Degree, coordinated by the <a href="https://www.ulb.be/">Université Libre de Bruxelles</a>. <br><br>

    The different course notes and projects that I have developed can be found in the dedicated page to the <a href="https://Lorenc1o.github.io/BDMA_Notes">BDMA notes</a>.
</div>
<div class="project-title" onclick="toggleProject('mathcs-content')">
    Double Bachelor's Degree in Mathematics and Computer Science
</div>
<div id="mathcs-content" class="project-content">
    I studied at the University of Murcia, Spain, a double bachelor's degree in Mathematics and Computer Science. It is a 5-years degree, awarding both degrees at the end of the studies. I finished the degree in 2022 and during the studies I developed several course notes and projects, which can be found in my repository dedicated to the <a href="https://github.com/Lorenc1o/Math_Info_UniversityNotes">Double Bachelor's Degree in Mathematics and Computer Science</a>. For more details, visit the <a href="https://lorenc1o.github.io/Math_Info_UniversityNotes/index.html">dedicated page</a>.
</div>
