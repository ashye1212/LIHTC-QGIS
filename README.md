# LIHTC-QGIS Prototype Mapping

This repository contains a QGIS-based prototype for exploring spatial sampling and scoring of potential **Low-Income Housing Tax Credit (LIHTC)** development areas across Metro Atlanta.

(Mar 26)
- The current version randomly samples points within five counties and assigns temporary values to simulate scoring outcomes. The goal is to evolve this prototype into a polished, interactive web map based on stakeholder feedback and real data.

---

## 📁 Project Structure

lihtc_qgis/
├── data/
│   ├── processed/                  # Tracked: cleaned shapefiles (<100MB)
│   │   ├── 30_random_points_0326.gpkg     # Randomly sampled test points
│   │   └── five_counties_atl_0326.gpkg    # Processed five-county boundary
│   └── raw/                        # Not tracked: raw shapefiles (>100MB)
│       ├── tl_2023_us_county/
│       └── tl_2024_13_tract/
├── output/
│   └── maps/
│       ├── test_0326.png           # Exported visualization
│       └── test_0326.pgw           # Georeferencing for PNG
├── qgis/
│   └── test_0326.qgz              # QGIS project file
├── notes.md                       # Project notes
└── .gitignore                     # Rules to avoid uploading large/unnecessary files

---
##  Next Step: Toward Interactive Web Map  (March 27 -> )

We aim to eventually publish this as a web-based map for broader accessibility
- Reference: https://doculy.ai/lihtc

---
##  🗺️ Prototype Overview (March 26)

This map prototype includes:
- **30 random points** generated within selected counties
- **Random value assignment** to each point for test visualization
- **Basic symbology** to differentiate values (gradients)

### Sample Expression (Value Assignment):
> QGIS → Attribute Table → Field Calculator → Expression  
```qgis
round(randf(0, 100))


---
##  Design Feedback Requested(March 27)

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


---
## Git Tracking Rules (For Developers)
	•	Do not push anything under data/raw/
	•	Use .gitignore to exclude large or temporary files
	•	Check file size before pushing:

find . -type f -size +90M -exec ls -lh {} \;

Update .gitignore as needed:

nano .gitignore
git add .gitignore
git commit -m "Update .gitignore"
git push

---
📌 Reproducibility Example

Algorithm Used: Random points in layer bounds
Input: five_counties.gpkg
Points: 30
Execution Time: ~5.76 seconds

