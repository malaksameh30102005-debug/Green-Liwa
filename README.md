# South Liwa: Relative Soil Salinity Screening with Sentinel-2

**Arab Youth Hackathon Challenge 813 | Track: Precision Agriculture & Smart Crop Analytics**

## Overview
This project screens a study area in South Liwa, UAE, using Sentinel-2 satellite imagery to assess land condition as the basis for a proposed solution: solar-powered desalination, precision irrigation (water demand by crop type and growth stage), and land reclamation.

## Study area
- Location: South Liwa, UAE
- Bounding box: 53.8904°E to 53.9404°E, 23.0743°N to 23.1243°N (about 28 km²)
- Period analysed: January to September 2026

## What the notebook does
`South_Liwa_Salinity_Screening.ipynb` (Python, Google Colab, Earth Engine API):
1. Builds cloud-masked Sentinel-2 composites for two periods and computes NDVI, NDMI, NDWI, SI and NDSI.
2. Classifies pixels into 5 **relative** spectral salinity-risk classes and tests whether high-risk pixels persist across both periods.
3. Plots monthly NDVI, NDMI and SI time series for the study area, a candidate hotspot, and reference farms.
4. Checks the candidate hotspot against the rest of the study area.
5. Computes elevation and slope (SRTM) for a project plot, to assess dune terrain.
6. Exports the final maps to Google Drive.

## Data sources
- Sentinel-2 SR Harmonized (Copernicus, via Google Earth Engine)
- SRTM 30 m elevation (USGS)
- ESA WorldCover (land cover)

## Key findings
- The study area is mostly bare, dry sand with very low vegetation (NDVI about 0.07 to 0.11), unlike irrigated reference farms nearby (NDVI about 0.37 to 0.47).
- The candidate hotspot did **not** rank among the highest spectral salinity signals in the study area, so **salinity is not confirmed** at this location. The site is better described as land needing reclamation.
- The terrain is dune terrain (plot elevation range about 32 m, mean slope about 5°), which is a cost constraint. The proposal addresses it with a phased pilot, siting on the flattest sub-area, native windbreaks and contour-aligned drip irrigation.

## Limitations
- The indices are **relative spectral proxies**, not measured salinity (% or dS/m). Calibration with field electrical conductivity (EC) measurements is required, and none were available to the team.
- Reference farms are detected automatically (NDVI > 0.3) and should be verified on high-resolution imagery.
- SRTM is 30 m, so terrain values are indicative only.
- Groundwater cannot be observed directly from optical imagery; well data would be needed.

## How to run
1. Open the notebook in Google Colab (File > Open notebook > GitHub, or upload the `.ipynb`).
2. Create or use a Google Cloud project with Earth Engine enabled.
3. In the second code cell, replace `YOUR_GOOGLE_CLOUD_PROJECT_ID` with your project ID.
4. Run the cells in order. The first run asks you to sign in to Google.

## References
- FAO Irrigation and Drainage Paper 56 (crop evapotranspiration) and Paper 29 (water quality for agriculture)
- Douaoui et al. (2006), salinity index (SI)
- Khan et al. (2005), normalized difference salinity index (NDSI)
- [Add the full citations before submission]

## Team
- Youmna
- Malak
- Assem
- Leen
- Maha
