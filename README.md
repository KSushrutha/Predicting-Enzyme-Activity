# 🧪 Enzyme Speed Test: Finding Max Power ($V_{\text{max}}$) and Affinity ($K_m$)

This project uses Python and fundamental machine learning concepts to analyze raw enzyme kinetic data. By transforming the data into a linear format (the Lineweaver-Burk plot), we use simple linear regression to determine key biochemical parameters such as $K_m$ and $V_{\text{max}}$ with high confidence.

---

## 💻 Tech Stack

This analysis was performed using:

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

## 📊 Example Results (37°C, pH 7.0)

From `EnzymePrediction.ipynb`:

- ⭐ **Confidence Score (R²):** 0.9999  
- 🧮 **Mean Squared Error (MSE):** 0.0000  
- ⚡ **Vmax:** 3095.21 µM/min  
- 🎯 **Km:** 5.562 mM  

### 🔍 Interpretation

- The enzyme is **most efficient at 37°C, pH 7.0**.  
- A moderately low $K_m$ suggests reasonable substrate affinity.  
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

Early on, the model’s accuracy was limited due to noise and inconsistencies in the data. After refining the dataset and improving preprocessing steps, the regression achieved an almost perfect R² score, demonstrating how crucial high-quality data is for reliable enzyme-kinetic modeling.


## 👤 Author

**By: _Sushrutha Konduru_**
