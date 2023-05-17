---
layout: post
title:  "Willmore Surfaces"
date:   2023-05-15
categories: math mathematics geometry differential-geometry willmore-surfaces willmore-functional
usemathjax: true
---
<head>
    <link rel="stylesheet" href="/assets/css/sidebar.css">
</head>
<div class="sidebar">
    <h2>Table of Contents</h2>
    <ul>
        <li><a href="#introduction">Introduction</a></li>
        <li><a href="#the-willmore-functional">The Willmore functional</a></li>
    </ul>
</div>

# Willmore Surfaces

## Introduction {#introduction}

I did my Mathematics Bachelor Thesis about Willmore Surfaces. I will try to explain the main ideas of the thesis in this post.

First, I will explain what the Willmore functional, \\(W\\), is. Then, I will visit some of the most important results about Willmore surfaces. Finally, I will explain the main result of my thesis, which is the derivation of the first variation of the Willmore functional, using basic tools of differential geometry in the three-dimensional Euclidean space, \\(\\mathbb{R}^3\\).

## The Willmore functional {#the-willmore-functional}

The Willmore functional of a compact surface, \\(S\\), is defined as:
\\[\\int_S H^2 dA,\\]
where \\(H\\) is the mean curvature of \\(S\\) and \\(dA\\) is the area element of \\(S\\).