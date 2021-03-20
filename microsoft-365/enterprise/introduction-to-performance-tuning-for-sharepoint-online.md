---
title: Introducción al ajuste del rendimiento para SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: En este artículo se explican los aspectos específicos que debe tener en cuenta al diseñar páginas para obtener el mejor rendimiento en SharePoint Online.
ms.openlocfilehash: 6f40243c9d6a1657b6716a071288f5b4fb018164
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909743"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a>Introducción al ajuste del rendimiento para SharePoint Online

En este artículo se explican los aspectos específicos que debe tener en cuenta al diseñar páginas para obtener el mejor rendimiento en SharePoint Online.
     
## <a name="sharepoint-online-metrics"></a>Métricas de SharePoint Online

Las siguientes métricas generales para SharePoint Online proporcionan datos reales sobre el rendimiento:
  
- Cómo se cargan las páginas rápidas
    
- Número de viajes de ida y vuelta necesarios por página
    
- Problemas con el servicio
    
- Otras cosas que causan degradación del rendimiento
    
### <a name="conclusions-reached-because-of-the-data"></a>Conclusiones alcanzadas debido a los datos

Los datos nos dicen:
  
- La mayoría de las páginas tienen un buen rendimiento en SharePoint Online.
    
- Las páginas no personalizadas se cargan muy rápidamente.
    
- OneDrive para la Empresa, los sitios de grupo y las páginas del sistema, como _layouts, etc., se cargan rápidamente.
    
- El 1% más lento de las páginas de SharePoint Online tarda más de 5.000 milisegundos en cargarse.
    
Una prueba comparativa sencilla que puede usar sería medir el rendimiento comparando el tiempo de carga de su propio portal con el tiempo de carga de la página principal de OneDrive para la Empresa, ya que usa pocas características personalizadas. Este suele ser el primer paso que el soporte técnico le pedirá que complete al solucionar problemas de rendimiento de red.
  
## <a name="use-a-standard-user-account-when-checking-performance"></a>Usar una cuenta de usuario estándar al comprobar el rendimiento

Un administrador de la colección de sitios, el propietario del sitio, el editor o el colaborador pertenecen a grupos de seguridad adicionales, tienen permisos adicionales y, por lo tanto, tienen elementos adicionales que SharePoint carga en una página.
  
Esto es aplicable a SharePoint local y SharePoint Online, pero en un escenario local las diferencias no se notan tan fácilmente como en SharePoint Online.
  
Para evaluar correctamente el rendimiento de una página para los usuarios, debe usar una cuenta de usuario estándar para evitar cargar los controles de creación y el tráfico adicional relacionado con los grupos de seguridad.
  
## <a name="connection-categories-for-performance-tuning"></a>Categorías de conexión para ajustar el rendimiento

Puede clasificar las conexiones entre el servidor y el usuario en tres componentes principales. Tenga en cuenta esto al diseñar páginas de SharePoint Online para obtener información sobre los tiempos de carga.
  
- **Servidor** Los servidores que Microsoft hospeda en centros de datos.
    
- **Red** La red de Microsoft, Internet y la red local entre el centro de datos y los usuarios.
    
- **Explorador** Donde se carga la página.
    
Dentro de estas tres conexiones normalmente hay cinco motivos que causan el 95 % de las páginas lentas. Cada uno de estos motivos se describe en este artículo:
  
- Problemas de navegación
    
- Lanzamiento de contenido
    
- Archivos grandes
    
- Muchas solicitudes al servidor
    
- Procesamiento de elementos web
    
### <a name="server-connection"></a>Conexión de servidor

Muchos de los problemas que afectan al rendimiento con SharePoint local también se aplican a SharePoint Online.
  
Como era de esperar, tiene mucho más control sobre el rendimiento de los servidores con SharePoint local. Con SharePoint Online, las cosas son un poco diferentes. Cuanto más trabajo realice un servidor, más tiempo se tarda en representar una página. Con SharePoint, el mayor responsable en este sentido son páginas complejas con varios elementos web.
  
SharePoint Server local
  
