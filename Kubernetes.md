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

Prometheus and Grafana.

