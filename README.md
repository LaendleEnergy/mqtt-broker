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
docker-compose.yaml
azure-pipeline.yaml
```

Notwendige Komponenten werden in Ordnern, gemeinsam mit einem `Dockerfile`
und ev. notwendigen Configfiles abgelegt. Das `docker-compose.yaml` fasst das
Projekt zusammen und start den Broker.

## Deployment produktiv

Jeder Push auf `master` testet, ob das Bauen der einzelnen Komponenten möglich
ist. Soll das Projekt auf `45.145.224.10` deployed werden, muss die Pipeline
manuell gestartet werden, wobei der Parameter `deploy` auf `true` gestellt
sein muss.

## Dev Lokal

```
docker compose up
```