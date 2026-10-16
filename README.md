# 🔥 Forest Fire Detection from Satellite Imagery

A satellite-imagery-based forest fire detection project focused on identifying wildfire-affected regions and generating spatial fire masks from remote-sensing data.

The project combines **satellite imagery, fire-related geospatial data, image preprocessing, CNN-based learning, and quantitative evaluation** to build a workflow for detecting and visualizing wildfire activity.

---

## 🌲 Project Overview

Wildfires can spread rapidly across large and difficult-to-access regions, making satellite imagery a valuable source for large-scale monitoring.

This project explores an automated pipeline that takes satellite imagery and associated fire information and produces:

* 🔥 Fire / non-fire detection
* 🗺️ Spatial fire masks
* 📊 Quantitative evaluation
* 🛰️ Geographic visualization
* 🎯 Confidence and FRP-based masks
* 🧪 QA overlays for visual inspection

The objective is not only to classify whether fire is present, but to investigate **where fire-related activity occurs within the imagery**.

---

## 🛰️ Data

The project uses satellite-derived wildfire data, including fire-related observations and rasterized mask products.

The processing pipeline generates different mask representations, including:

```text
masks/
├── confidence/
└── frp/
```

The generated raster files are intentionally **not included in the Git repository** because individual TIFF files can exceed 100 MB.

---

## ⚙️ Workflow

```text
Satellite / Fire Data
        │
        ▼
Data Preparation
        │
        ▼
Image & Mask Generation
        │
        ▼
Patch Extraction
        │
        ▼
CNN Training
        │
        ▼
Fire Detection
        │
        ├───────────────┐
        ▼               ▼
Fire Masks         Confidence / FRP
        │               │
        └───────┬───────┘
                ▼
        QA & Visualization
                │
                ▼
        Quantitative Results
```

---

## 🧠 Model

A **Convolutional Neural Network (CNN)** is used to learn spatial patterns associated with wildfire activity.

The training workflow is contained in:

```text
cnn_training.ipynb
```

The primary detection workflow and experiments are documented in:

```text
forest_fire_detection_v2 (2).ipynb
```

---

## 📁 Repository Structure

```text
Forest Fire Detection/
│
├── cnn_training.ipynb
├── forest_fire_detection_v2 (2).ipynb
│
├── README.md
├── .gitignore
│
├── data/                 # Raw/source data — not tracked
│
├── masks/                # Generated raster masks — not tracked
│   ├── confidence/
│   └── frp/
│
├── patches/              # Generated image patches — not tracked
│
├── qa_overlays/          # Visual QA overlays — not tracked
│
├── results/              # Generated results / visualizations
│
├── models/               # Trained model files
│
└── patch_index.csv       # Generated patch metadata
```

---

## 📊 Outputs

The project generates several types of outputs for analysing model behaviour and wildfire detection.

### Fire Masks

Spatial masks representing detected fire-related regions.

### Confidence Masks

Raster representations based on confidence-related information.

### FRP Masks

Fire Radiative Power (FRP)-related spatial masks used in the analysis.

### QA Overlays

Visual overlays are generated to compare the original satellite imagery with the corresponding fire masks and detection results.

These are particularly useful for manually inspecting:

* Detection quality
* Spatial alignment
* False positives
* False negatives
* Mask boundaries

---

## 🔬 Evaluation

The project evaluates the detection pipeline using both **quantitative metrics and visual inspection**.

The notebooks contain the experiments, generated results, plots, masks, and QA visualizations used to analyse model performance.

---

## 🧪 Reproducing the Project

### 1. Clone the repository

```bash
git clone https://github.com/JainHarsh00/Forest-Fire-Detection.git
cd Forest-Fire-Detection
```

### 2. Create an environment

Using Conda:

```bash
conda create -n wildfire python=3.10
conda activate wildfire
```

Or using Python virtual environments:

```bash
python -m venv .venv
```

### 3. Install dependencies

If a `requirements.txt` is provided:

```bash
pip install -r requirements.txt
```

### 4. Obtain the required satellite/fire dataset

Place the required source data inside:

```text
data/
```

The generated raster masks and patches should then be produced using the preprocessing workflow in the notebooks.

### 5. Run the notebooks

Start Jupyter:

```bash
jupyter notebook
```

Then run:

```text
cnn_training.ipynb
```

followed by:

```text
forest_fire_detection_v2 (2).ipynb
```

---

## 📌 Large Files

Large generated files are intentionally excluded from version control.

Examples include:

```text
*.tif
*.tiff
masks/
patches/
qa_overlays/
results/
models/
```

This keeps the repository lightweight and focused on the **code, methodology, experiments, and reproducibility workflow** rather than storing large raster datasets.

---

## 🚀 Future Improvements

Potential extensions of this project include:

* Real-time wildfire monitoring
* Larger multi-region training datasets
* Improved segmentation architectures
* Temporal satellite-image analysis
* Automated geospatial alert generation
* Integration with GIS platforms
* Deployment as a wildfire monitoring service
* Evaluation across different geographical regions and fire seasons

---

## 👨‍💻 Author

**Harsh Jain**

B.Tech — Artificial Intelligence & Machine Learning

---

## 📄 Project Status

🚧 **Research / Development Project**

This repository contains the implementation, experiments, visualizations, and analysis developed as part of a wildfire detection study using satellite imagery.
