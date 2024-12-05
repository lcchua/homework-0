### Prometheus & Grafana SRE Monitoring Tools
This repository contains the setup and configuration for Prometheus and Grafana monitoring tools, designed to monitor and visualize the key performance signals for system and application health. The monitoring setup adheres to SRE best practices, specifically focusing on the SRE 4 Golden Signals: 

![image](https://github.com/user-attachments/assets/cdead711-a757-4277-8c0d-1714588aae81)


#### **Installation** 
1. Ensure **Helm** is installed. If not, install Helm following the instructions [here](https://helm.sh/docs/intro/install/)
2. Install Prometheus from the official Prometheus Helm chart:
   ```bash
# Add Prometheus Helm repo
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update

# Install Prometheus
helm install prometheus prometheus-community/prometheus
- You must have a running Kubernetes cluster.
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

