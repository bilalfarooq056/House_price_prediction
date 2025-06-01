

# 🏠 House Price Prediction Using Decision Tree (Zameen.com Data)

This project implements a **Decision Tree Regressor** to predict **house prices in Pakistan** using real estate listings from **Zameen.com**. The model processes price strings, area formats, and location details to create a powerful regression model for price estimation.

---

## 📂 Dataset

- **File:** `zameen_homes_data_v1.csv`
- **Columns Used:**
  - `price`
  - `area`
  - `bedrooms`
  - `bathrooms`
  - `location`
  - *(optional features)* `floors`, `parking_spaces`, `furnished`

---

## 🧠 Machine Learning Model

- **Model:** `DecisionTreeRegressor` from `scikit-learn`
- **Target Variable:** `price` (converted to float in PKR)
- **Input Features:**
  - Area (in Marla)
  - Bedrooms
  - Bathrooms
  - Encoded Neighborhood (from location)
  - Parking Spaces
  - Furnished (binary flag)

---

## ⚙️ Preprocessing Pipeline

1. **Price Conversion:**  
   - Convert strings like `"PKR 3.5 Crore"` into numeric PKR values.

2. **Area Conversion:**  
   - Convert `kanal`, `marla`, and `square feet` into a unified Marla format.

3. **Neighborhood Encoding:**  
   - Extract neighborhood from the location and apply label encoding.

4. **Missing Values Handling:**  
   - Use numeric conversion, fill with zeros, or drop rows with missing core features.

---

## 📊 Evaluation Metrics

The model is evaluated using standard **regression metrics**:

| Metric | Description |
|--------|-------------|
| **MAE** | Mean Absolute Error |
| **RMSE** | Root Mean Squared Error |
| **MAPE** | Mean Absolute Percentage Error |
| **Accuracy** | Estimated as `100 - MAPE` |

---

## 📈 Model Visualization

The trained decision tree is visualized using `plot_tree()`:

```python
from sklearn.tree import plot_tree
plot_tree(dt_model, feature_names=X.columns, filled=True)
````

This shows how the model splits based on area, bedrooms, and neighborhood to make price predictions.

---

## 🧪 Sample Prediction

You can make predictions using new input data:

```python
area = 23
bedrooms = 6
bathrooms = 6
neighborhood_input = "F-7"
parking_spaces = 1
furnished = 0
```

**Example Output:**

```
Predicted Price for 23 Marla, 6 Bed, 6 Bath in F-7 = PKR 76,000,000
```

---

## 💾 Model Saving

The trained model is saved using `joblib` for future use:

```python
import joblib
joblib.dump(dt_model, "decision_tree_house_price_model.pkl")
```

---

## 🛠 Requirements

Install required libraries with:

```bash
pip install -r requirements.txt
```

**Dependencies:**

* `pandas`
* `numpy`
* `scikit-learn`
* `matplotlib`
* `joblib`

---

## 📁 Files in Repository

| File                                  | Description                       |
| ------------------------------------- | --------------------------------- |
| `house_price_model.py`                | Main training & evaluation script |
| `zameen_homes_data_v1.csv`            | Source dataset                    |
| `decision_tree_house_price_model.pkl` | Saved model for reuse             |
| `README.md`                           | Project documentation             |

---

## 👨‍💻 Author

**Bilal Farooq**
Artificial Intelligence Student, **FAST-NUCES**

---

## 📌 Notes

* This is a **regression task**, not classification.
* Accuracy is estimated using **MAPE**; focus is on **realistic price estimation**.
* The feature `floors` was excluded from the final model due to **inconsistent or missing values**.

Great! Below are the requested additions for your project:

---

## ✅ `requirements.txt`

Here’s a minimal `requirements.txt` file you can include to install dependencies:

```
pandas
numpy
scikit-learn
matplotlib
joblib
```

Save this content as a file named:

```bash
requirements.txt
```

---

## 🌐 HTML Version for Your Portfolio 

If you want to add this project to a **personal portfolio website**, here's a simple HTML snippet you can use:

```html
<section id="project">
  <h2>🏠 House Price Prediction Using Decision Tree</h2>
  <p>This project applies a Decision Tree Regressor to predict house prices in Pakistan based on real listings from Zameen.com. It uses preprocessed features such as area (in Marla), bedrooms, bathrooms, and neighborhood to estimate realistic property prices.</p>

  <ul>
    <li><strong>Model:</strong> DecisionTreeRegressor (scikit-learn)</li>
    <li><strong>Target:</strong> House price (PKR)</li>
    <li><strong>Evaluation:</strong> MAE, RMSE, MAPE, Accuracy</li>
    <li><strong>Tools:</strong> Python, Pandas, NumPy, scikit-learn, Matplotlib</li>
    <li><strong>Features:</strong> Area, Bedrooms, Bathrooms, Neighborhood, Furnished, Parking</li>
  </ul>

  <p><strong>Example Prediction:</strong> 23 Marla, 6 Bed, 6 Bath in F-7 → <em>PKR 76,000,000</em></p>

  <p><a href="https://github.com/bilalfarooq056/house-price-prediction">🔗 View on GitHub</a></p>
</section>
```

You can embed this into your portfolio or use it in a markdown-supported portfolio generator (e.g., Jekyll or GitHub Pages).

---





