---
title: Sitio de grupo de SharePoint Online aislado en su entorno para desarrollo y pruebas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 'Resumen: configure un sitio de grupo de SharePoint Online que esté aislado del resto de la organización en su entorno de desarrollo y pruebas de Microsoft 365.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ba1ddb2b5123db80be91f40c4fce8c6e2eb3d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286614"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>Sitio de grupo de SharePoint Online aislado en su entorno para desarrollo y pruebas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 de Microsoft Defender para Office 365](office-365-atp.md)
- SharePoint Online 


 **Resumen:** Configure un sitio de grupo de SharePoint Online aislado del resto de la organización en su entorno de desarrollo y pruebas de Microsoft 365.

Los sitios de grupo de SharePoint Online en Microsoft 365 son ubicaciones para colaboración mediante una biblioteca de documentos común, un bloc de notas de OneNote y otros servicios. En muchos casos, deseará contar con un acceso amplio y una colaboración entre departamentos u organizaciones. Sin embargo, en algunos casos, desea controlar estrechamente el acceso y los permisos de colaboración entre un pequeño grupo de personas.

El acceso a los sitios de grupo de SharePoint Online y lo que los usuarios pueden hacer se controla mediante grupos de SharePoint y niveles de permisos. De forma predeterminada, los sitios de SharePoint Online cuentan con tres niveles de acceso:

- **Miembros**, que pueden ver, crear y modificar los recursos del sitio.
- **Propietarios**, que tienen un control total sobre el sitio y pueden cambiar los permisos.
- **Visitantes**, que únicamente pueden ver los recursos del sitio.

En este artículo, se indican los pasos que se deben seguir para configurar un sitio de grupo de SharePoint Online aislado para un proyecto de investigación secreto, que llamaremos ProyectoX. Los requisitos de acceso son:

- Solo los miembros del proyecto pueden acceder al sitio y a su contenido (documentos, Bloc de notas de OneNote y páginas), con niveles de permiso de SharePoint de edición y visualización controlados a través de la pertenencia al grupo.

- Únicamente el creador del sitio y los miembros de un grupo de administradores del sitio pueden llevar a cabo tareas relacionadas con la administración, lo que incluye la modificación de los permisos del sitio.

Hay tres fases para configurar un sitio de grupo de SharePoint Online aislado en el entorno de desarrollo y pruebas de Microsoft 365:

1. Cree el entorno de desarrollo y pruebas de Microsoft 365.

2. Crear los usuarios y los grupos de ProyectoX.

3. Crear un sitio de grupo de SharePoint Online para ProyectoX y aislarlo.

