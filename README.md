Machine Learning in Health Care Enforcement
==============================

This project analyzes California healthcare enforcement actions to explore connections between the narrative text of accident reports and the size of the fines levied against hospitals and nursing homes. Using natural language processing tools and Latent Dirichlet Allocation (LDA) models, I identified 8 narrative topics in the 2,883 incident reports published by California's Department of Public Health. I then demonstrate that incidents with a primary topic of cardiovascular emergencies or elder abuse are associated with a fine of about $12,000 each, compared to an average of only $1,800 for incidents with a primary topic of diabetes or paperwork. The topics identified by the LDA model held up very well against new test data, and could be used to correctly identify 96% of the cases where the fine was over $5,000, even though only 27% of the total fines were over $5,000.

Sample Images
============================

![](https://github.com/JGreenLowe/HealthEnforcement/blob/master/Fines-by-Topic.png)
![](https://github.com/JGreenLowe/HealthEnforcement/blob/master/List-of-Trigrams.png)
![](https://github.com/JGreenLowe/HealthEnforcement/blob/master/Fine-Models.png)
![](https://github.com/JGreenLowe/HealthEnforcement/blob/master/Intertopic-Distance-Map.png)


Project Organization
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.testrun.org


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
