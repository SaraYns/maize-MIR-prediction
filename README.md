# Advanced AI Regression Models for Non-Destructive Prediction of Maize Chemical Composition Using Mid-Infrared Spectral Data

This project investigates the use of **machine learning regression models** and **advanced feature selection techniques** to predict maize enzyme activities using **Mid-Infrared (MIR) spectral data**. The proposed framework provides a **non-destructive, cost-effective, and accurate alternative** to traditional laboratory-based biochemical analysis.

---

## **Project Overview**
Traditional chemical analysis of maize composition is often destructive, labor-intensive, and time-consuming. This project explores the integration of **MIR spectral data** with **artificial intelligence (AI) regression models** to accurately predict multiple chemical and enzymatic properties of maize samples.

The workflow includes:
- MIR Spectral **preprocessing** (noise removal, normalization, derivative transformation)
- **Feature selection** (VIP, SPA, Stepwise, UVE, MC-UVE, iPLS, CARS, Sparse CARS, Adaptive Sparse CARS)
- **Regression modeling** (PLSR, LASSO, Ridge, Elastic Net)
- **Model evaluation** using R², RMSE

The study further evaluates the effectiveness of both traditional and sparsity-based feature selection methods for handling high-dimensional spectral datasets.

---

## **Dataset Description**
The dataset consists of two main components:
* **MIR Spectral Data (dataF)**  
  - Absorbance values at 1,868 wavelengths for each maize sample
  - Rows = maize samples, columns = spectral features

* **Enzyme Activity Data (dataC)**  
  - For each sample, five enzyme activities were measured:  
    - **β-glucosidase activity** (nmol g−1 h−1)
    - **N-Acetyl-β-glucosaminidase activity** (nmol g−1 h−1)
    - **Phosphatase activity** (nmol g−1 h−1)
    - **Net peroxidase** (nmol g−1 h−1)
    - **Phenol oxidase** (nmol g−1 h−1)

After preprocessing and cleaning, **258 valid maize samples** were analyzed.

---

## **Preprocessing**
- **Missing values**: Removed incomplete samples
- **Noise reduction**: Savitzky-Golay smoothing filter
- **Normalization**: Standard Normal Variate (SNV)
- **First derivative transformation**: To enhance subtle peak details

---

## **Feature Selection Methods**
To address the high dimensionality and multicollinearity of MIR spectral data, multiple feature selection methods were evaluated:

### **Traditional Methods**
- **VIP (Variable Importance in Projection)** – Based on PLSR, identifies most informative wavelengths
- **SPA (Successive Projection Algorithm)** – Reduces collinearity, selects non-redundant variables
- **Stepwise Regression** – Adds/removes predictors based on statistical significance
- **UVE (Uninformative Variable Elimination)** – Eliminates low-relevance spectral variables
- **MC-UVE (Monte Carlo UVE)** – Enhances UVE stability using Monte Carlo resampling
- **iPLS (Interval Partial Least Squares)** – Selects informative spectral intervals rather than individual wavelengths

### **CARS-Based Methods**
- **CARS (Competitive Adaptive Reweighted Sampling)** – Iteratively selects impactful features using adaptive weighting
- **Sparse CARS (Sparse Competitive Adaptive Reweighted Sampling)** – Extends CARS using sparsity regularization to reduce redundant variables
-  **Adaptive Sparse CARS (Adaptive Sparse Competitive Adaptive Reweighted Sampling)** –Incorporates adaptive sparsity weighting for improved wavelength optimization and predictive robustness
  
---

## **Regression Models**
The following regression algorithms were implemented and compared:
- **Partial Least Squares Regression (PLSR)**
- **Ridge Regression**
- **LASSO Regression**
- **Elastic Net Regression**
  
All models were evaluated using target-specific feature subsets generated within K-Fold cross-validation.

---

## **Evaluation Metrics**
- **R-squared (R²)**
- **Root Mean Square Error (RMSE)**
- **K-Fold Cross-Validation**
- **Computational runtime analysis**

---

## **Key Findings**
- Sparsity-based feature selection methods consistently outperformed traditional approaches.
- **Adaptive Sparse CARS** achieved the strongest overall predictive performance across most targets.
- **Ridge Regression** demonstrated the highest stability and robustness for MIR spectral prediction.
- Target-specific wavelength selection significantly improved prediction accuracy.

---
## Project Installation and Setup

### Clone the repository
```
$ git clone https://github.com/SaraYns/maize-MIR-prediction.git
```
### Navigate to the project directory
```
$ cd maize-MIR-prediction
```
### Create a virtual environment
```
$ python -m venv .venv
```
### Activate the virtual environment

- **Windows (PowerShell)**
```
$ .venv\Scripts\activate
```
- **Mac/Linux**
```
$ source .venv/bin/activate
```
### Install required Python packages
```
$ pip install -r requirements.txt
```
### Launch Jupyter Notebook
```
$ jupyter notebook
```








