# NTU CE7 Group 1 Capstone Project Use-Case Documentation
<br>

<img src="https://github.com/user-attachments/assets/b7e4e120-6c5d-41c1-aac1-2c69889b8f95" alt="MLOps Overview" width="1000" />
<br>

### Our Company Profile
Quantum AI is a Singapore-based tech startup specializing in AI platform engineering for the insurance industry. We are a team of 4 'hardcore' engineers who is responsible for the "development and operations" ('DevOps') of Quantum's cloud AI platform. It offers customer up-selling and cross-selling predictions for insurance and bancassurance companies. Each member of this team has specialised tech skills and subject-matter expertise working collectively to ensure the continuous advancement and resilience of the platform.
### The 'Hardcore' Engineering Team
| **Name**                  | **Roles**                           |  **Expertise**                               |
|---------------------------|-------------------------------------|----------------------------------------------|
| Stephen Tan               | DevOps/DevSecOps Engineer           | GitHub & CICD Wizard                         |
| Tan Yuan                  | Cloud & On-Premise Infra Engineer   | Kubernetes & Cloud Master                    |
| Jun Jie                   | Platform Monitoring Engineer        | Prometheus & Grafana Spymmaster              | 
| Chua Lai Chwang           | MLOps Engineer & Project Manager    | GitHub Actions Scrum Master                  |

<br>

