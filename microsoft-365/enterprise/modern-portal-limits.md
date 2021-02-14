---
title: Límites del sitio del portal moderno de SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/9/2019
audience: Admin
ms.topic: interactive-tutorial
ms.service: o365-administration
localization_priority: Normal
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
description: Obtenga información sobre las recomendaciones de rendimiento para sitios modernos en SharePoint Online, como la limitación de llamadas a SharePoint y extremos externos.
ms.openlocfilehash: 2afca20183bef8c8f6dda9bdc35a44e5153ef07c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694078"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>Límites del sitio del portal moderno de SharePoint Online

En este artículo se proporcionan recomendaciones de rendimiento para sitios de portal modernos en SharePoint Online. Use las directrices de este artículo para optimizar el rendimiento del sitio del portal moderno y evitar problemas comunes de rendimiento.

## <a name="performance-considerations-for-modern-portal-sites"></a>Consideraciones de rendimiento para sitios de portal modernos

Desde el punto de vista de la optimización del rendimiento, hay algunas características que hacen que los sitios de portal modernos sean únicos. La principal diferencia entre la colaboración y los sitios del portal en SharePoint Online es la escala. Por lo general, se espera que los sitios del portal sirvan más vistas de página a un mayor número de usuarios que sitios de colaboración y es probable que contengan más contenido estático y menos recursos editables. Además, la arquitectura de los sitios modernos difiere de los sitios clásicos en que la mayor parte del procesamiento implicado en la representación de páginas y la ejecución de código tiene lugar en el cliente en lugar del servidor.

La optimización del rendimiento para los sitios de portal modernos se centra principalmente en algunos objetivos generales:

- Reducir el tamaño total de los componentes de cada página de sitio
- Descargar el hospedaje de archivos estáticos comunes como imágenes, hojas de estilo y scripts en la red CDN
- Limitar las llamadas a SharePoint y los extremos externos solo a lo necesario
- Evitar solicitudes duplicadas para el mismo contenido

Muchas de las directrices de este artículo se centran en minimizar y optimizar las llamadas a SharePoint Online. Realizar llamadas repetitivas cada vez que se carga una página afectará al rendimiento de los usuarios, ya que la información se recuperará del servicio cada vez, aunque no haya cambiado. Como tal, las solicitudes a SharePoint se pueden clasificar como llamadas comunes para todos los usuarios o llamadas necesarias para cada usuario individual. Los resultados de estas dos categorías de llamada deben almacenarse en caché para optimizar la experiencia del usuario.

