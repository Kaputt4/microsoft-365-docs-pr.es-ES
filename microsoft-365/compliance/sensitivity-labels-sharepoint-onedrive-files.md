---
title: Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Los administradores pueden habilitar la compatibilidad con la etiqueta de confidencialidad para los archivos de Word, Excel y PowerPoint en SharePoint y OneDrive.
ms.openlocfilehash: fea28683136ae72603b3e7a6954d7d6ecf0ffbe4
ms.sourcegitcommit: 2eb4539291f5035b7bef746df89fbcc6faa17257
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2020
ms.locfileid: "41263342"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a>Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive (vista previa)

Antes de esta vista previa, al aplicar las etiquetas de confidencialidad que incluían cifrado a los archivos de Office almacenados en SharePoint y OneDrive, el servicio no podía procesar el contenido de estos archivos. La coautoría, la exhibición de documentos electrónicos, la prevención de pérdida de datos, la búsqueda, Delve y otras características de colaboración no funcionarán en estas circunstancias. Esta vista previa habilita estas características cuando se ha aplicado el cifrado con una clave basada en la nube:

- SharePoint reconoce las etiquetas de confidencialidad que se aplican a los archivos de Word, Excel y PowerPoint en SharePoint y OneDrive. SharePoint también aplica la configuración que corresponde a cada etiqueta.

- Cuando descarga un archivo desde SharePoint o desde OneDrive, la etiqueta de confidencialidad se desplaza con el archivo y la configuración sigue aplicándose.

- Aplicar etiquetas de confidencialidad a los archivos de Office y abrir y editar los archivos que tienen las etiquetas de confidencialidad aplicadas (si los permisos de la etiqueta lo permiten) mediante las versiones web de Word, Excel y PowerPoint. Con Word en la web, también puede usar la etiqueta automática al editar documentos.

- Office 365 eDiscovery admite la búsqueda de texto completo en los archivos a los que se han aplicado etiquetas de distinción. Las directivas de prevención de pérdida de datos (DLP) cubren el contenido de estos archivos.

- Hay tres nuevos eventos de auditoría disponibles para supervisar las etiquetas de confidencialidad:
  - FileSensitivityApplied
  - FileSensitivityLabelChanged
  - FileSensitivityLabelRemoved

> [!NOTE]
> Si no se ha aplicado el cifrado con una clave basada en la nube, pero con una clave local, una topología de administración de claves a menudo denominada "retener su propia clave" (HYOK), el comportamiento de SharePoint no cambia con esta vista previa. 

Ahora también puede aplicar etiquetas de confidencialidad a Microsoft Teams, a los grupos de Office 365 y a los sitios de SharePoint. Para obtener más información sobre esta vista previa independiente, vea [usar etiquetas de confidencialidad con Microsoft Teams, grupos de Office 365 y sitios de SharePoint (vista previa pública)](sensitivity-labels-teams-groups-sites.md).

Siempre tiene la opción de optar por no participar en esta vista previa en cualquier momento.

Vea el siguiente vídeo (sin audio) para ver estas nuevas funciones en acción:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a>Requirements