> [!TIP]
> Haga clic [aquí](https://aka.ms/catlgstack) para ver un mapa visual de todos los artículos en la pila de la Guía del entorno de pruebas de One Microsoft Cloud.

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a>Fase 1: Crear un entorno de desarrollo y pruebas ligero o simulado de Microsoft 365

Si solo desea crear un sitio de grupo aislado de SharePoint Online de forma ligera con los requisitos mínimos, siga las instrucciones de las fases 2 y 3 de la configuración [básica ligera.](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

Si desea crear un sitio de grupo aislado de SharePoint Online en una configuración empresarial simulada, siga las instrucciones de sincronización de hash de contraseña para su entorno de prueba de [Microsoft 365.](../../enterprise/password-hash-sync-m365-ent-test-environment.md)

> [!NOTE]
> La creación de un sitio aislado de SharePoint Online no requiere el entorno de desarrollo y pruebas empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como opción para que pueda probar un sitio de SharePoint Online aislado y experimentar con él en un entorno que representa una organización típica.

## <a name="phase-2-create-user-accounts-and-access-groups"></a>Fase 2: Crear cuentas de usuario y grupos de acceso

Siga las instrucciones de Conectarse a PowerShell de [Office 365](../../enterprise/connect-to-microsoft-365-powershell.md) para conectarse a su suscripción de prueba con su cuenta de administrador global desde:

- Su equipo (para el entorno ligero de desarrollo y pruebas de Microsoft 365).

- La máquina virtual CLIENT1 (para el entorno de desarrollo y pruebas de una empresa simulada de Microsoft 365).

Para crear los nuevos grupos de acceso para el sitio de grupo de SharePoint Online de ProjectX, ejecute estos comandos desde el símbolo del sistema del módulo Windows Azure Active Directory para Windows PowerShell usuario:

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

Rellene el nombre de la organización (ejemplo: contosotoycompany), el código de país de dos caracteres para su ubicación y, después, ejecute los comandos siguientes desde el símbolo del sistema de Módulo Microsoft Azure Active Directory para Windows PowerShell:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

En la pantalla del comando **New-MsolUser**, anote la contraseña generada para la cuenta del responsable de diseño y guárdela en un lugar seguro.

Ejecute los siguientes comandos desde el símbolo del sistema del Módulo de Windows Azure Active Directory para Windows PowerShell:

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

En la pantalla del comando **New-MsolUser**, anote la contraseña generada para la cuenta del responsable de investigación y guárdela en un lugar seguro.

Ejecute los siguientes comandos desde el símbolo del sistema del Módulo de Windows Azure Active Directory para Windows PowerShell:

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

En la pantalla del comando **New-MsolUser**, anote la contraseña generada para la cuenta del vicepresidente de investigación y guárdela en un lugar seguro.

A continuación, para agregar las nuevas cuentas a los nuevos grupos de acceso, ejecute estos comandos de PowerShell desde el Windows Azure módulo de Active Directory para Windows PowerShell solicitud:

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

Resultados:

- El ProjectX-Members de acceso contiene las cuentas de usuario diseñador de clientes potenciales e investigador principal

- El ProjectX-Admins de acceso de prueba contiene la cuenta de administrador global de la suscripción de prueba.

- El ProjectX-Viewers de acceso contiene la cuenta de usuario del vicepresidente de desarrollo

La figura 1 muestra los grupos de acceso y su pertenencia.

**Figura 1:**

![Los grupos de Microsoft 365 y su pertenencia a un sitio de grupo de SharePoint Online aislado](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>Fase 3: Crear un sitio de grupo de SharePoint Online para ProyectoX y aislarlo

Para crear un sitio de grupo de SharePoint Online para ProyectoX, siga estos pasos:

1. Con un explorador en el equipo local (configuración ligera) o en CLIENT1 (configuración empresarial simulada), inicie sesión en el Centro de administración de Microsoft 365 ( ) con su cuenta de administrador <https://admin.microsoft.com> global.

2. En la lista de iconos, haga clic en **SharePoint**.

3. En la nueva pestaña de SharePoint del explorador, haga clic en **+ Crear sitio**.

4. En **Nombre del sitio de grupo**, escriba **ProyectoX**. En **configuración de privacidad,** seleccione **Privado: solo los miembros pueden acceder a este sitio.**

5. En **Descripción del sitio de grupo**, escriba **Sitio de SharePoint para ProyectoX** y, a continuación, haga clic en **Siguiente**.

6. En el panel **¿A quién quiere agregar?**, haga clic en **Finalizar**.

7. En la nueva pestaña **ProyectoX-Inicio** del explorador, en la barra de herramientas, haga clic en el icono de configuración y, a continuación, en **Permisos del sitio**.

8. En el panel **Permisos del sitio**, haga clic en **Configuración avanzada de permisos**.

9. En la nueva pestaña **Permisos: ProyectoX** del explorador, haga clic en **Configuración de solicitud de acceso**.

10. En el cuadro de diálogo **Configuración de solicitud de acceso**, desactive **Permitir que los miembros compartan el sitio y archivos y carpetas individuales** y **Permitir solicitudes de acceso** (de modo que las tres casillas estén desactivadas) y, a continuación, haga clic en **Aceptar**.

11. Haga clic en la opción **Miembros del ProyectoX** de la lista.

12. En la página **Personas y grupos**, haga clic en **Nuevo**.

13. En el cuadro de diálogo **Compartir**, escriba **Miembros del ProyectoX**, seleccione esta opción y, a continuación, haga clic en **Compartir**.

14. Haga clic en el botón Atrás del explorador.

15. Haga clic en la opción **Propietarios del ProyectoX** de la lista.

16. En la página **Personas y grupos**, haga clic en **Nuevo**.

17. En el cuadro de diálogo **Compartir**, escriba **Administradores del ProyectoX**, seleccione esta opción y, a continuación, haga clic en **Compartir**.

18. Haga clic en el botón Atrás del explorador.

19. Haga clic en la opción **Visitantes del ProyectoX** de la lista.

20. En la página **Personas y grupos**, haga clic en **Nuevo**.

21. En el cuadro de diálogo **Compartir**, escriba **Lectores del ProyectoX**, seleccione esta opción y, a continuación, haga clic en **Compartir**.

22. Cierre la pestaña **Personas y grupos** del explorador, haga clic en la pestaña **Inicio del ProyectoX** del explorador y, a continuación, cierre el panel **Permisos del sitio**.

A continuación se indican los resultados de la configuración de permisos:

- El grupo de SharePoint Miembros de ProjectX contiene solo el grupo de acceso ProjectX-Members (que contiene solo las cuentas de usuario Diseñador de clientes potenciales e Investigador principal) y el grupo ProjectX (que contiene solo la cuenta de usuario de administrador global).

- El grupo de SharePoint Propietarios de ProjectX contiene solo el grupo ProjectX-Admins acceso (que contiene solo la cuenta de usuario de administrador global).

- El grupo de SharePoint De visitantes de ProjectX contiene solo el ProjectX-Viewers de acceso (que contiene solo la cuenta de usuario del vicepresidente de desarrollo).

- Los miembros no pueden modificar los permisos del nivel del sitio (solo los miembros del grupo “Administradores del ProyectoX” pueden realizar esta acción).

- El resto de cuentas de usuario no pueden tener acceso al sitio ni a sus recursos, y tampoco pueden solicitar acceso al sitio.

En la figura 2 se muestran los grupos de SharePoint y su pertenencia.

**Figura 2**

![Los grupos de SharePoint Online y su pertenencia a un sitio de grupo de SharePoint Online aislado](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

Ahora vamos a demostrar el acceso con la cuenta de usuario del diseñador de responsables:

1. Cierre la pestaña **Inicio del ProyectoX** del explorador y, a continuación, haga clic en la pestaña **Página principal de Microsoft Office**.

2. Haga clic en el nombre de su administrador global y, a continuación, en **Cerrar sesión**.

3. Inicie sesión en el Centro de administración de Microsoft 365 ( ) con el nombre de la cuenta del diseñador de clientes potenciales <https://admin.microsoft.com> y su contraseña.

4. En la lista de iconos, haga clic en **SharePoint**.

5. En la nueva pestaña **SharePoint** del explorador, escriba **ProyectoX** en el cuadro de búsqueda, active la búsqueda y, a continuación, haga clic en el sitio de grupo de **ProyectoX**. Debería ver una nueva pestaña para el sitio de grupo de ProyectoX en el explorador.

6. Haga clic en el icono de configuración. Fíjese en que no hay ninguna opción para **Permisos del sitio**. Esto es correcto, ya que solo los miembros del grupo Administradores del ProyectoX pueden modificar los permisos del sitio.

7. Abra el Bloc de notas o el editor de texto que prefiera.

8. Copie la dirección URL del sitio de grupo de ProyectoX y péguela en una nueva línea del Bloc de notas o su editor de texto.

9. En la pestaña **Inicio de ProyectoX** del explorador, haga clic en **Documentos**.

10. Copie la dirección URL de la carpeta de documentos del ProyectoX y péguela en una nueva línea del Bloc de notas o del editor de texto.

11. En la pestaña **Documentos del ProyectoX** del explorador, haga clic en **Nuevo > Documento de Word**.

12. Escriba texto en la página, espere a que el estado indique **Guardado,** haga clic en el botón Atrás en el explorador y, a continuación, actualice la página. Debería ver un nuevo **Documento.docx** en la carpeta **Documentos**.

13. Haga clic en el botón de puntos suspensivos del archivo **Documento.docx** y, a continuación, en **Obtener un vínculo**.

14. Copie la dirección URL en el cuadro de diálogo **Compartir "Document.docx",** péguela en una nueva línea del Bloc de notas o del editor de texto y, a continuación, cierre el cuadro de diálogo Compartir **"Document.docx".**

15. Cierre las pestañas **Documentos del ProyectoX** y **SharePoint** del explorador y, a continuación, haga clic en la pestaña **Página principal de Microsoft Office**.

16. Haga clic en el nombre del **responsable de diseño** y, a continuación, en **Cerrar sesión**.

Ahora vamos a demostrar el acceso con la cuenta de usuario del vicepresidente de desarrollo:

1. Inicie sesión en el Centro de administración de Microsoft 365 ( ) con el nombre de la cuenta del vicepresidente de desarrollo <https://admin.microsoft.com> y su contraseña.

2. En la lista de iconos, haga clic en **SharePoint**.

3. En la nueva pestaña **SharePoint** del explorador, escriba **ProyectoX** en el cuadro de búsqueda, active la búsqueda y, a continuación, haga clic en el sitio de grupo de **ProyectoX**. Debería ver una nueva pestaña para el sitio de grupo de ProyectoX en el explorador.

4. Haga clic en **Documentos** y, a continuación, en el archivo **Documento.docx**.

5. En la pestaña **Documento.docx** del explorador, intente modificar el texto. Debería ver un mensaje con el texto **El documento es de solo lectura**. Esto ocurre porque la cuenta de usuario de vicepresidente de desarrollo solo tiene permisos de visualización en el sitio.

6. Cierre las pestañas **Documento.docx**, **Documentos del ProyectoX** y **SharePoint** del explorador.

7. En la pestaña **Página principal de Microsoft Office**, haga clic en el nombre del **vicepresidente de desarrollo** y, a continuación, en **Cerrar sesión**.

Ahora vamos a demostrar el acceso con una cuenta de usuario que no tiene permisos:

1. Inicie sesión en el Centro de administración de Microsoft 365 ( ) con el nombre de la cuenta usuario <https://admin.microsoft.com> 3 y su contraseña.

2. En la lista de iconos, haga clic en **SharePoint**.

3. 	En la nueva pestaña **SharePoint** del explorador, escriba **ProyectoX** en el cuadro de búsqueda y, a continuación, active la búsqueda. Debería ver el mensaje **No se encontró nada que coincida con la búsqueda**.

4. Desde la instancia abierta del Bloc de notas o el editor de texto, copie la dirección URL del sitio del ProyectoX en la barra de direcciones del explorador y presione **Entrar**. Debería ver una página con el título **Acceso denegado**.

5. Desde la instancia abierta del Bloc de notas o el editor de texto, copie la dirección URL de la carpeta de documentos del ProyectoX en la barra de direcciones del explorador y presione **Entrar**. Debería ver una página con el título **Acceso denegado**.

6. Desde la instancia abierta del Bloc de notas o el editor de texto, copie la dirección URL del archivo Documentos.docx en la barra de direcciones del explorador y presione **Entrar**. Debería ver una página con el título **Acceso denegado**.

7. Desde la pestaña **SharePoint** de su explorador, haga clic en la pestaña **Página principal de Microsoft Office**, haga clic en el nombre **Usuario 3** y, a continuación, en **Cerrar sesión**.

El sitio aislado de SharePoint Online ya está listo para los experimentos adicionales.

## <a name="next-step"></a>Paso siguiente

Cuando esté preparado para implementar un sitio de grupo de SharePoint Online aislado en producción, vea las consideraciones de diseño paso a paso en [Diseñar un sitio de grupo aislado de SharePoint Online](design-an-isolated-sharepoint-online-team-site.md).

## <a name="see-also"></a>Vea también

[Sitios de grupo de SharePoint Online aislados](isolated-sharepoint-online-team-sites.md)

[Guías del entorno de pruebas de adopción de la nube (TLG)](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[Configuración básica empresarial simulada](../../enterprise/simulated-ent-base-configuration-microsoft-365-enterprise.md)

[Configuración básica ligera](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

[Centro de soluciones y arquitectura de Microsoft 365](../../solutions/index.yml)