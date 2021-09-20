# How to run the application

Build the docker image :

> cd app
> docker build -t username/nodejs-helloworld .

Push the image on docker hub (In real world it could be a private registry)

> docker push username/nodejs-helloworld

Apply kubernetes deployment, service, ingress

> kubectl apply -f app/application.yaml


Manifest is available at app/application.yaml.


# Monitoring

Prometheus and Grafana / Loki.

## Prometheus

Install Prometheus for metrics scrapping and storing.
It will allow service discovery from kubernetes api, and scrape metrics dynamically.
It also allow alert management.
It use PromQL to query metrics with great complexity.

## Grafana

Grafana allow visualisation of your metrics (and logs too) throw prometheus.

## Loki

Loki (with promtail) allow log ingestion and store it on a object storage for example. (S3)


# Component i used

