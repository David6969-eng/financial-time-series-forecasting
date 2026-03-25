# 📈 FinSignal — Pattern Recognition for Financial Time Series Forecasting

> **Second Assignment** | Pattern Recognition Course  
> Department of Computer Science & Engineering

---

## 👥 Team Members

| Name | Roll Number |
|------|-------------|
| David Chacko Binoy | TCR24CS022 |
| Abhiram H | TCR24CS002 |

---

## 📌 Objective

Explore how **time–frequency signal processing** and **deep learning** can be combined to predict stock prices using financial time series data.

---

## 📂 Project Structure

```
├── index.html        # Main website (single-file, no dependencies)
└── README.md         # Project documentation
```

---

## 🧠 Methodology

### 1. Signal Representation
Financial data is modeled as a multivariate signal:

```
X(t) = [ p(t),  r(t),  g(t),  s(t),  d(t) ]
```

| Symbol | Description |
|--------|-------------|
| `p(t)` | Stock Price vs Time |
| `r(t)` | Revenue vs Quarter |
| `g(t)` | Profit vs Quarter |
| `s(t)` | Market Index (Sensex) vs Time |
| `d(t)` | USD–INR Exchange Rate vs Time |

### 2. Time–Frequency Transformation (STFT)

Financial time series are **non-stationary**, so a Short-Time Fourier Transform (STFT) is applied:

```
STFT(t, f) = ∫ X(τ) · w(τ−t) · e^(−j2πfτ) dτ
```

The **spectrogram** is computed as:

```
S(t, f) = | STFT(t, f) |²
```

**Sliding Window Parameters:**
- `L` — Window Length (samples per segment)
- `H` — Hop Size (step between windows)
- `L − H` — Overlap

### 3. CNN Prediction Model

A CNN regression model is trained on spectrograms to predict future prices:

```
p̂(t + Δt) = f_θ(S_t)
```

**Architecture:**
```
Input (Spectrogram)
    → Conv2D + ReLU (32 filters)
    → MaxPool (2×2)
    → Conv2D + ReLU (64 filters)
    → MaxPool (2×2)
    → Flatten → Dense (128)
    → Output (p̂)
```

---

## ✅ Tasks

### Task 1 — Data Preparation
- Collect time series data for at least 3 companies
- Align all variables to a common time scale
- Normalize the data

### Task 2 — Signal Processing
- Apply Fourier Transform
- Generate spectrograms using STFT
- Visualize spectrograms

### Task 3 — Model Development
- Design a CNN regression model
- Train the model using spectrograms
- Predict future stock prices

### Task 4 — Analysis
- Compare predictions with actual values
- Evaluate using **MSE (Mean Squared Error)**
- Analyze effect of different input features

---

## 📊 Required Figures

- [ ] Time series plot
- [ ] Frequency spectrum
- [ ] Spectrogram visualization
- [ ] CNN architecture diagram

---

## 🌐 Data Sources

| Source | URL |
|--------|-----|
| Yahoo Finance | https://finance.yahoo.com |
| NSE India | https://www.nseindia.com |
| BSE India | https://www.bseindia.com |
| RBI Database | https://www.rbi.org.in |
| Kaggle | https://www.kaggle.com |

---

## 🚀 Running the Website

This project is a **single HTML file** with no dependencies or build step required.

```bash
# Clone the repo
git clone https://github.com/<your-username>/<repo-name>.git

# Open in browser
open index.html
```

Or deploy on **GitHub Pages**:
1. Go to repo **Settings → Pages**
2. Set source to `main` branch, root folder
3. Access at `https://<your-username>.github.io/<repo-name>/`

---

## 📚 References

1. Y. Zhang and C. Aggarwal — *"Stock Market Prediction Using Deep Learning,"* IEEE Access.
2. A. Tsantekidis et al. — *"Deep Learning for Financial Time Series Forecasting."*
3. S. Hochreiter and J. Schmidhuber — *"Long Short-Term Memory,"* Neural Computation, 1997.
4. A. Borovykh et al. — *"Conditional Time Series Forecasting with CNNs."*

---

## 🎯 Expected Outcome

- ✅ Financial time series can be analyzed as signals
- ✅ Spectrograms reveal hidden temporal patterns
- ✅ CNN models can learn useful representations for prediction

---

*Assignment II — Pattern Recognition | B.Tech Computer Science & Engineering*
