# MQTT Broker

dieses Projekt stellt einen MQTT Broker für LaendleEnergy bereit.

## Setup

```
project-root/
├─ eclipse-mosquitto/
│  ├─ Dockerfile
├─ component_2/
│  ├─ Dockerfile
│  ├─ config
azure-pipeline.yaml
```

Notwendige Komponenten werden in Ordnern, gemeinsam mit einem `Dockerfile`
und ev. notwendigen Configfiles abgelegt.

## Deployment produktiv

Jeder Push auf `master` testet, ob das Bauen der einzelnen Komponenten möglich
ist. Soll das Image auch auch `ghcr.io/LaendleEnergy/<component_name>` gepusht
werden, muss das bei einem manuellen Pipelinestart angegeben werden. Dabei
werden Images mit `latest` getagged, außer, es wird manuell ein anderer Tag
als Parameter angegeben.

## Dev Lokal

```
git pull https://WattWise@dev.azure.com/WattWise/mqtt-broker/_git/mqtt-broker.deployment
cd mqtt-broker.deployment
docker login ghcr.io
docker compose up
```