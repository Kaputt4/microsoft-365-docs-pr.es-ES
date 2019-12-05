---
title: Usar etiquetas de confidencialidad con Microsoft Teams, grupos de Office 365 y sitios de SharePoint (versión preliminar pública)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/03/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Puede aplicar etiquetas a Microsoft Teams, a los grupos de Office 365 y a los sitios de SharePoint.
ms.openlocfilehash: ebe5e00c3458782e1874274cb508326968461ce3
ms.sourcegitcommit: 1bd81cf48c7fab1b8aaf7c3f550ce42ab02136dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "39822496"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a>Usar etiquetas de confidencialidad con Microsoft Teams, grupos de Office 365 y sitios de SharePoint (versión preliminar pública)

Al crear etiquetas de confidencialidad en el [centro de cumplimiento de microsoft 365](https://protection.office.com/), ahora puede aplicarlas a Microsoft Teams, a los grupos de Office 365 y a los sitios de SharePoint. Puede asociar directivas con las etiquetas para controlar:

- Configuración pública o privada
- Acceso de invitado
- Acceso desde dispositivos no administrados

Cuando se aplica una etiqueta a un equipo o grupo, la etiqueta se aplica automáticamente al sitio de grupo de SharePoint conectado y al contrario.

Ahora, también puede habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive. [Obtenga más información](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a>Información sobre la versión preliminar pública para Microsoft Teams, Office 365 grupos y sitios de SharePoint

Las etiquetas de confidencialidad para Microsoft Teams, Office 365 grupos y sitios de SharePoint se implementan gradualmente para los inquilinos y podrían cambiar antes de la versión final.

La versión preliminar pública no funciona con las redes de entrega de contenido (CDN) de Office 365.

## <a name="overview"></a>Información general

Al publicar etiquetas de confidencialidad, los usuarios de Office 365 tienen acceso a la misma lista de etiquetas.

Estas imágenes muestran:

- Cómo aparece la lista cuando se crea un nuevo sitio de grupo desde SharePoint

- Cuando ve la lista en Word

![Una etiqueta de confidencialidad al crear un sitio de grupo desde SharePoint](media/sensitivity-label-new-team-site.png)

![Etiqueta de confidencialidad mostrada en la aplicación de escritorio de Word](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a>Habilitación de esta vista previa mediante Azure PowerShell

1. Inicie sesión en Azure como administrador global mediante Azure PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Ejecute el siguiente comando:

```powershell
  Connect-AzureAD
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

Office 365 ya no usa las clasificaciones antiguas para nuevos grupos y sitios de SharePoint cuando habilita esta vista previa. Si usó la [clasificación de sitios de Azure ad](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($Setting ["ClassificationList"]), los grupos y sitios existentes seguirán mostrando las clasificaciones antiguas. Para mostrar las clasificaciones nuevas, conviértalos. Para obtener información sobre cómo convertirlos, vea [si usó la clasificación clásica de sitios de Azure ad](#if-you-used-classic-azure-ad-site-classification). 

## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a>Establecer la configuración de sitios y grupos al crear o editar etiquetas de confidencialidad

Después de habilitar la vista previa, siga estos pasos para crear o editar las etiquetas de confidencialidad. Debe completar estos pasos para que las nuevas etiquetas de confidencialidad funcionen con sitios y grupos, incluso si ya tiene etiquetas definidas. Los cambios en esta configuración pueden tardar hasta 24 horas en sincronizarse.

1. En el centro de cumplimiento de Microsoft 365, seleccione**etiquetas de sensibilidad**de **clasificación** > .

2. Seleccione **crear una etiqueta**. Si ya tiene una etiqueta, vaya al paso siguiente.

3. Seleccione las opciones que desee y, a continuación, en la pestaña **configuración de sitio y grupo** , elija:

    - Privacidad (pública o privada): privada significa que solo los miembros aprobados en la organización pueden ver el contenido del grupo. Cualquier otra persona de la organización no puede ver el contenido del grupo. [Más información](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - Acceso de invitado: puede controlar si los invitados se pueden agregar a un grupo. [Información acerca de la administración del acceso de invitado en Office 365 grupos](/office365/admin/create-groups/manage-guest-access-in-groups)
    - Dispositivos no administrados: esta opción permite bloquear o limitar el acceso al contenido de SharePoint desde dispositivos que no son compatibles con AD híbrido o que no son compatibles con Intune. Si selecciona dispositivos no administrados, tendrá que ir a Azure AD para finalizar la configuración de la Directiva. Para obtener información, vea [controlar el acceso desde dispositivos no administrados](/sharepoint/control-access-from-unmanaged-devices).

![Ficha Configuración de sitio y grupo](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> Solo la configuración de sitio y grupo surte efecto cuando se aplica una etiqueta a un equipo, grupo o sitio. Otras opciones, como el cifrado y la marcación de contenido, no se aplican a todo el contenido dentro del equipo, grupo o sitio. De forma similar, si crea una etiqueta y no activa la configuración de sitio y grupo, la etiqueta seguirá estando disponible cuando los usuarios creen equipos, grupos y sitios, pero no hará nada cuando los usuarios lo apliquen.

[Obtener información sobre cómo publicar una etiqueta de confidencialidad](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="troubleshoot-sensitivity-label-deployment"></a>Solucionar problemas de implementación de etiqueta de confidencialidad

Si experimenta problemas al crear un grupo de Teams o 365 de Office después de habilitar esta configuración o realizar un cambio en la descripción de la etiqueta de confidencialidad, guarde la etiqueta, espere unas cuantas horas y, a continuación, vuelva a intentar crear el grupo de Office 365 o equipo.

Si sigue sin poder ver la nueva etiqueta de confidencialidad de SharePoint Online, póngase en contacto con el soporte técnico de Microsoft inmediatamente.

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>Aplicar una etiqueta de confidencialidad a un nuevo equipo

Los usuarios pueden seleccionar las etiquetas de confidencialidad cuando crean nuevos equipos en Microsoft Teams. Cuando seleccionan el nivel de confidencialidad, la configuración de privacidad cambia cuando sea necesario. En función de la configuración de acceso de invitado que haya seleccionado para la etiqueta, los usuarios podrán o no agregar personas fuera de la organización al equipo.

![La configuración de privacidad cuando se crea un nuevo equipo](media/privacy-setting-new-team.png)

Después de crear el equipo, la etiqueta de confidencialidad aparece en la esquina superior derecha de todos los canales.

![La etiqueta de confidencialidad aparece en el equipo](media/privacy-setting-teams.png)

El servicio aplica automáticamente la misma etiqueta de confidencialidad al grupo de Office 365 y al sitio de grupo de SharePoint conectado.

## <a name="apply-a-sensitivity-label-to-a-new-group"></a>Aplicar una etiqueta de confidencialidad a un nuevo grupo

En Outlook en la web, el nuevo cuadro de **confidencialidad** contiene las etiquetas publicadas. Si los usuarios desean más información, pueden hacer clic en el icono ayuda para leer los detalles sobre las etiquetas disponibles y las directivas asociadas.

![Creación de un grupo y selección de una opción en confidencialidad](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>Aplicar una etiqueta de confidencialidad a un sitio nuevo

Los administradores y los usuarios finales pueden seleccionar las etiquetas de confidencialidad cuando crean sitios de grupo y de comunicación modernos.

[Obtenga información sobre cómo crear un sitio en el nuevo centro de administración de SharePoint](/sharepoint/create-site-collection)

Cuando los usuarios crean sitios de comunicación y de equipo modernos, la etiqueta de confidencialidad ya está seleccionada de forma predeterminada. Los usuarios pueden seleccionar el icono de ayuda para obtener más información sobre las etiquetas.

![Creación de un sitio y selección de una opción en confidencialidad](media/sensitivity-label-new-communication-site.png)

Cuando los usuarios visitan el sitio, pueden ver el nombre de la etiqueta y las directivas aplicadas.

![Un sitio con una etiqueta de confidencialidad aplicada](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>Administrar las etiquetas de confidencialidad en el centro de administración de SharePoint

Para ver y editar las etiquetas, use la página sitios activos en el nuevo centro de administración de SharePoint.

![Columna confidencial de la página sitios activos](media/manage-site-sensitivity-labels.png)

[Obtenga más información sobre cómo administrar sitios en el nuevo centro de administración de SharePoint](/sharepoint/manage-sites-in-new-admin-center).

## <a name="change-site-and-group-settings-for-a-label"></a>Cambiar la configuración de sitio y grupo de una etiqueta

Como práctica recomendada, no cambie la configuración después de aplicar una etiqueta a varios equipos, grupos o sitios. Si debe realizar algún cambio, deberá usar un script de PowerShell de Azure AD para aplicar manualmente las actualizaciones. Este método garantiza que todos los equipos, sitios y grupos existentes apliquen la nueva configuración.

## <a name="support-for-the-new-sensitivity-labels"></a>Compatibilidad con las nuevas etiquetas de confidencialidad

Las siguientes aplicaciones y servicios admiten las etiquetas de confidencialidad en esta vista previa:

- Centro de cumplimiento de Microsoft 365
- SharePoint
- Outlook en la Web
- Teams
- Centro de administración de SharePoint
- Centro de administración de Azure AD

No puede usar las siguientes aplicaciones y servicios para crear grupos de Office 365 con las nuevas etiquetas de confidencialidad:

- Outlook para Mac
- Outlook Mobile  
- Escritorio de Outlook para Windows
- Formularios  
- Dynamics 365  
- Yammer  
- Stream  
- Planner  
- Project  
- PowerBI  
- Centro de administración de Teams  
- Centro de administración de 365 de Microsoft  
- Centro de administración de Exchange

## <a name="if-you-used-classic-azure-ad-site-classification"></a>Si usó la clasificación clásica del sitio de Azure AD

Office 365 ya no es compatible con las clasificaciones antiguas para nuevos grupos y sitios de SharePoint cuando habilita esta vista previa. Sin embargo, los grupos y sitios existentes todavía muestran las clasificaciones antiguas a menos que las convierta. Las clasificaciones antiguas incluyen la clasificación de los sitios "modernos" que configuró, posiblemente a través de Azure AD PowerShell o la biblioteca principal de PnP `ClassificationList` , que definía los valores de la configuración.

Por ejemplo, en PowerShell:

```powershell
   ($setting["ClassificationList"])
```

Para obtener más información sobre el método de clasificación anterior, consulte [clasificación de sitios "modernos" de SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).

En función de la implementación actual, tiene dos opciones para convertir las clasificaciones antiguas en las nuevas clasificaciones.

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>Si nunca ha usado etiquetas de confidencialidad (etiquetas unificadas de protección de la información de Microsoft) para los archivos y el correo electrónico

Le recomendamos que haga lo siguiente:

1. Cree nuevas etiquetas de confidencialidad en el centro de cumplimiento de Microsoft 365 que tengan los mismos nombres que las clasificaciones existentes.
2. Use PowerShell para aplicar las nuevas etiquetas a los grupos de Office 365 y los sitios de SharePoint existentes mediante la asignación de nombres.
3. Elimine las clasificaciones antiguas.

Las aplicaciones y los servicios que admitan las nuevas etiquetas de confidencialidad las mostrarán. Cree nuevos equipos, grupos y sitios con las nuevas etiquetas. Los usuarios pueden seguir creando grupos a partir de aplicaciones y servicios que no admiten las nuevas etiquetas. Sin embargo, los usuarios no pueden aplicar una etiqueta a estos grupos. Use PowerShell para aplicar las nuevas etiquetas de confidencialidad a estos grupos.

Puede mantener sus clasificaciones antiguas; sin embargo, se recomienda encarecidamente usar PowerShell para aplicar las nuevas etiquetas de confidencialidad a estos grupos.

Las aplicaciones y los servicios que admiten las nuevas etiquetas de confidencialidad se crearán con las nuevas etiquetas. Cuando los usuarios crean grupos a partir de aplicaciones y servicios que no admiten las nuevas etiquetas, pueden seleccionar una clasificación.

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>Si usa etiquetas de confidencialidad (etiquetas unificadas de protección de la información de Microsoft) para los archivos y el correo electrónico

En cuanto habilite esta vista previa, vaya a cada etiqueta del centro de cumplimiento de Microsoft 365 y aplique las directivas que desee para los sitios y grupos. Los usuarios empezarán a ver las etiquetas existentes disponibles para los sitios y grupos.

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a>Preparar el shell de administración de SharePoint Online antes de reetiquetar los grupos de Office 365

Antes de aplicar nuevas etiquetas, asegúrese de que está ejecutando el shell de administración de SharePoint Online más reciente. Si ya tiene la última versión, puede volver a [etiquetar los grupos de Office 365 con nuevas etiquetas de confidencialidad](#relabel-office-365-groups-with-new-sensitivity-labels).

Para preparar el shell de administración de SharePoint Online para la vista previa:

1. Si instaló una versión anterior del shell de administración de SharePoint Online, vaya a **Agregar o quitar programas** y desinstale "Shell de administración de SharePoint Online".

2. En un explorador Web, vaya a la página del centro de descarga y [Descargue el shell de administración de SharePoint Online más reciente](https://go.microsoft.com/fwlink/p/?LinkId=255251).

3. Seleccione su idioma y, a continuación, haga clic en **Descargar**.

4. Elija entre el archivo x64 y x86. msi. Descargue el archivo x64 si ejecuta la versión de 64 bits de Windows o el archivo x86 si está ejecutando la versión de 32 bits. Si no lo sabe, consulte ¿ [qué versión del sistema operativo Windows estoy ejecutando?](https://support.microsoft.com/help/13443/windows-which-operating-system).

5. Una vez descargado el archivo, ejecute el archivo y siga los pasos del Asistente para la instalación.

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a>Reetiquetar grupos de Office 365 con nuevas etiquetas de confidencialidad

1. Asegúrese de que está usando la versión más reciente del shell de administración de SharePoint Online. Para obtener instrucciones, vea [preparar el shell de administración de SharePoint Online antes de reetiquetar grupos de Office 365](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).

2. Con una cuenta profesional o educativa que tenga privilegios de administrador global o de administrador de SharePoint en Office 365, conéctese a la consola de administración de SharePoint Online. Para saber cómo hacerlo, vea [Introducción al Shell de administración de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

3. Ejecute el siguiente comando para obtener una lista de las etiquetas de confidencialidad y sus GUID.

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. Anote el GUID de la etiqueta que desea sobrescribir. Por ejemplo, la etiqueta "general".

5. Use el siguiente comando para obtener la lista de grupos que tienen la clasificación "general". Al ejecutar este comando, se conectará a Exchange Online PowerShell y ejecutará el cmdlet Get-UnifiedGroup.

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. Para cada grupo, agregue el nuevo GUID de la etiqueta de confidencialidad.

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
