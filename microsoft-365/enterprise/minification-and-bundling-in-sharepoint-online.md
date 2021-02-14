---
title: Minificación y agrupación en SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/1/2017
audience: Admin
ms.topic: troubleshooting
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
- SPO160
- MET150
ms.assetid: 87a52468-994e-43a2-b155-7229ed659291
description: Aprenda a usar técnicas de reducción y agrupación con Web Essentials para reducir las solicitudes HTTP y el tiempo que se tarda en cargar páginas en SharePoint Online.
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693663"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a><span data-ttu-id="97165-103">Minificación y agrupación en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="97165-103">Minification and bundling in SharePoint Online</span></span>

<span data-ttu-id="97165-104">En este artículo se describe cómo usar técnicas de reducción y agrupación con Web Essentials para reducir el número de solicitudes HTTP y reducir el tiempo necesario para cargar páginas en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="97165-104">This article describes how to use minification and bundling techniques with Web Essentials to reduce the number of HTTP requests and to reduce the time it takes to load pages in SharePoint Online.</span></span>
  
<span data-ttu-id="97165-105">Al personalizar el sitio web, puede terminar agregando un gran número de archivos adicionales al servidor para admitir la personalización.</span><span class="sxs-lookup"><span data-stu-id="97165-105">When you customize your website you can end up adding a large number of extra files to the server to support the customization.</span></span> <span data-ttu-id="97165-106">Agregar javaScript, CSS e imágenes adicionales aumenta el número de solicitudes HTTP al servidor, lo que a su vez aumenta el tiempo que se tarda en mostrar una página web.</span><span class="sxs-lookup"><span data-stu-id="97165-106">Adding extra JavaScript, CSS, and images increases the number of HTTP requests to the server which in turn increases the time it takes to display a web page.</span></span> <span data-ttu-id="97165-107">Si tienes varios archivos del mismo tipo, puedes agrupar estos archivos para que la descarga de estos archivos sea más rápida.</span><span class="sxs-lookup"><span data-stu-id="97165-107">If you have multiple files of the same type, you can bundle these files to make downloading these files faster.</span></span>
  
<span data-ttu-id="97165-108">Para los archivos JavaScript y CSS, también puede usar un enfoque denominado minification, donde se reduce el tamaño total de los archivos quitando los espacios en blanco y otros caracteres que no son necesarios.</span><span class="sxs-lookup"><span data-stu-id="97165-108">For JavaScript and CSS files, you can also use an approach called minification, where you reduce the total size of files by removing whitespace and other characters that aren't necessary.</span></span>
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a><span data-ttu-id="97165-109">Minification and bundling JavaScript and CSS files with Web Essentials</span><span class="sxs-lookup"><span data-stu-id="97165-109">Minification and bundling JavaScript and CSS files with Web Essentials</span></span>

<span data-ttu-id="97165-110">Puede usar software de terceros como Web Essentials para agrupar archivos CSS y JavaScript.</span><span class="sxs-lookup"><span data-stu-id="97165-110">You can use third-party software such as Web Essentials to bundle CSS and JavaScript files.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="97165-111">Web Essentials es un proyecto basado en la comunidad de código abierto de terceros.</span><span class="sxs-lookup"><span data-stu-id="97165-111">Web Essentials is a third-party, open-source, community-based project.</span></span> <span data-ttu-id="97165-112">El software es una extensión para Visual Studio 2012 y Visual Studio 2013 y no es compatible con Microsoft.</span><span class="sxs-lookup"><span data-stu-id="97165-112">The software is an extension to Visual Studio 2012 and Visual Studio 2013 and is not supported by Microsoft.</span></span> <span data-ttu-id="97165-113">Para descargar Web Essentials, visite el sitio web en [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) .</span><span class="sxs-lookup"><span data-stu-id="97165-113">To download Web Essentials, visit the website at [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629).</span></span> 
  
<span data-ttu-id="97165-114">Web Essentials ofrece dos formas de agrupación:</span><span class="sxs-lookup"><span data-stu-id="97165-114">Web Essentials offers two forms of bundling:</span></span>
  
