# Digital Optimization Group - Data Analysis Jupyter Notebooks with R

Usage of this repo requires an account with Digital Optimization Group. We are currently in developer preview. If you would like to get an account email preview@digitaloptgroup.com.

### Getting Started

#### Getting access to your BigQuery Dataset

Share your BigQuery Dataset with an email address associated with a Google account you control.

This can be done via our CLI by running:

```sh
dog apps:sharedataset EMAIL
```

Once that command has successfully executed you should have access to your dataset and be able to view it in your Google Cloud dashboard: https://console.cloud.google.com/bigquery?project=digital-opt-group-analytics

**Note**: You must have billing enabled to utilize these features within your Google Cloud Account.

You can now explore your tables and data from within the BigQuery user interface.

### Setting up Google AI Notebook for R

Follow Google's instructions for setting up an R notebook (taken from Google docs):

#### Before you begin

Before you can use AI Platform Notebooks, you must have a Google Cloud Platform (GCP) project and enable the Compute Engine API for that project.

https://cloud.google.com/ml-engine/docs/notebooks/before-you-begin

#### Create a new notebook instance

When selecting the instance choose "R". Follow the directions here:

https://cloud.google.com/ml-engine/docs/notebooks/create-new

#### Preparing for use with BigQuery

You will need to create a Service Account to access BigQuery from your notebook:

https://cloud.google.com/ml-engine/docs/notebooks/use-r-bigquery

#### Clone our Notebooks from Github

You can fork or clone this repo into your Notebook environment. If your familiar with a terminal and git, it's probably easiest to open a terminal for your notebook instance and do what you know.

Or follow along this guide:

https://cloud.google.com/ml-engine/docs/notebooks/save-to-github

#### Configure the Notebooks for your dataset

Rename `config.R-template` to `config.R` and replace the dataset name with your dataset's name. It will be your Digital Optimization Group project/App Id without the dashes and camelCased.
