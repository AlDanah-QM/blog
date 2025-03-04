---
layout: default
---

## Task 5: Touch, See, Hear: Interactive Museum Experience Prototype

This task involved testing an innovative museum experience that integrates RFID technology to display interactive 3D models of historical artifacts, accompanied by an audio guide in multiple languages. It took seven days and involved the following challenges:

### Challenge 1: Connecting the hardware

As computer science students, one of the challenges we face is working with hardware components like sensors, a topic typically covered in computer engineering rather than our curriculum. However, thanks to my prior experience with sensors and hardware from my senior project, I found it relatively easy to set up the hardware by following a tutorial. The image below illustrates the process of connecting an RFID sensor to a Raspberry Pi.

![image](https://github.com/user-attachments/assets/cefa86c4-f72e-4a47-99ed-e7a42ab2a958)


### Challenge 2: Finding the related libraries 

Two main libraries are required to run the RFID module (MFRC522) on a Rasbary bi:

1- RPi.GPIO - For controlling Raspberry Pi's GPIO pins.
```sh
sudo apt-get install python3-rpi.gpio
```
2- mfrc522 (for handling MFRC522 RFID readers) 
```sh
pip install mfrc522

```

In addition to the previous steps, there was an extra recomended step, which is enable SPI (Serial Peripheral Interface) on the Raspberry Pi using the follwoing:

1- ```sh
sudo raspi-config
```

2- Interfacing Options → SPI → Enable

3- ```sh
sudo reboot
```

- **Evaluating the underlying work** (e.g., determining the author’s date of death and publication status).

- **Assessing digital surrogates** (e.g., checking if digitized versions add creative input or are faithful reproductions).

- **Reviewing metadata considerations** (e.g., determining whether descriptive metadata contains copyrighted elements).


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
