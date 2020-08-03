---
title: "Nodos de Kubernetes"
date: 2018-10-03T10:15:55-07:00
draft: false
weight: 40
---

Las máquinas que forman un clúster de Kubernetes se llaman **nodos**.

Los nodos en un cluster de Kubernetes pueden ser físicos or virtuales.  

Hay dos clases de nodos:

* Una clase Control-plane-node, que conforman el [Control Plane](../../architecture/architecture_control), actuan como el cerebro del cluster.

* Una clase Worker-node type, que conforman el [Data Plane](../../architecture/architecture_worker), son los que corren los contenedores (a través de pods).

Vamos a profundizar en como los nodos interactuan entre ellos luego en el workshop.