![Captura de pantalla del servidor local](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
SharePoint en linea
  
![Captura de pantalla del servidor en línea](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
Con SharePoint Online, ciertas solicitudes de página pueden terminar llamando a varios servidores. Podría terminar con una matriz de solicitudes entre servidores para una solicitud individual. Estas interacciones son costosas desde una perspectiva de carga de página y ralentizarán las cosas.
  
Algunos ejemplos de estas interacciones de servidor a servidor son:
  
- Servidores web SQL web
    
- Servidores de aplicaciones web a
    
La otra cosa que puede ralentizar las interacciones del servidor son las pérdidas de caché. A diferencia de SharePoint local, existe una probabilidad muy pequeña de que se haga clic en el mismo servidor para una página que ha visitado anteriormente; esto hace que el almacenamiento en caché de objetos sea obsoleto.
  
### <a name="network-connection"></a>Conexión de red 

Con SharePoint local que no usa una WAN, puede usar una conexión de alta velocidad entre el centro de datos y los usuarios finales. Por lo general, las cosas son fáciles de administrar desde una perspectiva de red.
  
Con SharePoint Online, hay algunos factores más a tener en cuenta; por ejemplo:
  
- La red de Microsoft
    
- The Internet
    
- El ISP
    
Independientemente de la versión de SharePoint (y de la red) que esté usando, los aspectos que normalmente harán que la red esté ocupada incluyen:
  
- Carga de gran tamaño
    
- Muchos archivos
    
- Distancia física grande al servidor
    
Una característica que puede aprovechar en SharePoint Online es la red CDN de Microsoft (red de entrega de contenido). Una red CDN es básicamente una colección distribuida de servidores implementados en varios centros de datos. Con una red CDN, el contenido de las páginas se puede hospedar en un servidor cercano al cliente, incluso si el cliente está lejos del SharePoint Server de origen. Microsoft lo va a usar más en el futuro para almacenar instancias locales de páginas que no se pueden personalizar, por ejemplo, la página principal del administrador de SharePoint Online. Para obtener más información acerca de las CDN, vea [Redes de entrega de contenido](content-delivery-networks.md).
  
Algo que debe tener en cuenta pero que puede que no pueda hacer mucho es la velocidad de conexión de su ISP. Una herramienta de prueba de velocidad sencilla te dirá la velocidad de conexión.
  
### <a name="browser-connection"></a>Conexión del explorador

Hay algunos factores a tener en cuenta con los exploradores web desde una perspectiva de rendimiento.
  
Visitar páginas complejas afectará al rendimiento. La mayoría de los exploradores solo tienen una pequeña caché (alrededor de 90 MB), mientras que la página web promedio suele rondar los 1,6 MB. Esto no toma mucho tiempo para usarse.
  
El ancho de banda también puede ser un problema. Por ejemplo, si un usuario está viendo vídeos en otra sesión, esto afectará al rendimiento de la página de SharePoint. Aunque no puede impedir que los usuarios transmita contenido multimedia, puede controlar la forma en que se cargará una página para los usuarios.
  
Consulte los siguientes artículos para obtener distintas técnicas de personalización de páginas de SharePoint Online y otros procedimientos recomendados que le ayudarán a lograr un rendimiento óptimo.
  
- [Opciones de navegación para SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Usar la herramienta diagnóstico de página para SharePoint Online](page-diagnostics-for-spo.md)
    
- [Optimización de imágenes para SharePoint Online](image-optimization-for-sharepoint-online.md)
    
- [Retrasar la carga de imágenes y JavaScript en SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [Minificación y agrupación en SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [Uso de la red de entrega de contenido (CDN) de Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Uso del elemento web de búsqueda de contenido en lugar del elemento web consulta de contenido para mejorar el rendimiento en SharePoint Online](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [Planeamiento de capacidad y pruebas de carga en SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [Diagnosticar problemas de rendimiento con SharePoint Online](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [Usar la memoria caché de objetos con SharePoint Online](using-the-object-cache-with-sharepoint-online.md)
    
- [Cómo: Evitar estar limitado o bloqueado en SharePoint Online](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
