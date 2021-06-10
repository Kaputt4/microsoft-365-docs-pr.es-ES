---
title: Office 365 Content Delivery Network inicio rápido (CDN)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 Content Delivery Network inicio rápido (CDN)
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921599"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a><span data-ttu-id="45f07-103">Office 365 Content Delivery Network inicio rápido (CDN)</span><span class="sxs-lookup"><span data-stu-id="45f07-103">Office 365 Content Delivery Network (CDN) Quickstart</span></span>

<span data-ttu-id="45f07-104">Puede usar el Office 365 Content Delivery Network **integrado (CDN)** para hospedar activos estáticos (imágenes, JavaScript, hojas de estilos, archivos WOFF) para proporcionar un mejor rendimiento para las páginas de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="45f07-104">You can use the built-in **Office 365 Content Delivery Network (CDN)** to host static assets (images, JavaScript, Stylesheets, WOFF files) to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="45f07-105">La CDN de Office 365 mejora el rendimiento al almacenamiento en caché los archivos estáticos más cerca de los exploradores que los solicitan, lo que ayuda a acelerar descargas y reducir la latencia.</span><span class="sxs-lookup"><span data-stu-id="45f07-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="45f07-106">Además, el Office 365 CDN usa el protocolo HTTP/2 para mejorar la compresión y la canalización HTTP.</span><span class="sxs-lookup"><span data-stu-id="45f07-106">Also, the Office 365 CDN uses the HTTP/2 protocol for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="45f07-107">La red CDN de Office 365 se incluye como parte de la suscripción a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="45f07-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

