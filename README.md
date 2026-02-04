# Probability Density Function (PDF) Estimation using MLE

Project Workflow<img width="2712" height="1435" alt="PHOTO" src="https://github.com/user-attachments/assets/a6d534fb-14fc-4e10-9491-119189d29791" />


> *Figure: Project Workflow visualization including Data Selection, Personalized Transformation, and MLE Modeling.*

## 📌 Project Overview
This project focuses on learning a **Probability Density Function (PDF)** from real-world air quality data using **Maximum Likelihood Estimation (MLE)**. The core of the assignment involves applying a personalized, non-linear transformation to the data based on a university roll number before estimating the distribution parameters.

## 📂 Dataset
* **Source:** [India Air Quality Data (Kaggle)](https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data) 
* **Feature Selected:** `NO2` (Nitrogen Dioxide) 
***Preprocessing:** The feature is automatically detected, and missing values are removed to ensure data quality

## ⚙️ Methodology

### 1. Roll-Number-Parameterized Transformation
To personalize the dataset, each data point $x$ (NO2 concentration) is transformed into a new variable $z$ using a non-linear function parameterized by the student's roll number.

**Roll Number:** `102316054`

The transformation function is defined as:
$$z = T_r(x) = x + a_r \sin(b_r x)$$

Where parameters $a_r$ and $b_r$ are derived as follows:
* **$a_r$ Calculation:**
    $$a_r = 0.05 \times (102316054 \mod 7) = 0.05 \times 1 = \mathbf{0.05}$$
* **$b_r$ Calculation:**
    $$b_r = 0.3 \times ((102316054 \mod 5) + 1) = 0.3 \times (4 + 1) = \mathbf{1.5}$$

**Final Transformation Equation:**
$$z = x + 0.05 \sin(1.5x)$$

### 2. PDF Estimation (Gaussian Modeling)
We model the transformed data $z$ using a Gaussian-like Probability Density Function:
$$\hat{p}(z) = c \cdot e^{-\lambda(z-\mu)^{2}}$$

### 3. Maximum Likelihood Estimation (MLE)
The parameters $\lambda$, $\mu$, and $c$ are estimated using **Maximum Likelihood Estimation (MLE)**. This technique finds the parameter values that maximize the likelihood of observing the transformed data $z$.

## 🚀 How to Run
1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    ```
2.  **Install dependencies:**
    ```bash
    pip install numpy pandas matplotlib scipy
    ```
3.  **Run the Jupyter Notebook:**
    Execute `PDF_Estimation_MLE.ipynb` to visualize the transformation and estimated PDF.

## 📊 Results
The project successfully:
1.  Transforms the raw NO2 data using the unique roll-number-based function.
2.  Estimates the optimal parameters ($\mu$, $\lambda$, $c$) for the probability distribution.
3.  Visualizes the fit between the empirical data and the estimated PDF.

## 📝 Author
* **Name:** Shivansh Sharma
* **Roll Number:** 102316054
