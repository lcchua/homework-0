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
Home
  -->Connections
      -->Data sources

![image](https://github.com/user-attachments/assets/d3c180f1-7414-4846-8057-fb62b66a7683)

![image](https://github.com/user-attachments/assets/68679692-e380-4551-9816-746f1efb827c)

**_Add Prometheus as a Data Source:_**
- In the Grafana dashboard, click on the gear icon (⚙️) on the left sidebar to go to **Configuration**
- Under **Data Sources**, click **Add data source**
- Select **Prometheus** from the list of data sources.
- In the URL field, enter the URL of your Prometheus instance (e.g., http://localhost:9090).
- Click **Save & Test** to ensure the data source is connected.

_**Add Loki as a Data Source:**_
- Under **Configuration**, click **Add data source** again.
- Select **Loki **from the list of data sources.
- In the **URL** field, enter the URL of the Loki instance (e.g., http://localhost:3100).
- Click **Save & Test** to ensure the data source is connected.

4. Create a Dashboard from Scratch
- In the left sidebar, click the + icon and select **Dashboard**.
- This will create a new empty dashboard.
- Click on **Add Panel** to start adding the visualization.
- In the Query section, select** Prometheus** for metrics or **Loki **for logs.

5. Saving the Dashboard
- After making changes and finalizing your dashboard, click on the **"Save dashboard"** button located at the top right corner of the dashboard.
Enter a name for the dashboard and click "Save" to store the dashboard configuration.
![image](https://github.com/user-attachments/assets/f68eed71-aba6-4cae-9312-38335116d2ea)

6. Download the JSON File:
- To download the dashboard as a JSON file, click the **"Share" **button at the top of the dashboard.
![image](https://github.com/user-attachments/assets/3b202ffc-a59e-4ba1-8178-6ee1494a11d3)

- In the window that appears, select the **"Export"** tab and click the **"Save to file"** button.
![image](https://github.com/user-attachments/assets/32407c62-697d-4936-89b8-a57c6ad1128a)

- This will download the dashboard’s configuration as a JSON file to your computer.

7. Uploading the JSON File to EKS Cluster
- Once the EKS cluster is ready, the saved JSON file is imported to the EKS's grafana with configuration.
- Navigate to the Grafana dashboard running on the EKS cluster. If access is via Load Balancer, open the Grafana URL in the browser.
- In the Grafana UI, click the "+" icon on the left sidebar and select "Import".
- In the "Import Dashboard" section, click the "Upload JSON file" button.
- Browse to the location where you downloaded the JSON file and select it.

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

