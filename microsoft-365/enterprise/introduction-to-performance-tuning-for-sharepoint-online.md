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
ms.openlocfilehash: d3a9dedbd5812774b81494af0f8defa5568f7dac
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694125"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a><span data-ttu-id="36f7a-103">Introducción al ajuste del rendimiento para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="36f7a-103">Introduction to performance tuning for SharePoint Online</span></span>

<span data-ttu-id="36f7a-104">En este artículo se explican los aspectos específicos que debe tener en cuenta al diseñar páginas para obtener el mejor rendimiento en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="36f7a-104">This article explains what specific aspects you need to consider when designing pages for best performance in SharePoint Online.</span></span>
     
## <a name="sharepoint-online-metrics"></a><span data-ttu-id="36f7a-105">Métricas de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="36f7a-105">SharePoint Online metrics</span></span>

<span data-ttu-id="36f7a-106">Las siguientes métricas generales para SharePoint Online proporcionan datos reales sobre el rendimiento:</span><span class="sxs-lookup"><span data-stu-id="36f7a-106">The following broad metrics for SharePoint Online provide real world data about performance:</span></span>
  
- <span data-ttu-id="36f7a-107">Cómo se cargan las páginas rápidamente</span><span class="sxs-lookup"><span data-stu-id="36f7a-107">How fast pages load</span></span>
    
- <span data-ttu-id="36f7a-108">Número de recorridos de ida y vuelta necesarios por página</span><span class="sxs-lookup"><span data-stu-id="36f7a-108">How many round trips required per page</span></span>
    
- <span data-ttu-id="36f7a-109">Problemas con el servicio</span><span class="sxs-lookup"><span data-stu-id="36f7a-109">Issues with the service</span></span>
    
- <span data-ttu-id="36f7a-110">Otras cosas que provocan una degradación del rendimiento</span><span class="sxs-lookup"><span data-stu-id="36f7a-110">Other things that cause performance degradation</span></span>
    
### <a name="conclusions-reached-because-of-the-data"></a><span data-ttu-id="36f7a-111">Conclusiones a las que se ha llegado debido a los datos</span><span class="sxs-lookup"><span data-stu-id="36f7a-111">Conclusions reached because of the data</span></span>

<span data-ttu-id="36f7a-112">Los datos nos dicen:</span><span class="sxs-lookup"><span data-stu-id="36f7a-112">The data tells us:</span></span>
  
- <span data-ttu-id="36f7a-113">La mayoría de las páginas tienen un buen rendimiento en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="36f7a-113">Most of the pages perform well on SharePoint Online.</span></span>
    
- <span data-ttu-id="36f7a-114">Las páginas no personalizadas se cargan muy rápidamente.</span><span class="sxs-lookup"><span data-stu-id="36f7a-114">Non-customized pages load very quickly.</span></span>
    
- <span data-ttu-id="36f7a-115">OneDrive para la Empresa, los sitios de grupo y las páginas del sistema, como _layouts, etc., se cargan rápidamente.</span><span class="sxs-lookup"><span data-stu-id="36f7a-115">OneDrive for Business, team sites and system pages, such as _layouts, etc., are all quick to load.</span></span>
    
- <span data-ttu-id="36f7a-116">El 1 % más lento de las páginas de SharePoint Online tarda más de 5.000 milisegundos en cargarse.</span><span class="sxs-lookup"><span data-stu-id="36f7a-116">The slowest 1% of SharePoint Online pages take more than 5,000 milliseconds to load.</span></span>
    
<span data-ttu-id="36f7a-117">Una prueba comparativa simple que puede usar sería medir el rendimiento comparando el tiempo de carga de su propio portal con el tiempo de carga de la página principal de OneDrive para la Empresa, ya que usa pocas características personalizadas.</span><span class="sxs-lookup"><span data-stu-id="36f7a-117">One simple benchmark test you can use would be to measure performance by comparing the load time of your own portal against the load time of the OneDrive for Business home page as it uses few customized features.</span></span> <span data-ttu-id="36f7a-118">Este suele ser el primer paso que el soporte técnico le pedirá que complete al solucionar problemas de rendimiento de la red.</span><span class="sxs-lookup"><span data-stu-id="36f7a-118">This will often be the first step Support will ask you to complete when troubleshooting network performance issues.</span></span>
  
