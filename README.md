# Operationalizing Machine Learning

## Overview
This project is part of the Udacity Azure ML Nanodegree. There are two facets to this project. First, we will build a codeless configuration of a closed-based machine learning production model, deploy and consume it using AUTOML. Second, we will build an Azure ML pipeline using the Python SDK to achieve the same goal of creating, deploying (publishing) and consuming a production model. The two facets of the project, explores the Azure ML End-to-End solution platform for other web services to interact with a deployed model. 

## Summary
The data for use in this project is the UCI Bank Marketing dataset on client responses acquired through a direct call marketing campaign by a Portuguese banking Institution with the aim to access whether a client would subscribe for the bank term deposit given as a ‘yes’, or a ‘no’. Therefore, the problem suggests a binary classification problem where the goal is to predict if the client will subscribe a term deposit. The data can be found here: https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv". For this classification task of predicting whether a user will subscribe, which will either be a ‘yes’ or a ‘no’, the Voting Ensemble model emerged as the best performing model and serves as the production model which is deployed and consumed for client-side consumption.

## Project Architecture
This project architecture is diagrammatically shown below.

The individual steps to the realization of the Azure ML End-to-End solution deployment platform comprises of the following.
 
     1.	Authentication
     2.	Upload and Register Dataset
     3.	Automated ML Experiment
     4.	Deploy the best model
     5.	Enable logging
     6.	Swagger Documentation
     7.	Consume model endpoints
     8.	Create and publish a pipeline
     9.	Documentation

These steps will be described subsequently, though with the exclusion of the Authentication and Documentation steps. The Authentication step is basically for creating a service principle which will enable role-based access control for exploring Azure resources, but the project is currently using the Udacity provided access. For the Documentation, this “ReadMe file” provides the details of this project’s Azure ML pipeline execution process.
 

## Key Steps
Step 1: Upload and register the Bank Marketing dataset to workspace.


Step 2: Create a new Automated ML Experiment. This usually takes about 30 minutes to 1 hour to complete, but once completed the experiment status will change from ‘Running’ to ‘Completed’. 


Step 3: Select the best model. The best model is typically the top most of all listed models the AUTOML applied for solving the given Bank Marketing problem. As we can see below, the Voting Ensemble is projected the best model. 


Step 4: Deploy the best model. A deployed model interacts with a production environment via HTTP API service in order to receive input via a POST request and return the model’s predicted output. 


Step 5: Enable logging. This can be achieved with Application Insight tool which helps to detect anomalies and visualize errors. Shown below are the enabled “Application Insight” and the generated logs, respectively.


Step 6: Swagger Documentation. Azure ML has support for Swagger, which is a tool that makes it easy for internal and external services to interact with the HTTP API of a deployed model for back-end implementation and client-side consumption. We show our project HTTP API methods and its response on swagger as follows.


Step 7: Consume model endpoints. At this point, the consume model endpoint, which is created once the model is deployed, gives us the privilege to establish internal and external services interactions such as request and response to the HTTP API. 


Step 8: Create and publish a pipeline. The Azure ML pipeline offers a coding possibility for an End-to-End Machine Learning pipeline using the Python SDK to achieve the same goal of creating, deploying (publishing) and consuming a production model. The processes are summarized with the below given images. 

## Screen Recording
For a demonstration of the capabilities of Azure ML Studio for the development of End-to-End ML production model, click the provided link to a screencast recording of the project. 

                         https://www.youtube.com/watch?v=nTR-1-DI3Tg

## Standout Suggestions
There are two standout modifications mad: 

    • First: We replicated the default profiler in Azure ML studio, which generates profiles of registered dataset, by exploring the Pandas profiling functionality. Provided 
    below is a view of the correlation table generated between all variables in the dataset. 

    • In order to explore the importance of features that contributed to the success of the best prediction model within the Azure ML Python SDK, the model expandability     
    parameter was set to True in the AUTOML configuration settings. It allowed us to have a view of the top four features that contributed to the best model performance. 
