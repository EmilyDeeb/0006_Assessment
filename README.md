# Points of Interest as Crime Generators
## A Supervised Regression Analysis of London Ward-Level Crime Density

### Overview
This project examines whether the spatial layout of urban amenities predicts crime density across London wards, and whether specific amenity types are associated with different crime categories. Using open-source POI data from OpenStreetMap and recorded crime data from the Metropolitan Police Service, a supervised regression model assesses crime generators across 679 London wards.

### Research Questions
**Primary:** To what extent does the density of urban amenities predict person/society and property crime densities across London wards?

**Sub-question:** Which specific amenity categories serve as the primary crime generators for each crime type, and do these differ systematically between person/society and property crime?

### Repository Structure
```
├── CASA0006_EmilyDeeb.ipynb    # Main analysis notebook
├── environment.yml              # Conda environment
├── data/                        # Pre-processed data files
│   ├── crime.csv
│   ├── ward_population.csv
│   ├── wards_2024.geojson
│   ├── feature_matrix.csv
│   └── gla/
└── Diagram.png                  # Methodology diagram
```

### Reproducing the Analysis
1. Clone the repository
2. Recreate the environment:
```bash
conda env create -f environment.yml
conda activate urbsim
```
3. Open `CASA0006_EmilyDeeb.ipynb` in Jupyter
4. Run all cells — runtime ~1 minute (pre-processed data loaded from file)

> **Note:** Full data extraction and model training estimated ~45–60 minutes on first run. To run from scratch, follow the instructions in the notebook preparation section.

### Key Findings
- Convenience stores and fast food are the primary generators of person and society crime
- Café density is the dominant predictor of property crime
- Night-time economy venues (bars, pubs, nightclubs) show unexpectedly weak predictive power, consistent with mandatory guardianship of licensed premises suppressing crime opportunity
- Random Forest (R²=0.623 Type A, R²=0.716 Type B) outperforms MLR and KNN baselines

### Data Sources
| Dataset | Source |
|---------|--------|
| MPS recorded crime | [London Datastore](https://data.london.gov.uk) |
| Ward boundaries | [ONS Open Geography Portal](https://geoportal.statistics.gov.uk) |
| POI data | [OpenStreetMap](https://www.openstreetmap.org) via osmnx |
| Ward population | [ONS mid-2021 estimates](https://geoportal.statistics.gov.uk) |

### Environment
- Miniconda 3 · Python 3.x · urbsim environment
- Intel i7-10700 @ 2.90GHz · 10GB RAM
- Key packages: geopandas, scikit-learn, shap, osmnx, matplotlib, plotly

### Author
Emily Deeb · Student Number: 25127081  
UCL CASA · CASA0006 Data Science for Spatial Systems
