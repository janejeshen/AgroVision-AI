# AgroVision-AI: Satellite-Based Crop Classification in West Africa

AgroVision-AI is a machine learning project that leverages **satellite imagery** and **AI** to classify agricultural crops in West Africa at the **pixel level**. The focus is on distinguishing **cocoa, rubber, and oil palm plantations** using **multi-temporal Sentinel-2 data** from the Copernicus program.  

This project was developed as part of **Tolbi’s mission** to advance **precision agriculture** and **nature restoration** across Africa, starting with Côte d’Ivoire one of the world’s top producers of cocoa, rubber, and oil palm.

## Problem Statement

Traditional crop identification methods rely on manual field visits, which are:  
- ✅ Expensive  
- ✅ Time-consuming  
- ✅ Error-prone  

By contrast, **remote sensing + machine learning** offers a **scalable, cost-effective, and accurate** alternative.  

The challenge is to:  
- Classify each pixel into **Cocoa, Rubber, or Oil Palm**.  
- Use **multi-temporal imagery** (a full year of satellite data) to capture seasonal growth patterns.  
- Build a model that **generalises well** across diverse regions and crop types.


## Data

The dataset combines **Sentinel-2 imagery** with provided train/test splits:  

- **TrainDataset.csv** – metadata for the training set  
- **TestDataset.csv** – metadata for the test set  
- **S2Images.zip (585 MB)** – Sentinel-2 image tiles  
- **trainGeo.zip** – geospatial geometries for training data (for validation only, not inference)  
- **ByteSizedAgriStarterBook.ipynb** – starter notebook with preprocessing and baseline example  

👉 Additional Sentinel-2 imagery can be downloaded via the **Copernicus Data Space Ecosystem** to enrich models.  

⚠️ **Important constraint**: At test time, models must not use geometry-related features. Predictions must be based purely on satellite imagery, simulating real-world deployment.

## 🧠 Approach

The model leverages:  
- **Multi-temporal features** → capturing seasonal crop differences  
- **Spectral indices** (e.g., NDVI, EVI, NDWI) → highlighting vegetation health and water content  
- **Pixel-level classification** → mapping not just where crops are grown, but what exactly is being grown  

The classification task is evaluated using **Weighted F1 Multi-Class Score**, balancing performance across **Cocoa, Rubber, Palm** categories.

## 📊 Evaluation Metric

**Weighted F1 Score (Multi-Class)**  
- Balances macro-F1 with class frequency weighting.  
- Ensures fair performance across dominant and minority crop classes.

## Installation & Usage
1. Clone the repo
`git clone https://github.com/janejeshen/AgroVision-AI.git
cd AgroVision-AI`
2. Install dependencies
`pip install -r requirements.txt`
3. Download data
Place TrainDataset.csv, TestDataset.csv, and S2Images.zip in data/.
4. Run Data Extraction, data preprocessing & modelling respectively

