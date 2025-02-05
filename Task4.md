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
The GLiNER model exhibited reduced accuracy when transitioning from the Encyclopedia website to the [Collections website](https://collections.qm.org.qa/en/objects?filterOnDisplay=false&pageSize=24).

- The `person` label in collections produced irrelevant extractions. However, modifying it to `human` improved the accuracy by correctly identifying human names. This adjustment was implemented in the latest version of the tool.
- Arabic language accuracy was initially suboptimal. After integrating Arabic-specific features, extraction issues arose, which were resolved by making Arabic labels more precise than their English counterparts.
- The tool is now fully bilingual, supporting both English and Arabic. However, the number of extracted Arabic entities remains lower than English ones due to model accuracy limitations, which could not be further improved.
- Users can modify labels based on their preferences, adding more, removing some, or changing them to more accurate alternatives.

![image](https://github.com/user-attachments/assets/f1e82e1a-d991-435e-b45a-c44a1ca59d48)


### Third Challenge: Useless Visualization for Individual Webpages

Previously, we attempted to visualize the entities for each link visited during the crawling process. For the encyclopedia, this meant each artist had its own CSV file containing the extracted entities, their labels, and occurrences. However, when visualizing this data using word clouds and static graphs, no meaningful insights were found. 
To improve the process, we added code to extract all the entities from the entire website. These entities are now recorded in one CSV file, which includes all visited pages, the extracted entities, their labels, and occurrences.

![image](https://github.com/user-attachments/assets/405afa02-a998-471c-97a1-a7de1b2d744f)

This consolidated CSV file proved useful when we created another tool using the D3.js library to visualize the connections. We developed a simple interface with an upload function that allows users to upload any CSV file in the same format. The interface also includes a filter dropdown box featuring the unique extracted labels from the CSV file. When the CSV file is first uploaded, only the main entities appear (for example, in the encyclopedia case, this means the artist names associated with the pages visited).

![image](https://github.com/user-attachments/assets/72c96390-7066-4e53-ad8b-d1983eed0675)

After filtering—for instance, selecting "person"—the interface displays the extracted person names from each page and their relationships with the main entities (in this case, the artists). For context, the following image shows that Abu Ghazi and Prince Yusuf Kamal—two extracted entities labeled as persons—are linked to the two artists, Mahmoud Said and Mahmoud Mokhtar.

![image](https://github.com/user-attachments/assets/c9859e30-e46d-4142-9260-7c2e3cde3b51)

In another example, when filtering for the "place" label, the interface similarly shows relationships between specific places and the artists. The following image demonstrates that multiple artists are connected to a specific place, Mathaf.

![image](https://github.com/user-attachments/assets/f7cb24f5-746a-47d8-9cf6-f4ccfb82fed6)

The integration of the D3.js visualization tool makes it easy to explore connections between entities in a dynamic and interactive way. Users can upload any CSV with a similar structure, ensuring flexibility across datasets. The relationships between entities are shown clearly, helping users spot patterns and key connections.

One feature allows users to focus on a specific artist—by dragging their name, all unrelated nodes disappear, making it easier to see only the relevant connections. Clicking on the main entities (like artists) takes users directly to their page for more details.

These features make it easier for users to interact with the data, uncovering meaningful insights and improving the overall experience.

### Last Challenge: Encoding and Fonts

In the previous version of the tool, character encoding issues were encountered in the CSV file, word cloud, and static graphs. To resolve this, we applied the `UTF-8-SIG` encoding and used fonts that support the Arabic language. Additionally, we utilized the Python library `arabic_reshaper` to ensure that Arabic letters are properly aligned.

**Before**

![405588687-8cf4d648-408c-42ce-a8f5-791814f160a4](https://github.com/user-attachments/assets/ed6b0dff-df10-472b-8427-43357de880f2)

![image](https://github.com/user-attachments/assets/e1201f6d-1436-429c-b5d9-cf9069b3e4ab)

**After**

![image](https://github.com/user-attachments/assets/e2b1da80-d243-43d8-aa05-f12392dd23e1)

![image](https://github.com/user-attachments/assets/7fb86706-fa5c-4307-a627-0966cee48d2b)



[back](./)
