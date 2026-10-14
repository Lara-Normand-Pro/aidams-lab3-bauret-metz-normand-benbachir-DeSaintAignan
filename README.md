# AIDAMS Lab 3: Bottom-Up Steel Emissions with Uncertainty

**Course:** Research and Emerging Topics in Data Science: Climate Risks (AIDAMS)
**Group:** Lara Normand, Alix Bauret, Tiphaine De Saint Aignan, Amine BenBachir Hassani, Camille Metz

## What the notebook does

- **Part A: Emissions pipeline.** Builds a plant-level, bottom-up estimate of China's steel CO2 emissions for 2020-2030 from Global Energy Monitor data: operating plants, utilisation by technology (BF-BOF / EAF / Other), plant production, emission factors (Hasanbeigi 2019), company emissions, and a projection to 2030.
- **Part B: Uncertainty quantification.** Checks the results against official worldsteel statistics, fixes the coverage bias (matched plants), and builds 90% intervals with a bootstrap and a Monte Carlo simulation. It then compares three scenarios (no change, 30% BF-BOF retired, demand −10%) and ends with a note for a risk committee.

## Repository contents

| File | Description |
|---|---|
| `lab3.ipynb` | Completed notebook, all cells run with outputs visible |
| `requirements.txt` | Python dependencies |
| `README.md` | This file |

## Data

The dataset is **not included** in the repo (GEM licence, ~0.7 MB). To get it:

1. Go to the [GIST download page](https://globalenergymonitor.org/projects/global-iron-and-steel-tracker/download-data/), select **Iron and steel**, fill in the form and download it.
2. Save `Plant-level_data_Global_Iron_and_Steel_Tracker_June_2026_V1.xlsx` in the same folder as the notebook.

> **Version note.** We used the **June 2026** release, the only one available for download at submission time. The lab was written for the September 2025 release: the sheets are the same, a few column names differ (harmonised at the start of A1), and some figures differ slightly from the values quoted in the questions.

Official China crude steel production (B1): worldsteel, *World Steel in Figures*.

## How to run

```bash
# 1. (optional) create a virtual environment
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate

# 2. install dependencies
pip install -r requirements.txt

# 3. put the .xlsx next to the notebook (see Data), then
jupyter notebook lab3.ipynb
```

Then run **Kernel → Restart & Run All** (about 1 minute). Results are reproducible: all random draws use fixed seeds.

If the dataset is stored somewhere else, set its path with an environment variable instead of moving it:

```bash
GIST_PATH=/path/to/file.xlsx jupyter notebook lab3.ipynb
```

Tested with Python 3.12.
