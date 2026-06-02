# 🎵 MATLAB BPM Audio Classifier & Player

![MATLAB](https://img.shields.io/badge/MATLAB-R2021a%2B-blue?style=flat-square&logo=matlab)
![License](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)
![Signal Processing](https://img.shields.io/badge/Toolbox-Signal_Processing-orange?style=flat-square)

A comprehensive MATLAB Live Script project that automatically analyzes `.mp3` audio files, estimates their tempo (BPM) using energy-based onset detection, categorizes them into distinct playlists, and provides an integrated command-line interface (CLI) playback system.

Created as a Final Project for the **Robotic Tools** (Herramientas Robóticas - MATLAB) course.

---

## ✨ Features

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

## 🛠️ Prerequisites

To run this project, you will need:
* **MATLAB** (Tested on recent versions supporting Live Scripts `.mlx`).
* **Signal Processing Toolbox** (Required for the `findpeaks` function used in BPM estimation).

---

## 📂 Project Structure

Ensure your directory is set up as follows before running the script:

```text
📦 matlab-bpm-classifier
 ┣ 📂 canciones           # ⚠️ YOU MUST CREATE THIS: Place your raw .mp3 files here
 ┣ 📜 reproductor_bpm.mlx # The main MATLAB Live Script
 ┣ 📜 README.md           # Project documentation
 ┗ 📜 .gitignore          # MATLAB ignore file
