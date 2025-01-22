---
layout: default
---

## Task 3: Web Crawling and Scraping Task - Fisrt Part

The task took seven working days to complete—five from this week and two from the previous week. While I had no prior experience with data crawling and scraping, we were fortunate to discover the GLiNER model, which supports multiple languages and provides acceptable accuracy. Leveraging this tool made the process much more manageable. My experience in Python programming proved invaluable, as it allowed me to efficiently implement and adapt the model to meet the project requirements.

Despite the advantage of using the GLiNER model, the intricate structure of the target datasets still posed significant challenges. Tracing relationships between data points and understanding the underlying patterns required considerable effort and problem-solving. One notable difficulty we faced was stemming nationalities to their respective countries. Traditional stemming libraries are designed primarily for returning the root of verbs, which meant they were not suitable for this task. To address this, we had to develop a customized function to map nationalities accurately to their corresponding countries.

Additionally, extracting specific sections of the web pages proved challenging due to the inconsistent HTML structure across the website. This inconsistency required us to design tailored scraping solutions for different page layouts to ensure accurate data extraction. Despite these hurdles, we successfully extracted the "BIO" sections from all pages of the [Encyclopedia of Modern Art website](https://www.encyclopedia.mathaf.org.qa/).

The following sections include screenshots and detailed descriptions of the methodology, tools, and outputs.

### Website Crawling 

We implemented a web crawler using Python's `requests` and `BeautifulSoup` libraries to navigate through the website. The crawler identified and collected all URLs containing `/bios/Pages`, which indicated biography pages. The URLs were stored for further processing, and the crawler avoided redundant or irrelevant links by filtering based on predefined criteria.


### Web Scrapping

Using the collected URLs, we scraped the biography sections by locating the content between the "Biography" and "Exhibitions" headers. Inconsistent HTML structures across the website necessitated writing custom extraction logic for specific page layouts. Extracted content was processed for further analysis and entity recognition.


### Entity Recognition

To identify entities like names, countries, dates, and cities, we used the GLiNER model pre-trained on multilingual datasets. The model accurately extracted entities, which were then categorized into groups. For example:
- **People:** Excluding common pronouns.
- **Countries:** Processed using a customized function, `is_it_a_nationality`, to map nationalities to countries.
- **Dates:** Extracted and sorted by year.

The `is_it_a_nationality` function leveraged a CSV file containing country names and demonyms to identify and map nationalities accurately, addressing the limitations of standard stemming libraries.

### Data Organization

Entities were organized into CSV files, capturing their occurrences across the dataset. For each biography page, we saved the locations (links), extracted entities, their types, and their frequencies. The CSV files served as input for generating visualizations and word clouds.


### Visualization

We created word clouds from the extracted data to visualize the frequency of entities. The `generate_word_cloud` function read the entity-frequency pairs from the CSV files and generated word clouds using the WordCloud library. These visualizations highlighted the prominence of specific names, countries, and dates across the dataset.


[back](./)
