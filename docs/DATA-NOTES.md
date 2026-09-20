# Data notes

**Week 2 deliverable.** GeoDev Lab Africa, Cohort One.
**Author:** Dike Ebubechi

What I downloaded, where it came from, what is in it, and what is wrong
with it.

## Summary

| # | Dataset              | Type   | Retrieved         | Status  |
| - | -------------------- | ------ | ----------------- | ------- |
| 1 | Nigeria LGA Boundary | Vector | 12 September 2026 | OK      |
| 2 | OSM Roads            | Vector | 12 September 2026 | Partial |

---

## 1. Nigeria LGA Boundary

* **Source:** https://grid3.org/
* **Retrieved:** 12 September 2026
* **File:** `grid3_nga_boundary_vacclgas`
* **Format:** `ESRI Shapefile`
* **Geometry type:** Polygon
* **Feature count:** 774
* **CRS as downloaded:** `WGS 84`

### Key columns

| Column      | What it holds                                 | Nulls |
| ----------- | --------------------------------------------- | ----- |
| `Lganame`   | Name of the Local Government Area             | No    |
| `Statename` | Name of the state in which the LGA is located | No    |

### What I noticed

* The dataset contains **774 LGA polygon features**.
* The `Lganame` and `Statename` fields are available and contain no null values.
* The dataset covers the **Oshimili South and Oshimili North** study areas fully.
* The polygon geometry is suitable for identifying and extracting the required study-area LGAs.
* The dataset was obtained from **GRID3** on 12 September 2026.
* No missing values were identified in the important columns used for identifying the study area.

---

## 2. OSM Roads

* **Source:** OpenStreetMap
* **Retrieved:** 12 September 2026
* **File:** `roads_oshns_lgas`
* **Format:** `ESRI Shapefile`
* **Geometry type:** Line
* **Feature count:** 8,999
* **CRS as downloaded:** `WGS 84`

### Key columns

| Column    | What it holds                                  | Nulls |
| --------- | ---------------------------------------------- | ----- |
| `highway` | Classification/type of road or highway feature | Yes   |
| `surface` | Surface material or road-surface information   | Yes   |
| `name`    | Recorded name of the road                      | Yes   |

### What I noticed

* The road dataset contains **8,999 line features**.
* It was extracted from **OpenStreetMap using QuickOSM** with the query `highway=*`.
* The extraction covers **Oshimili South and adjoining Oshimili North**.
* Road coverage appears generally good within the study area.
* Many of the mapped roads are **unpaved**, based on the available `surface` information.
* Some road features do not have recorded road names, resulting in null values in the `name` field.
* Some records may also have missing information in the `highway` and `surface` fields.
* The presence of missing attribute information should be considered when using road names or surface types for subsequent analysis.

---

## Cross-cutting problems

**Incomplete road attributes.** The OSM road dataset contains null values in some attribute fields, particularly road names and potentially road-surface information. Therefore, analyses that depend on complete road names or surface classifications may have gaps.

**Different coverage characteristics.** The LGA boundary dataset provides complete polygon coverage of the study area, whereas the OSM road dataset represents mapped road features and may contain unmapped or incompletely attributed roads.

**Study-area consistency.** The LGA boundary dataset covers the study area fully, while the OSM road extraction includes Oshimili South and adjoining Oshimili North. The final road dataset should therefore be clipped to the exact study-area boundary where necessary.

---

**Status:** Week 2 complete. Reprojection and quality checks in Week 3, see [DATA PREPARATION.md](DATA PREPARATION.md).
