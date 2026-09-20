# Data preparation

**Week 3 deliverable.** GeoDev Lab Africa, Cohort One.
**Author:** Dike Ebubechi

*What I reprojected, what I clipped, what I checked, and what I fixed.*

---

## 1. Coordinate system decisions

**Working CRS:** EPSG:32632 – WGS 84 / UTM Zone 32N

**Why this one:** The study area is located in eastern Nigeria, and UTM Zone 32N was selected as the working coordinate system for the project. The projected CRS uses metres, making it suitable for distance and area calculations.

### Source and working CRS

The source datasets were received in **EPSG:4326 – WGS 84**.

The datasets used for this preparation were:

* Nigeria LGA Boundary from **GRID3**
* OSM road network from **OpenStreetMap**, extracted using **QuickOSM**

| Dataset              | CRS as downloaded | CRS after  | Operation   |
| -------------------- | ----------------- | ---------- | ----------- |
| Nigeria LGA Boundary | EPSG:4326         | EPSG:32632 | Reprojected |
| OSM road network     | EPSG:4326         | EPSG:32632 | Reprojected |

The reprojection was carried out in QGIS using the **Reproject Layer** tool.

The original files in `data/raw/` were not modified.

> Reprojecting recalculates the coordinates of the features into the new coordinate reference system. This is different from simply assigning or relabelling a CRS.

---

## 2. Clipping to the study area

**Boundary used:** Nigeria LGA Boundary from GRID3, covering **Oshimili South and the defined adjoining area of Oshimili North**.

**Features before clipping:**

* Nigeria LGA Boundary: 774 features
* OSM road network: 8,999 features

**Features after clipping:** 
* Study-area boundary: 2 polygon features
* OSM road network; Features: 7,012 line features

The required study area was first extracted from the Nigeria LGA boundary data using the relevant areas covering **Oshimili South and the defined adjoining area of Oshimili North**.

The selected study-area boundary was saved as:

`data/processed/study_area.gpkg`

The OSM road network was then clipped to the study-area boundary using the **Clip** geoprocessing tool in QGIS.

The resulting road layer contains only the road features within the defined study area and was prepared in **EPSG:32632**.

The clipped road network was saved as:

`data/processed/roads_asaba.gpkg`

The original source datasets in `data/raw/` were retained unchanged.

---

## 3. The five quality checks

| Check                                    | Result                | Action taken                                                                                                                                                                        |
| ---------------------------------------- | --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Is the CRS what I think it is?           | Yes                   | Source data were identified as EPSG:4326 and reprojected to EPSG:32632.                                                                                                             |
| Are there nulls in the fields I need?    | Yes                   | Null values were identified in some OSM descriptive fields, including `surface`, `smoothness`, and `name`. The affected features were retained and the missing values flagged.      |
| Are there duplicate features?            | No                    | Checked the data during inspection; no obvious duplicate features were observed.                                                                                                                  |
| Is the geometry valid?                   | Yes                   | Geometry was inspected and no obvious invalid geometries were observed.                                                                                                             |
| Does coverage span the whole study area? | Yes                   | The study-area boundary covers the defined study area, and the OSM road network provides road coverage across the study area. No major gaps were observed during visual inspection. |

### Additional quality observations

**Data completeness:** The study-area boundary covers the defined study area. The OSM road layer provides road coverage throughout the study area, and no major gaps were observed during visual inspection.

**Currency:** Both datasets were obtained or extracted on **12 September 2026**. The GRID3 LGA boundary was last updated on GRID3 in **December 2020**. The OSM road dataset represents the available/current road information at the time of extraction.

**Positional accuracy:** The OSM road network was visually checked against the study-area boundary and available basemap imagery. The roads generally align with their expected geographic positions, and no obvious systematic positional shift was observed.

**Fitness for purpose:** The prepared study-area boundary and road network are suitable for the intended spatial analysis and for supporting the interpretation of urban growth patterns. However, the current OSM road network is not sufficient by itself to measure built-up change between 2000 and 2025.

---

## 4. Problems found, and what I did

**Geographic CRS.** The original datasets were in **EPSG:4326**, a geographic coordinate system. This was not used for the final area calculation because the project requires measurements in metres, square metres, and square kilometres.

**Action taken:** The datasets were reprojected to **EPSG:32632 – WGS 84 / UTM Zone 32N** before the final area calculation and spatial preparation.

**Missing OSM attributes.** Some OSM road records contained null values in descriptive fields such as `surface`, `smoothness`, and `name`.

**Action taken:** The road features were retained because missing descriptive attributes do not necessarily mean that the road feature itself is missing. The null values were flagged as a limitation of the dataset rather than removing the affected road features.

**Temporal limitation of OSM roads.** The OSM road data were extracted on **12 September 2026** and therefore represent available/current road information rather than a complete historical road network for every year from 2000 to 2025.

**Action taken:** The OSM road dataset will be used as current/reference supporting data and not as the sole dataset for measuring historical built-up change.

**Area calculation.** Area was calculated after reprojection to **EPSG:32632** so that measurements were based on metres rather than geographic degrees.

**Action taken:** The QGIS Field Calculator was used with:

`$area`

The area was then converted from square metres to square kilometres using:

`$area / 1000000`

The calculated study-area boundary covers 769.884 km².

---

## 5. The analysis-ready output

### Study-area boundary

* **File:** `data/processed/study_area.gpkg`
* **Format:** GeoPackage
* **CRS:** EPSG:32632 – WGS 84 / UTM Zone 32N
* **Features:** 2 polygon features
* **Produced by:** Manually in QGIS

### Clipped OSM road network

* **File:** `data/processed/roads_asaba.gpkg`
* **Format:** GeoPackage
* **CRS:** EPSG:32632 – WGS 84 / UTM Zone 32N
* **Features:** 7,012 line features
* **Produced by:** Manually in QGIS

### Data storage

The original source datasets remain in:

`data/raw/`

The processed analysis-ready datasets are stored in:

`data/processed/`

The original raw datasets were not modified.

---

**Status:** Week 3 complete. First spatial analysis in Week 4.
