---
layout: post
title: "Classifiers in MATLAB"
date: 2023-05-18
lang: en
categories: [Machine Learning, MATLAB]
toc:
    -
        title: "Theoretical background"
        url: "#theoretical-background"
    -
        title: "LDA"
        url: "#lda"
    -
        title: "QDA"
        url: "#qda"
    -
        title: "KNN"
        url: "#knn"
usemathjax: true
---

## Theoretical background {#theoretical-background}

Discriminant analysis is the result of implementing a Bayes classifier assuming that the class-conditional distributions
\\(p\\left(x|y\\right)\\) are gaussian. This means that, having \\(\\mathcal{Y}=\\left\\{ c_{1},...,c_{K}\\right\\}\\),
then it is
\\[p\\left(x|y=c_{k}\\right)\\sim\\mathcal{N}\\left(\\mu_{k},\\Sigma_{k}\\right).\\]
If we also assume that the prior distributions are 
\\[p\\left(y=c_{k}\\right)=\\pi_{k},\\]
with \\(\\sum_{k}\\pi_{k}=1\\), then we define the **discriminant functions**
\\[g_{k}\left(x\right)=\log\left(P\left(y=c_{k}\right)P\left(x|y=x_{k}\right)\right)\\]
\\[= \log\left(\pi_{k}\cdot\frac{1}{\det\left(\Sigma_{k}\right)^{\frac{1}{2}}\left(2\pi\right)^{\frac{d}{2}}}\exp\left\\{ -\frac{1}{2}\left(x-\mu_{k}\right)^{T}\Sigma^{-1}\left(x-\mu_{k}\right)\right\\} \right)\\]
\\[= \log\pi_{k}-\frac{1}{2}\log\left(\det\Sigma_{k}\right)-\frac{d}{2}\log\left(2\pi\right)-\frac{1}{2}\left(x-\mu_{k}\right)^{T}\Sigma^{-1}\left(x-\mu_{k}\right)\\]
\\[=\log\pi_{k}-\frac{1}{2}\left[\log\left(\det\Sigma_{k}+\left(x-\mu_{k}\right)^{T}\Sigma_{k}^{-1}\left(x-\mu_{k}\right)\right)\right]+const.\\]
This is a **quadratic discriminant function**, and the corresponding classifier is implemented by predicting
\\[ y'=c_{k'},\ where\ k'=\arg\max_{k}g_{k}\left(x\right).\\]
This corresponds to choosing the label with maximum probability a posteriori.

The **decision boundaries** in this case are those regions in which there exist \\(k_{1},k_{2}\\) with
\\[g_{k_{1}}\left(x\right)=g_{k_{2}}\left(x\right).\\]
These corresponds to hyper-quadrics in the feature space, and this is a quadratic method, usually called **quadratic discriminant analysis (QDA)**.

Of course, we can further simplify our assumptions, by assuming that all labels have the same covariance matrix, \\(\Sigma_{k}=\Sigma\\) for all $k=1,...,K$. In this simpler case, the discriminant functions end up being
\\[g_{k}\left(x\right)=\log\pi_{k}+\mu_{k}^{T}\Sigma^{-1}x-\frac{1}{2}\mu_{k}^{T}\Sigma^{-1}\mu_{k},\\]
because now \\(\det\Sigma_{k}=\det\Sigma\\) is constant for all \\(k\\), so we can remove it. Furthermore, the term \\(x^{T}\Sigma_{k}^{-1}x=x^{T}\Sigma^{-1}x\\) is also constant with respect to \\(k\\), so it will not affect the \\(k\\) chosen. Therefore, we end up with **linear discriminant functions**, in which the **decision boundaries** correspond to hyperplanes in the feature space. This is a linear method, usually called **linear discriminant analysis (LDA)**.

Now, we are going to see how to use these methods in MATLAB.

## LDA {#lda}

We are going to develop a classification example, using the famous Iris dataset.