## The Project
Project Name: **Machine-Learning (ML) DevOps with DevSecOps and SRE Monitoring**<br>
- Our organization repository [CE7-Group1-Capstone](https://github.com/CE7-Group1-Capstone) consists of: 
  - [CI & Docker Image Registry Pipeline for ML Model Training & Publishing](https://github.com/CE7-Group1-Capstone/mlops-project)
  - [CI/CD Pipeline for AWS EKS/K8S Clusters Infrastructure & Monitoring Tools](https://github.com/CE7-Group1-Capstone/Capstone-Infrastructure)
  - CD Pipeline for Insurance Buying Prediction Application Deployment & Rollback is part of the above 2 repos

### Scope, Context and Motivation 
The primary use-case of this project centres on DevOps combined with basic use-cases of DevSecOps and SRE monitoring. This project covers the developing and deploying of machine learning (ML) models to the resilient, cloud-native Kubernetes (K8S) clusters in the non-production and production environments. The maintenance of ML models is excluded from this capstone due to time limitation. This CICD automation process of "DevOps for ML application" is known as MLOps which is generally illustrated as below. 

![MLOps Process](https://github.com/user-attachments/assets/a8f49323-ff20-44a9-b9ca-c5feccc7d8dc)

For our capstone scope, we have impelmented the source repository, CI/CD pipelines, data engineering, ML model engineering, ML metadata store including the ML model and data version control, model registry (of FastAPI app Docker images) and CD stage (of ML models serving as container Pods/Services/Deployments in the K8S clusters).

In this project context, the ML application is a prediction of whether an insurance customer is most likely to buy or renew an insurance policy or not, That is predicting the customer's propensity to buy an insurance product or otherwise. For ML model training, the aplication uses 3 different data classification algorithms of decision tree cliassifer, gradient boosting classifier and random forest classifier. 

Our motivation for electing the implementation coverage of MLOps, Kubernetes and SRE Monitoring for our capstone project lies with our desire to apply what we have learnt and in learning through hands-on practice. Though we did not implement the end-to-end MLOps process, we believe what we have started serve as as good baseline for us to learn further subsequently as we sought to extend our capstone implementation in the future. 

With the currrent proliferation of AI, it is imperative that the field of MLOps or AIOps will be a necessity in the technological advancement and mass adoption of AI wherein the process automation of AI/ML operation and security is essential.

### Solution Architecture Overview
The solution architecture can be described as follows:

![MLOps Capstone Solution Architecture](https://github.com/user-attachments/assets/751c6076-9e29-4c76-b1f3-dcafabd17de3)

It comprises of 3 major domains:
  -  Machine Learning Development: ML Model Training and Publishing to AWS Elastic Container Registry (ECR) with AWS S3 bucket for the ML model version control metatdata and training datasets storage
  -  Cluster Infra Deployment: Terraform creation for AWS Elastic Kubernetes Service (EKS), Prometheus / Grafana monitoring tools, K8S / AWS CloudWatch / Loki logging stack
  -  Prediction Application Deployment & Rollback: GitHub Actions CD workflow pipeline from ECR to EKS for deployment to prod environment

<br>

## Getting Started
First clone the above-mentioned Git repositories and get started with the project as follows:

### ML Model Training & Publishing
In general, a typical ML Pipeline has 3 workflow stages - Data Preparation, Model Training, Model Deployment, as depicted in the diagram below. 
![ML Pipeline](https://github.com/user-attachments/assets/1dc7dcd8-a8c5-4944-b24a-31df6cf235fd)

#### 1. Clone the Specific Git Repo for ML Model Training and Publishing
After the CE7-Group1-Capstone organisation "mlops-project" repository is cloned from GitHub, you will see the following screen from the Web browser.
```bash
  git clone https://github.com/CE7-Group1-Capstone/mlops-project.git
```
![git-repo-screenshot](https://github.com/user-attachments/assets/0572bcbc-d36a-4021-95f6-11ca19be007f)
Before we proceed to the next step, we need to configure the GitHub repo as follows:
![github-env-variables-screenshot](https://github.com/user-attachments/assets/8f4fdc67-b663-4042-bd01-a24eb4c09133)
![github-secret-variables-screenshot](https://github.com/user-attachments/assets/ac4666fc-42fb-42be-8456-9a751a4782fe)
### 2. First-time infra resource creation of the AWS S3 bucket and ECR private repos
For the first-time deployment, you will need to create a S3 bucket and the 2 ECR private repos. Click on `Actions` menu tab and you will see the following screen of the available GitHub Actions workflows:
![gha-ci-tf-screenshot](https://github.com/user-attachments/assets/b5fe8dff-de6d-4246-80d9-e75b7eb91a8f)
Next click on `CI Terraform` followed by click on `Run workflow`, then select _Use workflow from_ `Branch: main` and finally clicking on the `Run workflow` button. This will trigger a series of Terraform initialising, linting, formatting and validating checks - tflint, checkov, terraform init/fmt/validate.

After the `CI Terraform` workflow runs successfully, click on the next workflow of `CD Terraform` to run. Select `Branch: main` and choose `y` for the _Do you really want to proceed (y/n)?_ prompt.
![gha-cd-tf-screenshot](https://github.com/user-attachments/assets/e938c533-9145-4c80-a814-0a9f6a615cee)
This will trigger the Terraform AWS resources creation of the S3 bucket and ECR private repos:
  - S3 bucket `ce7-grp-1-bucket`
    - `new_ML_data` folder where the model training dataset (named as `train.csv`) and the model testing dataset (named as `test.csv`) are stored
    - `DVC_Artefacts` folder where the version control metadata of the trained ML models are saved by the [Data Version Control](https://dvc.org/) (DVC) tool that is used in the other workflows.
  ![s3-bucket-screenshot](https://github.com/user-attachments/assets/a8e40738-a771-4785-b5be-cb91eec92aef)
  - ECR private repos of `ce7-grp-1/nonprod/predict_buy_app` and `ce7-grp-1/prod/predict_buy_app`
  ![ecr-repos-screenshot](https://github.com/user-attachments/assets/48a4102c-8405-4d10-99cf-6de3ec05dd56)
Now that the AWS resources for ML model Training and Publishing are created, we can then proceed with the Data Prep Stage of the ML Pipeline.
#### 2. Preparing the ML training and testing datasets
Upload the `train.csv` and `'test.csv` files  into the S3 bucket.
![new-datasets-s3-bucket-screenshot](https://github.com/user-attachments/assets/a5da19c2-235a-48d6-a2c7-e22f3eec636e)
Example datasets to unzip-then-upload: [ml-datasets.zip](https://github.com/user-attachments/files/17989198/ml-datasets.zip)
#### 3. Train the Model using Python with Scikit-Learn

#### 4. Build the ML Application using FastAPI

#### 5. Promote the Application Docker Image from nonprod to prod ECR private registeries

#### 6. Test run the `predict_buy_app` using Postman

#### Dependencies
![MLOps CICD Plan](https://github.com/user-attachments/assets/bd768c7e-b205-4e3d-8f6f-431a1ec079d7)
#### Application or Repo Structure
|![repo-structure-screenshot1](https://github.com/user-attachments/assets/0abb694f-9581-4e45-ab59-f02d45e77932)|
![repo-structure-screenshot2](https://github.com/user-attachments/assets/91e99fee-e5d6-4318-89e8-bb2028ec6c15) |

#### Branching Strategies
![Adapted Branching Strategy](https://github.com/user-attachments/assets/0ffa771d-574b-400a-ba0d-20d7fb1ea65e)
#### Production Branch
_describe the branch actions for prod env if any_
#### Non-Production Branch
_describe the branch actions for nonprod env if any_
#### CICD Pipeline
_describe the pipeline workflow including output samples if any_
#### Learning Journey
_add what "little secrets" have been learnt that you like to share with others_ 

### AWS EKS/Kubernetes Cluster Infrastructure
_fill in the workkflow pipeline steps to check, install, build and execute_<br>
_remove this section as according_
#### Dependencies
_fill in the dependencies if any_
#### Application or Repo Structure
_describe the application or repo structure if any_
#### Branching Strategies
_describe the branching strategy if any_
#### Production Branch
_describe the branch actions for prod env if any_
#### Non-Production Branch
_describe the branch actions for nonprod env if any_
#### CICD Pipeline
_describe the pipeline workflow including output samples if any_
#### Learning Journey
_add what "little secrets" have been learnt that you like to share with others_ 

### Prometheus & Grafana SRE Monitoring Tools
_fill in the workflow pipeline steps to check, install, build and execute_<br>
_remove this section as according_
#### Dependencies
_fill in the dependencies if any_
#### Application or Repo Structure
_describe the application or repo structure if any_
#### Branching Strategies
_describe the branching strategy if any_
#### Production Branch
_describe the branch actions for prod env if any_
#### Non-Production Branch
_describe the branch actions for nonprod env if any_
#### CICD Pipeline
_describe the pipeline workflow including output samples if any_
#### Learning Journey
_add what "little secrets" have been learnt that you like to share with others_ 

### Insurance Buying Prediction Application Deployment & Rollback
_fill in the workflow pipeline steps to check, install, build and execute_<br>
_remove this section as according_
#### Dependencies
_fill in the dependencies if any_
#### Application or Repo Structure
_describe the application or repo structure if any_
#### Branching Strategies
_describe the branching strategy if any_
#### Production Branch
_describe the branch actions for prod env if any_
#### Non-Production Branch
_describe the branch actions for nonprod env if any_
#### CICD Pipeline
_describe the pipeline workflow including output samples if any_
#### Learning Journey
_add what "little secrets" have been learnt that you like to share with others_ 

<br>

## Licensing and Credits
Credits to the 'hardcore' team:
- Jun Jie
- Tan Yuan
- Stephen Tan
- Chua Lai Chwang

<br>

## Additional Resources if any
1. [Machine Learning Operations (MLOps) For Beginners](https://medium.com/@prasadmahamulkar/machine-learning-operations-mlops-for-beginners-a5686bfe02b2)
2. 
