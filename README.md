# Multimodal Behavioral State Analysis in Young Adults

This repository contains the data processing and analysis pipeline developed as part of a Master's thesis in Biomedical Engineering.

The project investigates behavioural state transitions in young adults using multimodal data, including wearable-derived activity and physiological measurements, contextual information, weather data, and geospatial mobility features.

The analysis combines data preprocessing, geospatial feature engineering, the implementation of a Finite State Machine (FSM), statistical analysis, and exploratory feature-importance analysis to characterise behavioural patterns and investigate factors associated with transitions between activity states.

# Project Overview

The main objectives of the project were to:

- Integrate multimodal physiological, behavioral, contextual, and mobility data.
- Construct daily participant-level datasets.
- Model behavioural states (with the chosen way to do this being a FSM).
- Analyse the frequency and characteristics of behavioural state transitions.
- Investigate contextual factors associated with transitions.
- Explore mobility and spatial changes before and during selected transitions.
- Asess potentially relevant contextual features.

# Analysis Pipeline

The project follows the general workflow:

```text
Raw multimodal data
        │
        ▼
Data preprocessing
        │
        ├── Participant characteristics
        ├── Activity and physiological data
        ├── Contextual data
        └── Geospatial data
        │
        ▼
Daily multimodal dataset
        │
        ▼
Finite State Machine
        │
        ▼
Behavioral states and transitions
        │
        ├── State distribution analysis
        ├── Transition analysis
        ├── BMI-profile analysis
        └── Contextual transition analysis
                │
                ├── Statistical tests
                ├── Random Forest feature importance
                └── Spatial transition analysis
```

# Repository Structure

```text
.
├── notebooks/
│   ├── 01_data_preparation/
│   │   ├── 01_bmi_profiles.ipynb
│   │   └── 02_preprocess_temporal_data.ipynb
│   │
│   ├── 02_geospatial_analysis/
│   │   ├── 01_high_altitude_exploration.ipynb
│   │   ├── 02_clean_geospatial_data.ipynb
│   │   ├── 03_define_routes.ipynb
│   │   ├── 04_route_features.ipynb
│   │   └── 05_elevation_features.ipynb
│   │
│   └── 03_state_machine/
│       ├── 00_config.ipynb
│       ├── 01_build_daily_dataset.ipynb
│       ├── 02_simulation.ipynb
│       ├── 03_simulation_results.ipynb
│       ├── 03a_simulation_results_perprofile.ipynb
│       ├── 04_transition_general_analysis.ipynb
│       └── 05_transition_specific_analysis.ipynb
│
├── requirements.txt
├── .gitignore
└── README.md
```

The original datasets and generated outputs are intentionally excluded from the repository.

# Notebook Workflow

## 1. Data Preparation

**`01_bmi_profiles.ipynb`**  
Processes participant anthropometric information and derives BMI-based participant profiles.

**`02_preprocess_temporal_data.ipynb`**  
Performs temporal preprocessing/analysis and cleaning of activity, mood, and social-context data.

## 2. Geospatial Analysis

**`01_high_altitude_exploration.ipynb`**  
Explores unusually high altitude observations in the geographical dataset.

**`02_clean_geospatial_data.ipynb`**  
Cleans the geographical dataset and removes implausible altitude observations in the studied area.

**`03_define_routes.ipynb`**  
Identifies participant mobility routes from GPS observations.

**`04_route_features.ipynb`**  
Extracts route-level mobility features.

**`05_elevation_features.ipynb`**  
Calculates elevation-related route features and combines them with the remaining mobility characteristics.

## 3. FFSM and Transition Analysis

**`00_config.ipynb`**  
Defines shared project paths, temporal parameters, and profile-specific FSM thresholds.

**`01_build_daily_dataset.ipynb`**  
Integrates participant characteristics, activity, physiological measurements, stress information, and ActiGraph-derived activity into a daily multimodal dataset.

**`02_simulation.ipynb`**  
Applies the FSM separately to each participant in a sequential day-by-day way and records daily behavioral states and transitions.

**`03_simulation_results.ipynb`**  
Analyses overall state distributions, transition frequencies, transition matrices, and participant-normalised state distributions.

**`03a_simulation_results_perprofile.ipynb`**  
Compares behavioural state distributions across participant profiles.

**`04_transition_general_analysis.ipynb`**  
Combines FSM transitions with demographic, weather, social, and mobility information. Statistical tests are used to investigate associations with behavioural transitions, complemented by Random Forest feature-importance analysis.

**`05_transition_specific_analysis.ipynb`**  
Investigates selected recurrent transitions in greater detail, including contextual comparisons and spatial changes between the day before a transition and the transition day.

##Main Methods

The analysis includes:

- Multimodal data integration
- Daily feature aggregation
- Feature engineering
- Finite State Machine modeling
- Behavioural transition analysis
- Geospatial and mobility analysis
- Mann–Whitney U tests
- Fisher's exact tests
- Chi-square tests
- Random Forest feature-importance analysis
- Stratified cross-validation

# Technologies

The project was developed in Python using libraries including:

- pandas
- NumPy
- SciPy
- scikit-learn
- Matplotlib
- Seaborn
- geopy
- openpyxl

# Installation

Install the required Python packages with:

```bash
pip install -r requirements.txt
```

# Data Availability and Privacy

The original participant-level dataset and derived outputs are not included in this repository due to privacy considerations.

# Reproducibility

The notebooks are organized according to their position in the analysis pipeline and should be executed in sequence.

Because the original research data cannot be publicly distributed, the full analysis cannot be reproduced directly from this repository without access to the underlying dataset.

## Thesis Context

This work was developed as part of the Master's thesis:

**“Intelligent Analysis of Data and Biosignals for the Identification and Assessment of Factors Influencing the Health Status of Young Adults”**