```matlab:Code
load fisheriris
f = figure;
gscatter(meas(:,1), meas(:,2), species,'rgb','o',5);
xlabel('Sepal length');
ylabel('Sepal width');
```

We can perform LDA, to obtain a linear classifier:

```matlab:Code
lda = fitcdiscr(meas(:,1:2),species);
ldaClass = resubPredict(lda);

figure(f)
bad = ~strcmp(ldaClass,species);
hold on;
plot(meas(bad,1), meas(bad,2), 'kx');
hold off;
```

<img src="/assets/images/classifiers_matlab/figure_0.png" alt="A torus of revolution." width="400" class="centered-image">

Now we can draw the regions:

```matlab:Code
figure;
[x,y] = meshgrid(4:.01:8,2:.01:4.5);
x = x(:);
y = y(:);
j = predict(lda, [x y]);
colors = [0 1 0; 1 0 0; 0 0 1];
face_alpha = 0.5;

% Loop through unique species and plot points with custom colors and transparency
unique_species = unique(j);
for i = 1:length(unique_species)
    scatter(x(strcmp(j, unique_species{i})), y(strcmp(j, unique_species{i})), [], colors(i,:), 'o', 'filled', 'MarkerFaceAlpha', face_alpha);
    hold on;
end
legend('versicolor','setosa','virginica')
```

<img src="/assets/images/classifiers_matlab/figure_1.png" alt="A torus of revolution." width="400" class="centered-image">

As we can see, the decision boundaries are hyperplanes (lines in the 2D case), which is a characteristic of linear classifiers.

## QDA {#qda}
Let's now repeat this with QDA, so that we can obtain non-linear regions:

```matlab:Code
f2 = figure;
gscatter(meas(:,1), meas(:,2), species,'rgb','o',5);
xlabel('Sepal length');
ylabel('Sepal width');

qda = fitcdiscr(meas(:,1:2),species,'DiscrimType','quadratic');
qdaClass = resubPredict(qda);

figure(f2)
bad = ~strcmp(qdaClass,species);
hold on;
plot(meas(bad,1), meas(bad,2), 'kx');
hold off;
```
<img src="/assets/images/classifiers_matlab/figure_2.png" alt="A torus of revolution." width="400" class="centered-image">

```matlab:Code

figure;
[x2,y2] = meshgrid(4:.01:8,2:.01:4.5);
x2 = x2(:);
y2 = y2(:);
j2 = predict(qda, [x2 y2]);
% Define custom colors for the species
colors = [0 1 0; 1 0 0; 0 0 1];
face_alpha = 0.5;

% Loop through unique species and plot points with custom colors and transparency
unique_species = unique(j2);
for i = 1:length(unique_species)
    scatter(x2(strcmp(j2, unique_species{i})), y2(strcmp(j2, unique_species{i})), [], colors(i,:), 'o', 'filled', 'MarkerFaceAlpha', face_alpha);
    hold on;
end
legend('versicolor','setosa','virginica')
```

<img src="/assets/images/classifiers_matlab/figure_3.png" alt="A torus of revolution." width="400" class="centered-image">

In this example we observe that the decision boundaries are no longer linear: they are quadrics in the input space. This fact increases highly the shapes that these boundaries can take.

