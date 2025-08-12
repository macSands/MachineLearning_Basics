# MachineLearning_Basics

Click the button below to run the notebook directly in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/macSands/MachineLearning_Basics/blob/main/AfRSG_ML_example.ipynb)

---

## **Machine Learning for Poaching Risk Prediction in Kruger National Park**

#### Jupyter Notebook Demo: "What is Artificial Intelligence in the context of African Rhino Research"
Sandra MacFadyen

---

### **How AI Can Help Rhino Protection in Africa**
Machine Learning (ML), a subset of **Artificial Intelligence (AI)**, offers powerful tools for **wildlife conservation** by:

- **Predicting Poaching Hotspots:** AI models analyze past incidents to identify **where poaching is most likely to occur**, allowing **proactive patrolling**.
- **Optimizing Ranger Deployment:** By focusing on **high-risk areas**, conservation teams can **allocate limited resources more effectively**.
- **Integrating Real-Time Data:** ML can process live data from **drones, camera traps, and satellites**, providing **early warnings of poaching threats**.
- **Enhancing Anti-Poaching Strategies:** AI can detect **patterns in poacher behavior**, helping authorities **stay ahead of illegal activities**.

By leveraging AI-driven models, conservationists can **improve rhino protection efforts** and combat poaching more efficiently, ensuring the survival of these endangered species in Africa.

---

### Machine Learning Workflow
This code demonstrates the basic building blocks of an AI-driven poaching risk pipeline for Kruger National Park:
It reads in a table of real poaching points (with longitude, latitude, and a label), then converts those points and a roads layer into a projected coordinate system (UTM 36S) so that distances can be measured in meters. It calculates each point’s minimum distance to the nearest road, then uses the reprojected DEM (elevation model) and slope raster to look up elevation and slope values for every point’s location. Finally, it stores these new columns—distance, elevation, slope—in a single GeoDataFrame and optionally transforms everything back to latitude–longitude (EPSG:4326) for sharing or display. The result is a unified dataset of poaching points enriched with roads‐distance, terrain height, and slope, ready for mapping or further modeling.

1. Data Simulation: Poaching incident points, non-incident points, roads.   
2. Feature Engineering: Distance to roads, slope (as a stand-in for terrain or habitat).   
3. Model Training: Random Forest classification.   
4. Grid Prediction: Generating a continuous surface of risk.   
5. Visualization: Static (matplotlib + contextily) and Interactive (folium).