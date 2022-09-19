# Overview
This repository contains example configurations for the OpenTelemetry Collector in Kubernetes for ingesting data into Dynatrace. In order to use the Dynatrace exporter, a Dynatrace API token has to be generated (see Section "Create Secrets").

dynatrace-otel-pod-scraping-example: Scrape Prometheus metrics from a Kubernetes Pod
dynatrace-otel-statds: Provide a statsD endpoint that supports counter and gauges with labels.
dynatrace-otel-kubelet: Scrapes kubelet and cadvisor metrics and exports them to Dynatrace

## Create Secrets
```
kubectl -n dynatrace create secret generic dynatrace-otelcol-dt-api-credentials \
  --from-literal=DT_API_ENDPOINT=https://xy.dynatrace.com \
  --from-literal=DT_API_TOKENdt0c01...TOKEN_WITH_METRIC_INGEST \
  --from-literal=DT_KUBERNETES_CLUSTER_ID=$(kubectl get ns/kube-system -o jsonpath='{.metadata.uid}')
```