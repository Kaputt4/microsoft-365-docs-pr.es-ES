---
title: Introducción al ajuste del rendimiento para SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: En este artículo se explican los aspectos específicos que debe tener en cuenta al diseñar páginas para obtener el mejor rendimiento en SharePoint Online.
ms.openlocfilehash: b31696766d3201b6677bf0c63108fad72c3ed49d
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65100751"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a>Introducción al ajuste del rendimiento para SharePoint Online

En este artículo se explican los aspectos específicos que debe tener en cuenta al diseñar páginas para obtener el mejor rendimiento en SharePoint Online.
     
## <a name="sharepoint-online-metrics"></a>métricas de SharePoint Online

Las siguientes métricas generales para SharePoint Online proporcionan datos reales sobre el rendimiento:
  
- Velocidad de carga de las páginas
    
- Número de recorridos de ida y vuelta necesarios por página
    
- Problemas con el servicio
    
- Otras cosas que provocan la degradación del rendimiento
    
### <a name="conclusions-reached-because-of-the-data"></a>Conclusiones alcanzadas debido a los datos

Los datos nos indican:
  
- La mayoría de las páginas funcionan bien en SharePoint Online.
    
- Las páginas no personalizadas se cargan rápidamente.
    
- OneDrive para la Empresa, los sitios de equipo y las páginas del sistema, como _layouts, etc., son rápidos de cargar.
    
- El 1 % más lento de SharePoint páginas en línea tarda más de 5000 milisegundos en cargarse.
    
Una prueba comparativa sencilla que puede usar sería medir el rendimiento comparando el tiempo de carga de su propio portal con el tiempo de carga de la página principal de OneDrive para la Empresa, ya que usa algunas características personalizadas. A menudo, este será el primer paso que el soporte técnico le pedirá que complete al solucionar problemas de rendimiento de red.
  
## <a name="use-a-standard-user-account-when-checking-performance"></a>Uso de una cuenta de usuario estándar al comprobar el rendimiento

Un administrador de la colección de sitios, un propietario del sitio, un editor o un colaborador pertenecen a otros grupos de seguridad, tienen más permisos y, por tanto, tienen elementos adicionales que SharePoint cargan en una página.
  
Esto es aplicable a SharePoint local y SharePoint En línea, pero en un escenario local las diferencias no se notarán tan fácilmente como en SharePoint Online.
  
Para evaluar correctamente cómo funcionará una página para los usuarios, debe usar una cuenta de usuario estándar para evitar cargar los controles de creación y el tráfico adicional relacionado con los grupos de seguridad.
  
## <a name="connection-categories-for-performance-tuning"></a>Categorías de conexión para el ajuste del rendimiento

Puede clasificar las conexiones entre el servidor y el usuario en tres componentes principales. Tenga en cuenta esto al diseñar SharePoint páginas en línea para obtener información sobre los tiempos de carga.
  
- **Servidor** Servidores que Microsoft hospeda en centros de datos.
    
- **Red** La red de Microsoft, Internet y la red local entre el centro de datos y los usuarios.
    
- **Explorador** Dónde se carga la página.
    
Dentro de estas tres conexiones, normalmente hay cinco motivos que provocan el 95 % de las páginas lentas. Cada una de estas razones se describe en este artículo:
  
- Problemas de navegación
    
- Sustitución de contenido
    
- Archivos grandes
    
- Muchas solicitudes al servidor
    
- Procesamiento de elementos web
    
### <a name="server-connection"></a>Conexión del servidor

Muchos de los problemas que afectan al rendimiento con SharePoint locales también se aplican a SharePoint Online.
  
Como cabría esperar, tiene mucho más control sobre cómo funcionan los servidores con SharePoint locales. Con SharePoint las cosas en línea son un poco diferentes. Cuanto más trabajo realice un servidor, más tiempo se tarda en representar una página. Con SharePoint, los principales culpables en este sentido son páginas complejas con varios elementos web.
  
SharePoint Server local
  
