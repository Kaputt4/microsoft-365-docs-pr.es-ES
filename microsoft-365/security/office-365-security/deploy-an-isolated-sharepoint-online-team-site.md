---
title: Implementar un sitio de grupo de SharePoint Online aislado
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: Use esta guía de implementación paso a paso para crear y configurar un sitio de grupo aislado de SharePoint Online en Microsoft Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b1f0342afc92b4540330417ad0fc9cabe1dc8a8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165504"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a>Implementar un sitio de grupo de SharePoint Online aislado

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

 **Resumen:** Implemente un nuevo sitio de grupo aislado de SharePoint Online con estas instrucciones paso a paso.

Este artículo es una guía de implementación paso a paso para crear y configurar un sitio de grupo de SharePoint Online aislado en Microsoft Office 365. Estos pasos suponen el uso de los tres grupos de SharePoint predeterminados y los niveles de permisos correspondientes, con un único grupo de acceso basado en Azure Active Directory (AD) para cada nivel de acceso.

## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a>Fase 1: Crear y rellenar los grupos de acceso al sitio de grupo

En esta fase, creará los tres grupos de acceso basados en Azure AD para los tres grupos de SharePoint predeterminados y los rellenará con las cuentas de usuario adecuadas.

> [!NOTE]
> En los pasos siguientes se supone que ya existen todas las cuentas de usuario necesarias y que se les asignan las licencias correspondientes. Si no es así, agrédalos y asigne licencias antes de continuar con el paso 1.

### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a>Paso 1: Enumerar los administradores de SharePoint Online para el sitio

Determine el conjunto de cuentas de usuario correspondiente a los administradores de SharePoint Online para el sitio de grupo aislado.

Si administra cuentas de usuario y grupos a través de Microsoft 365 y desea usar Windows PowerShell, haga una lista de sus nombres principales de usuario (UPN) (por ejemplo, UPN: belindan@contoso.com).

### <a name="step-2-list-the-members-for-the-site"></a>Paso 2: Enumerar los miembros del sitio

Determine el conjunto de cuentas de usuario correspondiente a los miembros del sitio de grupo aislado, aquellos que colaborarán en los recursos almacenados en el sitio.

Si está administrando cuentas de usuario y grupos a través de Microsoft 365 y desea usar PowerShell, haga una lista de sus UPN. Si hay una gran cantidad de miembros del sitio, puede almacenar la lista de UPN en un archivo de texto y agregarlos todos con un solo comando de PowerShell.

### <a name="step-3-list-the-viewers-for-the-site"></a>Paso 3: Enumerar los visores del sitio

Determine el conjunto de cuentas de usuario correspondiente a los visores del sitio de grupo aislado, aquellos que pueden ver los recursos almacenados en el sitio pero no modificarlos o colaborar directamente en su contenido.

Si está administrando cuentas de usuario y grupos a través de Microsoft 365 y desea usar PowerShell, haga una lista de sus UPN. Si hay una gran cantidad de miembros del sitio, puede almacenar la lista de UPN en un archivo de texto y agregarlos todos con un solo comando de PowerShell.

Los visores del sitio pueden incluir la administración ejecutiva, los asesores legales o las partes interesadas entre departamentos.

### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a>Paso 4: Crear los tres grupos de acceso para el sitio en Azure AD

Debe crear los siguientes grupos de acceso en Azure AD:

- Administradores del sitio (que contendrán la lista del paso 1)
- Miembros del sitio (que contendrán la lista del paso 2)
- Visores de sitios (que contendrán la lista del paso 3)

1. En el explorador, vaya a Azure Portal e inicie sesión con las credenciales de una cuenta asignada con el rol administrador de administración de usuarios o <https://portal.azure.com> administrador de la compañía.

2. En Azure Portal, haga clic en **Azure Active Directory > Grupos**.

3. En la hoja **Todos los grupos**, haga clic en **+ Nuevo grupo**.

4. En la **hoja Nuevo** grupo:

   - Seleccione **Seguridad** en **Tipo de grupo**.

   - Escriba el nombre del grupo en **Nombre**.

   - Escriba una descripción del grupo en la **descripción del grupo.**

   - Seleccione **Asignada** en **Tipo de pertenencia**.

