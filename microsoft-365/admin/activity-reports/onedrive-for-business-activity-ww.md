---
title: 'Microsoft 365 Informes en el Centro de administración: OneDrive para la Empresa actividad'
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Obtenga el OneDrive de uso de la organización y conozca la actividad de cada usuario OneDrive, el número de archivos compartidos y el uso del almacenamiento.
ms.openlocfilehash: 8257d8e85819ff5edae96967fd4a687be3a903a1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244097"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Microsoft 365 Informes en el Centro de administración: OneDrive para la Empresa actividad

El panel Microsoft 365 **informes le** muestra la introducción a la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle más información pormenorizada acerca de las actividades dentro de cada producto. Consulte [el tema de información general de los informes](activity-reports.md).
  
Por ejemplo, podrá comprender la actividad de cada usuario con licencia para usar OneDrive consultando su interacción con los archivos en OneDrive. También le ayuda a entender el nivel de colaboración actual observando el número de archivos compartidos.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, servicio de Teams, comunicaciones de Teams o administrador Skype Empresarial para ver informes.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>¿Cómo puedo tener acceso al informe de actividades de OneDrive?

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en el botón **Ver más** en la OneDrive panel.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Interpretar el informe de actividades de OneDrive para la Empresa

Puede ver las actividades en el informe OneDrive seleccionando la **pestaña** Actividad.<br/>![Microsoft 365: informe Microsoft OneDrive actividad.](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![OneDrive de actividad: elegir columnas](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

También puede exportar los datos del informe a un archivo Excel .csv seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 
  
|Elemento|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre de usuario  <br/> |Nombre de usuario del propietario de la OneDrive cuenta.  <br/> |
|Fecha de última actividad (UTC)  <br/> |La fecha más reciente en la que se realizó una actividad de archivo OneDrive cuenta para el intervalo de fechas seleccionado. . Para ver las actividades realizadas en una fecha específica, seleccione la fecha directamente en el gráfico.  <br/> |
|Archivos vistos o editados  <br/> |El número de archivos que el usuario cargó, descargó, modificó o visualizó.   <br/> |
|Archivos sincronizados  <br/> |El número de archivos que se han sincronizado desde el dispositivo local de un usuario con la cuenta OneDrive usuario. <br/> |
|Archivos compartidos internamente  <br/> | El número de archivos que se han compartido con usuarios de la organización o con usuarios de grupos (que pueden incluir usuarios externos).  <br/> |
|Archivos compartidos externamente  <br/> |El número de archivos que se han compartido con usuarios externos a la organización. <br/>|
|Eliminada  <br/> | Esto indica que se quitó la licencia del usuario.  <br/> NOTA: La actividad de un usuario eliminado seguirá mostrándose en un informe siempre y cuando se le haya concedido una licencia en algún momento durante el período de tiempo seleccionado. En la columna **Eliminado** puede observar que es posible que el usuario ya no esté activo, pero ha contribuido a los datos del informe.  <br/> |
|Fecha de eliminación  <br/> |La fecha en la que se quitó la licencia del usuario. <br/>|
|Producto asignado  <br/> |Los Microsoft 365 que tienen licencia para el usuario.|
|||