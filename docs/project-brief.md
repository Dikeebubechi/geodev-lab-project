# Project brief

**Week 1 deliverable.** GeoDev Lab Africa, Cohort One.
Author: Dike Ebubechi

---

## 1. The question

> How much has the built-up area of Asaba, Delta State, Nigeria expanded between 2000 and 2025, and in which directions has the expansion occurred?

## 2. Why this question

Asaba has experienced considerable urban development over the years, and understanding how its built-up area has changed can help show the pattern and direction of urban expansion. Its location along major transportation routes, including the Asaba–Onitsha corridor, also makes it suitable for studying the relationship between urban growth and transportation routes.

This project will provide a spatial view of how much built-up land has increased and where the expansion has occurred between 2000 and 2025.

## 3. Study area

The study focuses on Asaba, Delta State, Nigeria, located on the western bank of the River Niger, opposite Onitsha in Anambra State.

The main study area will cover **Oshimili South Local Government Area**, including adjoining parts of **Oshimili North** where urban development extends beyond the main built-up area.

The approximate central coordinates of Asaba are **6.20°N, 6.73°E**. The study area will be defined using the relevant administrative boundary data, particularly the Oshimili South boundary and adjoining Oshimili North area.

## 4. What I mean by the terms

**Built-up area:** Land covered by buildings and other constructed surfaces associated with urban development.

**Urban growth:** The increase and spatial expansion of built-up areas over time.

**Urban expansion:** The outward spread of built-up areas from existing urban areas into surrounding locations.

**Direction of expansion:** The main spatial directions in which built-up areas have increased between 2000 and 2025.

The project will measure built-up area for selected years and compare the changes to identify the main areas and directions of expansion.

## 5. Datasets

No link, no dataset. Every dataset below has a stated source.

| # | Dataset                             | What it gives me                                                                                                                 | Source                                                                |
| - | ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| 1 | Landsat 5 TM Surface Reflectance    | Satellite imagery for mapping built-up areas and other land-cover classes for 2000, 2005 and 2010.                               | https://developers.google.com/earth-engine/datasets/catalog/landsat-5 |
| 2 | Landsat 8 OLI Surface Reflectance   | Satellite imagery for mapping built-up areas and other land-cover classes for 2015 and 2020.                                     | https://developers.google.com/earth-engine/datasets/catalog/landsat-8 |
| 3 | Landsat 9 OLI-2 Surface Reflectance | Satellite imagery for mapping the most recent built-up area and providing the 2025 reference for comparison.                     | https://developers.google.com/earth-engine/datasets/catalog/landsat-9 |
| 4 | Nigeria Administrative Boundaries   | Administrative boundaries for identifying and defining the study area, particularly Oshimili South and adjoining Oshimili North. | https://grid3.org/                                                    |
| 5 | OpenStreetMap Road Network          | Road network data for examining the relationship between urban expansion and major transportation routes around Asaba.           | OpenStreetMap                                                         |

## 6. What "done" looks like

The completed project will produce built-up area maps for selected years between 2000 and 2025 and a comparison showing how much the built-up area has increased during the study period.

The final analysis will also identify the main directions and areas of urban expansion and examine the relationship between urban growth and major transportation routes around Asaba.

## 7. Known risks

**Cloud cover and image quality.** Cloud cover or poor-quality satellite imagery could affect the classification of built-up areas. Suitable imagery and appropriate image filtering will be used to reduce this problem.

**Classification errors.** Built-up areas may be confused with other land-cover types with similar spectral characteristics. Classification and visual checks will be used to identify and reduce errors.

**Study-area boundary.** Urban development may extend beyond the main administrative boundary of Oshimili South. Adjoining parts of Oshimili North will therefore be considered where urban development extends into the surrounding area.

---

**Status:** Week 1 complete. Data acquisition in Week 2, see
[02-data-notes.md](02-data-notes.md).