<span data-ttu-id="45f07-108">Para obtener instrucciones más detalladas, vea [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span><span class="sxs-lookup"><span data-stu-id="45f07-108">For more detailed information guidance see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="45f07-109">El Office 365 CDN solo está disponible para los inquilinos en la nube de producción (en todo el mundo).</span><span class="sxs-lookup"><span data-stu-id="45f07-109">The Office 365 CDN is only available to tenants in the production (worldwide) cloud.</span></span> <span data-ttu-id="45f07-110">Actualmente, los inquilinos de las nubes de Estados Unidos, China y Alemania no admiten el Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="45f07-110">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a><span data-ttu-id="45f07-111">Use la herramienta Diagnóstico de página para SharePoint para identificar elementos que no están en CDN</span><span class="sxs-lookup"><span data-stu-id="45f07-111">Use the Page Diagnostics for SharePoint tool to identify items not in CDN</span></span>

<span data-ttu-id="45f07-112">Puede usar  el diagnóstico de página para la extensión del explorador de herramientas SharePoint para enumerar fácilmente los activos de las páginas de SharePoint Online que se pueden agregar a un CDN origen.</span><span class="sxs-lookup"><span data-stu-id="45f07-112">You can use the **Page Diagnostics for SharePoint tool** browser extension to easily list assets in your SharePoint Online pages that can be added to a CDN origin.</span></span>

<span data-ttu-id="45f07-113">La **herramienta Diagnóstico de** página para SharePoint es una extensión de explorador para el nuevo Microsoft Edge ( y los exploradores Chrome que analizan tanto SharePoint Portal moderno en línea como páginas de sitio de publicación https://www.microsoft.com/edge) clásicas.</span><span class="sxs-lookup"><span data-stu-id="45f07-113">The **Page Diagnostics for SharePoint tool** is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="45f07-114">La herramienta le ofrece un informe para cada página analizada en el que se muestra el rendimiento de la página respecto a un conjunto definido de criterios de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="45f07-114">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="45f07-115">Para instalar e informarse de la herramienta Diagnóstico de página de SharePoint, visite [Usar la herramienta Diagnóstico de página para SharePoint Online](./page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="45f07-115">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](./page-diagnostics-for-spo.md).</span></span>

<span data-ttu-id="45f07-116">Al ejecutar la herramienta Diagnósticos de página para SharePoint en una página de  SharePoint Online, puede hacer clic en la pestaña Pruebas de diagnóstico para ver una lista de activos que el CDN.</span><span class="sxs-lookup"><span data-stu-id="45f07-116">When you run the Page Diagnostics for SharePoint tool on a SharePoint Online page, you can click the **Diagnostic Tests** tab to see a list of assets not being hosted by the CDN.</span></span> <span data-ttu-id="45f07-117">Estos activos se mostrarán bajo el encabezado **Content Delivery Network (CDN) como** se muestra en la captura de pantalla siguiente.</span><span class="sxs-lookup"><span data-stu-id="45f07-117">These assets will be listed under the heading **Content Delivery Network (CDN) check** as shown in the screenshot below.</span></span>

![Diagnósticos de página](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
><span data-ttu-id="45f07-119">La herramienta de Diagnóstico de páginas solo funciona para SharePoint Online y no se puede usar en una página del sistema de SharePoint. </span><span class="sxs-lookup"><span data-stu-id="45f07-119">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

## <a name="cdn-overview"></a><span data-ttu-id="45f07-120">CDN Información general</span><span class="sxs-lookup"><span data-stu-id="45f07-120">CDN Overview</span></span>

<span data-ttu-id="45f07-121">El Office 365 CDN está diseñado para optimizar el rendimiento de los usuarios mediante la distribución de objetos a los que se accede con frecuencia como imágenes y archivos javascript a través de una red global de alta velocidad, lo que reduce el tiempo de carga de la página y proporciona acceso a objetos hospedados lo más cerca posible para el usuario.</span><span class="sxs-lookup"><span data-stu-id="45f07-121">The Office 365 CDN is designed to optimize performance for users by distributing frequently accessed objects like images and javascript files over a high-speed global network, reducing page load time and providing access to hosted objects as close as possible to the user.</span></span> <span data-ttu-id="45f07-122">El CDN recupera los activos de una ubicación denominada _origen_.</span><span class="sxs-lookup"><span data-stu-id="45f07-122">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="45f07-123">Un origen puede ser un sitio SharePoint, biblioteca de documentos o carpeta a la que una dirección URL puede tener acceso.</span><span class="sxs-lookup"><span data-stu-id="45f07-123">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span>

<span data-ttu-id="45f07-124">El Office 365 CDN está separado en dos tipos básicos:</span><span class="sxs-lookup"><span data-stu-id="45f07-124">The Office 365 CDN is separated into two basic types:</span></span>

- <span data-ttu-id="45f07-125">**El CDN** público está diseñado para usarse para JS (JavaScript), CSS (StyleSheets), archivo de fuente web (WOFF, WOFF2) e imágenes no propietarias como logotipos de empresa.</span><span class="sxs-lookup"><span data-stu-id="45f07-125">**Public CDN** is designed to be used for JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) and non-proprietary images like company logos.</span></span>
- <span data-ttu-id="45f07-126">**El CDN** privado está diseñado para usarse para imágenes (PNG, JPG, JPEG, etc.).</span><span class="sxs-lookup"><span data-stu-id="45f07-126">**Private CDN** is designed to be used for images (PNG, JPG, JPEG, etc.).</span></span>

<span data-ttu-id="45f07-127">Puede elegir tener orígenes públicos o privados para su organización.</span><span class="sxs-lookup"><span data-stu-id="45f07-127">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="45f07-128">La mayoría de las organizaciones elegirán implementar una combinación de las dos.</span><span class="sxs-lookup"><span data-stu-id="45f07-128">Most organizations will choose to implement a combination of the two.</span></span> <span data-ttu-id="45f07-129">Las opciones públicas y privadas proporcionan ganancias de rendimiento similares, pero cada una tiene atributos y ventajas únicos.</span><span class="sxs-lookup"><span data-stu-id="45f07-129">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span> <span data-ttu-id="45f07-130">Para obtener más información acerca de los orígenes CDN públicos y privados, vea [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span><span class="sxs-lookup"><span data-stu-id="45f07-130">For more information about public and private CDN origins, see [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span>

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a><span data-ttu-id="45f07-131">Cómo habilitar los servicios públicos y CDN con la configuración predeterminada</span><span class="sxs-lookup"><span data-stu-id="45f07-131">How to enable Public and Private CDN with the default configuration</span></span>
<span data-ttu-id="45f07-132">Antes de realizar cambios en la configuración de CDN inquilino, debe comprobar que cumple las directivas de cumplimiento, seguridad y privacidad de su organización.</span><span class="sxs-lookup"><span data-stu-id="45f07-132">Before you make changes to the tenant CDN settings, you should verify that it meets compliance, security and privacy policies of your organization.</span></span>

<span data-ttu-id="45f07-133">Para obtener opciones de configuración más detalladas, o si ya ha habilitado CDN y desea agregar ubicaciones adicionales (orígenes), consulte la sección Configurar y configurar el Office 365 CDN mediante el Shell de administración en línea de [SharePoint](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span><span class="sxs-lookup"><span data-stu-id="45f07-133">For more detailed configuration settings, or if you have already enabled CDN and want to add additional locations (origins), please see the section [Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span></span>

<span data-ttu-id="45f07-134">Conectar a su inquilino mediante el Shell SharePoint administración en línea:</span><span class="sxs-lookup"><span data-stu-id="45f07-134">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

<span data-ttu-id="45f07-135">Para permitir que la organización use orígenes públicos y privados con la configuración predeterminada, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="45f07-135">To enable your organization to use both public and private origins with the default configuration, type the following command:</span></span>

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="45f07-136">El resultado de estos cmdlets debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="45f07-136">Output of these cmdlets should look like the following:</span></span>

![Salida de Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a><span data-ttu-id="45f07-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45f07-138">See also</span></span>

[<span data-ttu-id="45f07-139">Usar la herramienta Diagnóstico de página para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="45f07-139">Use the Page Diagnostics tool for SharePoint Online</span></span>](./page-diagnostics-for-spo.md)

[<span data-ttu-id="45f07-140">Uso de la red de entrega de contenido (CDN) de Office 365 con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="45f07-140">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)

[<span data-ttu-id="45f07-141">Redes de entrega de contenido</span><span class="sxs-lookup"><span data-stu-id="45f07-141">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="45f07-142">Planeamiento de red y ajuste del rendimiento para Office 365</span><span class="sxs-lookup"><span data-stu-id="45f07-142">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="45f07-143">SharePoint Serie de rendimiento: Office 365 CDN de vídeo</span><span class="sxs-lookup"><span data-stu-id="45f07-143">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)