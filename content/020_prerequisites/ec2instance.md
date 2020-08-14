---
title: "Vincular el rol de IAM a tu Workspace"
chapter: false
weight: 17
---

1. Seguir el siguiente link para [encontrar la instancia EC2 de Cloud9](https://console.aws.amazon.com/ec2/v2/home?#Instances:tag:Name=aws-cloud9-.*workshop.*;sort=desc:launchTime)
1. Seleccionar la instancia,luego elegir **Actions / Instance Settings / Attach/Replace IAM Role**
![c9instancerole](/images/c9instancerole.png)
1. Seleccionar **eksworkshop-admin** desde el menú desplegable de **IAM Role** y seleccionar **Apply**
![c9attachrole](/images/c9attachrole.png)