For instance, a hyperplane is always 'the same', in the sense that all hyperplanes are isomorphic. On the other hand, quadrics are much more complex. In 2D, for example, these are the conics, which can take the form of a line, a ellipse (with the circunference as special case), a parabola or an hyperbola. This variety increases highly with the dimensionality. In 3D and above they are usually called quadrics, and in 3D there are 17 standard-form types [[quadrics - wolfram mathworld]](https://mathworld.wolfram.com/QuadraticSurface.html#:~:text=Quadratic%20surfaces%20are%20also%20called,are%2017%20standard%2Dform%20types.).

## kNN {#knn}
A final example with a knn classifier:

```matlab:Code
% Train kNN classifier
k = 5; % You can change this value to choose a different number of neighbors
knn = fitcknn(meas(:,1:2), species, 'NumNeighbors', k);
knnClass = resubPredict(knn);

% Plot the dataset and misclassified points
f3 = figure;
gscatter(meas(:,1), meas(:,2), species, 'rgb', 'o', 5);
xlabel('Sepal length');
ylabel('Sepal width');

bad_knn = ~strcmp(knnClass, species);
hold on;
plot(meas(bad_knn, 1), meas(bad_knn, 2), 'kx');
hold off;
```

<img src="/assets/images/classifiers_matlab/figure_4.png" alt="A torus of revolution." width="400" class="centered-image">

```matlab:Code

% Visualize the decision regions
figure;
[x3, y3] = meshgrid(4:.01:8, 2:.01:4.5);
x3 = x3(:);
y3 = y3(:);
j3 = predict(knn, [x3 y3]);

% Define custom colors for the species
colors = [0 1 0; 1 0 0; 0 0 1];
face_alpha = 0.5;

% Loop through unique species and plot points with custom colors and transparency
unique_species = unique(j3);
for i = 1:length(unique_species)
    scatter(x3(strcmp(j3, unique_species{i})), y3(strcmp(j3, unique_species{i})), [], colors(i,:), 'o', 'filled', 'MarkerFaceAlpha', face_alpha);
    hold on;
end
legend('versicolor','setosa','virginica')
```

<img src="/assets/images/classifiers_matlab/figure_5.png" alt="A torus of revolution." width="400" class="centered-image">

This method generates more complex decision boundaries, which are not even continuous. This is because kNN is not optimizing an underlying function, which is ultimately what creates the continuous boundaries that we have seen in the previous methods. In this case, the boundaries are highly determined by the data instances.

It is a remarkable fact that they get smoother when k increases:

```matlab:Code
load fisheriris

% Define custom colors for the species
colors = [0 1 0; 1 0 0; 0 0 1];
face_alpha = 0.5;

k_values = [1, 5, 15, 35, 50];

for k_idx = 1:length(k_values)
    k = k_values(k_idx);

    % Train kNN classifier
    knn = fitcknn(meas(:,1:2), species, 'NumNeighbors', k);
    knnClass = resubPredict(knn);

    % Visualize the decision regions
    f = figure;
    [x, y] = meshgrid(4:.01:8, 2:.01:4.5);
    x = x(:);
    y = y(:);
    j = predict(knn, [x y]);

    % Loop through unique species and plot points with custom colors and transparency
    unique_species = unique(j);
    for i = 1:length(unique_species)
        scatter(x(strcmp(j, unique_species{i})), y(strcmp(j, unique_species{i})), [], colors(i,:), 'o', 'filled', 'MarkerFaceAlpha', face_alpha);
        hold on;
    end

    % Plot the original dataset on top of the decision regions
    gscatter(meas(:,1), meas(:,2), species, 'rgb', 'o', 5);

    % Plot misclassified points
    bad_knn = ~strcmp(knnClass, species);
    plot(meas(bad_knn, 1), meas(bad_knn, 2), 'kx');

    hold off;

    % Set title and labels
    title(sprintf('k = %d', k));
    xlabel('Sepal length');
    ylabel('Sepal width');
    legend('versicolor','setosa','virginica')
end
```

<img src="/assets/images/classifiers_matlab/figure_6.png" alt="A torus of revolution." width="400" class="centered-image">

<img src="/assets/images/classifiers_matlab/figure_7.png" alt="A torus of revolution." width="400" class="centered-image">

<img src="/assets/images/classifiers_matlab/figure_8.png" alt="A torus of revolution." width="400" class="centered-image">

<img src="/assets/images/classifiers_matlab/figure_9.png" alt="A torus of revolution." width="400" class="centered-image">

<img src="/assets/images/classifiers_matlab/figure_10.png" alt="A torus of revolution." width="400" class="centered-image">