## <a name="use-a-standard-user-account-when-checking-performance"></a><span data-ttu-id="36f7a-119">Usar una cuenta de usuario estándar al comprobar el rendimiento</span><span class="sxs-lookup"><span data-stu-id="36f7a-119">Use a standard user account when checking performance</span></span>

<span data-ttu-id="36f7a-120">Un administrador de la colección de sitios, el propietario del sitio, el editor o el colaborador pertenecen a grupos de seguridad adicionales, tienen permisos adicionales y, por lo tanto, tienen elementos adicionales que SharePoint carga en una página.</span><span class="sxs-lookup"><span data-stu-id="36f7a-120">A Site Collection Administrator, Site Owner, Editor, or Contributor belong to additional security groups, have additional permissions, and therefore have additional elements that SharePoint loads on a page.</span></span>
  
<span data-ttu-id="36f7a-121">Esto se aplica a SharePoint local y SharePoint Online, pero en un escenario local las diferencias no se notan tan fácilmente como en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="36f7a-121">This is applicable to SharePoint on-premises and SharePoint Online but in an on-premises scenario the differences will not be as easily noticed as in SharePoint Online.</span></span>
  
<span data-ttu-id="36f7a-122">Para evaluar correctamente el rendimiento de una página para los usuarios, debe usar una cuenta de usuario estándar para evitar cargar los controles de creación y el tráfico adicional relacionado con los grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="36f7a-122">In order to correctly evaluate how a page will perform for users, you should use a standard user account to avoid loading the authoring controls and additional traffic related to security groups.</span></span>
  
## <a name="connection-categories-for-performance-tuning"></a><span data-ttu-id="36f7a-123">Categorías de conexión para el ajuste del rendimiento</span><span class="sxs-lookup"><span data-stu-id="36f7a-123">Connection categories for performance tuning</span></span>

<span data-ttu-id="36f7a-124">Puede clasificar las conexiones entre el servidor y el usuario en tres componentes principales.</span><span class="sxs-lookup"><span data-stu-id="36f7a-124">You can categorize the connections between the server and the user into three main components.</span></span> <span data-ttu-id="36f7a-125">Tenga en cuenta esto al diseñar páginas de SharePoint Online para obtener información sobre los tiempos de carga.</span><span class="sxs-lookup"><span data-stu-id="36f7a-125">Consider these when designing SharePoint Online pages for insight into load times.</span></span>
  
- <span data-ttu-id="36f7a-126">**Servidor** Los servidores que Microsoft hospeda en centros de datos.</span><span class="sxs-lookup"><span data-stu-id="36f7a-126">**Server** The servers that Microsoft hosts in datacenters.</span></span>
    
- <span data-ttu-id="36f7a-127">**Red** La red de Microsoft, Internet y la red local entre el centro de datos y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="36f7a-127">**Network** The Microsoft network, the Internet, and your on-premises network between the datacenter and your users.</span></span>
    
- <span data-ttu-id="36f7a-128">**Explorador** Donde se carga la página.</span><span class="sxs-lookup"><span data-stu-id="36f7a-128">**Browser** Where the page is loaded.</span></span>
    
<span data-ttu-id="36f7a-129">Dentro de estas tres conexiones, normalmente hay cinco motivos que provocan el 95 % de las páginas lentas.</span><span class="sxs-lookup"><span data-stu-id="36f7a-129">Within these three connections there are typically five reasons that cause 95% of slow pages.</span></span> <span data-ttu-id="36f7a-130">Cada una de estas razones se describe en este artículo:</span><span class="sxs-lookup"><span data-stu-id="36f7a-130">Each of these reasons is discussed in this article:</span></span>
  
- <span data-ttu-id="36f7a-131">Problemas de navegación</span><span class="sxs-lookup"><span data-stu-id="36f7a-131">Navigation issues</span></span>
    
- <span data-ttu-id="36f7a-132">Succión de contenido</span><span class="sxs-lookup"><span data-stu-id="36f7a-132">Content roll up</span></span>
    
- <span data-ttu-id="36f7a-133">Archivos grandes</span><span class="sxs-lookup"><span data-stu-id="36f7a-133">Large files</span></span>
    
- <span data-ttu-id="36f7a-134">Muchas solicitudes al servidor</span><span class="sxs-lookup"><span data-stu-id="36f7a-134">Many requests to the server</span></span>
    
