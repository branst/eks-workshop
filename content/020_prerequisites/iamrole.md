---
title: "Crear un rol de IAM para tu Workspace"
chapter: false
weight: 16
---


1. Seguir los pasos del siguiente link para [crear un IAM role con acceso de Administrador.](https://console.aws.amazon.com/iam/home#/roles$new?step=review&commonUseCase=EC2%2BEC2&selectedUseCase=EC2&policies=arn:aws:iam::aws:policy%2FAdministratorAccess)
1. Confirmar que estén seleccionados tanto **AWS service** como **EC2**, luego hacer click en **Next** para ver permisos.
1. Confirmar que **AdministratorAccess** esté seleccionado, luego click en **Next: Tags** para asignar etiquetas.
1. Dejar los valores por defecto, y hacer click en **Next: Review** para revisar.
1. Ingresar **eksworkshop-admin** en el nombre, luego hacer click en **Create role**.
![createrole](/images/createrole.png)
