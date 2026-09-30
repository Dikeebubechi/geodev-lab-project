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

## Built-up Area Result

Using the Asaba study area and Landsat imagery processed in Google Earth Engine, the estimated built-up area was:

* **2000:** 1,310.27 ha (**13.10 km²**)
* **2025:** 3,005.88 ha (**30.06 km²**)

The estimated absolute expansion was:

* **1,695.61 ha**
* **16.96 km²**

This represents an estimated **129.41% increase** in built-up area between 2000 and 2025.

Therefore, the analysis answers the "how much" part of the project question: the built-up area increased by approximately **16.96 km² between 2000 and 2025**.

The 100 m road-buffer analysis provides supporting information for interpreting the spatial relationship between the road network and urban growth. The current analysis does not yet quantify the specific direction of expansion.

## What Surprised Me

The number of buffer features remained exactly the same as the input road features because the buffer was created without dissolving.

The geometry check also showed that all 7,012 output features were valid, with no invalid geometries or errors.

The built-up analysis also showed a substantial increase in the estimated built-up area between 2000 and 2025, from 13.10 km² to 30.06 km².

## What Data I Still Need

To fully answer the project question, I still need additional spatial analysis to determine the **directions of built-up expansion** between 2000 and 2025.

The OSM road network and 100 m road buffer will provide supporting information for interpreting the relationship between urban growth and the road network.

## Week 4 Output

The 100 m road-buffer output was saved as an analysis-ready GeoPackage in:

```text
data/processed/asaba_roads_100m_buffer.gpkg
```

The map showing the 100 m road buffer was exported as a PNG and saved in the project repository.
