---
title: "Actualizar la configuración de IAM para tu Workspace"
chapter: false
weight: 19
---

{{% notice info %}}
Cloud9 normalmente gestiona las credenciales IAM dinámicamente. Esto no es compatible actualmente con la autenticación IAM de EKS por lo tanto, vamos a deshabilitarla y usar el rol de IAM en su lugar.
{{% /notice %}}

- Regresar a tu workspace y hacer click en el icono de rueda dentada (esquina superior derecha) o hacer click para abrir una nueva pestaña y seleccionar "Open Preferences"
- Seleccionar **AWS SETTINGS**
- Desactivar **AWS managed temporary credentials**
- Cerrar la pestaña de Preferences
![c9disableiam](/images/c9disableiam.png)

Para asegurarnos que no hay ninguna credencial temporal configurada actualmente vamos a eliminar cualquier archivo de credenciales:
```sh
rm -vf ${HOME}/.aws/credentials
```

Debes configurar tu aws cli con la región que utilices como default.

{{% notice info %}}
Si te encuentras [en un evento de AWS](https://eksworkshop.com/020_prerequisites/aws_event/), pregúntale al instructor cuál **región de AWS** utilizar.
{{% /notice %}}

```sh
export ACCOUNT_ID=$(aws sts get-caller-identity --output text --query Account)
export AWS_REGION=$(curl -s 169.254.169.254/latest/dynamic/instance-identity/document | jq -r '.region')
```

Verificar si AWS_REGION tiene el valor de región correcto
```sh
test -n "$AWS_REGION" && echo AWS_REGION is "$AWS_REGION" || echo AWS_REGION is not set
```
 
Graba esto en el bash_profile
```sh
echo "export ACCOUNT_ID=${ACCOUNT_ID}" | tee -a ~/.bash_profile
echo "export AWS_REGION=${AWS_REGION}" | tee -a ~/.bash_profile
aws configure set default.region ${AWS_REGION}
aws configure get default.region
```

### Validar el rol de IAM

Usa el comando de la CLI [GetCallerIdentity](https://docs.aws.amazon.com/cli/latest/reference/sts/get-caller-identity.html) Cpara  validar que el IDE de Cloud9 está usando el rol de IAM que corresponde.

```
aws sts get-caller-identity --query Arn | grep eksworkshop-admin -q && echo "IAM role valid" || echo "IAM role NOT valid"
```

Si el rol de IAM no es válido, <span style="color: red;">**NO CONTINÚES**</span>. Vuelve a realizar los pasos descriptos en esta página.
