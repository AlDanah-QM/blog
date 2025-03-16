---
layout: default
---

# **Task 5: Touch, See, Hear – Interactive Museum Experience Prototype**  

This task involved developing and testing an **innovative museum experience** that integrates **RFID technology** to display **interactive 3D models** of historical artifacts, accompanied by an **audio guide** in multiple languages. The project spanned **seven days** and presented several challenges, which we successfully addressed.

---

## **Challenges and Solutions**  

### **Challenge 1: Connecting the Hardware**  
As **computer science students**, working with **hardware components** such as sensors was unfamiliar territory, as this is typically covered in **computer engineering** courses. However, my prior experience with **hardware and sensors** during my senior project made it easier to follow a tutorial and successfully set up the **RFID module** on a **Raspberry Pi**.  

The image below illustrates the **RFID sensor setup on a Raspberry Pi**:  

![image](https://github.com/user-attachments/assets/cefa86c4-f72e-4a47-99ed-e7a42ab2a958)  

---

### **Challenge 2: Finding the Required Libraries**  
To run the **RFID module (MFRC522)** on a **Raspberry Pi**, two primary libraries were required:  

1. **RPi.GPIO** – Controls the **GPIO pins** of the Raspberry Pi.  
   ```sh
   sudo apt-get install python3-rpi.gpio
   ```  
2. **mfrc522** – Manages **MFRC522 RFID readers**.  
   ```sh
   pip install mfrc522
   ```  

Additionally, **enabling SPI (Serial Peripheral Interface)** on the Raspberry Pi was a recommended step:  

1. Open Raspberry Pi configuration:  
   ```sh
   sudo raspi-config
   ```  
2. Navigate to:  
   ```
   Interfacing Options → SPI → Enable
   ```  
3. Restart the Raspberry Pi:  
   ```sh
   sudo reboot
   ```

---

### **Challenge 3: Limited RFID Storage Capacity**  
Initially, we intended to store **3D model API keys** directly on the RFID tags for easy access upon scanning. However, due to the **limited data storage** capacity of RFID tags, this approach was not feasible.  

#### **Alternative Solution:**  
Instead of storing large amounts of data, we **designed a webpage** displaying all four **3D models**, allowing users to **navigate between them**. The **RFID tags** were instead used to **store only the preferred language** of the visitor. Upon scanning, the system detects the stored language and automatically loads the **corresponding audio guide** in **Arabic, English, French, or Urdu**.  

---

### **Challenge 4: Integrating 3D Objects in HTML**  
Integrating **3D models** into the webpage via **iframes** presented several challenges:  

1. **Large File Sizes** – The **3D models** were large, leading to **slow loading times** on the Raspberry Pi.  
2. **Cross-Domain Restrictions** – Since the models were hosted on **Sketchfab**, their **HTML frames** could not be **modified** due to cross-domain security policies.  
3. **Audio Synchronization** – We could not **delay the appearance of the audio guide button** until the **3D model fully loaded**, due to iframe limitations.  

#### **Solutions Considered:**  
- **Hosting 3D Models Locally** – This would allow complete **HTML customization**, but required designing the **entire webpage** from scratch.  
- **Keeping Sketchfab iframes** (Final Choice) – Since modifying the **iframe structure** was not possible, we **overlaid** the **audio button** on top of the **iframe**. This ensured the **audio button** was **always available** upon page load, regardless of **3D model loading time**.  

---

### **Challenge 5: Integrating Python with HTML**  
Since the **RFID system and Raspberry Pi** operate using **Python**, we had to bridge the gap between Python and HTML.  

#### **Solution:**  
1. **Reading RFID Data** – A Python script (`API_v4.py`) was created to **read the stored language** from the RFID tag.  
2. **Generating Dynamic HTML** – Another script (`create_html_file_v5.py`) dynamically generates an **HTML file** containing:  
   - The **3D models**  
   - The **audio guide** in the detected **language**  
3. **Additional Web Components** – Other files handled **CSS styling, JavaScript interactivity, and RFID writing functions**.  

---

## **Conclusion**  
This project successfully demonstrated an **interactive museum experience** by integrating **RFID technology, 3D models, and multilingual audio guides**. Through overcoming hardware challenges, **RFID limitations**, and **HTML restrictions**, we developed a **seamless system** that enhances museum visits by allowing users to **see, hear, and interact with historical artifacts** in their preferred language.

Here is the link for the [code](https://github.com/Leen-QM/Raspberry)

Additionally, we conducted a survey to gather user feedback on their experience with the tool. The survey details, analysis, and visualizations can be found on the following page.

You can access the full survey report [here.](./Task7.md)


[back](./)
