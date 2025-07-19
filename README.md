# Symmetry-Informed Normalizing Flows for Gravitational Wave Analysis

**Project Status:** Archive (Completed Summer 2023)

This repository contains the work from a research project conducted at MIT during the summer of 2023, under the supervision of Dr. Deep Chatterjee (University of Illinois Urbana-Champaign).

The project explores the use of symmetry-informed normalizing flows to improve the analysis of gravitational wave data, specifically for signals from damped harmonic oscillators.

---

## Project Overview

Normalizing flows are a powerful class of generative models, but they can struggle with the complex, high-dimensional data found in gravitational wave signals. This project investigated whether embedding physical symmetries directly into the neural network architecture could lead to more efficient and accurate models.

The key idea was to use a similarity embedding network to learn a representation of the signal that is invariant to time shifts. This learned representation was then passed to a conditional residual network to model the flow, allowing for more precise posterior estimation.

## Key Contents

-   **/docs**: Contains the final project report and presentation slides, which provide a detailed theoretical background and a summary of the results.
-   **/notebooks**: Includes the Python notebooks used for the experiments.
    -   `damped-harmonic-oscillator-with-similarity-embedding-training.ipynb`: The main notebook for training the symmetry-informed flow model.
    -   `damped-harmonic-oscillator-without-similarity-embedding-training.ipynb`: A baseline model trained without the similarity embedding for comparison.

## Contributor

-   **Maanas Goel**
-   **Email:** [maanasgoel5@gmail.com](mailto:maanasgoel5@gmail.com)

---

*This work was conducted as part of the Summer 2023 research program at the MIT Kavli Institute for Astrophysics and Space Research.*
