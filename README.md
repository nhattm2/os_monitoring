```bash
git clone https://github.com/prometheus-operator/kube-prometheus.git
cd kube-prometheus

kubectl apply --server-side -f manifests/setup
until kubectl get servicemonitors --all-namespaces ; do date; sleep 1; echo ""; done
kubectl apply -f manifests/

cd ..
kubectl apply -f nodeportconfig/

## node exporter dashboard
https://grafana.com/grafana/dashboards/1860

```
