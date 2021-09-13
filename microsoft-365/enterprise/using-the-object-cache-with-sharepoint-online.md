---
title: Usar la memoria caché de objetos con SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 38bc9c14-3826-449c-beb6-b1003bcbeaaf
description: En este artículo se explica la diferencia entre usar la memoria caché de objetos en SharePoint Server 2013 local y SharePoint Online.
ms.openlocfilehash: 40863ccf375620cf4b38d231fa0a86336c4826cc
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210420"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a>Usar la memoria caché de objetos con SharePoint Online

En este artículo se explica la diferencia entre usar la memoria caché de objetos en SharePoint Server 2013 local y SharePoint Online.
  
Hay un impacto negativo significativo de confiar en la memoria caché de objetos en SharePoint implementación en línea. Cualquier dependencia de la memoria caché de objetos en SharePoint Online reducirá la confiabilidad de la página. 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a>Cómo funciona SharePoint caché de objetos SharePoint Server 2013

Cuando SharePoint Server 2013 se hospeda localmente, el cliente tiene servidores front-end web privados que hospedan la memoria caché de objetos. Esto significa que la memoria caché está dedicada a un cliente y solo está limitada por la cantidad de memoria disponible y asignada a la memoria caché de objetos. Dado que solo se sirve a un cliente en el escenario local, los servidores front-end web suelen tener usuarios que hacen solicitudes a los mismos sitios una y otra vez. Esto significa que la memoria caché se completa rápidamente y permanece llena de los resultados de la consulta de lista y SharePoint objetos que los usuarios están solicitando periódicamente.
  
![Muestra el tráfico y la carga en servidores front-end web locales.](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
Como resultado, la segunda vez que un usuario visita una página, el tiempo de carga de la página mejora. Después de un mínimo de cuatro cargas de la misma página, la página se almacena en caché en todos los servidores front-end web.
  
En cambio, en SharePoint Online hay muchos más servidores, pero también muchos más sitios. Cada usuario puede conectarse a un servidor front-end web diferente que no tenga la memoria caché rellenada. O bien, quizás la memoria caché se llene para un servidor, pero el siguiente usuario de ese servidor front-end web solicita una página de un sitio diferente. O bien, incluso si el siguiente usuario solicita la misma página que en su visita anterior, se equilibra la carga en un servidor front-end web diferente que no tenga esa página en la memoria caché. En este último caso, el almacenamiento en caché no ayuda en absoluto a los usuarios.
  
En la siguiente figura, cada punto representa una página que un usuario está solicitando y donde se almacena en caché. Diferentes colores representan a diferentes clientes que hacen uso compartido de la infraestructura SaaS.
  
![Muestra los resultados del almacenamiento en caché de objetos en SharePoint Online.](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
Como puede ver en el diagrama, las posibilidades de que un usuario determinado golpee a un servidor con la versión almacenada en caché de su página son escasas. Además, debido al gran rendimiento y al hecho de que los servidores se comparten entre muchos sitios, la memoria caché no dura mucho, ya que solo hay tanto espacio disponible para el almacenamiento en caché.
  
Por todas estas razones, confiar en los usuarios que tienen objetos almacenados en caché no es una forma eficaz de garantizar una experiencia de usuario de calidad y tiempos de carga de página en SharePoint Online.
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a>Si no podemos confiar en la memoria caché de objetos para mejorar el rendimiento en SharePoint Online, ¿qué usamos en su lugar?

Dado que no debe confiar en el almacenamiento en caché en SharePoint Online, debe evaluar métodos de diseño alternativos para SharePoint personalizaciones que usan la memoria caché de objetos. Esto significa usar métodos para problemas de rendimiento que no se basan en el almacenamiento en caché de objetos con el fin de producir buenos resultados para los usuarios. Esto se describe en algunos de los otros artículos de esta serie e incluyen:
  
- [Opciones de navegación para SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Minificación y agrupación en SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [Uso de la red de entrega de contenido (CDN) de Office 365 con SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Retrasar la carga de imágenes y JavaScript en SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

