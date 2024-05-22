# Devops Assignment
---

## Github repo guide

* Added Two branches to simplify all the task codes.

* There are two branch for `simple-python-code` build and test pipeline task and `Flask-api` build and deploy task named as `python` and `flask` respectively.

* Each branch has the code for the different task.

* `main` Branch contains the Readme and the screenshots of the tasks. Also added other branches code in two folders, however to run and test codes, need to checkout respective branches. 

---

### Documentation and task screenshots

1. Screenshot of Installation and integration of plugins on jenkins.

![Installationofjenkins](ScreenShots/Installationofjenkins.png)

2. Create freestyle Jenkins job to download code from Git

![jenkinJobToFetchGitRepo01](ScreenShots/jenkinJobToFetchGitRepo01.png)

Console output after successfull fetch
![JenkinsJobToFetchGitRepoLog01](ScreenShots/JenkinsJobToFetchGitRepoLog01.png)

3. Create pipeline to build and test basic python code
- FetchPythonCodeToBuildAndTest
![FetchPythonCodeToBuildTest](ScreenShots/FetchPythonCodeToBuildTest.png)
- Test Case passed logged messages
![PythonCodeTestCasesLogs](ScreenShots/PythonCodeTestCasesLogs.png)

- Pipeline script for the above
![PipelineScriptToBuildTestPythonCode01](ScreenShots/PipelineScriptToBuildTestPythonCode01.png)
![PipelineScriptToBuildTestPythonCode02](ScreenShots/PipelineScriptToBuildTestPythonCode02.png)

3. Create freestyle Jenkins pipeline to build and deploy a restful Flask API using Docker
- Pipeline Script
![PipelineScriptToBuildDeployFlaskApiOnDocker](ScreenShots/PipelineScriptToBuildDeployFlaskApiOnDocker.png)

- FlaskApi Deployed on Docker Success Logs 
![FlaskApiDeployedSuccessLog01](ScreenShots/FlaskApiDeployedSuccessLog01.png)
![FlaskApiDeployedSuccessLog02](ScreenShots/FlaskApiDeployedSuccessLog02.png)
![FlaskApiDeployedSuccessLog03](ScreenShots/FlaskApiDeployedSuccessLog03.png)

- Docker Container Screenshot
![flaskApiDocker](ScreenShots/flaskApiDocker.png)

---
