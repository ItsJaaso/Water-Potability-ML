# Water Potability — Machine Learning Project

**Student:** Joel Elizee | **Student ID:** joeeli7267

## Overview
This ECPI course project examines 3,276 water-quality samples (9 measurements and a binary `Potability` target) in a sequence of five parts. The data include missing values for pH, Sulfate, and Trihalomethanes. This is an educational data-science exercise, **not an approved drinking-water safety assessment**.

## Analytical tasks and results
| Task | Technique | Part 4 held-out result |
|---|---|---|
| Classification: predict potability | Tuned Random Forest | Accuracy ~63.72% (vs Part 3 66.16%) |
| Regression: predict pH | Tuned Random Forest Regressor | MAE ~1.2248; R² ~0.013 |
| Clustering: detect water-quality profiles | Tuned K-means with PCA | Test silhouette ~0.0823; k=2 |

**Part 5** simulates three changes on the classification model: pH moderation, higher solids/turbidity, and lower chloramine/trihalomethane measures. It also tests sensitivity to Solids and Turbidity. These scenarios reflect model response to invented feature changes, **not causal treatment effects**.

## Files
- `Water_Potability_EDA_Preprocessing.ipynb` — Part 2: exploration and preprocessing
- `Water_Potability_Model_Training.ipynb` — Part 3: train/evaluate three models
- `Water_Potability_Part4_Optimization.ipynb` — Part 4: tune three models
- `Water_Potability_Part5_Scenario_Analysis.ipynb` — Part 5: scenarios and sensitivity
- `water_potability.csv` — provided course dataset
- `requirements.txt` — Python package dependencies

## How to run
1. Use Python 3.10+ and create/activate a virtual environment.
2. Run `python -m pip install -r requirements.txt`.
3. Launch `jupyter notebook` from this directory.
4. Open Part 2, Part 3, Part 4, then Part 5 and run each notebook top to bottom. Each one independently reads `water_potability.csv`; the order is for instructional continuity.
5. Part 5 recreates the Part 4 optimized classification search with seed 42, so the results are reproducible without saving a model pickle.

## Limitations / ethics
Missing values are median-imputed on the training data; target pH is not imputed for regression. Model accuracy is limited, the source dataset's representativeness is not independently verified, and model-generated scores must not be used to decide if water is safe to drink. Scenarios can be physically unrealistic and do not prove causation.

## Repository and instructor access
Create a GitHub repository, upload this project, copy its real URL into the Part 5 Word report, and invite your instructor using the GitHub username supplied by your school. No instructor username is assumed here.
