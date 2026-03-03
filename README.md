# 📊 Data Science Practical Journal

> **Subject:** Data Science  
> **Total Practicals:** 8  
> **Tools Used:** Microsoft Excel, Python 3.x, Pandas, NumPy, Matplotlib, Scikit-learn, Scipy

---

# PRACTICAL NO 1

## AIM :-
Introduction to Excel
- a. Perform conditional formatting on a dataset using various criteria.
- b. Create a pivot table to analyze and summarize data.
- c. Use VLOOKUP function to retrieve information from a different worksheet or table.
- d. Perform what-if analysis using Goal Seek to determine input values for desired output.

---

## STEPS :-

**a. Conditional Formatting :-**

**1) Equal To (Numbers):**
1. Open Excel and create a new excel sheet. Select the range `C2:H11` for all stat values.
2. Click on the **Conditional Formatting** icon from Home menu → **Highlight Cell Rules** → **Equal To**.
3. Enter `50` into the input field and select the appearance.

**2) Equal To (Text):**
1. Select range `A2:A11`.
2. Click on **Conditional Formatting** → **Highlight Cell Rules** → **Equal To**.
3. Enter `"Jigglypuff"` and select appearance.

**3) Greater Than:**
1. Select range `C2:H11` (Numbers) or `A2:A11` (Text).
2. Click on **Conditional Formatting** → **Highlight Cell Rules** → **Greater Than**.
3. Enter `50` (for numbers) or `"Jigglypuff"` (for text).

**4) Less Than:**
1. Select range `C2:H11` (Numbers) or `A2:A11` (Text).
2. Click on **Conditional Formatting** → **Highlight Cell Rules** → **Less Than**.
3. Enter `50` (for numbers) or `"Jigglypuff"` (for text).

**b. Pivot Table :-**
1. Select data range `A1:H11`.
2. Click **PivotTable** from the **Insert** menu.
3. Choose **Existing Worksheet** as location.
4. Drag desired fields to Rows, Columns, and Values areas.

**c. VLOOKUP :-**
1. Use the VLOOKUP function to find a name based on ID.
2. If it returns `#N/A`, feed a value (e.g., `5`) in cell `L3`.

**d. Goal Seek :-**
1. Set up cells with financial data. Use the `PMT` function in cell `C6` for EMI calculation.
2. Go to **DATA Menu** → **What-If Analysis** → **Goal Seek**.
3. Set cell `C6`, To value `-50000`, By changing cell `C2` (Interest_Rate).

## OUTPUT :-
- Cells highlighted based on criteria (numbers and text).
- Pivot table created and summarized.
- VLOOKUP returns matching name from ID.
- Goal Seek solves for the required interest rate.

---

# PRACTICAL NO 2

## AIM :-
Data Frames and Basic Data Pre-processing
- a. Read data from CSV and JSON files into a data frame.
- b. Perform basic data pre-processing tasks such as handling missing values and outliers.
- c. Manipulate and transform data using functions like filtering, sorting, and grouping.

---

## CODE :-

```python
import json
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np

# Creating a data frame from CSV
df = pd.read_csv("D:\Data Science\CardioGoodFitness.csv")
print(df.head())

# Checking for missing values
print(df.isnull().sum())

# Dropping rows with missing values
df1 = df.dropna(axis=0)
print(df1.head())
print(df1.isnull().sum())

# Filling missing values with a default value
df['MaritalStatus'] = df['MaritalStatus'].fillna('Single')
print(df['MaritalStatus'])
print(df.isnull().sum())

# Visualizing outliers with scatter plot
plt.scatter(x=df['Age'], y=df['Fitness'])
plt.show()

# Sorting data by Age in descending order
sorted_df = df.sort_values(by='Age', ascending=False)
print(sorted_df)

# Grouping data by MaritalStatus
mcount = df.groupby('MaritalStatus')['MaritalStatus'].count()
print(mcount)

# Reading data from JSON file
f = open("D:\Data Science\iris.json")
d = json.load(f)
df = pd.DataFrame(d)
print(df)
print(df.isnull().sum())

# Drop and fill missing values in JSON dataframe
df1 = df.dropna(axis=0)
print(df1.head())
df['species'] = df['species'].fillna('setosa')
print(df['species'])
print(df.isnull().sum())
```

## OUTPUT :-
- Dataframe head displayed from CSV and JSON files.
- Null counts shown before and after handling.
- Scatter plot of Age vs Fitness displayed.
- Sorted data and grouped counts printed.

---

# PRACTICAL NO 3

## AIM :-
Hypothesis Testing
- a. Formulate null and alternative hypotheses for a given problem.
- b. Conduct a hypothesis test using appropriate statistical tests (e.g., t-test, chi-square test).
- c. Interpret the results and draw conclusions based on the test outcomes.

---

## CODE :-

