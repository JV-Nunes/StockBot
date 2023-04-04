# StockBot

This project aims to capture real-time stock market data from the Alpha Advantage API, store it in AWS S3, and use it to build a machine learning model that can predict stock prices.

## Architecture Overview
The project architecture consists of several components:

Data Ingestion Layer: This layer is responsible for retrieving data from the Alpha Advantage API in real-time and streaming it to AWS Kinesis.
Data Storage Layer: This layer is responsible for storing data in AWS S3 for later processing and analysis.
Data Processing Layer: This layer is responsible for processing and analyzing the data stored in AWS S3 using various AWS services, including AWS Glue, Amazon EMR, and Amazon Athena.
Machine Learning Layer: This layer is responsible for building and training machine learning models using the data stored in AWS S3, and using the trained model to predict stock prices.
The following diagram provides an overview of the project architecture:

## Project Architecture

## Installation
To run the project, you will need to have the following installed:

Python 3.6 or later
AWS CLI
AWS SDK for Python (Boto3)
Pandas
Numpy
Matplotlib
Jupyter Notebook
Git
To install the required Python packages, you can use pip:


pip install awscli boto3 pandas numpy matplotlib jupyter
To install Git, you can follow the instructions on the Git website.


# Configuration
Before running the project, you will need to configure your AWS credentials. You can do this by running the following command and following the prompts:


aws configure


You will also need to set up a Kinesis data stream, an S3 bucket, and an IAM role with the necessary permissions for Glue, EMR, and Athena. Refer to the documentation for each service for more information on how to set these up.

# Running the Project
To run the project, follow these steps:

Clone the repository:


git clone https://github.com/<your-github-username>/<your-repo-name>.git
Change into the project directory:


cd <your-repo-name>
Create a virtual environment and activate it:


python3 -m venv env
source env/bin/activate
Install the required Python packages:

pip install -r requirements.txt
Run the data ingestion script:


python src/ingestion/scripts/alpha_advantage_api.py
This will start retrieving real-time stock market data from the Alpha Advantage API and streaming it to your Kinesis data stream.

Run the data processing script:


python src/processing/glue/etl_job.py
This will run the Glue ETL job to transform and analyze the data stored in your S3 bucket.

Run the machine learning script:


python src/machine_learning/scripts/train.py
This will build and train a machine learning model using the data stored in your S3 bucket.

(Optional) Run the Jupyter Notebook to explore the data and visualize the results:

jupyter notebook
This will open the Jupyter Notebook interface in your web browser. Navigate to the src/machine_learning/notebooks directory and open the data_exploration.ipynb or model_training.ipynb notebook to explore the data and visualize the results.

Contributing