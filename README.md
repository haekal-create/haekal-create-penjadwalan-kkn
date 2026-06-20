# 🗓️ KKN Activity & Duty Scheduling System

<p align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white" alt="Pandas" />
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white" alt="Jupyter" />
</p>

## 📌 Overview
An automated, logic-driven scheduling system developed to manage daily administrative tasks and logistical planning during the **Kuliah Kerja Nyata (KKN)** community service program. 

This repository contains two primary scheduling engines that resolve time conflicts, ensure fair workload distribution among 8 team members, and strictly adhere to specific rotational constraints using Python.

## 🚀 Interactive Notebooks

You can run the scheduling algorithms directly in your browser without any local setup:

| Module | Description | Run in Colab |
| :--- | :--- | :--- |
| **Daily Task Scheduler** | Algorithms for Kitchen, Market, and Cleaning duties. | [![Open In Colab](https://colab.research.google.com/drive/1BNX66-cQwli8xAbwziVepdLVF7mH31nH?usp=sharing)] |
| **Drying Duty Scheduler** | Time-series based rotation for specific chores. | [![Open In Colab](https://colab.research.google.com/drive/1ArtQTbamvr66Wf8dOkNLui8klKyjtyGS?usp=sharing)]|

*(Note: Replace the URL placeholders above with the actual shareable links from your Google Colab).*

---

## 🧠 System Architecture & Logic

### 1. Daily Duty Scheduler (`Penjadwalan_piket.ipynb`)
A constraint satisfaction algorithm designed to distribute 4 distinct tasks (*Pasar, Masak, Bersih, Libur*) across 40 days for 8 participants.
* **Algorithmic Approach:** Utilizes randomized swapping logic (up to 200,000 iterations) to find an optimal schedule array.
* **Strict Constraints:** Enforces a "Zero Consecutive Violation" rule, ensuring no member performs the exact same duty two days in a row.
* **Automated Verification:** Includes an internal testing block to verify that all constraints are met (10 exact shifts per person per task) before generating the final output.

### 2. Rotational Drying Duty (`Jadwal_piket_jemur.ipynb`)
A deterministic time-series scheduler built with `pandas` and `datetime` to manage duty cycles from July 7, 2026, to August 14, 2026.
* **Cyclical Logic:** Implements a strict 5-day modulo rotation algorithm (3 days allocated for the Women's group, 2 days for the Men's group).
* **Data Formatting:** Automatically maps integer dates to localized strings (Indonesian days and months) for immediate user readability.

---

## 📊 Data Outputs (Exported CSVs)
The scripts automatically compile the generated schedules and export them into clean, ready-to-print CSV files:
* 📄 `jadwal_harian.csv` - The complete 40-day matrix for daily tasks.
* 📄 `rekap_beban_kerja.csv` - An analytical summary proving equal workload distribution (40 total shifts per member).
* 📄 `jadwal_piket_jemur.cs[jadwal_harian_piket_kkn (1).xlsx](https://github.com/user-attachments/files/29162352/jadwal_harian_piket_kkn.1.xlsx)
v` - The formatted timeline for the 5-day rotation groups.

## 🛠️ How to Run Locally

If you prefer to run the system on your local machine instead of Google Colab:

1. Clone this repository:
   ```bash
   git clone [https://github.com/UsernameKamu/NamaRepositori.git](https://github.com/UsernameKamu/NamaRepositori.git)
   cd NamaRepositori