5. Haga clic en **Crear** y, después, cierre la hoja **Grupo**.

6. Repita los pasos del 3 al 5 para los grupos adicionales.

> [!NOTE]
> Debe usar Azure Portal para crear los grupos de modo que tengan habilitadas las características de Office. Si un sitio aislado de SharePoint Online se configura más adelante como un sitio extremadamente confidencial con una etiqueta de Azure Information Protection para cifrar archivos y asignar permisos a grupos específicos, los grupos permitidos deben haber sido creados con las características de Office habilitadas. No puede cambiar la configuración de características de Office de un grupo de Azure AD después de crearlo.

Esta es la configuración resultante con los tres grupos de acceso al sitio.

![Los tres grupos de acceso para la implementación de un sitio aislado de SharePoint Online.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)

### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a>Paso 5. Agregar las cuentas de usuario a los grupos de acceso

En este paso, haga lo siguiente:

1. Agregue la lista de usuarios del paso 1 al grupo de acceso de administradores del sitio.
2. Agregue la lista de usuarios del paso 2 al grupo de acceso de miembros del sitio.
3. Agregue la lista de usuarios del paso 3 al grupo de acceso de visores del sitio.

Si administra cuentas de usuario y grupos a través de servicios de dominio de Active Directory (AD DS), agregue usuarios a los grupos de acceso adecuados mediante los procedimientos normales de administración de usuarios y grupos de AD DS y espere a que se la sincronización con su suscripción de Microsoft 365.

Si administra cuentas de usuario y grupos a través de Office 365, puede usar el Centro de administración de Microsoft 365 o PowerShell. Si tiene nombres de grupo duplicados para cualquiera de los grupos de acceso, debe usar el Centro de administración de Microsoft 365.

Para el Centro de administración de Microsoft 365, inicie sesión con una cuenta de usuario que tenga asignado el rol Administrador de cuentas de usuario o Administrador de la compañía y use Grupos para agregar las cuentas de usuario y los grupos adecuados a los grupos de acceso adecuados.

Para PowerShell, primero [conéctese con el módulo Azure Active Directory PowerShell para Graph.](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)

A continuación, use el siguiente bloque de comandos para agregar una cuenta de usuario individual a un grupo de acceso:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Si almacenaste los UPN de las cuentas de usuario para cualquiera de los grupos de acceso en un archivo de texto, puedes usar el siguiente bloque de comandos de PowerShell para agregarlos todos a la vez:

```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

Para PowerShell, use el siguiente bloque de comandos para agregar un grupo individual a un grupo de acceso:

```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Los resultados deben ser los siguientes:

- El grupo de administradores del sitio de Azure AD contiene los grupos o cuentas de usuario de administrador del sitio
- El grupo de Azure AD de los miembros del sitio contiene las cuentas de usuario o grupos de miembros del sitio
- El grupo de visores de sitios de Azure AD contiene las cuentas de usuario o grupos que solo pueden ver el contenido del sitio

Valide la lista de miembros del grupo para cada grupo de acceso con el Centro de administración de Microsoft 365 o con el siguiente bloque de comandos de PowerShell:

