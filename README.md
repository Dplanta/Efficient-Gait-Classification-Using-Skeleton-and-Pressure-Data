# Efficient Gait Classification Using Skeleton and Pressure Data: Deep and Spiking Neural Network Approaches
This repository contains the research findings for a project developed for the exam Machine Learning for Human Data: "Efficient Gait Classification Using Skeleton and Pressure Data: Deep and Spiking Neural Network Approaches".
The project explores the use of non-wearable sensors to automate the classification of one normal and five pathological gait patterns (Antalgic, Lurching, Steppage, Stiff-Legged, and Trendelenburg).

## Project Overview
Gait Analysis is a vital diagnostic tool in medicine. In this research we present Deep Learning models that leverage 3D skeleton data (captured via Azure Kinect) and foot pressure measurements (captured via a GW1100 pressure plate).
We developed and compared four distinct models:

- SkGRU: A Gated Recurrent Unit (GRU) encoder for 3D skeleton sequences
- PrCNN: A Convolutional Neural Network (CNN) for plantar pressure images
- HyM (Hybrid Model): A multimodal fusion model combining features from both SkGRU and PrCNN
- SkSNN: A Spiking Neural Network (SNN) based on skeleton data, designed for low-latency and high-efficiency neuromorphic hardware

 ## Performance summary

 | Model | Parameters | Accuracy | Inference Time (ms) |
| :--- | :--- | :--- | :--- |
| **HyM (Hybrid)** | 2.63M | 🟢 **94.8%** | 6.27 |
| **SkGRU** | 895k | 🟢 **94.2%** | 3.67 |
| **SkSNN** | 314k | 🟡 **83.2%** | 4.39 |
| **PrCNN** | 1.75M | 🔴 **48.9%** | 4.46 |

### Key Takeaways
- Multimodal Advantage: The Hybrid Model (HyM) achieves the highest accuracy by merging different sensor modalities
- Efficiency: The SkGRU model offers the best trade-off between performance and computational speed
- Neuromorphic Potential: The SkSNN is extremely lightweight (only 12% of the parameters of the Hybrid model), serving as a foundation for future applications

## Tech Stack
- Programming Language: Python
- Deep Learning: TensorFlow, Keras
- SNN Framework: snnTorch, PyTorch
- Environment: Google Colab (T4 GPU)
