# Kubernetes and helm exercise

In this project, I deployed a previously dockerized Node-js application (evergreen-app), together with Prometheus (system monitoring), and Grafana (visualizing Prometheus metrics), to my already existing cluster on AWS using first Kubernetes and later Helm.

## Kubernetes
- Grafana: using ConfigMap and Secret, default admin username and password were configured already at deployment (proper secret storing is not implemented yet). Used LoadBalancer service to expose application to the internet.

- Prometheus: using ConfigMap, configured data scraping jobs to pull data from evergreen-app and Prometheus itself.

## Helm
- Grafana:
    - Helm chart: https://artifacthub.io/packages/helm/grafana/grafana
    - Secret(proper secret storing is not implemented yet) must be run before the helm chart to configure default admin username and password
    - Used LoadBalancer service to expose application to the internet.

- Prometheus: 
    - Helm chart: https://artifacthub.io/packages/helm/prometheus-community/prometheus
    - Only enabled the Promethues server, every other bundled Prometheus service was disabled
    - Configured data scraping jobs to pull data from evergreen-app and Prometheus itself.
