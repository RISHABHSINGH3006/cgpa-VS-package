## CGPA vs. Package Prediction using Linear Regression  

This project uses Python, Pandas, Seaborn, Matplotlib, and Scikit-Learn to build a simple linear regression model that predicts salary packages based on CGPA.  

---

## 📂 Dataset  

The dataset **placement.csv** contains two columns:  
- **cgpa**: The student's CGPA  
- **package**: The offered package (in LPA)  

### Sample Data:  
| cgpa  | package |
|--------|---------|
| 6.89  | 3.26    |
| 5.12  | 1.98    |
| 7.82  | 3.25    |

---

## 📊 Exploratory Data Analysis  

- The dataset is checked for missing values (no null values found).  
- A scatter plot shows a **linear relationship** between CGPA and salary packages.  

```python
plt.figure(figsize=(3,3))
sns.scatterplot(x="cgpa",y="package",data=dataset)
plt.show()
```

---

## 🏗️ Model Training  

1. **Splitting the dataset**  
   - 80% training data, 20% testing data  

   ```python
   x = dataset[["cgpa"]]
   y = dataset["package"]
   x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.2, random_state=32)
   ```

2. **Training a Linear Regression Model**  

   ```python
   from sklearn.linear_model import LinearRegression
   lr = LinearRegression()
   lr.fit(x_train, y_train)
   ```

3. **Making Predictions**  

   ```python
   lr.predict([[9.9]])
   ```
   **Output:**  
   ```
   array([4.62793275])
   ```

4. **Model Performance (R² Score)**  

   ```python
   r2_score(y_test, lr.predict(x_test)) * 100
   ```
   **Output:**  
   ```
   80.87%
   ```

---

## 🚀 Usage  

1. Install dependencies:  
   ```
   pip install pandas seaborn matplotlib scikit-learn
   ```
2. Run the script to train the model and visualize the relationship.  
3. Use `lr.predict([[cgpa_value]])` to predict a salary package.  

---

## 📌 Conclusion  

- The model shows a strong correlation (**R² = 80.87%**) between CGPA and the package.  
- It can be used for basic salary predictions based on CGPA.  
- Improvements can be made using more features like skills, internships, and projects.  
