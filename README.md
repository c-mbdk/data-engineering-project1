# data-engineering-project1

## About this project
This project uses a file from Kaggle, transforms the data according to a pre-determined star schema data model then uploads the data to the relevant tables in BigQuery. Depending on whether the .ipynb file is converted to a .py file, minimal user input is required. The application default credentials must be set and the table id values which are used in the final section of the code must be updated. The Kaggle data is available here: https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset

## Background
This project started off as just transforming data found on Kaggle and loading that to BigQuery. Despite having a rather strict set of requirements + tasks managed in Asana, the project kept evolving. It continued evolving until it became clear that aspects of the project has become overcomplicated and unnecessary. The project was then stripped back to just the dataset, the virtual environment and the main notebook. 

The biggest learning point from this project? 'Make it work, make it right, make it fast.' It feels very tempting to try and incorporate multiple tools in a project, especially when they all seem interesting. But if they don't fit with the project aims and far too much time is spent trying to integrate the tools, it becomes a waste of time. Of all the common sayings in the software engineering world, 'make it work, make it right, make it fast' remains true and a good guideline for development.

## Future enhancements
There is definitely room to refactor the code here, specifically the actual load of the data from the dataframes to the BigQuery tables. 

Given that this was more of a project to get familiar with data modelling and using Python to interact with the BigQuery API, the enhancements may end there.

## How to Run

1. Install virtualenv:
```
$ pip install virtualenv
```

2. Open a terminal in the project root directory and run:
```
$ virtualenv env
```

3. Then run the command:
```
$ .\env\Scripts\activate
```

4. Then install the dependencies
```
$ (env) pip install -r requirements.txt
```

5. This is called out the in .ipynb file, after the imports. The GOOGLE_APPLICATION_CREDENTIALS environment variable must be set. This is what the BigQuery API will use to authenticate the requests, so the variable must be set to the location of the service account json file. If the .ipynb file is converted to a .py file, this variable can be set in the terminal before running the .py file. There are other ways to set up the Application Default Credentials, which you can find here: https://cloud.google.com/docs/authentication/provide-credentials-adc
```
$ export GOOGLE_APPLICATION_CREDENTIALS="path_to_service_account_json.file"
```

6. Update the table_id values which will be used in the load_table_from_dataframe function.