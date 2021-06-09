---
title: 'Microsoft 365 Informes en el Centro de administración: SharePoint actividad'
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
description: Obtenga el SharePoint de uso de actividad para conocer la actividad de cada usuario SharePoint, el número de archivos compartidos y el uso del almacenamiento.
ms.openlocfilehash: f049a67e8444654e05cfe3dc72a8d4fe39792cb2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244085"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Microsoft 365 Informes en el Centro de administración: SharePoint actividad

Como administrador Microsoft 365, el panel **informes** le muestra la introducción a la actividad en varios productos de su organización. Le permite explorar para obtener una visión más detallada de las actividades específicas de cada producto. Consulte los informes [de actividad en el centro Microsoft 365 administración](activity-reports.md).
  
Por ejemplo, podrá comprender la actividad de cada usuario con licencia para usar SharePoint consultando su interacción con los archivos. También le ayuda a entender el nivel de colaboración actual consultando el número de archivos compartidos.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, servicio de Teams, comunicaciones de Teams o administrador Skype Empresarial para ver informes. 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>¿Cómo puedo obtener acceso al informe de actividad de SharePoint?

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en el botón **Ver más** en la SharePoint panel.
  
## <a name="interpret-the-sharepoint-activity-report"></a>Interpretar el informe SharePoint actividad

Puede ver las actividades en el informe SharePoint mediante la pestaña **Actividad.**<br/>![Microsoft 365: informe de actividad SharePoint Microsoft.](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![SharePoint de actividad: elegir columnas](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

También puede exportar los datos del informe a un archivo Excel .csv seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 
  
|Elemento|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Nombre de usuario  <br/> |La dirección de correo electrónico del usuario que realizó la actividad en el SharePoint sitio.  <br/> |
|Fecha de última actividad (UTC)  <br/> |La fecha más reciente en que se realizó una actividad de archivo o se visitó una página para el intervalo de fechas seleccionado. Para ver las actividades realizadas en una fecha específica, seleccione la fecha directamente en el gráfico.  <br/> |
|Archivos vistos o editados  <br/> |El número de archivos que el usuario cargó, descargó, modificó o visualizó.   <br/> |
|Archivos sincronizados  <br/> |El número de archivos que se han sincronizado desde el dispositivo local de un usuario al sitio SharePoint usuario. <br/> |
|Archivos compartidos internamente  <br/> | Recuento de archivos que se han compartido con usuarios de la organización o con usuarios de grupos (que pueden incluir usuarios externos).  <br/> |
|Archivos compartidos externamente  <br/> |El número de archivos que se han compartido con usuarios externos a la organización. <br/>|
|Páginas visitadas  <br/> |Las visitas a páginas únicas del usuario. <br/>|
|Eliminada  <br/> | Esto indica que se quitó la licencia del usuario.  <br/>  **NOTA:** La actividad de un usuario eliminado aún se mostrará en el informe siempre y cuando se le haya concedido una licencia en algún momento durante el período de tiempo seleccionado. En la columna Eliminado puede observar que es posible que el usuario ya no esté activo, pero ha contribuido a los datos del informe.  <br/> |
|Fecha de eliminación  <br/> |La fecha en la que se quitó la licencia del usuario. <br/>|
|Producto asignado  <br/> |Los Microsoft 365 que tienen licencia para el usuario.|
|||