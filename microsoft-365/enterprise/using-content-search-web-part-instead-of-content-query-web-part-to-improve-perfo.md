---
title: Uso del elemento web Búsqueda de contenido en lugar del elemento web Consulta de contenido para mejorar el rendimiento en SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: e8ce6b72-745b-464a-85c7-cbf6eb53391b
description: Aprenda a aumentar el rendimiento reemplazando el elemento web Consulta de contenido por el elemento web búsqueda de contenido en SharePoint Server 2013 y SharePoint Online.
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694225"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a>Uso del elemento web Búsqueda de contenido en lugar del elemento web Consulta de contenido para mejorar el rendimiento en SharePoint Online

En este artículo se describe cómo aumentar el rendimiento reemplazando el elemento web Consulta de contenido por el elemento web búsqueda de contenido en SharePoint Server 2013 y SharePoint Online.
  
Una de las características nuevas más eficaces de SharePoint Server 2013 y SharePoint Online es el elemento web de búsqueda de contenido (CSWP). Este elemento web usa el índice de búsqueda para recuperar rápidamente los resultados que se muestran al usuario. Use el elemento web búsqueda de contenido en lugar del elemento web consulta de contenido (CQWP) en las páginas para mejorar el rendimiento de los usuarios.
  
El uso de un elemento web de búsqueda de contenido en un elemento web consulta de contenido casi siempre dará como resultado un rendimiento de carga de página significativamente mejor en SharePoint Online. Hay una pequeña configuración adicional para obtener la consulta correcta, pero las recompensas son un rendimiento mejorado y usuarios más contentos.
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a>Comparar la mejora de rendimiento que obtiene al usar el elemento web búsqueda de contenido en lugar del elemento web Consulta de contenido

En los ejemplos siguientes se muestran las mejoras de rendimiento relativas que puede recibir al usar un elemento web de búsqueda de contenido en lugar de un elemento web consulta de contenido. Los efectos son más evidentes con una estructura de sitio compleja y consultas de contenido muy amplias.
  
Este sitio de ejemplo tiene las siguientes características:
  
- 8 niveles de subsitios.
    
- Enumera el uso de un tipo de contenido personalizado "fruit".
    
- En el elemento web, la consulta de contenido es amplia y devuelve todos los elementos con el tipo de contenido "fruit".
    
- El ejemplo solo usa 50 elementos en los 8 sitios. Los efectos serán aún más pronunciados para los sitios con más contenido.
    
A continuación se muestra una captura de pantalla de los resultados del elemento web Consulta de contenido.
  
![Gráfico que muestra la consulta de contenido del elemento web](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
En Internet Explorer, usa la pestaña **Red** de las herramientas de desarrollo F12 para ver los detalles del encabezado de respuesta. En la siguiente captura de pantalla, el valor de **SPRequestDuration** para esta carga de página es de 924 milisegundos. 
  
![Captura de pantalla que muestra la duración de la solicitud de 924](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 **SPRequestDuration** indica la cantidad de trabajo que se realiza en el servidor para preparar la página. Cambiar el contenido por consulta elementos web contenido por búsqueda elementos web reduce considerablemente el tiempo necesario para representar la página. Por el contrario, una página con un elemento web de búsqueda de contenido equivalente que devuelve el mismo número de resultados tiene un valor **SPRequestDuration** de 106 milisegundos, como se muestra en esta captura de pantalla: 
  
![Captura de pantalla que muestra la duración de la solicitud de 106](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a>Adición de un elemento web de búsqueda de contenido en SharePoint Online

Agregar un elemento web de búsqueda de contenido es muy similar a un elemento web de consulta de contenido normal. Vea la sección  *"Agregar un elemento web*  de búsqueda de contenido" en Configurar un elemento web de búsqueda de contenido en [SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a>Creación de la consulta de búsqueda correcta para el elemento web de búsqueda de contenido

Una vez que haya agregado un elemento web de búsqueda de contenido, puede refinar la búsqueda y devolver los elementos que desee. Para obtener instrucciones detalladas sobre cómo hacerlo, vea la sección "Mostrar contenido mediante la configuración de una consulta avanzada en un elemento web de búsqueda de  *contenido"*  en Configurar un elemento web de búsqueda de contenido en [SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).
  
## <a name="query-building-and-testing-tool"></a>Herramienta de creación y pruebas de consultas

Para obtener una herramienta para crear y probar consultas complejas, vea [la herramienta de consulta de búsqueda](https://sp2013searchtool.codeplex.com/) en Codeplex. 
  

