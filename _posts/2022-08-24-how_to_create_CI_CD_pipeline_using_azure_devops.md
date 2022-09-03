---
published: true
layout: post
category: 'CI/CD, Azure DevOps, pipelines, Continuous Integration, Continuous Development'
title: How to create simple CI/CD pipeline using Azure DevOps
---
In this post I will show you how to create and setup a simple CI/CD pipeline using Azure DevOps.

Continuous Integration and Continuous deployement aka CI/CD is a concept to reduce the gap or time between developing and deploying an application. 

![CI CD Pipeline]({{site.baseurl}}/images/ci_cd_display_pic.jpg)

Generally, when a developer pushes a new feature to the applications code base, the code is passed through a series of checks to test the quality of the code. Once the test passes the code is then manually compiled and deployed on the server or wherver the deployment environment lies.

This is a manual and time consuming process and CI/CD pipelines aims to automate this process and reduce the time and manual efforts taken after each commit/code push.

In this post we will deploy the Simple Flask API created in this post and setup a CI/CD pipeline on top of it. This pipeline will monitor any changes in the code base and will compile and deploy the API on Azure Web Apps.

After completing this tutorial, you will know:
- Setup Azure Devops Account and repository
- Create Azure container registry
- Create Azure Pipelines
- Setup the Azure container registry with pipeline
- Deploy the API on Azure Web Apps

Lets get started!

