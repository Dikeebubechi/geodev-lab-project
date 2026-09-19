# Data Preparation and Quality Checks

## CRS and Data Preparation

### Source Coordinate Reference System

The source datasets were received in **EPSG:4326 – WGS 84**.

The datasets used for this preparation were:

* Nigeria LGA Boundary from **GRID3**
* OSM road network from **OpenStreetMap**, extracted using **QuickOSM**

### Working Coordinate System

The working coordinate system selected for the project is:

**EPSG:32632 – WGS 84 / UTM Zone 32N**

This CRS was selected because the study area is located in eastern Nigeria and UTM Zone 32N is appropriate for the area. The projected CRS also uses metres, making it suitable for distance and area calculations.

---

## Reprojection

The source study-area boundary was reprojected from **EPSG:4326** to **EPSG:32632**.

The OSM road data were also prepared in the working coordinate system, **EPSG:32632**, so that the datasets used for analysis have a common projected CRS.

The reprojection was carried out in QGIS using the **Reproject Layer** tool.

The original files in `data/raw/` were not modified.

---

## Study Area Extraction and Clipping

The required study area was extracted from the Nigeria LGA boundary data using the relevant areas covering **Oshimili South and the defined adjoining area of Oshimili North**.

The selected study-area boundary was saved as a GeoPackage in:

`data/processed/`

The OSM road network was then clipped to the study-area boundary using the **Clip** geoprocessing tool in QGIS.

The resulting road layer contains only the road features within the defined study area.

The clipped road data were prepared in **EPSG:32632** and saved in the `data/processed/` folder.

---

## Area Calculation

Area was calculated after reprojection to the projected CRS **EPSG:32632** so that the measurements were based on metres rather than geographic degrees.

The area was calculated in square metres using the QGIS Field Calculator:

```qgis
$area
```

The area was then converted to square kilometres using:

```qgis
$area / 1000000
```

The resulting study-area value was checked to ensure that it was reasonable for the defined Asaba study area.

**Final study-area value:** `[INSERT YOUR ACTUAL AREA IN km² FROM QGIS]`

The area calculation was used as a sanity check to confirm that the projected study-area geometry produced a reasonable measurement.

---

# Data Quality Checks

## 1. Data Completeness

**What I checked:**
I checked whether the study-area boundary and the clipped OSM road layer cover the whole defined study area and whether there are any obvious missing features.

**Result:**
The study-area boundary covers the defined study area, and the OSM road layer provides road coverage across the study area. No major gaps were observed during visual inspection. Both datasets were considered sufficient for carrying out the intended analysis.

**Decision:**
The datasets were retained for the project.

---

## 2. Currency

**What I checked:**
I checked how recent the datasets are and whether they are appropriate for the 2000–2025 urban growth study.

**Result:**
The GRID3 LGA boundary data and OSM road data were obtained/extracted on **12 September 2026**. The GRID3 LGA boundary was last updated on GRID3 in **December 2020**. The OSM road data represent the available/current road information at the time of extraction.

The datasets are sufficiently current for use as the current/reference spatial datasets for the project. However, the OSM road data were not treated as historical road data for the entire 2000–2025 period.

**Decision:**
The datasets were retained, with the date and temporal limitation of the OSM road data noted.

---

## 3. Positional Accuracy

**What I checked:**
I checked whether the spatial features are located in their expected geographic positions.

**Result:**
The OSM road network was visually checked against the study-area boundary and available basemap imagery. The roads generally align with their expected geographic positions, and no obvious systematic positional shift was observed.

**Decision:**
No positional correction was considered necessary based on the visual inspection.

---

## 4. Attribute Accuracy

**What I checked:**
I checked whether the descriptive attributes of the OSM road dataset are correctly populated and usable.

**Result:**
The main OSM road attributes, including `highway`, `surface`, and `name`, were examined. Some null values were found, particularly in descriptive fields such as `surface`, `smoothness`, and road names.

The records were retained because missing attribute values do not necessarily indicate missing road features. The null values were flagged as a limitation of the dataset.

**Decision:**
The road features were retained and the missing attribute values were flagged rather than removing the affected records.

---

## 5. Fitness for Purpose

**What I checked:**
I checked whether the prepared datasets are suitable for answering the project's spatial question and supporting the intended analysis.

**Result:**
The prepared study-area boundary and road network are suitable for the intended spatial analysis and for supporting the interpretation of urban growth patterns.

However, the OSM road dataset represents available/current road information and is not, by itself, sufficient to measure built-up change between 2000 and 2025. Additional historical and current built-up/LULC data are required for that part of the analysis.

**Decision:**
The datasets were retained because they are suitable for their intended supporting role in the project.

---

# Problems Identified and Actions Taken

### 1. Geographic CRS

The original datasets were in **EPSG:4326**, which is a geographic coordinate system and is not appropriate for final area calculations in square metres or square kilometres.

**Action taken:**
The data were reprojected to **EPSG:32632 – WGS 84 / UTM Zone 32N** before carrying out the final area calculation and spatial preparation.

### 2. Missing OSM Attributes

Some OSM road records contained null values in descriptive fields such as `surface`, `smoothness`, and `name`.

**Action taken:**
The road features were retained because missing descriptive attributes do not necessarily mean that the road feature itself is missing. The null values were flagged as a limitation of the dataset.

### 3. Temporal Limitation of OSM Roads

The OSM road data were extracted on **12 September 2026** and therefore represent available/current road information rather than a complete historical road network for every year from 2000 to 2025.

**Action taken:**
The OSM road dataset will be used as current/reference supporting data and not as the sole dataset for measuring historical built-up change.

---

# Analysis-Ready Data

The prepared analysis-ready files are stored in:

```text
data/processed/
```

The processed data include:

* **Study-area boundary:** `study_area.gpkg`
* **Clipped OSM road network:** `[INSERT EXACT ROAD FILENAME]`

All processed layers are in:

**EPSG:32632 – WGS 84 / UTM Zone 32N**

The original source data remain in:

```text
data/raw/
```

and were not modified.

---

# Summary

The Week 3 data preparation involved identifying the appropriate working CRS, reprojecting the datasets to **EPSG:32632**, extracting the defined Asaba study area, clipping the OSM road network to the study area, and calculating the study-area size in square kilometres.

Five data quality checks were carried out: **data completeness, currency, positional accuracy, attribute accuracy, and fitness for purpose**. The datasets were found to provide adequate coverage and positional alignment for the intended work. Some missing OSM attributes were identified and flagged, while the temporal limitation of the current OSM road data was also documented.

The resulting analysis-ready datasets are stored in `data/processed/`, while the original raw datasets in `data/raw/` were left unchanged.
