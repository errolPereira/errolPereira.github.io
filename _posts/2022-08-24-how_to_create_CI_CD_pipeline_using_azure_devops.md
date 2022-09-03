---
published: true
layout: post
category: 'CI/CD, Azure DevOps, pipelines, Continuous Integration, Continuous Development'
title: How to create simple CI/CD pipeline using Azure DevOps
---
In this post I will show you how to create and setup a simple CI/CD pipeline using Azure DevOps.

[Continuous Integration and Continuous deployement](https://www.simplilearn.com/tutorials/devops-tutorial/continuous-delivery-and-continuous-deployment) aka CI/CD is a concept to reduce the gap or time between developing and deploying an application. 

![CI CD Pipeline]({{site.baseurl}}/images/ci_cd_display_pic.jpg)

Generally, when a developer pushes a new feature to the applications code base, the code is passed through a series of checks to test the quality of the code. Once the test passes the code is then manually compiled and deployed on the server or wherver the deployment environment lies.

This is a manual and time consuming process and CI/CD pipelines aims to automate this process and reduce the time and manual efforts taken after each commit/code push.

In this post we will deploy the Simple Flask API created in this post and setup a CI/CD pipeline on top of it. This pipeline will monitor any changes in the code base and will compile and deploy the API on Azure Web Apps.

After completing this tutorial, you will know:
- Setup Azure Devops Account and repository
- Create Azure Pipelines
- Setup the Azure container registry with pipeline
- Deploy the API on Azure Web Apps

Lets get started!

## 1. Setup Azure DevOps Account

Go to [Azure DevOps](https://azure.microsoft.com/en-in/services/devops/) and click on Star Free. Log in with your gmail account and create and follow all the steps. You will be prompted to create an organization. Give your organization a unique name.

Once the registration is completed you will be redirected to the DevOps home page which will look like the image below.

![CI CD Pipeline]({{site.baseurl}}/images/home_page_devops.png)

Now let us create a repository/project in your organisation which you just created. Create a projeect with the name Simple Flask API and keep the visibility to be private. Click on Create Project button. This will create a project with the name Simple Flask API.

![CI CD Pipeline]({{site.baseurl}}/images/welcome_project_devops.png)

Once you are in your project view on the left you will see Repos. Click on the Repos and it will show you how to import or add codes or files to your repository. The interface is just like the Github. Lets add the Simple Flask API code which we created in this [post](https://errolpereira.github.io/deploy_flask_api_using_docker_container/). Use this [link](https://github.com/errolPereira/blog_resources/tree/main/Flask%20API) to download the code files.

Once you have added the codes in your azure repository you will see an output similar to the one below

![CI CD Pipeline]({{site.baseurl}}/images/azure_simple_flask_api.png)

## 2. Create Azure Pipelines