```python
# ── T-TEST ──────────────────────────────────────────────
from scipy.stats import ttest_1samp
import numpy as np

ages = [45, 89, 23, 46, 12, 69, 45, 24, 34, 67]
print("Ages:", ages)

mean = np.mean(ages)
print("Mean:", mean)

t_test, p_val = ttest_1samp(ages, 30)
print("P-value is:", p_val)

if p_val < 0.05:
    print("We can reject the null hypothesis")
else:
    print("We can accept the null hypothesis")


# ── CHI-SQUARE TEST ──────────────────────────────────────
from scipy.stats import chi2_contingency

data = [[207, 282, 241],
        [234, 242, 232]]

stat, p, dof, expected = chi2_contingency(data)
alpha = 0.05

print("p value is " + str(p))
if p <= alpha:
    print('Dependent (reject H0)')
else:
    print('Independent (H0 holds true)')
```

## OUTPUT :-
- T-test P-value printed with hypothesis decision.
- Chi-square P-value printed with dependence/independence decision.

---

# PRACTICAL NO 4

## AIM :-
ANOVA (Analysis of Variance)
- a. Perform one-way ANOVA to compare means across multiple groups.
- b. Conduct post-hoc tests to identify significant differences between group means.

---

## CODE :-

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import scipy.stats as stats
from scikit_posthocs import posthoc_tukey

np.random.seed(12)

races = ["asian", "black", "hispanic", "other", "white"]
voter_race = np.random.choice(
    a=races,
    p=[0.05, 0.15, 0.25, 0.05, 0.5],
    size=1000
)
voter_age = stats.poisson.rvs(loc=18, mu=30, size=1000)

voter_frame = pd.DataFrame({"race": voter_race, "age": voter_age})
groups = voter_frame.groupby("race").groups

asian    = voter_age[groups["asian"]]
black    = voter_age[groups["black"]]
hispanic = voter_age[groups["hispanic"]]
other    = voter_age[groups["other"]]
white    = voter_age[groups["white"]]

# One-Way ANOVA
print(stats.f_oneway(asian, black, hispanic, other, white))

# Post-hoc Tukey Test
print(posthoc_tukey(voter_frame, val_col="age", group_col="race"))
```

## OUTPUT :-
- F-statistic and P-value from One-Way ANOVA.
- Tukey post-hoc test table showing pairwise comparisons between groups.

---

# PRACTICAL NO 5

## AIM :-
Regression and Its Types
- a. Implement simple linear regression using a dataset.
- b. Explore and interpret the regression model coefficients and goodness-of-fit measures.
- c. Extend the analysis to multiple linear regression and assess the impact of additional predictors.

---

## CODE :-

```python
# ── SIMPLE LINEAR REGRESSION ─────────────────────────────
import pandas
import matplotlib.pyplot as plt
from scipy import stats

df = pandas.read_csv("D:\Data Science\DATA.csv")
x = df['Weight']
y = df['CO2']

slope, intercept, r, p, std_err = stats.linregress(x, y)

def myfunc(x):
    return slope * x + intercept

mymodel = list(map(myfunc, x))

plt.scatter(x, y)
plt.plot(x, mymodel)
plt.show()

predictedCO2 = myfunc(2300)
print("Predicted CO2:", predictedCO2)


# ── MULTIPLE LINEAR REGRESSION ───────────────────────────
import pandas
from sklearn import linear_model

df = pandas.read_csv("D:\Data Science\DATA.csv")
X = df[['Weight', 'Volume']]
y = df['CO2']

regr = linear_model.LinearRegression()
regr.fit(X, y)

prediction_data = pandas.DataFrame([[2300, 1300]], columns=['Weight', 'Volume'])
predictedCO2 = regr.predict(prediction_data)
print("Predicted CO2 (Multiple Regression):", predictedCO2)
```

## OUTPUT :-
- Scatter plot with regression line displayed.
- Predicted CO2 value for given Weight (Simple Regression).
- Predicted CO2 value for given Weight + Volume (Multiple Regression).

---

# PRACTICAL NO 6

## AIM :-
Logistic Regression and Decision Tree
- a. Build a logistic regression model to predict a binary outcome.
- b. Evaluate the model's performance using classification metrics (accuracy, precision, recall).
- c. Construct a decision tree model and interpret the decision rules for classification.

---

## CODE :-

```python
import numpy
from sklearn import linear_model
import pandas as pd

# ── Binary Logistic Regression ───────────────────────────
X = numpy.array([3.78, 2.44, 2.09, 0.14, 1.72, 1.65,
                 4.92, 4.37, 4.96, 4.52, 3.69, 5.88]).reshape(-1, 1)
y = numpy.array([0, 0, 0, 0, 0, 0, 1, 1, 1, 1, 1, 1])

logr = linear_model.LogisticRegression()
logr.fit(X, y)

predicted = logr.predict(numpy.array([3.46]).reshape(-1, 1))
print("Predicted class:", predicted)

