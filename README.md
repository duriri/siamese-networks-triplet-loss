# 🧠🖼️ Image Classification with Triplet Loss using CNN

This project implements a Convolutional Neural Network (CNN) with triplet loss for image classification of four animal classes: Dog, Cat, Spider, and Chicken. 🐶🐱🕷️🐔

## 😺 Dataset
- Classes: Dog ('cane'), Cat ('gatto'), Spider ('ragno'), Chicken ('gallina')
- 📊 Original class distribution:
  - 🐶 'cane': 4863 images  
  - 🐔 'gallina': 3098 images  
  - 🐱 'gatto': 1668 images  
  - 🕷️ 'ragno': 4821 images  
- 🖼️ All images are resized to 100×100 pixels and converted to grayscale

## 🧹 Data Preprocessing
1. ♾ **Data Augmentation**:
   - 🧪 Applied to address class imbalance
   - All classes:
     - 🔁 50% chance of horizontal flip
     - 💡 50% chance of brightness adjustment (±20%)
   - 🔬 Additional augmentation for minority classes ('gallina' and 'gatto'):
     - 🌫️ 50% chance of adding Gaussian noise

2. ✂️ **Data Splitting**:
   - 📚 Training set: 25,000 images  
   - 🧪 Validation set: 5,500 images  
   - 🧾 Test set: 5,500 images

3. ↔ **Normalization**:
   - 🔢 Images converted to float32 format  
   - 📉 Pixel values scaled to [0,1] range by dividing by 255

## 🧱💻 Model Architecture
The CNN consists of 5 convolutional blocks with the following components:

- 🧠 **Convolutional Layers**:
  - Varying filter depths from 64 to 512  
  - ⚡ ReLU activation functions

- 🛡️ **Regularization**:
  - 🚿 Dropout layers to prevent overfitting  
  - 📉 Max Pooling for dimensionality reduction

- 📦 **Output**:
  - 🔺 Produces a 512-dimensional embedding vector

## ⚙️ Training Configuration
| ⚙️ Parameter         | 🔢 Value        |
|---------------------|----------------|
| 🖼️ Input image shape | 100×100×1       |
| 🧬 Embedding size    | 512             |
| 🕰️ Epochs            | 65              |
| 🧠 Learning rate     | 0.0006          |
| 📦 Batch size        | 128             |
| ⏱️ Step size         | 10              |
| 🧩 Components        | 2               |

## 👶🏻👶🏻👶🏻 Triplet Loss Implementation
Uses **semi-hard triplet loss** with three key components:
1. 🧮 `pairwise_distance`: Computes pairwise distance matrix between samples  
2. 🚧 `masked_maximum`: Calculates maximum distance between pairs  
3. 🕵️‍♀️ `masked_minimum`: Calculates minimum distance between pairs  

Each triplet consists of:
- 🎯 Anchor (a): Selected image from dataset  
- 👍 Positive (p): Image from same class as anchor  
- 👎 Negative (n): Image from different class than anchor

## 🏋️‍♂️ Training Process
- 🧠 **Optimizer**: Adam  
- 📉 **Loss Function**: Semi-hard triplet loss  
- 🔗 The model combines:  
  1. 🏗️ Base network (produces image embeddings)  
  2. 🔧 Custom model (combines base network with input labels)

## 📈 Results
📉 Training and validation loss curves are available in the project files.

## 📦 Requirements
- 🧠 TensorFlow/Keras  
- 🧮 NumPy  
- 📊 Matplotlib (for visualization)  
- 🧰 Standard Python data processing libraries

## 🙋‍♀️ Author

**Faeze Abdoli Nejad**  
🎓 M.Sc. in AI (specialized in NLP & LLMs)  
📢 [Telegram: @Ml_duriri](https://t.me/Ml_duriri) – *Simplifying AI for Everyone*

---

## 📄 License

🪪 MIT License – free to use, share, and modify with attribution.