- <span data-ttu-id="36f7a-135">Procesamiento de elementos web</span><span class="sxs-lookup"><span data-stu-id="36f7a-135">Web Part processing</span></span>
    
### <a name="server-connection"></a><span data-ttu-id="36f7a-136">Conexión de servidor</span><span class="sxs-lookup"><span data-stu-id="36f7a-136">Server connection</span></span>

<span data-ttu-id="36f7a-137">Muchos de los problemas que afectan al rendimiento con SharePoint local también se aplican a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="36f7a-137">Many of the issues that affect performance with SharePoint on-premises also apply to SharePoint Online.</span></span>
  
<span data-ttu-id="36f7a-138">Como se esperaría, tiene mucho más control sobre el rendimiento de los servidores con SharePoint local.</span><span class="sxs-lookup"><span data-stu-id="36f7a-138">As you would expect, you have far more control over how servers perform with on-premises SharePoint.</span></span> <span data-ttu-id="36f7a-139">Con SharePoint Online, las cosas son un poco diferentes.</span><span class="sxs-lookup"><span data-stu-id="36f7a-139">With SharePoint Online things are a little different.</span></span> <span data-ttu-id="36f7a-140">Cuanto más trabajo realice un servidor, más tiempo se tarda en representar una página.</span><span class="sxs-lookup"><span data-stu-id="36f7a-140">The more work you make a server do, the longer it takes to render a page.</span></span> <span data-ttu-id="36f7a-141">Con SharePoint, el mayor responsable en este sentido son las páginas complejas con varios elementos web.</span><span class="sxs-lookup"><span data-stu-id="36f7a-141">With SharePoint, the biggest culprit in this respect are complex pages with multiple web parts.</span></span>
  
<span data-ttu-id="36f7a-142">SharePoint Server local</span><span class="sxs-lookup"><span data-stu-id="36f7a-142">SharePoint Server on-premises</span></span>
  
