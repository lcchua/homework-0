# NTU CE7 Group 1 Capstone Project Use-Case Documentation
<br>

![Alt text 1 MLOps](https://github.com/user-attachments/assets/b7e4e120-6c5d-41c1-aac1-2c69889b8f95)  
<br>

### Our Company Profile
Quantum AI is a Singapore-based tech startup specializing in AI platform engineering for the insurance industry. We are a team of 4 'hardcore' engineers who is responsible for the "development and operations" ('DevOps') of Quantum's cloud AI platform. It offers customer up-selling and cross-selling predictions for insurance and bancassurance companies. Each member of this team has specialised tech skills and subject-matter expertise working collectively to ensure the continuous advancement and resilience of the platform.
### The 'Hardcore' Engineering Team
| **Name**                  | **Roles**                           |  **Expertise**                               |
|---------------------------|-------------------------------------|----------------------------------------------|
| Stephen Tan               | DevOps/DevSecOps Engineer           | GitHub & CICD Wizard                         |
| Tan Yuan                  | Cloud & On-Premise Infra Engineer   | Kubernetes & Cloud Master                    |
| Jun Jie                   | Platform Monitoring Engineer        | Prometheus & Grafana Spymmaster              | 
| Chua Lai Chwang           | MLOps Engineer & Project Manager    | GitHub Actions Conductor                     |

<br>

## The Project
Project Name: **Machine-Learning (ML) DevOps with DevSecOps and SRE Monitoring**<br>
- Our organization repositor [CE7-Group1-Capstone](https://github.com/CE7-Group1-Capstone) is consisting of: 
  - [CI & Docker Image Registry Pipeline for ML Model Training & Publishing](https://github.com/CE7-Group1-Capstone/mlops-project)
  - [CI/CD Pipeline for AWS EKS/K8S Clusters Infrastructure & Monitoring Tools](https://github.com/CE7-Group1-Capstone/Capstone-Infrastructure)
  - CD Pipeline for Insurance Buying Prediction Application Deployment & Rollback is part of the above 2 repos

### Scope, Context and Motivation 
The primary use-case of this project centres on DevOps combined with basic use-cases of DevSecOps and SRE monitoring. This project covers the developing and deploying of machine learning (ML) models to the resilient, cloud-native Kubernetes (K8S) clusters in the non-production and production environments. The maintenance of ML models is excluded from this capstone due to time limitation. This CICD automation process of "DevOps for ML application" is known as MLOps which is generally illustrated as below. 

![Alt text 2 MLOps](https://github.com/user-attachments/assets/a8f49323-ff20-44a9-b9ca-c5feccc7d8dc)

For our capstone scope, we have impelmented the source repository, CI/CD pipelines, data engineering, ML model engineering, ML metadata store including the ML model and data version control, model registry (of FastAPI app Docker images) and CD stage (of ML models serving as container Pods/Services/Deployments in the K8S clusters).

In this project context, the ML application is a prediction of whether an insurance customer is most likely to buy or renew an insurance policy or not, That is predicting the customer's propensity to buy an insurance product or otherwise. For ML model training, the aplication uses 3 different data classification algorithms of decision tree cliassifer, gradient boosting classifier and random forest classifier. 

Our motivation for electing the implementation coverage of MLOps, Kubernetes and SRE Monitoring for our capstone project lies with our desire to apply what we have learnt and in learning through hands-on practice. Though we did not implement the end-to-end MLOps process, we believe what we have started serve as as good baseline for us to learn further subsequently as we sought to extend our capstone implementation in the future. 

With the currrent proliferation of AI, it is imperative that the field of MLOps or AIOps will be a necessity in the technological advancement and mass adoption of AI wherein the process automation of AI/ML operation and security is essential.

### Solution Architecture Overview
![image](https://github.com/user-attachments/assets/751c6076-9e29-4c76-b1f3-dcafabd17de3)

<br>

## Getting Started
Clone the above-mentioned Git repositories and then follow the following steps of action:

### ML Model Training & Publishing
_fill in the workflow pipeline steps to check, install, build and execute_<br>
_remove this section as according_`
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

## AWS EKS/Kubernetes Cluster Infrastructure
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

## Prometheus & Grafana SRE Monitoring Tools
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

## Insurance Buying Prediction Application Deployment & Rollback
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
