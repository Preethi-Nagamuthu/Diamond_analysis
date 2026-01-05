# 💎 Diamond Dynamics: Price Prediction and Market Segmentation

# 📌 Data Preprocessing:
Handle missing values (if any)


Convert zero or invalid values in x, y, z to null or imputed values


Drop unnecessary columns if irrelevant for prediction/clustering


# 📌 Outliers Handling:
IQR Method / Z-Score Method for numerical features (carat, price, x, y, z)


Visual checks via boxplots

# 📌 Skewness Handling:
Check skewness using .skew() function


Apply log transformation / square root / box-cox on highly skewed variables like price, carat, x, y, z

# 📌 Exploratory Data Analysis (EDA):
Analyses & Visualizations ideas:
Distribution plots for price, carat, x, y, z


Count plots for categorical features (cut, color, clarity)


Price variation with carat, cut, color, clarity using boxplots


Correlation heatmap for numerical features


Scatterplot matrix for carat, x, y, z, and price


Pairwise relationships using sns.pairplot()


Carat vs. price regression lineplot


Average price per cut, color, clarity categories using bar plots


# 📌 Feature Engineering:
Convert the price (in USD) to INR using a fixed or dynamic conversion rate
New Columns that can be Derived:
Volume = x * y * z


Price per Carat = price / carat


Dimension Ratio = (x + y) / (2 * z)


Carat Category: Light (<0.5), Medium (0.5-1.5), Heavy (>1.5)

# 📌 Feature Selection
To improve model performance and reduce redundancy, you can select the most relevant features using any one of the following techniques:
Available Techniques:
Correlation Matrix Analysis — To detect multicollinearity among numerical features.


Feature Importance — Using models like Random Forest or XGBoost to rank features by importance.


Recursive Feature Elimination (RFE) — Iteratively removes least important features.


Variance Inflation Factor (VIF) — To detect multicollinearity among numerical features.

📌 Encoding
Perform encoding of the categorical columns based on the requirements of your models. You can use techniques like Label Encoding, Ordinal Encoding, or One-Hot Encoding depending on whether the categorical variables are ordinal or nominal, and based on what the specific algorithm requires.

📌 Model Building:
📌 1️⃣ Regression (Price Prediction)
Split data into Train-Test sets (80-20 or 70-30).


Build 4–5 ML regression models (e.g., Linear Regression, Random Forest, XGBoost, Decision Tree, KNN).


Build an ANN regression model.


Evaluate all models using MAE, MSE, RMSE, R².


Compare model performances and save the best performing model as .pkl file

📌 2️⃣ Clustering (Market Segmentation)
Try K-Means clustering and optionally try different clustering techniques (e.g., K-Means, DBSCAN, Hierarchical Clustering).


Use the Elbow Method or Silhouette Score to find the optimal number of clusters.


Encode categorical variables (cut, color, clarity) before fitting the model.


Optionally, perform Dimensionality Reduction with PCA:


Reduce features to 2 or 3 principal components.


Use PCA for visualizing clusters in a 2D or 3D scatter plot.


Pickle the best-performing clustering model(pkl) for use in Streamlit.



# 📌 Cluster Naming Approach:
After clustering, analyze average price, carat, and cut distribution per cluster.
Name clusters based on characteristics like:


"Premium Heavy Diamonds"


"Affordable Small Diamonds"


"Mid-range Balanced Diamonds"

# 📱 Streamlit App Features
🎯 1️⃣ Price Prediction Module
Objective:
 Predict the price of a diamond based on its attributes using the trained regression model.
Functionality example:
Numeric inputs for:  carat, x, y, z


Select box inputs for:  cut, color, clarity


Button: Predict Price


Display: Predicted diamond price in INR


🎯 2️⃣ Market Segment Prediction (Clustering Module)
Objective:
 Predict the cluster (market category) the diamond belongs to, using the trained clustering model.
Functionality:
Use the same input form as price prediction


Button: Predict Cluster

