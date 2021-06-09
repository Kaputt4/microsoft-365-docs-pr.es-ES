---
title: Diagnosticar problemas de rendimiento con SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
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
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: En este artículo se muestra cómo diagnosticar problemas comunes con el sitio SharePoint Online mediante las herramientas de desarrollador de Internet Explorer.
ms.openlocfilehash: 6a29b8b2df54d74d8237418828a7aa89efdbcfaf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927617"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a><span data-ttu-id="b8096-103">Diagnosticar problemas de rendimiento con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b8096-103">Diagnosing performance issues with SharePoint Online</span></span>

<span data-ttu-id="b8096-104">En este artículo se muestra cómo diagnosticar problemas comunes con el sitio SharePoint Online mediante las herramientas de desarrollador de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b8096-104">This article shows you how you can diagnose common issues with your SharePoint Online site using Internet Explorer developer tools.</span></span>
  
<span data-ttu-id="b8096-105">Hay tres formas diferentes de identificar que una página de un sitio de SharePoint Online tiene un problema de rendimiento con las personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="b8096-105">There are three different ways that you can identify that a page on a SharePoint Online site has a performance problem with the customizations.</span></span>
  
- <span data-ttu-id="b8096-106">Monitor de red de la barra de herramientas F12</span><span class="sxs-lookup"><span data-stu-id="b8096-106">The F12 tool bar network monitor</span></span>

- <span data-ttu-id="b8096-107">Comparación con una línea base no personalizada</span><span class="sxs-lookup"><span data-stu-id="b8096-107">Comparison to a non-customized baseline</span></span>

- <span data-ttu-id="b8096-108">SharePoint Métricas de encabezado de respuesta en línea</span><span class="sxs-lookup"><span data-stu-id="b8096-108">SharePoint Online response header metrics</span></span>

<span data-ttu-id="b8096-109">En este tema se describe cómo usar cada uno de estos métodos para diagnosticar problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b8096-109">This topic describes how to use each of these methods to diagnose performance issues.</span></span> <span data-ttu-id="b8096-110">Una vez que haya descubierto la causa del problema, puede trabajar en una solución con los artículos sobre cómo mejorar SharePoint rendimiento que puede encontrar en https://aka.ms/tune .</span><span class="sxs-lookup"><span data-stu-id="b8096-110">Once you've figured out the cause of the problem, you can work toward a solution using the articles about improving SharePoint performance that you can find on https://aka.ms/tune.</span></span>
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a><span data-ttu-id="b8096-111">Uso de la barra de herramientas F12 para diagnosticar el rendimiento en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b8096-111">Using the F12 tool bar to diagnose performance in SharePoint Online</span></span>
<span data-ttu-id="b8096-112"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="b8096-112"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="b8096-113">En este artículo usamos Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="b8096-113">In this article we use Internet Explorer 11.</span></span> <span data-ttu-id="b8096-114">Las versiones de las herramientas de desarrollo F12 en otros exploradores tienen características similares, aunque pueden tener un aspecto ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="b8096-114">Versions of the F12 developer tools on other browsers have similar features though they may look slightly different.</span></span> <span data-ttu-id="b8096-115">Para obtener información sobre las herramientas para desarrolladores de F12, vea:</span><span class="sxs-lookup"><span data-stu-id="b8096-115">For information on the F12 developer tools, see:</span></span>
  
