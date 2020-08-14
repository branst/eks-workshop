---
title: "Crear una cuenta de AWS"
chapter: false
weight: 1
---

{{% notice warning %}}
Tu cuenta debe tener la capacidad de crear nuevos roles de IAM e incorporar otros permisos de IAM.
{{% /notice %}}

1. Si no tienes una cuenta de AWS con acceso de Administrador: [crear
una ahora haciendo click aquí](https://aws.amazon.com/getting-started/)

1. Una vez que tengas la cuenta de AWS, asegurarse de estar siguiendo los pasos del workshop restantes como un usuario IAM con acceso de administrador a la cuenta de AWS:
[Crear un nuevo usuario IAM para usar en el workshop](https://console.aws.amazon.com/iam/home?#/users$new)

1. Ingresar los detalles de usuario:
![Crear Usuario](/images/iam-1-create-user.png)

1. Vincular la política de AdministratorAccess:
![Vincular Política](/images/iam-2-attach-policy.png)

1. Click para crear el nuevo usuario:
![Confirmar Usuario](/images/iam-3-create-user.png)

1. Tomar nota de la URL de login y guardar:
![Login URL](/images/iam-4-save-url.png)
