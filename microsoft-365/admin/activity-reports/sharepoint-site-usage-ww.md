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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Obtenga el SharePoint de uso del sitio para saber cuántos archivos almacenan los usuarios en SharePoint sitios, cuántos se usan activamente y el almacenamiento total consumido.
ms.openlocfilehash: 116b4521408fd8cd41e22a959a7b530dbce01174
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2021
ms.locfileid: "59356106"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365 Informes en el Centro de administración: SharePoint de sitio

Como administrador Microsoft 365, el panel **Informes** le muestra la información general sobre la actividad en varios productos de su organización. Le permite explorar para obtener una visión más detallada de las actividades específicas de cada producto. Por ejemplo, puede obtener una vista de alto nivel del valor que obtiene de SharePoint en términos del número total de archivos que los usuarios almacenan en sitios de SharePoint, cuántos archivos se usan activamente y el almacenamiento consumido en todos estos sitios. Luego, puede explorar el informe de uso del sitio de SharePoint para analizar las tendencias y los detalles de nivel de cada sitio. 
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, servicio de Teams, comunicaciones de Teams o administrador Skype Empresarial para ver informes.
Microsoft 365 Los informes en el Centro de administración no se admiten GCC inquilinos de Alto y DoD.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Obtener acceso al informe de uso del sitio de SharePoint

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en el botón **Ver más** en la SharePoint panel.

## <a name="show-user-details-in-the-reports"></a>Mostrar detalles de usuario en los informes

Los informes proporcionan información sobre los datos de uso de la organización. De forma predeterminada, los informes muestran información con nombres identificables para usuarios, grupos y sitios. A partir del 1 de septiembre de 2021, ocultamos información de usuario de forma predeterminada para todos los informes como parte de nuestro compromiso continuo de ayudar a las empresas a apoyar sus leyes de privacidad locales.
  
La lista de usuarios será similar a la siguiente:
  
![Informes: lista anónima de usuarios](../../media/2ed99bce-4978-4ee3-9ea2-4a8db26eef02.png)
  
Los administradores globales pueden revertir este cambio para su inquilino y mostrar información de usuario identificable si las prácticas de privacidad de su organización lo permiten. Se puede lograr en el Centro de administración de Microsoft 365 siguiendo estos pasos:
  
1. En el Centro de administración, vaya a la página **Configuración** \> **Configuración de organización** \> **Servicios**.

2. Seleccione **Informes**. 
  
3. Desactive la instrucción **En todos los informes, mostrar nombres sin identificar para usuarios, grupos y sitios** y, a continuación, guarde los cambios. 
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Interpretar el informe SharePoint uso del sitio

Puede ver el uso del sitio en el informe SharePoint mediante la pestaña **Uso del** sitio.

:::image type="content" alt-text="Microsoft 365: informe de uso SharePoint sitio de Microsoft." source="../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png" lightbox="../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png":::

Seleccione **Elegir columnas** para agregar o quitar columnas del informe.

:::image type="content" alt-text="SharePoint de uso del sitio: elija columnas." source="../../media/71ac3195-c494-40c1-9346-a858125ef6df.png":::

También puede exportar los datos del informe a un archivo Excel .csv seleccionando el **vínculo** Exportar. Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos. 
  
|Métrica|Descripción|
|:-----|:-----|
|Dirección URL del sitio  |La dirección URL completa del sitio. |
|Deleted  |El estado de eliminación del sitio. Se tarda como mínimo siete días para que los sitios se marquen como eliminados.  |
|Propietario del sitio  |Nombre de usuario del propietario principal del sitio.   |
|Nombre principal del propietario del sitio  |La dirección de correo electrónico del propietario del sitio. |
|Fecha de última actividad (UTC)  | La fecha de la última vez que se detectó la actividad del archivo o una página se visualizó en el sitio.  |
|Id. de etiqueta de confidencialidad del sitio  | La etiqueta de confidencialidad del sitio.  |
|Uso compartido externo  | La configuración externa que se puede compartir en el sitio.  |
|Directiva de dispositivos no administrados  | La directiva de acceso al sitio para dispositivos no administrados.  |
|Ubicación geográfica  | Ubicación geográfica del sitio.  |
|Archivos  |El número de archivos del sitio. |
|Archivos activos  | Número de archivos activos en el sitio.<br/> NOTA: Si los archivos se quitaron durante el período de tiempo especificado para el informe, el número de archivos activos que se muestran en el informe puede ser mayor que el número actual de archivos en el sitio.  |
|Storage usado (MB)  |La cantidad de almacenamiento que se usa actualmente en el sitio.  |
|Storage asignado (MB)  |La cantidad máxima de almacenamiento asignada al sitio.  |
|Vistas de página  |El número de veces que se han visto las páginas en el sitio.  |
|Páginas visitadas  |El número de páginas únicas que se visitaron en el sitio.  |
|Recuento de vínculos anónimos  |El número de veces que se comparten documentos o carpetas con "Cualquiera con el vínculo" en el sitio.  |
|Recuento de vínculos de empresa  |El número de veces que se comparten documentos o carpetas con "Personas de la organización con el vínculo" en el sitio.  |
|Vínculo seguro para el recuento de invitados  |El número de veces que se comparten documentos o carpetas con "personas específicas" en el sitio.  |
|Vínculo seguro para el recuento de miembros  |El número de veces que se comparten documentos o carpetas con "personas específicas" en el sitio.  |
|Plantilla de web raíz  |Plantilla usada para crear el sitio.  <br/> NOTA: Si desea filtrar los datos por diferentes tipos de sitio, exporte los datos y use la columna Plantilla web raíz. |