```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

Esta es la configuración resultante con los tres grupos de acceso al sitio rellenados con cuentas de usuario o grupos.

![Los tres grupos de acceso se rellenan con cuentas de usuario.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)

## <a name="phase-2-create-and-configure-the-isolated-team-site"></a>Fase 2: Crear y configurar el sitio de grupo aislado

En esta fase, creará el sitio aislado de SharePoint Online y configurará los permisos para los niveles de permisos predeterminados de SharePoint Online para usar los nuevos grupos de acceso basados en Azure AD. De forma predeterminada, los nuevos sitios de grupo incluyen un grupo de Microsoft 365 y otros recursos relacionados, pero en este caso, crearemos un sitio de grupo sin un grupo de Microsoft 365. Esto permite mantener los permisos completamente a través de SharePoint.

En primer lugar, cree el sitio de grupo de SharePoint Online con estos pasos.

1. Inicie sesión en el Centro de administración de Microsoft 365 con una cuenta que también se usará para administrar el sitio de grupo de SharePoint Online (un administrador de SharePoint Online). Para obtener ayuda, vea [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).

2. En el Centro de administración de Microsoft 365, en **Centros de administración,** haga clic **en SharePoint.**

3. En el Centro de administración de SharePoint, expanda **Sitios** y haga clic **en Sitios activos.**

4. Haga **clic en** Crear y, a continuación, elija **Otras opciones.**

5. En la **lista Elegir una plantilla,** elija **Sitio de grupo.**

6. En **Nombre del sitio,** escriba un nombre para el sitio de grupo.

7. En **administrador principal,** escriba la cuenta con la que ha iniciado sesión.

8. Haga clic en **Finalizar**.

A continuación, desde el nuevo sitio de grupo de SharePoint Online, configure los permisos.

1. En la barra de herramientas, haga clic en el icono de configuración y, luego, en **Permisos del sitio**.

2. En **Uso compartido de sitios,** haga clic en Cambiar cómo pueden compartir los **miembros.**

3. Elija el **único sitio que los propietarios pueden compartir archivos, carpetas y el sitio.**

4. Establezca **Permitir solicitudes de acceso** en **Desactivado.**

5. Haga clic en **Guardar**.

6. En el **panel Permisos,** haga clic **en Configuración avanzada de permisos.**

7. En la **pestaña Permisos** del explorador, haga clic **\<site name> en Miembros** de la lista.

8. En **Personas y grupos**, haga clic en **Nuevo**.

9. En el **cuadro de** diálogo Compartir, escriba el nombre del grupo de acceso de miembros del sitio, selecciónelo y, a continuación, haga clic en **Compartir**.

10. Haga clic en el botón Atrás del explorador.

11. Haga **\<site name> clic en Propietarios** en la lista.

12. En **Personas y grupos**, haga clic en **Nuevo**.

13. En el **cuadro de** diálogo Compartir, escriba el nombre del grupo de acceso de administradores del sitio, selecciónelo y, a continuación, haga clic en **Compartir.**

14. Haga clic en el botón Atrás del explorador.

15. Haga **\<site name> clic en** Visitantes de la lista.

16. En **Personas y grupos**, haga clic en **Nuevo**.

17. En el **cuadro de** diálogo Compartir, escriba el nombre del grupo de acceso de visores del sitio, selecciónelo y, a continuación, haga clic en **Compartir**.

18. Cierre la pestaña **Permisos** del explorador.

Los resultados de esta configuración de permisos son los siguientes:

- El **\<site name> grupo propietarios** de SharePoint contiene el grupo de acceso de administradores del sitio, en el que todos los miembros tienen el **nivel de permisos control** total.
- El **\<site name> grupo de** Miembros de SharePoint contiene el grupo de acceso de miembros del sitio, en el que todos los miembros tienen el **nivel de** permisos Editar.
- El **\<site name> grupo visitantes** de SharePoint contiene el grupo de acceso de visores del sitio, en el que todos los miembros tienen el nivel **de** permisos de lectura.
- La posibilidad de que los miembros inviten a otros miembros o que no miembros soliciten acceso está deshabilitada.

Esta es la configuración resultante con los tres grupos de SharePoint para el sitio configurados para usar los tres grupos de acceso, que se rellenan con cuentas de usuario o grupos de Azure AD.

![La configuración final del sitio aislado de SharePoint Online con grupos de acceso y cuentas de usuario.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)

Usted y los miembros del sitio, a través de la pertenencia a grupos en uno de los grupos de acceso, ahora pueden colaborar con los recursos del sitio.

## <a name="next-step"></a>Paso siguiente

Cuando necesite cambiar la pertenencia al grupo de acceso al sitio o crear una carpeta de documentos con permisos personalizados, vea Administrar un sitio de grupo de [SharePoint Online aislado.](manage-an-isolated-sharepoint-online-team-site.md)

## <a name="see-also"></a>Vea también

[Sitios de grupo de SharePoint Online aislados](isolated-sharepoint-online-team-sites.md)

[Diseñar un sitio de grupo de SharePoint Online aislado](design-an-isolated-sharepoint-online-team-site.md)

[Administrar un sitio de grupo de SharePoint Online aislado](manage-an-isolated-sharepoint-online-team-site.md)
