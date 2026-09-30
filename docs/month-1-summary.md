# Month 1 Summary

## Project Question

How much has the built-up area of Asaba, Delta State, Nigeria expanded between 2000 and 2025, and in which directions has the expansion occurred?

## Spatial Operation

For Week 4, I carried out a **100 m buffer operation** on the clipped OSM road network prepared during Week 3.

The operation was carried out using the projected working CRS:

**EPSG:32632 – WGS 84 / UTM Zone 32N**

The buffer was created without dissolving the output.

## Why I Chose This Operation

I chose the buffer operation because roads provide an important spatial reference for examining urban growth patterns and potential development along transport corridors.

The 100 m buffer creates a road-proximity zone around the existing road network. This provides supporting spatial information for interpreting the relationship between roads and urban growth in the Asaba study area.

The buffer does not by itself measure built-up change between 2000 and 2025. Instead, it provides supporting information that can be considered alongside the historical and current built-up/LULC data required for the main analysis.

## What I Expected

Before running the operation, I expected the 100 m buffer to produce road-proximity polygons around the clipped OSM road network.

I expected the output to contain approximately the same number of features as the input road layer because the buffer was created without dissolving.

I also expected the buffered areas to follow the existing road network and remain within the defined Asaba study area because the roads had already been clipped to the study area during Week 3.

## What I Got

The buffer produced **7,012 features** from the **7,012 input road features**.

The output feature count was therefore consistent with the expectation because the buffer was created without dissolving.

The map inspection showed that:

* the buffer follows the clipped OSM road network;
* the buffer remains within the defined study area;
* no strange polygons were observed away from the road network;
* no obvious gaps were observed; and
* no obvious geometric problems were observed.

A manual inspection of one road feature showed that the corresponding buffer extended approximately **100 m** from the road.

The geometry check produced:

* **Valid features:** 7,012
* **Invalid features:** 0
* **Errors:** 0

This indicates that all 7,012 buffer features passed the geometry check.

## What Surprised Me

The result was generally consistent with my expectations. The number of buffer features remained exactly the same as the input road features because the buffer was created without dissolving.

The geometry check also showed that all 7,012 output features were valid, with no invalid geometries or errors.

## What Data I Still Need

The 100 m road-buffer analysis provides supporting information about the spatial relationship between the road network and areas around the roads. However, it does not directly measure how much built-up area changed between 2000 and 2025.

To answer the main project question, I still need suitable historical and current **built-up/LULC data for the 2000–2025 period**. These data will be used to measure the amount of built-up expansion and determine the direction of urban growth.

The OSM road network will be used as supporting/current reference data rather than as the sole dataset for measuring historical built-up change.

## Week 4 Output

The 100 m road-buffer output was saved as an analysis-ready GeoPackage in:

```text
data/processed/
```

The map showing the 100 m road buffer was exported as a PNG and saved in the project repository.
