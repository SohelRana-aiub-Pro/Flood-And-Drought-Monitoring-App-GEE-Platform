Flood-And-Drought-Monitoring-App-GEE-Platform.
-------------------------------------------- 

![Google Earth Engine](https://img.shields.io/badge/Platform-Google%20Earth%20Engine-blue)
![Remote Sensing](https://img.shields.io/badge/Field-Remote%20Sensing-green)
![GIS](https://img.shields.io/badge/Technology-GIS-orange)
![Satellite Data](https://img.shields.io/badge/Data-Sentinel--1%20%7C%20CHIRPS%20%7C%20WorldPop-lightgrey)



📌 Overview
----------------
The **Flood & Drought Monitoring Application** is a Google Earth Engine (GEE)-based geospatial analysis platform designed to monitor, visualize, and assess the impacts of climate-induced hazards including **floods and droughts**.
The application integrates multi-source satellite and geospatial datasets to generate:

- Flood extent maps using Sentinel-1 Synthetic Aperture Radar (SAR)
- Drought condition maps using rainfall anomaly analysis
- Population exposure assessment using WorldPop datasets
- Agricultural impact estimation using ESA WorldCover land-use data
- 
- Interactive hazard visualization through a Google Earth Engine user interface

The system demonstrates how cloud-based remote sensing technologies can support rapid disaster assessment, environmental monitoring, and decision-making.

---

 🎯 Objectives
----------------------
The primary objectives of this project are:

- Develop an interactive disaster monitoring application using Google Earth Engine
- Detect flood-affected regions using Sentinel-1 SAR imagery
- Identify drought-prone areas using rainfall variability analysis
- Estimate vulnerable population exposure
- Assess potential agricultural losses
- Provide a simple visualization dashboard for hazard interpretation

---

 🏗️ System Architecture
----------------------------
                Geospatial Data Sources

   Sentinel-1 SAR       CHIRPS Rainfall
         |                    |
         |                    |
         ↓                    ↓

    Flood Detection     Drought Detection


         WorldPop              ESA WorldCover
            |                       |
            ↓                       ↓

    Population Exposure     Cropland Impact


                |
                ↓

      Google Earth Engine Processing

                |
                ↓

         Interactive Dashboard


---

# 🛰️ Data Sources

## 1. Sentinel-1 SAR

**Dataset:**
COPERNICUS/S1_GRD


### Purpose:
Flood detection

### Characteristics:

- C-band Synthetic Aperture Radar
- Cloud independent observation
- Day/night acquisition capability
- VV polarization analysis

### Method:

Flood areas are detected based on reduced radar backscatter values:


VV Backscatter < Threshold

      ↓

Potential Water/Flood Pixels


---

## 2. CHIRPS Rainfall Dataset

**Dataset:**


UCSB-CHG/CHIRPS/PENTAD


Purpose:
----------------
Drought monitoring through rainfall anomaly analysis.

CHIRPS provides:

- Satellite-based rainfall estimation
- Long-term precipitation records
- Global coverage

Method:


Mean Annual Rainfall < Threshold

          ↓

Drought Condition


---

## 3. WorldPop Population Dataset

**Dataset:**


WorldPop/GP/100m/pop


### Purpose:

Population exposure estimation.

The system overlays hazard maps with population distribution:


Hazard Area

  +

Population Density

  ↓

Exposed Population Estimate


---

## 4. ESA WorldCover

**Dataset:**


ESA/WorldCover/v100


### Purpose:

Agricultural impact assessment.

Cropland classification:


Land Cover Class = 40

    ↓

Cropland Extraction

    ↓

Flood/Drought Impact Analysis


---

# 🔬 Methodology

## Flood Mapping Workflow

1. Collect Sentinel-1 SAR imagery
2. Filter by:
   - Study area
   - Date range
   - Instrument mode
   - Polarization
3. Generate median radar composite
4. Apply water threshold classification
5. Produce flood extent layer


## Drought Mapping Workflow

1. Collect CHIRPS precipitation data
2. Calculate rainfall statistics
3. Apply rainfall anomaly threshold
4. Generate drought severity map


## Impact Assessment Workflow

Hazard maps are combined with:

- Population density
- Land cover classification

to estimate:

- Human exposure
- Agricultural vulnerability

---

# 🖥️ Application Features

## Interactive Hazard Selection

Users can select:

- Floods
- Droughts
- Cropland Loss
- Affected Population

---

## Visualization

The dashboard provides:

- Hazard maps
- Color-coded layers
- Rainfall time-series charts
- Regional statistics

---


# 📂 Project Structure


Flood-And-Drought-Monitoring-App-GEE-Platform/
│
├── Flood_Drought_Monitoring_App.js
│
├── Project_Code_Structure.js
│
├── README.md
│
└── LICENSE


---

# 📊 Outputs

The application generates:

| Output | Description |
|-|-|
| Flood Extent Map | Areas potentially affected by flooding |
| Drought Map | Low rainfall regions |
| Population Exposure | People located in hazard zones |
| Cropland Loss | Agricultural areas under risk |
| Rainfall Chart | Temporal precipitation analysis |

---

# ⚠️ Limitations

This prototype has several limitations:

## Flood Detection

- Fixed backscatter threshold
- No terrain correction
- Limited validation with ground observations

## Drought Detection

- Uses rainfall only
- Does not include vegetation stress or soil moisture

## Impact Assessment

Population exposure does not represent actual casualties or damage.

More detailed models require:

- Flood depth estimation
- Infrastructure data
- Socioeconomic information

---

# 🔮 Future Improvements

Possible improvements include:

## Machine Learning Integration

Add:

- Random Forest classification
- Deep learning segmentation
- Flood probability prediction

---

## Advanced Drought Indicators

Integrate:

- NDVI anomaly
- Vegetation Condition Index (VCI)
- Soil Moisture Index
- Standardized Precipitation Index (SPI)

---

## Real-Time Monitoring

Future versions can include:

- Weather API integration
- Automated alerts
- Web-based dashboards
- Mobile notifications

---

# 📚 Related Works

## 1. Google Earth Engine for Disaster Monitoring

Google Earth Engine has been widely adopted for large-scale environmental monitoring because it provides cloud-based access to satellite archives and scalable geospatial computation.

**Relevant applications:**

- Flood mapping
- Drought assessment
- Land-cover change detection
- Climate impact analysis


---

## 2. Sentinel-1 SAR Based Flood Mapping

Many studies use Sentinel-1 SAR imagery for flood detection because radar observations are not affected by cloud cover.

Common approaches include:

- Backscatter thresholding
- Change detection
- Machine learning classification

Example research areas:

- Rapid flood mapping after extreme rainfall events
- Near-real-time disaster response systems


---

## 3. CHIRPS-Based Drought Monitoring

CHIRPS rainfall data has been widely used for drought analysis because of its high temporal resolution and long historical coverage.

Common drought indicators:

- Rainfall anomaly
- SPI calculation
- Seasonal precipitation monitoring


---

## 4. Population Exposure Assessment

Combining hazard layers with population datasets such as WorldPop is a common approach for estimating disaster vulnerability.

Applications include:

- Flood risk assessment
- Humanitarian planning
- Emergency response prioritization


---

## 5. Multi-Hazard Monitoring Platforms

Recent disaster management systems combine:

- Remote sensing
- GIS analysis
- Climate datasets
- Machine learning

to create decision-support tools for governments and humanitarian organizations.

---



# 📖 References
1. Gorelick et al. (2017).  
**Google Earth Engine: Planetary-scale geospatial analysis for everyone.**  
Remote Sensing of Environment.

2. Torres et al. (2017).  
**Sentinel-1 SAR mission and applications.**

3. Funk et al. (2015).  
**The Climate Hazards Infrared Precipitation with Stations (CHIRPS).**

4. Tatem et al.  
**WorldPop: High-resolution population datasets for development and disaster applications.**

5. Zanaga et al. (2021).  
**ESA WorldCover 10 m land cover dataset.**

---

# 🤝 Contribution

Contributions are welcome.

You can contribute by:

- Improving hazard detection algorithms
- Adding new datasets
- Improving visualization
- Adding validation methods

Steps:

1. Fork the repository
2. Create a feature branch
3. Commit changes
4. Submit a pull request



---
# 👨‍💻 Author

**Sohel Rana**

Digital Currency Investor & Technical Lead

https://github.com/SohelRana-aiub-Pro/Flood-And-Drought-Monitoring-App-GEE-Platform/

Related Resources; https://github.com/ianpdavies/cloudy_flood_prediction
