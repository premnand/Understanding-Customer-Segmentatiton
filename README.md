# Consumer Segmentation for Targeted Marketing

## Table of Contents
1. [Project Description](#project-description)
2. [Dataset](#dataset)
3. [Methodology](#methodology)
4. [Key Steps](#key-steps)
5. [Results](#results)
6. [Installation](#installation)
7. [Usage](#usage)
8. [Dependencies](#dependencies)
9. [Contributing](#contributing)
---

## Project Description
This project focuses on analyzing customer behavior using the **RFM (Recency, Frequency, Monetary)** framework to segment customers for targeted marketing strategies. The dataset used is the **Online Retail Dataset**, which contains transactional data for an online retail store. The project involves data preprocessing, exploratory data analysis (EDA), customer segmentation using **K-Means Clustering**, and classification using **K-Nearest Neighbors (KNN)**.

---

## Dataset
The dataset used in this project is the **Online Retail Dataset**, which contains transactional data from an online retail store. It includes the following columns:
- **InvoiceNo**: A 6-digit integral number uniquely assigned to each transaction. Starting letter 'c' indicates a cancellation.
- **InvoiceDate**: The day and time when each transaction was generated.
- **CustomerID**: A 5-digit integral number uniquely assigned to each customer.
- **StockCode**: Product (item) code. A 5-digit integral number uniquely assigned to each distinct product.
- **Description**: Product (item) name.
- **Quantity**: The number of units of the product purchased.
- **UnitPrice**: The price per unit of the product.
- **Country**: The name of the country where each customer resides.

The dataset can be downloaded from [here](https://archive.ics.uci.edu/ml/datasets/Online+Retail).

---

## Methodology
1. **Data Preprocessing**:
   - Handle missing values and duplicates.
   - Remove canceled transactions and negative quantities.
   - Remove outliers using the **Interquartile Range (IQR)** method.

2. **RFM Analysis**:
   - Calculate **Recency**, **Frequency**, and **Monetary** values for each customer.
   - Apply log transformation (`np.log1p`) to handle skewness in the data.
   - Standardize the RFM features using **StandardScaler**.

3. **Customer Segmentation**:
   - Use the **Elbow Method** to determine the optimal number of clusters.
   - Perform **K-Means Clustering** to segment customers into distinct groups.

4. **Classification**:
   - Use **K-Nearest Neighbors (KNN)** to classify customers into segments.
   - Optimize hyperparameters using **GridSearchCV**.
   - Evaluate the model using accuracy, precision, recall, and F1-score.

---

## Key Steps
1. **Data Cleaning**:
   - Remove rows with missing `CustomerID`.
   - Drop duplicate rows.
   - Remove canceled transactions and negative quantities.

2. **Feature Engineering**:
   - Create a `TotalAmount` column (`Quantity * UnitPrice`).
   - Calculate RFM metrics:
     - **Recency**: Days since the last purchase.
     - **Frequency**: Number of transactions.
     - **Monetary**: Total amount spent.

3. **Exploratory Data Analysis (EDA)**:
   - Visualize distributions of `Quantity` and `UnitPrice`.
   - Analyze skewness in RFM metrics and apply log transformation.

4. **Clustering**:
   - Use the **Elbow Method** to determine the optimal number of clusters.
   - Perform **K-Means Clustering** and visualize the results.

5. **Classification**:
   - Split the data into training and testing sets.
   - Train a **KNN** model and optimize hyperparameters using **GridSearchCV**.
   - Evaluate the model using a classification report and confusion matrix.

---

## Results
1. **Customer Segmentation**:
   - Customers were segmented into **3 clusters** based on their RFM scores.
   - Visualizations of the clusters were created to analyze the distribution of customers.

2. **KNN Classification**:
   - The KNN model achieved an accuracy of **92.05%** on the test set.
   - The classification report provided insights into precision, recall, and F1-score for each segment.

---

## Installation
To run this project locally, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/premnand/Understanding-Customer-Segmentatiton.git
   cd Understanding-Customer-Segmentation

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the Jupyter Notebook:
   ```bash
   jupyter notebook code1.ipynb
   ```

---

## Usage
1. Open the Jupyter Notebook (`code1.ipynb`).
2. Execute each cell sequentially to perform data preprocessing, EDA, clustering, and classification.
3. Modify the code as needed to experiment with different parameters or datasets.

---

## Dependencies
The project requires the following Python libraries:

- pandas
- numpy
- seaborn
- matplotlib
- scikit-learn
- scipy


## Contributing
Contributions are welcome! If you'd like to contribute to this project, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Commit your changes and push to the branch.
4. Submit a pull request.

---

## Acknowledgments
- **Dataset**: UCI Machine Learning Repository
- **Inspiration**: RFM analysis and customer segmentation techniques

For any questions or feedback, feel free to reach out to `premnand5657@gmail.com`.

---

