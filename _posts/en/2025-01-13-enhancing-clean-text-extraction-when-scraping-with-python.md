---
layout: post
title: Enhancing Clean Text Extraction when Scraping with Python
categories: programming
author:
  - Carlos A. Planchón
lang: en
---
Web scraping projects consistently face similar text extraction problems. Python's `parsel` library handles XPath and CSS selectors effectively, but recurring issues persist: text encoding errors (e.g., `cafÃ©` instead of `café`), excessive whitespace, and malformed HTML structures that require manual cleanup.

I developed `parsel_text` to address these problems systematically. The library extends `parsel` by integrating `BeautifulSoup` for flexible HTML parsing and `ftfy` for automatic encoding correction. Rather than replacing `parsel`, which remains superior for structured parsing tasks, `parsel_text` provides specialized functionality for extracting clean, normalized text.

### Core improvements

**Encoding correction:** `ftfy` normalizes text automatically, resolving common encoding errors like `cafÃ©` → `café`.

**Whitespace normalization:** Redundant spaces and line breaks are removed without manual `.strip()` or regex operations.

**HTML parsing:** `BeautifulSoup` handles deeply nested or malformed HTML structures more reliably than strict XML parsers.
    

* * *

### Usage

```
from parsel import Selector
from parsel_text import get_xpath_text

html_content = """
<div id="content">
    <p>Hello, world!</p>
    <p>Welcome to the parsel_text library.</p>
</div>
"""

selector = Selector(text=html_content)
text = get_xpath_text(selector, xpath="//p/text()")
print(text)
```

**Output:**

```
Hello, world!
Welcome to the parsel_text library.
```

The library handles text extraction and normalization in a single operation.

* * *

### When to use `parsel_text`

Use `parsel_text` when working with sites that have inconsistent HTML or encoding problems. It's particularly useful for projects that require automated text cleanup across multiple sources.

For well-structured pages with consistent formatting, standard `parsel` remains sufficient. `parsel_text` addresses cases where HTML quality is poor or encoding is unreliable.

* * *

### Performance

`parsel_text` is slower than `parsel` alone due to the additional processing from `BeautifulSoup` and `ftfy`. This tradeoff favors text quality over speed. For large-scale scraping operations where performance is critical, using `parsel` directly may be more appropriate.

* * *

### Additional features

The library includes several utility functions: `get_results_row_text` returns a list of cleaned text from a selector object, `get_bs4_soup_text` extracts text directly from BeautifulSoup objects, and the `fix_mojibake` parameter allows optional control over text correction behavior.

* * *

**References:**

[Official Parsel Documentation](https://parsel.readthedocs.io)

[GitHub Repository](https://github.com/carlosplanchon/parsel_text)