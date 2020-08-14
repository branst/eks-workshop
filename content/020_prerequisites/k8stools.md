---
title: "Instalar las herramientas de Kubernetes"
chapter: false
weight: 15
---

Los clusters de Amazon EKS requieren kubectl, los binarios de kubelet y la aws-cli o el binario de aws-iam-authenticator
para permitir la autenticación de IAM para tu cluster de Kubernetes.

{{% notice tip %}}
En este workshop vamos a dar los comandos para descargar los binarios de Linux. Si estás ejecutando Mac OSX / Windows, [ver la documentación oficial de EKS para los links de descarga
.](https://docs.aws.amazon.com/eks/latest/userguide/getting-started.html)
{{% /notice %}}

#### Instalar kubectl

```bash
sudo curl --silent --location -o /usr/local/bin/kubectl \
  https://amazon-eks.s3.us-west-2.amazonaws.com/1.17.7/2020-07-08/bin/linux/amd64/kubectl

sudo chmod +x /usr/local/bin/kubectl
```

#### Actualizar la awscli

Actualizar la AWS CLI de acuerdo a lo indicado en la [documentación de AWS](https://docs.aws.amazon.com/cli/latest/userguide/install-linux.html).

```bash
sudo pip install --upgrade awscli && hash -r
```

#### Instalar jq, envsubst (de las utilidades gettext de GNU) y  and bash-completion

```bash
sudo yum -y install jq gettext bash-completion moreutils
```

#### Instalar yq para el procesamiento de yaml 

```bash
echo 'yq() {
  docker run --rm -i -v "${PWD}":/workdir mikefarah/yq yq "$@"
}' | tee -a ~/.bashrc && source ~/.bashrc
```

#### Verificar que los binarios se encuentran en el path correspondiente y son ejecutables

```bash
for command in kubectl jq envsubst aws
  do
    which $command &>/dev/null && echo "$command in path" || echo "$command NOT FOUND"
  done
```

#### Habilitar kubectl bash_completion

```bash
kubectl completion bash >>  ~/.bash_completion
. /etc/profile.d/bash_completion.sh
. ~/.bash_completion
```

#### configurar la versión del Ingress Controller del AWS ALB

```bash
echo 'export ALB_INGRESS_VERSION="v1.1.8"' >>  ~/.bash_profile
.  ~/.bash_profile
```
