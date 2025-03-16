---
layout: default
---

## Task 7: RFID Scanner & 3D Model Audio Guide - Power BI Analysis Report

This task was conducted following the development of the system in the previous task to gather user feedback on its engagement and usability in QM. We collected 14 responses from staff members who interacted with the system. The survey covered four languages: English, Arabic, Urdu, and French. The following 11 questions were included:

| # | Question | Type | Required | Options |
|---|----------|------|----------|---------|
| 1 | What is your nationality? | Dropdown Menue | Yes | Select your answer |
| 2 | Please select your gender | Single choice | Yes | Male, Female, Prefer not to say |
| 3 | Please select your age range | Single choice | Yes | 19-24, 25-34, 35-44, 45-54, 55-64, 65-74, 75+ |
| 4 | Which language did you test the audio guide in? | Single choice | Yes | English, Arabic, French, Urdu |
| 5 | How easy was it to use the RFID scanner to access the 3D model? | Single choice | Yes | Very easy, Somewhat easy, Neutral, Somewhat difficult, Very difficult |
| 6 | How clear was the audio guide in terms of quality and comprehension? | Single choice | Yes | Very clear, Somewhat clear, Neutral, Somewhat unclear, Very unclear |
| 7 | Did the audio guide enhance your understanding of the 3D model? | Single choice | Yes | Yes, it provided valuable information; Somewhat, but I wanted more details; Not really, it didn’t add much to the experience; No, it was not helpful |
| 8 | How engaging was the interactive 3D model in addition to the audio guide? | Single choice | Yes | Very engaging, Somewhat engaging, Neutral, Not very engaging, Not engaging at all |
| 9 | How intuitive was the overall experience? | Rating | Yes | Scale of 1-5 |
| 10 | On a scale of 1 to 10, how likely would you recommend this system for use in a museum setting? | Net Promoter Score | Yes | Scale of 1-10 |
| 11 | Why did you give the rating in the previous question? If you rated it lower than 7, what improvements or features would you suggest? | Open-ended text | No | Free text input |

### Data Cleaning & Preparation

To make the dataset more suitable for analysis in Power BI, the following data cleaning steps were performed after loading the responses from Excel:
- Step 1: Removed the following unnecessary columns to streamline the dataset.
  - ID
  - Start Time
  - Completion Time
  - Email
  - Name
  - Last Modified Time

- Step 2: Renamed The following columns for better clarity and consistency.
  - "Please select your gender → Gender"
  - "Which language did you test the audio guide in? → Tested_Language"
  - "How easy was it to use the RFID scanner? → Ease_of_Use"
  - "How clear was the audio guide? → Audio_Clarity"
  - "Did the audio guide enhance understanding? → Enhanced_Understanding"
  - "How engaging was the 3D model? → Engagement"
  - "How intuitive was the experience? → Intuitiveness"
  - "On a scale of 1-10, would you recommend this system? → Recommendation"
  - "Feedback on the system → Feedback"

- Step 3: Converted the following numerical fields to Whole Number type for accurate analysis.
  - Intuitiveness
  - Recommendation

- Step 4: Handled the missing values to maintain data integrity by replacing empty Feedback responses with **No feedback provided**.

### Creating Measures for Analysis

I added this measure *Count of Responses* to ensures all responses are counted, which will be used in creating the charts.

Count_Responses = COUNTROWS(Table1)


### Key Insights from Visualizations

#### A. Overall User Experience (KPIs)

- Average Intuitiveness Score: 4.64 / 5

- Average Recommendation Score: 9.07 / 10

**Conclusion: Most users found the system intuitive and highly recommend it to be used in museums.**

