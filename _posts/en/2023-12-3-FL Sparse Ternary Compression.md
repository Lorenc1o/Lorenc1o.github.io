---
title: "Paper Review: Robust and Communication-Efficient Federated Learning from Non-IID Data"
date: 2023-12-3
image: /assets/images/FL/STC/title.png
categories: [Machine Learning, Research]
author: "Jose Antonio Lorencio Abril"
lang: en
permalink: "/posts/end/FL-STC/"
toc:
    - 
        title: "Introduction"
        url: "#introduction"
    - 
        title: "Motivation"
        url: "#motivation"
---

## Introduction {#introduction}

This is a continuation post of the previous one, where we saw the paper [Communication-Efficient Learning of Deep Networks from Decentralized Data](/posts/en/Federated-Learning/).

In this post, we will see the paper [Robust and Communication-Efficient Federated Learning from Non-IID Data](https://arxiv.org/pdf/1903.02891.pdf), which proposes an enhancement to the Federated Averaging approach. In this paper, the authors propose a new compression method called **Sparse Ternary Compression (STC)**, aiming to reduce the communication overhead of the Federated Averaging approach.

## Motivation {#motivation}

One of the problems in FL settings is the communication overhead that arises from the several rounds of communication between the server and the clients, and the subsequent sending of the model from server to clients and vice versa. If comunication bandwidth is limited, FL can be inneficient or even unfeasible. The total amount of bits that need to be uploaded and downloaded by every client in the training process is given by:
\\[
    b^{up/down} \in \mathcal{O}\left( N_{iter} \times f \times \left| \mathcal{W} \right| \times \left( H\left( \mathcal{W}^{up/down} \right) + \eta \right) \right),
\\]
where:
- \\(N_{iter}\\) is the number of forward and backward passes per client in each round.
- \\(f\\) is the communication frequency.
    - \\(N_{iter} \times f\\) is the total number of updates per client.
- \\(\left\| \mathcal{W} \right\|\\) is the number of parameters in the model.
- \\(H\left( \mathcal{W}^{up/down} \right)\\) is the entropy of the weight updates exchanged during upload/download.
- \\(\eta\\) is the inefficiency of the encoding, i.e., the difference between update size and the minimal update size (the entropy).
    - \\(\left\| \mathcal{W}\right\| \times H\left( \mathcal{W}^{up/down} \right) \times \eta\\) is the total update size.

The authors consider the size of the model and the number of iterations per client as fixed, and focus on the three remaining factors:
- Reduce the communication frequency \\(f\\).
- Reduce the entropy of the updates \\(H\left( \mathcal{W}^{up/down} \right)\\) using lossy compression.
- Reduce the inefficiency of the encoding \\(\eta\\) using more efficient encoding schemes.

In addition, we have to consider the following challenges of the FL setting (see the previous post for more details):
- **Unbalanced, non-IID data distribution**.
- **Large number of clients**.
- **Parameter server**: it is common to use an intermediate parameter server to coordinate the training process. This reduces the amount of communication per client and communication rounds. However, it introduces a new challenge to communication-efficient training, since now both the upload to the server and the download from the server need to be compressed.
- **Partial participation of clients**: they can get out of battery or disconnected from the network.
- **Small memory**: the clients have limited memory, so it is necessary to keep the number of gradient evaluations per client low, as well as the batch size.

They conclude that a good method should fulfill the following requirements:
- R1: Compress both upstream and downstream communication.
- R2: Robust to non-IID data, small batch sizes and unbalanced data distribution.
- R3: Robust to partial participation of a great number of clients.

