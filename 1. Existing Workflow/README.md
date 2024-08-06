# Existing Workflow for PCA-Based Face Recognition

This directory contains the implementation of the existing workflow for securely outsourcing PCA-based face recognition as described in Zhang et al.'s 2019 paper.

## Overview

Zhang et al. introduced a two-round outsourcing algorithm for PCA-based face recognition.

### Key Steps

1. **Generating the Image Matrix**

   - The client vectorizes the images into columns and combines them column-wise to form the image matrix `A`. This matrix is the starting point for PCA.

2. **Matrix Encryption**

   - The client generates random numbers and matrices to encrypt the matrix $$S = \frac{1}{m} A A^T$$
     and constructs an encrypted matrix `U`. This ensures that the data is secure before outsourcing.

3. **Outsourcing Eigendecomposition**

   - The encrypted matrix `U` is sent to the cloud for eigen-decomposition. The cloud performs the decomposition and returns the eigenvalues and eigenvectors of the encrypted matrix.

4. **Verification and Decryption**

   - The client verifies the correctness of the cloud's computation. If the results are correct, the client decrypts the results to obtain the eigenvectors of the original matrix `S`.

5. **Face Recognition**
   - After obtaining the eigenvectors, the client uses them to perform face recognition by finding the closest image in the transformed space.


## Flowchart
![workflow](https://private-user-images.githubusercontent.com/77045044/355271977-ec71bd49-dc33-4d0f-9bda-b3b57de6d44d.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MjI5MDQwMzEsIm5iZiI6MTcyMjkwMzczMSwicGF0aCI6Ii83NzA0NTA0NC8zNTUyNzE5NzctZWM3MWJkNDktZGMzMy00ZDBmLTliZGEtYjNiNTdkZTZkNDRkLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA4MDYlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwODA2VDAwMjIxMVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWNlZDhiNDg4YmJiNzQ3N2I4YTk5MzdkZmQyM2ExNjQ2Yjk3OTJiOWZhYzhjYWUxZTFkZTIzMmJlYmMzOGJkMzcmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.YjyaTzftXIoRA8-o95hBZA3-cs5ZKn0rtkOSI25fCKA))