>[!NOTE]
>Use la [herramienta Diagnóstico de páginas para SharePoint](https://aka.ms/perftool) como punto de partida para analizar métricas de rendimiento específicas en las páginas del sitio de SharePoint Online.

## <a name="modern-portal-site-limits-and-recommendations"></a>Recomendaciones y límites del sitio del portal moderno

|**Límite**|**Valor máximo recomendado**|**Notas**|
|:-----|:-----|:-----|:-----|
|Páginas y elementos de noticias  <br/> |5.000 por sitio  <br/> |Se recomienda limitar el número de páginas y elementos de noticias en un sitio de portal moderno a menos de 5.000.  <br/> |
|Elementos web de una página  <br/> |20 por página  <br/> |Se recomienda usar 20 o menos elementos web totales por página, incluidos los elementos web de Microsoft personalizados y los elementos web personalizados. <br/> Para obtener más información, vea [Optimizar el rendimiento del elemento web en las páginas de sitio modernas de SharePoint Online.](modern-web-part-optimization.md)  <br/> |
|Elementos web dinámicos en una página  <br/> |4 por página  <br/> |Los elementos web dinámicos que hacen una o más consultas a SharePoint para capturar los datos más recientes deben limitarse a 4 por página. El _elemento_ web Noticias es un ejemplo de un elemento web dinámico. <br/> Para obtener más información, vea [Optimizar el rendimiento del elemento web en las páginas de sitio modernas de SharePoint Online.](modern-web-part-optimization.md)    <br/> |
|Grupos de seguridad  <br/> |20 por sitio  <br/> |El número de grupos de seguridad afecta a la escala de muchas consultas en sitios de portal modernos. Se recomienda limitar el número de grupos de seguridad a un conjunto lo más pequeño posible, sin más de 20 por sitio.  <br/> |
|Elementos en la navegación del sitio  <br/> |100 por sitio  <br/> |Se recomienda agregar menos de 100 elementos a la navegación del sitio y usar los controles de navegación personalizados.  <br/> Para obtener más información, vea [Optimizar el peso de la página en las páginas de sitio modernas de SharePoint Online.](modern-page-weight-optimization.md) <br/> |
|Tamaño máximo de imagen  <br/> |300 Kb por imagen  <br/> |Se recomienda limitar el tamaño de las imágenes a 300 kb o más pequeños y usar una red CDN para hospedar imágenes, hojas de estilo y scripts. <br/>Para obtener más información, vea Optimizar imágenes en páginas de sitio modernas de [SharePoint Online](modern-image-optimization.md) y Usar la red de entrega de contenido [(CDN) de Office 365 con SharePoint Online.](use-microsoft-365-cdn-with-spo.md)  <br/> |
|Usuarios con derechos de edición  <br/> |200 usuarios por sitio  <br/> |Los sitios del portal de SharePoint están optimizados para ver y consumir contenido. Los permisos de edición en un portal deben limitarse a un grupo restringido de usuarios porque los permisos de edición descargan controles adicionales y, por lo tanto, tendrán un rendimiento más lento para esos usuarios. Por lo tanto, un número excesivo de usuarios con permisos de edición afectará a la experiencia general. <br/> |
|IFrames de terceros  <br/> |2 por página  <br/> |Los iFrames son impredeciblemente lentos porque cargan una página externa independiente, incluido todo el contenido asociado, como javascript, CSS y elementos de marco. Si debes usar iFrames, limita su número a 2 o menos por página.<br/> Para obtener más información, vea Optimizar iFrames en páginas de sitio de publicación modernas y [clásicas de SharePoint Online.](modern-iframe-optimization.md) <br/> |
|Llamadas al servicio UPA  <br/> |1 por usuario y hora  <br/> |Se recomienda no realizar llamadas _por_ solicitud al servicio UPA (aplicación de perfil de usuario). La [API de Microsoft Graph](https://docs.microsoft.com/graph/call-api) y [PageContext](https://docs.microsoft.com/javascript/api/sp-page-context/pagecontext?view=sp-typescript-latest) se pueden usar para consultar información de usuario.  <br/> Si es necesaria una llamada de servicio UPA, realice una sola llamada cuando sea necesario y, a continuación, almacenar en caché la información para reutilizarla en la misma sesión. |
|Llamadas al servicio de taxonomía  <br/> |5 por usuario y hora  <br/> |Se recomienda no realizar llamadas _por solicitud_ al servicio de taxonomía. Si las llamadas de servicio de taxonomía son necesarias, almacenar en caché la información para reutilizarla en la misma sesión. <br/> Para obtener más información, vea Optimizar las llamadas de página en las páginas de sitio de publicación modernas y clásicas [de SharePoint Online.](modern-page-call-optimization.md) <br/> |

## <a name="related-topics"></a>Temas relacionados

[Creación de un portal de SharePoint en buen estado](https://docs.microsoft.com/sharepoint/portal-health)

[Ajustar el rendimiento de SharePoint Online](tune-sharepoint-online-performance.md)

[Ajustar el rendimiento de Office 365](tune-microsoft-365-performance.md)

[SharePoint Online limits](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) (Límites de SharePoint Online)

[Rendimiento en la experiencia moderna de SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Performance guidance for SharePoint Online portals](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-performance) (Guía de rendimiento para los portales de SharePoint Online)
