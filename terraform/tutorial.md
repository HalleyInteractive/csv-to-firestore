# Cloudbuild Trigger Build - Terraform

## Setup

Welcome to Terraform in Google Cloud Shell! We need you to let us know what project you'd like to use with Terraform.

<walkthrough-project-billing-setup></walkthrough-project-billing-setup>

Terraform provisions real GCP resources, so anything you create in this session will be billed against this project.

## Terraforming!

Let's use {{project-id}} with Terraform! Click the Cloud Shell icon below to copy the command
to your shell, and then run it from the shell by pressing Enter/Return. Terraform will pick up
the project name from the environment variable.

```bash
export GOOGLE_CLOUD_PROJECT={{project-id}}
```

After that, let's get Terraform started. Run the following to pull in the providers.

```bash
terraform init
```

With the providers downloaded and a project set, you're ready to use Terraform. Go ahead!

```bash
terraform apply
```

Terraform will show you what it plans to do, and prompt you to accept. Type "yes" to accept the plan.

```bash
yes
```
