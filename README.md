# dna-trait-prediction
# 🧬 darwin-meets-deeplearning

> *What if a machine learning model could quantify the boundary between inheritance and evolution?*

---

## Overview

This project explores the predictability of child genetic traits from parental genetics using multiple machine learning models. The central finding is not just a number — it's a **biological insight**:

> **All models converge at ~76% accuracy — and the remaining 24% isn't model failure. It's evolution.**

---

## 🔬 The Core Finding

| Model | Accuracy |
|---|---|
| Neural Network (Keras) | ~76-77% |
| Random Forest | 76.5% |
| XGBoost | 75.7% |
| **Consensus Ceiling** | **~76%** |

When three fundamentally different algorithms — deep learning, ensemble trees, and gradient boosting — all plateau at the same accuracy, the conclusion isn't *"tune more hyperparameters."* It's that the data itself has a natural ceiling.

---

## 💡 The Biological Interpretation

```
76% = What parents reliably pass down       → Conservation
24% = What nature experiments with          → Evolution
```

The unpredictable 24% maps directly to known biological mechanisms:

- **Genetic Recombination** — chromosomal crossover during meiosis shuffles gene combinations randomly
- **Random Mutation** — DNA copying introduces novel variations
- **Epigenetics** — environmental factors switch genes on/off unpredictably
- **Incomplete Dominance** — neither parental trait fully expresses in the child
- **Polygenic Complexity** — complex traits depend on hundreds of genes, not just 12

This randomness is not a flaw. It is a **survival mechanism** — genetic diversity ensures that no single pathogen or environmental shift can eliminate an entire lineage. The 24% is DNA protecting and reinventing itself across generations.

---

## 📊 Dataset

- **Samples:** 7,000 (5,600 train / 1,400 test)
- **Features:** 12 parental genetic markers
- **Target:** 3 child trait classes
- **Preprocessing:** StandardScaler normalization + one-hot encoding

---

## 🏗️ Model Architecture (Neural Network)

```python
Sequential([
    Dense(256, activation='relu', input_shape=(12,)),
    Dropout(0.3),
    Dense(128, activation='relu'),
    Dropout(0.2),
    Dense(64, activation='relu'),
    Dense(3, activation='softmax')
])

optimizer = Adam(learning_rate=0.0005)
loss      = categorical_crossentropy
epochs    = 100 (early stopping, patience=15)
batch     = 32
```

---

## 📈 Training Curves

The final training curve shows:
- ✅ Fast convergence in early epochs
- ✅ Minimal overfitting gap (~2%)
- ✅ Stable plateau — no oscillation

*Training Accuracy: ~77% | Validation Accuracy: ~73%*

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.11-blue?style=flat-square&logo=python)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Keras-orange?style=flat-square&logo=tensorflow)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-RandomForest-green?style=flat-square&logo=scikit-learn)
![XGBoost](https://img.shields.io/badge/XGBoost-GradientBoosting-red?style=flat-square)

---

## 🚀 Getting Started

```bash
# Clone the repo
git clone https://github.com/Abhishek0077-cs/darwin-meets-deeplearning.git
cd darwin-meets-deeplearning

# Install dependencies
pip install -r requirements.txt

# Run the notebook
jupyter notebook genetics_trait_prediction.ipynb
```

---

## 📁 Project Structure

```
darwin-meets-deeplearning/
│
├── data/
│   └── parental_genetics.csv
│
├── notebooks/
│   └── genetics_trait_prediction.ipynb
│
├── models/
│   ├── neural_network.py
│   ├── random_forest.py
│   └── xgboost_model.py
│
├── plots/
│   └── training_validation_accuracy.png
│
├── requirements.txt
└── README.md
```

---

## 🧠 Key Takeaways

1. **ML can quantify biological heritability** — the ~76% accuracy aligns with real-world heritability coefficients for complex traits
2. **Model diversity validates findings** — when ANN, RF, and XGBoost agree, it's the data speaking, not the model
3. **Unpredictability has purpose** — the 24% "error" represents genetic variation that drives evolution and species resilience
4. **Neural networks ≠ always best** — on tabular genetic data, simpler models perform comparably

---

## 🔭 Future Scope

- [ ] Expand to more genetic markers (SNP data)
- [ ] Incorporate epigenetic features
- [ ] Test on real genomic datasets (e.g., 1000 Genomes Project)
- [ ] Visualize feature importance per trait class
- [ ] Deploy as a web app for interactive prediction

---

## 👤 Author

**Abhishek Singh**
- GitHub: [@Abhishek0077-cs](https://github.com/Abhishek0077-cs)
- LinkedIn: [abhishek-singh-224710250](https://linkedin.com/in/abhishek-singh-224710250)

---

## 📜 License

MIT License — feel free to use, modify, and build upon this work.

---

*"It is not the strongest of the species that survives, nor the most intelligent. It is the one most responsive to change."* — Charles Darwin
