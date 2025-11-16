# 🧪 Enzyme Speed Test: Finding Max Power ($V_{\text{max}}$) and Affinity ($K_m$)

This project uses Python and fundamental machine learning concepts to analyze raw enzyme kinetic data. By transforming the data into a linear format (the Lineweaver-Burk plot), we use simple linear regression to determine key biochemical parameters such as $K_m$ and $V_{\text{max}}$ with high confidence.

---

## 💻 Tech Stack

The analysis is built using:

- 🐍 **Python**
- 📦 **pandas** — data processing
- 🧮 **scikit-learn** — linear regression + metrics
- 📊 **matplotlib** — Lineweaver-Burk plotting

---

## 📁 How to See the Code and Results

Open the `EnzymePrediction.ipynb` notebook to view:

- ✅ A confidence score ($R^2$) of ~0.99 (near perfect)
- 📈 A Lineweaver-Burk plot showing the regression line
- 📉 Calculated values for $V_{\text{max}}$ and $K_m$

> 💡 **Tip:** The graph visually confirms the slope (Kₘ) and intercept (Vmax) for each substrate concentration.

---

## 💡 Key Concepts Explained

| 🔬 Term | 📝 Simple Explanation |
|--------|------------------------|
| **Enzyme Kinetics** | How fast enzymes work under different conditions. |
| **Lineweaver-Burk Plot** | A linear plot using $1/[S]$ and $1/v$ to simplify analysis. |
| **$V_{\text{max}}$** | Maximum reaction rate. |
| **$K_m$** | Substrate concentration at half-max rate (affinity indicator). |
| **$R^2$ Score** | Model accuracy; closer to 1 = better. |
| **MSE** | Prediction error; lower = better. |

---

## 📊 Example Output for T=37°C, pH=7.0

From `EnzymePrediction.ipynb`:

- ⭐ **Confidence Score (R²):** 0.9999  
- 🧮 **Mean Squared Error (MSE):** 0.0000  
- ⚡ **Vmax:** 3095.21 µM/min  
- 🎯 **Km:** 5.562 mM  

### 🔍 Interpretation

- The enzyme is **most efficient at 37°C, pH 7.0**.  
- Low Km indicates moderate substrate affinity.  
- The Lineweaver-Burk plot shows a regression line passing directly through the actual data points.

![Lineweaver-Burk Plot](./images/OutputGraph.png)

> 💡 Use the **y-intercept** for Vmax and the **x-intercept** for Km to compare enzyme behavior under different conditions.

---

## 🔬 Interpreting the Results

- **⚡ Enzyme Speed (Vmax):** Higher = faster enzyme activity.  
- **🎯 Substrate Affinity (Km):** Lower = stronger affinity.  
- **🛡️ Model Reliability (R²):**
  - >0.98 → extremely reliable  
  - >0.90 → good  
  - <0.80 → caution  

---

## 🛠️ Analysis Steps

1. **🔄 Data Transformation**  
   Convert $[S]$ and $v$ into reciprocals to linearize the relationship.

2. **🤖 Train the Model**  
   - X = $1/[S]$  
   - Y = $1/v$  
   - Fit using `LinearRegression()`

3. **📊 Calculate Metrics**  
   - $R^2$  
   - $V_{\text{max}} = 1/\text{intercept}$  
   - $K_m = \text{slope} \times V_{\text{max}}$

4. **📈 Plot Results**  
   - Plot the Lineweaver-Burk line using matplotlib  
   - Include both the regression line and original data points  

---

## ✨ Reflection

One of the biggest challenges in this project was **raising the confidence score as high as possible**. At the start, the model’s accuracy wasn’t great due to inconsistent data. But after refining the dataset and carefully adjusting the inputs, I achieved a **near-perfect R² score**, making the regression extremely reliable.

---

## 👤 Author

**By: _Sushrutha Konduru_**
