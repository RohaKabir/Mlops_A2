## MLOps Workflow with Apache Airflow
# Overview
This repository contains the implementation of an MLOps (Machine Learning Operations) workflow using Apache Airflow. The workflow automates the processes of data extraction, transformation, and version-controlled storage from news websites such as BBC.com and Dawn.com.

## Workflow Components
1. Data Extraction
The workflow begins by scraping the homepages of BBC.com and Dawn.com to extract the latest articles. Python libraries like requests and BeautifulSoup are used for this purpose.

2. Data Transformation
Extracted data undergoes transformation to ensure cleanliness and suitable formatting. This includes removing unnecessary characters, standardizing text format, and structuring the data for analysis.

3. Data Storage and Version Control
Transformed data is saved into a CSV file stored on Google Drive. Data Version Control (DVC) is employed to track changes in the dataset. DVC is configured with remote storage, and data files are added to DVC tracking and pushed to a Git repository for version control.

4. Apache Airflow DAG
An Apache Airflow Directed Acyclic Graph (DAG) automates the entire process, scheduling and executing tasks daily. The DAG manages task dependencies and ensures error handling throughout the workflow.

## Challenges Faced
Airflow Installation on Windows: Due to compatibility issues, Airflow had to be installed with WSL (Windows Subsystem for Linux) Ubuntu.

BashOperator Permissions: Errors were encountered with BashOperator permissions while accessing Git credentials, which were resolved through trial and error.

## Usage Instructions
Prepare Airflow DAG: Write the Python script for the Airflow DAG and place it in the airflow/dags folder.

Initialize Git and DVC: Initiate Git repository and DVC within the project directory. Use dvc init to set up DVC and add a remote storage.

Start Airflow Services: Launch the Airflow webserver and scheduler to begin DAG orchestration.

Activate the DAG: Navigate to the Airflow web interface, locate the DAG, and enable or trigger it manually.

Monitor Task Execution: Observe task execution progress and status through the Airflow web interface.

Data Extraction: Verify successful extraction of article titles and descriptions.

Execute DVC Commands: Run dvc add and dvc push commands to version-control and store data files. Verify synchronization between DVC and Git repositories.

Conclusion
This repository demonstrates the efficient deployment and monitoring of an MLOps workflow using Apache Airflow. By automating data handling processes and implementing version control, the workflow ensures reliability, reproducibility, and scalability in machine learning projects.





