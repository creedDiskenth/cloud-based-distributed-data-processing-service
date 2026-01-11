# Cloud-Based Distributed Data Processing Service

Authors: 
- أحمد فالح أبو جحجوح (120220173)  
- عبد الرحمن علاء الجديلي (120220456)

Faculty of Information Technology
The Islamic University of Gaza

Course: Cloud and Distributed Systems (SICT 4313)  
Instructor: Dr. Rebhi S. Baraka  

---

 Project Overview

This project presents a cloud-based distributed data processing service built using PySpark. The service allows users to upload datasets and perform:

- Descriptive statistical analysis
- Machine learning tasks including Decision Tree Classification, KMeans Clustering, FP-Growth frequent itemset mining, and Linear Regression.

The system is designed to handle large datasets efficiently using distributed processing on multiple cores and ensures scalable execution.

---

## Features

### User Functionality

- Upload CSV datasets
- View basic dataset information (rows, columns)
- Analyze missing values and descriptive statistics
- Run machine learning operations
- Select target columns for supervised algorithms
- Save results in cloud storage (Kaggle working directory)
- Display execution feedback and performance metrics

### Descriptive Statistics Operations

- Dataset Information
- Missing Values Analysis
- Descriptive Statistics (mean, min, max, stddev)
- Average of Numeric Columns

### Machine Learning Operations

- Decision Tree Classification
- KMeans Clustering
- FP-Growth Frequent Itemsets
- Linear Regression

---

## Architecture

The service follows a three-layer architecture:

1. User Interface Layer
   - Implemented using Jupyter Notebook and ipywidgets
   - Interactive selection of tasks and parameters
   - Dynamic target column selection for ML tasks

2. Processing Layer
   - Spark Core: distributed computation
   - Spark SQL: data loading and transformations
   - Spark MLlib: machine learning pipelines

3. Cloud Storage Layer
   - Cloud storage (local workspace on Kaggle)
   - Stores uploaded datasets and result files (CSV, TXT)

---

### Machine Learning Pipelines

Each ML algorithm follows a standard Spark ML pipeline:

1. Data preprocessing (handling missing values, categorical indexing)
2. Feature vector assembly with VectorAssembler
3. Model training
4. Prediction
5. Evaluation (Accuracy, RMSE)
6. Result storage in cloud directory

Supported ML Algorithms:

- Decision Tree Classifier  
- KMeans Clustering  
- FP-Growth Frequent Itemset Mining  
- Linear Regression  

---

## Implementation

- Language: Python 3.x  
- Libraries:
  - PySpark [1]  
  - Pandas [2]  
  - ipywidgets [3]  
  - Matplotlib [4]  

- Uploaded datasets are read using Spark CSV reader with schema inference.  
- Each ML function dynamically handles feature selection and preprocessing.  
- Results are saved in `/kaggle/working/` for later download.  

---

## Performance Testing (1248 Node Simulation)

- Tested 1, 2, 4, 8 cores on Kaggle environment  
- Execution results for Decision Tree Classification:

| Cores | Execution Time (sec) | Speedup | Efficiency | Accuracy |
|-------|--------------------|---------|------------|----------|
| 1     | 156.76             | 1.00    | 1.00       | 1.0      |
| 2     | 90.14              | 1.74    | 0.87       | 1.0      |
| 4     | 85.89              | 1.83    | 0.46       | 1.0      |
| 8     | 81.84              | 1.92    | 0.24       | 1.0      |

- Shows scalability of Spark distributed computation.  
- Speedup and efficiency calculated as:

