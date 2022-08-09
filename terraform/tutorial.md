# Cloudbuild Trigger Build - Terraform

## Setup

Welcome to Terraform in Google Cloud Shell! We need you to let us know what project you'd like to use with Terraform.

<walkthrough-project-billing-setup></walkthrough-project-billing-setup>

Terraform provisions real GCP resources, so anything you create in this session will be billed against this project.

## Cloud Project

<walkthrough-project-setup></walkthrough-project-setup>

Click the Cloud Shell icon below to copy the command to your shell, and then run it from the shell by pressing Enter/Return. Terraform will pick up the project name from the environment variable.

```bash
export GOOGLE_CLOUD_PROJECT=<walkthrough-project-id/>
```

## Prepare environment

Let's use <walkthrough-project-id/> with Terraform! 

Before we run terraform we need to set a couple of variables, let's open the example.tfvars file and configure them.

<walkthrough-editor-open-file filePath="example.tfvars">Open example.tfvars</walkthrough-editor-open-file>

You need to fill in the following variables

| Variable | Description |
| -------- | ----------- |
| gcp_project | Google Cloud Project ID: <walkthrough-project-id/> |
| gcp_bucket_location | [Google Cloud Storage Bucket location](https://cloud.google.com/storage/docs/locations) |
| gcp_region_cloud_function | [Google Cloud Function location](https://cloud.google.com/functions/docs/locations) |
| gcp_region_scheduler | [Google Cloud Scheduler location](https://cloud.google.com/appengine/docs/locations) |
| gcp_region_workflow | [Google Cloud Workflows location](https://cloud.google.com/workflows/docs/locations) |
| gcs_cf_upload | Name of the Google Cloud Bucket from where the Cloud Function will be deployed. Terraform will upload the code to this bucket and deploy the cloud function from there. |
| gcs_export_bucket | Google Cloud Storage Bucket where the BigQuery table will be exported to.
| fs_collection | Firestore Collection ID, the cloud function will store all rows into this collection. |
| csv_key_column | Column in the CSV file that is used as document ID in Firestore. |
| bq_dataset | BigQuery Dataset ID |
| bq_table | BigQuery Table to be imported in Firestore |
| bq_export_schedule | [Cron schedule](https://cloud.google.com/scheduler/docs/configuring/cron-job-schedules) |
| bq_export_schedule_timezone | [Cron schedule timezone](https://cloud.google.com/scheduler/docs/configuring/cron-job-schedules#time_zone) |

After that, let's get Terraform started. 

## Terraforming

Run the following to pull in the providers.

```bash
terraform init
```

With the providers downloaded and a project set, you're ready to use Terraform. Go ahead!

```bash
terraform apply -var-file=example.tfvars
```

Terraform will show you what it plans to do, and prompt you to accept. Type "yes" to accept the plan.

```bash
yes
```
