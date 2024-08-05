# Secure and Efficient Outsourcing of PCA-Based Face Recognition

This repository contains the implementation and verification codes for the paper "A Note on 'Secure and Efficient Outsourcing of PCA-Based Face Recognition'" by Satyabrat Rath, Jothi Rangasamy and Sohham Seal. The repository is structured to demonstrate the fundamental mathematical flaws in existing algorithms and propose robust solutions.

## Background

Face recognition relies heavily on pattern extraction, with Principal Component Analysis (PCA) being a key technique. Outsourcing the computation of PCA has become popular, but it raises concerns about security and reliability. Zhang et al. proposed a two-round outsourcing algorithm for PCA, but it suffers from a significant mathematical flaw. This repository addresses that flaw and proposes a robust verification scheme to ensure the accuracy and security of the outsourced computations.

## How to Navigate the Repository

### 1. Existing Workflow

This directory contains the implementation of the existing workflow as per Zhang et al.'s algorithm. It demonstrates the process of securely outsourcing the eigen-decomposition of a matrix derived from image data.

### 2. Cheating

This directory illustrates how cheating can occur in the verification phase of the outsourcing protocol. It shows how the cloud service can manipulate the results to pass the verification tests despite providing incorrect decompositions, in three different papers.

### 1.ipynb

The Jupyter notebook `1.ipynb` provides a workable fix for the faulty encryption technique used in Round 2 of securely outsourcing the Eigendecomposition.