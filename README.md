# Training Query Embeddings Using Triplet Loss and BERT
For Search query in Shopping Apps, design Search Query Embedding


Overview

This project demonstrates how to train a query embedding model using:

BERT (bert-base-uncased) as the encoder
Triplet Loss as the training objective
A small synthetic dataset of Amazon-like search queries

The goal is to learn embeddings such that:

Semantically similar queries are close in the embedding space.
Semantically dissimilar queries are far apart.

Anchor Query  ──┐
                │
Positive Query ─┼──> BERT Encoder ──> Embeddings
                │
Negative Query ─┘

                       ↓
                 Triplet Loss
                       ↓
                Update BERT Weights

Triplet Loss

The loss function is:

L=max(0,d(A,P)−d(A,N)+m)

where:

A = Anchor
P = Positive
N = Negative
m = Margin


Mathematical Intuition

The model tries to achieve:

Anchor ----- Positive

Anchor ------------------------ Negative

instead of:

Anchor -------- Positive
Anchor ---------- Negative