# ── Iris Dataset Classification ──────────────────────────
df = pd.read_csv("D:/Data Science/Iris.csv")
X1 = numpy.array(df['SepalLengthCm']).reshape(-1, 1)
y  = df['Species']

logr = linear_model.LogisticRegression()
logr.fit(X1, y)

predicted = logr.predict(numpy.array([3.4]).reshape(-1, 1))
print("Predicted species:", predicted)
```

## OUTPUT :-
- Predicted binary class (0 or 1) for given input.
- Predicted Iris species for given Sepal Length.

---

# PRACTICAL NO 7

## AIM :-
K-Means Clustering
- a. Apply the K-Means algorithm to group similar data points into clusters.
- b. Determine the optimal number of clusters using the Elbow Method or silhouette analysis.
- c. Visualize the clustering results and analyze cluster characteristics.

---

## CODE :-

```python
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

# Raw data
x = [4, 5, 10, 4, 3, 11, 14, 6, 10, 12]
y = [21, 19, 24, 17, 16, 25, 24, 22, 21, 21]

# Scatter plot of raw data
plt.scatter(x, y)
plt.show()

# Elbow Method to find optimal K
data = list(zip(x, y))
inertias = []

for i in range(1, 11):
    kmeans = KMeans(n_clusters=i)
    kmeans.fit(data)
    inertias.append(kmeans.inertia_)

plt.plot(range(1, 11), inertias, marker='o')
plt.title('Elbow Method')
plt.xlabel('Number of clusters')
plt.ylabel('Inertia')
plt.show()

# Apply K-Means with optimal K = 2
kmeans = KMeans(n_clusters=2)
kmeans.fit(data)

plt.scatter(x, y, c=kmeans.labels_)
plt.show()
```

## OUTPUT :-
- Scatter plot of raw data points.
- Elbow Method plot showing inertia vs number of clusters.
- Clustered scatter plot with color-coded labels.

---

# PRACTICAL NO 8

## AIM :-
Principal Component Analysis (PCA)
- a. Perform PCA on a dataset to reduce dimensionality.
- b. Evaluate the explained variance and select the appropriate number of principal components.
- c. Visualize the data in the reduced-dimensional space.

---

## CODE :-

```python
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.decomposition import PCA
from sklearn.linear_model import LogisticRegression
from matplotlib.colors import ListedColormap

# Load dataset
dataset = pd.read_csv("D:/Data Science/wine.csv")
X = dataset.iloc[:, 0:13].values
y = dataset.iloc[:, 13].values

# Train-Test Split
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=0
)

# Feature Scaling
sc = StandardScaler()
X_train = sc.fit_transform(X_train)
X_test  = sc.transform(X_test)

# Apply PCA (reduce to 2 components)
pca = PCA(n_components=2)
X_train = pca.fit_transform(X_train)
X_test  = pca.transform(X_test)

explained_variance = pca.explained_variance_ratio_
print("Explained Variance:", explained_variance)

# Logistic Regression on reduced data
classifier = LogisticRegression(random_state=0)
classifier.fit(X_train, y_train)

# Visualization
X_set, y_set = X_train, y_train
X1, X2 = np.meshgrid(
    np.arange(start=X_set[:, 0].min() - 1, stop=X_set[:, 0].max() + 1, step=0.01),
    np.arange(start=X_set[:, 1].min() - 1, stop=X_set[:, 1].max() + 1, step=0.01)
)

plt.contourf(X1, X2,
    classifier.predict(np.array([X1.ravel(), X2.ravel()]).T).reshape(X1.shape),
    alpha=0.75,
    cmap=ListedColormap(('yellow', 'white', 'aquamarine'))
)

plt.xlim(X1.min(), X1.max())
plt.ylim(X2.min(), X2.max())

for i, j in enumerate(np.unique(y_set)):
    plt.scatter(
        X_set[y_set == j, 0], X_set[y_set == j, 1],
        c=ListedColormap(('red', 'green', 'blue'))(i),
        label=j
    )

plt.title('Logistic Regression (Training set)')
plt.xlabel('PC1')
plt.ylabel('PC2')
plt.legend()
plt.show()
```

## OUTPUT :-
- Explained variance ratio for each principal component printed.
- Visualization of Logistic Regression decision boundary in PC1 vs PC2 space.

---

## 🛠️ Prerequisites

```bash
pip install pandas numpy matplotlib scikit-learn scipy scikit-posthocs
```

---

## 📁 Required Dataset Files

| File | Used In |
|------|---------|
| `CardioGoodFitness.csv` | Practical 2 |
| `iris.json` | Practical 2 |
| `DATA.csv` | Practical 5 |
| `Iris.csv` | Practical 6 |
| `wine.csv` | Practical 8 |

---

*📘 Data Science Lab Journal — For Educational Use Only*
