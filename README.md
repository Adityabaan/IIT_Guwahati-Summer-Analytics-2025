# IIT_Guwahati-Summer-Analytics-2025

# 🚗 Real-Time Dynamic Parking Pricing using Pathway

**IITG Summer Analytics 2025 Capstone**  
*Organized by Consulting & Analytics Club, IIT Guwahati*

---

## 📈 Overview

**Real-Time Dynamic Parking Pricing** is a capstone project that demonstrates a robust, real-time data streaming pipeline for dynamic parking price computation. Leveraging **Pathway** for stream processing and **Bokeh** for live visualization, this project showcases how modern analytics can optimize urban parking using live occupancy data.

**Key Features:**
- Real-time data ingestion and streaming
- Advanced feature engineering on streaming data
- Dynamic pricing based on utilization, demand, peak hours, and surge events
- Interactive, live dashboards for price signals

---

## 🗺️ Table of Contents

- [Overview](#-overview)
- [Architecture](#-architecture)
- [Tech Stack](#-tech-stack)
- [Repository Structure](#-repository-structure)
- [Getting Started](#-getting-started)
- [Project Workflow](#-project-workflow)
- [Results](#-results)
- [Extending the Project](#-extending-the-project)
- [Credits](#-credits)
- [License](#-license)

---

## 🏗️ Architecture

flowchart LR
    A[CSV Data Simulated Streaming]:::source --> 
    B[Pathway replay_csv]:::process --> 
    C[Schema Parsing and Timestamp Engineering]:::process --> 
    D[Windowing Daily Tumbling]:::process --> 
    E[Feature Engineering]:::feature --> 
    F[Dynamic Pricing Computation]:::compute --> 
    G[Bokeh Panel Visualization]:::output

    classDef source fill:#f9f,stroke:#333,stroke-width:2px;
    classDef process fill:#c6e2ff,stroke:#0366d6,stroke-width:2px;
    classDef feature fill:#ffe5b4,stroke:#ff9800,stroke-width:2px;
    classDef compute fill:#d5f5e3,stroke:#27ae60,stroke-width:2px;
    classDef output fill:#fce4ec,stroke:#c2185b,stroke-width:2px;



---

## 🛠️ Tech Stack

| Component         | Purpose                                 |
|-------------------|-----------------------------------------|
| **Python 3.11+**  | Core programming language               |
| **Pathway**       | Real-time data streaming & windowing    |
| **Pandas**        | Data preprocessing                      |
| **Bokeh + Panel** | Interactive visualization               |
| **Jupyter**       | Development & demonstration             |
| **Git + GitHub**  | Version control & collaboration         |

---

## 📁 Repository Structure

- `Notebook_FINAL.ipynb`  
  ↳ Final cleaned notebook with code & explanations

- `Notebook_FINAL.ipynb - Colab.pdf`  
  ↳ PDF version of the final notebook (for documentation)

- `bokeh_plot.png`  
  ↳ Exported Bokeh plot image

- `dataset.csv`  
  ↳ Primary dataset used for analysis

- `parking_stream.csv`  
  ↳ Simulated streaming data for real-time insights

- `problem statement.pdf`  
  ↳ Problem statement provided for the project

---

## 🚀 Getting Started

### 1️⃣ Clone the repository:
git clone https://github.com/<your-username>/IITG-Summer-Analytics-2025.git
cd IITG-Summer-Analytics-2025


### 2️⃣ Install dependencies:
pip install pathway pandas bokeh panel matplotlib

3️⃣ Launch Jupyter:
jupyter notebook


Open `Sample_Notebook.ipynb`, run all cells, and interact with the live streaming visualization.

---

## 🔄 Project Workflow

### 1. Data Ingestion
- Simulate live parking occupancy using a CSV file.
- Load with `pandas.read_csv` and stream via `pw.demo.replay_csv`.

### 2. Preprocessing
- Merge `Date` and `Time` into a single `Timestamp`.
- Sort data chronologically.

### 3. Pathway Streaming Pipeline
- Define a `ParkingSchema`.
- Stream and parse timestamps, extract day/hour features.
- Apply **daily tumbling windows** for aggregation.
- Compute daily `occ_max`, `occ_min`, and `capacity`.

### 4. Dynamic Pricing Model
- **Base price:** 5
- **Demand fluctuation:** Scaled by 10
- **Peak hours (8 AM - 6 PM):** +2
- **Surge pricing:** 1.5x multiplier if utilization > 80%
- **Final price:** Dynamically computed and rounded in-stream

### 5. Visualization
- Real-time, interactive price signals using **Bokeh** and **Panel**.

### 6. Execution
- Run the pipeline with `pw.run()`
- Monitor progress in Pathway’s dashboard
- Interact with the live Bokeh plot

---

## 📊 Results

- **Dynamic pricing pipeline** implemented and validated
- Real-time visualization aligns price with occupancy patterns
- Demonstrates practical use of Pathway streaming for analytics workflows

---

## 🌱 Extending the Project

- Ingest data from multiple parking spots
- Integrate predictive ML models for smarter pricing
- Enhance with weather or event data for richer analytics

---

## 🙌 Credits

- **Developed for:** IITG Summer Analytics 2025 Capstone
- **Organized by:** Consulting & Analytics Club, IIT Guwahati
- **Made by:** Adityabaan Tripathy
---

This project is submitted solely for academic evaluation for **IITG Summer Analytics 2025**.

> *Ready to revolutionize parking analytics? Fork, star, and contribute!*





