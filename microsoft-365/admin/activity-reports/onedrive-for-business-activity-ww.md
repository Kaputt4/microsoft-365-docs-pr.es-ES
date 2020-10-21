---
title: 'Microsoft 365 Reports en el centro de administración: actividad de OneDrive para la empresa'
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Obtenga el informe de uso de OneDrive para la organización y conozca la actividad de cada usuario de OneDrive, el número de archivos compartidos y el uso del almacenamiento.
ms.openlocfilehash: e83ec835f0aa4a453f14a44d9582edcfd5aa6433
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649867"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Microsoft 365 Reports en el centro de administración: actividad de OneDrive para la empresa

El panel de **informes** de Microsoft 365 muestra la información general de la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle más información pormenorizada acerca de las actividades dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Por ejemplo, podrá comprender la actividad de cada usuario con licencia para usar OneDrive consultando su interacción con los archivos en OneDrive. También le ayuda a entender el nivel de colaboración actual observando el número de archivos compartidos.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams, Team Communications o Skype empresarial para ver los informes.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>¿Cómo puedo tener acceso al informe de actividades de OneDrive?

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la Página principal del panel, haga clic en el botón **Ver más** de la tarjeta de OneDrive.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Interpretar el informe de actividades de OneDrive para la Empresa

Puede ver las actividades en el informe de OneDrive eligiendo la pestaña **actividad** .<br/>![Informes de Microsoft 365: informe de actividad de OneDrive de Microsoft.](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

Seleccione **elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Informe de actividad de OneDrive: elegir columnas](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

También puede exportar los datos del informe a un archivo. csv de Excel; para ello, seleccione el vínculo **exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 
  
|Item|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre de usuario  <br/> |El nombre de usuario del propietario de la cuenta de OneDrive.  <br/> |
|Fecha de la última actividad (UTC)  <br/> |La última fecha en que se realizó una actividad de archivo en la cuenta de OneDrive para el intervalo de fechas seleccionado. . Para ver las actividades realizadas en una fecha específica, seleccione la fecha directamente en el gráfico.  <br/> |
|Archivos vistos o modificados  <br/> |El número de archivos que el usuario cargó, descargó, modificó o vio.   <br/> |
|Archivos sincronizados  <br/> |El número de archivos que se han sincronizado desde el dispositivo local de un usuario a la cuenta de OneDrive. <br/> |
|Archivos compartidos internamente  <br/> | El número de archivos que se han compartido con usuarios dentro de la organización o con usuarios de grupos (que pueden incluir usuarios externos).  <br/> |
|Archivos compartidos de forma externa  <br/> |El número de archivos que se han compartido con usuarios fuera de la organización. <br/>|
|Deleted  <br/> | Esto indica que se ha quitado la licencia del usuario.  <br/> Nota: la actividad de un usuario eliminado se seguirá mostrando en un informe siempre que tenga una licencia en algún momento durante el período de tiempo seleccionado. En la columna **Eliminado** puede observar que es posible que el usuario ya no esté activo, pero ha contribuido a los datos del informe.  <br/> |
|Fecha de eliminación  <br/> |La fecha en la que se quitó la licencia del usuario. <br/>|
|Producto asignado  <br/> |Los productos de Microsoft 365 que tienen licencia para el usuario.|
|||