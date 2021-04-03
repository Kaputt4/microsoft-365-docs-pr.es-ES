---
title: 'Informes de Microsoft 365 en el Centro de administración: actividad de SharePoint'
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Obtenga el informe de uso de actividad de SharePoint para conocer la actividad de cada usuario de SharePoint, el número de archivos compartidos y el uso del almacenamiento.
ms.openlocfilehash: 71cea1e4b5875c0c00dd6dc6cb564e01b84cfb77
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579523"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Informes de Microsoft 365 en el Centro de administración: actividad de SharePoint

Como administrador de Microsoft 365, el panel **informes** muestra la introducción a la actividad en varios productos de la organización. Le permite explorar para obtener una visión más detallada de las actividades específicas de cada producto. Consulte los informes de actividad en el Centro de administración de [Microsoft 365](activity-reports.md).
  
Por ejemplo, podrá comprender la actividad de cada usuario con licencia para usar SharePoint consultando su interacción con los archivos. También le ayuda a entender el nivel de colaboración actual consultando el número de archivos compartidos.
  
> [!NOTE]
> Debe ser un administrador global, un lector global o un lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams Service, Teams Communications o Skype Empresarial para ver informes. 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>¿Cómo puedo obtener acceso al informe de actividad de SharePoint?

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en **el botón Ver más** de la tarjeta de SharePoint.
  
## <a name="interpret-the-sharepoint-activity-report"></a>Interpretar el informe de actividad de SharePoint

Puede ver las actividades en el informe de SharePoint seleccionando la **pestaña** Actividad.<br/>![Informes de Microsoft 365: informe de actividad de Microsoft SharePoint.](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Informe de actividad de SharePoint: elegir columnas](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

También puede exportar los datos del informe a un archivo .csv de Excel seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 
  
|Item|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre de usuario  <br/> |Dirección de correo electrónico del usuario que realizó la actividad en el sitio de SharePoint.  <br/> |
|Fecha de última actividad (UTC)  <br/> |La fecha más reciente en que se realizó una actividad de archivo o se visitó una página para el intervalo de fechas seleccionado. Para ver las actividades realizadas en una fecha específica, seleccione la fecha directamente en el gráfico.  <br/> |
|Archivos vistos o editados  <br/> |El número de archivos que el usuario cargó, descargó, modificó o visualizó.   <br/> |
|Archivos sincronizados  <br/> |El número de archivos que se han sincronizado desde el dispositivo local de un usuario al sitio de SharePoint. <br/> |
|Archivos compartidos internamente  <br/> | Recuento de archivos que se han compartido con usuarios de la organización o con usuarios de grupos (que pueden incluir usuarios externos).  <br/> |
|Archivos compartidos externamente  <br/> |El número de archivos que se han compartido con usuarios externos a la organización. <br/>|
|Páginas visitadas  <br/> |Las visitas a páginas únicas del usuario. <br/>|
|Deleted  <br/> | Esto indica que se quitó la licencia del usuario.  <br/>  **NOTA:** La actividad de un usuario eliminado aún se mostrará en el informe siempre y cuando se le haya concedido una licencia en algún momento durante el período de tiempo seleccionado. En la columna Eliminado puede observar que es posible que el usuario ya no esté activo, pero ha contribuido a los datos del informe.  <br/> |
|Fecha de eliminación  <br/> |La fecha en la que se quitó la licencia del usuario. <br/>|
|Producto asignado  <br/> |Los productos de Microsoft 365 con licencia para el usuario.|
|||