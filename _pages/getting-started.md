---
layout: page
title: Getting started
permalink: /getting-started/
---

### Step 1) Make sure you have Docker is installed and running

[Docker Install](https://www.docker.com/)

![img]()

### Step 2) Clone the Repository

```
git clone <url>
cd <project-folder>
``` 
### Step 3) Create your virtual environment

In your terminal run
```
python3.11 -m venv myenv
```

followed by:


```
myenv/Scripts/Activate
```
for windows
```
source myenv/bin/activate
```
for mocOS/Linux

### Step 4) Install dependencies

To install dependencies you must run 
```
pip install -r requirements.txt
```

### Step 5) Create .env file

You must also create a .env file with a Claude API key and a News API key

```
NEWS_API_KEY=your_news_api_key = <key here>
ANTHROPIC_API_KEY=your_anthropic_api_key = <key here>
```

## At this point, you should be good to run the program :)
```
python main.py
```

