Machine Learning in Health Care Enforcement
==============================

This project analyzes California healthcare enforcement actions to explore connections between the narrative text of accident reports and the size of the fines levied against hospitals and nursing homes. Using natural language processing tools and Latent Dirichlet Allocation (LDA) models, I identified 8 narrative topics in the 2,883 incident reports published by California's Department of Public Health. I then demonstrate that incidents with a primary topic of cardiovascular emergencies or elder abuse are associated with a fine of about $12,000 each, compared to an average of only $1,800 for incidents with a primary topic of diabetes or paperwork. The topics identified by the LDA model held up very well against new test data, and could be used to correctly identify 96% of the cases where the fine was over $5,000, even though only 27% of the total fines were over $5,000.

Fines By Topic
============================
Fines varied significantly by topic within the LDA model, suggesting areas where hospital administrators can focus their efforts to most efficiently reduce liability and promote patient health.
![](https://github.com/JGreenLowe/HealthEnforcement/blob/master/reports/figures/Fines-by-Topic.png)

List of Trigrams
============================
To process the raw text of the narrative reports, I used tools from the Spacy and Gensim libraries to lemmatize all words in the reports, stripping them of punctuation, whitespace, conjugation, capitalization, and stopwords. I then combined words that frequently occurred together into 2-word bigrams and 3-word trigrams to allow the models to take account of phrases that are more important than the sum of their parts.
![](https://github.com/JGreenLowe/HealthEnforcement/blob/master/reports/figures/List-of-Trigrams.png)

Categorical Fine Models
============================
Different types of models were more effective for different types of prediction: the Gradient Boosting Machine was most effective for predicting what category of fine a report would be associated with (small, medium, or large), and the Random Forest Generator was most effective for estimating the exact amount of a fine to the nearest dollar.
![](https://github.com/JGreenLowe/HealthEnforcement/blob/master/reports/figures/Fine-Models.png)

Intertopic Distance Map
============================
Using Principal Component Analysis (PCA), it is possible to graph all of the topics on a two-dimensional grid, with greater distance between topics suggesting a greater difference in meaning. Although the dimensions in PCA are usually abstract, here the x-axis of the graph appears to have a concrete meaning, with topics that are further to the left placing a stronger emphasis on physical medicine, and topics that are further to the right placing a stronger emphasis on money, fraud, and paperwork. 
![](https://github.com/JGreenLowe/HealthEnforcement/blob/master/reports/figures/Intertopic-Distance-Map.png)

Terms by Topic
============================
Each of the eight primary topics is made up a list of words that define that topic. The image below is a snapshot of a visualization tool that allows viewers to explore the definition of each topic from a sliding scale of perspectives: as the slider bar moves to the right, the display shows words that are very common in both a specific topic and the general corpus, and as the slider bar moves to the left, the display shows words that are unique to a particular topic and do not appear often in the general corpus.
![](https://github.com/JGreenLowe/HealthEnforcement/blob/master/reports/figures/Terms-By-Topic.png)



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
