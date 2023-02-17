# Overview

In this project we send data as input for a machine learning model to predict the price of a house.
Example:
These are parameters we are sending to machine learning model 
`{  
   "CHAS":{  
      "0":0
   },
   "RM":{  
      "0":6.575
   },
   "TAX":{  
      "0":296.0
   },
   "PTRATIO":{  
      "0":15.3
   },
   "B":{  
      "0":396.9
   },
   "LSTAT":{  
      "0":4.98
   }`
These features are used as input for a machine learning model to predict the price of a house.


## Project Plan

* A link to a Trello board for the project
* A link to a spreadsheet that includes the original and final project plan>

## Instructions

* Architectural Diagram (Shows how key parts of the system work)

            
 Azure Pipeline   <--------   Self-hosted Agent
         |                              |
         |                              |
         |                              |
         |                              |
      Source        <--------     Build and Test   
     Control                      Environment     

* Explanation of components


The architecture consists of an Azure Pipeline service that initiates the build and deployment process, and communicates with a self-hosted agent that is running on a user-managed machine. The self-hosted agent is responsible for executing the build and test steps, as well as deploying the application to the target environment.

The source control system is where the application's source code is stored, and is integrated with the Azure Pipeline service to trigger the build and deployment process. The build and test environment is where the application is built and tested, and is also integrated with the Azure Pipeline service to provide feedback on the build and test results.


<TODO:  Instructions for running the Python project.  How could a user with no context run this project without asking you for any help.  Include screenshots with explicit steps to create that work. Be sure to at least include the following screenshots:

* Project running on Azure App Service


* Project cloned into Azure Cloud Shell
![Git clone](./sc/gitclone.png)

* Passing tests that are displayed after running the `make all` command from the `Makefile`

* Output of a test run

* Successful deploy of the project in Azure Pipelines.  [Note the official documentation should be referred to and double checked as you setup CI/CD](https://docs.microsoft.com/en-us/azure/devops/pipelines/ecosystems/python-webapp?view=azure-devops).

* Running Azure App Service from Azure Pipelines automatic deployment

* Successful prediction from deployed flask app in Azure Cloud Shell.  [Use this file as a template for the deployed prediction](https://github.com/udacity/nd082-Azure-Cloud-DevOps-Starter-Code/blob/master/C2-AgileDevelopmentwithAzure/project/starter_files/flask-sklearn/make_predict_azure_app.sh).
The output should look similar to this:

```bash
udacity@Azure:~$ ./make_predict_azure_app.sh
Port: 443
{"prediction":[20.35373177134412]}
```

* Output of streamed log files from deployed application

> 

## Enhancements

<TODO: A short description of how to improve the project in the future>

## Demo 

<TODO: Add link Screencast on YouTube>
