# Urban Growth in Asaba, Delta State (2000–2025)

**GeoDev Lab Africa, Cohort One**
**Author:** Dike Ebubechi

This project examines the expansion of built-up areas and the spatial direction of urban growth in **Asaba, Delta State, Nigeria**, between 2000 and 2025.

The project brings together the four weekly tasks completed during the month into one workflow, from defining the project and preparing the data to carrying out the first spatial analysis.

---

## The Question

> **How much has the built-up area of Asaba, Delta State, Nigeria expanded between 2000 and 2025, and in which directions has the expansion occurred?**

---

## Study Area

The study area is Asaba, Delta State, located on the western bank of the River Niger, opposite Onitsha.

The analysis focuses mainly on **Oshimili South LGA** and the defined adjoining part of **Oshimili North LGA** needed to represent the Asaba urban area.

---

## What's in Here

```text
urban-growth-asaba/
│
├── README.md
│
├── docs/
│   ├── 01-project-brief.md
│   ├── 02-data-notes.md
│   ├── 03-data-preparation.md
│   └── 04-month-1-summary.md
│
├── data/
│   ├── raw/
│   └── processed/
│
├── maps/
│
├── scripts/
│
└── requirements.txt
```

---

## Weekly Work

### Week 1 — Project Brief

Defined the project topic, study area, spatial question, proposed datasets, and approach.

**File:** [01-project-brief.md](docs/PROJECT-BRIEF.md)

---

### Week 2 — Data Notes

Documented the datasets used for the project, including their sources, formats, coordinate systems, attributes, and initial checks.

The main datasets documented were:

* GRID3 Nigeria LGA boundary
* OpenStreetMap road network
* Landsat imagery

**File:** [02-data-notes.md](docs/DATA-NOTES.md)

---

### Week 3 — Data Preparation

Prepared the spatial data for analysis by:

* Reprojecting the data to **EPSG:32632 — WGS 84 / UTM Zone 32N**
* Clipping the data to the study area
* Checking data completeness
* Checking currency
* Checking positional accuracy
* Checking attribute accuracy
* Checking fitness for purpose

**File:** [03-data-preparation.md](docs/DATA_PREPARATION.md)

---

### Week 4 — First Spatial Analysis

Created a **100 m non-dissolved buffer** around the clipped OpenStreetMap road network.

The processing produced:

* **7,012 input road features**
* **7,012 output buffer features**
* **7,012 valid features**
* **0 invalid features**
* **0 geometry errors**

The resulting buffers followed the road network and remained within the study area.

The Week 4 analysis and results are documented in the monthly summary.

**File:** [04-month-1-summary.md](docs/month-1-summary.md)

**Map:** [Week 4 map](maps/asaba_100m_road_buffer.png)

**Processed data:** [Processed data](data/processed/asaba_roads_100m_buffer.gpkg)

---

## Data

The main datasets used in this project are:

| Dataset                    | Purpose                                                      |
| -------------------------- | ------------------------------------------------------------ |
| Landsat 5 TM               | Historical imagery for urban growth analysis                 |
| Landsat 8 OLI              | Later-period imagery for urban growth analysis               |
| Landsat 9 OLI-2            | 2025 imagery                                                 |
| GRID3 Nigeria LGA Boundary | Defining the study area                                      |
| OpenStreetMap Roads        | Examining the relationship between roads and urban expansion |

The project uses the original data sources documented in the Week 1 and Week 2 files.

---

## Coordinate Reference System

The working CRS for the prepared spatial data is:

**EPSG:32632 — WGS 84 / UTM Zone 32N**

This projected CRS was used because the study area is in eastern Nigeria and the analysis requires measurements in metres for operations such as distance, area, clipping, and buffering.

---

## Software

* **QGIS** — spatial data preparation, processing and mapping
* **Google Earth Engine** — Landsat data processing
* **GitHub** — project documentation and version control

---

## Monthly Progress

| Week   | Task                                | Status      |
| ------ | ----------------------------------- | ----------- |
| Week 1 | Project brief                       | ✅ Completed |
| Week 2 | Data notes                          | ✅ Completed |
| Week 3 | Data preparation and quality checks | ✅ Completed |
| Week 4 | First spatial analysis and checks   | ✅ Completed |

---

## Monthly Integrated Task

This repository combines the four weekly tasks into one project.

The workflow moves from:

**Project definition → Data collection → Data preparation → Spatial analysis**

The four weekly deliverables are linked above so that they can be opened directly from this repository.

---

## Current Outputs

The repository contains:

* Project brief
* Dataset documentation
* Data preparation and quality checks
* Prepared spatial data
* Week 4 road-buffer analysis
* Week 4 map
* Monthly summary

---

**Dike Ebubechi · GeoDev Lab Africa**
*Learn. Build. Collaborate. Transform.*
