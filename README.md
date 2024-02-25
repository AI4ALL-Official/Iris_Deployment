# Iris Deployment

![Python](https://img.shields.io/badge/python-v3.9.5-blue.svg)
![Contributions welcome](https://img.shields.io/badge/contributions-welcome-orange.svg)
[![GitHub issues](https://img.shields.io/github/issues/glickmac/GRAB.svg)](https://github.com/glickmac/GRAB/issues)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)


This application is designed to deploy a random forest algorithm to predict iris subtype based on user slider input using StreamLit. 



<p align="center"><img src="https://github.com/AI4ALL-Offical/Iris_Deployment/blob/main/images/Screenshot.png" width=60%></p>


## Table of Contents
[What is deployment?](#intro)    
[Why is model deployment important?](#importance)    
[Deployment Workflow](#workflow)    
[Quickstart](#quickstart)    
[Building your own StreamLit Deployable Model](#install)       

## <a name="intro"></a>What is deployment?

Model deployment is how you can share your developed model with others. There are industrial solutions, environmental containers, and more localized solutions.

## <a name="importance"></a>Why is model deployment important?

Model deployment is critical for collaborative development and testing. It is also important for distribution of a model to a broader audience. 

## <a name="workflow"></a>Deployment Workflow

<p align="center"><img src="https://github.com/AI4ALL-Offical/Iris_Deployment/blob/main/images/Deployment.png" width=60%></p>


### Types of Deployments

Below are different methods other than StreamLit to deploy ML models

#### Raw Files

Saving trained machine learning models as an **H5**, **pkl**, or **sav** file to be loaded into the environment by another user

#### Containerized Environment

Building a machine learning model and deploying the whole environment including the model itself as a **Docker** container. 

#### Web Application Framework

Building the model into a web application is a common method for deploying a model and is essentially what is happening in this **StreamLit** pipeline. Other python methods to build applications include **Django** and **Flask**. 

#### Hosting Services

Once a model is saved or built into a web application framework, cloud-based methods like Heroku, AWS Sagemaker, or StreamLit are needed to host the application and allow external users the ability to interact with the model. 
   

## <a name="install"></a>Building your own StreamLit Deployable Model

For this assignment, you will be forking this repository into your GitHub and connecting it with StreamLit to deploy the model on your own account. 
1. To start fork this repository into your own GitHub account.
2. Sign up for an account on [StreamLit](https://streamlit.io/)
3. Link StreamLit to your GitHub Account <p align="center"><img src="https://github.com/AI4ALL-Offical/Iris_Deployment/blob/main/images/Link.png" width=60%></p>
4. Build a new application by selecting "New App" <p align="center"><img src="https://github.com/AI4ALL-Offical/Iris_Deployment/blob/main/images/Build.png" width=60%></p>
5. Create a new application by selecting the proper repository from the dropdown: <p align="center"><img src="https://github.com/AI4ALL-Offical/Iris_Deployment/blob/main/images/Create.png" width=60%></p>
6. Make sure to change the Main File Path from "streamlit_app.py" to "app.py" <p align="left"><img src="https://github.com/AI4ALL-Offical/Iris_Deployment/blob/main/images/Error.png" width=40%></p><p align="right"><img src="https://github.com/AI4ALL-Offical/Iris_Deployment/blob/main/images/Change.png" width=40%></p>
7. You can choose a custom URL name for the application
8. Wait for the application to build









## [Download Iris Deployment](https://github.com/AI4ALL-Offical/Iris_Deployment/archive/refs/heads/main.zip)

To run this locally:
#### Unzip Iris Deployment and CD into Directory

```
unzip Iris_Deployment-main.zip
cd Iris_Deployment-main
```

Install StreamLit Locally (assuming you have python and pip)

```
pip install streamlit
```
Run the application by running the app.py file

```
streamlit run app.py
```

You may need to copy and past ```http://localhost:8501``` into a browser if it does not automatically open up a tab. 

