---
title: 'Teams para datos altamente regulados '
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Cree un equipo seguro para almacenar los archivos más importantes y confidenciales.
ms.openlocfilehash: 5117d310ccd877a7377e6e538e7fba13daaad4ef
ms.sourcegitcommit: 80dc9ceb14e3eb3ae61b0fc2c8c3d73d564a7ef9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2019
ms.locfileid: "37617268"
---
# <a name="teams-for-highly-regulated-data"></a>Teams para datos altamente regulados 

Este artículo contiene recomendaciones y pasos para configurar un equipo privado en Microsoft Teams que bloquea el acceso a las características de Teams (como chats, reuniones y archivos) únicamente a los miembros y propietarios del grupo de Office 365 para el equipo. 

Más allá del acceso privado basado en el grupo de Office 365, este artículo describe cómo configurar el sitio de grupo de SharePoint privado subyacente, al que puede obtener acceso desde la sección **Archivos** de un canal de equipo, para la seguridad adicional que necesita para almacenar datos altamente regulados. En este sitio de grupo de SharePoint, puede almacenar y colaborar en archivos, páginas, un calendario compartido, tareas, un bloc de notas y listas.

Los elementos de configuración para un equipo para datos altamente regulados son:

- Un equipo privado con el grupo de Office 365 correspondiente que tenga cuentas de usuario del propietario y de los miembros.
- Seguridad adicional en el sitio de SharePoint subyacente para el equipo que:
  - Impide que los miembros del sitio concedan acceso a otros usuarios.
  - Impide que los usuarios que no sean miembros del sitio soliciten acceso al sitio.
- Una etiqueta de retención de Office 365 para el sitio de SharePoint subyacente que se aplica automáticamente a los nuevos archivos en el sitio de forma predeterminada para definir directivas de retención.
- Una directiva de prevención de pérdida de datos (DLP) que usa la etiqueta de retención y bloquea a los usuarios para que no puedan compartir o enviar archivos fuera de la organización.
- Una etiqueta de confidencialidad de Office 365 o una subetiqueta de una etiqueta altamente regulada que tiene permisos de cifrado y coautoría en el grupo de Office 365 del equipo. Los usuarios pueden aplicar la etiqueta o subetiqueta a archivos almacenados en la sección **Archivos** del equipo desde la opción Sensibilidad de la barra de menú en Word, Excel y PowerPoint.

Esta es la configuración resultante con una etiqueta de sensibilidad.

![Configuración segura del escenario de equipo](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)
 
## <a name="configuration"></a>Configuración

La configuración descentralizada de un equipo seguro consta de los siguientes pasos:

1. Configure el acceso a dispositivos e identidades
2. Cree un equipo privado
3. Configure la seguridad adicional en el sitio de SharePoint subyacente.
4. Cree una etiqueta de retención y una directiva DLP.
5. Cree la etiqueta o subetiqueta de la etiqueta altamente regulada.

### <a name="step-1-configure-identity-and-device-access"></a>Paso 1: Configure el acceso a dispositivos e identidades

Para proteger el acceso al equipo de SharePoint subyacente, asegúrese de haber configurado las [directivas de acceso de identidades y dispositivos](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) y las [directivas de acceso recomendadas de SharePoint Online](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).

### <a name="step-2-create-a-private-team"></a>Paso 2: Cree un equipo privado

Siga [estas instrucciones](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) para crear un equipo privado.

Cuando se crea un equipo privado, estos son los permisos predeterminados:

- El grupo de Office 365 para el equipo (el grupo de equipo) tiene propietarios de grupos y miembros de grupos
- Para el sitio de SharePoint subyacente del equipo (el sitio de Equipo):
  - Los administradores de la colección de sitios están configurados para los propietarios del grupo de Equipo
  - Para el sitio de Equipo: 
    - El grupo de SharePoint de propietarios del sitio de Equipo (con el nivel de permisos control total) está configurado en los propietarios del grupo de Equipo.
    - El grupo de SharePoint de miembros del sitio de Equipo (con el nivel de permisos de edición) está configurado para los miembros del grupo de Equipo.
    - El grupo de SharePoint de visitantes del sitio de Equipo (con el nivel de permisos de lectura) no tiene grupos ni cuentas de usuario

