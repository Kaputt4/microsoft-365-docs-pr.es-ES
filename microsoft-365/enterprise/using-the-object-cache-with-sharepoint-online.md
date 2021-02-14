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
ms.openlocfilehash: 279d156a941aad6fbe7adbcf052c57f5b58c652f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696605"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a><span data-ttu-id="264e8-103">Usar la memoria caché de objetos con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="264e8-103">Using the object cache with SharePoint Online</span></span>

<span data-ttu-id="264e8-104">En este artículo se explica la diferencia entre usar la memoria caché de objetos en SharePoint Server 2013 local y SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="264e8-104">This article explains the difference between using the object cache in SharePoint Server 2013 on-premises and SharePoint Online.</span></span>
  
<span data-ttu-id="264e8-105">El uso de la memoria caché de objetos en la implementación de SharePoint Online tiene un impacto negativo significativo.</span><span class="sxs-lookup"><span data-stu-id="264e8-105">There is significant negative impact of relying on the object cache in SharePoint Online deployment.</span></span> <span data-ttu-id="264e8-106">Cualquier dependencia de la memoria caché de objetos en SharePoint Online reducirá la confiabilidad de la página.</span><span class="sxs-lookup"><span data-stu-id="264e8-106">Any dependency on object cache in SharePoint Online will reduce the reliability of your page.</span></span> 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a><span data-ttu-id="264e8-107">Cómo funciona la memoria caché de objetos de SharePoint Online y SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="264e8-107">How the SharePoint Online and SharePoint Server 2013 object cache works</span></span>

<span data-ttu-id="264e8-108">Cuando SharePoint Server 2013 se hospeda localmente, el cliente tiene servidores front-end web privados que hospedan la memoria caché de objetos.</span><span class="sxs-lookup"><span data-stu-id="264e8-108">When SharePoint Server 2013 is hosted on-premises, the customer has private front-end web servers that host the object cache.</span></span> <span data-ttu-id="264e8-109">Esto significa que la memoria caché está dedicada a un cliente y solo está limitada por la cantidad de memoria disponible y asignada a la memoria caché de objetos.</span><span class="sxs-lookup"><span data-stu-id="264e8-109">This means the cache is dedicated to one customer and is only limited by how much memory is available and allocated to the object cache.</span></span> <span data-ttu-id="264e8-110">Dado que solo se sirve a un cliente en el escenario local, los servidores front-end web suelen tener usuarios que hacen solicitudes a los mismos sitios una y otra vez.</span><span class="sxs-lookup"><span data-stu-id="264e8-110">Because only one customer is served in the on-premises scenario the front-end web servers typically have users making requests to the same sites over and over.</span></span> <span data-ttu-id="264e8-111">Esto significa que la memoria caché se llena rápidamente y permanece llena de los resultados de la consulta de lista y los objetos de SharePoint que los usuarios solicitan periódicamente.</span><span class="sxs-lookup"><span data-stu-id="264e8-111">This means that the cache gets full quickly and remains full of the list query results and SharePoint objects that your users are requesting on a regular basis.</span></span>
  
