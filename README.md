# ⚡ Power Plant Energy Output Prediction using Artificial Neural Networks (ANN)

## 📌 Project Overview

This project implements an **Artificial Neural Network (ANN)** using **PyTorch** to predict the electrical energy output of a power plant based on environmental conditions.

The model learns the relationship between several operational parameters and the plant's net hourly electrical energy output, demonstrating the application of deep learning techniques for regression problems.

---

## 🎯 Objective

To build and train a neural network capable of accurately predicting:

**PE (Net Hourly Electrical Energy Output)**

using the following input features:

- **AT** — Ambient Temperature
- **V** — Exhaust Vacuum
- **AP** — Ambient Pressure
- **RH** — Relative Humidity

---

## 🛠️ Technologies Used

- **Python**
- **PyTorch**
- **NumPy**
- **Pandas**
- **Scikit-Learn**
- **Matplotlib**

---

## 📂 Project Workflow

### 1. Data Loading
- Load the Power Plant dataset using Pandas.
- Perform initial data inspection.
- Check for missing values.

### 2. Data Preprocessing
- Separate features and target variable.
- Split data into training and testing sets.
- Standardize feature values using `StandardScaler`.

### 3. Data Conversion
- Convert NumPy arrays into PyTorch tensors.
- Create `TensorDataset` and `DataLoader` objects for efficient batch processing.

### 4. Neural Network Architecture

The ANN consists of:

| Layer | Neurons | Activation |
|---------|---------|------------|
| Input Layer | 4 | - |
| Hidden Layer 1 | 6 | ReLU |
| Hidden Layer 2 | 6 | ReLU |
| Output Layer | 1 | Linear |

---

## 🧠 Model Architecture

```python
Input (4 Features)
        │
        ▼
Linear(4 → 6)
        │
      ReLU
        │
        ▼
Linear(6 → 6)
        │
      ReLU
        │
        ▼
Linear(6 → 1)
        │
        ▼
Predicted Power Output
```

---

## ⚙️ Training Configuration

| Parameter | Value |
|------------|--------|
| Optimizer | Adam |
| Loss Function | Mean Squared Error (MSE) |
| Epochs | 100 |
| Framework | PyTorch |

---

## 📈 Training Process

During training:

- Forward propagation is performed.
- MSE loss is calculated.
- Backpropagation updates network weights.
- Validation loss is monitored after every epoch.
- The best-performing model is automatically saved.

```python
torch.save(model.state_dict(), "best_model.pt")
```

---

## 📊 Evaluation Metric

Model performance is evaluated using:

### R² Score (Coefficient of Determination)

```python
from sklearn.metrics import r2_score
```

A higher R² score indicates better predictive performance and stronger correlation between actual and predicted values.

---

## 🚀 Key Learning Outcomes

This project demonstrates:

- Deep Learning for Regression
- Building Custom Neural Networks in PyTorch
- Data Normalization and Preprocessing
- Training and Validation Loops
- Model Checkpointing
- Performance Evaluation using R² Score

---

## 📁 Project Structure

```text
PowerPlant-ANN-Regression/
│
├── PowerPlant ANN Regression.ipynb
├── best_model.pt
└── README.md
```

---

### Install Dependencies

```bash
pip install numpy pandas matplotlib scikit-learn torch
```
---

## 🔮 Future Improvements

- Hyperparameter tuning
- Experiment with deeper architectures
- Early stopping implementation
- Learning rate scheduling
- K-Fold Cross Validation
- Model deployment using Flask or FastAPI

---

## 🤝 Contributions

Contributions, suggestions, and improvements are welcome. Feel free to fork the repository and submit a pull request.

---

## 📜 License

This project is licensed under the MIT License.

---

### ⭐ If you found this project useful, consider giving the repository a star!
