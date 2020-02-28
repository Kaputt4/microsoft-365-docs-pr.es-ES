---
title: Usar etiquetas de confidencialidad con Microsoft Teams, grupos de Office 365 y sitios de SharePoint (versión preliminar pública)
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Puede aplicar etiquetas en Microsoft Teams, en grupos de Office 365 y en sitios de SharePoint.
ms.openlocfilehash: 611876b7e403c8d877c602d21967675adef2d061
ms.sourcegitcommit: 45ee610a380db113c2a50f6ea82d30137498babb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "42288583"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a>Usar etiquetas de confidencialidad con Microsoft Teams, grupos de Office 365 y sitios de SharePoint (versión preliminar pública)

Al crear etiquetas de confidencialidad en el [Centro de cumplimiento de Microsoft 365](https://protection.office.com/), ahora puede aplicarlas a los siguientes contenedores: Microsoft Teams, grupos de Office 365 y sitios de SharePoint. Use la configuración de etiquetas para controlar las opciones siguientes para estos contenedores:

- Privacidad de los sitios de equipos conectados a grupos de Office 365 (público o privado)
- Acceso de usuarios externos
- Acceso desde dispositivos no administrados 

Cuando aplica esta etiqueta a uno de los contenedores compatibles, la etiqueta aplica automáticamente las opciones configuradas en el sitio de SharePoint o en el sitio de grupo conectado. 

Sin embargo, el contenido de esos contenedores no hereda las etiquetas para configuraciones como el nombre de la etiqueta, las marcas visuales o el cifrado. Para etiquetar archivos en sitios de SharePoint o sitios de grupo, [habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a>Acerca de la versión preliminar pública para Microsoft Teams, grupos de Office 365 y sitios de SharePoint

Las etiquetas de confidencialidad de Microsoft Teams, grupos de Office 365 y sitios de SharePoint se están introduciendo gradualmente para los inquilinos y es posible que haya cambios antes de la versión final. Esta versión preliminar pública no funciona con las redes de entrega de contenido (CDN) de Office 365.

Antes de habilitar esta versión preliminar y configurar las etiquetas de confidencialidad para la nueva configuración, los usuarios pueden ver y aplicar etiquetas de confidencialidad en sus aplicaciones. Por ejemplo, en Word:

![Una etiqueta de confidencialidad mostrada en la aplicación de escritorio de Word](../media/sensitivity-label-word.png)

Después de habilitar y configurar esta versión preliminar, los usuarios también pueden ver y aplicar etiquetas de confidencialidad en Microsoft Teams, en los grupos de Office 365 y en los sitios de SharePoint. Por ejemplo, al crear un sitio de grupo de SharePoint:

![Una etiqueta de confidencialidad al crear un sitio de grupo de SharePoint](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a>Habilitar versión preliminar y sincronizar etiquetas

1. Dado que esta característica usa la funcionalidad de Azure AD, siga las instrucciones de la documentación de Azure AD para habilitar la versión preliminar: [asignar etiquetas de confidencialidad a grupos de Office 365 en Azure Active Directory (versión preliminar)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).

2. En una sesión de PowerShell, conéctese al Centro de seguridad y cumplimiento con una cuenta profesional o educativa con privilegios de administrador global. Para obtener instrucciones, consulte [Conectarse al Centro de seguridad y cumplimiento de Office 365 desde PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

3. Ejecute los siguientes comandos para sincronizar las etiquetas en Azure AD, de modo que se puedan usar con los grupos de Office 365:
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a>Cómo configurar opciones del sitio y los grupos al crear o editar etiquetas de confidencialidad

Ya está listo para crear o editar las etiquetas de confidencialidad que quiera y que estén disponibles para sitios y grupos. El habilitar la versión preliminar hace que una nueva página sea visible en los asistentes de etiquetas de confidencialidad: **Configuración de sitio y grupo**

Si necesita ayuda para crear o editar una etiquetas de confidencialidad, vea las instrucciones en [Crear y configurar etiquetas de confidencialidad](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).

En la nueva página **Configuración de sitio y grupo**, configure las opciones:

- **Privacidad de los sitios de equipos conectados a grupos de Office 365**: la configuración predeterminada como **pública** está seleccionada automáticamente, lo que significa que cualquier persona de su organización puede tener acceso al sitio de grupo en el que se aplica esta etiqueta. Seleccione **Privado** cuando quiera que solo los miembros aprobados en la organización tengan acceso al sitio de grupo del grupo. 
    
    La configuración seleccionada reemplaza a la configuración de privacidad anterior que puede estar configurada para el grupo y bloquea el valor de privacidad, para que solo se pueda modificar quitando primero la etiqueta de confidencialidad del sitio o grupo de equipo. Después de quitar la etiqueta de confidencialidad, la configuración de privacidad de la etiqueta permanece y ahora puede cambiarla si es necesario.

- **Acceso de usuarios externos**: controla si el propietario del grupo puede [agregar invitados al grupo](/office365/admin/create-groups/manage-guest-access-in-groups).

- **Dispositivos no administrados**: para [dispositivos sin administrar](/sharepoint/control-access-from-unmanaged-devices), permite acceso total, acceso de solo Web, o bloquear el acceso completamente. 

![La pestaña de configuración de sitio y grupo](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> La configuración de sitio y grupo solo surte efecto al aplicar una etiqueta a un equipo, grupo o sitio. El resto de opciones de configuración de etiqueta, como el cifrado y la marcación de contenido, no se aplican a todo el contenido del equipo, grupo o sitio.
> 
> De forma similar, si crea una etiqueta y no activa la configuración de sitio y de grupo, la etiqueta seguirá estando disponible cuando los usuarios creen equipos, grupos y sitios, pero solo se aplicará el nombre de la etiqueta.

Si la etiqueta aún no se ha publicado, publíquela [agregándola a una directiva de etiqueta](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).

## <a name="sensitivity-label-management"></a>Administración de etiquetas de confidencialidad

> [!WARNING]
> Para crear, modificar y eliminar las etiquetas de confidencialidad que usa para Microsoft Teams, grupos de Office 365 y sitios de SharePoint se requiere una cuidadosa coordinación con las directivas de etiquetas de publicación para los usuarios. 

Evite errores de creación de sitios y grupos que puedan afectar a todos los usuarios con las instrucciones siguientes.

**Guardar y publicar etiquetas:**

Una vez se crea y se publica una etiqueta de confidencialidad, puede tardar hasta 24 horas en ser visible para los usuarios en los equipos, grupos y sitios. Siga los pasos siguientes para publicar una etiqueta para todos los usuarios en el espacio empresarial:

1. Cree la etiqueta de confidencialidad y publíquela solo para algunas cuentas de usuario del espacio empresarial.

2. Espere 24 horas.

3. Cuando transcurran 24 horas, utilice una de las cuentas de usuario que especificó en el paso 1 para crear un equipo, un grupo de Office 365 o un sitio de SharePoint con la etiqueta creada en el paso 1.

4. Si no se han producido errores durante la operación de creación del paso 3, publique la etiqueta para todos los usuarios de su espacio empresarial. Si hay errores, póngase en contacto con el [Soporte técnico de Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

**Modificar y eliminar etiquetas publicadas:**

Si modifica o elimina una etiqueta de confidencialidad incluida en una o varias directivas de etiquetas, estas acciones pueden ocasionar errores en la creación de todos los equipos, grupos y sitios. Para evitarlo, siga las instrucciones que se indican a continuación:

1. Elimine la etiqueta de confidencialidad de todas las directivas de etiqueta que la incluyan.

2. Espere 48 horas.

3. Transcurrida la espera de 48 horas, pruebe a crear un equipo, grupo o sitio y compruebe que la etiqueta ya no es visible.

4. Si la etiqueta de confidencialidad no es visible, ya la puede modificar o eliminar de forma segura. Si la etiqueta sigue visible, póngase en contacto con el [Soporte técnico de Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

## <a name="assign-sensitivity-labels-to-office-365-groups"></a>Asignar etiquetas de confidencialidad a grupos de Office 365

Ya está listo para aplicar la etiqueta o las etiquetas de confidencialidad a los grupos de Office 365. Regrese a la documentación de Azure AD para obtener instrucciones:

- [Asignar una etiqueta a un grupo nuevo en Azure Portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [Asignar una etiqueta a un grupo existente en Azure Portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  [Quitar una etiqueta a un grupo existente en Azure Portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal)

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>Aplicar una etiqueta de confidencialidad a un nuevo equipo

Los usuarios pueden seleccionar etiquetas de confidencialidad al crear nuevos equipos en Microsoft Teams. Cuando seleccionan el nivel de confidencialidad, la configuración de privacidad cambia según las necesidades. En función de la configuración de acceso de usuarios externos que haya seleccionado para la etiqueta, los usuarios pueden o no, agregar al equipo personas de fuera de la organización.

[Más información sobre las etiquetas de confidencialidad para Teams](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![La configuración de privacidad al crear un nuevo equipo](../media/privacy-setting-new-team.png)

Después de crear el equipo, se muestra la etiqueta de confidencialidad en la esquina superior derecha de todos los canales.

![La etiqueta de confidencialidad se muestra en el equipo](../media/privacy-setting-teams.png)

El servicio aplica automáticamente la misma etiqueta de confidencialidad al grupo de Office 365 y al sitio de grupo de SharePoint conectado.

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a>Aplicar una etiqueta de confidencialidad a un nuevo grupo en Outlook en la Web

En Outlook en la Web, al crear un grupo, puede seleccionar o cambiar la opción **confidencialidad** para las etiquetas publicadas:

![Crear un grupo y seleccionar una opción en Confidencialidad](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>Aplicar una etiqueta de confidencialidad a un nuevo sitio

Los administradores y los usuarios finales pueden seleccionar etiquetas de confidencialidad cuando [crean sitios de grupo y de comunicación modernos](/sharepoint/create-site-collection).

Cuando los usuarios crean sitios modernos de equipo y comunicación, ya hay una etiqueta de confidencialidad seleccionada de forma predeterminada. Los usuarios pueden seleccionar el icono de ayuda para obtener más información sobre las etiquetas.

![Crear un sitio y seleccionar una opción en Confidencialidad](../media/sensitivity-label-new-communication-site.png)

Cuando los usuarios exploren el sitio, podrán ver el nombre de la etiqueta y las directivas aplicadas.

![Un sitio en el que se ha aplicado una etiqueta de confidencialidad](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a>Ver etiquetas de confidencialidad en el Centro de administración de SharePoint

Para ver las etiquetas de confidencialidad aplicadas, use la página **Sitios activos** en el nuevo Centro de administración de SharePoint. Es posible que primero tenga que agregar la columna **confidencialidad**:

![La columna Confidencialidad en la página Sitios activos](../media/manage-site-sensitivity-labels.png)

[Obtenga más información para administrar sitios en el nuevo centro de administración de SharePoint](/sharepoint/manage-sites-in-new-admin-center).

## <a name="change-site-and-group-settings-for-a-label"></a>Cambiar la configuración de sitio y grupo para una etiqueta

Siempre que haga un cambio en la configuración de sitio y de grupo de una etiqueta, debe ejecutar los comandos de PowerShell que se indican a continuación para que los equipos, sitios y grupos puedan usar la nueva configuración. Se recomienda no cambiar la configuración del sitio y el grupo de una etiqueta después de haber aplicado la etiqueta a varios equipos, grupos o sitios.

1. Ejecute los siguientes comandos para conectarse al PowerShell del Centro de seguridad y cumplimiento de Office 365 y obtener la lista de etiquetas de confidencialidad y sus GUID.
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. Tome nota del GUID para la(s) etiqueta(s) que ha cambiado.

3. Ahora, conéctese al PowerShell de Exchange Online y ejecute el cmdlet Get-UnifiedGroup, especificando el GUID de la etiqueta en vez del GUID de ejemplo de "e48058ea-98e8-4940-8db0-ba1310fd955e": 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. Para cada grupo, vuelva a aplicar la etiqueta de confidencialidad, especificando el GUID de la etiqueta en vez del GUID de ejemplo de "e48058ea-98e8-4940-8db0-ba1310fd955e":
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a>Soporte técnico para las etiquetas de confidencialidad

Puede usar las etiquetas de confidencialidad que ha configurado para la configuración del sitio y el grupo con las siguientes aplicaciones y servicios:

- SharePoint Online
- Teams
- Outlook en la Web
- Centro de administración de SharePoint
- Centro de administración de Azure AD

Otras aplicaciones y servicios que actualmente no puede usar las etiquetas de confidencialidad que ha configurado para la configuración del sitio y el grupo incluyen:

- Outlook para Mac
- Outlook para dispositivos móviles
- Outlook de escritorio para Windows
- Formularios
- Dynamics 365
- Yammer
- Stream
- Planner
- Proyecto
- PowerBI
- Centro de administración de Teams
- Centro de administración de Microsoft 365
- Centro de administración de Exchange


## <a name="classic-azure-ad-site-classification"></a>Clasificación clásica de sitio de Azure AD

Office 365 ya no admite las clasificaciones antiguas para nuevos grupos y sitios de SharePoint una vez habilitada esta versión preliminar. Sin embargo, los grupos y sitios existentes aún muestran las clasificaciones antiguas a menos que las convierta para usar etiquetas de confidencialidad. Entre las clasificaciones antiguas se incluyen la clasificación de sitios "modernos" que usted haya configurado, probablemente a través de PowerShell de Azure AD o la biblioteca principal PnP, donde se definían valores para la configuración de `ClassificationList`.

Por ejemplo, en PowerShell:

```powershell
   ($setting["ClassificationList"])
```

Para obtener más información sobre el método antiguo de clasificación, consulte [Clasificación de sitios "modernos" de SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).

Para convertir las clasificaciones antiguas en etiquetas de confidencialidad, siga uno de estos procedimientos:

- Usar etiquetas existentes: especifique la configuración de la etiqueta que desee para los sitios y grupos al editar las etiquetas de confidencialidad existentes que ya están publicadas.

- Crear etiquetas nuevas: especifique la configuración de la etiqueta que desee para los sitios y grupos creando y publicando nuevas etiquetas de confidencialidad que tengan los mismos nombres que las de las clasificaciones existentes.

Entonces: 

1. Use PowerShell para aplicar las etiquetas de confidencialidad a los grupos de Office 365 y a los sitios de SharePoint mediante la asignación de nombres. Vea la siguiente sección para obtener instrucciones.

2. Quitar las clasificaciones antiguas de los grupos y sitios existentes.

Aunque no se puede impedir que los usuarios creen grupos nuevos en aplicaciones y servicios que aún no admiten las etiquetas de confidencialidad, puede ejecutar un script de PowerShell periódico para buscar grupos nuevos que los usuarios han creado con las clasificaciones anteriores y convertirlos para usar etiquetas de confidencialidad. 

#### <a name="use-powershell-to-convert-classifications-for-office-365-groups-to-sensitivity-labels"></a>Usar PowerShell para convertir clasificaciones de grupos de Office 365 a etiquetas de confidencialidad

1. Asegúrese de que utiliza la versión 16.0.19418.12000 (o posterior) de Shell de SharePoint Online Management. Si ya tiene la versión más reciente, vaya al paso 4.

2. Si tiene instalada una versión anterior de Shell de SharePoint Online Management de la galería de PowerShell, puede actualizar el módulo ejecutando el siguiente cmdlet.
    
    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

3. Si tiene instalada una versión anterior de Shell de SharePoint Online Management del Centro de descarga de Microsoft, vaya a **agregar o quitar programas** y desinstale el Shell de SharePoint Online Management. Después, instale el último Shell de SharePoint Online Management desde el [Centro de descarga](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Utilice una cuenta profesional o educativa con privilegios de administrador global o de administrador de SharePoint en Office 365 para conectarse al Shell de administración de SharePoint Online. Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

5. Ejecute los comandos siguientes para obtener la lista de etiquetas de confidencialidad y sus GUID.

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

6. Tome nota de los GUID para las etiquetas de confidencialidad que quiere aplicar a los grupos de Office 365.

7. Use el comando siguiente como ejemplo para obtener la lista de grupos que actualmente tienen la clasificación de "general":

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. Para cada grupo, agregue el nuevo GUID de etiqueta de confidencialidad. Por ejemplo:

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

## <a name="auditing-sensitivity-label-activities"></a>Auditar actividades de etiqueta de confidencialidad

Si alguien carga un documento en un sitio protegido con una etiqueta de confidencialidad y el documento tiene una etiqueta de confidencialidad de [mayor prioridad](sensitivity-labels.md#label-priority-order-matters) que la etiqueta de confidencialidad que se aplica al sitio, esta acción no está bloqueada. Por ejemplo, aplicó la etiqueta **general** a un sitio de SharePoint y alguien carga en este sitio un documento etiquetado como **confidencial**. Debido a que una etiqueta de confidencialidad con mayor prioridad identifica el contenido que es más confidencial que el contenido que tiene un orden de menor prioridad, esta situación podría ser un problema de seguridad.

Aunque la acción no está bloqueada, se audita, por lo que puede identificar los documentos que no están alineados con la prioridad de las etiquetas y tomar las medidas necesarias. Por ejemplo, eliminar o mover el documento cargado del sitio. 

No sería un problema de seguridad si el documento tiene una etiqueta de confidencialidad de menor prioridad que la etiqueta de confidencialidad aplicada al sitio. Por ejemplo, un documento con la etiqueta **general** se carga en un sitio con la etiqueta **confidencial**. En este escenario, no se genera un evento de auditoría.

Para buscar el registro de auditoría para este evento, busque **Desfase detectado de la confidencialidad del documento** en la categoría de las **actividades de archivos y páginas**. 

Cuando alguien agrega o quita una etiqueta de confidencialidad a un sitio o grupo, estas actividades también se auditan. Estos eventos se pueden encontrar en la categoría de [actividades de etiqueta de confidencialidad](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities). 

Para obtener instrucciones sobre cómo buscar el registro de auditoría, vea [buscar el registro de auditoría en el Centro de seguridad y cumplimiento](search-the-audit-log-in-security-and-compliance.md).

## <a name="troubleshoot-sensitivity-label-deployment"></a>Resolución de problemas de implementación de etiquetas de confidencialidad

¿Tiene problemas con las etiquetas de confidencialidad de Microsoft Teams, Grupos de Office 365 y sitios de SharePoint? Compruebe lo siguiente:

### <a name="labels-not-visible-after-publishing"></a>Las etiquetas no son visibles tras su publicación
Si tiene problemas al crear un equipo o grupo de Office 365 después de habilitar estas opciones de configuración o modificar la descripción de una etiqueta de confidencialidad, espere unas horas después de guardar los cambios en la etiqueta y, después, intente crear de nuevo el equipo o grupo. Para obtener más información, consulte [Programar la implementación tras crear o cambiar una etiqueta de confidencialidad](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).

Si sigue sin poder ver la nueva etiqueta de confidencialidad desde SharePoint Online, póngase en contacto con el [Soporte técnico de Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

### <a name="team-group-or-sharepoint-site-creation-errors"></a>Errores de creación de equipo, grupo o sitio de SharePoint
Si experimenta errores de creación durante la versión preliminar pública, tiene dos opciones:

- Asegúrese de que las etiquetas de confidencialidad no son obligatorias para algún usuario.

- Puede desactivar las etiquetas de confidencialidad de Microsoft Teams, los grupos de Office 365 y los sitios de SharePoint siguiendo las mismas instrucciones que se indican en [Habilitar la compatibilidad con las etiquetas de confidencialidad en PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell). Sin embargo, para deshabilitar la versión preliminar, en el paso 5, deshabilite la característica con `$setting["EnableMIPLabels"] = "False"`.

