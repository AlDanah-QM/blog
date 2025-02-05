---
layout: default
---

## Task 4: Web Crawling and Scraping Task - Second Part

This task required more working days to complete compared to the previous one. Enhancing details in the code proved to be more challenging than writing it from scratch. Throughout this process, we encountered multiple challenges, but by working as a team and effectively dividing tasks, we successfully overcame them.

### First Challenge: Customized code for QM
Last week, we encountered a challenge due to the inconsistent HTML structure of the Encyclopedia website. Despite this, we successfully extracted the "BIO" sections from all pages of the [Encyclopedia of Modern Art website](https://www.encyclopedia.mathaf.org.qa/). This solution effectively customized the tool for QM, specifically for the encyclopedia website.

However, to make the tool more adaptable for multiple websites, we decided to incorporate user input. This enhancement allows users to specify their extraction preferences, such as: 

- **Choose between:**  
  - Whole website scraping  
  - Single-page scraping  
- **Define the type of website being scraped:**  
  - Encyclopedia  
  - Collection   
- **Specify the starting and ending sentences for targeted extraction**  

**Benefits:**  
- Enhances versatility, allowing the tool to work on multiple websites beyond the Encyclopedia of Modern Art.
- Ability to adjust extracted labels based on website type:  
  - *Encyclopedia:* `person`, `place`, `date`, `country`, `city`  
  - *Collection:* `material`, `era`, `date`, `human`, `country`

  ![image](https://github.com/user-attachments/assets/aa96c3f2-4107-484b-9163-858e77f07bec)


### Second Challenge: Accuracy of the GliNER Model
second_challenge:
  title: "Accuracy of the GLiNER Model"
  description: "The GLiNER model exhibited reduced accuracy when transitioning from the Encyclopedia website to the Collections website."
  issues:
    - label_extraction:
        problem: "'person' label in collections produced irrelevant extractions."
        solution: "Changed to 'human', improving accuracy by correctly identifying human names."
    - arabic_language_accuracy:
        problem: "Initial accuracy was suboptimal."
        solution: "Integrated Arabic-specific features and refined Arabic labels to be more precise than English ones."
    - bilingual_support:
        status: "Fully bilingual, supporting both English and Arabic."
        limitation: "Arabic entity extraction remains lower than English due to model accuracy constraints, with no further possible enhancements."


### Web Scrapping

Using the collected URLs, we scraped the biography sections by locating the content between the "Biography" and "Exhibitions" headers. Inconsistent HTML structures across the website necessitated writing custom extraction logic for specific page layouts. Extracted content was processed for further analysis and entity recognition.


### Entity Recognition



[back](./)
