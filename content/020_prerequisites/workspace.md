---
title: "Crear un Workspace"
chapter: false
weight: 14
---

{{% notice warning %}}
El workspace de Cloud9 debe ser creado por un usuario IAM con privilegios de Administrador, no por el usuario con acceso root a la cuenta. Por favor, asegurarse de haber ingresado como un usuario IAM y no el usuario root.
{{% /notice %}}

<!---
{{% notice info %}}
This workshop was designed to run in the **Oregon (us-west-2)** region. **Please don't
run in any other region.** Future versions of this workshop will expand region availability,
and this message will be removed.
{{% /notice %}}
-->

{{% notice tip %}}
Deben deshabilitarse los Ad blockers, javascript disablers y tracking blockers para el dominio de Cloud9 ya que la conexión al workspace podría verse impactada.
Cloud9 requiere cookies de terceros. Puedes colocar en whitelist los [dominios específicos]( https://docs.aws.amazon.com/cloud9/latest/user-guide/troubleshooting.html#troubleshooting-env-loading).
{{% /notice %}}

### Lanzar Cloud9 en la región más cercana: -> Revisar
{{< tabs name="Region" >}}
{{{< tab name="Oregon" include="us-west-2.md" />}}
{{{< tab name="Ireland" include="eu-west-1.md" />}}
{{{< tab name="Ohio" include="us-east-2.md" />}}
{{{< tab name="Singapore" include="ap-southeast-1.md" />}}
{{< /tabs >}}

- Seleccionar **Create environment**
- Nombrarlo **eksworkshop**, click en Next.
- Elegir el tipo de instancia **"t3.small"**, tomar todos los valores por defecto y hacer click en **Create environment**
- Cuando inicialice, cerrar la **tab de bienvenida (1)** y 
 el **area de trabajo inferior (2)**. Por último, abrir una nueva **terminal (3)** en el área de trabajo principal:
![c9before](/images/c9before.png)

- Tu workspace debería verse ahora de la siguiente manera:
![c9after](/images/c9after.png)


