---
title: SharePoint los límites del sitio del portal moderno en línea
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 10/9/2019
audience: Admin
ms.topic: interactive-tutorial
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
description: Obtenga información sobre las recomendaciones de rendimiento para sitios modernos en SharePoint Online, como limitar las llamadas a SharePoint y puntos de conexión externos.
ms.openlocfilehash: a0163cd808ce3eb25da8d1c94fb27ed9d238d75a
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091157"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>SharePoint los límites del sitio del portal moderno en línea

En este artículo se proporcionan recomendaciones de rendimiento para los sitios del portal modernos en SharePoint Online. Use las directrices de este artículo para optimizar el rendimiento del sitio del portal moderno y evitar problemas comunes de rendimiento.

## <a name="performance-considerations-for-modern-portal-sites"></a>Consideraciones de rendimiento para sitios de portal modernos

Desde el punto de vista de la optimización del rendimiento, hay algunas características que hacen que los sitios de portal modernos sean únicos. La principal diferencia entre la colaboración y los sitios del portal en SharePoint Online es la escala. Por lo general, se espera que los sitios del portal sirvan más vistas de página a un mayor número de usuarios que los sitios de colaboración, y es probable que contengan más contenido estático y menos recursos modificables. Además, la arquitectura de los sitios modernos difiere de los sitios clásicos, ya que la mayor parte del procesamiento implicado en la representación de páginas y la ejecución de código tiene lugar en el cliente en lugar del servidor.

La optimización del rendimiento de los sitios de portal modernos se centra principalmente en algunos objetivos generales:

- Reducir el tamaño total de los componentes de cada página de sitio
- Descargue el hospedaje de archivos estáticos comunes, como imágenes, hojas de estilos y scripts, para CDN
- Limitar las llamadas a SharePoint y puntos de conexión externos solo a lo necesario
- Evitar solicitudes duplicadas para el mismo contenido

Muchas de las directrices de este artículo se centran en minimizar y optimizar las llamadas a SharePoint Online. Realizar llamadas repetitivas cada vez que se carga una página afectará al rendimiento de los usuarios, ya que la información se recuperará del servicio cada vez, incluso si no ha cambiado. Por lo tanto, las solicitudes a SharePoint se pueden clasificar como llamadas que son comunes para todos los usuarios o llamadas necesarias para cada usuario individual. Los resultados de estas dos categorías de llamadas deben almacenarse en caché para optimizar la experiencia del usuario.

>[!NOTE]
>Use la [herramienta Diagnóstico de páginas para SharePoint](./page-diagnostics-for-spo.md) como punto de partida para analizar métricas de rendimiento específicas en SharePoint páginas de sitio en línea.

## <a name="modern-portal-site-limits-and-recommendations"></a>Recomendaciones y límites del sitio del portal moderno

|**Límite**|**Valor máximo recomendado**|**Notas**|
|:-----|:-----|:-----|:-----|
|Páginas y elementos de noticias  <br/> |5.000 por sitio  <br/> |Se recomienda limitar el número de páginas y elementos de noticias de un sitio de portal moderno a menos de 5000.  <br/> |
|Elementos web en una página  <br/> |20 por página  <br/> |Se recomienda usar 20 o menos elementos web totales por página, incluidos los elementos web de Microsoft de fábrica y los elementos web personalizados. <br/> Para obtener más información, consulte [Optimización del rendimiento de elementos web en SharePoint páginas de sitio modernos en línea](modern-web-part-optimization.md).  <br/> |
|Elementos web dinámicos en una página  <br/> |4 por página  <br/> |Los elementos web dinámicos que realizan una o varias consultas para SharePoint para capturar los datos más recientes deben limitarse a 4 por página. El elemento web _Noticias_ es un ejemplo de un elemento web dinámico. <br/> Para obtener más información, consulte [Optimización del rendimiento de elementos web en SharePoint páginas de sitio modernos en línea](modern-web-part-optimization.md).    <br/> |
|Grupos de seguridad  <br/> |20 por sitio  <br/> |El número de grupos de seguridad afecta a la escala de muchas consultas en sitios de portal modernos. Se recomienda limitar el número de grupos de seguridad a un conjunto lo más pequeño posible, sin más de 20 por sitio.  <br/> |
|Elementos en la navegación del sitio  <br/> |100 por sitio  <br/> |Se recomienda agregar menos de 100 elementos a la navegación del sitio y usar controles de navegación integrados.  <br/> Para obtener más información, vea [Optimizar el peso de la página en SharePoint páginas de sitio modernos en línea](modern-page-weight-optimization.md). <br/> |
|Tamaño máximo de imagen  <br/> |300 Kb por imagen  <br/> |Se recomienda limitar el tamaño de las imágenes a 300 kb o más pequeño y usar un CDN para hospedar imágenes, hojas de estilos y scripts. <br/>Para obtener más información, vea [Optimizar imágenes en SharePoint páginas de sitios modernos en línea](modern-image-optimization.md) y [Usar el Office 365 Content Delivery Network (CDN) con SharePoint Online](use-microsoft-365-cdn-with-spo.md).  <br/> |
|Usuarios con derechos de edición  <br/> |200 usuarios por sitio  <br/> |SharePoint sitios del portal están optimizados para ver y consumir contenido. Los permisos de edición en un portal deben limitarse a un grupo restringido de usuarios porque los permisos de edición descargan controles adicionales y, por tanto, se realizarán más lentos para esos usuarios. Por lo tanto, un número excesivo de usuarios con permisos de edición afectará a la experiencia general. <br/> |
|IFrames de terceros  <br/> |2 por página  <br/> |Los iFrames son impredeciblemente lentos porque cargan una página externa independiente, incluido todo el contenido asociado, como javascript, CSS y elementos de marco. Si debe usar iFrames, limite su número a 2 o menos por página.<br/> Para obtener más información, vea [Optimizar iFrames en SharePoint páginas de sitio de publicación modernas y clásicas en línea](modern-iframe-optimization.md). <br/> |
|Llamadas al servicio UPA  <br/> |1 por usuario y hora  <br/> |Se recomienda no realizar llamadas _por solicitud_ al servicio UPA (aplicación de perfil de usuario). [Microsoft Graph API](/graph/call-api) y [PageContext](/javascript/api/sp-page-context/pagecontext) se pueden usar para consultar la información del usuario.  <br/> Si es necesaria una llamada de servicio UPA, realice una sola llamada cuando sea necesario y, a continuación, almacene en caché la información para su reutilización en la misma sesión. |
|Llamadas al servicio taxonomía  <br/> |5 por usuario y hora  <br/> |Se recomienda no realizar llamadas _por solicitud_ al servicio taxonomía. Si son necesarias llamadas al servicio Taxonomía, almacene en caché la información para su reutilización en la misma sesión. <br/> Para obtener más información, vea [Optimizar las llamadas a páginas en SharePoint páginas de sitio de publicación modernas y clásicas en línea](modern-page-call-optimization.md). <br/> |

## <a name="related-topics"></a>Temas relacionados

[Creación de un portal de SharePoint correcto](/sharepoint/portal-health)

[Ajustar el rendimiento de SharePoint Online](tune-sharepoint-online-performance.md)

[Ajustar el rendimiento de Office 365](tune-microsoft-365-performance.md)

[SharePoint Online limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) (Límites de SharePoint Online)

[Rendimiento en la experiencia moderna de SharePoint](/sharepoint/modern-experience-performance)

[Performance guidance for SharePoint Online portals](/sharepoint/dev/solution-guidance/portal-performance) (Guía de rendimiento para los portales de SharePoint Online)
