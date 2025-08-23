# KIA Calculator - Baby Weight Prediction Model

[![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)](https://www.python.org/downloads/)
[![PyTorch](https://img.shields.io/badge/PyTorch-1.9+-red.svg)](https://pytorch.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

> **KIA (Kesehatan Ibu dan Anak)** - A machine learning model to predict baby weight based on growth parameters using WHO standards.

## 🌟 Features

- **Neural Network Model**: Deep learning model trained on WHO growth standards
- **Multi-parameter Input**: Uses head circumference, length, and age for predictions
- **Visualization**: Interactive 3D plots and 2D growth charts
- **WHO Standards**: Based on World Health Organization growth references
- **Real-time Prediction**: Instant weight predictions with condition assessment

## 📊 Model Performance

| Metric | Value |
|--------|-------|
| **MAE** | 0.1465 |
| **RMSE** | 0.2283 |
| **R² Score** | 0.9457 |
| **Average Error** | 0.034 kg |

## 🚀 Quick Start

### Prerequisites

```bash
pip install -r requirements.txt
```

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/kia-calculator.git
   cd kia-calculator
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Jupyter notebook**
   ```bash
   jupyter notebook KIA-calculator.ipynb
   ```

## 🧠 How It Works

### Input Parameters
- **Head Circumference** (cm): Baby's head circumference measurement
- **Length** (cm): Baby's body length/height
- **Age** (months): Baby's age in months (0-24 months)

### Model Architecture
```
Input Layer (3) → Hidden Layer 1 (32, Tanh) → Hidden Layer 2 (16, ReLU) → Output Layer (1)
```

### Prediction Process
1. **Data Normalization**: Input data is normalized using mean and standard deviation
2. **Neural Network**: Forward pass through the trained model
3. **Denormalization**: Output is converted back to actual weight values
4. **Assessment**: Compare with WHO median standards

## 📈 Usage Example

```python
# Example input data
new_data = torch.tensor([[45.2, 80.3, 16.0]], dtype=torch.float32)  # [head_circ, length, month]

# Make prediction
predicted_weight = model(new_data)
print(f"Predicted weight: {predicted_weight:.2f} kg")

# Condition assessment
if predicted_weight > who_median + 0.5:
    print("→ Overweight")
elif predicted_weight < who_median - 0.5:
    print("→ Underweight")
else:
    print("→ Normal condition")
```

## 📊 Visualizations

### 2D Growth Chart
- Actual vs Predicted weight comparison
- WHO median reference line
- Error margin visualization

### 3D Interactive Plot
- Growth path in 3D space
- Color-coded by weight
- Interactive test point placement

## 🏥 Medical Disclaimer

⚠️ **Important**: This tool is for educational and research purposes only. It should not replace professional medical advice. Always consult with healthcare professionals for accurate growth assessment and medical decisions.

## 📁 Project Structure

```
kia-calculator/
├── KIA-calculator.ipynb     # Main Jupyter notebook
├── requirements.txt         # Python dependencies
├── README.md               # This file
├── LICENSE                 # MIT License
└── .gitignore             # Git ignore file
```

## 🛠️ Technical Details

### Data Source
- **WHO Growth Standards**: Based on World Health Organization growth references
- **Official Source**: [CDC WHO Growth Charts](https://www.cdc.gov/growthcharts/who-growth-charts.htm) - Centers for Disease Control and Prevention
- **Age Range**: 0-24 months
- **Gender**: Female (girls) median values
- **Parameters**: Length-for-age, Weight-for-age, Head circumference-for-age

### Model Training
- **Epochs**: 500
- **Batch Size**: 5
- **Learning Rate**: 0.001
- **Optimizer**: Stochastic Gradient Descent (SGD)
- **Loss Function**: Mean Squared Error (MSE)


### How to Contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **World Health Organization (WHO)** for growth standards data
- **Centers for Disease Control and Prevention (CDC)** for providing the [WHO Growth Charts](https://www.cdc.gov/growthcharts/who-growth-charts.htm)
- **PyTorch** team for the deep learning framework
- **Matplotlib** and **Plotly** for visualization capabilities

## 📞 Contact

- **Project Link**: [https://github.com/yourusername/kia-calculator](https://github.com/yourusername/kia-calculator)
- **Issues**: [https://github.com/yourusername/kia-calculator/issues](https://github.com/yourusername/kia-calculator/issues)

---

<div align="center">
  <p>Made with ❤️ for maternal and child health</p>
  <p>⭐ Star this repository if you find it helpful!</p>
</div> 