Estas características solo funcionan con las [etiquetas de confidencialidad](sensitivity-labels.md) . Si tiene etiquetas de Azure Information Protection, primero deberá migrarlas a las etiquetas de confidencialidad para que pueda habilitarlas para los nuevos archivos que cargue. Para obtener instrucciones, consulte [How to Migrate Azure Information Protection Labels to Unified Sensitivity Labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

Para esta vista previa, use la versión 19.002.0121.0008 o posterior de la aplicación de sincronización de OneDrive en Windows y la versión 19.002.0107.0008 o posterior en Mac. Ambas versiones se han lanzado el 28 de enero de 2019 y actualmente están publicadas para todos los anillos. Para obtener más información, vea las notas de la [versión de OneDrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0). Una vez habilitada esta vista previa, se pedirá a los usuarios que ejecuten una versión anterior de la aplicación de sincronización que la actualicen.

## <a name="limitations"></a>Limitaciones

- Cuando se habilita esta vista previa, los usuarios que cambian una etiqueta a un archivo en una carpeta de sincronización de OneDrive podrían no ser capaces de guardar otros cambios realizados en el archivo.  Los usuarios ven un [círculo rojo con un error de icono en forma de cruz blanca](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)y se les pide que guarden los cambios nuevos como una copia independiente.  Además de los cambios de etiqueta que inician los usuarios, se puede producir el mismo comportamiento si un administrador cambia la configuración de una etiqueta publicada que ya se ha aplicado a los archivos descargados en el cliente de sincronización de los usuarios.
    
    Para evitar la pérdida de trabajo en estos escenarios, realice una de estas acciones:
    - Para aplicar etiquetas, use las versiones web de las aplicaciones de Office.
    - Cierre un archivo después de aplicar una etiqueta y, a continuación, vuelva a abrir el archivo para realizar otros cambios.

- SharePoint no aplica automáticamente las nuevas etiquetas a los archivos existentes que ya se han cifrado con las etiquetas de Azure Information Protection. En su lugar, para que las características funcionen después de habilitar esta vista previa, complete estas tareas:
    
    1. Asegúrese de que ha migrado las etiquetas de Azure Information Protection a las etiquetas de confidencialidad y las ha publicado en el centro de cumplimiento de Microsoft 365, o bien en el centro de administración de etiquetas equivalente.
    
    2. Descargue los archivos y cárguelos en SharePoint.

- SharePoint no puede procesar archivos cifrados cuando la etiqueta que ha aplicado el cifrado tiene alguna de las siguientes configuraciones para el cifrado:
    - **Permitir que los usuarios asignen permisos cuando apliquen la etiqueta** y **en Word, PowerPoint y Excel, pida a los usuarios que especifiquen permisos** .
    - El **acceso del usuario a las expiraciones de contenido** se establece en un valor que no es **nunca**.

- En el caso de un documento cifrado que concede permisos de edición a un usuario, no se puede bloquear la copia en las versiones web de las aplicaciones de Office.

- No se admite el sitio de seguimiento de documentos de Azure Information Protection.

- Las aplicaciones de escritorio y las aplicaciones móviles de Office no admiten la coautoría. En su lugar, estas aplicaciones continúan a la vez que los archivos se abren en el modo de edición exclusivo.

- Si una etiqueta incluye cifrado, Microsoft Cloud App Security no puede leer la información de etiqueta de los archivos en SharePoint.

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a>Preparar el shell de administración de SharePoint Online para la versión preliminar

Antes de habilitar la vista previa, asegúrese de que está ejecutando la versión 16.0.19418.12000 o posterior del shell de administración de SharePoint Online. Si ya tiene la versión más reciente, puede seguir adelante y habilitar la vista previa.

1. Si ha instalado una versión anterior del shell de administración de SharePoint Online desde la galería de PowerShell, puede actualizar el módulo mediante la ejecución del siguiente cmdlet.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. Como alternativa, si ha instalado una versión anterior del shell de administración de SharePoint Online desde el centro de descarga de Microsoft, también puede ir a **Agregar o quitar programas** y desinstalar el shell de administración de SharePoint Online.

3. En un explorador web, vaya a la página del centro de descargas y [Descargue el Shell más reciente de administración de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Seleccione el idioma y, a continuación, haga clic en **Descargar**.

5. Elija entre el archivo .msi x64 y x86. Descargue el archivo x64 si ejecuta la versión de 64 bits de Windows o el archivo x86 si ejecuta la versión de 32 bits. Si no lo sabe, consulte ¿ [qué versión del sistema operativo Windows estoy ejecutando?](https://support.microsoft.com/help/13443/windows-which-operating-system)


6. Una vez que haya descargado el archivo, ejecute el archivo y siga los pasos del Asistente para la instalación.

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a>Habilitación de la vista previa mediante PowerShell de Microsoft (opción opcional)

Para habilitar la vista previa, use el cmdlet Set-SPOTenant:

1. Con una cuenta profesional o educativa con privilegios de administrador global o de administrador de SharePoint en Office 365, conéctese a SharePoint. Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

2. Ejecute el comando siguiente:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a>Programar la distribución después de crear o cambiar una etiqueta de confidencialidad

Después de crear o cambiar una etiqueta de confidencialidad en el centro de cumplimiento de Microsoft 365, publíquela en fases. Si publica etiquetas que no se han sincronizado completamente, cuando los usuarios aplican las etiquetas a los archivos y los cargan en SharePoint, los archivos no se pueden abrir en las versiones web de las aplicaciones de Office. La búsqueda y la exhibición de documentos electrónicos tampoco funcionan para los archivos.

Le recomendamos que siga estos pasos:

1. Publicar la etiqueta de confidencialidad nueva o modificada solo para una o dos personas.

2. Espere al menos 24 horas después de la publicación inicial. Compruebe que la etiqueta se haya sincronizado completamente.

3. Publique la etiqueta de forma general.

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a>Deshabilitar la vista previa mediante PowerShell de Microsoft (no participar)

Si deshabilita esta vista previa, los archivos que cargó en la vista previa seguirán protegidos por la etiqueta. La configuración correspondiente se sigue aplicando. Cuando se aplican etiquetas a nuevos archivos después de deshabilitar la vista previa, la búsqueda de texto completo, la exhibición de documentos electrónicos y la coautoría dejarán de funcionar.

Para deshabilitar la vista previa, use el cmdlet Set-SPOTenant:

1. Con una cuenta profesional o educativa con privilegios de administrador global o de administrador de SharePoint en Office 365, conéctese a SharePoint. Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

2. Ejecute el comando siguiente:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
