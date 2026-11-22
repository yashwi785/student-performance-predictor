# Student Performance Predictor

Predicts a student's final grade (G3, scale 0-20) from study habits, background and earlier grades, using scikit-learn.

**Dataset:** UCI Student Performance (math class), 395 students, 33 columns. By P. Cortez and A. Silva.

## Results

| Model | Features | MAE (grade points) | R2 |
|---|---|---|---|
| Linear Regression | with G1, G2 | 1.65 | 0.72 |
| Linear Regression | without G1, G2 | 3.40 | 0.14 |
| Random Forest | with G1, G2 | 1.17 | 0.81 |
| Random Forest | without G1, G2 | 3.08 | 0.27 |

## Findings

- Earlier grades (G1, G2) are by far the strongest predictors of the final grade.
- Without them, the model explains much less (R2 0.27). Absences and past failures are the most important remaining features, followed by health, going out and age.
- Some students have a final grade of 0, which is hard to predict from this data.
- Feature importance shows what the model uses, not what causes grades.

## Project structure

- `01_exploration.ipynb`: data exploration and charts
- `02_baseline_model.ipynb`: model training and comparison
- `data/`: dataset
- `requirements.txt`: dependencies

## Run it

    pip install -r requirements.txt
    jupyter notebook

## Next steps

- Tune the Random Forest and try other models
- Save the best model and serve predictions with FastAPI
