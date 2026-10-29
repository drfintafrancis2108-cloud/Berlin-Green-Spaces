# Mapping Land Use and Green/Open Spaces in Berlin

## Overview

This independent project explores the use of geospatial data to visualise and describe land-use patterns across Berlin. It combines an initial thematic mapping exercise in QGIS with descriptive analysis and data visualisation in R.

The project is an ongoing practical exercise in GIS, spatial data handling, descriptive statistics, and reproducible research, with an interest in applications to environmental epidemiology.

## Research questions

1. How are recorded land-use areas distributed across Berlin's 12 districts?
2. How do the recorded areas of selected green/open-space categories vary between districts?
3. How sensitive are district-level green/open-space totals to alternative category definitions?

## Data

* **Source:** Berlin Environmental Atlas
* **Dataset:** Land-use and green/open-space inventory
* **Reference year:** 2021
* **Original format:** GeoPackage (`.gpkg`)
* **Key land-use attribute:** `enutzung`
* **Area attribute:** `flalle` (area in square metres, according to the dataset metadata)
* **Coordinate reference system:** ETRS89 / UTM zone 33N (EPSG:25833)

The dataset contains multiple land-use categories and should not be interpreted as representing only green spaces.

## Workflow

### 1. Geospatial mapping in QGIS

* Imported the GeoPackage into QGIS.
* Inspected the available attributes and coordinate reference system.
* Created a categorised thematic map using the `enutzung` field.
* Prepared a print layout with a title, legend, and source note.
* Exported the map as a PNG.
* Investigated spatial data quality, including geometry validity and a potential overlap issue.

### 2. Descriptive analysis in R

* Prepared a district-by-category summary table from the mapped land-use data.
* Examined the distribution of recorded land-use categories across districts.
* Converted recorded area totals from square metres to hectares.
* Created plots to compare recorded land-use area between districts.

### 3. Sensitivity analysis

Two operational definitions of green/open space were compared:

* **Narrow definition:** selected categories such as forests, parks/green spaces, allotment gardens, meadows and pastures, selected fallow areas, and tree nurseries/horticulture.
* **Broader definition:** the narrow definition plus cemeteries, city squares/promenades, and weekend-cottage/allotment-garden-type areas.

The comparison illustrates how the choice of included land-use categories affects the resulting district-level totals.

### 4. Reproducible reporting

The analysis is documented in an R Markdown report that combines code, explanations, summary results, and visualisations. The report can be knitted to HTML in RStudio.

## Outputs

* **QGIS project:** project file (`.qgz`)
* **Thematic map:** exported PNG
* **R analysis:** `QGIS_data_analysis_Berlin.Rmd`
* **HTML report:** `QGIS_data_analysis_Berlin.html`
* **Derived data:** district-by-category summary CSV

See the repository folders for the available files.

## Key considerations and limitations

* This is an exploratory, descriptive analysis rather than a completed environmental exposure assessment.
* The selected categories are analytical definitions of green/open space, not necessarily an official or validated measure of green-space availability.
* Recorded land-use area does not directly measure public accessibility, quality, proximity, or individual exposure to green space.
* District-level summaries do not establish associations with health outcomes.
* Geometry validity does not rule out overlapping polygons. Potential overlaps require appropriate spatial checks, and the results should be interpreted in light of the data-quality assessment.
* The analysis uses a 2021 dataset and does not assess changes over time.

## Tools

* QGIS
* R and RStudio
* R Markdown
* `readr`, `dplyr`, and `ggplot2`

## Map output

![Berlin land-use map](berlin_land_use_map.png)

## Data source

Berlin Environmental Atlas. Land-use and green/open-space inventory (2021). Consult the original dataset and its metadata for the definitions, coverage, and limitations of the recorded categories.
