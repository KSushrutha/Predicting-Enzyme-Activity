# 🧪 Enzyme Speed Test: Finding Max Power ($V_{\text{max}}$) and Affinity ($K_m$)

This project uses Python and fundamental machine learning concepts to analyze raw enzyme kinetic data. By transforming the data into a linear format (the Lineweaver-Burk plot), we can use simple linear regression to accurately determine key biochemical parameters, such as $K_m$ and $V_{\text{max}}$, with high confidence.

---

## 💻 Tech Stack

The analysis is built entirely using Python and its core scientific libraries:

- **Language:** Python 🐍
- **Data Processing:** pandas
- **Modeling & Metrics:** scikit-learn (`LinearRegression`, `r2_score`)
- **Visualization:** matplotlib (for plotting the Lineweaver-Burk line)

---

## 📁 How to See the Code and Results

To view the specific code, the calculated output values, and the generated Lineweaver-Burk plot, please navigate to the `EnzymePrediction.ipynb` file.

---

## 💡 Key Concepts Explained

| Complicated Term | Simple Explanation |
|-----------------|------------------|
| **Enzyme Kinetics** | The study of how fast enzymes work (their speed) and how they are affected by things like temperature and the amount of "food" (substrate) they have. |
| **Lineweaver-Burk Plot** | Turns the curved relationship between enzyme speed and substrate amount into a straight line using reciprocals ($1/[S]$ and $1/v$), making calculations easier. |
| **$V_{\text{max}}$ (Maximum Velocity)** | The absolute fastest rate the enzyme can work when fully saturated with substrate. |
| **$K_m$ (Michaelis Constant)** | Measures affinity—how strongly the enzyme "likes" its substrate. Lower $K_m$ = higher affinity. |
| **$R^2$ Score** | Confidence score of the linear model; close to 1.0 = excellent fit. |
| **Mean Squared Error (MSE)** | Average squared difference between actual points and predicted line; close to 0 = excellent fit. |

---

## 🔬 Interpreting the Results

The output values show the enzyme's performance under a specific test condition (e.g., $37^\circ\text{C}$, pH 7.0):

1. **Enzyme Speed & Power ($V_{\text{max}}$)**  
   - **What it measures:** Ultimate potential of the enzyme.  
   - **How to judge:** Highest $V_{\text{max}}$ indicates optimal condition.  
   - **Example:** $V_{\text{max}}$ at 37°C = 3000 µM/min, at 50°C = 500 µM/min → enzyme is five times more powerful at 37°C.

2. **Enzyme Efficiency & Affinity ($K_m$)**  
   - **What it measures:** How well the enzyme binds substrate.  
   - **How to judge:**  
     - Low $K_m$ → high affinity, efficient enzyme.  
     - High $K_m$ → low affinity, less efficient.  
   - **Example:** Lower $K_m$ at pH 7.0 than at pH 6.0 → enzyme more efficient at pH 7.0.

3. **Model Trustworthiness ($R^2$ Score)**  
   - **What it measures:** Reliability of $V_{\text{max}}$ and $K_m$.  
   - **Interpretation:**  
     - >0.98 → excellent fit, fully trust the parameters.  
     - >0.90 → good fit, some noise may exist.  
     - <0.80 → poor fit, parameters should be viewed cautiously.

---

## 🛠️ Analysis Steps

1. **Data Transformation (The Reciprocal Step)**  
   - Transform Substrate ($[S]$) and Initial Rate ($v$) into reciprocals ($1/[S]$ and $1/v$) for a straight-line relationship.  

2. **Isolation & Model Training**  
   - Filter data for a single condition (e.g., 37°C, pH 7.0).  
   - Train a `LinearRegression` model with $1/[S]$ as X and $1/v$ as Y.  

3. **Calculation & Metrics**  
   - Compute $R^2$ score as a confidence metric.  
   - Determine kinetic parameters:  
     - $V_{\text{max}} = 1/\text{Intercept}$  
     - $K_m = \text{Slope} \times V_{\text{max}}$  

4. **Visualization**  
   - Use matplotlib to plot the Lineweaver-Burk plot.  
   - Show data points, regression line, and intercepts to confirm $V_{\text{max}}$ and $K_m$.  
