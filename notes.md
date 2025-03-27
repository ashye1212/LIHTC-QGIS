lihtc_qgis/
├── data/                           # All data files are organized here
│   ├── processed/                  # Tracked: processed outputs that are clean and <100MB
│   │   ├── 30_random_points_0326.gpkg     # Tracked: randomly generated test points (March 26 version)
│   │   └── five_counties_atl_0326.gpkg    # Tracked: clipped and processed version of five counties
│   └── raw/                        # Not tracked: raw or large input shapefiles (>100MB)
│       ├── tl_2023_us_county/             # Ignored: original county-level shapefiles (2023)
│       └── tl_2024_13_tract/              # Ignored: original tract-level shapefiles (2024)
├── notes.md                        # Tracked: project notes, versioned with the repo
├── output/                         # Folder for exported figures or maps
│   └── maps/
│       ├── test_0326.pgw           # Tracked: georeferencing world file for the PNG export
│       └── test_0326.png           # Tracked: exported visualization (e.g. map layout screenshot)
└── qgis/
    └── test_0326.qgz              # Tracked: current QGIS project file (March 26 version)


## Next step 
Goal: Build interactive map could be published in the web 
references: https://doculy.ai/lihtc


## Comments in 25-03-26

Hi Team, 

I’m sharing a prototype visualization created in QGIS as part of our effort to explore spatial sampling of potential LIHTC development areas. This version randomly samples points within five Metro Atlanta counties and assigns each point a random value (for now) to simulate location-based scoring potential. The styling is basic but intended as a starting point for feedback.

I’d love your input on the following areas:

1. Reference + Examples:
    - Are there strong examples (internal or external) of map visualizations—either static or interactive—we should use as references?
    - Any QAP-related visualizations you’ve seen that were especially effective?
2. Purpose & Audience
    - Who is the intended audience for this map?
    - What insight or message do we want the reader to walk away with?
3. Deliverables:
    - What output format is ideal for future delivery? Static maps (PDF), QGIS packages, or interactive (e.g., web map or dashboard)?
4. Information content: 
    - Are there key **map elements** missing that we should include (e.g., basemap, legend, annotation)?
    - Should we show raw scores, categories (e.g., low/med/high), or just visual gradients?
5. Spatial Design
    1. Scope & Framing
        - Should we zoom in closer on priority census tracts, or show all of Metro Atlanta?
        - Would it help to include a state-level outline or context (e.g., showing Georgia boundary in gray)?
        - Should the visualization include “known development zones” or past award overlays?
    2.  **Symbology & Labeling**
        1. format suggestions: color,  front choices?



------
## Git Tracking Rules (Notes to Self)
- Do NOT push anything in `data/raw/`
- Use `.gitignore` to avoid large or temporary files
- Check file size with `ls -lh` if unsure
- Identify Large Files (>100MB)
```{bash}
find . -type f -size +90M -exec ls -lh {} \;
```

```{bash}
nano .gitignore

# Save 
Ctrl + X, then press Y, then Enter)

# After editing
git add .gitignore
git commit -m "Update .gitignore to ignore more files"
git push


```


---
## Guide 

# Assign value
Attribute Table -> Field Caculator  -> Expression
round(randf(0, 100))

# Change labels
propoerties -> labels -> field 

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

-
