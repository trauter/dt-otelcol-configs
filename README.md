# Overview
Contains example configs for opentelemetry-collector

## create secrets
```
kubectl -n dynatrace create secret generic dynatrace-otelcol-dt-api-credentials --from-literal=api-endpoint=https://xy.dynatrace.com --from-literal=api-token=dt0c01...TOKEN_WITH_METRIC_INGEST
```


