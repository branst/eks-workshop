---
title: "Recursos de Kubernetes"
date: 2018-10-03T10:15:55-07:00
draft: false
weight: 50
---

Los recursos de Kubernetes son las entidades utilizadas para representar el estado del cluster.

Un objeto o recurso es un “registro de intención" – una vez creado, el cluster hace su mayor esfuerzo para que exista como fue definido. Esto es conocido como el "estado deseado" del cluster.

Kubernetes siempre esta trabajando para mantener el "estado actual" igual al "estado deseado" de un objeto. Un estado deseado puede describir:

* Que pods (contenedores) estan corriendo y en que nodos
* Las direciones IP que representan un grupo lógico de contendores
* Cuantas réplicas de un mismo contendor están en ejecucion
* y muchas más ...

Vamos a revisar en detalle que son estos recursos de Kubernetes...
