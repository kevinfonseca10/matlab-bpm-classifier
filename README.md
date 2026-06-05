# 🎵 MATLAB BPM Audio Classifier & Player

![MATLAB](https://img.shields.io/badge/MATLAB-R2021a%2B-blue?style=flat-square&logo=matlab)
![License](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)
![Signal Processing](https://img.shields.io/badge/Toolbox-Signal_Processing-orange?style=flat-square)

## 1. Project Description
A comprehensive MATLAB Live Script project that automatically analyzes `.mp3` audio files, estimates their tempo (BPM) using energy-based onset detection, categorizes them into distinct playlists, and provides an integrated command-line interface (CLI) playback system.

Created as a Final Project for the **Robotic Tools** (Herramientas Robóticas - MATLAB) course.

### ✨ Features
* **🔍 Automatic MP3 Detection:** Scans a designated `canciones` directory and safely creates destination folders.
* **📊 Energy-Based BPM Estimation:** Converts stereo tracks to mono, calculates signal energy over 50ms windows, and uses the `findpeaks` algorithm to detect rhythmic onsets.
* **🗂️ Triple Classification System:** Evaluates tracks using three distinct methods:
    1.  **Standard Fixed Thresholds** (Slow < 90, Medium 90-130, Fast > 130).
    2.  **Alternative Fixed Thresholds** (Custom limits).
    3.  **Automatic Percentiles** (Dynamic limits based on the 33rd and 66th percentiles of the current dataset).
* **📈 Data Visualization:** Generates a beautiful inline scatter plot comparing the songs against the dynamic percentile thresholds.
* **📁 Automated File Routing:** Safely copies and organizes the `.mp3` files into `lento`, `medio`, and `rapido` folders based on the chosen classification method.
* **⌨️ Interactive CLI Player:** A built-in keyboard-controlled audio player allowing users to play `[x]`, pause `[c]`, stop `[v]`, or skip `[z]/[b]` tracks directly from the MATLAB command window.

---

## 2. Justification
This project was developed to practically apply core principles of digital signal processing, algorithm design, and automated file management within a MATLAB environment. Estimating BPM using energy-based onset detection serves as a foundational exercise in extracting meaningful features from raw sensor data (in this case, audio signals). Furthermore, building a dynamic classification system and an interactive CLI player demonstrates how computational logic can be used to automate everyday tasks, a crucial skill for software and hardware integration.

---

## 3. Development
The project was developed as a MATLAB Live Script (`reproductor_bpm.mlx`) divided into six logical execution cells:

1. **Initial Setup:** Automates the creation of destination folders and scans the directory for raw `.mp3` files.
2. **BPM Estimation:** Reads audio files, calculates signal energy, utilizes the `findpeaks` function to detect rhythmic onsets, and calculates the BPM based on peak intervals.
3. **Classification Logic:** Implements three sorting algorithms to classify the music (Fixed, Alternative, and Percentile-based).
4. **Data Visualization:** Plots a scatter graph comparing the estimated BPMs against the dynamically generated thresholds.
5. **File Routing:** Safely copies the original `.mp3` files into their respective category folders.
6. **CLI Audio Player:** A built-in keyboard-controlled loop for playback navigation directly from the command window.

## 4. Results
The algorithm successfully reads and sorts audio files without data loss, demonstrating a robust ability to estimate tempos and dynamically adjust sorting thresholds based on the given dataset. The interactive interface runs smoothly without interrupting the main MATLAB thread.

🎥 **[▶️ Watch the Video Presentation Here]-([(https://youtu.be/rmFKoHQGKFs)])**

### 🛠️ Prerequisites & Project Structure
To run this project, you will need **MATLAB** (Live Scripts supported) and the **Signal Processing Toolbox**. Ensure your repository is structured as follows, with the code properly located in its respective folders:
### 📚 Citations & Acknowledgments
* **Musical Repository:** The audio dataset utilized for testing and development was provided by Francisco Carlos Calderon Bocanegra.
* **AI Assistance:** Artificial Intelligence tools, specifically Claude and GitHub Copilot, were used to assist in structuring the code and formatting this documentation.

### 👨‍💻 Authors
* Kevin Fonseca Escamilla - @kevinfonseca10
* Sergio Andres Florez Tique

```text
📦 matlab-bpm-classifier
 ┣ 📂 canciones           # ⚠️ YOU MUST CREATE THIS: Place your raw .mp3 files here
 ┣ 📂 lento               # Automatically populated with slow tempo tracks
 ┣ 📂 medio               # Automatically populated with medium tempo tracks
 ┣ 📂 rapido              # Automatically populated with fast tempo tracks
 ┣ 📜 Macro_Proyecto.mlx  # The main MATLAB Live Script
 ┣ 📜 README.md           # Project documentation
 ┗ 📜 .gitignore          # MATLAB ignore file



