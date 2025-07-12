# Generative-Adversarial-Network-GAN-on-MNIST-Digits
This project implements a **Generative Adversarial Network (GAN)** using **Keras** and **TensorFlow** to generate handwritten digits similar to those in the **MNIST dataset**.
It consists of:
- A **Generator** that produces fake digit images from random noise.
- A **Discriminator** that distinguishes real images from generated ones.
- A combined **GAN model** that trains the generator to fool the discriminator.

---

##  Technologies Used

- Python 🐍
- TensorFlow / Keras
- NumPy
- Matplotlib

---

**Install dependencies:**
pip install -r requirements.txt

---

📊 **Project Overview**
1. Data Preparation
MNIST images are loaded and reshaped from (28, 28) to flat vectors (784,).

Pixel values are normalized to [0, 1].
x_train = x_train.reshape(-1, 784).astype('float32') / 255.0

2. Generator Architecture
Transforms a random noise vector (100 dimensions) into a fake image of shape 784 (28×28).
Dense(256) → LeakyReLU
Dense(512) → LeakyReLU
Dense(784) → Sigmoid

3. Discriminator Architecture
A binary classifier that takes a 784-d image and predicts if it's real or fake.
Dense(512) → LeakyReLU → Dropout
Dense(256) → LeakyReLU → Dropout
Dense(1)   → Sigmoid

4. Training Strategy
Each epoch consists of:

Training the Discriminator on both real and fake images (with soft labels: 0.9 for real, 0.0 for fake).

Training the Generator via the combined GAN model to fool the discriminator.

5. Visualization
After training, 10 generated fake digit images are displayed.

Generator and Discriminator loss plots are also visualized.

---

📌 **Key Features**
Eager execution enabled for better debugging.

Soft labels (0.9) used for real images to stabilize training.

Separate optimizers for generator and discriminator to avoid optimizer state conflicts.

Automatic plotting of losses and sample generations after training.

---

**Contributing**
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

---

🙋‍♂️ **Acknowledgments**
Ian Goodfellow for inventing GANs.

TensorFlow/Keras team for the open-source framework.

MNIST dataset provided by Yann LeCun and collaborators.


---

Let me know if you'd like this converted into a Jupyter Notebook with markdown and code cells, or a Colab version for interactive use.
