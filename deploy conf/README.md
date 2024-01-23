# Elastic Deploy

## Elastic quickstart documentation

https://www.elastic.co/guide/en/cloud-on-k8s/master/k8s-overview.html

## Pre-requisites

### Deploy K8S Elastic Definitions / Operator

```
kubectl create -f https://download.elastic.co/downloads/eck/2.11.0/crds.yaml
```

```
kubectl apply -f https://download.elastic.co/downloads/eck/2.11.0/operator.yaml
```

## Deploy Elastic Cluster

### K8S Storage Class Name

\* Optional if already defined

```
kubectl apply -f sc.yaml
```

### K8S Persistent Volume

```
kubectl apply -f pv.yaml
```

### Elastic Password

\* Optional

If not deployed random password is created on secret `quickstart-es-elastic-user`

Default value: elastic

```
kubectl apply -f secret.yaml
```

### Elastic Node

```
kubectl apply -f elastic.yaml
```

### Kibana

```
kubectl apply -f kibana.yaml
```

### APM

```
kubectl apply -f apm.yaml
```

## Access

### Elastic

```
localhost:9200
```

```
Authentication Basic
elastic:elastic
```

### Kibana

```
localhost:5601
```

```
Username: elastic
Password: elastic (or value stored in secret quickstart-es-elastic-user)
```

### APM

```
localhost:8200
```

```
Token: value stored in secret apm-server-quickstart-apm-token
```