![Captura de pantalla del servidor local.](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
SharePoint Online
  
![Captura de pantalla del servidor en línea.](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
Con SharePoint Online, es posible que algunas solicitudes de página terminen llamando a varios servidores. Podría terminar con una matriz de solicitudes entre servidores para una solicitud individual. Estas interacciones son costosas desde la perspectiva de la carga de páginas y harán que las cosas sean lentas.
  
Algunos ejemplos de estas interacciones de servidor a servidor son:
  
- Servidores web a SQL
    
- Web a servidores de aplicaciones
    
La otra cosa que puede ralentizar las interacciones del servidor son las faltas de caché. A diferencia de los SharePoint locales, existe una pequeña posibilidad de que llegue al mismo servidor para una página que ha visitado anteriormente; esto hace que el almacenamiento en caché de objetos esté obsoleto.
  
### <a name="network-connection"></a>Conexión de red 

Con SharePoint locales que no usan una WAN, puede usar una conexión de alta velocidad entre el centro de datos y los usuarios finales. Por lo general, las cosas son fáciles de administrar desde la perspectiva de la red.
  
Con SharePoint Online, hay algunos factores más a tener en cuenta; por ejemplo:
  
- La red de Microsoft
    
- The Internet
    
- El ISP
    
Independientemente de la versión de SharePoint (y de la red) que use, entre los elementos que normalmente harán que la red esté ocupada se incluyen:
  
- Carga útil grande
    
- Muchos archivos
    
- Gran distancia física al servidor
    
Una característica que puede usar en SharePoint Online es microsoft CDN (Content Delivery Network). Un CDN es básicamente una colección distribuida de servidores implementados en varios centros de datos. Con un CDN, el contenido de las páginas se puede hospedar en un servidor cercano al cliente, incluso si el cliente está lejos del servidor de SharePoint de origen. Microsoft lo usará más en el futuro para almacenar instancias locales de páginas que no se pueden personalizar, por ejemplo, la página principal del administrador en línea de SharePoint. Para obtener más información sobre las redes CDN, consulte [Redes de entrega de contenido](content-delivery-networks.md).
  
Algo que debe tener en cuenta, pero que puede que no pueda hacer mucho, es la velocidad de conexión de su ISP. Una sencilla herramienta de prueba de velocidad le indicará la velocidad de conexión.
  
### <a name="browser-connection"></a>Conexión del explorador

Hay algunos factores que se deben tener en cuenta con los exploradores web desde una perspectiva de rendimiento.
  
Visitar páginas complejas afectará al rendimiento. La mayoría de los exploradores solo tienen una caché pequeña (alrededor de 90 MB), mientras que la página web promedio suele ser de aproximadamente 1,6 MB. Esto no tarda mucho en acostumbrarse.
  
El ancho de banda también puede ser un problema. Por ejemplo, si un usuario está viendo vídeos en otra sesión, esto afectará al rendimiento de la página de SharePoint. Aunque no puede impedir que los usuarios transmita contenido multimedia, puede controlar la forma en que se cargará una página para los usuarios.
  
Consulte los artículos siguientes para obtener diferentes técnicas de personalización de páginas en línea SharePoint y otros procedimientos recomendados para ayudarle a lograr un rendimiento óptimo.
  
- [Opciones de navegación para SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Uso de la herramienta Diagnóstico de página para SharePoint Online](page-diagnostics-for-spo.md)
    
- [Optimización de imágenes para SharePoint Online](image-optimization-for-sharepoint-online.md)
    
- [Retrasar la carga de imágenes y JavaScript en SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [Minificación y agrupación en SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [Uso de la red de entrega de contenido (CDN) de Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Uso del elemento web búsqueda de contenido en lugar del elemento web de consulta de contenido para mejorar el rendimiento en SharePoint Online](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [Planeamiento de capacidad y pruebas de carga en SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [Diagnosticar problemas de rendimiento con SharePoint Online](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [Usar la memoria caché de objetos con SharePoint Online](using-the-object-cache-with-sharepoint-online.md)
    
- [Cómo: Evitar estar limitado o bloqueado en SharePoint Online](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
