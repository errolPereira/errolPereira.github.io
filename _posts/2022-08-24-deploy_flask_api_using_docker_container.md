---
published: true
layout: post
title: How to deploy Simple Flask API in Docker Container
publish: true
---
In this post, I will guide you in deploying a simple flask API in a docker container.

After completing this tutorial, you will know:
- Create and test a simple Flask API
- Create Dockerfile
- Create Docker image of the application using the Dockerfile
- Create  container to run the application

![docker_blog_image]({{site.baseurl}}/images/docker_blog_image.jpg)
<center><a href='https://www.freepik.com/vectors/import'>Import vector created by freepik - www.freepik.com</a></center>

## Creating and testing a Simple Flask API

The first thing that we will need is a Flask API application that will receive requests from the client and will return an acknowledgement once the request has been received.

I have already created a simple API that does the things I have mentioned above. You can clone the repository from [here](https://github.com/errolPereira/blog_resources/tree/main/Flask%20API).

Change the directory to Flask API and run the below command to run your API in your local environment.

<p style="background-color:#f2f2f2; padding:10px;"><code>cd Flask API</code></p>
<p style="background-color:#f2f2f2; padding:10px;"><code>pip install -r requirements.txt</code></p>
<p style="background-color:#f2f2f2; padding:10px;"><code>python3 app.py</code></p>

![Flask local run]({{site.baseurl}}/images/Flask_API_run_page.png)

You should now see the above output in your console. Great! It means that the API is running in your local environment. It's time to test out our API. We will use an API testing application known as Postman for this. If you have not already installed it, you can install it [here](https://www.postman.com/downloads/).

Open the application and create a new tab, then paste the below URL into the tab.

<p style="background-color:#f2f2f2; padding:10px;"><code>http://127.0.0.1:5005/apirequest</code></p>

![Flask local run]({{site.baseurl}}/images/postman_home_page.png)

Let's breakdown the URL:
1. **http://127.0.0.1**-This is the local URL or local host on which our API is deployed.
2. **5005** : This is the port on which the API is deployed on
3. **/apirequest** - This is the endpoint of the API. Basically, this means which part of the application should I hit to get the relevant response from the API. An API can have multiple endpoints.

Apart from this, an API can also have a body to pass additional input to the application to get the desired result. To learn more about APIs, please read this [awesome blog](https://realpython.com/api-integration-in-python/).

Click on the send button and you should get a response from the API similar to "Hello from the FLASK GET API"

## Creating Dockerfile for the API

Great! We have our API created and tested and ready for deployment. We need to deploy this API on a docker container. For this we will first need to create a docker image of our application. If  you do have docker installed in your system, please follow the instructions on their [offlicial website](https://docs.docker.com/engine/install/) and get it installed.

Once docker is installed use the below comman to create a docker image of the API.

<p style="background-color:#f2f2f2; padding:10px;"><code>docker build -t flask_docker_image .</code></p>

![Docke Build]({{site.baseurl}}/images/docker_build.png)

This will go ahead and install all the dependencies required to run our application into the docker image and will create a new image with the name flask_docker_image.

To verify whether an image has been created or not run the below command

<p style="background-color:#f2f2f2; padding:10px;"><code>docker image ls.</code></p>

![Docke Image]({{site.baseurl}}/images/image ls.png)

Now that our image is created, time to create a docker container and deploy our application on that container.

Run the below command to create a docker container instance of your image.

<p style="background-color:#f2f2f2; padding:10px;"><code>docker run --name flask_container -p 5000:5000 flask_docker_image</code></p>

You should be able to see a similar output as we saw while running our model on the local system.

![Docke Deployed API]({{site.baseurl}}/images/deployed_api.png)


Now you can go ahead and test your API again using Postman. You should be able to see a similar response. But this time your API is running on a docker container instance rather than your local system.

Refrences:
- [Docker Official Documentation](https://docs.docker.com/engine/reference/commandline/run/)



