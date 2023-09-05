### Why KEDA?

- To automatically scale your Kubernetes workloads based on external event metrics. It is a Kubernetes-based Event Driven Autoscaler.


### Example Use Cases
1. KEDA can be leveraged to dynamically scale image processing pods based on messages in an Apache Kafka topic or RabbitMQ queue or AWS SQS queue.
2. KEDA can be leveraged to dynamically scale data processing pods based on Prometheus metrics indicating memory consumption surpassing 80%.

### Precondition
- K8S Cluster(s)

### Installation

1. Add helm repo

```helm repo add kedacore https://kedacore.github.io/charts```

2. Update helm repo

```helm repo update```

3. Install keda helm chart

```helm install keda kedacore/keda --namespace keda --create-namespace```



### Resources
1. https://keda.sh/
1. https://github.com/kedacore/keda