# Processing Big Data Predict
© Explore Data Science Academy

## Student Instructions 👩‍🏫️
This predict contains multiple notebooks that you will be required to update in order to arrive at your solution. To successfully complete this predict you will need to:
 1. log in to your Github account;
 2. [fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo) this repo to create your own remote copy; and
 3. clone the forked repo on your account so you can work with the files locally on your machine.

## Predict overview

You are part of a small dynamic team of Data Scientists trying to create the latest and greatest automated stock market trading robots. You assume the role of a Data Engineer and is responsible for ensuring that the Data Science team has access to high-quality training datasets.

<div align="center" style="width: 600px; font-size: 80%; text-align: center; margin: 0 auto">
<img src="https://raw.githubusercontent.com/Explore-AI/Pictures/master/data_engineering/transform/predict/TradingBot.jpg"
     alt="Trading Bot"
     style="float: center; padding-bottom=0.5em"
     width=50%/>
     <p><em>Figure 1. Trading Bot</em></p>
</div>

You will need to perform data profiling, quality analysis, and testing on the ingested data to ensure that the dataset is of sufficient quality. Data quality analysis and testing have to be done in such a way as to be generic and abstracted to the level where the notebook(s) can be run for any point in time, on a regular schedule, or as part of an ingestion pipeline. 

## Dataset

<div align="center" style="width: 600px; font-size: 80%; text-align: center; margin: 0 auto">
<img src="https://raw.githubusercontent.com/Explore-AI/Pictures/master/data_engineering/transform/predict/Nasdaq.png"
     alt="Nasdaq"
     style="float: center; padding-bottom=0.5em"
     width=50%/>
     <p><em>Figure 2. Nasdaq</em></p>
</div>

The data that you will be working with is a historical snapshot of market data taken from the Nasdaq electronic market. This dataset contains historical daily prices for all tickers currently trading on Nasdaq. The up-to-date list can be found on their [website](https://www.nasdaq.com/).

The dataset for the predict can be found in an AWS S3 bucket called: `processing-big-data-predict-stocks-data`. The bucket contains two items:

- Stock data: [stocks.zip](https://processing-big-data-predict-stocks-data.s3.eu-west-1.amazonaws.com/stocks.zip)
- Metadata: [symbols_valid_meta.csv](https://processing-big-data-predict-stocks-data.s3.eu-west-1.amazonaws.com/symbols_valid_meta.csv)

## Task 1
You need to download the data stored in the S3 bucket and store it on your local machine.

This first step in the data engineering process serves to ingest the data into a working environment which makes it available for wider use for anyone else in the Data Science team.

<div align="center" style="width: 600px; font-size: 80%; text-align: center; margin: 0 auto">
<img src="https://raw.githubusercontent.com/Explore-AI/Pictures/master/data_engineering/transform/predict/DataIngestion.jpg"
     alt="Data Ingestion"
     style="float: center; padding-bottom=0.5em"
     width=40%/>
     <p><em>Figure 3. Data Ingestion</em></p>
</div>

Typically, you will use a specific subset of the dataset to develop your ingestion, data quality and testing process. This ensures that you first create a robust process before starting on the productionisation of the process and code.

In this task, you will be using the first data subset (**1962**) in the dataset as a testing set. 

Some of the reasons for choosing this dataset is:
- it is the first year within the dataset;
- it contains a small portion of the dataset and will be very fast to develop on, while not requiring a lot of computation; and
- since it is the oldest in the dataset, it likely contains the most errors.

At the end of this task, your notebook should be able to produce parquet files for a specific year.



### **Assessment** ⏰️
This section is mainly concerned with the setup and ingestion of the dataset; you will be assessed using multiple-choice questions.

The following actions need to be taken to complete the assessments in this section:

- [ ] Submit Notebook
- [ ] Complete Data Ingestion MCQ

### **Resources** 📕️
The below resource should be used to complete the work found in this section:

- [Data ingestion notebook](./Task1_data_ingestion/Data_ingestion_student_version.ipynb)

## Task 2

After the data has been ingested and basic sense checks have been performed on the dataset, the next step is to ensure that we have a full view of the dataset. This does not refer to exploratory data analysis (EDA) that data scientists are typically familiar with, but rather an exploration of the dataset considering the six (or more) dimensions of data quality.

This ensures that we are completely aware of the data landscape, any possible flaws in the dataset, and characteristics that will have to be considered when building models or performing analytics.

<div align="center" style="width: 600px; font-size: 80%; text-align: center; margin: 0 auto">
<img src="https://github.com/Explore-AI/Pictures/raw/master/data_engineering/transform/predict/DataQuality.jpg"
     alt="Data Quality"
     style="float: center; padding-bottom=0.5em"
     width=100%/>
     <p><em>Figure 4. Six dimensions of data quality</em></p>
</div>



In this section, you will be required to: 

1. Derive summary statistics on the dataset across the six dimensions of data quality; and
2. identify possible concerns in the data quality, and correct any issues identified. 

At the end of this task, you will be required to produce a `csv` file of all the data transformations you have made during your data quality checks.


### **Assessment** ⏰️
This section mainly focuses on transformations required to address the data quality issues found in the dataset. The `csv` file produced will be used to auto-grade your work. You will also be required to complete an MCQ.

The following actions need to be taken to complete the assessments in this section:

- [ ] Submit Notebook
- [ ] Submit `csv` output file
- [ ] Complete Data Profiling MCQ

### **Resources** 📕️
The below resource should be used to complete the work found in this section:

- [Data profiling notebook](./Task2_data_profiling/Data_profiling_student_version.ipynb)



## Task 3
Manually inspecting the data for characteristics and flaws is very powerful but not practical when working with production-grade datasets.

Production systems have several challenges, the largest being:
- **Size**: Incoming data can be so large that manual inspection becomes unfeasible; and
- **Frequency**: Data can arrive at any interval, sometimes being near real-time. At which point, manual inspection would be impossible as well.

This can be mediated by having an automated process for monitoring data quality and performing tests every time the data gets ingested.

In this section, you will be required to set up a generic process on which you can perform continuous data quality monitoring and testing.


### **Assessment** ⏰️

This section will mainly focus on your ability to make use of an automated data testing tool. You will revisit the six dimensions of data quality using [Deequ](https://github.com/awslabs/deequ).

The following actions need to be taken to complete the assessments in this section:

- [ ] Submit Notebook
- [ ] Complete Data Testing MCQ


### **Resources** 📕️
The below resource should be used to complete the work found in this section:

- [Deequ data testing notebook](./Task3_automatic_data_quality_testing/Data_deequ_tests_student_version.ipynb)


---

## FAQ ❓

This section of the repo will be periodically updated to represent common questions that may arise around its use. If you detect any problems/bugs, please [create an issue](https://help.github.com/en/github/managing-your-work-on-github/creating-an-issue), and we will do our best to resolve it as quickly as possible.

We wish you all the best in your learning experience 🚀!

<p align='center'>
     <img src="https://raw.githubusercontent.com/Explore-AI/Pictures/master/EDSA_logo.png"
     alt='EDSA-logo'
     width=450px/>
     <br>
</p>

