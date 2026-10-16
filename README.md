# Season-Aware Machine Learning Framework for Flood Susceptibility Mapping in Kerala

This repository implements a season-aware machine learning framework for dynamic flood susceptibility modeling across Kerala, India. The workflow integrates static topographic and geomorphological conditioning factors with dynamic, seasonal hydrometeorological predictors at a 90m spatial resolution.

## Repository Structure

```text
season-aware-ml-framework/
├── aligned_layers/        # Static conditioning factor rasters (11 GeoTIFF layers, aligned & cropped)
├── seasonal_factors/      # Dynamic seasonal predictor rasters (6 GeoTIFF layers, pre/post-monsoon)
├── code.ipynb             # Primary Jupyter Notebook for feature extraction, model training, and evaluation
├── features.csv           # Extracted multi-factor tabular dataset for model training and validation
├── features_2019.csv      # Temporal validation dataset corresponding to the 2019 Kerala flood event
├── kerala.geojson         # Study area boundary vector for Kerala State
├── requirements.txt       # Python package dependencies
├── .gitignore             # Git exclusion rules for temporary and auxiliary GIS files
└── README.md              # Project documentation
```

## Spatial Data Specifications

* **Study Area:** Kerala, India (`kerala.geojson`)
* **Spatial Resolution:** 90m x 90m
* **Coordinate Reference System (CRS):** EPSG:7781
* **Static Predictors (`aligned_layers/`):** 11 core topographic, hydrological, and anthropogenic rasters (e.g., Elevation, Slope, TWI, Distance to Streams/Roads, LULC).
* **Dynamic Predictors (`seasonal_factors/`):** 6 seasonal meteorological and vegetation rasters capturing pre-monsoon and monsoon conditions (e.g., CHIRPS Precipitation, Antecedent Soil Moisture, CAPE, NDVI).

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/YOUR-USERNAME/season-aware-ml-framework.git
cd season-aware-ml-framework
```

### 2. Set Up Isolated Jupyter Kernel & Dependencies
You can install the dependencies directly inside the running notebook or set up an isolated virtual environment kernel. Both options use **python** version **3.10.22**.

**Option A: Inside `code.ipynb` (Quickest)**
Run the following in the first cell of the notebook to install packages directly to the active kernel:
```python
%pip install -r requirements.txt
```

**Option B: Dedicated Virtual Environment Kernel**
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install ipykernel
pip install -r requirements.txt
python -m ipykernel install --user --name=season-ml-env --display-name="Python (Season-Aware ML)"
```

### 3. Run the Workflow
Launch Jupyter to run the data preprocessing, feature engineering, and machine learning model evaluation pipeline:

```bash
jupyter notebook code.ipynb
```

## License
This project is open source and available for research and educational purposes.