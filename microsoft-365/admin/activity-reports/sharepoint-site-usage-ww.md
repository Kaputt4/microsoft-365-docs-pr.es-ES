---
title: 'Informes de Microsoft 365 en el centro de administración: uso del sitio de SharePoint'
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
description: Obtenga el informe de uso del sitio de SharePoint para saber cuántos archivos almacenan los usuarios en los sitios de SharePoint, cuántos se usan activamente y el almacenamiento total que se ha consumido.
ms.openlocfilehash: bc9345a5e281f1e7343bf62a2dc6832587d0786e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649876"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Informes de Microsoft 365 en el centro de administración: uso del sitio de SharePoint

Como administrador de Microsoft 365, el panel **informes** muestra la información general de la actividad en varios productos de la organización. Le permite explorar para obtener una visión más detallada de las actividades específicas de cada producto. Por ejemplo, puede obtener una vista de alto nivel del valor que se genera desde SharePoint en cuanto al número total de archivos que almacenan los usuarios en sitios de SharePoint, el número de archivos que se usan de manera activa y el almacenamiento consumido en todos estos sitios. Luego, puede explorar el informe de uso del sitio de SharePoint para analizar las tendencias y los detalles de nivel de cada sitio. 
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams, Team Communications o Skype empresarial para ver los informes.
Los informes de Microsoft 365 en el centro de administración no son compatibles con los inquilinos de GCC High y DoD.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Obtener acceso al informe de uso del sitio de SharePoint

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la Página principal del panel, haga clic en el botón **Ver más** de la tarjeta de SharePoint.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Interpretar el informe de uso del sitio de SharePoint

Puede ver el uso del sitio en el informe de SharePoint seleccionando la pestaña **uso del sitio** .<br/>![Microsoft 365 Reports: informe de uso del sitio de Microsoft SharePoint.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Seleccione **elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Informe de uso del sitio de SharePoint: elegir columnas](../../media/639f3cfd-6725-4318-a225-6d5c2f01770c.png)

También puede exportar los datos del informe a un archivo. csv de Excel; para ello, seleccione el vínculo **exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 
  
|Item|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Dirección URL del sitio  <br/> |La dirección URL completa del sitio. <br/> |
|Deleted  <br/> |El estado de eliminación del sitio. Se tarda como mínimo siete días para que los sitios se marquen como eliminados.  <br/> |
|Propietario del sitio  <br/> |El nombre de usuario del propietario principal del sitio.   <br/> |
|Nombre principal del propietario del sitio  <br/> |La dirección de correo electrónico del propietario del sitio. <br/> |
|Fecha de la última actividad (UTC)  <br/> | Fecha de la última vez que se detectó actividad de archivo o se vio una página en el sitio.  <br/> |
|Archivos  <br/> |El número de archivos del sitio. <br/>|
|Archivos activos  <br/> | El número de archivos activos en el sitio.<br/> Nota: si los archivos se quitaron durante el período de tiempo especificado para el informe, el número de archivos activos que se muestran en el informe puede ser mayor que el número actual de archivos en el sitio.  <br/> |
|Almacenamiento usado (MB)  <br/> |La cantidad de almacenamiento que se está usando actualmente en el sitio.  <br/>|
|Almacenamiento asignado (MB)  <br/> |La cantidad máxima de almacenamiento asignado para el sitio.  <br/>|
|Vistas de página  <br/> |Número de veces que las páginas se han visto en el sitio.  <br/>|
|Páginas visitadas  <br/> |Número de páginas únicas que se han visitado en el sitio.  <br/>|
|Plantilla de web raíz  <br/> |Plantilla utilizada para crear el sitio.  <br/> Nota: Si desea filtrar los datos por distintos tipos de sitio, exporte los datos y use la columna raíz Web Template. |
|||