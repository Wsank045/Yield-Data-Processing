# Yield-Data-Processing

This repository contains code and data for processing raw yield monitor data to remove erroneous or unreliable measurements. The goal is to ensure high-quality yield maps for further analysis and modeling (e.g., yield prediction, agronomic decision-making).

## 📋 Overview

The data cleaning procedures implemented in this project are inspired by the following research papers:

- Lyle, G., Bryan, B. A., & Ostendorf, B. (2013). *Post-processing methods to eliminate erroneous grain yield measurements: review and directions for future development*. Precision Agriculture, 15(4), 377–402. https://doi.org/10.1007/s11119-013-9336-3  
- Blackmore, S. (1999). *Remedial correction of yield MAP data*. Precision Agriculture, 1(1), 53–66. https://doi.org/10.1023/a:1009969601387

## 🛠️ Processing Steps

1. **Harvest Lag Time** – Removing records affected by delay between sensor and grain flow.
2. **Fill/Finish Mode Errors** – Filtering out low-flow or buffer-fill data from beginning/end of each pass.
3. **Continuous Measurement Check** – Removing yield/moisture outliers.
4. **Short Segments** – Eliminating segments shorter than a defined distance threshold.
5. **Harvester Speed** – Filtering records with speeds outside expected operational range.
6. **Overlap Removal** – Cleaning double-counted or overlapping swaths.


## 📍 Data Sources and Field Details

### Manitoba

**Important Attributes:**
- `Coordinates`: Geographical position of yield samples  
- `Time` / `IsoTime`: UTC timestamp / ISO-formatted timestamp  
- `DISTANCE`: Travelled distance since last point  
- `SWATHWIDTH`: Width of harvester equipment  
- `Moisture`: Crop moisture content (%)  
- `Elevation`: Elevation (feet)  
- `VEHICLSPEED`: Harvester speed  
- `VRYIEDVOL`: Volumetric yield (bu/ac)  
- `WetMass`: Wet mass yield (lbs/ac)  
- `SECTION ID`: Pass number  

---

### Alberta


**Important Attributes:**
- `Coordinates`: UTM Easting and Northing (meters)  
- `Time` / `Date`: Recording timestamp  
- `Elevation_`: GPS elevation (feet)  
- `Swth_Wdth_`: Swath width (feet)  
- `Yld_Mass_W`: Wet mass yield (lb/ac)  
- `Yld_Vol_Dr`: Dry volumetric yield (bu/ac)  
- `Yld_Mass_D`: Dry mass yield (lb/ac)  
- `Yld_Vol_We`: Wet volumetric yield (bu/ac)  
- `Moisture__`: Moisture content (%)  
- `Pass_Num`: Harvester pass number  
- `Distance_f`: Travelled distance (feet)  
- `Speed_mph_`: Harvester speed  

---

### Southern Ontario


**Important Attributes:**
- `Coordinates`: UTM Easting and Northing (meters)  
- `Time` / `Date`: Recording date  
- `Duration_s`: Duration between samples (seconds)  
- `Elevation_`: Elevation (feet)  
- `Swth_Wdth_`: Swath width (feet)  
- `Speed_mph_`: Vehicle speed  
- `Distance_f`: Travelled distance (feet)  
- `Yld_Mass_W`: Wet mass yield (lb/ac)  
- `Yld_Vol_Dr`: Dry volumetric yield (bu/ac)  
- `Yld_Mass_D`: Dry mass yield (lb/ac)  
- `Yld_Vol_We`: Wet volumetric yield (bu/ac)  
- `Moisture__`: Moisture content (%)  
- `Pass_Num`: Harvester pass number
