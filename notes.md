```
/Users/sibilz/Desktop/000-MSQTM/QTM_25spring/550_1_quantitative_science_project/QGIS_2503/lihtc_test
├── data
│   ├── processed
│   ├── rasters
│   └── raw
├── notes.md
├── output
│   ├── maps
│   └── reports
└── qgis
    └── project.qgz
```



---

QGIS version: 3.42.1-Münster
QGIS code revision: 1fc52835a89
Qt version: 5.15.2
Python version: 3.9.5
GDAL version: 3.3.2
GEOS version: 3.9.1-CAPI-1.14.2
PROJ version: Rel. 8.1.1, September 1st, 2021
PDAL version: 2.3.0 (git-version: Release)
Algorithm started at: 2025-03-27T14:33:20
Algorithm 'Random points in layer bounds' starting…
Input parameters:
{ 'INPUT' : '/Users/sibilz/Desktop/lihtc_test/data/processed/five_counties.gpkg|layername=tl_2023_us_county', 'MIN_DISTANCE' : 1e-06, 'OUTPUT' : 'TEMPORARY_OUTPUT', 'POINTS_NUMBER' : 30 }

Execution completed in 5.76 seconds
Results:
  OUTPUT: Random_points_ecc6d1f1_6137_48b9_ab65_9505d409117c

Loading resulting layers
Algorithm 'Random points in layer bounds' finished

---

# Assign value
Attribute Table -> Field Caculator  -> Expression
round(randf(0, 100))

# change labels
propoerties -> labels -> field 