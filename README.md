
# NLP Project about essay evaluation

## Folder Structure using my cookiecutter settings


    ├── .gitignore                <- GitHub's excellent Python .gitignore customized for this project
    ├── LICENSE                   <- Your project's license.
    ├── Pipfile                   <- The Pipfile for reproducing the analysis environment
    ├── README.md                 <- The top-level README for developers using this project.
    │
    ├── data
    │   ├── 0_raw                 <- The original, immutable data dump.
    │   ├── 1_external            <- Data from third party sources.
    │   ├── 2_interim             <- Intermediate data that has been transformed.
    │   └── 3_final               <- The final, canonical data sets for modeling.
    │
    ├── docs                      <- GitHub pages website
    │   ├── data_dictionaries     <- Data dictionaries
    │   └── references            <- Papers, manuals, and all other explanatory materials.
    │
    ├── notebooks                 <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                                the creator's initials, and a short `_` delimited description, e.g.
    │                                `01_cp_exploratory_data_analysis.ipynb`.
    │
    ├── output
    │   ├── features              <- Fitted and serialized features
    │   ├── models                <- Trained and serialized models, model predictions, or model summaries
    |   |   └── mlruns            <- MLflow artifacts 
    │   └── reports               <- Generated analyses as HTML, PDF, LaTeX, etc.
    │       └── figures           <- Generated graphics and figures to be used in reporting
    │
    |
    │
    └── serve                     <- HTTP API for serving predictions
        ├── Dockerfile            <- Dockerfile for HTTP API
        ├── Pipfile               <- The Pipfile for reproducing the serving environment
        ├── app.py                <- The entry point of the HTTP API
        └── tests
            ├── fixtures          <- Where to put example inputs and outputs
            │   ├── input.json    <- Test input data
            │   └── output.json   <- Test output data
            └── test_app.py       <- Integration tests for the HTTP API

## Project objective and data

### Objective

The idea is to develop a [NLP] model to correct English written essays.
My main objective is to put in practice all my knowledge on [NLP], not necessarily submit a prediction or win any prize.

### Data

The essays are graded in 6 aspects:

* cohesion
* syntax
* vocabulary
* phraseology
* grammar
* conventions

The grades for each of the review aspects are graded from 1.0 to 5.0 with increments of 0.5
For this project I choose to join(again) a Kaggle competition, and the data description is:

* train.csv - The training set, comprising the full_text of each essay, identified by a unique text_id. The essays are also given a score for each of the seven analytic measures above: cohesion, etc. These analytic measures comprise the target for the competition.
* test.csv - For the test data we give only the full_text of an essay together with its text_id.
* sample_submission.csv - A submission file in the correct format. See the Evaluation page for details.

*Please note that this is a Code Competition. We give a few sample essays in test.csv to help you author your solutions. When your submission is scored, this example test data will be replaced with the full test set. The full test set comprises about 2700 essays.*

The submission will be scored using MCRMSE - Mean Columnwise root mean squared error

$$ MCRMSE = \frac{1}{N_t} \sum^{N_t}_{j=1}{\sqrt{\frac{1}{n} \sum_{i=1}^{n}(y_{ij}-\hat{y}_{ij})²} } $$
































------

### Links


[NLP]: https://www.ibm.com/cloud/learn/natural-language-processing#:~:text=Natural%20language%20processing%20(NLP)%20refers,same%20way%20human%20beings%20can.

[cohesion]:https://en.wikipedia.org/wiki/Cohesion_(linguistics)
[syntax]:https://en.wikipedia.org/wiki/Syntax
[vocabulary]: https://bit.ly/3Talycd
[phraseology]: https://en.wikipedia.org/wiki/Phraseology
[grammar]: https://en.wikipedia.org/wiki/Grammar
[conventions]: --