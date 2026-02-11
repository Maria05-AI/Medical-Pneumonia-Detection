# 🩻 AI Medical Diagnosis: Pneumonia Detection

> **"In medical diagnosis, a False Negative is critical. This model prioritizes High Recall (99.7%) to ensure no patient is left behind."**

![Project Banner](https://img.shields.io/badge/Domain-Healthcare_AI-blue?style=for-the-badge&logo=medrt)
![Accuracy](https://img.shields.io/badge/Recall-99.74%25-green?style=for-the-badge)
![Tech](https://img.shields.io/badge/Tech-TensorFlow_%7C_CNN-orange?style=for-the-badge)

## Project Overview
Pneumonia accounts for **15% of all deaths** of children under 5 years old worldwide. Early and accurate diagnosis is crucial for saving lives.
Driven by my passion for **AI in Healthcare**, I undertook this independent project to explore how Deep Learning can aid in saving lives.

This project utilizes **Convolutional Neural Networks (CNNs)** to analyze chest X-ray images. Unlike standard academic examples, I focused on solving a real-world problem: optimizing for **Sensitivity (Recall)** to ensure no positive case is missed.

## Key Results (The "Hero" Metric)
I evaluated the model on a strict, unseen test set of 624 images.

| Metric | Score | Clinical Interpretation |
| :--- | :---: | :--- |
| **Recall (Sensitivity)** | **99.74%** 🌟 | The model successfully detects nearly **ALL** positive cases. |
| **Accuracy** | ~73% | The model is "cautious," flagging suspicious cases for doctor review rather than missing them. |
| **Precision** | ~70% | Accepted trade-off to maximize Recall. |

## Tech Stack & Tools
* **Deep Learning Framework:** TensorFlow / Keras
* **Language:** Python
* **Data Processing:** Pandas, NumPy, ImageDataGenerator
* **Visualization:** Matplotlib, Seaborn
* **Development Environment:** Google Colab (GPU accelerated)

## Dataset
* **Source:** [Chest X-Ray Images (Pneumonia)](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia) from Kaggle.
* **Size:** 5,856 X-Ray images (JPEG).
* **Classes:**
    * `NORMAL` (Healthy lungs)
    * `PNEUMONIA` (Bacterial/Viral infection)

## Model Architecture
I built a custom CNN architecture from scratch to capture spatial hierarchies in X-Ray images:

1.  **Input Layer:** 150x150 pixels (Grayscale).
2.  **Feature Extraction:**
    * 3 Convolutional Blocks (`Conv2D` + `ReLU` + `MaxPooling`).
    * Filters increase depth (32 -> 64 -> 128) to capture complex patterns like lung opacity.
3.  **Classification Head:**
    * `Flatten` layer.
    * `Dense` layer (512 neurons).
    * **`Dropout(0.5)`**: Critical to prevent overfitting and improve generalization.
    * `Sigmoid` Output: Returns a probability score (0 to 1).

## Performance Visualization
Below is the training history showing the model's learning curve. Notice how **Validation Recall** (Orange line) remains high throughout training.

![Model Performance Charts](./model_performance.jpg)


## How to Run
1.  Clone this repository.
2.  Open the `Medical-XRay-Analysis.ipynb` file in **Google Colab**.
3.  Upload your `kaggle.json` API token when prompted.
4.  Run all cells to download data, train the model, and see the results!

---
*Developed by Maria – Aspiring AI Engineer*