- <span data-ttu-id="b8096-116">[Novedades de F12 Tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="b8096-116">[What's new in F12 Tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span></span>

- <span data-ttu-id="b8096-117">[Usar las herramientas de desarrollo F12](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="b8096-117">[Using the F12 developer tools](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))</span></span>

<span data-ttu-id="b8096-118">Para mostrar las herramientas de desarrollador, **presione F12** y, a continuación, haga clic en Wi-Fi icono:</span><span class="sxs-lookup"><span data-stu-id="b8096-118">To bring up the developer tools press **F12** and then click the Wi-Fi icon:</span></span>
  
![Captura de pantalla del icono wifi de herramientas de desarrollo F12](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
<span data-ttu-id="b8096-120">En la **pestaña Red,** presione el botón de reproducción verde para cargar una página.</span><span class="sxs-lookup"><span data-stu-id="b8096-120">On the **Network** tab, press the green play button to load a page.</span></span> <span data-ttu-id="b8096-121">La herramienta devuelve todos los archivos que el explorador solicita para obtener la página que solicitó.</span><span class="sxs-lookup"><span data-stu-id="b8096-121">The tool returns all of the files that the browser requests in order to get the page you asked for.</span></span> <span data-ttu-id="b8096-122">En la siguiente captura de pantalla se muestra una de estas listas.</span><span class="sxs-lookup"><span data-stu-id="b8096-122">The following screen shot shows one such list.</span></span>
  
![Captura de pantalla de la lista de archivos que se devuelve con una solicitud de página.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
<span data-ttu-id="b8096-124">También puede ver los tiempos de descarga de los archivos en el lado derecho, como se muestra en esta captura de pantalla.</span><span class="sxs-lookup"><span data-stu-id="b8096-124">You can also see the download times of the files on the right side as shown in this screen shot.</span></span>
  
![Diagrama que muestra el tiempo empleado en cargar las páginas solicitadas desde SharePoint](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
<span data-ttu-id="b8096-126">Esto proporciona una representación visual del tiempo que tardó el archivo en cargarse.</span><span class="sxs-lookup"><span data-stu-id="b8096-126">This gives you a visual representation of how long the file took to load.</span></span> <span data-ttu-id="b8096-127">La línea verde representa cuándo está lista la página para representarla el explorador.</span><span class="sxs-lookup"><span data-stu-id="b8096-127">The green line represents when the page is ready to be rendered by the browser.</span></span> <span data-ttu-id="b8096-128">Esto puede proporcionar una vista rápida de los diferentes archivos que pueden estar provocando cargas de página lentas en el sitio.</span><span class="sxs-lookup"><span data-stu-id="b8096-128">This can give you a quick view of the different files that might be causing slow page loads on your site.</span></span>
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a><span data-ttu-id="b8096-129">Configurar una línea base no personalizada para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b8096-129">Setting up a non-customized baseline for SharePoint Online</span></span>
<span data-ttu-id="b8096-130"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="b8096-130"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="b8096-131">La mejor manera de determinar los puntos débiles de rendimiento del sitio es configurar una colección de sitios completamente lista para usar en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b8096-131">The best way to determine your site's performance weak points is to set up a completely out-of-the-box site collection in SharePoint Online.</span></span> <span data-ttu-id="b8096-132">De este modo, puede comparar todos los distintos aspectos de su sitio con lo que se obtiene sin personalización en la página.</span><span class="sxs-lookup"><span data-stu-id="b8096-132">This way you can compare all the various aspects of your site with what you would get with no customization on the page.</span></span> <span data-ttu-id="b8096-133">La OneDrive para la Empresa principal es un buen ejemplo de una colección de sitios independiente que es poco probable que tenga personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="b8096-133">The OneDrive for Business home page is a good example of a separate site collection that is unlikely to have any customizations.</span></span>
  
## <a name="viewing-sharepoint-response-header-information"></a><span data-ttu-id="b8096-134">Ver SharePoint de encabezado de respuesta</span><span class="sxs-lookup"><span data-stu-id="b8096-134">Viewing SharePoint response header information</span></span>
<span data-ttu-id="b8096-135"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="b8096-135"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="b8096-136">En SharePoint Online, puede obtener acceso a la información que se envía de nuevo al explorador en el encabezado de respuesta de cada archivo.</span><span class="sxs-lookup"><span data-stu-id="b8096-136">In SharePoint Online, you can access the information that is sent back to the browser in the response header for each file.</span></span> <span data-ttu-id="b8096-137">El valor más útil para diagnosticar problemas de rendimiento es **SPRequestDuration,** que muestra la cantidad de tiempo que la solicitud tardó en procesarse en el servidor.</span><span class="sxs-lookup"><span data-stu-id="b8096-137">The most useful value for diagnosing performance issues is **SPRequestDuration**, which displays the amount of time that the request took on the server to be processed.</span></span> <span data-ttu-id="b8096-138">Esto puede ayudar a determinar si la solicitud es muy pesada e intensiva en recursos.</span><span class="sxs-lookup"><span data-stu-id="b8096-138">This can help determine if the request is very heavy and resource intensive.</span></span> <span data-ttu-id="b8096-139">Esta es la mejor información que tiene sobre cuánto trabajo está realizando el servidor para servir a la página.</span><span class="sxs-lookup"><span data-stu-id="b8096-139">This is the best insight you have into how much work the server is doing to serve the page.</span></span>

### <a name="to-view-sharepoint-response-header-information"></a><span data-ttu-id="b8096-140">Para ver la SharePoint de encabezado de respuesta</span><span class="sxs-lookup"><span data-stu-id="b8096-140">To view SharePoint response header information</span></span>
  
1. <span data-ttu-id="b8096-141">Asegúrese de que tiene instaladas las herramientas F12.</span><span class="sxs-lookup"><span data-stu-id="b8096-141">Ensure that you have the F12 tools installed.</span></span> <span data-ttu-id="b8096-142">Para obtener más información sobre cómo descargar e instalar estas herramientas, vea [Novedades de las herramientas F12](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="b8096-142">For more information on downloading and installing these tools, see [What's new in F12 tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85)).</span></span>

2. <span data-ttu-id="b8096-143">En las herramientas F12, en la **pestaña** Red, presione el botón verde de reproducción para cargar una página.</span><span class="sxs-lookup"><span data-stu-id="b8096-143">In the F12 tools, on the **Network** tab, press the green play button to load a page.</span></span>

3. <span data-ttu-id="b8096-144">Haga clic en uno de los archivos .aspx devueltos por la herramienta y, a continuación, haga clic **en DETALLES**.</span><span class="sxs-lookup"><span data-stu-id="b8096-144">Click one of the .aspx files returned by the tool and then click **DETAILS**.</span></span>

    ![Muestra los detalles del encabezado de respuesta](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. <span data-ttu-id="b8096-146">Haga clic **en Encabezados de respuesta**.</span><span class="sxs-lookup"><span data-stu-id="b8096-146">Click **Response headers**.</span></span>

    ![Diagrama que muestra la dirección URL del encabezado de respuesta](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a><span data-ttu-id="b8096-148">¿Qué está causando problemas de rendimiento en SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="b8096-148">What's causing performance issues in SharePoint Online?</span></span>
<span data-ttu-id="b8096-149"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="b8096-149"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="b8096-150">En el artículo Opciones de navegación para [SharePoint Online](navigation-options-for-sharepoint-online.md) se muestra un ejemplo de uso del valor SPRequestDuration para determinar que la navegación estructural complicada estaba provocando que la página tardara mucho tiempo en procesarse en el servidor.</span><span class="sxs-lookup"><span data-stu-id="b8096-150">The article [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) shows an example of using the SPRequestDuration value to determine that the complicated structural navigation was causing the page to take a long time to process on the server.</span></span> <span data-ttu-id="b8096-151">Al tomar un valor para un sitio de línea base (sin personalización), es posible determinar si un archivo determinado tarda mucho tiempo en cargarse.</span><span class="sxs-lookup"><span data-stu-id="b8096-151">By taking a value for a baseline site (without customization), it is possible to determine if any given file is taking a long time to load.</span></span> <span data-ttu-id="b8096-152">El ejemplo usado en [Opciones de navegación para SharePoint Online](navigation-options-for-sharepoint-online.md) es el archivo .aspx principal.</span><span class="sxs-lookup"><span data-stu-id="b8096-152">The example used in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) is the main .aspx file.</span></span> <span data-ttu-id="b8096-153">Ese archivo contiene la mayor parte del ASP.NET que se ejecuta para la carga de la página.</span><span class="sxs-lookup"><span data-stu-id="b8096-153">That file contains most of the ASP.NET code that runs for your page load.</span></span> <span data-ttu-id="b8096-154">Según la plantilla de sitio que use, podría ser start.aspx, home.aspx, default.aspx u otro nombre si personaliza la página principal.</span><span class="sxs-lookup"><span data-stu-id="b8096-154">Depending on the site template you use, this could be start.aspx, home.aspx, default.aspx, or another name if you customize the home page.</span></span> <span data-ttu-id="b8096-155">Si este número es considerablemente mayor que el sitio de línea base, es una buena indicación de que hay algo complejo en la página que está causando problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b8096-155">If this number is considerably higher than your baseline site, then it's a good indication that there is something complex going on in your page that is causing performance issues.</span></span>
  
<span data-ttu-id="b8096-156">Una vez que haya identificado que un problema específico del sitio, la forma recomendada de averiguar lo que está causando un rendimiento deficiente es eliminar todas las causas posibles, como personalizaciones de página y, a continuación, volver a agregarlas al sitio uno por uno.</span><span class="sxs-lookup"><span data-stu-id="b8096-156">Once you have identified that an issue specific to your site, the recommended way to figure out what is causing poor performance is to eliminate all of the possible causes, like page customizations, and then add them back to the site one by one.</span></span> <span data-ttu-id="b8096-157">Una vez que haya quitado suficientes personalizaciones que la página está realizando bien, puede agregar personalizaciones específicas una por una.</span><span class="sxs-lookup"><span data-stu-id="b8096-157">Once you have removed enough customizations that the page is performing well, you can then add back specific customizations one by one.</span></span>
  
<span data-ttu-id="b8096-158">Por ejemplo, si tiene una navegación muy compleja, intente cambiar la navegación para no mostrar subs sitios, compruebe las herramientas de desarrollo para ver si esto marca la diferencia.</span><span class="sxs-lookup"><span data-stu-id="b8096-158">For example, if you have a very complex navigation try changing the navigation to not show sub-sites then check the developer tools to see if this makes a difference.</span></span> <span data-ttu-id="b8096-159">O bien, si tiene una gran cantidad de roll-ups de contenido, intente quitarlos de la página y vea si esto mejora las cosas.</span><span class="sxs-lookup"><span data-stu-id="b8096-159">Or if you have a large amount of content roll-ups try removing them from your page and see if this improves things.</span></span> <span data-ttu-id="b8096-160">Si elimina todas las causas posibles y las agrega de una en una, puede identificar fácilmente qué características son el mayor problema y, a continuación, trabajar hacia una solución.</span><span class="sxs-lookup"><span data-stu-id="b8096-160">If you eliminate all of the possible causes and add them back in one at a time, you can easily identify which features are the biggest problem and then work towards a solution.</span></span>