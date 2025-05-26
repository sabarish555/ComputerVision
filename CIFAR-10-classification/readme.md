# 🧠 CIFAR-10 Image Classification using PyTorch

This project implements a **Convolutional Neural Network (CNN)** from scratch to classify images from the **CIFAR-10** dataset using **PyTorch**. The notebook is designed to demonstrate hands-on experience in building and training deep learning models for computer vision tasks, emphasizing critical concepts such as **ReLU activation**, **softmax output**, **cross-entropy loss**, **backpropagation**, and **GPU acceleration**.

Keywords: PyTorch, CIFAR-10, CNN, Image Classification, Deep Learning, Computer Vision


---

## 📌 Project Summary

Key highlights of this project:

- 🖼️ Data loading and normalization of CIFAR-10 images using `torchvision.datasets`
- 🧠 Design and implementation of a **CNN architecture** with multiple convolutional and pooling layers
- 🔁 Use of **ReLU (Rectified Linear Unit)** activations to introduce non-linearity
- 🧮 Application of **cross-entropy loss**  for robust training
- 🎯 Evaluation of the model using test accuracy and loss metrics
- 📉 Visualization of training and validation performance
- 💾 Saving the trained model using `torch.save()` for inference

---

## 🏗️ Model Architecture

The network consists of:

- `Conv2d` → `ReLU` → `MaxPool2d`
- `Conv2d` → `ReLU` → `MaxPool2d`
- Fully connected (`Linear`) layers
- **Softmax** at the output for multi-class classification

This architecture learns **spatial hierarchies** of features through **convolutional kernels**, followed by non-linear activations and downsampling operations.

---

## 🔧 Technologies Used

| Tool/Library   | Description                                    |
|----------------|------------------------------------------------|
| PyTorch        | Deep learning framework for model training     |
| Torchvision    | For loading and transforming CIFAR-10 dataset  |
| NumPy          | Efficient array operations                     |
| Matplotlib     | Visualization of accuracy/loss curves          |
| Jupyter Notebook | Interactive development and experimentation |

---

## ⚙️ Training Details

- **Loss Function**: `nn.CrossEntropyLoss()`  
- **Activation**: `nn.ReLU()`  
- **Output Layer**: `nn.Softmax(dim=1)`  
- **Epochs**: 4 (tunable)
- **Batch Size**: 4 (configurable)
- **Device**: CPU / GPU (`torch.device("cuda" if torch.cuda.is_available() else "cpu")`)

---

## 🧪 Results & Evaluation

After training, the model achieves:

- **Test Accuracy**: ~60% 
- **Visualized predictions** on test images with class labels


## 🛠️ Setup Instructions

1. **Install dependencies:**

```bash
pip install torch torchvision matplotlib numpy jupyter

