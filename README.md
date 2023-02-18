# Azure-ML-devops-project
## Overview

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

* [Trello Board](./sc/trello-board.png)
* [Project plan in excel](https://github.com/gurumukh/azure-devops-project/blob/main/plan.xlsx)

## Instructions

* Architectural Diagram
 
![Git clone](./sc/arch.png)
* Explanation of components


The architecture consists of an Azure Pipeline service that initiates the build and deployment process, and communicates with a self-hosted agent that is running on a user-managed machine. The self-hosted agent is responsible for executing the build and test steps, as well as deploying the application to the target environment.

The source control system is where the application's source code is stored, and is integrated with the Azure Pipeline service to trigger the build and deployment process. The build and test environment is where the application is built and tested, and is also integrated with the Azure Pipeline service to provide feedback on the build and test results.


 ### Instructions for running the Python project.

* Project running on Azure App Service
![Project running](./sc/project-running.png)

* Project cloned into Azure Cloud Shell
1. first you need to create ssh key and add into your github profile .
2. you just need to clone from github in your azure cloud shell using `git clone <rep url>`
3. setup virtual environment
    ```
    python3 -m venv env 
    source venv/bin/activate
    ```
![Git clone](./sc/gitclone.png)

* Passing tests that are displayed after running the `make all` command from the `Makefile`
![makeall](./sc/makeall.png)

* Output of a test run
![test pass](./sc/githubtestpass.png)
![test pass](./sc/batch-readme.png)

* Successful deploy of the project in Azure Pipelines.
![build success](./sc/build-success.png)

* Running Azure App Service from Azure Pipelines automatic deployment
![azure pipeline](./sc/running-az-pipeservice.png)

* Successful prediction from deployed flask app in Azure Cloud Shell.
1. run your project using `python app.py`
2. run ./make_predicition.sh
![Git clone](./sc/predection.png)

* Output of streamed log files from deployed application
```
2023-02-17T07:00:18.4220514Z ##[section]Starting: BuildJob
2023-02-17T07:00:19.5395064Z ##[section]Starting: Initialize job
2023-02-17T07:00:19.5397496Z Agent name: 'udacity-devops'
2023-02-17T07:00:19.5398154Z Agent machine name: 'udacity-devops'
2023-02-17T07:00:19.5398525Z Current agent version: '2.217.2'
2023-02-17T07:00:19.5419849Z Agent running as: 'devops'
2023-02-17T07:00:19.5477697Z Prepare build directory.
2023-02-17T07:00:19.5991939Z Set build variables.
2023-02-17T07:00:19.6032260Z Download all required tasks.
2023-02-17T07:00:19.6305211Z Checking job knob settings.
2023-02-17T07:00:19.6320969Z    Knob: ContinueAfterCancelProcessTreeKillAttempt = true Source: $(VSTSAGENT_CONTINUE_AFTER_CANCEL_PROCESSTREEKILL_ATTEMPT) 
2023-02-17T07:00:19.6321775Z Finished checking job knob settings.
2023-02-17T07:00:19.7496334Z Plugin: 'Test Result Parser plugin' is running in background.
2023-02-17T07:00:19.7497402Z Plugin: 'Test File Publisher plugin' is running in background.
2023-02-17T07:00:19.7499034Z Start tracking orphan processes.
2023-02-17T07:00:19.7727252Z ##[section]Finishing: Initialize job
2023-02-17T07:00:19.8216997Z ##[section]Starting: Checkout gurumukh/azure-devops-project@main to s
2023-02-17T07:00:19.8669031Z ==============================================================================
2023-02-17T07:00:19.8670504Z Task         : Get sources
2023-02-17T07:00:19.8671609Z Description  : Get sources from a repository. Supports Git, TfsVC, and SVN repositories.
2023-02-17T07:00:19.8672592Z Version      : 1.0.0
2023-02-17T07:00:19.8673412Z Author       : Microsoft
2023-02-17T07:00:19.8674619Z Help         : [More Information](https://go.microsoft.com/fwlink/?LinkId=798199)
2023-02-17T07:00:19.8675340Z ==============================================================================
2023-02-17T07:00:26.5177422Z Syncing repository: gurumukh/azure-devops-project (GitHub)
2023-02-17T07:00:26.5199973Z ##[command]git version
2023-02-17T07:00:26.5212584Z git version 2.25.1
2023-02-17T07:00:26.5216379Z ##[command]git config --get remote.origin.url
2023-02-17T07:00:26.5230347Z ##[command]git clean -ffdx
2023-02-17T07:00:26.5242615Z ##[command]git reset --hard HEAD
2023-02-17T07:00:26.5257606Z HEAD is now at f509905 update readme
2023-02-17T07:00:26.5275330Z ##[command]git config gc.auto 0
2023-02-17T07:00:26.5295592Z ##[command]git config --get-all http.https://github.com/gurumukh/azure-devops-project.extraheader
2023-02-17T07:00:26.5311137Z ##[command]git config --get-all http.extraheader
2023-02-17T07:00:26.5323416Z ##[command]git config --get-regexp .*extraheader
2023-02-17T07:00:26.5344806Z ##[command]git config --get-all http.proxy
2023-02-17T07:00:26.5368184Z ##[command]git config http.version HTTP/1.1
2023-02-17T07:00:26.5403392Z ##[command]git -c http.extraheader="AUTHORIZATION: basic ***" fetch --force --tags --prune --prune-tags --progress --no-recurse-submodules origin --depth=1
2023-02-17T07:00:26.5423703Z remote: Enumerating objects: 8, done.        
2023-02-17T07:00:26.5425801Z remote: Counting objects:  12% (1/8)        
2023-02-17T07:00:26.5426727Z remote: Counting objects:  25% (2/8)        
2023-02-17T07:00:26.5427721Z remote: Counting objects:  37% (3/8)        
2023-02-17T07:00:26.5428590Z remote: Counting objects:  50% (4/8)        
2023-02-17T07:00:26.5430199Z remote: Counting objects:  62% (5/8)        
2023-02-17T07:00:26.5432452Z remote: Counting objects:  75% (6/8)        
2023-02-17T07:00:26.5434197Z remote: Counting objects:  87% (7/8)        
2023-02-17T07:00:26.5435820Z remote: Counting objects: 100% (8/8)        
2023-02-17T07:00:26.5437417Z remote: Counting objects: 100% (8/8), done.        
2023-02-17T07:00:26.5439064Z remote: Compressing objects:  50% (1/2)        
2023-02-17T07:00:26.5441718Z remote: Compressing objects: 100% (2/2)        
2023-02-17T07:00:26.5443998Z remote: Compressing objects: 100% (2/2), done.        
2023-02-17T07:00:26.5445615Z remote: Total 5 (delta 3), reused 5 (delta 3), pack-reused 0        
2023-02-17T07:00:26.5446829Z From https://github.com/gurumukh/azure-devops-project
2023-02-17T07:00:26.5448452Z  + f509905...b1d3018 main       -> origin/main  (forced update)
2023-02-17T07:00:27.8729185Z ##[command]git checkout --progress --force b1d30182cfa6b36ab3550b225892cea3eb370066
2023-02-17T07:00:27.8757056Z Warning: you are leaving 1 commit behind, not connected to
2023-02-17T07:00:27.8759596Z any of your branches:
2023-02-17T07:00:27.8760462Z 
2023-02-17T07:00:27.8761548Z   f509905 update readme
2023-02-17T07:00:27.8762398Z 
2023-02-17T07:00:27.8763688Z If you want to keep it by creating a new branch, this may be a good time
2023-02-17T07:00:27.8765116Z to do so with:
2023-02-17T07:00:27.8765952Z 
2023-02-17T07:00:27.8767666Z  git branch <new-branch-name> f509905
2023-02-17T07:00:27.8768546Z 
2023-02-17T07:00:27.8769761Z HEAD is now at b1d3018 update readme for build success in azure
2023-02-17T07:00:27.8881454Z ##[section]Finishing: Checkout gurumukh/azure-devops-project@main to s
2023-02-17T07:00:28.5098531Z ##[section]Starting: myStep 1
2023-02-17T07:00:28.5124561Z ==============================================================================
2023-02-17T07:00:28.5126383Z Task         : Command line
2023-02-17T07:00:28.5127312Z Description  : Run a command line script using Bash on Linux and macOS and cmd.exe on Windows
2023-02-17T07:00:28.5129126Z Version      : 2.212.0
2023-02-17T07:00:28.5130144Z Author       : Microsoft Corporation
2023-02-17T07:00:28.5131164Z Help         : https://docs.microsoft.com/azure/devops/pipelines/tasks/utility/command-line
2023-02-17T07:00:28.5132138Z ==============================================================================
2023-02-17T07:00:30.8957793Z Generating script.
2023-02-17T07:00:30.8986966Z ========================== Starting Command Output ===========================
2023-02-17T07:00:30.9001355Z [command]/usr/bin/bash --noprofile --norc /home/devops/myagent/_work/_temp/0cd9c1d7-a5a5-41f9-8b7b-732158f7ad86.sh
2023-02-17T07:00:31.3643906Z Defaulting to user installation because normal site-packages is not writeable
2023-02-17T07:00:31.5106483Z Requirement already satisfied: pip in /home/devops/.local/lib/python3.7/site-packages (23.0)
2023-02-17T07:00:32.4548423Z Defaulting to user installation because normal site-packages is not writeable
2023-02-17T07:00:32.6389757Z ERROR: Could not find a version that satisfies the requirement setup (from versions: none)
2023-02-17T07:00:32.6435221Z ERROR: No matching distribution found for setup
2023-02-17T07:00:33.1690992Z Defaulting to user installation because normal site-packages is not writeable
2023-02-17T07:00:33.3185979Z Requirement already satisfied: Flask==2.2.2 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 1)) (2.2.2)
2023-02-17T07:00:33.3198316Z Requirement already satisfied: pandas==1.3.5 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 2)) (1.3.5)
2023-02-17T07:00:33.3214849Z Requirement already satisfied: scikit-learn==1.0.2 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 3)) (1.0.2)
2023-02-17T07:00:33.3230051Z Requirement already satisfied: joblib==1.2.0 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 4)) (1.2.0)
2023-02-17T07:00:33.3265950Z Requirement already satisfied: pylint==2.13.7 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 5)) (2.13.7)
2023-02-17T07:00:33.3270302Z Requirement already satisfied: pytest==7.1.2 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 6)) (7.1.2)
2023-02-17T07:00:33.3429369Z Requirement already satisfied: click>=8.0 in /home/devops/.local/lib/python3.7/site-packages (from Flask==2.2.2->-r requirements.txt (line 1)) (8.1.3)
2023-02-17T07:00:33.3466579Z Requirement already satisfied: importlib-metadata>=3.6.0 in /home/devops/.local/lib/python3.7/site-packages (from Flask==2.2.2->-r requirements.txt (line 1)) (6.0.0)
2023-02-17T07:00:33.3490289Z Requirement already satisfied: itsdangerous>=2.0 in /home/devops/.local/lib/python3.7/site-packages (from Flask==2.2.2->-r requirements.txt (line 1)) (2.1.2)
2023-02-17T07:00:33.3604661Z Requirement already satisfied: Werkzeug>=2.2.2 in /home/devops/.local/lib/python3.7/site-packages (from Flask==2.2.2->-r requirements.txt (line 1)) (2.2.3)
2023-02-17T07:00:33.3608912Z Requirement already satisfied: Jinja2>=3.0 in /home/devops/.local/lib/python3.7/site-packages (from Flask==2.2.2->-r requirements.txt (line 1)) (3.1.2)
2023-02-17T07:00:33.3773704Z Requirement already satisfied: pytz>=2017.3 in /home/devops/.local/lib/python3.7/site-packages (from pandas==1.3.5->-r requirements.txt (line 2)) (2022.7.1)
2023-02-17T07:00:33.3814719Z Requirement already satisfied: numpy>=1.17.3 in /home/devops/.local/lib/python3.7/site-packages (from pandas==1.3.5->-r requirements.txt (line 2)) (1.21.6)
2023-02-17T07:00:33.3852854Z Requirement already satisfied: python-dateutil>=2.7.3 in /home/devops/.local/lib/python3.7/site-packages (from pandas==1.3.5->-r requirements.txt (line 2)) (2.8.2)
2023-02-17T07:00:33.4350480Z Requirement already satisfied: scipy>=1.1.0 in /home/devops/.local/lib/python3.7/site-packages (from scikit-learn==1.0.2->-r requirements.txt (line 3)) (1.7.3)
2023-02-17T07:00:33.4355189Z Requirement already satisfied: threadpoolctl>=2.0.0 in /home/devops/.local/lib/python3.7/site-packages (from scikit-learn==1.0.2->-r requirements.txt (line 3)) (3.1.0)
2023-02-17T07:00:33.4565811Z Requirement already satisfied: typing-extensions>=3.10.0 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (4.5.0)
2023-02-17T07:00:33.4597820Z Requirement already satisfied: isort<6,>=4.2.5 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (5.11.5)
2023-02-17T07:00:33.4602453Z Requirement already satisfied: dill>=0.2 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (0.3.6)
2023-02-17T07:00:33.4605766Z Requirement already satisfied: platformdirs>=2.2.0 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (3.0.0)
2023-02-17T07:00:33.4629137Z Requirement already satisfied: tomli>=1.1.0 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (2.0.1)
2023-02-17T07:00:33.4647894Z Requirement already satisfied: astroid<=2.12.0-dev0,>=2.11.3 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (2.11.7)
2023-02-17T07:00:33.4664355Z Requirement already satisfied: mccabe<0.8,>=0.6 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (0.7.0)
2023-02-17T07:00:33.5102449Z Requirement already satisfied: packaging in /home/devops/.local/lib/python3.7/site-packages (from pytest==7.1.2->-r requirements.txt (line 6)) (23.0)
2023-02-17T07:00:33.5115602Z Requirement already satisfied: py>=1.8.2 in /home/devops/.local/lib/python3.7/site-packages (from pytest==7.1.2->-r requirements.txt (line 6)) (1.11.0)
2023-02-17T07:00:33.5131454Z Requirement already satisfied: pluggy<2.0,>=0.12 in /home/devops/.local/lib/python3.7/site-packages (from pytest==7.1.2->-r requirements.txt (line 6)) (1.0.0)
2023-02-17T07:00:33.5145129Z Requirement already satisfied: attrs>=19.2.0 in /usr/lib/python3/dist-packages (from pytest==7.1.2->-r requirements.txt (line 6)) (19.3.0)
2023-02-17T07:00:33.5155044Z Requirement already satisfied: iniconfig in /home/devops/.local/lib/python3.7/site-packages (from pytest==7.1.2->-r requirements.txt (line 6)) (2.0.0)
2023-02-17T07:00:33.5298098Z Requirement already satisfied: wrapt<2,>=1.11 in /home/devops/.local/lib/python3.7/site-packages (from astroid<=2.12.0-dev0,>=2.11.3->pylint==2.13.7->-r requirements.txt (line 5)) (1.14.1)
2023-02-17T07:00:33.5323975Z Requirement already satisfied: typed-ast<2.0,>=1.4.0 in /home/devops/.local/lib/python3.7/site-packages (from astroid<=2.12.0-dev0,>=2.11.3->pylint==2.13.7->-r requirements.txt (line 5)) (1.5.4)
2023-02-17T07:00:33.5340607Z Requirement already satisfied: setuptools>=20.0 in /usr/lib/python3/dist-packages (from astroid<=2.12.0-dev0,>=2.11.3->pylint==2.13.7->-r requirements.txt (line 5)) (45.2.0)
2023-02-17T07:00:33.5355980Z Requirement already satisfied: lazy-object-proxy>=1.4.0 in /home/devops/.local/lib/python3.7/site-packages (from astroid<=2.12.0-dev0,>=2.11.3->pylint==2.13.7->-r requirements.txt (line 5)) (1.9.0)
2023-02-17T07:00:33.5901362Z Requirement already satisfied: zipp>=0.5 in /usr/lib/python3/dist-packages (from importlib-metadata>=3.6.0->Flask==2.2.2->-r requirements.txt (line 1)) (1.0.0)
2023-02-17T07:00:33.6134418Z Requirement already satisfied: MarkupSafe>=2.0 in /home/devops/.local/lib/python3.7/site-packages (from Jinja2>=3.0->Flask==2.2.2->-r requirements.txt (line 1)) (2.1.2)
2023-02-17T07:00:33.6623266Z Requirement already satisfied: six>=1.5 in /usr/lib/python3/dist-packages (from python-dateutil>=2.7.3->pandas==1.3.5->-r requirements.txt (line 2)) (1.14.0)
2023-02-17T07:00:33.9253545Z ##[section]Finishing: myStep 1
2023-02-17T07:00:35.1454163Z ##[section]Starting: myStep 2
2023-02-17T07:00:35.1473891Z ==============================================================================
2023-02-17T07:00:35.1474835Z Task         : Command line
2023-02-17T07:00:35.1475426Z Description  : Run a command line script using Bash on Linux and macOS and cmd.exe on Windows
2023-02-17T07:00:35.1476214Z Version      : 2.212.0
2023-02-17T07:00:35.1478912Z Author       : Microsoft Corporation
2023-02-17T07:00:35.1480309Z Help         : https://docs.microsoft.com/azure/devops/pipelines/tasks/utility/command-line
2023-02-17T07:00:35.1481135Z ==============================================================================
2023-02-17T07:00:37.4171125Z Generating script.
2023-02-17T07:00:37.4199950Z ========================== Starting Command Output ===========================
2023-02-17T07:00:37.4315839Z [command]/usr/bin/bash --noprofile --norc /home/devops/myagent/_work/_temp/28385a9b-c470-4623-92d0-a2db56880927.sh
2023-02-17T07:00:37.4387942Z pip install --upgrade pip &&\
2023-02-17T07:00:37.4390059Z 	pip install -r requirements.txt
2023-02-17T07:00:38.5900501Z Defaulting to user installation because normal site-packages is not writeable
2023-02-17T07:00:38.5945187Z Requirement already satisfied: pip in /home/devops/.local/lib/python3.7/site-packages (23.0)
2023-02-17T07:00:38.9780087Z Defaulting to user installation because normal site-packages is not writeable
2023-02-17T07:00:39.1243677Z Requirement already satisfied: Flask==2.2.2 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 1)) (2.2.2)
2023-02-17T07:00:39.1256294Z Requirement already satisfied: pandas==1.3.5 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 2)) (1.3.5)
2023-02-17T07:00:39.1274759Z Requirement already satisfied: scikit-learn==1.0.2 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 3)) (1.0.2)
2023-02-17T07:00:39.1290499Z Requirement already satisfied: joblib==1.2.0 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 4)) (1.2.0)
2023-02-17T07:00:39.1310191Z Requirement already satisfied: pylint==2.13.7 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 5)) (2.13.7)
2023-02-17T07:00:39.1324225Z Requirement already satisfied: pytest==7.1.2 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 6)) (7.1.2)
2023-02-17T07:00:39.1455042Z Requirement already satisfied: Jinja2>=3.0 in /home/devops/.local/lib/python3.7/site-packages (from Flask==2.2.2->-r requirements.txt (line 1)) (3.1.2)
2023-02-17T07:00:39.1481149Z Requirement already satisfied: importlib-metadata>=3.6.0 in /home/devops/.local/lib/python3.7/site-packages (from Flask==2.2.2->-r requirements.txt (line 1)) (6.0.0)
2023-02-17T07:00:39.1496697Z Requirement already satisfied: itsdangerous>=2.0 in /home/devops/.local/lib/python3.7/site-packages (from Flask==2.2.2->-r requirements.txt (line 1)) (2.1.2)
2023-02-17T07:00:39.1511767Z Requirement already satisfied: Werkzeug>=2.2.2 in /home/devops/.local/lib/python3.7/site-packages (from Flask==2.2.2->-r requirements.txt (line 1)) (2.2.3)
2023-02-17T07:00:39.1525784Z Requirement already satisfied: click>=8.0 in /home/devops/.local/lib/python3.7/site-packages (from Flask==2.2.2->-r requirements.txt (line 1)) (8.1.3)
2023-02-17T07:00:39.1709443Z Requirement already satisfied: pytz>=2017.3 in /home/devops/.local/lib/python3.7/site-packages (from pandas==1.3.5->-r requirements.txt (line 2)) (2022.7.1)
2023-02-17T07:00:39.1739485Z Requirement already satisfied: numpy>=1.17.3 in /home/devops/.local/lib/python3.7/site-packages (from pandas==1.3.5->-r requirements.txt (line 2)) (1.21.6)
2023-02-17T07:00:39.1754766Z Requirement already satisfied: python-dateutil>=2.7.3 in /home/devops/.local/lib/python3.7/site-packages (from pandas==1.3.5->-r requirements.txt (line 2)) (2.8.2)
2023-02-17T07:00:39.2169356Z Requirement already satisfied: scipy>=1.1.0 in /home/devops/.local/lib/python3.7/site-packages (from scikit-learn==1.0.2->-r requirements.txt (line 3)) (1.7.3)
2023-02-17T07:00:39.2182725Z Requirement already satisfied: threadpoolctl>=2.0.0 in /home/devops/.local/lib/python3.7/site-packages (from scikit-learn==1.0.2->-r requirements.txt (line 3)) (3.1.0)
2023-02-17T07:00:39.2363507Z Requirement already satisfied: typing-extensions>=3.10.0 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (4.5.0)
2023-02-17T07:00:39.2387272Z Requirement already satisfied: tomli>=1.1.0 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (2.0.1)
2023-02-17T07:00:39.2401712Z Requirement already satisfied: mccabe<0.8,>=0.6 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (0.7.0)
2023-02-17T07:00:39.2418539Z Requirement already satisfied: isort<6,>=4.2.5 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (5.11.5)
2023-02-17T07:00:39.2434957Z Requirement already satisfied: astroid<=2.12.0-dev0,>=2.11.3 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (2.11.7)
2023-02-17T07:00:39.2448529Z Requirement already satisfied: platformdirs>=2.2.0 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (3.0.0)
2023-02-17T07:00:39.2462753Z Requirement already satisfied: dill>=0.2 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (0.3.6)
2023-02-17T07:00:39.2685083Z Requirement already satisfied: py>=1.8.2 in /home/devops/.local/lib/python3.7/site-packages (from pytest==7.1.2->-r requirements.txt (line 6)) (1.11.0)
2023-02-17T07:00:39.2694712Z Requirement already satisfied: iniconfig in /home/devops/.local/lib/python3.7/site-packages (from pytest==7.1.2->-r requirements.txt (line 6)) (2.0.0)
2023-02-17T07:00:39.2708605Z Requirement already satisfied: attrs>=19.2.0 in /usr/lib/python3/dist-packages (from pytest==7.1.2->-r requirements.txt (line 6)) (19.3.0)
2023-02-17T07:00:39.2720686Z Requirement already satisfied: packaging in /home/devops/.local/lib/python3.7/site-packages (from pytest==7.1.2->-r requirements.txt (line 6)) (23.0)
2023-02-17T07:00:39.2735110Z Requirement already satisfied: pluggy<2.0,>=0.12 in /home/devops/.local/lib/python3.7/site-packages (from pytest==7.1.2->-r requirements.txt (line 6)) (1.0.0)
2023-02-17T07:00:39.2875437Z Requirement already satisfied: typed-ast<2.0,>=1.4.0 in /home/devops/.local/lib/python3.7/site-packages (from astroid<=2.12.0-dev0,>=2.11.3->pylint==2.13.7->-r requirements.txt (line 5)) (1.5.4)
2023-02-17T07:00:39.2891672Z Requirement already satisfied: setuptools>=20.0 in /usr/lib/python3/dist-packages (from astroid<=2.12.0-dev0,>=2.11.3->pylint==2.13.7->-r requirements.txt (line 5)) (45.2.0)
2023-02-17T07:00:39.2909656Z Requirement already satisfied: lazy-object-proxy>=1.4.0 in /home/devops/.local/lib/python3.7/site-packages (from astroid<=2.12.0-dev0,>=2.11.3->pylint==2.13.7->-r requirements.txt (line 5)) (1.9.0)
2023-02-17T07:00:39.2923373Z Requirement already satisfied: wrapt<2,>=1.11 in /home/devops/.local/lib/python3.7/site-packages (from astroid<=2.12.0-dev0,>=2.11.3->pylint==2.13.7->-r requirements.txt (line 5)) (1.14.1)
2023-02-17T07:00:39.3452693Z Requirement already satisfied: zipp>=0.5 in /usr/lib/python3/dist-packages (from importlib-metadata>=3.6.0->Flask==2.2.2->-r requirements.txt (line 1)) (1.0.0)
2023-02-17T07:00:39.3632337Z Requirement already satisfied: MarkupSafe>=2.0 in /home/devops/.local/lib/python3.7/site-packages (from Jinja2>=3.0->Flask==2.2.2->-r requirements.txt (line 1)) (2.1.2)
2023-02-17T07:00:39.3989086Z Requirement already satisfied: six>=1.5 in /usr/lib/python3/dist-packages (from python-dateutil>=2.7.3->pandas==1.3.5->-r requirements.txt (line 2)) (1.14.0)
2023-02-17T07:00:39.6981611Z ##[section]Finishing: myStep 2
2023-02-17T07:00:40.8833689Z ##[section]Starting: myStep 3 - Run lint tests
2023-02-17T07:00:40.8845688Z ==============================================================================
2023-02-17T07:00:40.8846908Z Task         : Command line
2023-02-17T07:00:40.8848004Z Description  : Run a command line script using Bash on Linux and macOS and cmd.exe on Windows
2023-02-17T07:00:40.8848529Z Version      : 2.212.0
2023-02-17T07:00:40.8848908Z Author       : Microsoft Corporation
2023-02-17T07:00:40.8849372Z Help         : https://docs.microsoft.com/azure/devops/pipelines/tasks/utility/command-line
2023-02-17T07:00:40.8849858Z ==============================================================================
2023-02-17T07:00:43.0946946Z Generating script.
2023-02-17T07:00:43.0951677Z ========================== Starting Command Output ===========================
2023-02-17T07:00:43.0966945Z [command]/usr/bin/bash --noprofile --norc /home/devops/myagent/_work/_temp/8e801b8c-bc3e-411e-b432-ef9b1e700148.sh
2023-02-17T07:00:43.1059466Z pip install --upgrade pip &&\
2023-02-17T07:00:43.1061377Z 	pip install -r requirements.txt
2023-02-17T07:00:43.5564459Z Defaulting to user installation because normal site-packages is not writeable
2023-02-17T07:00:43.7105789Z Requirement already satisfied: pip in /home/devops/.local/lib/python3.7/site-packages (23.0)
2023-02-17T07:00:44.6154582Z Defaulting to user installation because normal site-packages is not writeable
2023-02-17T07:00:44.7666737Z Requirement already satisfied: Flask==2.2.2 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 1)) (2.2.2)
2023-02-17T07:00:44.7679140Z Requirement already satisfied: pandas==1.3.5 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 2)) (1.3.5)
2023-02-17T07:00:44.7694704Z Requirement already satisfied: scikit-learn==1.0.2 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 3)) (1.0.2)
2023-02-17T07:00:44.7709734Z Requirement already satisfied: joblib==1.2.0 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 4)) (1.2.0)
2023-02-17T07:00:44.7728275Z Requirement already satisfied: pylint==2.13.7 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 5)) (2.13.7)
2023-02-17T07:00:44.7742314Z Requirement already satisfied: pytest==7.1.2 in /home/devops/.local/lib/python3.7/site-packages (from -r requirements.txt (line 6)) (7.1.2)
2023-02-17T07:00:44.7861364Z Requirement already satisfied: itsdangerous>=2.0 in /home/devops/.local/lib/python3.7/site-packages (from Flask==2.2.2->-r requirements.txt (line 1)) (2.1.2)
2023-02-17T07:00:44.7873878Z Requirement already satisfied: Jinja2>=3.0 in /home/devops/.local/lib/python3.7/site-packages (from Flask==2.2.2->-r requirements.txt (line 1)) (3.1.2)
2023-02-17T07:00:44.7900087Z Requirement already satisfied: importlib-metadata>=3.6.0 in /home/devops/.local/lib/python3.7/site-packages (from Flask==2.2.2->-r requirements.txt (line 1)) (6.0.0)
2023-02-17T07:00:44.7913751Z Requirement already satisfied: Werkzeug>=2.2.2 in /home/devops/.local/lib/python3.7/site-packages (from Flask==2.2.2->-r requirements.txt (line 1)) (2.2.3)
2023-02-17T07:00:44.7928783Z Requirement already satisfied: click>=8.0 in /home/devops/.local/lib/python3.7/site-packages (from Flask==2.2.2->-r requirements.txt (line 1)) (8.1.3)
2023-02-17T07:00:44.8119407Z Requirement already satisfied: numpy>=1.17.3 in /home/devops/.local/lib/python3.7/site-packages (from pandas==1.3.5->-r requirements.txt (line 2)) (1.21.6)
2023-02-17T07:00:44.8133766Z Requirement already satisfied: pytz>=2017.3 in /home/devops/.local/lib/python3.7/site-packages (from pandas==1.3.5->-r requirements.txt (line 2)) (2022.7.1)
2023-02-17T07:00:44.8150559Z Requirement already satisfied: python-dateutil>=2.7.3 in /home/devops/.local/lib/python3.7/site-packages (from pandas==1.3.5->-r requirements.txt (line 2)) (2.8.2)
2023-02-17T07:00:44.8556759Z Requirement already satisfied: scipy>=1.1.0 in /home/devops/.local/lib/python3.7/site-packages (from scikit-learn==1.0.2->-r requirements.txt (line 3)) (1.7.3)
2023-02-17T07:00:44.8571124Z Requirement already satisfied: threadpoolctl>=2.0.0 in /home/devops/.local/lib/python3.7/site-packages (from scikit-learn==1.0.2->-r requirements.txt (line 3)) (3.1.0)
2023-02-17T07:00:44.8761161Z Requirement already satisfied: typing-extensions>=3.10.0 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (4.5.0)
2023-02-17T07:00:44.8784850Z Requirement already satisfied: tomli>=1.1.0 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (2.0.1)
2023-02-17T07:00:44.8799806Z Requirement already satisfied: dill>=0.2 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (0.3.6)
2023-02-17T07:00:44.8816330Z Requirement already satisfied: astroid<=2.12.0-dev0,>=2.11.3 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (2.11.7)
2023-02-17T07:00:44.8833970Z Requirement already satisfied: platformdirs>=2.2.0 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (3.0.0)
2023-02-17T07:00:44.8847826Z Requirement already satisfied: isort<6,>=4.2.5 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (5.11.5)
2023-02-17T07:00:44.8862271Z Requirement already satisfied: mccabe<0.8,>=0.6 in /home/devops/.local/lib/python3.7/site-packages (from pylint==2.13.7->-r requirements.txt (line 5)) (0.7.0)
2023-02-17T07:00:44.9079517Z Requirement already satisfied: packaging in /home/devops/.local/lib/python3.7/site-packages (from pytest==7.1.2->-r requirements.txt (line 6)) (23.0)
2023-02-17T07:00:44.9095811Z Requirement already satisfied: pluggy<2.0,>=0.12 in /home/devops/.local/lib/python3.7/site-packages (from pytest==7.1.2->-r requirements.txt (line 6)) (1.0.0)
2023-02-17T07:00:44.9109788Z Requirement already satisfied: iniconfig in /home/devops/.local/lib/python3.7/site-packages (from pytest==7.1.2->-r requirements.txt (line 6)) (2.0.0)
2023-02-17T07:00:44.9124371Z Requirement already satisfied: py>=1.8.2 in /home/devops/.local/lib/python3.7/site-packages (from pytest==7.1.2->-r requirements.txt (line 6)) (1.11.0)
2023-02-17T07:00:44.9140418Z Requirement already satisfied: attrs>=19.2.0 in /usr/lib/python3/dist-packages (from pytest==7.1.2->-r requirements.txt (line 6)) (19.3.0)
2023-02-17T07:00:44.9277421Z Requirement already satisfied: lazy-object-proxy>=1.4.0 in /home/devops/.local/lib/python3.7/site-packages (from astroid<=2.12.0-dev0,>=2.11.3->pylint==2.13.7->-r requirements.txt (line 5)) (1.9.0)
2023-02-17T07:00:44.9293913Z Requirement already satisfied: wrapt<2,>=1.11 in /home/devops/.local/lib/python3.7/site-packages (from astroid<=2.12.0-dev0,>=2.11.3->pylint==2.13.7->-r requirements.txt (line 5)) (1.14.1)
2023-02-17T07:00:44.9323551Z Requirement already satisfied: typed-ast<2.0,>=1.4.0 in /home/devops/.local/lib/python3.7/site-packages (from astroid<=2.12.0-dev0,>=2.11.3->pylint==2.13.7->-r requirements.txt (line 5)) (1.5.4)
2023-02-17T07:00:44.9339131Z Requirement already satisfied: setuptools>=20.0 in /usr/lib/python3/dist-packages (from astroid<=2.12.0-dev0,>=2.11.3->pylint==2.13.7->-r requirements.txt (line 5)) (45.2.0)
2023-02-17T07:00:45.0044652Z Requirement already satisfied: zipp>=0.5 in /usr/lib/python3/dist-packages (from importlib-metadata>=3.6.0->Flask==2.2.2->-r requirements.txt (line 1)) (1.0.0)
2023-02-17T07:00:45.0215896Z Requirement already satisfied: MarkupSafe>=2.0 in /home/devops/.local/lib/python3.7/site-packages (from Jinja2>=3.0->Flask==2.2.2->-r requirements.txt (line 1)) (2.1.2)
2023-02-17T07:00:45.0578403Z Requirement already satisfied: six>=1.5 in /usr/lib/python3/dist-packages (from python-dateutil>=2.7.3->pandas==1.3.5->-r requirements.txt (line 2)) (1.14.0)
2023-02-17T07:00:45.3067498Z #hadolint Dockerfile #uncomment to explore linting Dockerfiles
2023-02-17T07:00:45.3076220Z pylint --disable=R,C,W1203,W0703 app.py
2023-02-17T07:00:55.1986065Z 
2023-02-17T07:00:55.1990009Z --------------------------------------------------------------------
2023-02-17T07:00:55.1992035Z Your code has been rated at 10.00/10 (previous run: 10.00/10, +0.00)
2023-02-17T07:00:55.1993262Z 
2023-02-17T07:00:57.8365348Z ##[section]Finishing: myStep 3 - Run lint tests
2023-02-17T07:00:59.0015605Z ##[section]Starting: myStep 4 - Archive files
2023-02-17T07:00:59.0032869Z ==============================================================================
2023-02-17T07:00:59.0033921Z Task         : Archive files
2023-02-17T07:00:59.0034636Z Description  : Compress files into .7z, .tar.gz, or .zip
2023-02-17T07:00:59.0035584Z Version      : 2.215.0
2023-02-17T07:00:59.0036406Z Author       : Microsoft Corporation
2023-02-17T07:00:59.0037124Z Help         : https://docs.microsoft.com/azure/devops/pipelines/tasks/utility/archive-files
2023-02-17T07:00:59.0038027Z ==============================================================================
2023-02-17T07:01:00.6317249Z Found 19 files
2023-02-17T07:01:00.6318527Z Archiving file: .git
2023-02-17T07:01:00.6319651Z Archiving file: .github
2023-02-17T07:01:00.6320751Z Archiving file: .gitignore
2023-02-17T07:01:00.6323363Z Archiving file: Dockerfile
2023-02-17T07:01:00.6324811Z Archiving file: Housing_price_model
2023-02-17T07:01:00.6326384Z Archiving file: Makefile
2023-02-17T07:01:00.6327789Z Archiving file: README.md
2023-02-17T07:01:00.6329152Z Archiving file: app.py
2023-02-17T07:01:00.6331174Z Archiving file: azure-pipelines-for-self-hosted-agent.yml
2023-02-17T07:01:00.6332832Z Archiving file: hello.py
2023-02-17T07:01:00.6334188Z ... 9 more ...
2023-02-17T07:01:00.6398060Z files=.git
2023-02-17T07:01:00.6400588Z files=.github
2023-02-17T07:01:00.6402604Z files=.gitignore
2023-02-17T07:01:00.6406723Z files=Dockerfile
2023-02-17T07:01:00.6414781Z files=Housing_price_model
2023-02-17T07:01:00.6417005Z files=Makefile
2023-02-17T07:01:00.6418970Z files=README.md
2023-02-17T07:01:00.6421329Z files=app.py
2023-02-17T07:01:00.6424886Z files=azure-pipelines-for-self-hosted-agent.yml
2023-02-17T07:01:00.6430028Z files=hello.py
2023-02-17T07:01:00.6438486Z files=housing.csv
2023-02-17T07:01:00.6445516Z files=make_predict_azure_app.sh
2023-02-17T07:01:00.6451572Z files=make_prediction.sh
2023-02-17T07:01:00.6471520Z files=requirements.txt
2023-02-17T07:01:00.6476918Z files=run_docker.sh
2023-02-17T07:01:00.6479123Z files=run_kubernetes.sh
2023-02-17T07:01:00.6481197Z files=sc
2023-02-17T07:01:00.6483160Z files=test_hello.py
2023-02-17T07:01:00.6485126Z files=upload_docker.sh
2023-02-17T07:01:00.6519125Z [command]/usr/bin/zip -r /home/devops/myagent/_work/1/a/8.zip .git .github .gitignore Dockerfile Housing_price_model Makefile README.md app.py azure-pipelines-for-self-hosted-agent.yml hello.py housing.csv make_predict_azure_app.sh make_prediction.sh requirements.txt run_docker.sh run_kubernetes.sh sc test_hello.py upload_docker.sh
2023-02-17T07:01:00.7939010Z   adding: .git/ (stored 0%)
2023-02-17T07:01:00.7940785Z   adding: .git/ORIG_HEAD (stored 0%)
2023-02-17T07:01:00.7941818Z   adding: .git/shallow (deflated 40%)
2023-02-17T07:01:00.7943370Z   adding: .git/objects/ (stored 0%)
2023-02-17T07:01:00.7945135Z   adding: .git/objects/e2/ (stored 0%)
2023-02-17T07:01:00.7946657Z   adding: .git/objects/e2/db7fda4446e6eb976e852f8a36371593f7af15 (stored 0%)
2023-02-17T07:01:00.7948053Z   adding: .git/objects/ac/ (stored 0%)
2023-02-17T07:01:00.7949502Z   adding: .git/objects/ac/e29656112e2fc1b60ed4a6adb08b5b3962954a (stored 0%)
2023-02-17T07:01:00.7950810Z   adding: .git/objects/ba/ (stored 0%)
2023-02-17T07:01:00.7952138Z   adding: .git/objects/ba/f3d5dde58c5d0676dc6cca610fad00da18f76f (stored 0%)
2023-02-17T07:01:00.7953565Z   adding: .git/objects/d1/ (stored 0%)
2023-02-17T07:01:00.7954954Z   adding: .git/objects/d1/a7a23a6d6aef8e38584fff34ba3cd0b29ef662 (stored 0%)
2023-02-17T07:01:00.7956344Z   adding: .git/objects/45/ (stored 0%)
2023-02-17T07:01:00.7957706Z   adding: .git/objects/45/03f4505b6683e7464aa09f886405541e3796ee (stored 0%)
2023-02-17T07:01:00.7959091Z   adding: .git/objects/5d/ (stored 0%)
2023-02-17T07:01:00.7960500Z   adding: .git/objects/5d/36dbf0e405bf9844a0fd655d6e1243253aa267 (stored 0%)
2023-02-17T07:01:00.7961834Z   adding: .git/objects/b2/ (stored 0%)
2023-02-17T07:01:00.7963479Z   adding: .git/objects/b2/c1142fc2d0c0f32664c6a944b17830595a091b (stored 0%)
2023-02-17T07:01:00.7964886Z   adding: .git/objects/ab/ (stored 0%)
2023-02-17T07:01:00.7966467Z   adding: .git/objects/ab/2f7f07bbc8acbcda8cfde9250c7a69e9314742 (stored 0%)
2023-02-17T07:01:00.7967841Z   adding: .git/objects/39/ (stored 0%)
2023-02-17T07:01:00.7969164Z   adding: .git/objects/39/ae185496de820e4248867e50bcf32f60dacd38 (stored 0%)
2023-02-17T07:01:00.7970555Z   adding: .git/objects/a7/ (stored 0%)
2023-02-17T07:01:00.7972022Z   adding: .git/objects/a7/c760536be2fa5ef41e638e5104fda8f00750e5 (stored 0%)
2023-02-17T07:01:00.7973553Z   adding: .git/objects/a7/363de5dc1b453f3c8e6947bc217353b00752f3 (stored 0%)
2023-02-17T07:01:00.7975380Z   adding: .git/objects/a7/7d95efe936d705db8e3c60ee290347f1f70329 (stored 0%)
2023-02-17T07:01:00.7976792Z   adding: .git/objects/08/ (stored 0%)
2023-02-17T07:01:00.7978116Z   adding: .git/objects/08/b6b758dab786f09e95c07b732df7e28d915d25 (stored 0%)
2023-02-17T07:01:00.7979569Z   adding: .git/objects/e8/ (stored 0%)
2023-02-17T07:01:00.7980780Z   adding: .git/objects/e8/54215f9d2b5638648a8cec65a00246f2347a1a (deflated 0%)
2023-02-17T07:01:00.7981998Z   adding: .git/objects/0f/ (stored 0%)
2023-02-17T07:01:00.7983522Z   adding: .git/objects/0f/8d8de3a28a90bc422f581eed557ebfbee5ed5d (deflated 0%)
2023-02-17T07:01:00.7984791Z   adding: .git/objects/83/ (stored 0%)
2023-02-17T07:01:00.7987129Z   adding: .git/objects/83/91ac32361b99449940cf203702bf9d701d0054 (stored 0%)
2023-02-17T07:01:00.7988398Z   adding: .git/objects/f9/ (stored 0%)
2023-02-17T07:01:00.7989947Z   adding: .git/objects/f9/dcf27fcc8fb09418226d133b53961013cdace7 (deflated 0%)
2023-02-17T07:01:00.7991164Z   adding: .git/objects/99/ (stored 0%)
2023-02-17T07:01:00.7992410Z   adding: .git/objects/99/cac4f351117fc6046f31d7ed97531b669692db (stored 0%)
2023-02-17T07:01:00.7993579Z   adding: .git/objects/e4/ (stored 0%)
2023-02-17T07:01:00.7994758Z   adding: .git/objects/e4/858e7a08032f2d716deb437ea6065de8da0b67 (stored 0%)
2023-02-17T07:01:00.7996460Z   adding: .git/objects/4a/ (stored 0%)
2023-02-17T07:01:00.8000204Z   adding: .git/objects/4a/59a386aab59667bb7698934c890c2e71a07587 (stored 0%)
2023-02-17T07:01:00.8001919Z   adding: .git/objects/b6/ (stored 0%)
2023-02-17T07:01:00.8003124Z   adding: .git/objects/b6/e47617de110dea7ca47e087ff1347cc2646eda (stored 0%)
2023-02-17T07:01:00.8004189Z   adding: .git/objects/f8/ (stored 0%)
2023-02-17T07:01:00.8005316Z   adding: .git/objects/f8/3ac56475f80c1c291208e1199e6a5122978ddc (deflated 0%)
2023-02-17T07:01:00.8006379Z   adding: .git/objects/ef/ (stored 0%)
2023-02-17T07:01:00.8007525Z   adding: .git/objects/ef/164e77e64b4e560d403bb11e76b7f225d7bd87 (stored 0%)
2023-02-17T07:01:00.8008699Z   adding: .git/objects/fb/ (stored 0%)
2023-02-17T07:01:00.8010325Z   adding: .git/objects/fb/6372020f6b2d8adbe0409e9070883dd46b1b25 (deflated 0%)
2023-02-17T07:01:00.8012037Z   adding: .git/objects/bd/ (stored 0%)
2023-02-17T07:01:00.8013665Z   adding: .git/objects/bd/8bc9804b96fa74cd037bf0c78da167bf04a182 (stored 0%)
2023-02-17T07:01:00.8014844Z   adding: .git/objects/fa/ (stored 0%)
2023-02-17T07:01:00.8015982Z   adding: .git/objects/fa/5bd0ee76f5f84e808d525e7f3ef5ca32f3c655 (stored 0%)
2023-02-17T07:01:00.8017130Z   adding: .git/objects/b1/ (stored 0%)
2023-02-17T07:01:00.8018216Z   adding: .git/objects/b1/d30182cfa6b36ab3550b225892cea3eb370066 (stored 0%)
2023-02-17T07:01:00.8019309Z   adding: .git/objects/77/ (stored 0%)
2023-02-17T07:01:00.8020525Z   adding: .git/objects/77/7b65d49968cc22e2dcf77a5f654a637d669eb4 (deflated 0%)
2023-02-17T07:01:00.8022085Z   adding: .git/objects/b5/ (stored 0%)
2023-02-17T07:01:00.8023546Z   adding: .git/objects/b5/d13ccb47f65e8b0ad33d977db429cb1c93a388 (stored 0%)
2023-02-17T07:01:00.8025417Z   adding: .git/objects/b5/bd1fbf5d68b04f476a8fc22c7707e1517762bd (stored 0%)
2023-02-17T07:01:00.8026754Z   adding: .git/objects/e5/ (stored 0%)
2023-02-17T07:01:00.8027883Z   adding: .git/objects/e5/e44455777196e68548452b286692bda2d53152 (stored 0%)
2023-02-17T07:01:00.8029260Z   adding: .git/objects/f5/ (stored 0%)
2023-02-17T07:01:00.8030621Z   adding: .git/objects/f5/09905cfb84a29b7d66fa34f044de8ee973958b (stored 0%)
2023-02-17T07:01:00.8031881Z   adding: .git/objects/4c/ (stored 0%)
2023-02-17T07:01:00.8033326Z   adding: .git/objects/4c/4b93a6321e18df3db86f1c5018071268fa50b9 (stored 0%)
2023-02-17T07:01:00.8034634Z   adding: .git/objects/18/ (stored 0%)
2023-02-17T07:01:00.8036396Z   adding: .git/objects/18/338b78e0c4b62e92b0d16c9c794b9cbb2006d5 (deflated 0%)
2023-02-17T07:01:00.8037615Z   adding: .git/objects/b9/ (stored 0%)
2023-02-17T07:01:00.8038805Z   adding: .git/objects/b9/d4c74b23b9a0fa9e9fdf865bf466e3c6de809a (stored 0%)
2023-02-17T07:01:00.8040023Z   adding: .git/objects/2d/ (stored 0%)
2023-02-17T07:01:00.8041246Z   adding: .git/objects/2d/a8b0f3170f8744f88a4fa5c3119e059691574d (deflated 0%)
2023-02-17T07:01:00.8042513Z   adding: .git/objects/info/ (stored 0%)
2023-02-17T07:01:00.8043598Z   adding: .git/objects/c2/ (stored 0%)
2023-02-17T07:01:00.8045043Z   adding: .git/objects/c2/a1710c00e5b24aa8f7a40702ed4b3800fa9f76 (stored 0%)
2023-02-17T07:01:00.8046323Z   adding: .git/objects/78/ (stored 0%)
2023-02-17T07:01:00.8047667Z   adding: .git/objects/78/ab2ee558971c8d63b240c4661fd6824af65506 (stored 0%)
2023-02-17T07:01:00.8048898Z   adding: .git/objects/65/ (stored 0%)
2023-02-17T07:01:00.8050210Z   adding: .git/objects/65/094e518036b822f8c3389b784814fd8dbc8d02 (stored 0%)
2023-02-17T07:01:00.8051578Z   adding: .git/objects/92/ (stored 0%)
2023-02-17T07:01:00.8053101Z   adding: .git/objects/92/ad0996dc472f7182c6a2963f7ac9dba5d74a8e (stored 0%)
2023-02-17T07:01:00.8054177Z   adding: .git/objects/09/ (stored 0%)
2023-02-17T07:01:00.8054975Z   adding: .git/objects/09/41176f648ae9c9c26a1d43f3568930952e902b (stored 0%)
2023-02-17T07:01:00.8056011Z   adding: .git/objects/d0/ (stored 0%)
2023-02-17T07:01:00.8056745Z   adding: .git/objects/d0/6002054cb1000460c86f3f361d9fd62d308438 (stored 0%)
2023-02-17T07:01:00.8057521Z   adding: .git/objects/a0/ (stored 0%)
2023-02-17T07:01:00.8058309Z   adding: .git/objects/a0/27541fa1d934cf9998054bfc3c00ed2f2e49b4 (stored 0%)
2023-02-17T07:01:00.8059227Z   adding: .git/objects/70/ (stored 0%)
2023-02-17T07:01:00.8059959Z   adding: .git/objects/70/a686a1bb91f1601d17ef9c511f54f30fda7c39 (stored 0%)
2023-02-17T07:01:00.8060713Z   adding: .git/objects/5a/ (stored 0%)
2023-02-17T07:01:00.8061460Z   adding: .git/objects/5a/f0d6f80c5fb451596f249dc4f168637b1ab57a (stored 0%)
2023-02-17T07:01:00.8062205Z   adding: .git/objects/79/ (stored 0%)
2023-02-17T07:01:00.8063202Z   adding: .git/objects/79/fe633db0eb88d4e5e99e33b12809cecacdfd9c (stored 0%)
2023-02-17T07:01:00.8063974Z   adding: .git/objects/23/ (stored 0%)
2023-02-17T07:01:00.8064731Z   adding: .git/objects/23/39a84b56e65032d9ac29f872920274c0804ed9 (stored 0%)
2023-02-17T07:01:00.8065477Z   adding: .git/objects/ed/ (stored 0%)
2023-02-17T07:01:00.8066220Z   adding: .git/objects/ed/ed0ff58eb1c02b024f1f969001f45dc9311c61 (stored 0%)
2023-02-17T07:01:00.8067319Z   adding: .git/objects/47/ (stored 0%)
2023-02-17T07:01:00.8068068Z   adding: .git/objects/47/855ef41927e9a9515d29c59a185b5895345933 (stored 0%)
2023-02-17T07:01:00.8068840Z   adding: .git/objects/07/ (stored 0%)
2023-02-17T07:01:00.8069620Z   adding: .git/objects/07/deb766bf044c246a9c116728b46851c11cab65 (deflated 0%)
2023-02-17T07:01:00.8070390Z   adding: .git/objects/24/ (stored 0%)
2023-02-17T07:01:00.8071146Z   adding: .git/objects/24/41ac492ec611c5b84814a55d98adac7dbcb41f (stored 0%)
2023-02-17T07:01:00.8071972Z   adding: .git/objects/01/ (stored 0%)
2023-02-17T07:01:00.8072761Z   adding: .git/objects/01/e2c96425ac2c526b7f3d8794ce8c616980ad30 (deflated 0%)
2023-02-17T07:01:00.8073517Z   adding: .git/objects/12/ (stored 0%)
2023-02-17T07:01:00.8074292Z   adding: .git/objects/12/af1d7191bef9a29b0c1c608de064d48df8f561 (stored 0%)
2023-02-17T07:01:00.8077291Z   adding: .git/objects/pack/ (stored 0%)
2023-02-17T07:01:00.8078347Z   adding: .git/objects/44/ (stored 0%)
2023-02-17T07:01:00.8079156Z   adding: .git/objects/44/fea226a766d06040420feba2f33550841401f2 (stored 0%)
2023-02-17T07:01:00.8080799Z   adding: .git/objects/44/8b19af4f39e54b8bbd757484789a7b9311bdb8 (stored 0%)
2023-02-17T07:01:00.8081663Z   adding: .git/objects/ee/ (stored 0%)
2023-02-17T07:01:00.8082937Z   adding: .git/objects/ee/7596c9d5f0a8632cabb13674f954d50037d2a4 (stored 0%)
2023-02-17T07:01:00.8084006Z   adding: .git/objects/1c/ (stored 0%)
2023-02-17T07:01:00.8084754Z   adding: .git/objects/1c/92fd99b003d1786af59326bc09db97739307c8 (stored 0%)
2023-02-17T07:01:00.8085520Z   adding: .git/objects/3a/ (stored 0%)
2023-02-17T07:01:00.8086773Z   adding: .git/objects/3a/6a2a67a0ad0495c6a51ede83ab905e0ad896d2 (stored 0%)
2023-02-17T07:01:00.8087711Z   adding: .git/objects/3f/ (stored 0%)
2023-02-17T07:01:00.8088482Z   adding: .git/objects/3f/09b15ea4c1c6116f2fa89a1d7af5e90190a175 (stored 0%)
2023-02-17T07:01:00.8089236Z   adding: .git/objects/53/ (stored 0%)
2023-02-17T07:01:00.8090240Z   adding: .git/objects/53/0f5ea3443865cea01c6ec8483812277e97fe18 (deflated 0%)
2023-02-17T07:01:00.8090973Z   adding: .git/index (deflated 46%)
2023-02-17T07:01:00.8091639Z   adding: .git/hooks/ (stored 0%)
2023-02-17T07:01:00.8093115Z   adding: .git/hooks/pre-receive.sample (deflated 40%)
2023-02-17T07:01:00.8094421Z   adding: .git/hooks/prepare-commit-msg.sample (deflated 50%)
2023-02-17T07:01:00.8095192Z   adding: .git/hooks/update.sample (deflated 68%)
2023-02-17T07:01:00.8096258Z   adding: .git/hooks/applypatch-msg.sample (deflated 42%)
2023-02-17T07:01:00.8097416Z   adding: .git/hooks/fsmonitor-watchman.sample (deflated 52%)
2023-02-17T07:01:00.8098463Z   adding: .git/hooks/pre-applypatch.sample (deflated 38%)
2023-02-17T07:01:00.8099659Z   adding: .git/hooks/pre-merge-commit.sample (deflated 39%)
2023-02-17T07:01:00.8100649Z   adding: .git/hooks/pre-rebase.sample (deflated 59%)
2023-02-17T07:01:00.8101973Z   adding: .git/hooks/post-update.sample (deflated 27%)
2023-02-17T07:01:00.8103300Z   adding: .git/hooks/commit-msg.sample (deflated 44%)
2023-02-17T07:01:00.8104421Z   adding: .git/hooks/pre-commit.sample (deflated 45%)
2023-02-17T07:01:00.8105466Z   adding: .git/hooks/pre-push.sample (deflated 50%)
2023-02-17T07:01:00.8106206Z   adding: .git/description (deflated 14%)
2023-02-17T07:01:00.8106907Z   adding: .git/HEAD (stored 0%)
2023-02-17T07:01:00.8107584Z   adding: .git/branches/ (stored 0%)
2023-02-17T07:01:00.8108289Z   adding: .git/FETCH_HEAD (deflated 11%)
2023-02-17T07:01:00.8108924Z   adding: .git/logs/ (stored 0%)
2023-02-17T07:01:00.8109610Z   adding: .git/logs/HEAD (deflated 80%)
2023-02-17T07:01:00.8110307Z   adding: .git/logs/refs/ (stored 0%)
2023-02-17T07:01:00.8110969Z   adding: .git/logs/refs/remotes/ (stored 0%)
2023-02-17T07:01:00.8111667Z   adding: .git/logs/refs/remotes/origin/ (stored 0%)
2023-02-17T07:01:00.8112439Z   adding: .git/logs/refs/remotes/origin/main (deflated 79%)
2023-02-17T07:01:00.8113120Z   adding: .git/info/ (stored 0%)
2023-02-17T07:01:00.8114028Z   adding: .git/info/exclude (deflated 28%)
2023-02-17T07:01:00.8114874Z   adding: .git/refs/ (stored 0%)
2023-02-17T07:01:00.8115486Z   adding: .git/refs/heads/ (stored 0%)
2023-02-17T07:01:00.8116157Z   adding: .git/refs/remotes/ (stored 0%)
2023-02-17T07:01:00.8116892Z   adding: .git/refs/remotes/origin/ (stored 0%)
2023-02-17T07:01:00.8117605Z   adding: .git/refs/remotes/origin/main (stored 0%)
2023-02-17T07:01:00.8118293Z   adding: .git/refs/tags/ (stored 0%)
2023-02-17T07:01:00.8118955Z   adding: .git/config (deflated 27%)
2023-02-17T07:01:00.8119734Z   adding: .github/ (stored 0%)
2023-02-17T07:01:00.8120485Z   adding: .github/workflows/ (stored 0%)
2023-02-17T07:01:00.8121466Z   adding: .github/workflows/python-app.yml (deflated 49%)
2023-02-17T07:01:00.8122353Z   adding: .gitignore (deflated 46%)
2023-02-17T07:01:00.8123265Z   adding: Dockerfile (deflated 31%)
2023-02-17T07:01:00.8123967Z   adding: Housing_price_model/ (stored 0%)
2023-02-17T07:01:00.8124927Z   adding: Housing_price_model/GradientBoostingRegressor.joblib (deflated 70%)
2023-02-17T07:01:00.8126443Z   adding: Housing_price_model/StochasticGradientDescent.joblib (deflated 24%)
2023-02-17T07:01:00.8127798Z   adding: Housing_price_model/LinearRegression.joblib (deflated 18%)
2023-02-17T07:01:00.8128655Z   adding: Housing_price_model/housing.csv (deflated 74%)
2023-02-17T07:01:00.8129469Z   adding: Housing_price_model/Boston_housing_predict.ipynb (deflated 82%)
2023-02-17T07:01:00.8130278Z   adding: Housing_price_model/RidgeCV.joblib (deflated 25%)
2023-02-17T07:01:00.8131072Z   adding: Housing_price_model/California_housing_predict.ipynb (deflated 83%)
2023-02-17T07:01:00.8131789Z   adding: Makefile (deflated 34%)
2023-02-17T07:01:00.8132440Z   adding: README.md (deflated 63%)
2023-02-17T07:01:00.8133088Z   adding: app.py (deflated 57%)
2023-02-17T07:01:00.8134316Z   adding: azure-pipelines-for-self-hosted-agent.yml (deflated 58%)
2023-02-17T07:01:00.8135105Z   adding: hello.py (deflated 35%)
2023-02-17T07:01:00.8135790Z   adding: housing.csv (deflated 74%)
2023-02-17T07:01:00.8136540Z   adding: make_predict_azure_app.sh (deflated 40%)
2023-02-17T07:01:00.8137412Z   adding: make_prediction.sh (deflated 41%)
2023-02-17T07:01:00.8138076Z   adding: requirements.txt (deflated 10%)
2023-02-17T07:01:00.8138764Z   adding: run_docker.sh (deflated 30%)
2023-02-17T07:01:00.8139432Z   adding: run_kubernetes.sh (deflated 41%)
2023-02-17T07:01:00.8140072Z   adding: sc/ (stored 0%)
2023-02-17T07:01:00.8140978Z   adding: sc/project-running.png (deflated 10%)
2023-02-17T07:01:00.8142012Z   adding: sc/batch-readme.png (deflated 14%)
2023-02-17T07:01:00.8143424Z   adding: sc/ouput-logs.txt (deflated 71%)
2023-02-17T07:01:00.8144467Z   adding: sc/build-job.png (deflated 13%)
2023-02-17T07:01:00.8145406Z   adding: sc/makeall.png (deflated 7%)
2023-02-17T07:01:00.8146374Z   adding: sc/build-success.png (deflated 16%)
2023-02-17T07:01:00.8147121Z   adding: sc/arch.png (deflated 82%)
2023-02-17T07:01:00.8148394Z   adding: sc/running-az-pipeservice.png (deflated 11%)
2023-02-17T07:01:00.8149299Z   adding: sc/githubtestpass.png (deflated 18%)
2023-02-17T07:01:00.8150111Z   adding: sc/predection.png (deflated 4%)
2023-02-17T07:01:00.8150787Z   adding: sc/gitclone.png (deflated 7%)
2023-02-17T07:01:00.8151427Z   adding: test_hello.py (deflated 53%)
2023-02-17T07:01:00.8152167Z   adding: upload_docker.sh (deflated 41%)
2023-02-17T07:01:00.8160762Z ##[section]Finishing: myStep 4 - Archive files
2023-02-17T07:01:02.4196430Z ##[section]Starting: myStep 5 - Upload package
2023-02-17T07:01:02.4208032Z ==============================================================================
2023-02-17T07:01:02.4208923Z Task         : Publish pipeline artifact
2023-02-17T07:01:02.4209541Z Description  : Publish a local directory or file as a named artifact for the current pipeline
2023-02-17T07:01:02.4210401Z Version      : 0.141.0
2023-02-17T07:01:02.4210924Z Author       : Microsoft Corporation
2023-02-17T07:01:02.4211538Z Help         : https://docs.microsoft.com/azure/devops/pipelines/tasks/utility/publish-pipeline-artifact
2023-02-17T07:01:02.4212721Z ==============================================================================
2023-02-17T07:01:03.8157141Z Uploading pipeline artifact from /home/devops/myagent/_work/1/a/8.zip for build #8
2023-02-17T07:01:03.8641663Z Using default max parallelism.
2023-02-17T07:01:03.8666870Z Max dedup parallelism: 192
2023-02-17T07:01:11.5640117Z ApplicationInsightsTelemetrySender will correlate events with X-TFS-Session b091a0ed-3f0e-420c-87fe-d6513f80eaea
2023-02-17T07:01:11.5934317Z DedupManifestArtifactClient will correlate http requests with X-TFS-Session b091a0ed-3f0e-420c-87fe-d6513f80eaea
2023-02-17T07:01:11.7892127Z 1 files processed.
2023-02-17T07:01:11.7905912Z Processed 1 files from /home/devops/myagent/_work/1/a successfully.
2023-02-17T07:01:16.6089201Z Uploading 1 files from directory /home/devops/myagent/_work/1/a.
2023-02-17T07:01:16.6092351Z Uploaded 804,210 out of 2,641,927 bytes.
2023-02-17T07:01:17.7244816Z Uploaded 804,386 out of 2,642,103 bytes
2023-02-17T07:01:17.7246265Z Content upload is done!
2023-02-17T07:01:17.7268439Z 
2023-02-17T07:01:17.7270587Z Content upload statistics:
2023-02-17T07:01:17.7273551Z Total Content: 5.3 MB
2023-02-17T07:01:17.7275259Z Physical Content Uploaded: 0.8 MB
2023-02-17T07:01:17.7276994Z Logical Content Uploaded: 0.8 MB
2023-02-17T07:01:17.7278633Z Compression Saved: 9.2 KB
2023-02-17T07:01:17.7280112Z Deduplication Saved: 4.5 MB
2023-02-17T07:01:17.7281637Z Number of Chunks Uploaded: 12
2023-02-17T07:01:17.7283296Z Total Number of Chunks: 106
2023-02-17T07:01:17.7284291Z 
2023-02-17T07:01:19.2071666Z Associated artifact 7 with build 8
2023-02-17T07:01:19.2074248Z ApplicationInsightsTelemetrySender correlated 2 events with X-TFS-Session b091a0ed-3f0e-420c-87fe-d6513f80eaea
2023-02-17T07:01:19.2075442Z Uploading pipeline artifact finished.
2023-02-17T07:01:19.2082150Z ##[section]Finishing: myStep 5 - Upload package
2023-02-17T07:01:20.4592843Z ##[section]Starting: Checkout gurumukh/azure-devops-project@main to s
2023-02-17T07:01:20.4599160Z ==============================================================================
2023-02-17T07:01:20.4599703Z Task         : Get sources
2023-02-17T07:01:20.4600345Z Description  : Get sources from a repository. Supports Git, TfsVC, and SVN repositories.
2023-02-17T07:01:20.4600880Z Version      : 1.0.0
2023-02-17T07:01:20.4601436Z Author       : Microsoft
2023-02-17T07:01:20.4601876Z Help         : [More Information](https://go.microsoft.com/fwlink/?LinkId=798199)
2023-02-17T07:01:20.4602653Z ==============================================================================
2023-02-17T07:01:22.1697930Z Cleaning any cached credential from repository: gurumukh/azure-devops-project (GitHub)
2023-02-17T07:01:22.1844650Z ##[section]Finishing: Checkout gurumukh/azure-devops-project@main to s
2023-02-17T07:01:23.3274228Z ##[section]Starting: Finalize Job
2023-02-17T07:01:23.3310385Z TestResultLogParser: JasmineTestResultParser : Starting jasmine test result parser.
2023-02-17T07:01:23.3311147Z TestResultLogParser: JestTestResultParser : Starting jest test result parser.
2023-02-17T07:01:23.3311910Z TestResultLogParser: MochaTestResultParser : Starting mocha test result parser.
2023-02-17T07:01:23.3314852Z TestResultLogParser: PythonTestResultParser : Starting python test result parser.
2023-02-17T07:01:23.3315940Z TestResultLogParser: PythonTestResultParser : ExpectingTestResults: transitioned to state ExpectingFailedResults at line 66
2023-02-17T07:01:23.7639183Z Cleaning up task key
2023-02-17T07:01:23.7641062Z Start cleaning up orphan processes.
2023-02-17T07:01:23.7999458Z ##[section]Finishing: Finalize Job
2023-02-17T07:01:23.8046836Z ##[section]Finishing: BuildJob
```

## Enhancements

Here are some additional features that we can  consider adding to our project to improve the accuracy of our house price predictions:

* Property characteristics: we could consider including additional features that describe the physical characteristics of the property, such as the number of bedrooms, bathrooms, square footage, lot size, or age of the property.

* Location features: We could include location-based features, e.g. schools, parks, mall), crime rates, and other neighborhood features that might affect property values.

## Demo 
[Click here to watch demo](https://www.youtube.com/watch?v=a6bgs2APn0E)
