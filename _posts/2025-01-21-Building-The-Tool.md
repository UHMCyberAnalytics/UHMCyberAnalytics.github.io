---
layout: post
title:  Building The Tool
---

![img](https://github.com/UHMCyberAnalytics/UHMCyberAnalytics.github.io/blob/6d2d34b49c5748fb5d196497c70102259ceffbb8/images/pipline.png?raw=true)

## Week 1

In the first week of our project, we discussed which Large Language Model (LLM) we wanted to use in our program. We only needed the LLM to do basic functions and what web scraping tools are best to use. We considered using [Jina AI](https://jina.ai/), [Crawl4AI](https://crawl4ai.com/mkdocs/), and [llama 3.2 3B](https://www.llama.com/).

## Week 2

After discussing which AI models to use with fine-tuning, we decided on [Claude AI](https://www.anthropic.com/claude) along with Crawl4AI. For our first test run, we included only one website to gather information and evaluate whether our project was functioning properly.

AI Analysis with our LLM which is Claude in this case:

```python
async def analyze_with_claude(query: str, context: list[str]):
    client = AsyncAnthropic(api_key=os.getenv("ANTHROPIC_API_KEY"))
    context_str = "\n\n".join(context)
    prompt = f"Based on this context:\n{context_str}\n\nAnswer this query: {query}"
    message = await client.messages.create(model="claude-3-5-sonnet-20241022", max_tokens=1000, messages=[{"role": "user", "content": prompt}])
    return message.content[0].text
```


## Week 3

Implemented RAG to convert crawled content into a Facebook AI Similarity Search (FAISS) vector database for similarity-based retrieval. We also integrated the News API, allowing us to specify the number of websites our program should analyze for reporting. This eliminates the need for manually searching for news articles and making direct HTTP requests.


Fetching News Articles:

```python
async def get_news_articles(query: str, num_articles: int = 5):
    try:
        articles = newsapi.get_everything(q=query, language='en', sort_by='relevancy', page_size=num_articles)
        return articles.get('articles', [])
    except Exception as e:
        print(f"News API error: {e}")
        return []
```
RAG Pipeline Setup:

```python
def setup_rag(content: str):
    text_splitter = RecursiveCharacterTextSplitter(chunk_size=1000, chunk_overlap=200)
    chunks = text_splitter.split_text(content)
    embeddings = HuggingFaceEmbeddings(model_name="all-MiniLM-L6-v2", model_kwargs={'device': 'cpu'}, encode_kwargs={'normalize_embeddings': False})
    return FAISS.from_texts(chunks, embeddings)
```


## Week 4

This is the chatbot interface we developed for querying threat intelligence about hackers from specific regions. It provides categorized, detailed insights on groups like APT1, APT3, and APT41.

![img](https://github.com/UHMCyberAnalytics/UHMCyberAnalytics.github.io/blob/6d2d34b49c5748fb5d196497c70102259ceffbb8/images/main.png?raw=true)

## Week 5

The chart below visualizes Google search trends over the past year for the keyword "hackers" across several countries, including China, Russia, North Korea, and Iran. This helps us understand public interest patterns and potential spikes in cyber-related activity.

![img](https://github.com/UHMCyberAnalytics/UHMCyberAnalytics.github.io/blob/6d2d34b49c5748fb5d196497c70102259ceffbb8/images/trends.png?raw=true)



