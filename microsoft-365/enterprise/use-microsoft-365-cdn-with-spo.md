---
title: Usar la red de entrega de contenido (CDN) de Office 365 con SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
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
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: Obtenga información sobre cómo usar la Red de entrega de contenido (CDN) de Office 365 para acelerar la entrega de los activos de SharePoint Online.
ms.openlocfilehash: 6b740fc1429613627e0597dc6ecf2e150c015989
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924821"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="a808f-103">Uso de la red de entrega de contenido (CDN) de Office 365 con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a808f-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="a808f-104">Puede usar la red de entrega de contenido (CDN) de Office 365 integrada para hospedar archivos estáticos y mejorar el rendimiento de las páginas de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a808f-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="a808f-105">La CDN de Office 365 mejora el rendimiento al almacenamiento en caché los archivos estáticos más cerca de los exploradores que los solicitan, lo que ayuda a acelerar descargas y reducir la latencia.</span><span class="sxs-lookup"><span data-stu-id="a808f-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="a808f-106">Además, la red CDN de Office 365 usa el [protocolo HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) para mejorar la compresión y la canalización HTTP.</span><span class="sxs-lookup"><span data-stu-id="a808f-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="a808f-107">La red CDN de Office 365 se incluye como parte de la suscripción a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a808f-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="a808f-108">La red CDN de Office 365 solo está disponible para los inquilinos en la **nube de** producción (mundial).</span><span class="sxs-lookup"><span data-stu-id="a808f-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="a808f-109">Actualmente, los inquilinos de las nubes de Estados Unidos, China y Alemania no admiten la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a808f-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="a808f-110">La CDN de Office 365 se compone de varias redes CDN que permite hospedar archivos estáticos en varias ubicaciones u _orígenes_ y a realizar la entrega desde redes de alta velocidad globales.</span><span class="sxs-lookup"><span data-stu-id="a808f-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="a808f-111">Según el tipo de contenido que quiera hospedar en la CDN de Office 365, puede agregar orígenes **públicos**, **privados** o ambos.</span><span class="sxs-lookup"><span data-stu-id="a808f-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="a808f-112">Vea [Elegir si cada origen debe ser público o privado](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) para obtener más información sobre la diferencia entre orígenes públicos y privados.</span><span class="sxs-lookup"><span data-stu-id="a808f-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="a808f-113">![Diagrama conceptual de cdn de Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Diagrama conceptual de cdn de Office 365")</span><span class="sxs-lookup"><span data-stu-id="a808f-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="a808f-114">Si ya está familiarizado con el modo en que funcionan las CDN, solo tiene que completar algunos pasos para habilitar la red CDN de Office 365 para su inquilino.</span><span class="sxs-lookup"><span data-stu-id="a808f-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="a808f-115">En este tema se describe cómo.</span><span class="sxs-lookup"><span data-stu-id="a808f-115">This topic describes how.</span></span> <span data-ttu-id="a808f-116">Sigue leyendo para obtener información sobre cómo empezar a hospedar los activos estáticos.</span><span class="sxs-lookup"><span data-stu-id="a808f-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="a808f-117">Hay otras CDN hospedadas por Microsoft que se pueden usar con Office 365 para escenarios de uso especializado, pero no se abordan en este tema porque están fuera del ámbito de la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a808f-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="a808f-118">Para obtener más información, vea [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span><span class="sxs-lookup"><span data-stu-id="a808f-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="a808f-119">**Vuelva a [Planificación de red y ajuste del rendimiento para Office 365](./network-planning-and-performance.md).**</span><span class="sxs-lookup"><span data-stu-id="a808f-119">**Head back to [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="a808f-120">Información general sobre cómo trabajar con la red CDN de Office 365 en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a808f-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="a808f-121">Para configurar la red CDN de Office 365 para su organización, siga estos pasos básicos:</span><span class="sxs-lookup"><span data-stu-id="a808f-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="a808f-122">Planear la implementación de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="a808f-123">[Determine qué activos estáticos desea hospedar en la red CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span><span class="sxs-lookup"><span data-stu-id="a808f-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="a808f-124">[Determine dónde desea almacenar los activos](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span><span class="sxs-lookup"><span data-stu-id="a808f-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="a808f-125">Esta ubicación puede ser un sitio, biblioteca o carpeta de SharePoint y se denomina _origen_.</span><span class="sxs-lookup"><span data-stu-id="a808f-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="a808f-126">[Elija si cada origen debe ser público o privado.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="a808f-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="a808f-127">Puede agregar varios orígenes de tipos públicos y privados.</span><span class="sxs-lookup"><span data-stu-id="a808f-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="a808f-128">Configurar y configurar la red CDN con PowerShell o la CLI de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a808f-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="a808f-129">Configurar y configurar la red CDN mediante el Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a808f-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="a808f-130">Configurar y configurar la RED CDN con PowerShell pnP</span><span class="sxs-lookup"><span data-stu-id="a808f-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="a808f-131">Configurar y configurar la RED CDN mediante la CLI de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="a808f-132">Cuando complete este paso, tendrá:</span><span class="sxs-lookup"><span data-stu-id="a808f-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="a808f-133">Se ha habilitado la red CDN para su organización.</span><span class="sxs-lookup"><span data-stu-id="a808f-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="a808f-134">Se agregaron los orígenes, identificando cada origen como público o privado.</span><span class="sxs-lookup"><span data-stu-id="a808f-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="a808f-135">Una vez que haya terminado con la instalación, puede administrar la red CDN de [Office 365](use-microsoft-365-cdn-with-spo.md#CDNManage) con el tiempo:</span><span class="sxs-lookup"><span data-stu-id="a808f-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="a808f-136">Agregar, actualizar y quitar activos</span><span class="sxs-lookup"><span data-stu-id="a808f-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="a808f-137">Agregar y quitar orígenes</span><span class="sxs-lookup"><span data-stu-id="a808f-137">Adding and removing origins</span></span>
+ <span data-ttu-id="a808f-138">Configuración de directivas de RED CDN</span><span class="sxs-lookup"><span data-stu-id="a808f-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="a808f-139">Si es necesario, deshabilitar la red CDN</span><span class="sxs-lookup"><span data-stu-id="a808f-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="a808f-140">Por último, consulte [Uso de los activos de la red CDN](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) para obtener información sobre cómo obtener acceso a los activos de red CDN desde orígenes públicos y privados.</span><span class="sxs-lookup"><span data-stu-id="a808f-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="a808f-141">Consulte [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) para obtener instrucciones sobre cómo resolver problemas comunes.</span><span class="sxs-lookup"><span data-stu-id="a808f-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="a808f-142">Planear la implementación de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="a808f-143">Antes de implementar la red CDN de Office 365 para su inquilino de Office 365, debe tener en cuenta los siguientes factores como parte del proceso de planeación.</span><span class="sxs-lookup"><span data-stu-id="a808f-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="a808f-144">Determinar qué activos estáticos desea hospedar en la red CDN</span><span class="sxs-lookup"><span data-stu-id="a808f-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="a808f-145">Determinar dónde desea almacenar los activos</span><span class="sxs-lookup"><span data-stu-id="a808f-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="a808f-146">Elegir si cada origen debe ser público o privado</span><span class="sxs-lookup"><span data-stu-id="a808f-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="a808f-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="a808f-148">Determinar qué activos estáticos desea hospedar en la red CDN</span><span class="sxs-lookup"><span data-stu-id="a808f-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="a808f-149">En general, las CDN son más eficaces para hospedar activos _estáticos_ o activos que no cambian con mucha frecuencia.</span><span class="sxs-lookup"><span data-stu-id="a808f-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="a808f-150">Una buena regla general es identificar los archivos que cumplen algunas o todas estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="a808f-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="a808f-151">Archivos estáticos incrustados en una página (como scripts e imágenes) que pueden tener un impacto incremental significativo en los tiempos de carga de la página</span><span class="sxs-lookup"><span data-stu-id="a808f-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="a808f-152">Archivos grandes como archivos ejecutables y archivos de instalación</span><span class="sxs-lookup"><span data-stu-id="a808f-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="a808f-153">Bibliotecas de recursos que admiten código del lado cliente</span><span class="sxs-lookup"><span data-stu-id="a808f-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="a808f-154">Por ejemplo, los archivos pequeños que se solicitan repetidamente como imágenes de sitio y scripts pueden mejorar significativamente el rendimiento de representación del sitio y reducir de forma incremental la carga en los sitios de SharePoint Online al agregarlos a un origen de red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="a808f-155">Los archivos más grandes, como los ejecutables de instalación, se pueden descargar de la red CDN, lo que proporciona un impacto positivo en el rendimiento y una reducción posterior de la carga en el sitio de SharePoint Online, incluso si no se tiene acceso a ellos con tanta frecuencia.</span><span class="sxs-lookup"><span data-stu-id="a808f-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="a808f-156">La mejora del rendimiento por archivo depende de muchos factores, como la proximidad del cliente al extremo de red CDN más cercano, las condiciones transitorias en la red local, etc.</span><span class="sxs-lookup"><span data-stu-id="a808f-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="a808f-157">Muchos archivos estáticos son bastante pequeños y se pueden descargar desde Office 365 en menos de un segundo.</span><span class="sxs-lookup"><span data-stu-id="a808f-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="a808f-158">Sin embargo, una página web puede contener muchos archivos incrustados con un tiempo de descarga acumulado de varios segundos.</span><span class="sxs-lookup"><span data-stu-id="a808f-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="a808f-159">El servicio de estos archivos desde la red CDN puede reducir significativamente el tiempo de carga general de la página.</span><span class="sxs-lookup"><span data-stu-id="a808f-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="a808f-160">Vea [¿Qué mejoras de rendimiento proporciona una RED CDN?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) para ver un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a808f-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="a808f-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="a808f-162">Determinar dónde desea almacenar los activos</span><span class="sxs-lookup"><span data-stu-id="a808f-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="a808f-163">La red CDN recupera los activos de una ubicación denominada _origen_.</span><span class="sxs-lookup"><span data-stu-id="a808f-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="a808f-164">Un origen puede ser un sitio de SharePoint, una biblioteca de documentos o una carpeta a la que una dirección URL puede tener acceso.</span><span class="sxs-lookup"><span data-stu-id="a808f-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="a808f-165">Tiene una gran flexibilidad al especificar orígenes para su organización.</span><span class="sxs-lookup"><span data-stu-id="a808f-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="a808f-166">Por ejemplo, puede especificar varios orígenes o un único origen donde desea colocar todos los activos de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="a808f-167">Puede elegir tener orígenes públicos o privados para su organización.</span><span class="sxs-lookup"><span data-stu-id="a808f-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="a808f-168">La mayoría de las organizaciones elegirán implementar una combinación de las dos.</span><span class="sxs-lookup"><span data-stu-id="a808f-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="a808f-169">Puede crear un nuevo contenedor para sus orígenes, como carpetas o bibliotecas de documentos, y agregar archivos que desee que estén disponibles desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="a808f-170">Este es un buen enfoque si tiene un conjunto específico de activos que desea que estén disponibles desde la red CDN y desea restringir el conjunto de activos de CDN solo a esos archivos en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="a808f-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="a808f-171">También puede configurar una colección de sitios, un sitio, una biblioteca o una carpeta existentes como origen, lo que hará que todos los activos elegibles del contenedor estén disponibles desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="a808f-172">Antes de agregar un contenedor existente como origen, es importante asegurarse de que está al tanto de su contenido y permisos para que no exponga de forma involuntaria los activos al acceso anónimo o a usuarios no autorizados.</span><span class="sxs-lookup"><span data-stu-id="a808f-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="a808f-173">Puede definir directivas _de CDN para_ excluir contenido de sus orígenes de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="a808f-174">Las directivas de CDN excluyen activos en  orígenes públicos o privados por atributos como el tipo de archivo y la clasificación de _sitios,_ y se aplican a todos los orígenes del CdnType (privado o público) que especifique en la directiva.</span><span class="sxs-lookup"><span data-stu-id="a808f-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="a808f-175">Por ejemplo, si agrega un origen privado que consta de un sitio que contiene varios  subsitios, puede definir una directiva para excluir sitios marcados como confidenciales para que el contenido de los sitios con esa clasificación aplicada no se pueda servir desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="a808f-176">La directiva se aplicará al contenido de _todos los_ orígenes privados que haya agregado a la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="a808f-177">Tenga en cuenta que, a mayor número de orígenes, mayor será el impacto en el tiempo que tarda el servicio cdn en procesar las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="a808f-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="a808f-178">Se recomienda limitar el número de orígenes tanto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="a808f-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="a808f-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="a808f-180">Elegir si cada origen debe ser público o privado</span><span class="sxs-lookup"><span data-stu-id="a808f-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="a808f-181">Al identificar un origen, se especifica si se debe hacer público _o_ _privado_.</span><span class="sxs-lookup"><span data-stu-id="a808f-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="a808f-182">El acceso a los activos de RED CDN en orígenes públicos es anónimo y el contenido de la red CDN en orígenes privados se protege mediante tokens generados dinámicamente para mayor seguridad.</span><span class="sxs-lookup"><span data-stu-id="a808f-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="a808f-183">Independientemente de la opción que elija, Microsoft realiza todo el trabajo pesado para usted cuando se trata de la administración de la propia RED CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="a808f-184">Además, puede cambiar de opinión más adelante, después de configurar la red CDN e identificar sus orígenes.</span><span class="sxs-lookup"><span data-stu-id="a808f-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="a808f-185">Las opciones públicas y privadas proporcionan ganancias de rendimiento similares, pero cada una tiene atributos y ventajas únicos.</span><span class="sxs-lookup"><span data-stu-id="a808f-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="a808f-186">**Los** orígenes públicos dentro de la RED CDN de Office 365 son accesibles de forma anónima y cualquier persona que tenga la dirección URL del activo puede acceder a los activos hospedados.</span><span class="sxs-lookup"><span data-stu-id="a808f-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="a808f-187">Como el acceso al contenido en orígenes públicos es anónimo, solo debe usarlos para almacenar en caché contenido genérico y no confidencial, como archivos javascript, scripts, iconos e imágenes.</span><span class="sxs-lookup"><span data-stu-id="a808f-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as javascript files, scripts, icons and images.</span></span>

<span data-ttu-id="a808f-188">**Los** orígenes privados dentro de la RED CDN de Office 365 proporcionan acceso privado al contenido del usuario, como bibliotecas de documentos de SharePoint Online, sitios e imágenes propietarias.</span><span class="sxs-lookup"><span data-stu-id="a808f-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="a808f-189">El acceso al contenido en orígenes privados está protegido por tokens generados dinámicamente para que solo puedan acceder a él los usuarios con permisos para la biblioteca de documentos original o la ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="a808f-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="a808f-190">Los orígenes privados de la RED CDN de Office 365 solo se pueden usar para el contenido de SharePoint Online y solo puede tener acceso a activos en orígenes privados mediante el redireccionamiento desde el inquilino de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a808f-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="a808f-191">Puede obtener más información sobre cómo funciona el acceso de la RED CDN a los activos de un origen privado [en Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span><span class="sxs-lookup"><span data-stu-id="a808f-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="a808f-192">Atributos y ventajas de hospedar activos en orígenes públicos</span><span class="sxs-lookup"><span data-stu-id="a808f-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="a808f-193">Cualquier persona puede acceder a los activos expuestos en un origen público de forma anónima.</span><span class="sxs-lookup"><span data-stu-id="a808f-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="a808f-194">Nunca debe colocar recursos que contengan información de usuario o que se consideren confidenciales para su organización en un origen público.</span><span class="sxs-lookup"><span data-stu-id="a808f-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>
+ <span data-ttu-id="a808f-195">Si elimina un activo de un origen público, el activo podría continuar disponible durante un máximo de 30 días desde la memoria caché. Sin embargo, se invalidarán los vínculos a los activos en la red CDN en 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a808f-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>
+ <span data-ttu-id="a808f-196">Si hospeda hojas de estilo (archivos CSS) en un origen público, puede usar las rutas relativas y URI dentro del código.</span><span class="sxs-lookup"><span data-stu-id="a808f-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="a808f-197">Esto significa que puede hacer referencia a la ubicación de las imágenes de fondo y otros objetos con respecto a la ubicación del activo que está llamando.</span><span class="sxs-lookup"><span data-stu-id="a808f-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>
+ <span data-ttu-id="a808f-198">Aunque puede crear la dirección URL de un origen público, debe proceder con precaución y asegurarse de usar la propiedad de contexto de página y seguir las instrucciones para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="a808f-198">While you can construct a public origin's URL, you should proceed with caution and ensure you utilize the page context property and follow the guidance for doing so.</span></span> <span data-ttu-id="a808f-199">El motivo de esto es que, si no está disponible el acceso a la red CDN, la dirección URL no resolverá automáticamente su organización en SharePoint Online y podría producir vínculos rotos y otros errores.</span><span class="sxs-lookup"><span data-stu-id="a808f-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span> <span data-ttu-id="a808f-200">La dirección URL también está sujeta a cambios, por lo que no debe codificarse de forma sencilla en su valor actual.</span><span class="sxs-lookup"><span data-stu-id="a808f-200">The URL is also subject to change wich is why it should not just be hard coded to its current value.</span></span>
+ <span data-ttu-id="a808f-201">Los tipos de archivo predeterminados que se incluyen para orígenes públicos son .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff y .woff2.</span><span class="sxs-lookup"><span data-stu-id="a808f-201">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="a808f-202">Puede especificar tipos de archivo adicionales.</span><span class="sxs-lookup"><span data-stu-id="a808f-202">You can specify additional file types.</span></span>
+ <span data-ttu-id="a808f-203">Puede configurar una directiva para excluir los activos identificados por las clasificaciones de sitios que especifique.</span><span class="sxs-lookup"><span data-stu-id="a808f-203">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="a808f-204">Por ejemplo, puede elegir excluir todos los activos que están marcados como restringidos o confidenciales aunque sean un tipo de archivo permitido y se encuentren en un origen público.</span><span class="sxs-lookup"><span data-stu-id="a808f-204">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="a808f-205">Atributos y ventajas de hospedar activos en orígenes privados</span><span class="sxs-lookup"><span data-stu-id="a808f-205">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="a808f-206">Los orígenes privados solo se pueden usar para activos de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a808f-206">Private origins can only be used for SharePoint Online assets.</span></span>
+ <span data-ttu-id="a808f-207">Los usuarios solo pueden obtener acceso a los activos desde un origen privado si tienen permisos para acceder al contenedor.</span><span class="sxs-lookup"><span data-stu-id="a808f-207">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="a808f-208">Se impide el acceso anónimo a estos activos.</span><span class="sxs-lookup"><span data-stu-id="a808f-208">Anonymous access to these assets is prevented.</span></span>
+ <span data-ttu-id="a808f-209">Los activos en orígenes privados se deben hacer referencia desde el inquilino de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a808f-209">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="a808f-210">El acceso directo a activos de RED CDN privados no funciona.</span><span class="sxs-lookup"><span data-stu-id="a808f-210">Direct access to private CDN assets does not work.</span></span>
+ <span data-ttu-id="a808f-211">Si quita un activo del origen privado, el activo puede seguir estando disponible hasta una hora desde la memoria caché; sin embargo, invalidaremos los vínculos al activo en la RED CDN en un plazo de 15 minutos desde la eliminación del activo.</span><span class="sxs-lookup"><span data-stu-id="a808f-211">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>
+ <span data-ttu-id="a808f-212">Los tipos de archivo predeterminados que se incluyen en el origen privado son .gif, .ico, .jpeg, .jpg, .js y .png.</span><span class="sxs-lookup"><span data-stu-id="a808f-212">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="a808f-213">Puede especificar tipos de archivo adicionales.</span><span class="sxs-lookup"><span data-stu-id="a808f-213">You can specify additional file types.</span></span>
+ <span data-ttu-id="a808f-214">Al igual que con los orígenes públicos, puede configurar una directiva para excluir los activos identificados por las clasificaciones de sitios que especifique incluso si usa caracteres comodín para incluir todos los activos de una carpeta o biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="a808f-214">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="a808f-215">Para obtener más información sobre por qué usar la red CDN de Office 365, los conceptos generales de CDN y otras CDN de Microsoft que puede usar con su inquilino de Office 365, vea [Content Delivery Networks](content-delivery-networks.md).</span><span class="sxs-lookup"><span data-stu-id="a808f-215">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="a808f-216">Orígenes de red CDN predeterminados</span><span class="sxs-lookup"><span data-stu-id="a808f-216">Default CDN origins</span></span>

<span data-ttu-id="a808f-217">A menos que especifique lo contrario, Office 365 configura algunos orígenes predeterminados cuando habilita la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a808f-217">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="a808f-218">Si inicialmente opta por no aprovisionarlos, puede agregar estos orígenes después de completar la configuración.</span><span class="sxs-lookup"><span data-stu-id="a808f-218">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="a808f-219">A menos que comprenda las consecuencias de omitir la configuración de orígenes predeterminados y tenga una razón específica para hacerlo, debe permitir que se cree al habilitar la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-219">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="a808f-220">Orígenes de CDN privados predeterminados:</span><span class="sxs-lookup"><span data-stu-id="a808f-220">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="a808f-221">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="a808f-221">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="a808f-222">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="a808f-222">\*/siteassets</span></span>

<span data-ttu-id="a808f-223">Orígenes de cdn públicos predeterminados:</span><span class="sxs-lookup"><span data-stu-id="a808f-223">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="a808f-224">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="a808f-224">\*/masterpage</span></span>
+ <span data-ttu-id="a808f-225">\*Biblioteca /style</span><span class="sxs-lookup"><span data-stu-id="a808f-225">\*/style library</span></span>
+ <span data-ttu-id="a808f-226">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="a808f-226">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="a808f-227">_clientsideassets_ es un origen público predeterminado que se agregó al servicio de red CDN de Office 365 en diciembre de 2017.</span><span class="sxs-lookup"><span data-stu-id="a808f-227">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="a808f-228">Este origen debe estar presente para que las soluciones de SharePoint Framework en la red CDN funcionen.</span><span class="sxs-lookup"><span data-stu-id="a808f-228">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="a808f-229">Si habilitó la red CDN de Office 365 antes de diciembre de 2017 o si omitió la configuración de orígenes predeterminados al habilitar la red CDN, puede agregar manualmente este origen.</span><span class="sxs-lookup"><span data-stu-id="a808f-229">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="a808f-230">Para obtener más información, vea [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span><span class="sxs-lookup"><span data-stu-id="a808f-230">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="a808f-231"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-231"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="a808f-232">Configurar y configurar la red CDN de Office 365 mediante el Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a808f-232">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="a808f-233">Los procedimientos de esta sección requieren que use el Shell de administración de SharePoint Online para conectarse a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a808f-233">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="a808f-234">Para obtener instrucciones, consulte [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="a808f-234">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="a808f-235">Complete estos pasos para configurar y configurar la red CDN para hospedar los activos en SharePoint Online mediante el Shell de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a808f-235">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="a808f-236">Haga clic para expandir</span><span class="sxs-lookup"><span data-stu-id="a808f-236">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="a808f-237">Permitir que su organización use la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-237">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="a808f-238">Antes de realizar cambios en la configuración de la red CDN del inquilino, debe recuperar el estado actual de la configuración de la red CDN privada en su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a808f-238">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="a808f-239">Conéctese al espacio empresarial mediante el Shell de administración de SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="a808f-239">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="a808f-240">Ahora use el cmdlet **Get-SPOTenantCdnEnabled** para recuperar la configuración de estado de la red CDN del inquilino:</span><span class="sxs-lookup"><span data-stu-id="a808f-240">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="a808f-241">El estado de la red CDN del CdnType especificado se mostrará en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="a808f-241">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="a808f-242">Use el cmdlet **Set-SPOTenantCdnEnabled** para permitir que su organización use la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a808f-242">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="a808f-243">Puede permitir que su organización use orígenes públicos, orígenes privados o ambos a la vez.</span><span class="sxs-lookup"><span data-stu-id="a808f-243">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="a808f-244">También puede configurar la red CDN para omitir la configuración de orígenes predeterminados al habilitarla.</span><span class="sxs-lookup"><span data-stu-id="a808f-244">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="a808f-245">Siempre puede agregar estos orígenes más adelante, como se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="a808f-245">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="a808f-246">En Windows Powershell para SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="a808f-246">In Windows Powershell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="a808f-247">Por ejemplo, para permitir que la organización use orígenes públicos y privados, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a808f-247">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="a808f-248">Para permitir que la organización use orígenes públicos y privados, pero omitir la configuración de los orígenes predeterminados, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a808f-248">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="a808f-249">Consulte Orígenes de [cdn](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) predeterminados para obtener información sobre los orígenes que se aprovisionan de forma predeterminada al habilitar la red CDN de Office 365 y el posible impacto de omitir la configuración de orígenes predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a808f-249">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="a808f-250">Para permitir que la organización use orígenes públicos, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a808f-250">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="a808f-251">Para permitir que la organización use orígenes privados, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a808f-251">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="a808f-252">Para obtener más información acerca de este cmdlet, [vea Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span><span class="sxs-lookup"><span data-stu-id="a808f-252">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

<span data-ttu-id="a808f-253"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-253"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="a808f-254">Cambiar la lista de tipos de archivo para incluir en la red CDN de Office 365 (opcional)</span><span class="sxs-lookup"><span data-stu-id="a808f-254">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="a808f-255">Al definir tipos de archivo mediante el cmdlet **Set-SPOTenantCdnPolicy,** se sobrescribe la lista definida actualmente.</span><span class="sxs-lookup"><span data-stu-id="a808f-255">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="a808f-256">Si desea agregar tipos de archivo adicionales a la lista, use primero el cmdlet para averiguar qué tipos de archivo ya están permitidos e incluirlos en la lista junto con los nuevos.</span><span class="sxs-lookup"><span data-stu-id="a808f-256">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="a808f-257">Use el cmdlet **Set-SPOTenantCdnPolicy** para definir tipos de archivo estáticos que pueden hospedarse en orígenes públicos y privados en la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-257">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="a808f-258">De forma predeterminada, se permiten tipos de activos comunes, como .css, .gif, .jpg y .js.</span><span class="sxs-lookup"><span data-stu-id="a808f-258">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="a808f-259">En Windows PowerShell para SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="a808f-259">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="a808f-260">Por ejemplo, para habilitar la red CDN para hospedar archivos .css y .png, escriba el comando:</span><span class="sxs-lookup"><span data-stu-id="a808f-260">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="a808f-261">Para ver qué tipos de archivo permite actualmente la red CDN, use el cmdlet **Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="a808f-261">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="a808f-262">Para obtener más información acerca de estos cmdlets, vea [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) y [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span><span class="sxs-lookup"><span data-stu-id="a808f-262">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="a808f-263"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-263"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="a808f-264">Cambiar la lista de clasificaciones de sitios que desea excluir de la red CDN de Office 365 (opcional)</span><span class="sxs-lookup"><span data-stu-id="a808f-264">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="a808f-265">Cuando se excluyen las clasificaciones de sitios mediante el cmdlet **Set-SPOTenantCdnPolicy,** se sobrescribe la lista definida actualmente.</span><span class="sxs-lookup"><span data-stu-id="a808f-265">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="a808f-266">Si desea excluir clasificaciones de sitios adicionales, use el cmdlet primero para averiguar qué clasificaciones ya están excluidas y, a continuación, agregarlas junto con las nuevas.</span><span class="sxs-lookup"><span data-stu-id="a808f-266">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="a808f-267">Use el cmdlet **Set-SPOTenantCdnPolicy** para excluir las clasificaciones de sitio que no desee que estén disponibles en la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-267">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="a808f-268">De forma predeterminada, no se excluyen clasificaciones de sitio.</span><span class="sxs-lookup"><span data-stu-id="a808f-268">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="a808f-269">En Windows PowerShell para SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="a808f-269">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="a808f-270">Para ver qué clasificaciones de sitios están restringidas actualmente, use el cmdlet **Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="a808f-270">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="a808f-271">Las propiedades que se devolverán _son IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ y _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="a808f-271">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="a808f-272">La _propiedad IncludeFileExtensions_ contiene la lista de extensiones de archivo que se van a servir desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-272">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="a808f-273">Las extensiones de archivo predeterminadas son diferentes entre lo público y lo privado.</span><span class="sxs-lookup"><span data-stu-id="a808f-273">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="a808f-274">La _propiedad ExcludeRestrictedSiteClassifications_ contiene las clasificaciones de sitio que desea excluir de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-274">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="a808f-275">Por ejemplo, puede excluir  sitios marcados como confidenciales para que el contenido de los sitios con esa clasificación aplicada no se pueda servir desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-275">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="a808f-276">La _propiedad ExcludeIfNoScriptDisabled_ excluye el contenido de la red CDN en función de la configuración del atributo _NoScript_ de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="a808f-276">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="a808f-277">De forma predeterminada, _el atributo NoScript_ se establece en **Habilitado** para sitios _modernos_ y **Deshabilitado** para _sitios clásicos._</span><span class="sxs-lookup"><span data-stu-id="a808f-277">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="a808f-278">Esto depende de la configuración del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="a808f-278">This depends on your tenant settings.</span></span>

<span data-ttu-id="a808f-279">Para obtener más información acerca de estos cmdlets, vea [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) y [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span><span class="sxs-lookup"><span data-stu-id="a808f-279">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="a808f-280"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-280"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="a808f-281">Agregar un origen para los activos</span><span class="sxs-lookup"><span data-stu-id="a808f-281">Add an origin for your assets</span></span>

<span data-ttu-id="a808f-282">Use el cmdlet **Add-SPOTenantCdnOrigin** para definir un origen.</span><span class="sxs-lookup"><span data-stu-id="a808f-282">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="a808f-283">Puede definir varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="a808f-283">You can define multiple origins.</span></span> <span data-ttu-id="a808f-284">El origen es una dirección URL que apunta a una biblioteca de SharePoint o la carpeta que contiene los activos que desea que se hospeden mediante la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-284">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a808f-285">Nunca debe colocar recursos que contengan información de usuario o que se consideren confidenciales para su organización en un origen público.</span><span class="sxs-lookup"><span data-stu-id="a808f-285">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="a808f-286">El valor de _path es_ la ruta de acceso relativa a la biblioteca o carpeta que contiene los activos.</span><span class="sxs-lookup"><span data-stu-id="a808f-286">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="a808f-287">Puede usar caracteres comodín además de rutas relativas.</span><span class="sxs-lookup"><span data-stu-id="a808f-287">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="a808f-288">Los orígenes admiten caracteres comodín anteponer a la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="a808f-288">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="a808f-289">Esto le permite crear orígenes que abarcan varios sitios.</span><span class="sxs-lookup"><span data-stu-id="a808f-289">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="a808f-290">Por ejemplo, para incluir todos los activos en la carpeta masterpages de todos los sitios como origen público dentro de la red CDN, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a808f-290">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="a808f-291">El modificador de caracteres comodín \* solo se puede usar al principio de la ruta de acceso y coincidirá con todos los **/** segmentos de dirección URL en la dirección URL especificada.</span><span class="sxs-lookup"><span data-stu-id="a808f-291">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="a808f-292">La ruta de acceso puede apuntar a una biblioteca de documentos, una carpeta o un sitio.</span><span class="sxs-lookup"><span data-stu-id="a808f-292">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="a808f-293">Por ejemplo, la ruta _\*/site1_ coincidirá con todas las bibliotecas de documentos del sitio.</span><span class="sxs-lookup"><span data-stu-id="a808f-293">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="a808f-294">Puede agregar un origen con una ruta de acceso relativa específica.</span><span class="sxs-lookup"><span data-stu-id="a808f-294">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="a808f-295">No se puede agregar un origen mediante la ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="a808f-295">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="a808f-296">En este ejemplo se agrega un origen privado de la biblioteca siteassets en un sitio específico:</span><span class="sxs-lookup"><span data-stu-id="a808f-296">This example adds a private origin of the siteassets library on a specific site:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="a808f-297">En este ejemplo se agrega un origen privado de la _carpeta folder1_ de la biblioteca de activos de sitio de la colección de sitios:</span><span class="sxs-lookup"><span data-stu-id="a808f-297">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="a808f-298">Si hay un espacio en la ruta de acceso, puede rodear la ruta entre comillas dobles o reemplazar el espacio con la codificación de dirección URL %20.</span><span class="sxs-lookup"><span data-stu-id="a808f-298">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="a808f-299">En los ejemplos siguientes se agrega un origen privado de la _carpeta 1_ de la biblioteca de activos de sitio de la colección de sitios:</span><span class="sxs-lookup"><span data-stu-id="a808f-299">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="a808f-300">Para obtener más información acerca de este comando y su sintaxis, [vea Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="a808f-300">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

> [!NOTE]
> <span data-ttu-id="a808f-301">En orígenes privados, los activos que se comparten desde un origen deben tener una versión principal publicada para poder acceder a ellos desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-301">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="a808f-302">Una vez ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="a808f-302">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="a808f-303">Esto puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a808f-303">This can take up to 15 minutes.</span></span>

<span data-ttu-id="a808f-304"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-304"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="a808f-305">Ejemplo: configurar un origen público para las páginas maestras y para la biblioteca de estilos para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a808f-305">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="a808f-306">Normalmente, estos orígenes se establecen automáticamente cuando habilita la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a808f-306">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="a808f-307">Sin embargo, si desea habilitarlos manualmente, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a808f-307">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="a808f-308">Use el cmdlet **Add-SPOTenantCdnOrigin** para definir la biblioteca de estilos como un origen público.</span><span class="sxs-lookup"><span data-stu-id="a808f-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="a808f-309">Use el cmdlet **Add-SPOTenantCdnOrigin** para definir las páginas maestras como un origen público.</span><span class="sxs-lookup"><span data-stu-id="a808f-309">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="a808f-310">Para obtener más información acerca de este comando y su sintaxis, [vea Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="a808f-310">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="a808f-311">Una vez ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="a808f-311">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="a808f-312">Esto puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a808f-312">This can take up to 15 minutes.</span></span>

<span data-ttu-id="a808f-313"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-313"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="a808f-314">Ejemplo: configurar un origen privado para los activos del sitio, páginas de sitio e imágenes de publicación para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a808f-314">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="a808f-315">Use el cmdlet **Add-SPOTenantCdnOrigin** para definir la carpeta de activos del sitio como un origen privado.</span><span class="sxs-lookup"><span data-stu-id="a808f-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="a808f-316">Use el cmdlet **Add-SPOTenantCdnOrigin** para definir la carpeta de páginas del sitio como un origen privado.</span><span class="sxs-lookup"><span data-stu-id="a808f-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="a808f-317">Use el cmdlet **Add-SPOTenantCdnOrigin** para definir la carpeta de imágenes de publicación como un origen privado.</span><span class="sxs-lookup"><span data-stu-id="a808f-317">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="a808f-318">Para obtener más información acerca de este comando y su sintaxis, [vea Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="a808f-318">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="a808f-319">Una vez ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="a808f-319">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="a808f-320">Esto puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a808f-320">This can take up to 15 minutes.</span></span>

<span data-ttu-id="a808f-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="a808f-322">Ejemplo: Configurar un origen privado para una colección de sitios para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a808f-322">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="a808f-323">Use el cmdlet **Add-SPOTenantCdnOrigin** para definir una colección de sitios como un origen privado.</span><span class="sxs-lookup"><span data-stu-id="a808f-323">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="a808f-324">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a808f-324">For example:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="a808f-325">Para obtener más información acerca de este comando y su sintaxis, [vea Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="a808f-325">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>
  
<span data-ttu-id="a808f-326">Una vez ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="a808f-326">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="a808f-327">Es posible que vea un _mensaje pendiente de_ configuración que se espera a medida que el inquilino de SharePoint Online se conecta al servicio de red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-327">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="a808f-328">Esto puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a808f-328">This can take up to 15 minutes.</span></span>

<span data-ttu-id="a808f-329"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-329"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="a808f-330">Administrar la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-330">Manage the Office 365 CDN</span></span>

<span data-ttu-id="a808f-331">Una vez que haya configurado la red CDN, puede realizar cambios en la configuración a medida que actualiza el contenido o a medida que cambian sus necesidades, como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="a808f-331">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="a808f-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="a808f-333">Agregar, actualizar o quitar activos de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-333">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="a808f-334">Una vez que hayas completado los pasos de configuración, puedes agregar nuevos activos y actualizar o quitar activos existentes cuando quieras.</span><span class="sxs-lookup"><span data-stu-id="a808f-334">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="a808f-335">Solo tiene que realizar los cambios en los activos de la carpeta o biblioteca de SharePoint que identificó como origen.</span><span class="sxs-lookup"><span data-stu-id="a808f-335">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="a808f-336">Si agrega un nuevo activo, estará disponible a través de la red CDN inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="a808f-336">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="a808f-337">Sin embargo, si actualiza el activo, la nueva copia tardaría hasta 15 minutos en propagarse y estar disponible en la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-337">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="a808f-338">Si necesita recuperar la ubicación del origen, puede usar el cmdlet **Get-SPOTenantCdnOrigins.**</span><span class="sxs-lookup"><span data-stu-id="a808f-338">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="a808f-339">Para obtener información sobre cómo usar este cmdlet, [vea Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).</span><span class="sxs-lookup"><span data-stu-id="a808f-339">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).</span></span>

<span data-ttu-id="a808f-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="a808f-341">Quitar un origen de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-341">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="a808f-342">Puede quitar el acceso a una carpeta o biblioteca de SharePoint que identificó como origen.</span><span class="sxs-lookup"><span data-stu-id="a808f-342">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="a808f-343">Para ello, use el cmdlet **Remove-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="a808f-343">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="a808f-344">Para obtener información sobre cómo usar este cmdlet, vea [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="a808f-344">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="a808f-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="a808f-346">Modificar un origen en la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-346">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="a808f-347">No puede modificar un origen que haya creado.</span><span class="sxs-lookup"><span data-stu-id="a808f-347">You cannot modify an origin you've created.</span></span> <span data-ttu-id="a808f-348">En su lugar, quite el origen y, a continuación, agregue uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="a808f-348">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="a808f-349">Para obtener más información, vea Para quitar un origen de la red CDN de [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) y [Para agregar un origen para los activos](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span><span class="sxs-lookup"><span data-stu-id="a808f-349">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="a808f-350"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-350"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="a808f-351">Deshabilitar la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-351">Disable the Office 365 CDN</span></span>

<span data-ttu-id="a808f-352">Use el cmdlet **Set-SPOTenantCdnEnabled** para deshabilitar la red CDN de su organización.</span><span class="sxs-lookup"><span data-stu-id="a808f-352">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="a808f-353">Si tiene los orígenes públicos y privados habilitados para la red CDN, debe ejecutar el cmdlet dos veces como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a808f-353">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="a808f-354">Para deshabilitar el uso de orígenes públicos en la red CDN, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a808f-354">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="a808f-355">Para deshabilitar el uso de los orígenes privados en la red CDN, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a808f-355">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="a808f-356">Para obtener más información acerca de este cmdlet, [vea Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span><span class="sxs-lookup"><span data-stu-id="a808f-356">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

</details>

<span data-ttu-id="a808f-357"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-357"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="a808f-358">Configurar y configurar la red CDN de Office 365 mediante PowerShell pnP</span><span class="sxs-lookup"><span data-stu-id="a808f-358">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="a808f-359">Los procedimientos de esta sección requieren que use PnP PowerShell para conectarse a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a808f-359">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="a808f-360">Para obtener instrucciones, consulte [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span><span class="sxs-lookup"><span data-stu-id="a808f-360">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="a808f-361">Complete estos pasos para configurar y configurar la RED CDN para hospedar sus activos en SharePoint Online con PnP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a808f-361">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="a808f-362">Haga clic para expandir</span><span class="sxs-lookup"><span data-stu-id="a808f-362">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="a808f-363">Permitir que su organización use la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-363">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="a808f-364">Antes de realizar cambios en la configuración de la red CDN del inquilino, debe recuperar el estado actual de la configuración de la red CDN privada en su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a808f-364">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="a808f-365">Conéctese al espacio empresarial con PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a808f-365">Connect to your tenant using PnP PowerShell:</span></span>

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="a808f-366">Ahora use el cmdlet **Get-PnPTenantCdnEnabled** para recuperar la configuración de estado de la red CDN del inquilino:</span><span class="sxs-lookup"><span data-stu-id="a808f-366">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="a808f-367">El estado de la red CDN del CdnType especificado se mostrará en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="a808f-367">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="a808f-368">Use el cmdlet **Set-PnPTenantCdnEnabled** para permitir que su organización use la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a808f-368">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="a808f-369">Puede permitir que su organización use orígenes públicos, orígenes privados o ambos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="a808f-369">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="a808f-370">También puede configurar la red CDN para omitir la configuración de orígenes predeterminados al habilitarla.</span><span class="sxs-lookup"><span data-stu-id="a808f-370">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="a808f-371">Siempre puede agregar estos orígenes más adelante, como se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="a808f-371">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="a808f-372">En PowerShell pnP:</span><span class="sxs-lookup"><span data-stu-id="a808f-372">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="a808f-373">Por ejemplo, para permitir que la organización use orígenes públicos y privados, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a808f-373">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="a808f-374">Para permitir que la organización use orígenes públicos y privados, pero omitir la configuración de los orígenes predeterminados, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a808f-374">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="a808f-375">Consulte Orígenes de [cdn](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) predeterminados para obtener información sobre los orígenes que se aprovisionan de forma predeterminada al habilitar la red CDN de Office 365 y el posible impacto de omitir la configuración de orígenes predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a808f-375">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="a808f-376">Para permitir que la organización use orígenes públicos, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a808f-376">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="a808f-377">Para permitir que la organización use orígenes privados, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a808f-377">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="a808f-378">Para obtener más información acerca de este cmdlet, [vea Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span><span class="sxs-lookup"><span data-stu-id="a808f-378">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="a808f-379"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-379"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="a808f-380">Cambiar la lista de tipos de archivo para incluir en la red CDN de Office 365 (opcional)</span><span class="sxs-lookup"><span data-stu-id="a808f-380">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="a808f-381">Al definir tipos de archivo mediante el cmdlet **Set-PnPTenantCdnPolicy,** se sobrescribe la lista definida actualmente.</span><span class="sxs-lookup"><span data-stu-id="a808f-381">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="a808f-382">Si desea agregar tipos de archivo adicionales a la lista, use primero el cmdlet para averiguar qué tipos de archivo ya están permitidos e incluirlos en la lista junto con los nuevos.</span><span class="sxs-lookup"><span data-stu-id="a808f-382">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="a808f-383">Use el cmdlet **Set-PnPTenantCdnPolicy** para definir tipos de archivo estáticos que pueden hospedarse en orígenes públicos y privados en la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-383">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="a808f-384">De forma predeterminada, se permiten tipos de activos comunes, como .css, .gif, .jpg y .js.</span><span class="sxs-lookup"><span data-stu-id="a808f-384">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="a808f-385">En PowerShell pnP:</span><span class="sxs-lookup"><span data-stu-id="a808f-385">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="a808f-386">Por ejemplo, para habilitar la red CDN para hospedar archivos .css y .png, escriba el comando:</span><span class="sxs-lookup"><span data-stu-id="a808f-386">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="a808f-387">Para ver qué tipos de archivo permite actualmente la red CDN, use el cmdlet **Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="a808f-387">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="a808f-388">Para obtener más información acerca de estos cmdlets, vea [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) y [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span><span class="sxs-lookup"><span data-stu-id="a808f-388">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="a808f-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="a808f-390">Cambiar la lista de clasificaciones de sitios que desea excluir de la red CDN de Office 365 (opcional)</span><span class="sxs-lookup"><span data-stu-id="a808f-390">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="a808f-391">Cuando se excluyen las clasificaciones de sitios mediante el cmdlet **Set-PnPTenantCdnPolicy,** se sobrescribe la lista definida actualmente.</span><span class="sxs-lookup"><span data-stu-id="a808f-391">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="a808f-392">Si desea excluir clasificaciones de sitios adicionales, use el cmdlet primero para averiguar qué clasificaciones ya están excluidas y, a continuación, agregarlas junto con las nuevas.</span><span class="sxs-lookup"><span data-stu-id="a808f-392">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="a808f-393">Use el cmdlet **Set-PnPTenantCdnPolicy** para excluir las clasificaciones de sitios que no desea que estén disponibles a través de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-393">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="a808f-394">De forma predeterminada, no se excluyen clasificaciones de sitio.</span><span class="sxs-lookup"><span data-stu-id="a808f-394">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="a808f-395">En PowerShell pnP:</span><span class="sxs-lookup"><span data-stu-id="a808f-395">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="a808f-396">Para ver qué clasificaciones de sitios están restringidas actualmente, use el cmdlet **Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="a808f-396">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="a808f-397">Las propiedades que se devolverán _son IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ y _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="a808f-397">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="a808f-398">La _propiedad IncludeFileExtensions_ contiene la lista de extensiones de archivo que se van a servir desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-398">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="a808f-399">Las extensiones de archivo predeterminadas son diferentes entre lo público y lo privado.</span><span class="sxs-lookup"><span data-stu-id="a808f-399">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="a808f-400">La _propiedad ExcludeRestrictedSiteClassifications_ contiene las clasificaciones de sitio que desea excluir de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-400">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="a808f-401">Por ejemplo, puede excluir  sitios marcados como confidenciales para que el contenido de los sitios con esa clasificación aplicada no se pueda servir desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-401">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="a808f-402">La _propiedad ExcludeIfNoScriptDisabled_ excluye el contenido de la red CDN en función de la configuración del atributo _NoScript_ de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="a808f-402">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="a808f-403">De forma predeterminada, _el atributo NoScript_ se establece en **Habilitado** para sitios _modernos_ y **Deshabilitado** para _sitios clásicos._</span><span class="sxs-lookup"><span data-stu-id="a808f-403">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="a808f-404">Esto depende de la configuración del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="a808f-404">This depends on your tenant settings.</span></span>

<span data-ttu-id="a808f-405">Para obtener más información acerca de estos cmdlets, vea [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) y [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span><span class="sxs-lookup"><span data-stu-id="a808f-405">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="a808f-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="a808f-407">Agregar un origen para los activos</span><span class="sxs-lookup"><span data-stu-id="a808f-407">Add an origin for your assets</span></span>

<span data-ttu-id="a808f-408">Use el cmdlet **Add-PnPTenantCdnOrigin** para definir un origen.</span><span class="sxs-lookup"><span data-stu-id="a808f-408">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="a808f-409">Puede definir varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="a808f-409">You can define multiple origins.</span></span> <span data-ttu-id="a808f-410">El origen es una dirección URL que apunta a una biblioteca de SharePoint o la carpeta que contiene los activos que desea que se hospeden mediante la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-410">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a808f-411">Nunca debe colocar recursos que contengan información de usuario o que se consideren confidenciales para su organización en un origen público.</span><span class="sxs-lookup"><span data-stu-id="a808f-411">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="a808f-412">El valor de _path es_ la ruta de acceso relativa a la biblioteca o carpeta que contiene los activos.</span><span class="sxs-lookup"><span data-stu-id="a808f-412">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="a808f-413">Puede usar caracteres comodín además de rutas relativas.</span><span class="sxs-lookup"><span data-stu-id="a808f-413">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="a808f-414">Los orígenes admiten caracteres comodín anteponer a la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="a808f-414">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="a808f-415">Esto le permite crear orígenes que abarcan varios sitios.</span><span class="sxs-lookup"><span data-stu-id="a808f-415">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="a808f-416">Por ejemplo, para incluir todos los activos en la carpeta masterpages de todos los sitios como origen público dentro de la red CDN, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a808f-416">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="a808f-417">El modificador de caracteres comodín \* solo se puede usar al principio de la ruta de acceso y coincidirá con todos los **/** segmentos de dirección URL en la dirección URL especificada.</span><span class="sxs-lookup"><span data-stu-id="a808f-417">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="a808f-418">La ruta de acceso puede apuntar a una biblioteca de documentos, una carpeta o un sitio.</span><span class="sxs-lookup"><span data-stu-id="a808f-418">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="a808f-419">Por ejemplo, la ruta _\*/site1_ coincidirá con todas las bibliotecas de documentos del sitio.</span><span class="sxs-lookup"><span data-stu-id="a808f-419">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="a808f-420">Puede agregar un origen con una ruta de acceso relativa específica.</span><span class="sxs-lookup"><span data-stu-id="a808f-420">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="a808f-421">No se puede agregar un origen mediante la ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="a808f-421">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="a808f-422">En este ejemplo se agrega un origen privado de la biblioteca de activos del sitio en un sitio específico:</span><span class="sxs-lookup"><span data-stu-id="a808f-422">This example adds a private origin of the site assets library on a specific site:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="a808f-423">En este ejemplo se agrega un origen privado de la _carpeta folder1_ de la biblioteca de activos de sitio de la colección de sitios:</span><span class="sxs-lookup"><span data-stu-id="a808f-423">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="a808f-424">Si hay un espacio en la ruta de acceso, puede rodear la ruta entre comillas dobles o reemplazar el espacio con la codificación de dirección URL %20.</span><span class="sxs-lookup"><span data-stu-id="a808f-424">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="a808f-425">En los ejemplos siguientes se agrega un origen privado de la _carpeta 1_ de la biblioteca de activos de sitio de la colección de sitios:</span><span class="sxs-lookup"><span data-stu-id="a808f-425">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="a808f-426">Para obtener más información acerca de este comando y su sintaxis, [vea Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="a808f-426">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="a808f-427">En orígenes privados, los activos que se comparten desde un origen deben tener una versión principal publicada para poder acceder a ellos desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-427">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="a808f-428">Una vez ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="a808f-428">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="a808f-429">Esto puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a808f-429">This can take up to 15 minutes.</span></span>

<span data-ttu-id="a808f-430"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-430"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="a808f-431">Ejemplo: configurar un origen público para las páginas maestras y para la biblioteca de estilos para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a808f-431">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="a808f-432">Normalmente, estos orígenes se establecen automáticamente cuando habilita la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a808f-432">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="a808f-433">Sin embargo, si desea habilitarlos manualmente, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a808f-433">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="a808f-434">Use el cmdlet **Add-PnPTenantCdnOrigin** para definir la biblioteca de estilos como un origen público.</span><span class="sxs-lookup"><span data-stu-id="a808f-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="a808f-435">Use el cmdlet **Add-PnPTenantCdnOrigin** para definir las páginas maestras como un origen público.</span><span class="sxs-lookup"><span data-stu-id="a808f-435">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="a808f-436">Para obtener más información acerca de este comando y su sintaxis, [vea Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="a808f-436">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="a808f-437">Una vez ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="a808f-437">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="a808f-438">Esto puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a808f-438">This can take up to 15 minutes.</span></span>

<span data-ttu-id="a808f-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="a808f-440">Ejemplo: configurar un origen privado para los activos del sitio, páginas de sitio e imágenes de publicación para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a808f-440">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="a808f-441">Use el cmdlet **Add-PnPTenantCdnOrigin** para definir la carpeta de activos del sitio como un origen privado.</span><span class="sxs-lookup"><span data-stu-id="a808f-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="a808f-442">Use el cmdlet **Add-PnPTenantCdnOrigin** para definir la carpeta de páginas del sitio como un origen privado.</span><span class="sxs-lookup"><span data-stu-id="a808f-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="a808f-443">Use el cmdlet **Add-PnPTenantCdnOrigin** para definir la carpeta de imágenes de publicación como un origen privado.</span><span class="sxs-lookup"><span data-stu-id="a808f-443">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="a808f-444">Para obtener más información acerca de este comando y su sintaxis, [vea Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="a808f-444">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="a808f-445">Una vez ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="a808f-445">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="a808f-446">Esto puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a808f-446">This can take up to 15 minutes.</span></span>

<span data-ttu-id="a808f-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="a808f-448">Ejemplo: Configurar un origen privado para una colección de sitios para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a808f-448">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="a808f-449">Use el cmdlet **Add-PnPTenantCdnOrigin** para definir una colección de sitios como un origen privado.</span><span class="sxs-lookup"><span data-stu-id="a808f-449">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="a808f-450">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a808f-450">For example:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="a808f-451">Para obtener más información acerca de este comando y su sintaxis, [vea Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="a808f-451">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="a808f-452">Una vez ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="a808f-452">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="a808f-453">Es posible que vea un _mensaje pendiente de_ configuración que se espera a medida que el inquilino de SharePoint Online se conecta al servicio de red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-453">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="a808f-454">Esto puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a808f-454">This can take up to 15 minutes.</span></span>

<span data-ttu-id="a808f-455"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-455"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="a808f-456">Administrar la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-456">Manage the Office 365 CDN</span></span>

<span data-ttu-id="a808f-457">Una vez que haya configurado la red CDN, puede realizar cambios en la configuración a medida que actualiza el contenido o a medida que cambian sus necesidades, como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="a808f-457">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="a808f-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="a808f-459">Agregar, actualizar o quitar activos de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-459">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="a808f-460">Una vez que hayas completado los pasos de configuración, puedes agregar nuevos activos y actualizar o quitar activos existentes cuando quieras.</span><span class="sxs-lookup"><span data-stu-id="a808f-460">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="a808f-461">Solo tiene que realizar los cambios en los activos de la carpeta o biblioteca de SharePoint que identificó como origen.</span><span class="sxs-lookup"><span data-stu-id="a808f-461">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="a808f-462">Si agrega un nuevo activo, estará disponible a través de la red CDN inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="a808f-462">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="a808f-463">Sin embargo, si actualiza el activo, la nueva copia tardaría hasta 15 minutos en propagarse y estar disponible en la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-463">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="a808f-464">Si necesita recuperar la ubicación del origen, puede usar el cmdlet **Get-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="a808f-464">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="a808f-465">Para obtener información sobre cómo usar este cmdlet, [vea Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="a808f-465">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="a808f-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="a808f-467">Quitar un origen de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-467">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="a808f-468">Puede quitar el acceso a una carpeta o biblioteca de SharePoint que identificó como origen.</span><span class="sxs-lookup"><span data-stu-id="a808f-468">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="a808f-469">Para ello, use el cmdlet **Remove-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="a808f-469">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="a808f-470">Para obtener información sobre cómo usar este cmdlet, vea [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="a808f-470">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="a808f-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="a808f-472">Modificar un origen en la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-472">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="a808f-473">No puede modificar un origen que haya creado.</span><span class="sxs-lookup"><span data-stu-id="a808f-473">You cannot modify an origin you've created.</span></span> <span data-ttu-id="a808f-474">En su lugar, quite el origen y, a continuación, agregue uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="a808f-474">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="a808f-475">Para obtener más información, vea Para quitar un origen de la red CDN de [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) y [Para agregar un origen para los activos](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span><span class="sxs-lookup"><span data-stu-id="a808f-475">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="a808f-476"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-476"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="a808f-477">Deshabilitar la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-477">Disable the Office 365 CDN</span></span>

<span data-ttu-id="a808f-478">Use el cmdlet **Set-PnPTenantCdnEnabled** para deshabilitar la red CDN de su organización.</span><span class="sxs-lookup"><span data-stu-id="a808f-478">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="a808f-479">Si tiene los orígenes públicos y privados habilitados para la red CDN, debe ejecutar el cmdlet dos veces como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a808f-479">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="a808f-480">Para deshabilitar el uso de orígenes públicos en la red CDN, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a808f-480">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="a808f-481">Para deshabilitar el uso de los orígenes privados en la red CDN, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a808f-481">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="a808f-482">Para obtener más información acerca de este cmdlet, [vea Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span><span class="sxs-lookup"><span data-stu-id="a808f-482">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="a808f-483"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-483"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="a808f-484">Instalar y configurar la red CDN de Office 365 con la CLI de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-484">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="a808f-485">Los procedimientos de esta sección requieren que haya instalado la [CLI de Office 365](https://aka.ms/o365cli).</span><span class="sxs-lookup"><span data-stu-id="a808f-485">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="a808f-486">A continuación, conéctese a su inquilino de Office 365 mediante el [comando de inicio de](https://pnp.github.io/office365-cli/cmd/login/) sesión.</span><span class="sxs-lookup"><span data-stu-id="a808f-486">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="a808f-487">Complete estos pasos para configurar y configurar la RED CDN para hospedar los activos en SharePoint Online mediante la CLI de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a808f-487">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="a808f-488">Haga clic para expandir</span><span class="sxs-lookup"><span data-stu-id="a808f-488">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="a808f-489">Habilitar la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-489">Enable the Office 365 CDN</span></span>

<span data-ttu-id="a808f-490">Puede administrar el estado de la red CDN de Office 365 en su cuenta empresarial con el comando [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/).</span><span class="sxs-lookup"><span data-stu-id="a808f-490">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="a808f-491">Para habilitar la red CDN pública de Office 365 en su cuenta empresarial ejecute:</span><span class="sxs-lookup"><span data-stu-id="a808f-491">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```sh
spo cdn set --type Public --enabled true
```

<span data-ttu-id="a808f-492">Para habilitar la red CDN de SharePoint de Office 365, ejecute:</span><span class="sxs-lookup"><span data-stu-id="a808f-492">To enable the Office 365 SharePoint CDN, execute:</span></span>

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="a808f-493">Vea el estado actual de la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a808f-493">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="a808f-494">Para comprobar si el tipo concreto de CDN de Office 365 está habilitado o deshabilitado, use el [comando spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)</span><span class="sxs-lookup"><span data-stu-id="a808f-494">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="a808f-495">Para comprobar si la red CDN pública de Office 365 está habilitada, ejecute:</span><span class="sxs-lookup"><span data-stu-id="a808f-495">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="a808f-496">Ver los orígenes de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-496">View the Office 365 CDN origins</span></span>

<span data-ttu-id="a808f-497">Para ver los orígenes configurados actualmente de la red CDN pública de Office 365, ejecute:</span><span class="sxs-lookup"><span data-stu-id="a808f-497">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```sh
spo cdn origin list --type Public
```

<span data-ttu-id="a808f-498">Consulte [Orígenes de cdn](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) predeterminados para obtener información sobre los orígenes que se aprovisionan de forma predeterminada al habilitar la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a808f-498">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="a808f-499">Agregar un origen de red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-499">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a808f-500">Nunca debe colocar recursos que se consideren confidenciales para su organización en una biblioteca de documentos de SharePoint configurada como un origen público.</span><span class="sxs-lookup"><span data-stu-id="a808f-500">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="a808f-501">Use el comando [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) definir un origen de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-501">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="a808f-502">Puede definir varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="a808f-502">You can define multiple origins.</span></span> <span data-ttu-id="a808f-503">El origen es una dirección URL que apunta a una biblioteca de SharePoint o la carpeta que contiene los activos que desea que se hospeden mediante la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-503">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="a808f-504">Dónde `path` es la ruta de acceso relativa a la carpeta que contiene los activos.</span><span class="sxs-lookup"><span data-stu-id="a808f-504">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="a808f-505">Puede usar caracteres comodín además de rutas relativas.</span><span class="sxs-lookup"><span data-stu-id="a808f-505">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="a808f-506">Para incluir todos los activos en la **Galería de páginas maestras** de todos los sitios como origen público, ejecute:</span><span class="sxs-lookup"><span data-stu-id="a808f-506">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```sh
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="a808f-507">Para configurar un origen privado para una colección de sitios específica, ejecute:</span><span class="sxs-lookup"><span data-stu-id="a808f-507">To configure a private origin for a specific site collection, execute:</span></span>

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="a808f-508">Después de agregar un origen de la red CDN, puede tardar hasta 15 minutos para poder recuperar archivos mediante el servicio de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-508">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="a808f-509">Puede comprobar si ya se ha habilitado el origen particular con el comando [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/).</span><span class="sxs-lookup"><span data-stu-id="a808f-509">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="a808f-510">Quitar un origen de red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-510">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="a808f-511">Use el comando [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) para eliminar un origen de la red CDN para el tipo de red CDN especificado.</span><span class="sxs-lookup"><span data-stu-id="a808f-511">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="a808f-512">Para quitar un origen público de la configuración de la red CDN, ejecute:</span><span class="sxs-lookup"><span data-stu-id="a808f-512">To remove a public origin from the CDN configuration, execute:</span></span>

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="a808f-513">Quitar un origen de red CDN no afecta a los archivos almacenados en ninguna biblioteca de documentos que coincida con ese origen.</span><span class="sxs-lookup"><span data-stu-id="a808f-513">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="a808f-514">Si se hace referencia a estos activos mediante su dirección URL de SharePoint, SharePoint volverá automáticamente a la dirección URL original que apunta a la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="a808f-514">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="a808f-515">Sin embargo, si se hace referencia a los activos mediante una dirección URL de red CDN pública, quitar el origen romperá el vínculo y deberá cambiarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="a808f-515">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="a808f-516">Modificar un origen de red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-516">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="a808f-517">No es posible modificar un origen de la red CDN existente.</span><span class="sxs-lookup"><span data-stu-id="a808f-517">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="a808f-518">En su lugar, debe eliminar el origen de la red CDN definido anteriormente con el comando `spo cdn origin remove` y agregar uno nuevo con el comando `spo cdn origin add`.</span><span class="sxs-lookup"><span data-stu-id="a808f-518">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="a808f-519">Cambiar los tipos de archivos que se incluirán en la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-519">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="a808f-520">De forma predeterminada, los siguientes tipos de archivo se incluyen en la red CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff y .woff2_.</span><span class="sxs-lookup"><span data-stu-id="a808f-520">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="a808f-521">Si tiene que incluir otros tipos de archivo en la red CDN, puede cambiar la configuración de la red CDN con el comando [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/).</span><span class="sxs-lookup"><span data-stu-id="a808f-521">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="a808f-522">Al cambiar la lista de tipos de archivo, se sobrescribe la lista definida actualmente.</span><span class="sxs-lookup"><span data-stu-id="a808f-522">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="a808f-523">Si desea incluir otros tipos de archivo, use el comando [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) para averiguar qué tipos de archivos están configurados en este momento.</span><span class="sxs-lookup"><span data-stu-id="a808f-523">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="a808f-524">Para agregar el _tipo de_ archivo JSON a la lista predeterminada de tipos de archivo incluidos en la red CDN pública, ejecute:</span><span class="sxs-lookup"><span data-stu-id="a808f-524">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="a808f-525">Cambiar la lista de clasificaciones de sitio que desea excluir de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-525">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="a808f-526">Use el comando [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) para excluir las clasificaciones de sitio que no desee que estén disponibles en la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-526">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="a808f-527">De forma predeterminada, no se excluyen clasificaciones de sitio.</span><span class="sxs-lookup"><span data-stu-id="a808f-527">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="a808f-528">Al cambiar la lista de clasificaciones de sitio excluidas, se sobrescribe la lista definida actualmente.</span><span class="sxs-lookup"><span data-stu-id="a808f-528">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="a808f-529">Si quiere excluir clasificaciones adicionales, use el comando [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) para averiguar qué clasificaciones están configuradas en este momento.</span><span class="sxs-lookup"><span data-stu-id="a808f-529">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="a808f-530">Para excluir sitios clasificados como _HBI_ de la red CDN pública, ejecute</span><span class="sxs-lookup"><span data-stu-id="a808f-530">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="a808f-531">Deshabilitar la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-531">Disable the Office 365 CDN</span></span>

<span data-ttu-id="a808f-532">Para deshabilitar la red CDN de Office 365, use el comando `spo cdn set`, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a808f-532">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="a808f-533">Uso de los activos de red CDN</span><span class="sxs-lookup"><span data-stu-id="a808f-533">Using your CDN assets</span></span>

<span data-ttu-id="a808f-534">Ahora que ha habilitado la red CDN y ha configurado orígenes y directivas, puede empezar a usar los activos de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-534">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="a808f-535">Esta sección le ayudará a comprender cómo usar direcciones URL de CDN en las páginas y el contenido de SharePoint para que SharePoint redirija las solicitudes de activos en orígenes públicos y privados a la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-535">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="a808f-536">Actualizar vínculos a activos de RED CDN</span><span class="sxs-lookup"><span data-stu-id="a808f-536">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="a808f-537">Uso de activos en orígenes públicos</span><span class="sxs-lookup"><span data-stu-id="a808f-537">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="a808f-538">Uso de activos en orígenes privados</span><span class="sxs-lookup"><span data-stu-id="a808f-538">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="a808f-539">Para obtener información sobre cómo usar la red CDN para hospedar elementos web del lado cliente, vea el tema Hospedar el elemento web del lado cliente desde la red CDN de [Office 365 (parte 4](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)de Hello World).</span><span class="sxs-lookup"><span data-stu-id="a808f-539">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="a808f-540">Si agrega la carpeta _ClientSideAssets_ a la lista de orígenes de **la** red CDN privada, los elementos web personalizados hospedados en CDN no se representarán.</span><span class="sxs-lookup"><span data-stu-id="a808f-540">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="a808f-541">Los archivos usados por elementos web spfx solo pueden usar la red CDN pública y la carpeta ClientSideAssets es un origen predeterminado para la red CDN pública.</span><span class="sxs-lookup"><span data-stu-id="a808f-541">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="a808f-542">Actualizar vínculos a activos de RED CDN</span><span class="sxs-lookup"><span data-stu-id="a808f-542">Updating links to CDN assets</span></span>

<span data-ttu-id="a808f-543">Para usar activos que haya agregado a un origen, solo tiene que actualizar los vínculos al archivo original con la ruta de acceso al archivo en el origen.</span><span class="sxs-lookup"><span data-stu-id="a808f-543">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="a808f-544">Edite la página o el contenido que contiene vínculos a activos que ha agregado a un origen.</span><span class="sxs-lookup"><span data-stu-id="a808f-544">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="a808f-545">También puede usar uno de varios métodos para buscar y reemplazar vínculos globalmente en un sitio o colección de sitios si desea actualizar el vínculo a un activo determinado en cualquier lugar en el que aparezca.</span><span class="sxs-lookup"><span data-stu-id="a808f-545">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="a808f-546">Para cada vínculo a un activo de un origen, reemplace la ruta de acceso por la ruta de acceso al archivo en el origen de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-546">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="a808f-547">Puede usar rutas de acceso relativas.</span><span class="sxs-lookup"><span data-stu-id="a808f-547">You can use relative paths.</span></span>
+ <span data-ttu-id="a808f-548">Guarde la página o el contenido.</span><span class="sxs-lookup"><span data-stu-id="a808f-548">Save the page or content.</span></span>

<span data-ttu-id="a808f-549">Por ejemplo, considere la imagen _/site/SiteAssets/images/image.png_, que ha copiado en la carpeta de biblioteca de documentos _/site/CDN_origins/public/_.</span><span class="sxs-lookup"><span data-stu-id="a808f-549">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="a808f-550">Para usar el activo cdn, reemplace la ruta de acceso original a la ubicación del archivo de imagen por la ruta de acceso al origen para que la nueva dirección URL _/site/CDN_origins/public/image.png_.</span><span class="sxs-lookup"><span data-stu-id="a808f-550">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="a808f-551">Si desea usar la dirección URL completa para el activo en lugar de una ruta de acceso relativa, construya el vínculo de este modo:</span><span class="sxs-lookup"><span data-stu-id="a808f-551">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="a808f-552">En general, no debe codificar las direcciones URL directamente a los activos de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-552">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="a808f-553">Sin embargo, puede crear manualmente direcciones URL para activos en orígenes públicos si es necesario.</span><span class="sxs-lookup"><span data-stu-id="a808f-553">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="a808f-554">Para obtener más información, [vea Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).</span><span class="sxs-lookup"><span data-stu-id="a808f-554">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).</span></span>

<span data-ttu-id="a808f-555">Para obtener información sobre cómo comprobar que los activos se están sirviendo desde la red CDN, vea ¿Cómo confirmo que la red [CDN](use-microsoft-365-cdn-with-spo.md#CDNConfirm) proporciona servicios a los activos? en la sección Solución de problemas de la red CDN de [Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)</span><span class="sxs-lookup"><span data-stu-id="a808f-555">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in the [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) section.</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="a808f-556">Uso de activos en orígenes públicos</span><span class="sxs-lookup"><span data-stu-id="a808f-556">Using assets in public origins</span></span>

<span data-ttu-id="a808f-557">La **característica** de publicación en SharePoint Online reescribe automáticamente las direcciones URL de los activos almacenados en orígenes públicos en sus equivalentes de cdn para que los activos se atenúen desde el servicio de red CDN en lugar de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a808f-557">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="a808f-558">Si el origen se encuentra en un sitio con la característica de publicación habilitada y los activos que desea descargar a la red CDN se encuentran en una de las siguientes categorías, SharePoint reescribirá automáticamente las direcciones URL de los activos del origen, siempre que una directiva de red CDN no excluya el activo.</span><span class="sxs-lookup"><span data-stu-id="a808f-558">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="a808f-559">A continuación, se muestra información general sobre los vínculos que la característica de publicación de SharePoint reescribe automáticamente:</span><span class="sxs-lookup"><span data-stu-id="a808f-559">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="a808f-560">URL de IMG/LINK/CSS en respuestas de HTML de página de publicación clásica</span><span class="sxs-lookup"><span data-stu-id="a808f-560">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="a808f-561">Esto incluye imágenes que han agregado autores en el contenido HTML de una página</span><span class="sxs-lookup"><span data-stu-id="a808f-561">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="a808f-562">URL de las imágenes del elemento web de presentación de la biblioteca de imágenes</span><span class="sxs-lookup"><span data-stu-id="a808f-562">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="a808f-563">Campos de imagen de los resultados de la API de REST SPList (RenderListDataAsStream)</span><span class="sxs-lookup"><span data-stu-id="a808f-563">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="a808f-564">Use la nueva propiedad _ImageFieldsToTryRewriteToCdnUrls_ para proporcionar una lista separada por comas de campos</span><span class="sxs-lookup"><span data-stu-id="a808f-564">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="a808f-565">Admite campos de hipervínculo y campos PublishingImage</span><span class="sxs-lookup"><span data-stu-id="a808f-565">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="a808f-566">Representaciones de imágenes de SharePoint</span><span class="sxs-lookup"><span data-stu-id="a808f-566">SharePoint image renditions</span></span>

<span data-ttu-id="a808f-567">En el diagrama siguiente se muestra el flujo de trabajo cuando SharePoint recibe una solicitud para una página que contiene activos de un origen público.</span><span class="sxs-lookup"><span data-stu-id="a808f-567">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="a808f-568">![Diagrama de flujo de trabajo: recuperación de activos de red CDN de Office 365 desde un origen público](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Flujo de trabajo: recuperación de activos de RED CDN de Office 365 desde un origen público")</span><span class="sxs-lookup"><span data-stu-id="a808f-568">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="a808f-569">Si desea deshabilitar la reescritura automática para direcciones URL específicas de una página, puede desangre la página y agregar el parámetro de cadena de consulta **? NoAutoReWrites=true** al final de cada vínculo que desea deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="a808f-569">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="constructing-cdn-urls-for-public-assets"></a><span data-ttu-id="a808f-570">Construcción de direcciones URL de CDN para activos públicos</span><span class="sxs-lookup"><span data-stu-id="a808f-570">Constructing CDN URLs for public assets</span></span>

<span data-ttu-id="a808f-571">Si  la característica de publicación no está habilitada para un origen público o el activo no es uno de los tipos de vínculo admitidos por la característica de reescritura automática del servicio de red CDN, puede crear manualmente direcciones URL en la ubicación de la red CDN de los activos y usar estas direcciones URL en el contenido.</span><span class="sxs-lookup"><span data-stu-id="a808f-571">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="a808f-572">No puede codificar o construir direcciones URL de CDN en activos de un origen privado porque el token de acceso necesario que forma la última sección de la dirección URL se genera en el momento en que se solicita el recurso.</span><span class="sxs-lookup"><span data-stu-id="a808f-572">You cannot hardcode or construct CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span> <span data-ttu-id="a808f-573">Puede crear la dirección URL de la red CDN pública y la dirección URL no debe estar codificada de forma dura, ya que está sujeta a cambios.</span><span class="sxs-lookup"><span data-stu-id="a808f-573">You can construct the URL for Public CDN and the URL should not be hard coded as it is subject to change.</span></span>

<span data-ttu-id="a808f-574">Para los activos de red CDN pública, el formato de dirección URL tendrá el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="a808f-574">For public CDN assets, the URL format will look like the following:</span></span>

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="a808f-575">Reemplace **TenantHostName** por su nombre de inquilino.</span><span class="sxs-lookup"><span data-stu-id="a808f-575">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="a808f-576">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a808f-576">Example:</span></span>

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```
> [!NOTE]
> <span data-ttu-id="a808f-577">La propiedad de contexto de página debe usarse para construir el prefijo en lugar de codificar de forma rígida " https://publiccdn.sharepointonline.com ".</span><span class="sxs-lookup"><span data-stu-id="a808f-577">The page context property should be used to construct the prefix instead of hard coding "https://publiccdn.sharepointonline.com".</span></span> <span data-ttu-id="a808f-578">La dirección URL está sujeta a cambios y no debe estar codificada de forma dura.</span><span class="sxs-lookup"><span data-stu-id="a808f-578">The URL is subject to change and should not be hard coded.</span></span> <span data-ttu-id="a808f-579">Si usa plantillas para mostrar con SharePoint Online clásico, puede usar la propiedad "window._spPageContextInfo.publicCdnBaseUrl" en la plantilla para mostrar para el prefijo de la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="a808f-579">If you are using display templates with Classic SharePoint Online then you can use the property "window._spPageContextInfo.publicCdnBaseUrl" in your display template for the prefix of the URL.</span></span> <span data-ttu-id="a808f-580">Si es elementos web de SPFx para SharePoint moderno y clásico, puede usar la propiedad "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span><span class="sxs-lookup"><span data-stu-id="a808f-580">If you are SPFx web parts for modern and classic SharePoint the you can utilize the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span></span> <span data-ttu-id="a808f-581">Esto proporcionará el prefijo para que, si se cambia, la implementación se actualice con él.</span><span class="sxs-lookup"><span data-stu-id="a808f-581">This will provide the prefix so that if it is changed then your implementation will update with it.</span></span> <span data-ttu-id="a808f-582">Como ejemplo para SPFx, la dirección URL se puede construir con la propiedad "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL para el elemento".</span><span class="sxs-lookup"><span data-stu-id="a808f-582">As an example for SPFx, the URL can be constructed using the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item".</span></span> <span data-ttu-id="a808f-583">Consulta [Usar la red CDN en el código del lado](https://youtu.be/IH1RbQlbhIA) cliente, que forma parte de la serie de rendimiento de la temporada [1](https://aka.ms/sppnp-perfvideos)</span><span class="sxs-lookup"><span data-stu-id="a808f-583">Please see [Using CDN in Client-side code](https://youtu.be/IH1RbQlbhIA) which is part of the [season 1 performance series](https://aka.ms/sppnp-perfvideos)</span></span>


### <a name="using-assets-in-private-origins"></a><span data-ttu-id="a808f-584">Uso de activos en orígenes privados</span><span class="sxs-lookup"><span data-stu-id="a808f-584">Using assets in private origins</span></span>

<span data-ttu-id="a808f-585">No se requiere ninguna configuración adicional para usar activos en orígenes privados.</span><span class="sxs-lookup"><span data-stu-id="a808f-585">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="a808f-586">SharePoint Online reescribe automáticamente las direcciones URL de los activos de orígenes privados para que las solicitudes de esos activos siempre se atenúe desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-586">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="a808f-587">No puede crear manualmente direcciones URL en activos cdn en orígenes privados porque estas direcciones URL contienen tokens que SharePoint Online debe generar automáticamente en el momento en que se solicita el activo.</span><span class="sxs-lookup"><span data-stu-id="a808f-587">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="a808f-588">El acceso a activos en orígenes privados está protegido por tokens generados dinámicamente en función de los permisos de usuario al origen, con las advertencias descritas en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="a808f-588">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="a808f-589">Los usuarios deben tener al menos **acceso de** lectura a los orígenes de la red CDN para representar contenido.</span><span class="sxs-lookup"><span data-stu-id="a808f-589">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="a808f-590">En el siguiente diagrama se muestra el flujo de trabajo cuando SharePoint recibe una solicitud para una página que contiene activos de un origen privado.</span><span class="sxs-lookup"><span data-stu-id="a808f-590">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="a808f-591">![Diagrama de flujo de trabajo: recuperación de activos de red CDN de Office 365 desde un origen privado](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Flujo de trabajo: recuperación de activos de CDN de Office 365 desde un origen privado")</span><span class="sxs-lookup"><span data-stu-id="a808f-591">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="a808f-592">Autorización basada en tokens en orígenes privados</span><span class="sxs-lookup"><span data-stu-id="a808f-592">Token-based authorization in private origins</span></span>

<span data-ttu-id="a808f-593">El acceso a los activos en orígenes privados en la red CDN de Office 365 se concede mediante tokens generados por SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a808f-593">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="a808f-594">A los usuarios que ya tienen permiso para acceder a la carpeta o biblioteca designadas por el origen se les conceden automáticamente tokens que permiten al usuario tener acceso al archivo en función de su nivel de permisos.</span><span class="sxs-lookup"><span data-stu-id="a808f-594">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="a808f-595">Estos tokens de acceso son válidos de 30 a 90 minutos después de que se generen para ayudar a evitar ataques de reproducción de tokens.</span><span class="sxs-lookup"><span data-stu-id="a808f-595">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="a808f-596">Una vez generado el token de acceso, SharePoint Online devuelve un URI personalizado al cliente que contiene dos parámetros de autorización _(token_ de autorización perimetral) y avena _(token_ de autorización de origen).</span><span class="sxs-lookup"><span data-stu-id="a808f-596">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="a808f-597">La estructura de cada token _es< de_ expiración en el formato de tiempo de >__< la firma segura >.</span><span class="sxs-lookup"><span data-stu-id="a808f-597">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="a808f-598">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a808f-598">For example:</span></span>

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="a808f-599">Cualquier persona que esté en posesión del token puede tener acceso al recurso en la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-599">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="a808f-600">Sin embargo, las direcciones URL que contienen estos tokens de acceso solo se comparten a través de HTTPS, por lo que a menos que un usuario final comparta explícitamente la dirección URL antes de que expire el token, el activo no será accesible para usuarios no autorizados.</span><span class="sxs-lookup"><span data-stu-id="a808f-600">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="a808f-601">Los permisos de nivel de elemento no se admiten para activos en orígenes privados</span><span class="sxs-lookup"><span data-stu-id="a808f-601">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="a808f-602">Es importante tener en cuenta que SharePoint Online no admite permisos de nivel de elemento para activos en orígenes privados.</span><span class="sxs-lookup"><span data-stu-id="a808f-602">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="a808f-603">Por ejemplo, para un archivo ubicado en , los usuarios tienen acceso efectivo `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` al archivo dadas las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="a808f-603">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="a808f-604">Usuario</span><span class="sxs-lookup"><span data-stu-id="a808f-604">User</span></span>  |<span data-ttu-id="a808f-605">Permisos</span><span class="sxs-lookup"><span data-stu-id="a808f-605">Permissions</span></span>  |<span data-ttu-id="a808f-606">Acceso efectivo</span><span class="sxs-lookup"><span data-stu-id="a808f-606">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a808f-607">Usuario 1</span><span class="sxs-lookup"><span data-stu-id="a808f-607">User 1</span></span>     |<span data-ttu-id="a808f-608">Tiene acceso a folder1</span><span class="sxs-lookup"><span data-stu-id="a808f-608">Has access to folder1</span></span>         |<span data-ttu-id="a808f-609">Puede obtener image1.jpg desde la red CDN</span><span class="sxs-lookup"><span data-stu-id="a808f-609">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="a808f-610">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="a808f-610">User 2</span></span>     |<span data-ttu-id="a808f-611">No tiene acceso a folder1</span><span class="sxs-lookup"><span data-stu-id="a808f-611">Does not have access to folder1</span></span>         |<span data-ttu-id="a808f-612">No se puede image1.jpg desde la red CDN</span><span class="sxs-lookup"><span data-stu-id="a808f-612">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="a808f-613">Usuario 3</span><span class="sxs-lookup"><span data-stu-id="a808f-613">User 3</span></span>     |<span data-ttu-id="a808f-614">No tiene acceso a folder1, pero se le concede permiso explícito para acceder a image1.jpg en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a808f-614">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="a808f-615">Puede obtener acceso al recurso image1.jpg directamente desde SharePoint Online, pero no desde la red CDN</span><span class="sxs-lookup"><span data-stu-id="a808f-615">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="a808f-616">Usuario 4</span><span class="sxs-lookup"><span data-stu-id="a808f-616">User 4</span></span>     |<span data-ttu-id="a808f-617">Tiene acceso a folder1, pero se ha denegado explícitamente el acceso a image1.jpg en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a808f-617">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="a808f-618">No se puede obtener acceso al activo desde SharePoint Online, pero se puede acceder al activo desde la red CDN a pesar de que se le deniegue el acceso al archivo en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a808f-618">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="a808f-619"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-619"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="a808f-620">Solución de problemas de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-620">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="a808f-621"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="a808f-621"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="a808f-622">¿Cómo confirmo que la red CDN sirve a los activos?</span><span class="sxs-lookup"><span data-stu-id="a808f-622">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="a808f-623">Una vez que haya agregado vínculos a activos de RED CDN a una página, puede confirmar que el activo se está sirviendo desde la red CDN explorando la página, haciendo clic con el botón secundario en la imagen una vez que se ha representado y revisando la dirección URL de la imagen.</span><span class="sxs-lookup"><span data-stu-id="a808f-623">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="a808f-624">También puede usar las herramientas de desarrollador del explorador para ver la dirección URL de cada activo de una página o usar una herramienta de seguimiento de red de terceros.</span><span class="sxs-lookup"><span data-stu-id="a808f-624">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="a808f-625">Si usa una herramienta de red como Fiddler para probar los activos fuera de representar el activo desde una página de SharePoint, debe agregar manualmente el encabezado de referencia "Referer: " a la solicitud GET donde la dirección URL es la dirección URL raíz del inquilino de `https://yourdomain.sharepoint.com` SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a808f-625">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="a808f-626">No puede probar direcciones URL de CDN directamente en un explorador web porque debe tener un referente procedente de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a808f-626">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="a808f-627">Sin embargo, si agrega la dirección URL del activo de red CDN a una página de SharePoint y, a continuación, abre la página en un explorador, verá el activo cdn representado en la página.</span><span class="sxs-lookup"><span data-stu-id="a808f-627">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="a808f-628">Para obtener más información sobre el uso de las herramientas de desarrollador en el explorador Microsoft Edge, vea [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span><span class="sxs-lookup"><span data-stu-id="a808f-628">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="a808f-629">Para ver un breve vídeo hospedado en el canal de YouTube De patrones y prácticas para desarrolladores de [SharePoint](https://aka.ms/sppnp-videos) que muestra cómo comprobar que la red CDN funciona, consulte [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span><span class="sxs-lookup"><span data-stu-id="a808f-629">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="a808f-630">¿Por qué los activos de un nuevo origen no están disponibles?</span><span class="sxs-lookup"><span data-stu-id="a808f-630">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="a808f-631">Los activos de nuevos orígenes no estarán disponibles inmediatamente para su uso, ya que el registro tarda en propagarse a través de la red CDN y para que los activos se carguen desde el origen al almacenamiento de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="a808f-631">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="a808f-632">El tiempo necesario para que los activos estén disponibles en la red CDN depende del número de activos y el tamaño de los archivos.</span><span class="sxs-lookup"><span data-stu-id="a808f-632">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="a808f-633">Mi elemento web del lado cliente o la solución de SharePoint Framework no funciona</span><span class="sxs-lookup"><span data-stu-id="a808f-633">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="a808f-634">Al habilitar la red CDN de Office 365 para orígenes públicos, el servicio de red CDN crea automáticamente estos orígenes predeterminados:</span><span class="sxs-lookup"><span data-stu-id="a808f-634">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="a808f-635">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="a808f-635">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="a808f-636">\*/BIBLIOTECA DE ESTILOS</span><span class="sxs-lookup"><span data-stu-id="a808f-636">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="a808f-637">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="a808f-637">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="a808f-638">Si falta el origen \*/clientsideassets, las soluciones de SharePoint Framework producirán un error y no se generarán mensajes de advertencia o error.</span><span class="sxs-lookup"><span data-stu-id="a808f-638">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="a808f-639">Este origen puede faltar porque la red CDN se ha habilitado con el parámetro _-NoDefaultOrigins_ establecido en **$true**, o porque el origen se eliminó manualmente.</span><span class="sxs-lookup"><span data-stu-id="a808f-639">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="a808f-640">Puede comprobar qué orígenes están presentes con el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a808f-640">You can check to see which origins are present with the following PowerShell command:</span></span>

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="a808f-641">O puede comprobar con la CLI de Office 365:</span><span class="sxs-lookup"><span data-stu-id="a808f-641">Or you can check with the Office 365 CLI:</span></span>

``` powershell
spo cdn origin list
```

<span data-ttu-id="a808f-642">Para agregar el origen en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a808f-642">To add the origin in PowerShell:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="a808f-643">Para agregar el origen en la CLI de Office 365:</span><span class="sxs-lookup"><span data-stu-id="a808f-643">To add the origin in the Office 365 CLI:</span></span>

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="a808f-644">¿Qué módulos de PowerShell y shells de CLI necesito para trabajar con la red CDN de Office 365?</span><span class="sxs-lookup"><span data-stu-id="a808f-644">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="a808f-645">Puede elegir trabajar con la red CDN de Office 365 mediante el módulo PowerShell del Shell de administración de **SharePoint Online** o la CLI de **Office 365.**</span><span class="sxs-lookup"><span data-stu-id="a808f-645">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="a808f-646">Introducción al Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a808f-646">Getting started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="a808f-647">Instalar Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="a808f-647">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="a808f-648">Vea también</span><span class="sxs-lookup"><span data-stu-id="a808f-648">See also</span></span>

[<span data-ttu-id="a808f-649">Redes de entrega de contenido</span><span class="sxs-lookup"><span data-stu-id="a808f-649">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="a808f-650">Planeamiento de red y ajuste del rendimiento para Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-650">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="a808f-651">Serie de rendimiento de SharePoint: serie de vídeo cdn de Office 365</span><span class="sxs-lookup"><span data-stu-id="a808f-651">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)