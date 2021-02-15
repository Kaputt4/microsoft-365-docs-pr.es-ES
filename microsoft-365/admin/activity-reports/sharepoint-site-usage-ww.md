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
description: Obtenga el informe de uso del sitio de SharePoint para saber cuántos archivos almacenan los usuarios en sitios de SharePoint, cuántos se usan activamente y el almacenamiento total consumido.
ms.openlocfilehash: 403ebfd75fca5ba5777832140155bb09734db3c7
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233518"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Informes de Microsoft 365 en el centro de administración: uso del sitio de SharePoint

Como administrador de Microsoft 365, el panel informes muestra la información general sobre la actividad en varios productos de la organización.  Le permite explorar para obtener una visión más detallada de las actividades específicas de cada producto. Por ejemplo, puede obtener una vista de alto nivel del valor que se genera desde SharePoint en cuanto al número total de archivos que almacenan los usuarios en sitios de SharePoint, el número de archivos que se usan de manera activa y el almacenamiento consumido en todos estos sitios. Luego, puede explorar el informe de uso del sitio de SharePoint para analizar las tendencias y los detalles de nivel de cada sitio. 
  
> [!NOTE]
> Debe ser un administrador global, un lector global o un lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams Service, Teams Communications o Skype Empresarial para ver informes.
Los informes de Microsoft 365 en el centro de administración no son compatibles con los inquilinos GCC High y DoD.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Obtener acceso al informe de uso del sitio de SharePoint

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en el **botón Ver más** en la tarjeta de SharePoint.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Interpretar el informe de uso del sitio de SharePoint

Puede ver el uso del sitio en el informe de SharePoint seleccionando la **pestaña Uso del** sitio.<br/>![Informes de Microsoft 365: informe de uso del sitio de Microsoft SharePoint.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![Informe de uso del sitio de SharePoint: elegir columnas](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)

También puede exportar los datos del informe a un archivo .csv de Excel seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 
  
|Elemento|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Dirección URL del sitio  <br/> |La dirección URL completa del sitio. <br/> |
|Deleted  <br/> |El estado de eliminación del sitio. Se tarda como mínimo siete días para que los sitios se marquen como eliminados.  <br/> |
|Propietario del sitio  <br/> |Nombre de usuario del propietario principal del sitio.   <br/> |
|Nombre principal del propietario del sitio  <br/> |La dirección de correo electrónico del propietario del sitio. <br/> |
|Fecha de la última actividad (UTC)  <br/> | La fecha de la última vez que se detectó la actividad del archivo o se visualizó una página en el sitio.  <br/> |
|Id. de etiqueta de confidencialidad del sitio  <br/> | La etiqueta de confidencialidad del sitio.  <br/> |
|Uso compartido externo  <br/> | La configuración externa que se puede compartir en el sitio.  <br/> |
|Directiva de dispositivo no administrado  <br/> | Directiva de acceso al sitio para dispositivos no administrados.  <br/> |
|Ubicación geográfica  <br/> | Ubicación geográfica del sitio.  <br/> |
|Archivos  <br/> |El número de archivos del sitio. <br/>|
|Archivos activos  <br/> | El número de archivos activos en el sitio.<br/> NOTA: Si los archivos se quitaron durante el período de tiempo especificado para el informe, el número de archivos activos que se muestran en el informe puede ser mayor que el número actual de archivos en el sitio.  <br/> |
|Almacenamiento usado (MB)  <br/> |La cantidad de almacenamiento que se usa actualmente en el sitio.  <br/>|
|Almacenamiento asignado (MB)  <br/> |La cantidad máxima de almacenamiento asignada al sitio.  <br/>|
|Vistas de página  <br/> |El número de veces que se han visto las páginas en el sitio.  <br/>|
|Páginas visitadas  <br/> |El número de páginas únicas que se visitaron en el sitio.  <br/>|
|Recuento de vínculos anónimos  <br/> |El número de veces que se comparten documentos o carpetas con "Cualquiera con el vínculo" en el sitio.  <br/>|
|Recuento de vínculos de empresa  <br/> |El número de veces que se comparten documentos o carpetas con "Personas de la organización con el vínculo" en el sitio.  <br/>|
|Vínculo seguro para el recuento de invitados  <br/> |El número de veces que se comparten documentos o carpetas con "personas específicas" en el sitio.  <br/>|
|Vínculo seguro para el recuento de miembros  <br/> |El número de veces que se comparten documentos o carpetas con "personas específicas" en el sitio.  <br/>|
|Plantilla de web raíz  <br/> |Plantilla usada para crear el sitio.  <br/> NOTA: Si desea filtrar los datos por diferentes tipos de sitio, exporte los datos y use la columna Plantilla web raíz. |
|||