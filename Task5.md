---
layout: default
---

## Task 5: Copy Rights Clearance For Glam-e Lab and QM

This task involved a detailed review of copyright clearance processes, documentation requirements, and the development of an interactive tool to guide users through jurisdiction-specific copyright assessments. The implementation of the user interface and the JavaScript code was straightforward; however, the real challenges lay in the following aspects:

### Challenge 1: Understanding the Legal Language 
One of the primary difficulties in copyright clearance is interpreting legal terminology accurately. Legal documents often contain complex language, technical jargon, and jurisdiction-specific clauses that can be challenging for non-experts to navigate. Misinterpretations can lead to compliance issues, risking copyright infringement or unnecessary restrictions on public domain works. To address this, I worked on simplifying key legal concepts by breaking them down into smaller sections and carefully analyzing their meanings step by step. Additionally, I connected information across different sections of the legal documents to understand how various copyright terms interrelate. This approach helped in making informed decisions regarding copyright status while ensuring legal compliance.


### Challenge 2: QM Document Lacks Detailed Guidelines

The QM copyright documentation lacks detailed guidelines on determining whether a work is in the public domain, under copyright protection, or requires further review. Unlike the Glam-E Lab handbook, which provides comprehensive checklists and decision-making criteria for clearing copyright, the QM documentation offers limited details on these distinctions. The Glam-E Lab handbook presents structured checklists for:

- **Evaluating the underlying work** (e.g., determining the author’s date of death and publication status).

- **Assessing digital surrogates** (e.g., checking if digitized versions add creative input or are faithful reproductions).

- **Reviewing metadata considerations** (e.g., determining whether descriptive metadata contains copyrighted elements).

However, the abundance of information in the Glam-E Lab document can be overwhelming for individuals without legal expertise. The extensive copyright rules across different jurisdictions (UK, US, and EU) add layers of complexity, making it difficult to extract only the necessary details for practical use. To overcome this, I focused on summarizing essential information and structuring it into a step-by-step format that simplifies decision-making for copyright clearance.

### Challenge 3: Creating the mermaid graphs 

For each document, we were required to create Mermaid graphs to visually represent the copyright clearance workflow. This process varied in complexity depending on the document:

- **QM Copyright Flow:** The QM copyright documentation has a relatively simple structure with fewer decision points, making it straightforward to map out. The flowchart visually represents the limited distinctions between public domain, copyright protection, and contractual obligations. [This is the flowchart for QM](https://github.com/AlDanah-QM/copyrightTool/blob/main/QMFlowChart.md).

- **Glam-E Lab Copyright Flow:** The Glam-E Lab documentation contains detailed workflows covering two countries (UK and US) and three checklists. Creating an accurate Mermaid graph required multiple iterations to correctly represent the complex interconnections between these elements. The final graph successfully depicts the relationships between:

  - Copyright expiration rules for the UK and US.

  - Criteria for evaluating digital reproductions.

  - Decision points based on metadata ownership and copyright implications.

This graph serves as a useful reference for navigating the Glam-E Lab copyright clearance process, ensuring that digital collections are handled in compliance with legal standards. [This is the flowchart for Glam-e Lab](https://github.com/AlDanah-QM/copyrightTool/blob/main/GamLabChart.md).

### Conclusion

This task successfully streamlined the copyright clearance process by integrating legal documentation standards with a practical, automated assessment tool. By implementing structured guidelines and an interactive web interface, we have significantly enhanced the efficiency of copyright verification for digital collections. Moving forward, further improvements may include multilingual support and AI-driven assistance to optimize user interactions. [This is the tool preview](https://htmlpreview.github.io/?https://github.com/AlDanah-QM/copyrightTool/blob/main/index.html).




[back](./)
