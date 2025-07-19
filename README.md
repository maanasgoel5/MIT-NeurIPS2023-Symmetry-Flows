# Optimizing Likelihood-free Inference using Self-supervised Neural Symmetry Embeddings

This project was developed during a scientific research internship in Summer 2023 at the MIT LIGO Laboratory, which is hosted by the MIT Kavli Institute for Astrophysics and Space Research (MKI). LIGO is a joint effort between Caltech and MIT, supported by the National Science Foundation, focused on detecting and studying gravitational waves. This research was supervised by MIT Research Scientists Dr. Deep Chatterjee and Dr. Erik Katsavounidis, and supported by NSF award 2117997.

This branch of the repository contains notebooks and weights of trained models used for the [ML4PS](https://ml4physicalsciences.github.io/2023/) workshop (submission 69) at NeurIPS 2023. The final paper draft can be found in the [papers](https://ml4physicalsciences.github.io/2023/#papers) section of the workshop website.

#### **Contributor:** Maanas Goel ([Email](mailto:maanasgoel5@gmail.com), [LinkedIn](https://www.linkedin.com/in/maanas-goel/))

---

## Project Overview

Likelihood-free inference using normalizing flows is a popular method for parameter estimation, but it faces computational challenges when dealing with symmetries in the data, such as time translation. This is a hurdle for analyzing un-modeled gravitational-wave signals, where parameters like frequency and duration are often more critical than the precise arrival time of a signal in a given data segment.

This project demonstrates a proof-of-concept solution by building a normalizing flow that is conditioned on a **symmetry-informed embedding network**. This pre-trained network learns to be agnostic to time shifts, allowing the main flow to focus on the intrinsic parameters of the signal (e.g., natural frequency and damping coefficient).

The key results show that this method leads to **faster convergence with a smaller, more efficient model** compared to a traditional normalizing flow that is not aware of such symmetries.

## Detailed File Manifest

This section provides a detailed breakdown of the key files and notebooks within the repository. Each directory contains the notebooks and trained weights to reproduce the figures in the paper. In particular, representations in Fig. 2 of the draft are found [here](./notebooks/DampedHarmonicOscillator/sho-reps.ipynb) for the SHO model and [here](./notebooks/SineGaussian/sg-reps.ipynb) for SG models. Comparison posteriors between a trained flow model with similarity training vs. that without similarity pre-training and nested sampling in Fig. 3 of the draft are found [here](./notebooks/DampedHarmonicOscillator/sho-baseline-training.ipynb) for the SHO model and [here](./notebooks/SineGaussian/sine-gaussian-baseline-training.ipynb) for the SG model.

### reports

-   `MIT_Gravitational_Waves_Research_Report_2023_Maanas_Goel.pdf`
    -   This is my final, comprehensive research report for the project. It can also be viewed on [Overleaf](https://www.overleaf.com/read/kmxckfhbvdvg).

### Damped Harmonic Oscillator (DHO) Notebooks

-   `damped-harmonic-oscillator-with-similarity-embedding-training.ipynb`: Trains the DHO flow using the pre-trained similarity embedding.
-   `damped-harmonic-oscillator-without-similarity-embedding-training.ipynb`: Trains the DHO flow without the similarity embedding for baseline comparison.
-   `damped-harmonic-oscillator-moneyplot-similarity-embedding-improvement.ipynb`: Compares losses and shows the efficiency of the similarity embedding for the DHO model.
-   `damped-harmonic-oscillator-similarity-embedding-weights.pth`: Saved weights for the DHO similarity embedding network.
-   `damped-harmonic-oscillator-with-similarity-embedding-flow-weights.pth`: Saved weights for the DHO flow trained *with* similarity embedding.
-   `damped-harmonic-oscillator-without-similarity-embedding-flow-weights.pth`: Saved weights for the DHO flow trained *without* similarity embedding.

### Sine-Gaussian (SG) Notebooks

-   `sine-gaussian-with-similarity-embedding-training.ipynb`: Trains the SG flow using the pre-trained similarity embedding.
-   `sine-gaussian-without-similarity-embedding-training.ipynb`: Trains the SG flow without the similarity embedding for baseline comparison.
-   `sine-gaussian-moneyplot-similarity-embedding-improvement.ipynb`: Compares losses and shows the efficiency of the similarity embedding for the SG model.
-   `sine-gaussian-similarity-embedding-weights.pth`: Saved weights for the SG similarity embedding network.
-   `sine-gaussian-with-similarity-embedding-flow-weights.pth`: Saved weights for the SG flow trained *with* similarity embedding.
-   `sine-gaussian-without-similarity-embedding-flow-weights.pth`: Saved weights for the SG flow trained *without* similarity embedding.
