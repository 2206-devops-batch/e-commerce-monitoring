https://github.com/grafana/helm-charts/issues/939#issuecomment-1011389950 <br>
https://artifacthub.io/packages/helm/prometheus-community/kube-prometheus-stack <br>
https://github.com/prometheus-operator/kube-prometheus/issues/555#issuecomment-635938188 <br>
1. kubectl create namespace monitoring
2. helm upgrade --install -n monitoring loki grafana/loki-stack --set grafana.enabled=false,prometheus.enabled=false
   1. helm uninstall loki -n monitoring
3. install kube-prometheus-stack
   1. helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
   2. helm repo update
   3. helm install prometheus prometheus-community/kube-prometheus-stack -n monitoring --values values.yaml
      1. helm uninstall prometheus -n monitoring
4. 