# Web Scraping with Python

### Requests

- Requests is used to execute HTTP requests.
- The Requests object holds the results of the request. This is not only the page content, but also many other items about the result such as HTTP status codes and headers
- Requests is used __only to get the page__, it does not do any parsing

### Scrapy 

> __Scrapy__ is a very popular open source Python scraping framework for extracting data. It was originally designed for only scraping, but it is has also evolved into a powerful web crawling solution.

###### Notable features

- replaces the need for [requests|urllib3] + BeautifulSoup

- Built-in extensions to make HTTP requests and handle compression, authentication, caching, manipulate user-agents, and HTTP headers

- Built-in support for selecting and extracting data with selector languages such as CSS and XPath, as well as support for utilizing regular expressions for selection of content and links

  - XPath is the native means of  navigating HTML in Scrapy e.g.:

    ```python
    html_content.xpath('h3[@class="eveen-title"]/a/text()').extract_first()
    ```

    

- Encoding support to deal with languages and non-standard encoding declarations

- Flexible APIs to reuse and write custom middleware and piplines, which provide a clean and easy way to implement tasks such as automatically downloading assets (e.g., images or media) and storing data in storage such as file systems, S3, databases, and others

> __Everything in Scrapy revolves around creating a spider__. Spiders crawl through pages on the Internet based upon rules that we provide. 

```python
# example of creating a spider object
import scrapy 

class PythonEventsSpider(scrapy.Spider):
    # define rules
```

