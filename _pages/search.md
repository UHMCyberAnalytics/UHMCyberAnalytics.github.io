---
layout: page
title: Search
permalink: /search/
---

<div id="search-container">
    <input type="text" id="search-input" placeholder="Search through the blog posts...">
    <ul id="results-container"></ul>
</div>

<script src="{{ site.baseurl }}/assets/simple-jekyll-search.min.js" type="text/javascript"></script>

<script>
    SimpleJekyllSearch({
        searchInput: document.getElementById('search-input'),
        resultsContainer: document.getElementById('results-container'),
        searchResultTemplate: `
            <div style="text-align: left !important;">
                <a href="{url}"><h1 style="text-align:left !important;">{title}</h1></a>
                <span style="text-align:left !important;">{date}</span>
                <p>{excerpt}</p>
            </div>
        `,
        json: '{{ site.url }}{{ site.baseurl }}/search.json',
        filter: function(results, query) {
            query = query.toLowerCase();
            return results.filter(function(item) {
                const titleMatch = item.title.toLowerCase().includes(query);
                const contentMatch = item.content ? item.content.toLowerCase().includes(query) : false;
                return titleMatch || contentMatch;
            });
        },
        templateMiddleware: function(prop, value) {
            if (prop === 'excerpt') {
                const query = document.getElementById('search-input').value.toLowerCase();
                const content = (value || "").toLowerCase();
                const index = content.indexOf(query);
                if (index !== -1) {
                    const start = Math.max(0, index - 50);
                    const end = Math.min(content.length, index + query.length + 50);
                    return '...' + content.slice(start, end) + '...';
                }
                return 'No preview available.';
            }
            return value;
        }
    });
</script>
