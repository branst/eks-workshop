---
title: "Control Plane"
date: 2018-10-03T10:18:27-07:00
draft: false
weight: 100
---

{{<mermaid>}}
graph TB
kubectl{kubectl}
  subgraph Control Plane
    api(API Server)
    controller(Controller Manager)
    scheduler(Scheduler)
    etcd(etcd)
  end

  kubectl-->api
  controller-->api
  scheduler-->api
  api-->kubelet
  api-->etcd

  classDef green fill:#9f6,stroke:#333,stroke-width:4px;
  classDef orange fill:#f96,stroke:#333,stroke-width:4px;
  classDef blue fill:#6495ed,stroke:#333,stroke-width:4px;
  class api blue;
  class internet green;
  class kubectl orange;
{{< /mermaid >}}

* Uno o más API Servers: punto de entra para API REST / kubectl

* etcd: Almacenamiento clave/valor distribuido

* Controller-manager: Evaluador constante de estados: actual vs deseado

* Scheduler: Asigna pods a worker nodes

Revisa [la documentación oficial de Kubernetes](https://kubernetes.io/docs/concepts/overview/components/#master-components) para una revisión en profundidad del control plane y sus componentes.
