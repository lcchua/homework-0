### Prometheus & Grafana SRE Monitoring Tools
This repository contains the setup and configuration for Prometheus and Grafana monitoring tools, designed to monitor and visualize the key performance signals for system and application health. The monitoring setup adheres to SRE best practices, specifically focusing on the SRE 4 Golden Signals: 

![image](https://github.com/user-attachments/assets/cdead711-a757-4277-8c0d-1714588aae81)

#### Dependencies
This repository requires the following dependencies to be set up:
- Prometheus for metrics collection and monitoring.
- Grafana for data visualization and dashboard creation.
- Node Exporter for system-level metrics (CPU, memory, disk, network, file system).
- Loki (for log aggregation and query in Grafana).

#### **Installation** 
1. Ensure **Helm** is installed. If not, install Helm following the instructions [here](https://helm.sh/docs/intro/install/)

2. Install Prometheus Helm chart:
```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
helm install prometheus prometheus-community/prometheus
```

3. Install Grafana Helm Chart:
```bash
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update
helm install grafana grafana/grafana
```

4. Install Loki stack for log aggregation:
```bash
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update
helm install loki grafana/loki-stack
```

#### Creating a Grafana Dashboard from Scratch and Linking Data Sources
In this project, Grafana, Prometheus, and Loki were initially installed on a local machine while awaiting the finalisation of the workflow for the capstone project's EKS cluster. A custom Grafana dashboard was created for set up and testing purposes. Once the group's capstone EKS cluster was ready, the dashboard configuration was saved as a JSON file and uploaded to the cluster.

To create a dashboard on Grafana localhost from scratch. Follow these steps:

1. Access Grafana
Open your browser and go to Grafana’s web interface, typically available at
```bash http://localhost:3000```

2. The default login credentials are:

- Username: ```bash admin```
- Password: ```bash admin (or prom-operator)```

3. Add Prometheus and Loki Data Sources
Before creating the dashboard, ensure that Prometheus and Loki are added as data sources:

**_Add Prometheus as a Data Source:_**
- In the Grafana dashboard, click on the gear icon (⚙️) on the left sidebar to go to **Configuration**
- Under **Data Sources**, click **Add data source**
- Select **Prometheus** from the list of data sources.
- In the URL field, enter the URL of your Prometheus instance (e.g., http://localhost:9090).
- Click **Save & Test** to ensure the data source is connected.

_**Add Loki as a Data Source:**_
- Under **Configuration**, click **Add data source** again.
- Select **Loki **from the list of data sources.
- In the **URL** field, enter the URL of your Loki instance (e.g., http://localhost:3100).
- Click **Save & Test** to ensure the data source is connected.

4. Create a Dashboard from Scratch
- In the left sidebar, click the + icon and select **Dashboard**.
- This will create a new empty dashboard.
- Click on **Add Panel** to start adding your first visualization.
- In the Query section, choose your data source. You can select** Prometheus** for metrics or **Loki **for logs.


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