Estos son los permisos predeterminados para el sitio de Equipo.

![Los permisos predeterminados de un sitio de Equipo](./media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
>Si ve el grupo de SharePoint \<nombre de equipo> grupo de propietarios de SharePoint para el nivel de permisos de edición, no se mostrará \<nombre de equipo> Propietarios.
>

Los permisos resultantes permiten lo siguiente:

- Que los propietarios de los grupos de Team administren el sitio y tengan control total sobre el contenido del sitio.
- Que los miembros de los grupos de Team puedan crear y editar archivos en el sitio. 

El mantenimiento de permisos es el mismo que el mantenimiento del miembro del equipo y del propietario.

Esta es la configuración resultante hasta ahora.

![Paso 2 de la configuración segura del escenario de equipo](./media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a>Paso 3: Configure la seguridad adicional en el sitio de SharePoint subyacente

Desde el sitio de Equipo, configure estos ajustes de permisos.

1. En la barra de herramientas, haga clic en el icono de configuración y, luego, en **Permisos del sitio**.
2. En **Permisos del sitio**, haga clic en **Configuración de uso compartido** y después en **Cambiar configuración de uso compartido**.
3. En **Permisos de uso compartido**, elija **Solo los propietarios del sitio pueden compartir archivos, carpetas y el sitio**.
4. Desactive **Permitir solicitudes de acceso** y, después, haga clic en **Guardar**.

Con estos ajustes de configuración, se deshabilita la posibilidad de que los miembros del grupo de Equipo compartan el sitio con otros miembros o que los usuarios que no son miembros soliciten el acceso al sitio de Equipo.

Esta es la configuración resultante hasta ahora.

![Paso 3 de la configuración segura del escenario de equipo](./media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a>Paso 4: Cree una etiqueta de retención y una directiva DLP.

Siga [estas instrucciones](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) para:

1. Crear y publicar una etiqueta de retención para datos altamente regulados (si es necesario).
2. Configurar el sitio de Equipo para la etiqueta de retención que creó en el paso 1.
3. Crear una directiva DLP para datos altamente regulados que usen la etiqueta de retención creada en el paso 2 y bloquee el envío de archivos fuera de la organización por parte de los usuarios. También puede configurar la directiva para requerimientos adicionales, como por ejemplo, las regulaciones de las industrias de salud y finanzas, en función de las [plantillas de directiva de DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).

Esta es la configuración resultante hasta ahora.

![Paso 4 de la configuración segura del escenario de equipo](./media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-the-label-or-a-sublabel-of-the-highly-regulated-label"></a>Paso 5: Cree la etiqueta o una subetiqueta de la etiqueta altamente regulada.

A diferencia de una etiqueta de confidencialidad para datos altamente regulados que cualquier persona puede aplicar a cualquier archivo, un equipo seguro necesita su propia etiqueta o sub-etiqueta para que los archivos asignados:

- Se cifren y el cifrado se desplace con el archivo.
- Contengan permisos personalizados para que solo los miembros del grupo de Equipo puedan abrirlo.

Para lograr este nivel adicional de seguridad para los archivos almacenados en el sitio de Equipo, debe configurar una nueva etiqueta de confidencialidad que sea su propia etiqueta o una sub-etiqueta de la etiqueta general para archivos altamente regulados. Solo los miembros del grupo de Equipo la verán en su lista de etiquetas.

Usar una etiqueta de confidencialidad cuando necesite representa un número reducido de etiquetas tanto para los equipos de uso global como para los individuales privados. Utilice una subetiqueta de confidencialidad cuando tenga un gran número de etiquetas o cuando desee organizar las etiquetas para equipos privados bajo su etiqueta altamente regulada.

[Siga estas instrucciones ](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar una etiqueta independiente o subetiqueta con la siguiente configuración:

- El nombre de la etiqueta contiene el nombre del equipo
- El cifrado está habilitado
- El grupo de Equipo tiene permisos de Coautor

Esta es la configuración resultante con la nueva etiqueta.

![Paso 5 de la configuración segura del escenario de equipo](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

Esta es la relación entre la etiqueta de confidencialidad y el grupo de Equipo.

![Relación entre el grupo de Equipo y los permisos de etiqueta](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
>Si configura la etiqueta o subetiqueta de confidencialidad para los permisos definidos por el usuario o con una fecha de expiración, no podrá abrir el archivo desde Teams o SharePoint Online. Debe usar una aplicación de Office.
>

## <a name="using-the-team-and-a-sensitivity-label"></a>Usar el equipo y una etiqueta de confidencialidad

Los miembros del grupo de Equipo pueden obtener acceso al equipo y a todos sus recursos, incluidos chats, reuniones y otras aplicaciones. Al trabajar con archivos de la sección **Archivos** de un canal, los miembros del grupo de Equipo deben asignar la etiqueta o subetiqueta de confidencialidad a los archivos creados para el equipo seguro. He aquí un ejemplo.

![Ejemplo de una etiqueta aplicada a un archivo de un equipo seguro](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
Cuando la etiqueta se aplica al archivo está protegido. Los miembros del grupo de Equipo pueden abrirlo en Teams y colaborar en tiempo real. Se cifra y se incluyen los permisos de coautoría establecidos para los miembros del grupo de Equipo. Si el archivo abandona el sitio y se reenvía a un usuario malintencionado, tendrá que proporcionar credenciales de una cuenta de usuario que sea miembro del grupo de Equipo para abrir el archivo y ver su contenido. 

Puede ver qué archivos tienen una etiqueta asignada viendo una carpeta en SharePoint Online y añadiendo la columna **Confidencialidad** a través de la opción **Mostrar/ocultar columnas** que está en **Añadir columna**.

## <a name="custom-permissions"></a>Permisos personalizados

También puede configurar permisos personalizados de sitio de SharePoint para el sitio de Equipo y, si es necesario, su etiqueta de confidencialidad correspondiente. Aquí se muestran dos ejemplos.

### <a name="example-1-delegating-sharepoint-site-administration"></a>Ejemplo 1: Delegar la administración del sitio de SharePoint

Si el propietario del equipo no tiene la experiencia de administración de SharePoint o desea delegar la administración del sitio de Equipo, puede agregar la cuenta de usuario de un administrador del servicio de SharePoint a la lista de los propietarios del equipo. Sin embargo, el administrador del servicio de SharePoint tendría acceso total al equipo y a todos sus recursos, y podrá abrir un archivo con la etiqueta de sensibilidad aplicada. 

Para impedir que esto otorgue demasiados privilegios, agregue la cuenta de usuario del administrador del servicio de SharePoint al grupo de SharePoint Propietarios del sitio de Equipo en la configuración de permisos avanzados del sitio. El administrador del servicio de SharePoint puede administrar el sitio, pero no podrá tener acceso al equipo y a ninguno de sus recursos, ni abrir los archivos con la etiqueta de sensibilidad asignada.

### <a name="example-2-allowing-view-only-access-to-labeled-files"></a>Ejemplo 2: Permitir el acceso de solo lectura a archivos etiquetados

Si el personal solo necesita ver el contenido de los archivos con etiquetas en el sitio de Equipo, agregue sus cuentas de usuario individuales al:

- \<nombre de equipo > Grupo de visitantes de SharePoint, que tiene el nivel de permisos de lectura de forma predeterminada. 
- La etiqueta de sensibilidad con los permisos del Visualizador.

Estos son los permisos resultantes en la etiqueta.

![Ejemplo de permisos personalizados para ver archivos etiquetados](./media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
Los visitantes del sitio podrán tener acceso al sitio de Equipo directamente y ver el contenido de los archivos que tienen la subetiqueta aplicada. Pero, como no son miembros del grupo de Equipo, no podrán tener acceso al equipo ni a ninguno de sus recursos.

## <a name="see-also"></a>Vea también

[Sitios de SharePoint para datos extremadamente regulados](teams-sharepoint-online-sites-highly-regulated-data.md)

[Guía de implementación](deploy-microsoft-365-enterprise.md)
