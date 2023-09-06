# !!! WIP


### Why KEDA?

- To automatically scale your Kubernetes workloads based on external event metrics. It is a Kubernetes-based Event Driven Autoscaler.


### Example Use Cases
1. KEDA can be leveraged to dynamically scale image processing pods based on messages in an Apache Kafka topic or RabbitMQ queue or AWS SQS queue.
2. KEDA can be leveraged to dynamically scale data processing pods based on Prometheus metrics indicating memory consumption surpassing 80%.

### Precondition
- K8S Cluster

### Installation

0. Install RabbitMQ Server

```helm repo add bitnami https://charts.bitnami.com/bitnami```

```helm install rabbitmq --set auth.username=guest --set auth.password=guest bitnami/rabbitmq --wait```

To Access the RabbitMQ AMQP port:

```kubectl port-forward --namespace default svc/rabbitmq 5672:5672```

To Access the RabbitMQ Management interface:

```kubectl port-forward --namespace default svc/rabbitmq 15672:15672```

1. Add helm repo

```helm repo add kedacore https://kedacore.github.io/charts```

2. Update helm repo

```helm repo update```

3. Install keda helm chart

```helm install keda kedacore/keda --namespace keda --create-namespace```

### Test
1. Open  RabbitMQ Management Web dashboard

```http://localhost:15672/```

The user and psw are :  ```guest```


### Resources
1. https://keda.sh/
2. https://github.com/kedacore/keda
3. https://keda.sh/docs/2.11/scalers/rabbitmq-queue/
4. https://keda.sh/docs/2.11/concepts/scaling-deployments/
5. https://github.com/kedacore/sample-go-rabbitmq/blob/main/README.md