- <span data-ttu-id="97165-115">.bundle: para archivos CSS y JavaScript</span><span class="sxs-lookup"><span data-stu-id="97165-115">.bundle: for CSS and JavaScript files</span></span>
    
- <span data-ttu-id="97165-116">.sprite: para imágenes (solo disponible en Visual Studio 2013)</span><span class="sxs-lookup"><span data-stu-id="97165-116">.sprite: for images (only available in Visual Studio 2013)</span></span>
    
<span data-ttu-id="97165-117">Puede usar Web Essentials si tiene una característica existente con algunos elementos de personalización de marca a los que se hace referencia dentro de una página maestra personalizada, como:</span><span class="sxs-lookup"><span data-stu-id="97165-117">You can use Web Essentials if you have an existing feature with some branding elements that are referenced inside a custom master page, such as:</span></span>
  
![Captura de pantalla de un elemento que identifica la marca en la página maestra personalizada](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 <span data-ttu-id="97165-119">**Para crear un paquete TE000127218 y CSS en Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="97165-119">**To create a TE000127218 and CSS bundle in Web Essentials**</span></span>
  
1. <span data-ttu-id="97165-120">En Visual Studio, en el Explorador de soluciones, seleccione los archivos que desea incluir en la agrupación.</span><span class="sxs-lookup"><span data-stu-id="97165-120">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="97165-121">Haga clic con el botón secundario en los archivos seleccionados y, a continuación, seleccione **Web Essentials** Crear archivo de agrupación de \> **JavaScript** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="97165-121">Right-click the selected files and then select **Web Essentials** \> **Create JavaScript bundle file** from the context menu.</span></span> <span data-ttu-id="97165-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="97165-122">For example:</span></span> 
    
    ![Captura de pantalla que muestra las opciones de menú de Web Essentials](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a><span data-ttu-id="97165-124">Visualización de los resultados de la agrupación de archivos JavaScript y CSS</span><span class="sxs-lookup"><span data-stu-id="97165-124">Viewing the results of bundling JavaScript and CSS files</span></span>

<span data-ttu-id="97165-125">Al crear una agrupación de JavaScript y CSS, Web Essentials crea un archivo XML denominado archivo de receta que identifica los archivos JavaScript y CSS, así como otra información de configuración:</span><span class="sxs-lookup"><span data-stu-id="97165-125">When you create a JavaScript and CSS bundle, Web Essentials creates an XML file called a recipe file that identifies the JavaScript and CSS files as well as some other configuration information:</span></span> 
  
![Captura de pantalla del archivo receta de JavaScript y CSS](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
<span data-ttu-id="97165-127">Además, si la marca de reducción se establece en true en la receta de agrupación, los archivos se reducen en tamaño y se agrupan juntos.</span><span class="sxs-lookup"><span data-stu-id="97165-127">In addition, if the minify flag is set to true in the bundling recipe the files are reduced in size as well as bundled together.</span></span> <span data-ttu-id="97165-128">Esto significa que se crearon versiones nuevas y minadas de los archivos JavaScript a las que puede hacer referencia en la página maestra.</span><span class="sxs-lookup"><span data-stu-id="97165-128">This means that new, minified versions of the JavaScript files were created that you can reference in your master page.</span></span>
  
![Captura de pantalla de la marca de minify establecida en verdadero](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
<span data-ttu-id="97165-130">Al cargar una página desde el sitio web, puede usar las herramientas de desarrollo del explorador web, como Internet Explorer 11, para ver el número de solicitudes enviadas al servidor y el tiempo que tardó cada archivo en cargarse.</span><span class="sxs-lookup"><span data-stu-id="97165-130">When you load a page from your web site, you can use the developer tools from your web browser, such as Internet Explorer 11, to see the number of requests sent to the server and how long each file took to load.</span></span>
  
<span data-ttu-id="97165-131">La siguiente figura es el resultado de cargar los archivos JavaScript y CSS antes de la minificación.</span><span class="sxs-lookup"><span data-stu-id="97165-131">The following figure is the result of loading the JavaScript and CSS files before minification.</span></span>
  
![Captura de pantalla que muestra los 80 artículos descargándose](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
<span data-ttu-id="97165-133">Después de agrupar los archivos CSS y JavaScript, el número de solicitudes disminuyó a 74 y cada archivo tardó un poco más que los archivos originales en descargarse individualmente:</span><span class="sxs-lookup"><span data-stu-id="97165-133">After bundling the CSS and JavaScript files together, the number of requests dropped to 74 and each file took only slightly longer than the original files to download individually:</span></span>
  
![Captura de pantalla que muestra los 74 artículos descargándose](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
<span data-ttu-id="97165-135">Después de la agrupación, el archivo de agrupación de JavaScript se reduce significativamente de 815 KB a 365 KB:</span><span class="sxs-lookup"><span data-stu-id="97165-135">After bundling, the JavaScript bundle file is reduced significantly from 815KB to 365KB:</span></span>
  
![Captura de pantalla que muestra el tamaño de la descarga reducido](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a><span data-ttu-id="97165-137">Agrupación de imágenes mediante la creación de un sprite de imagen</span><span class="sxs-lookup"><span data-stu-id="97165-137">Bundling images by creating an image sprite</span></span>

<span data-ttu-id="97165-138">De forma similar a la forma en que agrupas archivos JavaScript y CSS, puedes combinar muchos iconos pequeños y otras imágenes comunes en una hoja sprite más grande y, a continuación, usar CSS para mostrar las imágenes individuales.</span><span class="sxs-lookup"><span data-stu-id="97165-138">Similar to how you bundle JavaScript and CSS files, you can combine many small icons and other common images into a larger sprite sheet and then use CSS to reveal the individual images.</span></span> <span data-ttu-id="97165-139">En lugar de descargar cada imagen individual, el explorador web del usuario descarga la hoja sprite una vez y, a continuación, la almacena en caché en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="97165-139">Instead of downloading each individual image, the user's web browser downloads the sprite sheet once and then caches it on the local computer.</span></span> <span data-ttu-id="97165-140">Esto mejora el rendimiento de la carga de página al reducir el número de descargas y viajes de ida y vuelta al servidor web.</span><span class="sxs-lookup"><span data-stu-id="97165-140">This improves page load performance by cutting down on the number of downloads and round trips to the web server.</span></span>
  
 <span data-ttu-id="97165-141">**Para crear un sprite de imagen en Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="97165-141">**To create an image sprite in Web Essentials**</span></span>
  
1. <span data-ttu-id="97165-142">En Visual Studio, en el Explorador de soluciones, seleccione los archivos que desea incluir en la agrupación.</span><span class="sxs-lookup"><span data-stu-id="97165-142">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="97165-143">Haz clic con el botón derecho en los archivos seleccionados y, a **continuación, selecciona Web Essentials** Crear sprite de \> **imagen** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="97165-143">Right-click the selected files and then select **Web Essentials** \> **Create image sprite** from the context menu.</span></span> <span data-ttu-id="97165-144">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="97165-144">For example:</span></span> 
    
    ![Captura de pantalla que muestra cómo crear un objeto sprite de imagen](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. <span data-ttu-id="97165-146">Elige una ubicación para guardar el archivo sprite.</span><span class="sxs-lookup"><span data-stu-id="97165-146">Choose a location to save the sprite file.</span></span> <span data-ttu-id="97165-147">El archivo .sprite es un archivo XML que describe la configuración y los archivos del sprite.</span><span class="sxs-lookup"><span data-stu-id="97165-147">The .sprite file is an XML file that describes the settings and files in the sprite.</span></span> <span data-ttu-id="97165-148">Las siguientes figuras muestran un ejemplo de un archivo PNG sprite y su archivo .sprite XML correspondiente.</span><span class="sxs-lookup"><span data-stu-id="97165-148">The following figures show an example of a sprite PNG file and its corresponding .sprite XML file.</span></span>
    
    ![Captura de pantalla de un archivo de sprite](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Captura de pantalla de archivo XML de sprite](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

