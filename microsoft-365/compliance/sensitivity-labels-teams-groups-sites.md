---
title: Usar etiquetas de confidencialidad con Microsoft Teams, grupos de Office 365 y sitios de SharePoint (versión preliminar pública)
ms.author: krowley
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
ms.openlocfilehash: 0b5c4e8ef3611b417c59f7ac5b36f83a799e3397
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238447"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a>Usar etiquetas de confidencialidad con Microsoft Teams, grupos de Office 365 y sitios de SharePoint (versión preliminar pública)

Cuando cree etiquetas de confidencialidad en el [centro de cumplimiento de Microsoft 365](https://protection.office.com/), ahora podrá aplicarlas a Microsoft Teams, a los grupos de Office 365 y a los sitios de SharePoint. Se pueden asociar directivas a las etiquetas para controlar:

- Configuración pública/privada
- Acceso de invitados
- Acceso desde dispositivos no administrados

Al aplicar una etiqueta a un equipo o grupo, esta se aplica automáticamente al correspondiente sitio del equipo de SharePoint y viceversa.

Ahora también puede habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive. Para más información, vea[ Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive (vista previa)](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a>Acerca de la versión preliminar pública para Microsoft Teams, grupos de Office 365 y sitios de SharePoint

Las etiquetas de confidencialidad de Microsoft Teams, grupos de Office 365 y sitios de SharePoint se están introduciendo gradualmente para los inquilinos y es posible que haya cambios antes de la versión final.

Esta versión preliminar pública no funciona con las redes de entrega de contenido (CDN) de Office 365.

## <a name="overview"></a>Información general

Cuando publica etiquetas de confidencialidad, los usuarios de Office 365 tienen acceso a la misma lista de etiquetas.

Se muestran estas imágenes:

- Cómo se muestra la lista cuando se crea un nuevo sitio de grupo desde SharePoint

- Cuando se ve la lista en Word

Por ejemplo:

![Una etiqueta de confidencialidad al crear un sitio de grupo desde SharePoint](media/sensitivity-label-new-team-site.png)

![Una etiqueta de confidencialidad mostrada en la aplicación de escritorio de Word](media/sensitivity-label-word.png)

## <a name="enable-this-preview"></a>Habilitar esta versión preliminar

Debe usar la versión preliminar de [Azure Active Directory PowerShell para Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) (nombre de módulo **AzureADPreview**) para habilitar esta vista previa de las etiquetas de confidencialidad en Microsoft Teams, grupos de Office 365 y sitios de SharePoint:

- Si todavía no ha instalado ninguna de las versiones de los módulos de PowerShell de Azure AD, consulte [Instalar el módulo de Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) y siga las instrucciones para instalar la versión preliminar pública.

- Si tiene instalada la versión 2.0 de disponibilidad general para el módulo de PowerShell de Azure AD (AzureAD), deberá desinstalarla ejecutando `Uninstall-Module AzureAD` en su sesión de PowerShell y, a continuación, instalar la versión preliminar ejecutando `Install-Module AzureADPreview`.

- Si ya ha instalado la versión preliminar, ejecute `Install-Module AzureADPreview` para asegurarse de que es la última versión de este módulo.

Ahora está listo para habilitar la versión preliminar de las etiquetas de confidencialidad con Microsoft Teams, grupos de Office 365 y sitios de SharePoint:

1. En una sesión de PowerShell, utilice una cuenta profesional o educativa con privilegios de administrador global para conectarse a Azure Active Directory. Por ejemplo, ejecute:
    
    ```powershell
    Connect-AzureAD
    ````
    
    Para obtener instrucciones detalladas, consulte [conectarse a Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad).

2. Ejecute los comandos siguientes:
    
    ```powershell
    $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
    if ($setting -eq $null)
    {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
    }
    else
    {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
    }
    ```
    
    > [!NOTE]
    > Office 365 ya no usa las clasificaciones antiguas para nuevos grupos y sitios de SharePoint cuando se habilita esta versión preliminar. Si ha utilizado la [clasificación de sitio de Azure AD](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), los grupos y sitios existentes siguen mostrando las clasificaciones antiguas. Conviértalos para que muestren las nuevas clasificaciones. Para obtener información sobre cómo convertirlos, consulte [Si utilizaba la clasificación clásica del sitio de Azure AD](#if-you-used-classic-azure-ad-site-classification). 

3. En la misma sesión de PowerShell, conéctese ahora al Centro de seguridad y cumplimiento con una cuenta profesional o educativa con privilegios de administrador global. Para obtener instrucciones, consulte [Conectarse a PowerShell del Centro de seguridad y cumplimiento de Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

4. Ejecute los siguientes comandos para sincronizar las etiquetas en Azure AD, de modo que se puedan usar con los grupos de Office 365:
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```
## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a>Establezca los ajustes del sitio y los grupos al crear o editar etiquetas de confidencialidad

Una vez habilitada la versión preliminar, siga los mismos pasos para crear o editar etiquetas de confidencialidad. Debe seguir estos pasos para que se puedan usar las etiquetas de confidencialidad con sitios y grupos, incluso si ya tiene etiquetas definidas. Los cambios en estos ajustes pueden tardar hasta 24 horas en sincronizarse.

1. En el centro de cumplimiento de Microsoft 365, seleccione **Clasificación** > **Etiquetas de confidencialidad**.

2. Seleccione**Crear una etiqueta**. Si ya tiene una etiqueta, omita este paso.

3. Seleccione las opciones que desee y, a continuación, seleccione en la pestaña **Configuración de sitio y grupo**:
    
    - Privacidad (Público/Privado): Privado significa que solo los miembros autorizados de la organización pueden ver el contenido del grupo. Ninguna otra persona de la organización puede ver lo que hay en el grupo. [Obtener más información](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - Acceso de invitado: Usted puede controlar si se pueden añadir invitados a un grupo. [Más información sobre cómo administrar el acceso de invitados en grupos de Office 365](/office365/admin/create-groups/manage-guest-access-in-groups)
    - Dispositivos no administrados: Esta opción le permite bloquear o limitar el acceso a contenido de SharePoint desde dispositivos que no sean unidos a Azure AD híbridos o compatibles con Intune. Si selecciona Dispositivos no administrados, debe ir a Azure AD para finalizar la configuración de la directiva. Para más información, vea [Control de acceso desde dispositivos no administrados](/sharepoint/control-access-from-unmanaged-devices).
    
    ![La pestaña de configuración de sitio y grupo](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> La configuración de sitio y grupo solo surte efecto al aplicar una etiqueta a un equipo, grupo o sitio. El resto de opciones de configuración, como el cifrado y la marcación de contenido, no se aplican a todo el contenido del equipo, grupo o sitio.
> 
> De forma similar, si crea una etiqueta y no activa la configuración de sitio y de grupo, la etiqueta seguirá estando disponible cuando los usuarios creen equipos, grupos y sitios, pero estos se clasificarán sin aplicar ninguna configuración.

[Más información sobre la publicación de etiquetas de confidencialidad](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

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

## <a name="troubleshoot-sensitivity-label-deployment"></a>Resolución de problemas de implementación de etiquetas de confidencialidad

### <a name="labels-not-visible-after-publishing"></a>Las etiquetas no son visibles tras su publicación
Si tiene problemas al crear un equipo o un grupo de Office 365 después de habilitar esta configuración o de modificar la descripción de una etiqueta de confidencialidad, guarde la etiqueta, espere algunas horas y, a continuación, vuelva a intentar crear el equipo o grupo. Para obtener más información, consulte [Programar la implementación tras crear o cambiar una etiqueta de confidencialidad](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).

Si sigue sin poder ver la nueva etiqueta de confidencialidad desde SharePoint Online, póngase en contacto con el [Soporte técnico de Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

### <a name="team-group-or-sharepoint-site-creation-errors"></a>Errores de creación de equipo, grupo o sitio de SharePoint
Si experimenta errores de creación durante la versión preliminar pública, tiene dos opciones:

- Asegúrese de que las etiquetas de confidencialidad no son obligatorias para algún usuario.

- Puede desactivar las etiquetas de confidencialidad de Microsoft Teams, grupos Office 365 y sitios de SharePoint siguiendo las mismas instrucciones que se muestran en la sección [Habilitar esta versión preliminar](#enable-this-preview) en esta página. Sin embargo, para deshabilitar la versión preliminar, busque la línea `$setting["EnableMIPLabels"] = "True"` y cambie el valor **True** a **False**.

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>Aplicar una etiqueta de confidencialidad a un nuevo equipo

Los usuarios pueden seleccionar etiquetas de confidencialidad al crear nuevos equipos en Microsoft Teams. Cuando seleccionan el nivel de confidencialidad, la configuración de privacidad cambia según las necesidades. En función de la configuración de acceso de invitado que haya seleccionado para la etiqueta, los usuarios pueden agregar al equipo personas de fuera de la organización.

[Más información sobre las etiquetas de confidencialidad para Teams](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![La configuración de privacidad al crear un nuevo equipo](media/privacy-setting-new-team.png)

Después de crear el equipo, se muestra la etiqueta de confidencialidad en la esquina superior derecha de todos los canales.

![La etiqueta de confidencialidad se muestra en el equipo](media/privacy-setting-teams.png)

El servicio aplica automáticamente la misma etiqueta de confidencialidad al grupo de Office 365 y al sitio de grupo de SharePoint conectado.

## <a name="apply-a-sensitivity-label-to-a-new-group"></a>Aplicar una etiqueta de confidencialidad a un nuevo grupo

En Outlook en la Web, el nuevo cuadro de **Confidencialidad** contiene las etiquetas publicadas. Si los usuarios desean más información, pueden hacer clic en el icono de ayuda para ver detalles sobre las etiquetas disponibles y las directivas asociadas.

![Crear un grupo y seleccionar una opción en Confidencialidad](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>Aplicar una etiqueta de confidencialidad a un nuevo sitio

Los administradores y los usuarios finales pueden seleccionar etiquetas de confidencialidad al crear sitios modernos de grupo y de comunicación.

[Más información sobre crear un sitio en el nuevo centro de administración de SharePoint](/sharepoint/create-site-collection)

Cuando los usuarios crean sitios modernos de equipo y comunicación, ya hay una etiqueta de confidencialidad seleccionada de forma predeterminada. Los usuarios pueden seleccionar el icono de ayuda para obtener más información sobre las etiquetas.

![Crear un sitio y seleccionar una opción en Confidencialidad](media/sensitivity-label-new-communication-site.png)

Cuando los usuarios exploren el sitio, podrán ver el nombre de la etiqueta y las directivas aplicadas.

![Un sitio en el que se ha aplicado una etiqueta de confidencialidad](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>Administrar etiquetas de confidencialidad en el centro de administración de SharePoint

Para ver y editar las etiquetas, use la página Sitios activos en el nuevo centro de administración de SharePoint.

![La columna Confidencialidad en la página Sitios activos](media/manage-site-sensitivity-labels.png)

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

## <a name="support-for-the-new-sensitivity-labels"></a>Soporte técnico para las nuevas etiquetas de confidencialidad

Las siguientes aplicaciones y servicios son compatibles con las etiquetas de confidencialidad en esta versión preliminar:

- Centro de cumplimiento de Microsoft 365
- SharePoint
- Outlook en la Web
- Teams
- Centro de administración de SharePoint
- Centro de administración de Azure AD

No se pueden usar las siguientes aplicaciones y servicios para crear grupos de Office 365 con las nuevas etiquetas de confidencialidad:

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

## <a name="if-you-used-classic-azure-ad-site-classification"></a>Si usó la clasificación clásica de sitio de Azure AD

Office 365 ya no admite las clasificaciones antiguas para nuevos grupos y sitios de SharePoint una vez habilitada esta versión preliminar. Sin embargo, los grupos y sitios existentes siguen mostrando las clasificaciones antiguas, a menos que usted los convierta. Entre las clasificaciones antiguas se incluyen la clasificación de sitios "modernos" que usted haya configurado, probablemente a través de PowerShell de Azure AD o la biblioteca principal PnP, donde se definían valores para la configuración de `ClassificationList`.

Por ejemplo, en PowerShell:

```powershell
   ($setting["ClassificationList"])
```

Para obtener más información sobre el método antiguo de clasificación, consulte [Clasificación de sitios "modernos" de SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).

En función de la implementación actual, tiene dos opciones para convertir las clasificaciones antiguas en nuevas.

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>Si nunca ha usado etiquetas de confidencialidad (etiquetas unificadas de protección de información de Microsoft) para archivos y correo electrónico

Le recomendamos que haga lo siguiente:

1. Cree nuevas etiquetas de confidencialidad en el centro de cumplimiento de Microsoft 365 con los mismos nombres que las clasificaciones existentes.
2. Use PowerShell para aplicar las nuevas etiquetas a los grupos de Office 365 y los sitios de SharePoint ya existentes mediante el mapeo de nombres.
3. Elimine las clasificaciones antiguas.

Las aplicaciones y los servicios compatibles con las nuevas etiquetas de confidencialidad las mostrarán. Cree nuevos equipos, grupos y sitios con las nuevas etiquetas. Los usuarios todavía pueden crear grupos desde aplicaciones y servicios que no son compatibles con las nuevas etiquetas. Sin embargo, los usuarios no pueden aplicar una etiqueta a estos grupos. Use PowerShell para aplicar las nuevas etiquetas de confidencialidad a estos grupos.

Puede conservar las clasificaciones antiguas; sin embargo, se recomienda encarecidamente usar PowerShell para aplicar las nuevas etiquetas de confidencialidad a estos grupos.

Las aplicaciones y los servicios compatibles con las nuevas etiquetas de confidencialidad se crearán con las nuevas etiquetas. Cuando los usuarios crean grupos desde aplicaciones y servicios que no son compatibles con las nuevas etiquetas, pueden seleccionar una clasificación.

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>Si utiliza etiquetas de confidencialidad (etiquetas unificadas de protección de información de Microsoft) para archivos y correo electrónico

Tan pronto como habilite esta versión preliminar, vaya a cada etiqueta en el centro de cumplimiento de Microsoft 365 y aplique las directivas que desee para los sitios y grupos. Los usuarios comenzarán a ver las etiquetas ya existentes disponibles para sitios y grupos.

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a>Preparar el Shell de administración de SharePoint Online antes de reetiquetar grupos de Office 365

Antes de aplicar las nuevas etiquetas, asegúrese de que está ejecutando el Shell de administración de SharePoint Online más reciente. Si ya tiene instalada la versión más reciente, puede continuar y [Reetiquetar grupos de Office 365 con nuevas etiquetas de confidencialidad](#relabel-office-365-groups-with-new-sensitivity-labels).

Para preparar el Shell de administración de SharePoint Online para la versión preliminar:

1. Si instaló una versión anterior del Shell de administración de SharePoint Online, vaya a **Agregar o quitar programas** y desinstale "Shell de administración de SharePoint Online".

2. En un explorador web, vaya a la página del centro de descargas y [Descargue el Shell más reciente de administración de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).

3. Seleccione el idioma y, a continuación, haga clic en **Descargar**.

4. Elija entre el archivo .msi x64 y x86. Descargue el archivo x64 si está ejecutando la versión de 64 bits de Windows o el archivo x86 si está ejecutando la versión de 32 bits. Si no lo sabe, consulte [¿Qué versión del sistema operativo Windows estoy ejecutando?](https://support.microsoft.com/help/13443/windows-which-operating-system)

5. Después de descargar el archivo, ejecútelo y siga los pasos del asistente de configuración.

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a>Reetiquetar grupos de Office 365 con nuevas etiquetas de confidencialidad

1. Asegúrese de que utiliza la versión más reciente del Shell de administración de SharePoint Online. Para obtener instrucciones, consulte [Preparar el Shell de administración de SharePoint Online antes de reetiquetar grupos de Office 365](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).

2. Utilice una cuenta profesional o educativa con privilegios de administrador global o de administrador de SharePoint en Office 365 para conectarse al Shell de administración de SharePoint Online. Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

3. Ejecute el comando siguiente para obtener la lista de etiquetas de confidencialidad y sus GUID.

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. Tome nota del GUID de la etiqueta que desea sobrescribir. Por ejemplo, etiqueta "General".

5. Use el comando siguiente para obtener la lista de grupos que tienen la clasificación "General". Al ejecutar este comando, se conectará al PowerShell de Exchange Online y ejecutará el cmdlet Get-UnifiedGroup.

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. Para cada grupo, agregue el nuevo GUID de etiqueta de confidencialidad.

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
