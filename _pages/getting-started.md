---
layout: page
title: Getting started
permalink: /getting-started/
---
### Step 1) Download the "Ollama" repository on our GitHub

[GitHub Repo](https://github.com/UHMCyberAnalytics/modern)

### Step 2) Make sure you have Docker is installed and running

[Docker Install Link](https://www.docker.com/)

![img](https://github.com/UHMCyberAnalytics/UHMCyberAnalytics.github.io/blob/27f77cfa88c0a3a7ad1aae000bb2cf8a1ff83994/images/Docker.png?raw=true)

### Step 3) Open Terminal and Build Docker Container

##### Locate the GitHub repo you just downloaded in terminal and make you way towards the streamlit_app folder


locate the streamlit_app folder then follow these commands
```
cd streamlit_app
docker-compose up -d --build
```
It should look like this after running the commands
![img](https://github.com/UHMCyberAnalytics/UHMCyberAnalytics.github.io/blob/27f77cfa88c0a3a7ad1aae000bb2cf8a1ff83994/images/DockerFin.png?raw=true)

### Step 4) Open New Build Container

![img](https://github.com/UHMCyberAnalytics/UHMCyberAnalytics.github.io/blob/70ef86856f62a5d34e06d3a1aa867948a7c43efd/images/open%20container.png?raw=true)

Click open container and it should look like this. Then open the local host link
![img](https://github.com/UHMCyberAnalytics/UHMCyberAnalytics.github.io/blob/27f77cfa88c0a3a7ad1aae000bb2cf8a1ff83994/images/open%20local%20host.png?raw=true)

### Step 5) Input Keys and Model

After Inputting the model and keys you are now able to use the program
![img](https://github.com/UHMCyberAnalytics/UHMCyberAnalytics.github.io/blob/212ae5406a6e7ce6a4522bc7b8fc9304462e291f/images/input%20keys.png?raw=true)

![img](https://github.com/UHMCyberAnalytics/UHMCyberAnalytics.github.io/blob/212ae5406a6e7ce6a4522bc7b8fc9304462e291f/images/input%20model.png?raw=true)

### Closing the Program

To close the Docker program just type the following in your terminal
```
docker-compose down
```


