# HideNet – CNN Prediction Based Reversible Data Hiding

**HideNet** is a research project implemented as part of our B.Tech coursework at **NIT Jalandhar**.  
It is based on the paper:  
📄 *Runwen Hu and Shijun Xiang, “CNN Prediction Based Reversible Data Hiding,” IEEE Signal Processing Letters, 2021.*

The project demonstrates a **deep learning approach for Reversible Data Hiding (RDH)** using a CNN predictor.  
Unlike traditional predictors, HideNet improves pixel prediction accuracy, allowing us to embed more data (10,000 bits) into an image while preserving high visual quality and enabling perfect recovery of the original image.

---

## 🔍 Project Overview

Reversible Data Hiding (RDH) is a technique where **data is hidden inside an image**, but both:
- The secret data, and  
- The original cover image  

can be **perfectly recovered**.  

### What HideNet Does
1. Splits the image into **Cross** and **Dot** sets.  
2. Trains a CNN predictor to estimate missing pixel values.  
3. Embeds **10,000 secret bits** into the prediction error using:  
   - **Prediction Error Expansion (PEE)**  
   - **Histogram Shifting (HS)**  
4. Extracts the secret bits and reconstructs the original image.  

### Why CNN?
- CNN predictor uses **multi-receptive fields** (3×3, 5×5, 7×7 filters)  
- Outperforms traditional predictors in terms of **MSE and PSNR**  
- Allows **higher embedding capacity with lower distortion**  

---

## 📂 Repository Structure

```bash
HideNet/
│── src/
│   ├── cnnp_training.py     # Train CNN predictor
│   ├── rdh_demo.py          # Run embedding + extraction demo
│── README.md                # Project documentation
│── requirements.txt         # Python dependencies
│── examples/                # Example input/output images

```

---

## ⚙️ Setup & Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/gopiraman27/HideNet.git
   cd HideNet
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

---

## 🚀 Usage

### 1. Train the CNN Predictor

Run the following script to train the CNN model on sample images:

```bash
python src/cnnp_training.py
```

This will download a sample dataset, train the model, and save weights to the specified path.

### 2. Run the RDH Demo

After training, run the demo to embed and extract data:

```bash
python src/rdh_demo.py
```

The script will:
- Download standard test images
- Load the trained model
- Embed 10,000 bits into a test image
- Extract the bits and verify perfect recovery
- Display results and metrics (MSE, PSNR, embedding rate)

---

## 📝 Notes
- The code is designed for educational and research purposes.
- For best results, use a CUDA-enabled GPU (but CPU is supported).
- All images are resized to 512x512 grayscale for consistency.
- Model weights and test images are saved in the working directory.

---

## 📖 Citation

If you use this code or ideas in your research, please cite:

> Runwen Hu and Shijun Xiang, “CNN Prediction Based Reversible Data Hiding,” IEEE Signal Processing Letters, 2021.

---