![Muestra el tráfico y la carga a los servidores locales front-end web](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
<span data-ttu-id="264e8-113">Como resultado, la segunda vez que un usuario visita una página, el tiempo de carga de la página mejora.</span><span class="sxs-lookup"><span data-stu-id="264e8-113">As a result, the second time a user visits a page, the page load time improves.</span></span> <span data-ttu-id="264e8-114">Después de un mínimo de cuatro cargas de la misma página, la página se almacena en caché en todos los servidores front-end web.</span><span class="sxs-lookup"><span data-stu-id="264e8-114">After a minimum of four loads of the same page, the page is cached on all of the front-end web servers.</span></span>
  
<span data-ttu-id="264e8-115">Por el contrario, en SharePoint Online hay muchos más servidores, pero también muchos más sitios.</span><span class="sxs-lookup"><span data-stu-id="264e8-115">In contrast, in SharePoint Online there are many more servers but also many more sites.</span></span> <span data-ttu-id="264e8-116">Cada usuario puede conectarse a un servidor front-end web diferente que no tiene la memoria caché rellenada.</span><span class="sxs-lookup"><span data-stu-id="264e8-116">Each user may connect to a different front-end web server that doesn't have the cache populated.</span></span> <span data-ttu-id="264e8-117">O bien, quizás la memoria caché se llene para un servidor, pero el siguiente usuario del servidor front-end web solicita una página de un sitio diferente.</span><span class="sxs-lookup"><span data-stu-id="264e8-117">Or, perhaps the cache does get populated for a server, but the next user to that front-end web server requests a page from a different site.</span></span> <span data-ttu-id="264e8-118">O bien, incluso si el siguiente usuario solicita la misma página que en su visita anterior, se equilibra la carga con un servidor front-end web diferente que no tiene esa página en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="264e8-118">Or, even if the next user requests the same page as on their previous visit, they are load-balanced to a different front-end web server that doesn't have that page in its cache.</span></span> <span data-ttu-id="264e8-119">En este último caso, el almacenamiento en caché no ayuda en absoluto a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="264e8-119">In this last case, caching doesn't help the users at all.</span></span>
  
<span data-ttu-id="264e8-120">En la figura siguiente, cada punto representa una página que un usuario solicita y donde se almacena en caché.</span><span class="sxs-lookup"><span data-stu-id="264e8-120">In the following figure, each dot represents a page that a user is requesting and where it cached.</span></span> <span data-ttu-id="264e8-121">Los distintos colores representan a diferentes clientes que hacen uso compartido de la infraestructura SaaS.</span><span class="sxs-lookup"><span data-stu-id="264e8-121">Different colors represent different customers making shared use of the SaaS infrastructure.</span></span>
  
![Muestra los resultados de almacenamiento en memoria caché de objetos en SharePoint Online](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
<span data-ttu-id="264e8-123">Como puede ver en el diagrama, las posibilidades de que un usuario determinado entre en un servidor con la versión almacenada en caché de su página son muy pocas.</span><span class="sxs-lookup"><span data-stu-id="264e8-123">As you can see from the diagram, the chances of any given user hitting a server with the cached version of their page are slim.</span></span> <span data-ttu-id="264e8-124">Además, debido al gran rendimiento y al hecho de que los servidores se comparten entre muchos sitios, la memoria caché no dura mucho tiempo, ya que solo hay tanto espacio disponible para el almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="264e8-124">Also, due to the large throughput and fact that the servers are shared between many sites, the cache doesn't last long since there is only so much space for caching available.</span></span>
  
<span data-ttu-id="264e8-125">Por todas estas razones, confiar en los usuarios que se almacenan en caché objetos no es una forma eficaz de garantizar una experiencia de usuario de calidad y tiempos de carga de página en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="264e8-125">For all of these reasons, relying on users getting cached objects is not an effective way to ensure a quality user experience and page load times in SharePoint Online.</span></span>
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a><span data-ttu-id="264e8-126">Si no podemos confiar en la memoria caché de objetos para mejorar el rendimiento en SharePoint Online, ¿qué usamos en su lugar?</span><span class="sxs-lookup"><span data-stu-id="264e8-126">If we can't rely on the object cache to improve performance in SharePoint Online, what do we use instead?</span></span>

<span data-ttu-id="264e8-127">Dado que no debe confiar en el almacenamiento en caché en SharePoint Online, debe evaluar métodos de diseño alternativos para las personalizaciones de SharePoint que usan la memoria caché de objetos.</span><span class="sxs-lookup"><span data-stu-id="264e8-127">Since you shouldn't rely on caching in SharePoint Online, you should evaluate alternative design approaches for SharePoint customizations that use the object cache.</span></span> <span data-ttu-id="264e8-128">Esto significa usar enfoques para problemas de rendimiento que no se basan en el almacenamiento en caché de objetos para producir buenos resultados para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="264e8-128">This means using approaches for performance issues which do not rely on the object caching in order to produce good results for users.</span></span> <span data-ttu-id="264e8-129">Esto se describe en algunos de los otros artículos de esta serie e incluyen:</span><span class="sxs-lookup"><span data-stu-id="264e8-129">This is described in some of the other articles in this series and include:</span></span>
  
- [<span data-ttu-id="264e8-130">Opciones de navegación para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="264e8-130">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="264e8-131">Minificación y agrupación en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="264e8-131">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="264e8-132">Uso de la red de entrega de contenido (CDN) de Office 365 con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="264e8-132">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="264e8-133">Retrasar la carga de imágenes y JavaScript en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="264e8-133">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

