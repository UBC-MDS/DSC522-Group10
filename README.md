<figure>
    <img src="img/CardioPredict.png" alt="Alt text for image" width="800" height="400">
    <figcaption>Created by DALL-E</figcaption>
</figure>

# CardioPredict: Assessing Heart Disease Risk

![Python](https://img.shields.io/badge/lanaguge-Python-blue.svg)
![codesize](https://img.shields.io/github/languages/code-size/UBC-MDS/DSCI522-Group10)
![GitHub release (latest by date including pre-releases)](https://img.shields.io/github/v/release/UBC-MDS/DSCI522-Group10?include_prereleases)
![GitHub last commit](https://img.shields.io/github/last-commit/UBC-MDS/DSCI522-Group10)
![GitHub pull requests](https://img.shields.io/github/issues-pr/UBC-MDS/DSCI522-Group10)
![GitHub](https://img.shields.io/github/license/UBC-MDS/DSCI522-Group10)
![contributors](https://img.shields.io/github/contributors/UBC-MDS/DSCI522-Group10)

> CardioPredict harnesses the power of logistic regression and k-Nearest Neighbours to analyze key health indicators and provide a predictive model for assessing the risk of coronary heart disease in individuals.

Author: Joey Wu, He Ma, Sandy Gross and Doris Wang

# Project Overview

This project utilizes the Framingham Heart Study dataset to develop and evaluate two classification models, Logistic Regression and k-Nearest Neighbours (kNN), for coronary heart disease risk. The Framingham Heart Study is a comprehensive and long-term research project focused on understanding the factors contributing to cardiovascular health. Our model aims to utilize this dataset to identify the major risk factors to heart disease and effectively predict heart disease risk for individuals. The Logistic Regression model, optimized for recall, achieved a modest accuracy but excelled in identifying disease presence, albeit with many false positives. The kNN model, after addressing class imbalance through oversampling, showed improved recall but reduced accuracy. Both models underscore the need for further refinement in feature analysis and data preprocessing to enhance predictive accuracy, highlighting the potential for collaboration in healthcare to advance disease prediction methods.

Final report: [heart_analyis_model.html](https://ubc-mds.github.io/CardioPredict/heart_analyis_model.html)

# Installation and Setup

To get started with CardioPredict on your local machine, follow these steps:

## Usage via Virtual Envrionment

First time running the project, run the following from the root of this repository:

```shell
conda env create --file environment.yaml
```

To run the analysis, run the following from the root of this repository:

```shell
conda activate 522-project-disease
jupyter lab 
```

Open `heart_disease_analysis.ipynb` or `heart_analyis_model.ipynb` in Jupyter Lab and under the "Kernel" menu click "Restart Kernel and Run All Cells...".

## Usage via Docker

1. Install Docker
2. Clone the GitHub Repository
   Clone the CardioPredict project repository to your local machine using the following command in your terminal or command prompt:
3. Running the Analysis
   Navigate to the Project Directory
   Use the command line to navigate to the root directory of the cloned CardioPredict project:
   Run the following command to build and start the Docker container:

```shell
docker compose up
```

4. Access Jupyter Lab
   After running the above command, Docker will start Jupyter Lab.
   Look for a URL in the terminal output that starts with [http://127.0.0.1:8888/lab?token=]().
   Copy this URL and paste it into your web browser to access Jupyter Lab.
   Run the Analysis Notebook

   In Jupyter Lab, navigate to and open the heart_analyis_model.ipynb notebook (or the relevant notebook for your analysis).
   To run the analysis, go to the "Kernel" menu in Jupyter Lab, and select "Restart Kernel and Run All Cells...".

5. Clean Up
   To stop the Docker container, go back to your terminal where you launched the container.
   Press Ctrl + C to shut it down.
   Remove the Container

   After shutting down the container, you can remove the stopped containers and associated resources by running:

```shell
docker compose rm
```

## Dependencies

* `conda` (version 23.9.0 or higher)
* `nb_conda_kernels` (version 2.3.1 or higher)
* Python and packages listed in [environment.yaml](environment.yaml)

## Running Tests with pytest

To ensure the reliability and correctness of the functionalities in the CardioPredict project, we have provided comprehensive tests in the test/ directory. To run these tests, simply navigate to the root of the project in your command line interface and execute pytest. This command will automatically discover and run all test files located in the test/ directory that are designed to validate the code in the src/ directory.

# Data

CardioPredict is based on data from the [Framingham Heart Study](https://clinicaltrials.gov/study/NCT00005121), an extensive cohort study that tracks health metrics related to heart disease. The full Framingham dataset, encompassing data from the first 32 clinical exams and event follow-up until 2018, is available upon request from the [National Institutes of Health](https://biolincc.nhlbi.nih.gov/studies/framcohort/).

## Source Data

For this project, we utilized a refined subset obtained from [Paul Blanche\'s dataset](https://paulblanche.com/files/DataFramingham.html), which contains 1,363 records detailing key health indicators such as age, blood pressure, cholesterol, smoking habits, and occurrences of heart disease.

## Data Overview

The dataset includes variables such as age, gender, blood pressure, cholesterol levels, and smoking habits, analyzed to predict the likelihood of developing heart disease.

| Variable | Explanation                                                            |
| -------- | ---------------------------------------------------------------------- |
| sex      | sex (Female/Male)                                                      |
| AGE      | Age in years                                                           |
| FRW      | "Framingham relative weight" (pct.) at baseline (52-222)               |
| SBP      | systolic blood pressure at baseline mmHg (90-300)                      |
| DBP      | diastolic blood pressure at baseline mmHg (50-160)                     |
| CHOL     | cholesterol at baseline mg/100ml (96-430)                              |
| CIG      | cigarettes per day at baseline (0-60)                                  |
| disease  | 1 if coronary heart disease occurred during the follow-up, 0 otherwise |

# Code structure

The project is structured as follows:

```bash
├── data
│   └── framingham.csv
├── heart_analyis_model.ipynb
├── heart_analyis_model.html
├── tests
    └── test_logistic_regression_evaluation.py
    └── test_run_knn_analysis.py
    └── test_create_pairwise_scatter_plot.py
    └── test_run_split.py
├── src
    └── create_pairwise_scatter_plot.py
    └── logistic_regression_evaluation.py
    └── run_knn_analysis.py
    └── run_split.py
├── Img
│   └── CardioPredict.png
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── environment.yaml
├── Dockerfile
├── docker-compose.yml
├── LICENSE
└── README.md
```

# Results and Evaluation

The Logistic Regression model achieved an accuracy of 55.3% and a recall of 84%, effectively identifying disease presence but also resulting in many false positives. The class-balanced kNN model showed a recall of 51.7% and an accuracy of 63.7%. The model's performance metrics and graphs are included in the final report.

# Future Work

Future extensions of this project could include exploring more complex models, incorporating more variables, and applying the model to other datasets to validate its robustness.

# References

- Framingham Heart Study. 2023. [https://www.framinghamheartstudy.org/](https://www.framinghamheartstudy.org/)
- National Heart, Lung, and Blood Institute. 2021. Framingham Heart Study Longitudinal Data Documentation for Teaching Dataset. [https://biolincc.nhlbi.nih.gov/media/teachingstudies/FHS_Teaching_Longitudinal_Data_Documentation_2021a.pdf](https://biolincc.nhlbi.nih.gov/media/teachingstudies/FHS_Teaching_Longitudinal_Data_Documentation_2021a.pdf)
- Andersson C, Johnson A D, Benjamin E J, et al. 2019. 70-year legacy of the Framingham Heart Study. Nature Reviews Cardiology, 2019, 16(11): 687-698. [https://www.nature.com/articles/s41569-019-0202-5](https://www.nature.com/articles/s41569-019-0202-5)
- World Heart Report 2023. 2023. World heart report 2023 confronting the world's number one killer.[https://world-heart-federation.org/wp-content/uploads/World-Heart-Report-2023.pdf](https://world-heart-federation.org/wp-content/uploads/World-Heart-Report-2023.pdf)
- World Heart Federation. 2023. Deaths from Cardiovascular Disease Surged 60% Globally Over the Last 30 Years: Report.[https://world-heart-federation.org/news/deaths-from-cardiovascular-disease-surged-60-globally-over-the-last-30-years-report/](https://world-heart-federation.org/news/deaths-from-cardiovascular-disease-surged-60-globally-over-the-last-30-years-report/)
- World Health Organization. 2023. Cardiovascular diseases (CVDs). [https://www.who.int/news-room/fact-sheets/detail/cardiovascular-diseases-(cvds)](https://www.who.int/news-room/fact-sheets/detail/cardiovascular-diseases-(cvds))

# License

This project is released under [MIT License](https://opensource.org/license/mit/).
