---
title: Centro de administración de Microsoft 365 informes de actividad de SharePoint
f1.keywords:
- NOCSH
ms.author: camillepack
author: camillepack
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Obtenga el informe de uso de actividad de SharePoint para obtener información sobre las interacciones de archivos de usuario con licencia de SharePoint, el número de archivos compartidos y el uso del almacenamiento.
ms.openlocfilehash: 97457e396a9a733183dadf7d10045321c7aed226
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68722646"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Informes de Microsoft 365 en el Centro de administración: actividad de SharePoint

Como administrador de Microsoft 365, el panel Informes muestra la información general de la actividad en varios productos de la organización. Le permite explorar para obtener una visión más detallada de las actividades específicas de cada producto. Consulte los [informes de actividad en el Centro de administración de Microsoft 365](activity-reports.md).
  
For example, you can understand the activity of every user licensed to use SharePoint by looking at their interaction with files. It also helps you to understand the level of collaboration going on by looking at the number of files shared.
  
## <a name="how-do-i-get-to-the-sharepoint-activity-report"></a>Cómo llegar al informe de actividad de SharePoint?

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en el botón **Ver más** de la tarjeta de SharePoint.
  
## <a name="interpret-the-sharepoint-activity-report"></a>Interpretación del informe de actividad de SharePoint

Para ver las actividades en el informe de SharePoint, elija la pestaña **Actividad** .<br/>![Informes de Microsoft 365: informe de actividad de Microsoft SharePoint.](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe. 

![Informe de actividad de SharePoint: elija columnas.](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

También puede exportar los datos del informe a un archivo de excel .csv seleccionando el vínculo **Exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado.  

El informe de **actividad de SharePoint** se puede ver para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará los datos durante un máximo de 28 días a partir de la fecha actual (no la fecha en que se generó el informe).
  
|Elemento|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre de usuario  <br/> |Dirección de correo electrónico del usuario que realizó la actividad en el sitio de SharePoint.  <br/> |
|Fecha de la última actividad (UTC)  <br/> |La última fecha en que se realizó una actividad de archivo o se visitó una página para el intervalo de fechas seleccionado. Para ver las actividades realizadas en una fecha específica, seleccione la fecha directamente en el gráfico.  <br/> |
|Archivos vistos o editados  <br/> |Número de archivos que el usuario cargó, descargó, modificó o ha visto.   <br/> |
|Archivos sincronizados  <br/> |Número de archivos que se han sincronizado desde el dispositivo local de un usuario al sitio de SharePoint. <br/> |
|Archivos compartidos internamente  <br/> | Recuento de archivos que se han compartido con usuarios de la organización o con usuarios dentro de grupos (que pueden incluir usuarios externos).  <br/> |
|Archivos compartidos externamente  <br/> |Número de archivos que se han compartido con usuarios fuera de la organización. <br/>|
|Páginas visitadas  <br/> |Las visitas a páginas únicas por parte del usuario. <br/>|
|Deleted  <br/> | Esto indica que se quitó la licencia del usuario.  <br/>  **NOTA:** La actividad de un usuario eliminado seguirá mostrándose en el informe siempre y cuando se le haya concedido una licencia en algún momento durante el período de tiempo seleccionado. En la columna Eliminado puede observar que es posible que el usuario ya no esté activo, pero ha contribuido a los datos del informe.  <br/> |
|Fecha de eliminación  <br/> |Fecha en la que se quitó la licencia del usuario. <br/>|
|Producto asignado  <br/> |Los productos de Microsoft 365 con licencia para el usuario.|
|||