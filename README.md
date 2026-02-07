**Synthetic Crop Leaf Disease Image Generation using DCGAN**

This project implements a Deep Convolutional Generative Adversarial Network (DCGAN) to generate synthetic crop leaf disease images. The generated images help agricultural researchers and machine learning systems train robust disease detection models while overcoming data scarcity and class imbalance in real-world agricultural datasets.

**🔹 Module-Wise Implementation**

**Module 1 — Data Pipeline & Preprocessing**
This module prepares crop leaf disease images for DCGAN training.
Implemented Features:
Load leaf images in JPG / PNG format
Resize images (e.g., 64×64 or 128×128)
Convert to RGB (3-channel color images)
Normalize pixel values from [0, 255] → [-1, 1] (Tanh compatible)
Batch processing for efficient training
Purpose:
Ensures clean, standardized plant disease images for stable DCGAN training.

**Module 2 — Model Design (DCGAN Architecture)**
Generator (G):
Input: Random noise vector (latent space)
Fully connected layer + reshape
Multiple ConvTranspose layers for upsampling
Batch Normalization for training stability
Activation:
ReLU (hidden layers)
Tanh (output layer)
Discriminator (D):
Input: Real or generated leaf image
Multiple Conv layers with downsampling
Batch Normalization
Dense layer with Sigmoid output
Activation: LeakyReLU (0.2)
Loss & Optimizer:
Binary Cross Entropy (BCE)
Adam Optimizer
Learning rate = 0.0002
Beta1 = 0.5

<img width="546" height="742" alt="image" src="https://github.com/user-attachments/assets/64161196-6db5-4a2c-b729-199b055bc9c3" />

**Module 3 — Training & Monitoring**
This module handles DCGAN training and stability monitoring.
Training Process:
Train Discriminator on:
Real leaf disease images
Generated (fake) images
Train Generator to fool the Discriminator
Repeat for 100–300 epochs
Monitoring:
Track:
Generator loss (G_loss)
Discriminator loss (D_loss)
Save:
Generated disease image samples
Model checkpoints (G_final, D_final)
Outcome:
Generated leaf disease images become more realistic with clear texture and color patterns.

**Module 4 — Evaluation & Visualization**
Evaluates realism, diversity, and disease pattern quality.
Quantitative Metrics:
Classifier-based disease realism score
Diversity score (intra-class variation)
FID proxy score (real vs synthetic comparison)
Qualitative Analysis:
Visual inspection by domain experts
Detection of mode collapse
Visualizations:
Loss curves (G_loss vs D_loss)
Generated image grids by disease type
Latent space interpolation
t-SNE plots (real vs synthetic leaf images)

**Module 5 — Deployment Layer**
Enables real-world agricultural usage.
Implemented Concepts:
Export trained Generator model
Inference script for batch image generation
Deployment Options:
Streamlit UI
Flask / FastAPI API
Use Cases:
Generate synthetic leaf disease datasets
Balance under-represented disease classes
Improve crop disease detection models

**Module 6 — Monitoring & Update Pipeline**
Ensures long-term reliability and ethical AI usage.
Monitoring:
Track inference latency
Monitor image generation frequency
Log generation failures
Model Updates:
Periodic retraining with new disease samples
Version control:
G_v1, G_v2, G_v3
Ethical & Data Quality Checks:
Prevent memorization of real leaf images
Validate diversity across disease classes

**🌾 Real-Life Applications**
Automated crop disease detection systems
Precision agriculture solutions
Agricultural research and extension services
Dataset augmentation for plant pathology

**🛠️ Technologies Used**
Python
TensorFlow / Keras
NumPy, Matplotlib
Google Colab
Streamlit / Flask (deployment)

**▶️ How to Run**
Open the notebook in Google Colab
Run all cells sequentially
Visualize generated crop disease images
Use inference or deployment scripts for dataset generation

**📌 Conclusion**
This project demonstrates that a DCGAN can effectively generate high-quality synthetic crop leaf disease images. The approach addresses dataset imbalance and data scarcity in agriculture, enabling more accurate and robust plant disease classification systems.
