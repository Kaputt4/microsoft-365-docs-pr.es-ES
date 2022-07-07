---
title: Centro de administración de Microsoft 365 informes de uso del sitio de SharePoint
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Obtenga el informe de uso del sitio de SharePoint para saber cuántos archivos almacenan los usuarios en sitios de SharePoint, cuántos se usan activamente y el almacenamiento total consumido.
ms.openlocfilehash: 0be00d712ba4a65ff14b10aadd6f74f2d5f82b43
ms.sourcegitcommit: 5014666778b2d48912c68c2e06992cdb43cfaee3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2022
ms.locfileid: "66662710"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Informes de Microsoft 365 en el Centro de administración: uso del sitio de SharePoint

Como administrador de Microsoft 365, el panel Informes muestra la información general de la actividad en varios productos de la organización. Le permite explorar para obtener una visión más detallada de las actividades específicas de cada producto. Por ejemplo, puede obtener una vista de alto nivel del valor que obtiene de SharePoint en términos del número total de archivos que los usuarios almacenan en sitios de SharePoint, cuántos archivos se usan activamente y el almacenamiento consumido en todos estos sitios. Luego, puede explorar el informe de uso del sitio de SharePoint para analizar las tendencias y los detalles de nivel de cada sitio. 

## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Obtener acceso al informe de uso del sitio de SharePoint

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en el botón **Ver más** de la tarjeta de SharePoint.

## <a name="show-user-details-in-the-reports"></a>Mostrar detalles de usuario en los informes

Los informes proporcionan información sobre los datos de uso de la organización. De forma predeterminada, los informes muestran información con nombres identificables para usuarios, grupos y sitios. A partir del 1 de septiembre de 2021, ocultamos información de usuario de forma predeterminada para todos los informes como parte de nuestro compromiso continuo de ayudar a las empresas a apoyar sus leyes de privacidad locales.
  
La lista de usuarios será similar a la siguiente:
  
![Informes: lista anónima de usuarios](../../media/2ed99bce-4978-4ee3-9ea2-4a8db26eef02.png)
  
Los administradores globales pueden revertir este cambio para su inquilino y mostrar información de usuario identificable si las prácticas de privacidad de su organización lo permiten. Se puede lograr en el Centro de administración de Microsoft 365 siguiendo estos pasos:
  
1. En el Centro de administración, vaya a la página **Configuración** \> **Configuración de organización** \> **Servicios**.

2. Seleccione **Informes**. 
  
3. Desactive la instrucción **En todos los informes, mostrar nombres sin identificar para usuarios, grupos y sitios** y, a continuación, guarde los cambios. 
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Interpretación del informe de uso del sitio de SharePoint

Para ver el uso del sitio en el informe de SharePoint, elija la pestaña **Uso del sitio** .

:::image type="content" alt-text="Informes de Microsoft 365: informe de uso del sitio de Microsoft SharePoint." source="../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png" lightbox="../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png":::

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.

:::image type="content" alt-text="Informe de uso del sitio de SharePoint: elija columnas." source="../../media/71ac3195-c494-40c1-9346-a858125ef6df.png":::

También puede exportar los datos del informe a un archivo de excel .csv seleccionando el vínculo **Exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. 

El informe **de uso del sitio de SharePoint** se puede ver para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará los datos durante un máximo de 28 días a partir de la fecha actual (no la fecha en que se generó el informe).
  
|Métrica|Descripción|
|:-----|:-----|
|Dirección URL del sitio  |Dirección URL completa del sitio. |
|Deleted  |Estado de eliminación del sitio. Se tarda como mínimo siete días para que los sitios se marquen como eliminados.  |
|Propietario del sitio  |Nombre de usuario del propietario principal del sitio.   |
|Nombre principal del propietario del sitio  |Dirección de correo electrónico del propietario del sitio. |
|Fecha de la última actividad (UTC)  | Fecha de la última vez que se detectó la actividad del archivo o se vio una página en el sitio.  |
|Identificador de etiqueta de confidencialidad del sitio  | Etiqueta de confidencialidad en el sitio.  |
|Uso compartido externo  | Valor de la configuración de uso compartido externo para el sitio. Este valor no refleja los cambios en la configuración efectiva realizada por las etiquetas de confidencialidad del sitio. Si usa etiquetas de confidencialidad, use los [informes de gobernanza de acceso a datos](/sharepoint/data-access-governance-reports) para obtener los valores correctos.|
|Directiva de dispositivo no administrado  | Directiva de acceso al sitio para dispositivos no administrados.  |
|Ubicación geográfica  | Ubicación geográfica del sitio.  |
|Archivos  |Número de archivos en el sitio. |
|Archivos activos  | Número de archivos activos en el sitio. Un archivo se considera activo si se guardó, sincronizó, modificó o compartió dentro del período de tiempo especificado.<br/> NOTA: Si los archivos se quitaron durante el período de tiempo especificado para el informe, el número de archivos activos que se muestran en el informe puede ser mayor que el número actual de archivos en el sitio.  |
|Almacenamiento usado (MB)  |Cantidad de almacenamiento que se usa actualmente en el sitio.  |
|Almacenamiento asignado (MB)  |Cantidad máxima de almacenamiento asignada para el sitio.  |
|Vistas de página  |Número de veces que se han visto páginas en el sitio.  |
|Páginas visitadas  |El número de páginas únicas que se visitaron en el sitio.  |
|Recuento de vínculos anónimos  |El número de veces que se comparten documentos o carpetas mediante "Cualquiera con el vínculo" en el sitio.  |
|Recuento de vínculos de empresa  |El número de veces que se comparten documentos o carpetas mediante "Personas en la organización con el vínculo" en el sitio.  |
|Vínculo seguro para el recuento de invitados  |El número de veces que se comparten documentos o carpetas mediante "personas específicas" en el sitio.  |
|Vínculo seguro para el recuento de miembros  |El número de veces que se comparten documentos o carpetas mediante "personas específicas" en el sitio.  |
|Plantilla de web raíz  |Plantilla usada para crear el sitio.  <br/> NOTA: Si desea filtrar los datos por tipos de sitio diferentes, exporte los datos y use la columna Plantilla web raíz. |

