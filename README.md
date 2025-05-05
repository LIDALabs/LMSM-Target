# LIDA Multi Server Monitoring

Plantilla de configuración Docker Compose, del cliente que recopola y envia los datos del servidor usando Node Exporter y cAdvisor a un servidor central con Grafana con Prometheus.

``` stateDiagram-v2
stateDiagram-v2
    state Server {
    Grafana --> Prometheus
    }
    Prometheus --> NodeExporter1
    Prometheus --> cAdvisor1
    Prometheus --> NodeExporter2
    Prometheus --> cAdvisor2
    state TargetServer1 {
        NodeExporter1
        cAdvisor1
    }
    state TargetServer2 {
        NodeExporter2
        cAdvisor2
    }
```