![Captura de pantalla del servidor local](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
<span data-ttu-id="36f7a-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="36f7a-144">SharePoint Online</span></span>
  
![Captura de pantalla del servidor en línea](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
<span data-ttu-id="36f7a-146">Con SharePoint Online, es posible que determinadas solicitudes de página acaben llamando a varios servidores.</span><span class="sxs-lookup"><span data-stu-id="36f7a-146">With SharePoint Online, certain page requests may actually end up calling multiple servers.</span></span> <span data-ttu-id="36f7a-147">Podría terminar con una matriz de solicitudes entre servidores para una solicitud individual.</span><span class="sxs-lookup"><span data-stu-id="36f7a-147">You could end up with a matrix of requests between servers for an individual request.</span></span> <span data-ttu-id="36f7a-148">Estas interacciones son costosas desde una perspectiva de carga de página y ralentizarán las cosas.</span><span class="sxs-lookup"><span data-stu-id="36f7a-148">These interactions are expensive from a page load perspective and will make things slow.</span></span>
  
<span data-ttu-id="36f7a-149">Algunos ejemplos de estas interacciones de servidor a servidor son:</span><span class="sxs-lookup"><span data-stu-id="36f7a-149">Examples of these server to server interactions are:</span></span>
  
- <span data-ttu-id="36f7a-150">Servidores web SQL web</span><span class="sxs-lookup"><span data-stu-id="36f7a-150">Web to SQL Servers</span></span>
    
- <span data-ttu-id="36f7a-151">Servidores de aplicaciones web a aplicaciones</span><span class="sxs-lookup"><span data-stu-id="36f7a-151">Web to application servers</span></span>
    
<span data-ttu-id="36f7a-152">La otra cosa que puede ralentizar las interacciones del servidor son los problemas de caché.</span><span class="sxs-lookup"><span data-stu-id="36f7a-152">The other thing that can slow down server interactions is cache misses.</span></span> <span data-ttu-id="36f7a-153">A diferencia de SharePoint local, existe una posibilidad muy única de que se visita el mismo servidor para una página que ha visitado anteriormente; esto hace que el almacenamiento en caché de objetos sea obsoleto.</span><span class="sxs-lookup"><span data-stu-id="36f7a-153">Unlike on-premises SharePoint, there is a very slim chance that you will hit the same server for a page that you have visited previously; this makes object caching obsolete.</span></span>
  
### <a name="network-connection"></a><span data-ttu-id="36f7a-154">Conexión de red </span><span class="sxs-lookup"><span data-stu-id="36f7a-154">Network connection</span></span>

<span data-ttu-id="36f7a-155">Con SharePoint local que no usa una WAN, puede usar una conexión de alta velocidad entre el centro de datos y los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="36f7a-155">With on-premises SharePoint that doesn't make use of a WAN, you may use a high-speed connection between datacenter and end-users.</span></span> <span data-ttu-id="36f7a-156">Por lo general, las cosas son fáciles de administrar desde la perspectiva de la red.</span><span class="sxs-lookup"><span data-stu-id="36f7a-156">Generally, things are easy to manage from a network perspective.</span></span>
  
<span data-ttu-id="36f7a-157">Con SharePoint Online, hay que tener en cuenta algunos factores más; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="36f7a-157">With SharePoint Online, there are a few more factors to consider; for example:</span></span>
  
- <span data-ttu-id="36f7a-158">La red de Microsoft</span><span class="sxs-lookup"><span data-stu-id="36f7a-158">The Microsoft network</span></span>
    
- <span data-ttu-id="36f7a-159">The Internet</span><span class="sxs-lookup"><span data-stu-id="36f7a-159">The Internet</span></span>
    
- <span data-ttu-id="36f7a-160">El ISP</span><span class="sxs-lookup"><span data-stu-id="36f7a-160">The ISP</span></span>
    
<span data-ttu-id="36f7a-161">Independientemente de la versión de SharePoint (y de la red) que use, los aspectos que normalmente harán que la red esté ocupada incluyen:</span><span class="sxs-lookup"><span data-stu-id="36f7a-161">Regardless of which version of SharePoint (and which network) you are using, things that will typically cause the network to be busy include:</span></span>
  
- <span data-ttu-id="36f7a-162">Carga de gran tamaño</span><span class="sxs-lookup"><span data-stu-id="36f7a-162">Large payload</span></span>
    
- <span data-ttu-id="36f7a-163">Muchos archivos</span><span class="sxs-lookup"><span data-stu-id="36f7a-163">Many files</span></span>
    
- <span data-ttu-id="36f7a-164">Gran distancia física con el servidor</span><span class="sxs-lookup"><span data-stu-id="36f7a-164">Large physical distance to the server</span></span>
    
<span data-ttu-id="36f7a-165">Una característica que puede aprovechar en SharePoint Online es la red CDN de Microsoft (red de entrega de contenido).</span><span class="sxs-lookup"><span data-stu-id="36f7a-165">One feature that you can leverage in SharePoint Online is the Microsoft CDN (Content Delivery Network).</span></span> <span data-ttu-id="36f7a-166">Una red CDN es básicamente una colección distribuida de servidores implementados en varios centros de datos.</span><span class="sxs-lookup"><span data-stu-id="36f7a-166">A CDN is basically a distributed collection of servers deployed across multiple datacenters.</span></span> <span data-ttu-id="36f7a-167">Con una red CDN, el contenido de las páginas se puede hospedar en un servidor cercano al cliente, incluso si el cliente está lejos del SharePoint Server de origen.</span><span class="sxs-lookup"><span data-stu-id="36f7a-167">With a CDN, content on pages can be hosted on a server close to the client even if the client is far away from the originating SharePoint Server.</span></span> <span data-ttu-id="36f7a-168">Microsoft lo va a usar más en el futuro para almacenar instancias locales de páginas que no se pueden personalizar, por ejemplo, la página principal del administrador de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="36f7a-168">Microsoft will be using this more in the future to store local instances of pages which cannot be customized, for example the SharePoint Online admin home page.</span></span> <span data-ttu-id="36f7a-169">Para obtener más información acerca de las redes CDN, vea [Redes de entrega de contenido.](content-delivery-networks.md)</span><span class="sxs-lookup"><span data-stu-id="36f7a-169">For more information about CDNs, see [Content delivery networks](content-delivery-networks.md).</span></span>
  
<span data-ttu-id="36f7a-170">Algo que debes tener en cuenta, pero que es posible que no pueda hacer mucho, es la velocidad de conexión de tu ISP.</span><span class="sxs-lookup"><span data-stu-id="36f7a-170">Something that you need to be aware of but may not be able to do much about is the connection speed of your ISP.</span></span> <span data-ttu-id="36f7a-171">Una herramienta de prueba de velocidad simple te mostrará la velocidad de conexión.</span><span class="sxs-lookup"><span data-stu-id="36f7a-171">A simple speed test tool will tell you the connection speed.</span></span>
  
### <a name="browser-connection"></a><span data-ttu-id="36f7a-172">Conexión del explorador</span><span class="sxs-lookup"><span data-stu-id="36f7a-172">Browser connection</span></span>

<span data-ttu-id="36f7a-173">Hay algunos factores que se deben tener en cuenta con los exploradores web desde una perspectiva de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="36f7a-173">There are a few factors to consider with web browsers from a performance perspective.</span></span>
  
<span data-ttu-id="36f7a-174">Visitar páginas complejas afectará al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="36f7a-174">Visiting complex pages will affect performance.</span></span> <span data-ttu-id="36f7a-175">La mayoría de los exploradores solo tienen una memoria caché pequeña (alrededor de 90 MB), mientras que la página web promedio suele estar en torno a 1,6 MB.</span><span class="sxs-lookup"><span data-stu-id="36f7a-175">Most browsers only have a small cache (around 90MB), while the average web page is typically around 1.6MB.</span></span> <span data-ttu-id="36f7a-176">Esto no puede tardar mucho tiempo en usarse.</span><span class="sxs-lookup"><span data-stu-id="36f7a-176">This doesn't take long to get used up.</span></span>
  
<span data-ttu-id="36f7a-177">El ancho de banda también puede ser un problema.</span><span class="sxs-lookup"><span data-stu-id="36f7a-177">Bandwidth may also be an issue.</span></span> <span data-ttu-id="36f7a-178">Por ejemplo, si un usuario ve vídeos en otra sesión, esto afectará al rendimiento de la página de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="36f7a-178">For example, if a user is watching videos in another session, this will affect the performance of your SharePoint page.</span></span> <span data-ttu-id="36f7a-179">Aunque no puede impedir que los usuarios transmita contenido multimedia, puede controlar la forma en que se cargará una página para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="36f7a-179">While you can't prevent users from streaming media, you can control the way a page will load for users.</span></span>
  
<span data-ttu-id="36f7a-180">Consulte los artículos siguientes para obtener distintas técnicas de personalización de páginas de SharePoint Online y otros procedimientos recomendados que le ayudarán a lograr un rendimiento óptimo.</span><span class="sxs-lookup"><span data-stu-id="36f7a-180">Check out the following articles for different SharePoint Online page customization techniques and other best practices to help you achieve optimal performance.</span></span>
  
- [<span data-ttu-id="36f7a-181">Opciones de navegación para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="36f7a-181">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="36f7a-182">Usar la herramienta diagnóstico de páginas para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="36f7a-182">Use the Page Diagnostics tool for SharePoint Online</span></span>](page-diagnostics-for-spo.md)
    
- [<span data-ttu-id="36f7a-183">Optimización de imágenes para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="36f7a-183">Image optimization for SharePoint Online</span></span>](image-optimization-for-sharepoint-online.md)
    
- [<span data-ttu-id="36f7a-184">Retrasar la carga de imágenes y JavaScript en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="36f7a-184">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [<span data-ttu-id="36f7a-185">Minificación y agrupación en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="36f7a-185">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="36f7a-186">Uso de la red de entrega de contenido (CDN) de Office 365 con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="36f7a-186">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="36f7a-187">Uso del elemento web Búsqueda de contenido en lugar del elemento web Consulta de contenido para mejorar el rendimiento en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="36f7a-187">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [<span data-ttu-id="36f7a-188">Planeamiento de capacidad y pruebas de carga en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="36f7a-188">Capacity planning and load testing SharePoint Online</span></span>](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [<span data-ttu-id="36f7a-189">Diagnosticar problemas de rendimiento con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="36f7a-189">Diagnosing performance issues with SharePoint Online</span></span>](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [<span data-ttu-id="36f7a-190">Usar la memoria caché de objetos con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="36f7a-190">Using the object cache with SharePoint Online</span></span>](using-the-object-cache-with-sharepoint-online.md)
    
- [<span data-ttu-id="36f7a-191">Cómo: Evitar estar limitado o bloqueado en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="36f7a-191">How to: Avoid getting throttled or blocked in SharePoint Online</span></span>](https://msdn.microsoft.com/library/office/dn889829.aspx)
    

