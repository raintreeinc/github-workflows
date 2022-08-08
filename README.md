# Introduction
This repository contains reusable workflows for use in deploying Raintree infrastructure and code

## Workflow Overview
- terraform_plan.yml: Runs the 'terraform plan' command, outputs results to a 'tfplan' file, and uploads the artifact. This is meant to be used in preparation for deploying infrastructure. A user will issue a pull request, then review the results of the plan, and assuming all looks good, approve the PR which will trigger the terraform_apply pipeline.
- terraform_apply.yml: Designed to run in conjunction with the above terraform_plan pipeline. This will only run after a PR is closed and merged into main. The pipeline grabs the tfplan artifact created by the plan pipeline and then applies it. Note: there is no further review performed, the PR is the review. So as soon as the PR is approved, the plan will be applied. 
