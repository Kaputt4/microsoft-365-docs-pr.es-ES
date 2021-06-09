---
title: 'Microsoft 365 Informes en el Centro de administración: SharePoint de sitio'
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
description: Obtenga el SharePoint de uso del sitio para saber cuántos archivos almacenan los usuarios en SharePoint sitios, cuántos se usan activamente y el almacenamiento total consumido.
ms.openlocfilehash: 62bf01c867b7e9217d25e655af6633a72773caa1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241873"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365 Informes en el Centro de administración: SharePoint de sitio

Como administrador Microsoft 365, el panel **Informes** le muestra la información general sobre la actividad en varios productos de su organización. Le permite explorar para obtener una visión más detallada de las actividades específicas de cada producto. Por ejemplo, puede obtener una vista de alto nivel del valor que se genera desde SharePoint en cuanto al número total de archivos que almacenan los usuarios en sitios de SharePoint, el número de archivos que se usan de manera activa y el almacenamiento consumido en todos estos sitios. Luego, puede explorar el informe de uso del sitio de SharePoint para analizar las tendencias y los detalles de nivel de cada sitio. 
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, servicio de Teams, comunicaciones de Teams o administrador Skype Empresarial para ver informes.
Microsoft 365 Los informes en el Centro de administración no se admiten GCC inquilinos de Alto y DoD.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Obtener acceso al informe de uso del sitio de SharePoint

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en el botón **Ver más** en la SharePoint panel.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Interpretar el informe SharePoint uso del sitio

Puede ver el uso del sitio en el informe SharePoint mediante la pestaña **Uso del** sitio.<br/>![Microsoft 365: informe de uso SharePoint sitio de Microsoft.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.  <br/> ![SharePoint de uso del sitio: elija columnas](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)

También puede exportar los datos del informe a un archivo Excel .csv seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 
  
|Elemento|Descripción|
|:-----|:-----|
|**Métrica**|**Definición**|
|Dirección URL del sitio  <br/> |La dirección URL completa del sitio. <br/> |
|Eliminada  <br/> |El estado de eliminación del sitio. Se tarda como mínimo siete días para que los sitios se marquen como eliminados.  <br/> |
|Propietario del sitio  <br/> |Nombre de usuario del propietario principal del sitio.   <br/> |
|Nombre principal del propietario del sitio  <br/> |La dirección de correo electrónico del propietario del sitio. <br/> |
|Fecha de última actividad (UTC)  <br/> | La fecha de la última vez que se detectó la actividad del archivo o una página se visualizó en el sitio.  <br/> |
|Id. de etiqueta de confidencialidad del sitio  <br/> | La etiqueta de confidencialidad del sitio.  <br/> |
|Uso compartido externo  <br/> | La configuración externa que se puede compartir en el sitio.  <br/> |
|Directiva de dispositivos no administrados  <br/> | La directiva de acceso al sitio para dispositivos no administrados.  <br/> |
|Ubicación geográfica  <br/> | Ubicación geográfica del sitio.  <br/> |
|Archivos  <br/> |El número de archivos del sitio. <br/>|
|Archivos activos  <br/> | Número de archivos activos en el sitio.<br/> NOTA: Si los archivos se quitaron durante el período de tiempo especificado para el informe, el número de archivos activos que se muestran en el informe puede ser mayor que el número actual de archivos en el sitio.  <br/> |
|Storage usado (MB)  <br/> |La cantidad de almacenamiento que se usa actualmente en el sitio.  <br/>|
|Storage asignado (MB)  <br/> |La cantidad máxima de almacenamiento asignada al sitio.  <br/>|
|Vistas de página  <br/> |El número de veces que se han visto las páginas en el sitio.  <br/>|
|Páginas visitadas  <br/> |El número de páginas únicas que se visitaron en el sitio.  <br/>|
|Recuento de vínculos anónimos  <br/> |El número de veces que se comparten documentos o carpetas con "Cualquiera con el vínculo" en el sitio.  <br/>|
|Recuento de vínculos de empresa  <br/> |El número de veces que se comparten documentos o carpetas con "Personas de la organización con el vínculo" en el sitio.  <br/>|
|Vínculo seguro para el recuento de invitados  <br/> |El número de veces que se comparten documentos o carpetas con "personas específicas" en el sitio.  <br/>|
|Vínculo seguro para el recuento de miembros  <br/> |El número de veces que se comparten documentos o carpetas con "personas específicas" en el sitio.  <br/>|
|Plantilla de web raíz  <br/> |Plantilla usada para crear el sitio.  <br/> NOTA: Si desea filtrar los datos por diferentes tipos de sitio, exporte los datos y use la columna Plantilla web raíz. |
|||