---
layout: post
title:  Building The Tool
---

![img](https://github.com/UHMCyberAnalytics/UHMCyberAnalytics.github.io/blob/3e9e10437d7eaa7b068ca25b9ee5741eb07d39d9/images/pipline.png?raw=true)

## Week 1

In the first week of our project, we discussed which Large Language Model (LLM) we wanted to use in our program. We only needed the LLM to do basic functions and what web scraping tools are best to use. We considered using [Jina AI](https://jina.ai/), [Crawl4AI](https://crawl4ai.com/mkdocs/), and [llama 3.2 3B](https://www.llama.com/).

## Week 2

After discussing which AI models to use with fine-tuning, we decided on [Claude AI](https://www.anthropic.com/claude) along with Crawl4AI. For our first test run, we included only one website to gather information and evaluate whether our project was functioning properly.

## Week 3

Implemented RAG to convert crawled content into a Facebook AI Similarity Search (FAISS) vector database for similarity-based retrieval. We also integrated the News API, allowing us to specify the number of websites our program should analyze for reporting. This eliminates the need for manually searching for news articles and making direct HTTP requests.

This is a raw snippet:

```
hello world
123
This is a text snippet
```

This is a PHP snippet:

```php
<?php
    echo 'Hello, World!';
?>
```

This is a JavaScript snippet:

```js
const add = (a, b) => a + b
const minus = (a, b) => a - b

console.log(add(100,200))  // 300
console.log(minus(100,200))  // -100
```

This is a Python snippet:

```python
def say_hello():
    print("hello world!")

say_hello()   // "hello world!"
```
