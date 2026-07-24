# Machine Learning Model: MAGIC Gamma Telescope Classification

This project implements an advanced machine learning pipeline built for binary classification using the **MAGIC Gamma Telescope (MAGIC04)** dataset. Designed with robust feature engineering and model evaluation protocols, it addresses the fundamental challenge of distinguishing primary gamma-ray signals from high-energy cosmic-ray hadronic backgrounds in atmospheric Cherenkov telescope imaging.

---

## Overview & Scientific Context

The MAGIC04 dataset contains observations collected by the **Major Atmospheric Gamma Imaging Cherenkov (MAGIC)** Telescope system. Instead of capturing gamma-ray photons directly—which are absorbed by Earth's atmosphere—the telescope records the faint optical **Cherenkov radiation** flashes produced when high-energy gamma rays initiate electromagnetic particle cascades (extensive air showers) in the upper atmosphere. 

From these recorded optical images and sensor parameters, several numerical image-parameter features are extracted. These features describe the elliptical shape of the Cherenkov light images, enabling algorithms to classify events with high fidelity.

| Parameter | Description |
| :--- | :--- |
| **fLength** | Major axis length of the ellipse (in pixels) |
| **fWidth** | Minor axis length of the ellipse (in pixels) |
| **fSize** | 10log of sum of content of all pixels in the image |
| **fConc** | Ratio of sum of two highest pixel intensities to total sum |
| **fConc1** | Ratio of sum of highest pixel intensity to total sum |
| **fAsym** | Distance from highest pixel to center, projected on major axis |
| **fM3Long** | Third-order root along major axis |
| **fM3Trans** | Third-order root along minor axis |
| **fAlpha** | Angle of major axis with vector to origin |
| **fDist** | Distance from origin to image centroid |

---

## Why Gamma-Ray Detection Matters

Gamma rays represent the highest-energy band of the electromagnetic spectrum, serving as pristine messengers from the most extreme and violent particle accelerators in the universe. Accurate detection and classification allow astrophysicists to investigate:

* **Supernova Remnants & Pulsars:** Understanding particle acceleration mechanisms in stellar remnants.
* **Active Galactic Nuclei (AGN):** Probing supermassive black holes and relativistic jet physics.
* **Dark Matter Indirect Searches:** Looking for spectral signatures of annihilating dark matter candidates.

Accurate gamma-ray classification filters out overwhelming hadronic background noise (cosmic rays), directly improving observational sensitivity and cosmological discovery potential.

<p align="center">
  <img src="images/images.jpg" alt="MAGIC Telescope Principle" width="45%"/>
  <img src="images/images.png" alt="Cherenkov Shower Simulation" width="45%"/>
</p>

---

## Dataset Specifications

* **Source:** UCI Machine Learning Repository / MAGIC Gamma Telescope Dataset (MAGIC04)
* **Task:** Supervised Binary Classification
* **Total Instances:** 19,020 samples
* **Features:** 10 continuous numerical attributes derived from image analysis
* **Target Classes:**
  * **Gamma (`1` / `g`):** Signal events induced by primary gamma-ray photons (~65%)
  * **Hadron (`0` / `h`):** Background events induced by cosmic-ray hadrons (~35%)

---

## Project Architecture & Pipeline

1. **Data Preprocessing & Exploratory Data Analysis:** Handling feature scaling, outlier inspection, and mapping categorical classes (`g`/`h`) to binary labels (`1`/`0`).
2. **Model Training & Balancing:** Handling class distribution imbalances using oversampling techniques and training robust classification algorithms.
3. **Evaluation Metrics:** Assessing performance using precision, recall, accuracy, and confusion matrices.

---

## Getting Started

### Prerequisites

Ensure you have Python installed along with the core data science libraries:

```bash
pip install numpy pandas scikit-learn matplotlib imbalanced-learn
```

### Usage

Clone the repository and run your Google Colab or training script:

```bash
git clone https://github.com/username/magic-gamma-ml-model.git
cd magic-gamma-ml-model
```

---

## License

This project is licensed under the MIT License - see the LICENSE file for details.
