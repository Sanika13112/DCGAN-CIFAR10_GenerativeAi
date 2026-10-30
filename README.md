# 🧠 DCGAN Image Generation Using CIFAR-10

### Deep Convolutional Generative Adversarial Network

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Deep%20Learning-orange?logo=tensorflow)
![Keras](https://img.shields.io/badge/Keras-Neural%20Networks-red?logo=keras)
![Dataset](https://img.shields.io/badge/Dataset-CIFAR--10-green)
![Platform](https://img.shields.io/badge/Platform-Google%20Colab-yellow?logo=googlecolab)

---

## 📌 1. Project Overview

This project focuses on implementing and training a **Deep Convolutional Generative Adversarial Network (DCGAN)** using TensorFlow and Keras.

The main objective is to generate new synthetic images by learning visual patterns from the CIFAR-10 dataset.

DCGAN consists of two neural networks:

- **Generator:** Generates synthetic images from random noise.
- **Discriminator:** Determines whether an image is real or artificially generated.

Both networks are trained against each other through an adversarial learning process. As training progresses, the Generator attempts to produce more realistic images that can fool the Discriminator.

This project demonstrates how deep learning and adversarial training can be used for image generation.

## 🎯 2. Project Objectives

- Understand the working principle of Generative Adversarial Networks (GANs).
- Implement a Deep Convolutional Generative Adversarial Network.
- Build Generator and Discriminator architectures using CNN layers.
- Train the model using the CIFAR-10 dataset.
- Generate synthetic images from random latent vectors.
- Analyze Generator and Discriminator loss curves.
- Evaluate image quality and diversity through visual inspection.

## 📚 3. Dataset Description

**Dataset:** CIFAR-10

CIFAR-10 is a standard image dataset containing 60,000 colour images divided into 10 different categories.

| Dataset Details | Description |
|---|---|
| Total images | 60,000 |
| Training images | 50,000 |
| Testing images | 10,000 |
| Image dimensions | 32 × 32 × 3 |
| Number of classes | 10 |
| Image type | RGB colour images |

### CIFAR-10 Categories

1. Airplane
2. Automobile
3. Bird
4. Cat
5. Deer
6. Dog
7. Frog
8. Horse
9. Ship
10. Truck

The dataset is automatically downloaded using TensorFlow/Keras.

**Dataset source:** https://www.cs.toronto.edu/~kriz/cifar.html

## ⚙️ 4. Technologies and Tools Used

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| TensorFlow | Deep learning framework |
| Keras | Building neural network architectures |
| NumPy | Numerical computations |
| Matplotlib | Visualizing images and loss graphs |
| Google Colab | Model implementation and training |
| CIFAR-10 | Training dataset |

## 🏗️ 5. DCGAN Architecture

The DCGAN architecture consists of two major components that work together.

### A. Generator Network

The Generator creates synthetic images using random noise.

**Working process:**

1. Takes a random latent vector as input.
2. Passes it through a Dense layer.
3. Reshapes the output into a feature map.
4. Uses Transposed Convolution layers to increase image dimensions.
5. Uses Batch Normalization and ReLU activation.
6. Produces a 32 × 32 RGB synthetic image using Tanh activation.

**Generator architecture:**

Random Noise (128 dimensions)  
↓  
Dense Layer  
↓  
Reshape (4 × 4 × 512)  
↓  
Transposed Convolution (8 × 8)  
↓  
Transposed Convolution (16 × 16)  
↓  
Transposed Convolution (32 × 32)  
↓  
RGB Synthetic Image

### B. Discriminator Network

The Discriminator identifies whether an input image is real or generated.

**Working process:**

1. Takes a 32 × 32 RGB image as input.
2. Extracts image features using Convolutional layers.
3. Uses LeakyReLU activation.
4. Applies Batch Normalization and Dropout.
5. Uses Flatten and Dense layers.
6. Produces a real/fake prediction score.

**Discriminator architecture:**

Input Image (32 × 32 × 3)  
↓  
Convolutional Layer  
↓  
LeakyReLU + Dropout  
↓  
Convolutional Layers  
↓  
Batch Normalization  
↓  
Flatten  
↓  
Dense Layer  
↓  
Real or Fake Prediction

## 🔄 6. Working Methodology

The project follows these steps:

### Step 1: Dataset Loading

CIFAR-10 is downloaded using the TensorFlow dataset loader.

### Step 2: Data Preprocessing

- Convert image data into float32.
- Normalize pixel values from [0, 255] to [-1, 1].
- Prepare batches using TensorFlow Dataset.

### Step 3: Model Construction

Build the Generator and Discriminator using convolutional neural network layers.

### Step 4: Loss Function

Binary Cross-Entropy is used to calculate the loss of both networks.

- Generator Loss: Measures how unsuccessfully the Generator fools the Discriminator.
- Discriminator Loss: Measures how unsuccessfully the Discriminator identifies real and generated images.

### Step 5: Model Training

Both networks are trained through adversarial learning.

The Generator tries to generate realistic images, while the Discriminator tries to distinguish real images from fake images.

### Step 6: Image Generation

After training, random latent vectors are passed through the Generator to create synthetic images.

### Step 7: Performance Evaluation

The model is evaluated using:

- Generator loss graph.
- Discriminator loss graph.
- Generated image samples.
- Visual quality and diversity analysis.

## 🧮 7. Training Configuration

The improved experiment uses the following configuration:

| Parameter | Value |
|---|---|
| Dataset | CIFAR-10 |
| Epochs | 100 |
| Batch Size | 128 |
| Latent Dimension | 128 |
| Optimizer | Adam |
| Learning Rate | 0.0002 |
| Beta 1 | 0.5 |
| Generator Output | 32 × 32 × 3 |
| Loss Function | Binary Cross-Entropy |
| Output Activation | Tanh |

The training configuration can be modified depending on the available computational resources and experimental requirements.

## 📊 8. Results and Performance Evaluation

The trained DCGAN generates synthetic images using the learned patterns from the CIFAR-10 dataset.

Performance is evaluated through two major outputs.

### A. Generator and Discriminator Loss

The loss graph shows how both networks perform during adversarial training.

The Generator and Discriminator losses may fluctuate because both networks continuously compete with each other.

### B. Synthetic Image Generation

The Generator produces new images from random noise.

The generated samples demonstrate different colour patterns, textures and object-like structures.

However, some generated images may contain blur, distortion or unclear object details.

### Performance Evaluation Criteria

| Criteria | Evaluation |
|---|---|
| Model implementation | Generator and Discriminator implemented successfully |
| Training | Adversarial training completed |
| Loss analysis | Both loss curves plotted |
| Image generation | Synthetic images generated |
| Image clarity | Some images remain blurry |
| Image diversity | Different visual patterns generated |

## 📁 9. Project Structure

```text
DCGAN-CIFAR10/
│
├── DCGAN_CIFAR10_Improved_Complete.ipynb
│
├── dcgan_loss_curves.png
│
├── dcgan_final_generated_images.png
│
├── dcgan_training_history.npz
│
├── README.md
│
└── requirements.txt
```

**File descriptions:**

- `DCGAN_CIFAR10_Improved_Complete.ipynb` – Complete implementation and training notebook.
- `dcgan_loss_curves.png` – Generator and Discriminator loss visualization.
- `dcgan_final_generated_images.png` – Final synthetic images.
- `dcgan_training_history.npz` – Recorded training loss values.
- `README.md` – Project documentation.
- `requirements.txt` – Required Python libraries.

## 🚀 10. Installation and Execution

### Prerequisites

- Python 3.x
- Google Colab or Jupyter Notebook
- GPU recommended for faster training.

### Step 1: Clone the repository

```bash
git clone https://github.com/Sanika13112/DCGAN-CIFAR10_GenerativeAi.git
```

### Step 2: Navigate to the project directory

```bash
cd DCGAN-CIFAR10
```

### Step 3: Install dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Open the notebook

Open `DCGAN_CIFAR10_Improved_Complete.ipynb` using Google Colab or Jupyter Notebook.

### Step 5: Execute the notebook

Run all cells sequentially.

The CIFAR-10 dataset will be downloaded automatically, and the model will begin training.

## 📦 11. Requirements

Create a `requirements.txt` file containing:

```text
tensorflow
numpy
matplotlib
```

## ⚠️ 12. Limitations

- CIFAR-10 images have relatively low resolution (32 × 32).
- Generated images may contain blurry or distorted details.
- GAN training can be unstable.
- Generator and Discriminator losses may fluctuate.
- Image quality depends on model architecture, hyperparameters and training duration.
- Visual inspection alone does not provide a complete quantitative evaluation.

## 🔮 13. Future Improvements

Possible future enhancements include:

- Experimenting with deeper Generator and Discriminator architectures.
- Improving training stability through hyperparameter tuning.
- Exploring higher-resolution image datasets.
- Implementing Fréchet Inception Distance (FID) for quantitative image-quality evaluation.
- Comparing DCGAN with other generative models such as Conditional GANs and Variational Autoencoders.
- Exploring higher-quality image generation techniques.

## 🎓 14. Learning Outcomes

Through this project, the following concepts were explored:

- Generative Adversarial Networks.
- Deep Convolutional Neural Networks.
- Generator and Discriminator architecture.
- Transposed Convolution.
- Adversarial Training.
- Binary Cross-Entropy Loss.
- Model Optimization.
- Synthetic Image Generation.
- Loss Curve Analysis.

## 👩‍💻 15. Author

**Sanika Dhanaji Mane**

Artificial Intelligence and Machine Learning Engineering

### Project Domain
Generative Artificial Intelligence | Deep Learning | Computer Vision

---

⭐ If you find this project useful, consider giving the repository a star!

