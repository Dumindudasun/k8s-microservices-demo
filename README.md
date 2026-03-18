# Kubernetes Microservices Monitoring Demo

## Overview

This project provides a comprehensive demonstration of end-to-end monitoring for a Kubernetes-based three-tier application using Prometheus and Grafana. The monitoring stack is designed to collect, store, and visualize metrics related to application performance, resource utilization, and system health. The primary objective is to showcase practical DevOps and Kubernetes monitoring skills relevant to entry-level DevOps, Site Reliability Engineering (SRE), or Platform Engineering positions.
<img width="1536" height="1024" alt="ChatGPT Image Mar 18, 2026, 04_58_24 PM" src="https://github.com/user-attachments/assets/0a7516fe-4a74-46f7-b1e7-1c74203f155c" />


---

## Architecture

### Application Structure

- **Frontend:** Web User Interface
- **Backend:** Application/API Layer
- **Database:** Persistent Storage

### Monitoring Components

- **Prometheus:** Metrics collection and storage
- **Grafana:** Visualization dashboards
- **Alertmanager:** Alert management and notifications
- **Node Exporter:** Node-level metrics collection
- **Kube State Metrics:** Kubernetes object metrics

---

## Features

- Real-time monitoring of application and infrastructure
- CPU and memory usage tracking per pod
- Node resource utilization metrics
- Kubernetes workload status monitoring
- Custom Grafana dashboards for visualization
- Integrated alerting support

---

## Technologies Used

- Kubernetes
- Prometheus
- Grafana
- Alertmanager
- kube-prometheus-stack (Helm)
- Docker
- Linux

---

## Setup Instructions

### 1. Install the Monitoring Stack

Using Helm:

```sh
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
helm install monitoring prometheus-community/kube-prometheus-stack
```

### 2. Access Prometheus

```sh
kubectl port-forward svc/monitoring-kube-prometheus-prometheus 9090:9090
```
Open Prometheus at: [http://localhost:9090](http://localhost:9090)

### 3. Access Grafana

```sh
kubectl port-forward svc/monitoring-grafana 3000:80
```
Open Grafana at: [http://localhost:3000](http://localhost:3000)

Retrieve the Grafana admin password:

```sh
kubectl get secret monitoring-grafana -o jsonpath="{.data.admin-password}" | base64 --decode
```
##Dashboard Panels

The Grafana dashboard includes:
- Pod CPU Usage
- Pod Memory Usage
- Node Resource Usage
- Application Health Metrics
![readme -dashbord](https://github.com/user-attachments/assets/c797490d-e997-4207-9826-4090a74496da)

##Alert
Alert rules can be configured in Prometheus to notify when thresholds are exceeded, such as:
- High CPU usage
- High memory consumption
- Pod failures
- Node pressure conditions
![promithues](https://github.com/user-attachments/assets/d494eedf-4f27-435a-95b6-d85b6fabf682)




## Demonstrated Skills

- Implementation of Kubernetes monitoring best practices
- Construction of Prometheus metric queries (PromQL)
- Design and customization of Grafana dashboards
- Application of observability principles
- Integration and configuration of real-world DevOps tooling

