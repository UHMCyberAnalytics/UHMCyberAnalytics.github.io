---
layout: page
title: Getting started
permalink: /getting-started/
---

### Step 1) Make sure you have pip and python installed on your computer.


You must use Python Version 3.11.9, and create a virtual environment

### Step 2) Create your virtual environment

In your terminal run

python3.11 -m venv myenv

followed by

myenv/Scripts/Activate

### Step 3) Install dependencies

To install dependencies you must run 

pip install -r requirements.txt

You must also create a .env file with a Claude API key and a News API key

## At this point, you should be good to run the program by running python main.py