# Digital Optimization Group - Data Analysis Jupyter Notebooks with R

Usage of this repo requires an account with Digital Optimization Group. We are currently in developer preview. If you would like to get an account email preview@digitaloptgroup.com.

### Getting Started

#### Getting access to your BigQuery Dataset

Share your BigQuery Dataset with an email address associated with a Google account you control.

This can be done via our CLI by running:

```sh
dog apps:sharedataset EMAIL
```

Once that command has successfully executed you should have access to your dataset. However, your dataset will probably not show up immediately in your BigQuery dashboard (although you should be able to run queries). To be able to view it in your Google Cloud dashboard you'll need to go through this URL, else it will not show up under "Resources": https://console.cloud.google.com/bigquery?p=digital-opt-group-analytics

**Note**

- You must have billing enabled to utilize these features within your Google Cloud Account.
- You must have a Google Cloud project and your user must have at least BigQuer.jobUser permission to run queries
- Billing for queries will be billed to your Google account according the Google pricing applying to your account
- To view your dataset you'll need to use this URL: https://console.cloud.google.com/bigquery?p=digital-opt-group-analytics

You can now explore your tables and data from within the BigQuery user interface.

### Setting up a Google AI Notebook for R

There are links to detailed documentation from Google further down, or you can try the quick start.

#### Quick start

- From Google Cloud menu access ARTIFICIAL INTELLIGENCE > AI Platform > Notebooks
  - https://console.cloud.google.com/mlengine/notebooks
  - If this is the first time it will ask you to enable the Compute API, do so
- Click `+ New Instance` & select "R 3.5.3" (or similar)
  - Name and customize the instance as you desire
- Create a Service Account: PRODUCTS > APIs & Services > Credentials
  - https://console.cloud.google.com/apis/credentials
  - Click `Create credentials`
    - Choose `Service account key`
    - In the Service account drop-down menu select New service account to create a new one
    - Give it a name and add BigQuery Admin access as the Role
    - Copy the email address and give it access to your Dataset (you'll need to do this via our CLI - as you did for your email)
      - `dog apps:sharedataset SERVICE_ACCOUNT_EMAIL`
    - Select JSON as the key type
    - Click create and note where the file was saved on your computer, you'll need to upload this to your Notebook
- Open your Notebook `OPEN JUPYTERLAB`
  - https://console.cloud.google.com/mlengine/notebooks
  - Click the `Upload Files` icon
    - Find and upload the service account you created
    - Right click the file, select `rename` and rename it `service-account.json`
  - Clone this Repo into your Notebook
    - In your Notebook's menu: Git > Open Terminal
    - git clone https://github.com/DigitalOptimizationGroup/digitaloptgroup-r-notebooks.git
  - You should now see the cloned repo `digitaloptgroup-r-notebooks` in the file browser
    - Open the folder
    - Right click `config.R-template` and rename it simply `config.R`
    - Open your, newly renamed, `config.R`
      - replace `YOUR_DIGITAL_OPT_GROUP_DATASET_NAME` with your dataset name. Note your dataset name is a camelCased version of your project/app Id. So `happy-camper-239` would become `happyCamper239`
      - replace `YOUR_GOOGLE_CLOUD_PROJECT_ID` with the ProjectId of your service account that will be responsible for Google billing charges
    - Save the file and close it
  - Open the `notebooks` folder
    - Now you can open any Notebook and should be able to run all the queries accessing your Dataset
      - Hint: Select the first cell and type Shift+Enter, then repeat for all the cells. This reruns them and should get your data.

## Additional Documentation References

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
