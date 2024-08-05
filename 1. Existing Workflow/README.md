# Existing Workflow for PCA-Based Face Recognition

This directory contains the implementation of the existing workflow for securely outsourcing PCA-based face recognition as described in Zhang et al.'s 2019 paper.

## Overview

Zhang et al. introduced a two-round outsourcing algorithm for PCA-based face recognition. 



### Key Steps

1. **Matrix Encryption**
   - The client generates random numbers and matrices to encrypt the matrix `S` and constructs an encrypted matrix `U`.

2. **Cloud Computation**
   - The encrypted matrix `U` is sent to the cloud for eigen-decomposition. The cloud returns the eigenvalues and eigenvectors of the encrypted matrix.

3. **Verification and Decryption**
   - The client verifies the correctness of the computation and decrypts the results to obtain the eigenvectors of the original matrix.

