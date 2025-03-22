========================================
Data Workflow Overview

The typical workflow in a Business Intelligence (BI) and Data Science (DS) collaboration is reflected in this project:
BI Analyst Role:
	The historical dataset absenteeism_data.csv (700 rows) was preprocessed by the BI Analyst using python. This includes data cleaning, formatting, and preparing features required for modeling. The work is documented in the preprocessing/Absenteeism_Preprocessing.ipynb.

Data Science Team Role (Assumed in this project):
	After preprocessing, the data is assumed to be handed off to a Data Science team, who used it to develop a machine learning model for absenteeism prediction. Their deliverables (already provided in this project) include:
		absenteeism_new_data.csv — new, unseen data for prediction (40 rows).
		absenteeism_module.py — the prediction module containing the trained model logic.
		model — serialized trained model file.
		scaler — serialized preprocessing scaler used during model training.
		Absenteeism_Integration.ipynb — integration notebook demonstrating how to apply the model on new data.

BI Analyst (Post-Model) Role:
    The BI Analyst then uses the model output (predictions) for business insights and visualization using SQL and Tableau.

========================================
Installation on VS Code to run the python files

install python 3.8
install https://visualstudio.microsoft.com/visual-cpp-build-tools/
	Choose Desktip Development with C++
	x “C++ build tools”
	x “Windows 10 SDK” (or 11, depending on your system)
open bash terminal
py -3.8 -m venv venv38
Ctrl+Shift+P -> "Python: Select Interpreter" -> select the venv38
source venv38/Scripts/activate
pip install -r requirements.txt # if requirements.txt is exist, then ignore pip install below
pip install scikit-learn==0.22 ipykernel pandas==1.4.4 numpy==1.19.5 pymysql
# or
venv38/Scripts/python.exe -m pip install scikit-learn==0.22 ipykernel pandas==1.4.4 numpy==1.19.5 pymysql
run the create_database.sql SQL script to create the database and the table on MySQL

========================================
saving the dependencies into requirements.txt

pip freeze > requirements.txt