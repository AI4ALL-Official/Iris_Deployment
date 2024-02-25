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




## [Download GRAB](https://github.com/glickmac/GRAB/raw/master/GRAB.zip)

#### Unzip GRAB and CD into Directory

```
unzip GRAB.zip
cd GRAB
```

#### Other installations (Git)

```
git clone https://github.com/glickmac/GRAB
```

