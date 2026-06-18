# Football Player Performance Analytics

## Overview

This project analyzes football player statistics from the 2022–2023 season to explore player performance, create comparable metrics, and identify player profiles using data analysis and basic machine learning techniques.

The main goal is to build an end-to-end data science portfolio project covering data understanding, cleaning, exploratory analysis, feature engineering, clustering, visualization, and documentation.

## Project Goals

* Understand the structure and quality of the dataset
* Clean and prepare player statistics for analysis
* Create performance metrics such as per-90 indicators
* Explore player performance by position, club, and competition
* Identify player profiles using clustering techniques
* Build visualizations and a Power BI dashboard for scouting-style insights
* Document the full analytical process in a reproducible way

## Dataset

The project uses the public Kaggle dataset:

**2022–2023 Football Player Stats**
Source: Kaggle — `vivovinco/20222023-football-player-stats`

The dataset contains player-level statistics from the 2022–2023 football season, including performance indicators related to minutes played, goals, assists, shooting, passing, defensive actions, possession, and aerial duels.

## Current Status

This project is currently in the **data cleaning and preparation phase**.

Completed work includes:

* Set up the repository structure
* Created a Python virtual environment
* Installed core data analysis dependencies
* Downloaded the dataset
* Created the first notebook: `01_data_understanding.ipynb`
* Loaded and inspected the dataset
* Checked dataset shape, data types, available columns, missing values, and duplicated rows
* Documented the first observations about the dataset
* Started the data cleaning notebook: `02_data_cleaning.ipynb`
* Checked missing values and duplicated records
* Applied a minimum minutes filter to create an analysis-ready dataset
* Compared the original dataset shape with the filtered dataset shape
* Documented the reasoning behind removing players with fewer than 300 minutes

## Initial Findings

The initial data understanding notebook identified that:

* The dataset contains **2,689 rows** and **124 columns**
* The data is structured at the player level
* The dataset includes player identification columns, such as player name, nationality, position, squad, and competition
* Most columns contain numerical performance metrics, which are useful for future analysis and feature engineering
* Only one missing value was found, in the `Nation` column
* No duplicated rows were found

Overall, the dataset appears to be well structured and suitable for the next steps of the project.

## Data Cleaning Decisions

During the data cleaning phase, a minimum minutes filter was applied to reduce noise caused by very small sample sizes.

Players with fewer than **300 minutes played** were removed from the analysis-ready dataset. This decision was made because players with limited playing time may have inflated or unstable per-90 metrics, making comparisons unfair against players who played a more representative number of minutes.

The original dataset shape was:

```text
(2689, 124)
```

After applying the 300-minute filter, the filtered dataset shape became:

```text
(1832, 124)
```

This means the analysis-ready dataset keeps players with a more representative amount of playing time while preserving the same number of columns.

The raw dataset remains unchanged. The filtered version will be used for the main exploratory analysis, feature engineering, rankings, and clustering steps.

## Planned Analysis

The project will be developed in stages:

1. Data understanding
2. Data cleaning
3. Exploratory data analysis
4. Feature engineering
5. Player clustering
6. Dashboard creation
7. AI-assisted scouting summary
8. Final documentation and portfolio presentation

## Future Feature: Scouting Profile Finder

A planned feature of this project is the **Scouting Profile Finder**, a scouting-oriented tool that allows users to search for players based on specific role requirements.

Instead of simply ranking players by raw numbers, the user would define the type of player they are looking for, select relevant metrics, and assign weights to each characteristic.

For example, a club looking for a ball-playing center back could prioritize progressive passes, long passing accuracy, defensive actions, aerial duel success, and low error rate. The system would then calculate a role-based scouting score and return a ranked list of players who best match that profile.

This feature aims to make the project more realistic and decision-oriented by connecting statistical analysis with practical scouting needs.

## Repository Structure

```text
football-player-performance-analytics/
├── data/
│   ├── raw/
│   └── processed/
├── docs/
│   ├── analytical_questions.md
│   └── scouting_profile_finder.md
├── notebooks/
│   ├── 01_data_understanding.ipynb
│   └── 02_data_cleaning.ipynb
├── src/
├── dashboard/
├── assets/
├── requirements.txt
├── .gitignore
└── README.md
```

## Main Tools

* Python
* pandas
* numpy
* matplotlib
* scikit-learn
* Jupyter Notebook
* Power BI
* Git/GitHub

## Setup

Create a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Register the environment as a Jupyter kernel:

```bash
python -m ipykernel install --user --name football-analytics --display-name "Python (football-analytics)"
```

## Downloading the Dataset

The dataset can be downloaded using `kagglehub`:

```python
import kagglehub

path = kagglehub.dataset_download(
    "vivovinco/20222023-football-player-stats",
    output_dir="data/raw",
    force_download=True
)

print("Path to dataset files:", path)
```

## Next Steps

* Finish the data cleaning notebook
* Save the cleaned dataset in `data/processed`
* Save the analysis-ready dataset with the 300-minute filter
* Create or update the data dictionary with the main columns
* Start the exploratory data analysis notebook
* Analyze distributions of age, minutes, goals, assists, and positions
* Compare performance across positions
* Begin identifying metrics that will be useful for per-90 analysis

## Project Positioning

This project is part of my transition from software/front-end engineering into data science and analytics. It combines my background in software development with data analysis, machine learning fundamentals, and business-oriented storytelling.
