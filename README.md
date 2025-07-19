# Symmetry-Informed Normalizing Flows for Gravitational Wave Analysis
A Summer Research Project by Maanas Goel at the MIT LIGO Lab (2023)

[**LinkedIn: Maanas Goel**](https://www.linkedin.com/in/maanas-goel/) | [**Email: maanasgoel5@gmail.com**](mailto:maanasgoel5@gmail.com)

---

This repository contains the work from a research project conducted at the **MIT Kavli Institute for Astrophysics and Space Research**. The project was supervised by MIT Research Scientists Dr. Deep Chatterjee and Dr. Erik Katsavounidis.

---

## Project Overview

Likelihood-free inference using normalizing flows is a popular method for parameter estimation, but it faces computational challenges when dealing with symmetries in the data, such as time translation. This is a hurdle for analyzing un-modeled gravitational-wave signals, where parameters like frequency and duration are often more critical than the precise arrival time of a signal in a given data segment.

This project demonstrates a proof-of-concept solution by building a normalizing flow that is conditioned on a **symmetry-informed embedding network**. This pre-trained network learns to be agnostic to time shifts, allowing the main flow to focus on the intrinsic parameters of the signal (e.g., natural frequency and damping coefficient).

The key results show that this method leads to **faster convergence with a smaller, more efficient model** compared to a traditional normalizing flow that is not aware of such symmetries. While this work uses simplified physical models (Damped Harmonic Oscillators and Sine-Gaussians), it establishes a promising framework for real-world applications in gravitational-wave parameter estimation.

## Key Contents & Repository Structure

-   **/reports**: Contains the final project report and presentation slides, which provide a detailed theoretical background and a summary of the results.
-   **/notebooks**: Includes the Python notebooks used for the experiments, separated by the physical model used.

## Detailed File Manifest

This section provides a detailed breakdown of the key files and notebooks within the repository.

### Documents

-   `MIT_Gravitational_Waves_Research_Report_2023_Maanas_Goel.pdf`
    -   The final, comprehensive research paper for the project.
    -   Available on Overleaf for viewing: [https://www.overleaf.com/read/kmxckfhbvdvg](https://www.overleaf.com/read/kmxckfhbvdvg)

### Damped Harmonic Oscillator (DHO) Notebooks

-   `damped-harmonic-oscillator-with-similarity-embedding-training.ipynb`
    -   **Main experiment:** Trains the normalizing flow using a pre-trained, frozen similarity embedding network.
    -   Demonstrates the core methodology of this project.

-   `damped-harmonic-oscillator-without-similarity-embedding-training.ipynb`
    -   **Baseline comparison:** Trains the normalizing flow without a pre-trained similarity embedding.
    -   Used to measure the performance improvement of the symmetry-informed approach.

-   `damped-harmonic-oscillator-moneyplot-similarity-embedding-improvement.ipynb`
    -   **Results analysis:** Compares the training losses of the two models above and generates plots showing the improved efficiency of the similarity embedding.

-   `damped-harmonic-oscillator-similarity-embedding-weights.pth`
    -   The saved weights of the trained similarity embedding network.

-   `damped-harmonic-oscillator-with-similarity-embedding-flow-weights.pth`
    -   The saved weights of the main flow trained *with* the similarity embedding.

-   `damped-harmonic-oscillator-without-similarity-embedding-flow-weights.pth`
    -   The saved weights of the baseline flow trained *without* the similarity embedding.

### Sine-Gaussian (SG) Notebooks

-   `sine-gaussian-with-similarity-embedding-training.ipynb`
    -   **Main experiment:** Applies the same symmetry-informed methodology to the Sine-Gaussian model, which is more representative of generic burst morphologies in gravitational-wave signals.

-   `sine-gaussian-without-similarity-embedding-training.ipynb`
    -   **Baseline comparison:** Trains a baseline model for the Sine-Gaussian signal.

-   `sine-gaussian-moneyplot-similarity-embedding-improvement.ipynb`
    -   **Results analysis:** Compares the training losses for the Sine-Gaussian models to demonstrate efficiency gains.

-   `sine-gaussian-similarity-embedding-weights.pth`
    -   The saved weights of the trained similarity embedding network for the SG model.

-   `sine-gaussian-with-similarity-embedding-flow-weights.pth`
    -   The saved weights of the main flow trained *with* the similarity embedding for the SG model.

-   `sine-gaussian-without-similarity-embedding-flow-weights.pth`
    -   The saved weights of the baseline flow trained *without* the similarity embedding for the SG model.

---

*This work was conducted as part of the Summer 2023 research program at the MIT Kavli Institute for Astrophysics and Space Research and was supported by NSF award 2117997.*