![image](https://github.com/user-attachments/assets/aa49884a-dae7-49b2-ac7b-d0297913a03d)

#### B. Overall User Experience (Ratings)

1- Count of Responses by Intuitiveness:
- Most users (majority) rated the system’s intuitiveness as 5 (highest rating).
- A smaller group rated it 4, and very few rated it 3.
- No ratings below 3, indicating that users generally found the system easy to use and intuitive.

**Conclusion: The system is well-designed and intuitive for most users, but a few lower ratings (3 and 4) suggest there may be minor usability improvements needed**

2- Count of Responses by Recommendation:
- Most users gave a perfect recommendation score of 10, suggesting strong satisfaction.
- A few users rated 8, and a small number rated 6 or below.
- Higher scores dominate the distribution, indicating users are highly likely to recommend the system.

**Conclusion: The system is well-received, with strong recommendation scores, but some users rated it lower (6-8), indicating potential areas for improvement—possibly related to ease of use, engagement, or audio clarity.**

![image](https://github.com/user-attachments/assets/65c654aa-2cbe-4891-b537-a0f6b3294fbb)

#### C. Demographics & Intuitiveness

1- Count of Responses by Age Range and Intuitiveness:
- Users in the 35-44 age range rated intuitiveness mostly as 5, with some giving 4.
- 45-54 age group had a mix of 4 and 5, indicating some variation in experience.
- Younger users (19-24 and 25-34) mostly rated 5, suggesting they found the system intuitive.
- No users rated Intuitiveness below 3, indicating a generally positive experience across all age groups.

**Conclusion: Older users (35-44 and 45-54) still found the system intuitive but had a slightly broader range of ratings. While Younger users (19-24, 25-34) rated the system highly intuitive. Finally, 45-54 age group had more variation (some rated 4)—this group might need better onboarding or usability adjustments to improve their experience.**

2- Sum of Intuitiveness by Gender and Recommendation:
- Female users contributed the highest sum of intuitiveness scores and also had the highest recommendation scores (10).
- Male users also rated intuitiveness high, but their sum of recommendation scores was slightly lower than females.
- Some female users rated lower (5, 8, 9), but most gave 10.
- Male users had a more even spread of recommendation scores, suggesting different user experiences.

**Conclusion: Female users found the system more intuitive and were more likely to recommend it. While male users also rated the system highly, but with slightly more variation in recommendations. Finally, a few lower ratings exist in both genders—potential factors could be ease of use, engagement level, or clarity of instructions.**

![image](https://github.com/user-attachments/assets/882570e7-22f8-43e6-a86d-f65da3a6c5d3)

#### D. Analysis of Intuitiveness

1- Count of Responses by Intuitiveness and Engagement:
- Users who rated Intuitiveness as 5 (highest rating) were also the most engaged, with the majority rating the system as "Very Engaging" (orange).
- Users who rated Intuitiveness as 4 had mixed engagement, with some rating it as "Somewhat Engaging" (blue) and others as "Very Engaging" (orange).
- Users who rated Intuitiveness as 3 had only "Somewhat Engaging" or Neutral ratings, with no "Very Engaging" responses.

**Conclusion: Higher intuitiveness correlates with better engagement—users who found the system intuitive also found it engaging. Where users who rated Intuitiveness as 3 were less engaged, indicating that making the system more intuitive could lead to better engagement. Hence, Improvements in UI/UX, onboarding, or usability enhancements could help users find the system more engaging.**

2- Average Intuitiveness by Tested Language (Pie Chart):
- English and Urdu speakers gave the highest average intuitiveness scores (5.00).
- Arabic speakers rated slightly lower (4.78).
- French speakers had the lowest intuitiveness rating (3.50).

**Conclusion: English and Urdu users found the system the most intuitive—this could be due to better language familiarity or translation accuracy. However, Arabic users rated slightly lower, suggesting minor usability challenges or translation clarity issues. Finally, French users had the lowest average intuitiveness score (3.50)—this indicates a potential need to improve the French version of the system, whether it's the interface, audio clarity, or translation quality.**

![image](https://github.com/user-attachments/assets/08da79e6-1508-4046-8c36-04350e6b572b)

#### E. Analysis of Audio Clarity

1- Count of Responses by Audio Clarity and Recommendation:
- Users who rated the audio as "Very Clear" had the highest recommendation scores, with the majority giving a 10/10 recommendation (purple bar).
- A few users in the "Very Clear" category rated their recommendation as 9 or 8, suggesting minor room for improvement.
- Users who rated the audio as "Neutral" or "Somewhat Clear" had significantly lower recommendation scores, mostly 5 or 8.

**Conclusion: Audio clarity significantly impacts recommendation scores. Users who found the audio "Very Clear" were much more likely to recommend the system highly. Hence, lower clarity ratings correlate with lower recommendations, suggesting improving audio quality can boost user satisfaction.**

2-Count of Responses by Tested Language and Audio Clarity:
- English audio was rated "Very Clear" the most, with a few "Neutral" ratings.
- Arabic users had mostly "Very Clear" ratings, but also some "Somewhat Clear" responses, suggesting minor clarity issues.
- French users had a mix of "Somewhat Clear" and "Neutral" ratings, with fewer "Very Clear" responses.
- Urdu users rated audio clarity well, mostly in the "Very Clear" category.

**Conclusion: English and Urdu users found the audio clarity the best. However, Arabic users mostly rated the audio highly, but there are some "Somewhat Clear" responses, indicating potential improvements needed in pronunciation or audio delivery. Finally, French users rated the audio clarity the lowest—this suggests that the French version of the audio guide may need better translation, pronunciation adjustments, or improved audio quality.**

![image](https://github.com/user-attachments/assets/cf0718e5-efad-40c5-9cd8-f2cd5318761f)

#### F. Engagement and Ease of Use

1- Count of Recommendation by Engagement and Intuitiveness:
- Users who found the system "Very Engaging" gave the highest recommendation scores, with most ratings at 10/10 (orange).
- Users who found the system "Somewhat Engaging" had mixed recommendation scores, with some giving lower ratings (3-4, blue).
- Users who rated engagement as "Neutral" had lower recommendation scores, indicating a direct link between engagement and willingness to recommend.

**Conclusion: Engagement strongly influences recommendation scores. Users who were highly engaged were also much more likely to recommend the system at 10/10. However, lower engagement correlates with lower recommendations, suggesting that improving the interactive experience could boost recommendation scores further. Finally, users with lower intuitiveness ratings (3-4) also tended to rate engagement and recommendation lower, reinforcing the importance of system usability and engagement features.**

2- Count of Engagement by Ease of Use:
- Users who found the system "Very Easy" to use had the highest engagement levels.
- Engagement drops significantly when users rated Ease of Use as "Somewhat Easy."

**Conclusion: Ease of Use is a major factor in user engagement. Users who found the system very easy to use were also the most engaged. However, a slight difficulty in using the system led to a noticeable drop in engagement. Thus, improvements in ease of use (e.g., better onboarding, clearer instructions, or UI enhancements) could help maintain high engagement across all users.**

![image](https://github.com/user-attachments/assets/80a9dc40-9197-4526-9171-7a58a77292b0)

#### G. Feedback

- Users who rated Intuitiveness as 5 mostly gave a Recommendation score of 10.
  - Most of these users did not leave additional feedback, suggesting they were satisfied.
  - Some users left positive comments like "Amazing experience", "I love this <3", and "Clarity improvement".
- Users who rated Intuitiveness as 4 had varied recommendations (8-10).
  - One user suggested "Tune of the audio guide should be adapted to feel friendlier."
  - Another mentioned "Glitch stuff, level of language should be easier for other ages and public."
- The lowest-rated Intuitiveness score (3) had the lowest recommendation (5).
  - The feedback given is unclear but might indicate dissatisfaction or confusion.

**Conclusion: Users who found the system highly intuitive (5) were more likely to recommend it and had fewer complaints. Moreover, some users still suggested minor improvements (e.g., clarity of audio, glitch fixes, and more language options). Also, users with an Intuitiveness score of 4 raised concerns about audio friendliness and system glitches. Finally, the user who rated Intuitiveness as 3 and Recommendation as 5 might have had a poor experience, but their feedback is unclear.**

![image](https://github.com/user-attachments/assets/6779e64f-bacd-4d1d-a53d-dcaf296f118f)

### Conclusion & Recommendations

The RFID Scanner & 3D Model Audio Guide system was well-received, with most users rating Intuitiveness as 5 and Recommendation as 10, confirming its effectiveness in a museum setting. A strong correlation was found between Ease of Use and Engagement—users who rated the system "Very Easy" had the highest interaction levels.
However, audio clarity impacted user satisfaction, with French and some Arabic users rating it lower. Minor usability issues were noted, particularly among those who rated Ease of Use as “Somewhat Easy”, leading to lower engagement.
Additionally, a few users reported system glitches and suggested language level adjustments. Expanding language support could further enhance accessibility and inclusivity for diverse museum visitors.

Thus, the following recommendations should be considered for future enhancments:

#### 1. Improve Audio Clarity & Language Adaptation:

- Optimize audio quality for French and Arabic users, ensuring clear pronunciation and volume consistency.
- Adjust the tone of the audio guide to be more engaging and friendly, as suggested by some users.
- Expand language support by including additional languages to accommodate a more diverse audience.
- Test the system in different linguistic and cultural contexts to ensure it meets the needs of a global audience.

#### 2. Enhance System Usability & Engagement:

- Refine the RFID scanning process to make it even smoother and more intuitive.
- Provide a quick onboarding guide (e.g., on-screen prompts or a short tutorial) to assist first-time users.
- Improve 3D model interactivity, ensuring smoother controls for zooming, rotating, and synchronizing the audio guide with the visual model.
- 

#### 3. Address Glitches & Stability Issues

- Investigate reported system glitches and conduct further testing to enhance stability and responsiveness.
- Optimize UI design for accessibility, particularly for older users (45-54 age group) who had more variation in intuitiveness ratings.

#### 4. Personalizing the Audio Guide Experience

To enhance user engagement and improve the educational value of the audio guide, the RFID bracelets can be utilized to store and adapt user information for a more tailored experience.
- Age-Based Adaptation: Adjust the tone, complexity, and vocabulary of the audio guide based on the user’s age group, ensuring that younger audiences receive simpler explanations while adults receive more detailed insights.
- Knowledge Level Tracking: Allow users to select or input their level of knowledge (e.g., beginner, intermediate, expert) so the system can provide more tailored and relevant information during the experience.
- Personalized Follow-Ups: Enable the bracelets to store user contact details (e.g., email or phone number) to send additional information about the objects they viewed, relevant historical insights, or museum event invitations.
- Data-Driven Insights: Use collected user data to analyze visitor engagement trends, helping the museum refine content and improve future exhibits.


In conclusion, the following link has the survey [form](https://forms.office.com.mcas.ms/Pages/DesignPageV2.aspx?origin=NeoPortalPage&subpage=design&id=q_hkVYnFTUqMnhNUgAr8cYQM0E4QuMlIgZW7K0JkdzhURFozQlM1UllDRzJGRkdOVkNKS0MwRTRYRi4u)

[back](./)
