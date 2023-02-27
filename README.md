# Prometheus & Grafana kubernetes setup

### Steps to be done to reproduce results in this repo:
1. Copy [grafana+prometheus compose](https://github.com/docker/awesome-compose/tree/master/prometheus-grafana) files
2. Use the following command to generate kubernetes .yaml files in `kubernetes` folder:
    ```
    kompose convert -f compose.yaml -o kubernetes/
    ```
3. Edit generated files in `kubernetes` folder to:
    - Configure secrets
    - Set configmaps according to `grafana/` and `prometheus/` `.yml` files
4. To deploy with kubectl, use the following command:
    ```
    kubectl apply -f kubernetes/
    ```
5. Show artifacts we interested in:
    ```
    kubectl get pods,services,secrets,configmaps,pvc
    ```
6. You can use the following command to easily access the grafana UI:
    ```
    minikube service grafana
    ```