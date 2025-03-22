# Absenteeism-Analysis

# 📊 Data Workflow Overview

This project illustrates a typical workflow in a Business Intelligence (BI) and Data Science (DS) collaboration. In this project, I assume the role of the BI Analyst.

---

## 🧩 Roles and Responsibilities

### 🔷 BI Analyst Role (Pre-Model Phase)

- Preprocessing was performed on the historical dataset `absenteeism_data.csv` (700 rows) using Python.
- Tasks include data categorizing, dropping unnecessary column, etc..
- Documented in: `preprocessing/Absenteeism_Preprocessing.ipynb`

### 🔷 Data Science Team Role (Model Development)

After preprocessing, the dataset is assumed to be handed over to the Data Science team, who developed a machine learning model for absenteeism prediction. Their deliverables (included in this repository) are:

- `absenteeism_new_data.csv` — New, unseen data for prediction (40 rows).
- `absenteeism_module.py` — Python module containing the trained model logic.
- `model` — Serialized trained model file.
- `scaler` — Serialized preprocessing scaler used during training.
- `Absenteeism_Integration.ipynb` — Integration notebook demonstrating how to apply the model to new data.

### 🔷 BI Analyst Role (Post-Model Phase)

- The BI Analyst uses the model output (predictions) to derive business insights.
- Further analysis and visualization are done using SQL and Tableau.
- Dashboard View
  ![Absenteeism_Dashboard](https://github.com/user-attachments/assets/759696eb-b72f-43a4-97fb-8be9f2498fba)

---

## 💻 Local Environment Setup (VS Code)

1. Install **Python 3.8**
2. Install **Visual C++ Build Tools**:

   - [Download here](https://visualstudio.microsoft.com/visual-cpp-build-tools/)
   - Select:
     - "Desktop Development with C++"
     - ✔ "C++ build tools"
     - ✔ "Windows 10 SDK" or "Windows 11 SDK" (depending on your system)

3. Open terminal (bash or PowerShell) and create a virtual environment:
   ```bash
   py -3.8 -m venv venv38
   ```
4. In VS Code:
   Press Ctrl+Shift+P → "Python: Select Interpreter" → Select venv38
5. Activate the virtual environment:
   ```bash
   source venv38/Scripts/activate
   ```
6. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
   If requirements.txt is not available, use the command below:
   ```bash
   pip install scikit-learn==0.22 ipykernel pandas==1.4.4 numpy==1.19.5 pymysql
   ```
   Alternatively:
   ```bash
   venv38/Scripts/python.exe -m pip install scikit-learn==0.22 ipykernel pandas==1.4.4 numpy==1.19.5 pymysql
   ```
7. Set up the database:
   Run create_database.sql on your MySQL server to create the required database and table.

### 📦 Saving Dependencies

To generate a requirements.txt file:

```bash
pip freeze > requirements.txt
```

---

## 📁 Project Structure

```pgsql
├── data/
│   └── processed/
│   └── raw/
├── preprocessing/
│   └── model/
│   └── scaler/
├── sql/
└── tableau/
```

---

## 📌 Notes

Ensure MySQL server is running before executing the integration.
