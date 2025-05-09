---
layout: page
title: Getting started
permalink: /getting-started/
---
### Step 1) Download the "Ollama" repository on our GitHub

[GitHub Repo](https://github.com/UHMCyberAnalytics/modern)

### Step 2) Make sure you have Docker is installed and running

[Docker Install Link](https://www.docker.com/)

![Docker](../images/Docker.png)

### Step 3) Open Terminal and Build Docker Container

##### Locate the GitHub repo you just downloaded in terminal and make you way towards the streamlit_app folder


locate the streamlit_app folder then follow these commands
```
cd streamlit_app
docker-compose up -d --build
```
It should look like this after running the commands
![Docker](../images/DockerFin.png)

### Step 4) Open New Build Container

![container](../images/open container.png)

Click open container and it should look like this. Then open the local host link
![local host](../images/open local host.png)

### Step 5) Input Keys and Model

After Inputting the model and keys you are now able to use the program
![input](../images/input keys.png)


![input](../images/input model.png)

### Closing the Program

To close the Docker program just type the following in your terminal
```
docker-compose down
```


