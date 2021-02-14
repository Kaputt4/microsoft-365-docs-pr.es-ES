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
description: Obtenga información sobre cómo usar la red de entrega de contenido (CDN) de Office 365 para acelerar la entrega de los activos de SharePoint Online.
ms.openlocfilehash: 0ef7922f4e8881065f97a5fdeb4f21242c2b6467
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693647"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="68e29-103">Uso de la red de entrega de contenido (CDN) de Office 365 con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68e29-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="68e29-104">Puede usar la red de entrega de contenido (CDN) de Office 365 integrada para hospedar archivos estáticos y mejorar el rendimiento de las páginas de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68e29-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="68e29-105">La CDN de Office 365 mejora el rendimiento al almacenamiento en caché los archivos estáticos más cerca de los exploradores que los solicitan, lo que ayuda a acelerar descargas y reducir la latencia.</span><span class="sxs-lookup"><span data-stu-id="68e29-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="68e29-106">Además, la red CDN de Office 365 usa el [protocolo HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) para mejorar la compresión y la canalización HTTP.</span><span class="sxs-lookup"><span data-stu-id="68e29-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="68e29-107">La red CDN de Office 365 se incluye como parte de la suscripción a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68e29-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="68e29-108">La red CDN de Office 365 solo está disponible para los inquilinos en la **nube de producción** (en todo el mundo).</span><span class="sxs-lookup"><span data-stu-id="68e29-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="68e29-109">Actualmente, los inquilinos de las nubes del Gobierno de Estados Unidos, China y Alemania no admiten la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="68e29-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="68e29-110">La CDN de Office 365 se compone de varias redes CDN que permite hospedar archivos estáticos en varias ubicaciones u _orígenes_ y a realizar la entrega desde redes de alta velocidad globales.</span><span class="sxs-lookup"><span data-stu-id="68e29-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="68e29-111">Según el tipo de contenido que quiera hospedar en la CDN de Office 365, puede agregar orígenes **públicos**, **privados** o ambos.</span><span class="sxs-lookup"><span data-stu-id="68e29-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="68e29-112">Consulta [Elegir si cada origen debe ser público o privado](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) para obtener más información sobre la diferencia entre orígenes públicos y privados.</span><span class="sxs-lookup"><span data-stu-id="68e29-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="68e29-113">![Diagrama conceptual de la red CDN de Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Diagrama conceptual de la red CDN de Office 365")</span><span class="sxs-lookup"><span data-stu-id="68e29-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="68e29-114">Si ya está familiarizado con el modo en que funcionan las CDN, solo tiene que completar unos pocos pasos para habilitar la red CDN de Office 365 para su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="68e29-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="68e29-115">En este tema se describe cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="68e29-115">This topic describes how.</span></span> <span data-ttu-id="68e29-116">Sigue leyendo para obtener información sobre cómo empezar a hospedar tus activos estáticos.</span><span class="sxs-lookup"><span data-stu-id="68e29-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="68e29-117">Hay otras CDN hospedadas por Microsoft que se pueden usar con Office 365 para escenarios de uso especializado, pero no se abordan en este tema porque están fuera del ámbito de la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="68e29-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="68e29-118">Para obtener más información, vea [Otras CDN de Microsoft.](content-delivery-networks.md#other-microsoft-cdns)</span><span class="sxs-lookup"><span data-stu-id="68e29-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="68e29-119">**Vuelva a la [planeación de red y al ajuste del rendimiento de Office 365.](https://aka.ms/tune)**</span><span class="sxs-lookup"><span data-stu-id="68e29-119">**Head back to [Network planning and performance tuning for Office 365](https://aka.ms/tune).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="68e29-120">Información general sobre cómo trabajar con la red CDN de Office 365 en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68e29-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="68e29-121">Para configurar la red CDN de Office 365 para su organización, siga estos pasos básicos:</span><span class="sxs-lookup"><span data-stu-id="68e29-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="68e29-122">Planear la implementación de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="68e29-123">[Determine qué activos estáticos desea hospedar en la red CDN.](use-microsoft-365-cdn-with-spo.md#CDNAssets)</span><span class="sxs-lookup"><span data-stu-id="68e29-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="68e29-124">[Determine dónde desea almacenar los activos.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)</span><span class="sxs-lookup"><span data-stu-id="68e29-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="68e29-125">Esta ubicación puede ser un sitio, biblioteca o carpeta de SharePoint y se denomina _origen._</span><span class="sxs-lookup"><span data-stu-id="68e29-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="68e29-126">[Elige si cada origen debe ser público o privado.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="68e29-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="68e29-127">Puede agregar varios orígenes de tipos públicos y privados.</span><span class="sxs-lookup"><span data-stu-id="68e29-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="68e29-128">Configurar y configurar la red CDN con PowerShell o la CLI de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68e29-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="68e29-129">Configurar y configurar la red CDN mediante el Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68e29-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="68e29-130">Configurar la red CDN con PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="68e29-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="68e29-131">Configurar y configurar la red CDN con la CLI de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="68e29-132">Cuando complete este paso, tendrá:</span><span class="sxs-lookup"><span data-stu-id="68e29-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="68e29-133">Habilitó la red CDN para su organización.</span><span class="sxs-lookup"><span data-stu-id="68e29-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="68e29-134">Se agregaron los orígenes, identificando cada origen como público o privado.</span><span class="sxs-lookup"><span data-stu-id="68e29-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="68e29-135">Una vez que haya terminado con la configuración, puede administrar la red CDN de [Office 365](use-microsoft-365-cdn-with-spo.md#CDNManage) con el tiempo:</span><span class="sxs-lookup"><span data-stu-id="68e29-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="68e29-136">Agregar, actualizar y quitar activos</span><span class="sxs-lookup"><span data-stu-id="68e29-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="68e29-137">Agregar y quitar orígenes</span><span class="sxs-lookup"><span data-stu-id="68e29-137">Adding and removing origins</span></span>
+ <span data-ttu-id="68e29-138">Configuración de directivas de red CDN</span><span class="sxs-lookup"><span data-stu-id="68e29-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="68e29-139">Si es necesario, deshabilitar la red CDN</span><span class="sxs-lookup"><span data-stu-id="68e29-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="68e29-140">Por último, consulte [Uso de los activos de la red CDN](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) para obtener información sobre cómo obtener acceso a los activos de la red CDN desde orígenes públicos y privados.</span><span class="sxs-lookup"><span data-stu-id="68e29-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="68e29-141">Vea la solución de problemas de la red CDN de [Office 365](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) para obtener instrucciones sobre cómo resolver problemas comunes.</span><span class="sxs-lookup"><span data-stu-id="68e29-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="68e29-142">Planear la implementación de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="68e29-143">Antes de implementar la red CDN de Office 365 para su inquilino de Office 365, debe tener en cuenta los siguientes factores como parte del proceso de planeación.</span><span class="sxs-lookup"><span data-stu-id="68e29-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="68e29-144">Determinar qué activos estáticos desea hospedar en la red CDN</span><span class="sxs-lookup"><span data-stu-id="68e29-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="68e29-145">Determinar dónde quieres almacenar los activos</span><span class="sxs-lookup"><span data-stu-id="68e29-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="68e29-146">Elegir si cada origen debe ser público o privado</span><span class="sxs-lookup"><span data-stu-id="68e29-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="68e29-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="68e29-148">Determinar qué activos estáticos desea hospedar en la red CDN</span><span class="sxs-lookup"><span data-stu-id="68e29-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="68e29-149">En general, las CDN son más eficaces para hospedar activos _estáticos_ o activos que no cambian con mucha frecuencia.</span><span class="sxs-lookup"><span data-stu-id="68e29-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="68e29-150">Una buena regla general es identificar los archivos que cumplen algunas o todas estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="68e29-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="68e29-151">Archivos estáticos incrustados en una página (como scripts e imágenes) que pueden tener un impacto incremental significativo en los tiempos de carga de la página</span><span class="sxs-lookup"><span data-stu-id="68e29-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="68e29-152">Archivos de gran tamaño, como archivos ejecutables y archivos de instalación</span><span class="sxs-lookup"><span data-stu-id="68e29-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="68e29-153">Bibliotecas de recursos que admiten código del lado cliente</span><span class="sxs-lookup"><span data-stu-id="68e29-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="68e29-154">Por ejemplo, los archivos pequeños que se solicitan repetidamente, como imágenes de sitio y scripts, pueden mejorar significativamente el rendimiento de la representación del sitio y reducir de forma incremental la carga en los sitios de SharePoint Online al agregarlos a un origen de red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="68e29-155">Los archivos más grandes, como los ejecutables de instalación, se pueden descargar desde la red CDN, lo que proporciona un impacto positivo en el rendimiento y una reducción posterior de la carga en el sitio de SharePoint Online, incluso si no se tiene acceso a ellos con tanta frecuencia.</span><span class="sxs-lookup"><span data-stu-id="68e29-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="68e29-156">La mejora del rendimiento por archivo depende de muchos factores, como la proximidad del cliente al punto de conexión de red CDN más cercano, las condiciones transitorias en la red local, etc.</span><span class="sxs-lookup"><span data-stu-id="68e29-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="68e29-157">Muchos archivos estáticos son bastante pequeños y se pueden descargar de Office 365 en menos de un segundo.</span><span class="sxs-lookup"><span data-stu-id="68e29-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="68e29-158">Sin embargo, una página web puede contener muchos archivos incrustados con un tiempo de descarga acumulado de varios segundos.</span><span class="sxs-lookup"><span data-stu-id="68e29-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="68e29-159">El servicio de estos archivos desde la red CDN puede reducir significativamente el tiempo de carga general de la página.</span><span class="sxs-lookup"><span data-stu-id="68e29-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="68e29-160">Vea [¿Qué mejoras de rendimiento proporciona una red CDN?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) para ver un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="68e29-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="68e29-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="68e29-162">Determinar dónde quieres almacenar los activos</span><span class="sxs-lookup"><span data-stu-id="68e29-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="68e29-163">La red CDN recupera los activos de una ubicación denominada _origen._</span><span class="sxs-lookup"><span data-stu-id="68e29-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="68e29-164">Un origen puede ser un sitio de SharePoint, una biblioteca de documentos o una carpeta a la que se puede tener acceso mediante una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="68e29-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="68e29-165">Tiene una gran flexibilidad al especificar los orígenes de su organización.</span><span class="sxs-lookup"><span data-stu-id="68e29-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="68e29-166">Por ejemplo, puede especificar varios orígenes o un único origen donde quiera colocar todos los activos de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="68e29-167">Puede elegir tener orígenes públicos o privados para su organización.</span><span class="sxs-lookup"><span data-stu-id="68e29-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="68e29-168">La mayoría de las organizaciones elegirán implementar una combinación de las dos.</span><span class="sxs-lookup"><span data-stu-id="68e29-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="68e29-169">Puede crear un nuevo contenedor para sus orígenes, como carpetas o bibliotecas de documentos, y agregar archivos que desee que estén disponibles desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="68e29-170">Este es un buen enfoque si tiene un conjunto específico de activos que desea que estén disponibles desde la red CDN y desea restringir el conjunto de activos de la red CDN solo a esos archivos en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="68e29-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="68e29-171">También puede configurar una colección de sitios, un sitio, una biblioteca o una carpeta existentes como origen, lo que hará que todos los activos elegibles del contenedor estén disponibles desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="68e29-172">Antes de agregar un contenedor existente como origen, es importante asegurarse de que conoce su contenido y permisos para que no exponga accidentalmente activos a usuarios anónimos o no autorizados.</span><span class="sxs-lookup"><span data-stu-id="68e29-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="68e29-173">Puede definir directivas _de red CDN_ para excluir contenido de sus orígenes de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="68e29-174">Las directivas de red CDN excluyen activos  en orígenes públicos o privados por atributos como el tipo de archivo y la clasificación de _sitios,_ y se aplican a todos los orígenes de CdnType (privado o público) que especifique en la directiva.</span><span class="sxs-lookup"><span data-stu-id="68e29-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="68e29-175">Por ejemplo, si agrega un origen privado que consta de un sitio que contiene varios  subsitios, puede definir una directiva para excluir sitios marcados como confidenciales para que el contenido de los sitios con esa clasificación aplicada no se aprotegerá desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="68e29-176">La directiva se aplicará al contenido de _todos los_ orígenes privados que haya agregado a la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="68e29-177">Tenga en cuenta que, a mayor número de orígenes, mayor será el impacto en el tiempo que tarda el servicio de red CDN en procesar las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="68e29-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="68e29-178">Se recomienda limitar el número de orígenes tanto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="68e29-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="68e29-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="68e29-180">Elegir si cada origen debe ser público o privado</span><span class="sxs-lookup"><span data-stu-id="68e29-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="68e29-181">Cuando identifica un origen, especifica si debe hacerse público _o_ _privado._</span><span class="sxs-lookup"><span data-stu-id="68e29-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="68e29-182">El acceso a los activos de la red CDN en orígenes públicos es anónimo y el contenido de la red CDN en orígenes privados se protege mediante tokens generados dinámicamente para una mayor seguridad.</span><span class="sxs-lookup"><span data-stu-id="68e29-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="68e29-183">Independientemente de la opción que elija, Microsoft realiza todo el trabajo pesado por usted cuando se trata de la administración de la propia red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="68e29-184">Además, puede cambiar de opinión más adelante, después de configurar la red CDN e identificar sus orígenes.</span><span class="sxs-lookup"><span data-stu-id="68e29-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="68e29-185">Las opciones públicas y privadas proporcionan mejoras de rendimiento similares, pero cada una tiene atributos y ventajas únicos.</span><span class="sxs-lookup"><span data-stu-id="68e29-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="68e29-186">**Los** orígenes públicos dentro de la red CDN de Office 365 son accesibles de forma anónima y cualquier persona que tenga la dirección URL del activo puede tener acceso a los activos hospedados.</span><span class="sxs-lookup"><span data-stu-id="68e29-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="68e29-187">Como el acceso al contenido en orígenes públicos es anónimo, solo debe usarlos para almacenar en caché contenido genérico y no confidencial, como archivos javascript, scripts, iconos e imágenes.</span><span class="sxs-lookup"><span data-stu-id="68e29-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as javascript files, scripts, icons and images.</span></span>

<span data-ttu-id="68e29-188">**Los** orígenes privados dentro de la red CDN de Office 365 proporcionan acceso privado al contenido del usuario, como bibliotecas de documentos de SharePoint Online, sitios e imágenes propietarias.</span><span class="sxs-lookup"><span data-stu-id="68e29-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="68e29-189">El acceso al contenido en orígenes privados se protege mediante tokens generados dinámicamente para que solo puedan acceder a él los usuarios con permisos en la biblioteca de documentos original o la ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="68e29-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="68e29-190">Los orígenes privados en la red CDN de Office 365 solo se pueden usar para el contenido de SharePoint Online y solo puede acceder a los activos en orígenes privados a través de la redirección desde su espacio empresarial de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68e29-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="68e29-191">Puede obtener más información sobre cómo funciona el acceso de la red CDN a los activos de un origen privado en Uso de [activos en orígenes privados.](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)</span><span class="sxs-lookup"><span data-stu-id="68e29-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="68e29-192">Atributos y ventajas de hospedar activos en orígenes públicos</span><span class="sxs-lookup"><span data-stu-id="68e29-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="68e29-193">Cualquier persona puede acceder a los activos expuestos en un origen público de forma anónima.</span><span class="sxs-lookup"><span data-stu-id="68e29-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="68e29-194">Nunca debe colocar recursos que contengan información de usuario o que se consideren confidenciales para su organización en un origen público.</span><span class="sxs-lookup"><span data-stu-id="68e29-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>
+ <span data-ttu-id="68e29-195">Si elimina un activo de un origen público, el activo podría continuar disponible durante un máximo de 30 días desde la memoria caché. Sin embargo, se invalidarán los vínculos a los activos en la red CDN en 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="68e29-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>
+ <span data-ttu-id="68e29-196">Si hospeda hojas de estilo (archivos CSS) en un origen público, puede usar las rutas relativas y URI dentro del código.</span><span class="sxs-lookup"><span data-stu-id="68e29-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="68e29-197">Esto significa que puede hacer referencia a la ubicación de las imágenes de fondo y otros objetos con respecto a la ubicación del activo que está llamando.</span><span class="sxs-lookup"><span data-stu-id="68e29-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>
+ <span data-ttu-id="68e29-198">Aunque puede integrar una dirección URL de un origen público, no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="68e29-198">While you can hard code a public origin's URL, doing so is not recommended.</span></span> <span data-ttu-id="68e29-199">El motivo de esto es que, si no está disponible el acceso a la red CDN, la dirección URL no resolverá automáticamente su organización en SharePoint Online y podría producir vínculos rotos y otros errores.</span><span class="sxs-lookup"><span data-stu-id="68e29-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span>
+ <span data-ttu-id="68e29-200">Los tipos de archivo predeterminados que se incluyen para orígenes públicos son .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff y .woff2.</span><span class="sxs-lookup"><span data-stu-id="68e29-200">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="68e29-201">Puede especificar tipos de archivo adicionales.</span><span class="sxs-lookup"><span data-stu-id="68e29-201">You can specify additional file types.</span></span>
+ <span data-ttu-id="68e29-202">Puede configurar una directiva para excluir los activos identificados por las clasificaciones de sitio que especifique.</span><span class="sxs-lookup"><span data-stu-id="68e29-202">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="68e29-203">Por ejemplo, puede elegir excluir todos los activos que están marcados como restringidos o confidenciales aunque sean un tipo de archivo permitido y se encuentren en un origen público.</span><span class="sxs-lookup"><span data-stu-id="68e29-203">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="68e29-204">Atributos y ventajas de hospedar activos en orígenes privados</span><span class="sxs-lookup"><span data-stu-id="68e29-204">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="68e29-205">Los orígenes privados solo se pueden usar para activos de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68e29-205">Private origins can only be used for SharePoint Online assets.</span></span>
+ <span data-ttu-id="68e29-206">Los usuarios solo pueden acceder a los activos desde un origen privado si tienen permisos para acceder al contenedor.</span><span class="sxs-lookup"><span data-stu-id="68e29-206">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="68e29-207">Se impide el acceso anónimo a estos activos.</span><span class="sxs-lookup"><span data-stu-id="68e29-207">Anonymous access to these assets is prevented.</span></span>
+ <span data-ttu-id="68e29-208">Los activos en orígenes privados se deben hacer referencia desde el inquilino de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68e29-208">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="68e29-209">El acceso directo a los activos de red CDN privada no funciona.</span><span class="sxs-lookup"><span data-stu-id="68e29-209">Direct access to private CDN assets does not work.</span></span>
+ <span data-ttu-id="68e29-210">Si quita un activo del origen privado, el activo puede seguir estando disponible hasta una hora de la memoria caché; sin embargo, invalidaremos los vínculos al activo en la red CDN en un plazo de 15 minutos a partir de la eliminación del activo.</span><span class="sxs-lookup"><span data-stu-id="68e29-210">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>
+ <span data-ttu-id="68e29-211">Los tipos de archivo predeterminados que se incluyen en el origen privado son .gif, .ico, .jpeg, .jpg, .js y .png.</span><span class="sxs-lookup"><span data-stu-id="68e29-211">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="68e29-212">Puede especificar tipos de archivo adicionales.</span><span class="sxs-lookup"><span data-stu-id="68e29-212">You can specify additional file types.</span></span>
+ <span data-ttu-id="68e29-213">Al igual que con los orígenes públicos, puede configurar una directiva para excluir los activos identificados por las clasificaciones de sitio que especifique, incluso si usa caracteres comodín para incluir todos los activos dentro de una carpeta o biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="68e29-213">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="68e29-214">Para obtener más información sobre por qué usar la red CDN de Office 365, los conceptos generales de la red CDN y otras redes CDN de Microsoft que puede usar con su inquilino de Office 365, vea Redes de entrega de [contenido.](content-delivery-networks.md)</span><span class="sxs-lookup"><span data-stu-id="68e29-214">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="68e29-215">Orígenes predeterminados de la red CDN</span><span class="sxs-lookup"><span data-stu-id="68e29-215">Default CDN origins</span></span>

<span data-ttu-id="68e29-216">A menos que especifique lo contrario, Office 365 configura algunos orígenes predeterminados automáticamente al habilitar la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="68e29-216">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="68e29-217">Si inicialmente opta por no aprovisionarlos, puede agregar estos orígenes después de completar la configuración.</span><span class="sxs-lookup"><span data-stu-id="68e29-217">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="68e29-218">A menos que comprenda las consecuencias de omitir la configuración de los orígenes predeterminados y tenga una razón específica para hacerlo, debe permitir que se cree cuando habilite la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-218">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="68e29-219">Orígenes predeterminados de la red CDN privada:</span><span class="sxs-lookup"><span data-stu-id="68e29-219">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="68e29-220">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="68e29-220">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="68e29-221">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="68e29-221">\*/siteassets</span></span>

<span data-ttu-id="68e29-222">Orígenes predeterminados de la red CDN pública:</span><span class="sxs-lookup"><span data-stu-id="68e29-222">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="68e29-223">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="68e29-223">\*/masterpage</span></span>
+ <span data-ttu-id="68e29-224">\*/style library</span><span class="sxs-lookup"><span data-stu-id="68e29-224">\*/style library</span></span>
+ <span data-ttu-id="68e29-225">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="68e29-225">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="68e29-226">_clientsideassets_ es un origen público predeterminado que se agregó al servicio de red CDN de Office 365 en diciembre de 2017.</span><span class="sxs-lookup"><span data-stu-id="68e29-226">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="68e29-227">Este origen debe estar presente para que las soluciones de SharePoint Framework en la red CDN funcionen.</span><span class="sxs-lookup"><span data-stu-id="68e29-227">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="68e29-228">Si habilitó la red CDN de Office 365 antes de diciembre de 2017 o si omitió la configuración de los orígenes predeterminados al habilitar la red CDN, puede agregar manualmente este origen.</span><span class="sxs-lookup"><span data-stu-id="68e29-228">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="68e29-229">Para obtener más información, vea Mi elemento web del lado cliente o La solución [de SharePoint Framework no funciona.](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)</span><span class="sxs-lookup"><span data-stu-id="68e29-229">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="68e29-230"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-230"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="68e29-231">Configurar y configurar la red CDN de Office 365 mediante el Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68e29-231">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="68e29-232">Los procedimientos de esta sección requieren que use el Shell de administración de SharePoint Online para conectarse a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68e29-232">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="68e29-233">Para obtener instrucciones, consulte [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="68e29-233">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="68e29-234">Complete estos pasos para configurar y configurar la red CDN para hospedar los activos en SharePoint Online mediante el Shell de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68e29-234">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="68e29-235">Haga clic para expandir</span><span class="sxs-lookup"><span data-stu-id="68e29-235">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="68e29-236">Permitir que su organización use la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-236">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="68e29-237">Antes de realizar cambios en la configuración de la red CDN del espacio empresarial, debe recuperar el estado actual de la configuración de la red CDN privada en su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="68e29-237">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="68e29-238">Conéctese al espacio empresarial mediante el Shell de administración de SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="68e29-238">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="68e29-239">Ahora use el cmdlet **Get-SPOTenantCdnEnabled** para recuperar la configuración de estado de la red CDN del inquilino:</span><span class="sxs-lookup"><span data-stu-id="68e29-239">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="68e29-240">El estado de la red CDN para el CdnType especificado se mostrará en pantalla.</span><span class="sxs-lookup"><span data-stu-id="68e29-240">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="68e29-241">Use el cmdlet **Set-SPOTenantCdnEnabled** para permitir que su organización use la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="68e29-241">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="68e29-242">Puede permitir que su organización use orígenes públicos, privados o ambos a la vez.</span><span class="sxs-lookup"><span data-stu-id="68e29-242">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="68e29-243">También puede configurar la red CDN para omitir la configuración de los orígenes predeterminados al habilitarla.</span><span class="sxs-lookup"><span data-stu-id="68e29-243">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="68e29-244">Siempre puede agregar estos orígenes más adelante, como se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="68e29-244">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="68e29-245">En Windows PowerShell para SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="68e29-245">In Windows Powershell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="68e29-246">Por ejemplo, para permitir que su organización use orígenes públicos y privados, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="68e29-246">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="68e29-247">Para permitir que su organización use orígenes públicos y privados, pero omita la configuración de los orígenes predeterminados, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="68e29-247">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="68e29-248">Vea los orígenes predeterminados de la red [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) para obtener información sobre los orígenes que se aprovisionan de forma predeterminada al habilitar la red CDN de Office 365 y el posible impacto de omitir la configuración de los orígenes predeterminados.</span><span class="sxs-lookup"><span data-stu-id="68e29-248">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="68e29-249">Para permitir que su organización use orígenes públicos, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="68e29-249">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="68e29-250">Para permitir que su organización use orígenes privados, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="68e29-250">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="68e29-251">Para obtener más información acerca de este cmdlet, [vea Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span><span class="sxs-lookup"><span data-stu-id="68e29-251">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span></span>

<span data-ttu-id="68e29-252"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-252"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="68e29-253">Cambiar la lista de tipos de archivo para incluir en la red CDN de Office 365 (opcional)</span><span class="sxs-lookup"><span data-stu-id="68e29-253">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="68e29-254">Al definir tipos de archivo mediante el cmdlet **Set-SPOTenantCdnPolicy,** se sobrescribe la lista definida actualmente.</span><span class="sxs-lookup"><span data-stu-id="68e29-254">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="68e29-255">Si desea agregar tipos de archivo adicionales a la lista, use el cmdlet primero para averiguar qué tipos de archivo ya están permitidos e incluirlos en la lista junto con los nuevos.</span><span class="sxs-lookup"><span data-stu-id="68e29-255">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="68e29-256">Use el cmdlet **Set-SPOTenantCdnPolicy** para definir tipos de archivo estáticos que se pueden hospedar en orígenes públicos y privados en la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-256">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="68e29-257">De forma predeterminada, se permiten tipos de activos comunes, por ejemplo .css, .gif, .jpg y .js.</span><span class="sxs-lookup"><span data-stu-id="68e29-257">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="68e29-258">En Windows PowerShell para SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="68e29-258">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="68e29-259">Por ejemplo, para habilitar la red CDN para hospedar archivos .css y .png, debe escribir el comando:</span><span class="sxs-lookup"><span data-stu-id="68e29-259">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="68e29-260">Para ver qué tipos de archivo permite actualmente la red CDN, use el cmdlet **Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="68e29-260">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="68e29-261">Para obtener más información acerca de estos cmdlets, vea [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) y [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span><span class="sxs-lookup"><span data-stu-id="68e29-261">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span></span>

<span data-ttu-id="68e29-262"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-262"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="68e29-263">Cambiar la lista de clasificaciones de sitio que desea excluir de la red CDN de Office 365 (opcional)</span><span class="sxs-lookup"><span data-stu-id="68e29-263">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="68e29-264">Cuando se excluyen las clasificaciones de sitio mediante el cmdlet **Set-SPOTenantCdnPolicy,** se sobrescribe la lista definida actualmente.</span><span class="sxs-lookup"><span data-stu-id="68e29-264">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="68e29-265">Si desea excluir clasificaciones de sitio adicionales, use el cmdlet primero para averiguar qué clasificaciones ya están excluidas y, a continuación, agregarlas junto con las nuevas.</span><span class="sxs-lookup"><span data-stu-id="68e29-265">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="68e29-266">Use el cmdlet **Set-SPOTenantCdnPolicy** para excluir las clasificaciones de sitio que no desee que estén disponibles en la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-266">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="68e29-267">De forma predeterminada, no se excluyen clasificaciones de sitio.</span><span class="sxs-lookup"><span data-stu-id="68e29-267">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="68e29-268">En Windows PowerShell para SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="68e29-268">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="68e29-269">Para ver qué clasificaciones de sitio están restringidas actualmente, use el cmdlet **Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="68e29-269">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="68e29-270">Las propiedades que se devolverán _son IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ y _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="68e29-270">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="68e29-271">La _propiedad IncludeFileExtensions_ contiene la lista de extensiones de archivo que se van a servir desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-271">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="68e29-272">Las extensiones de archivo predeterminadas son diferentes entre pública y privada.</span><span class="sxs-lookup"><span data-stu-id="68e29-272">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="68e29-273">La _propiedad ExcludeRestrictedSiteClassifications_ contiene las clasificaciones de sitio que desea excluir de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-273">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="68e29-274">Por ejemplo, puede excluir  sitios marcados como confidenciales para que el contenido de los sitios con esa clasificación aplicada no se abate desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-274">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="68e29-275">La _propiedad ExcludeIfNoScriptDisabled_ excluye el contenido de la red CDN en función de la configuración de atributos _de NoScript_ en el nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="68e29-275">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="68e29-276">De forma predeterminada, _el atributo NoScript_ se establece en **Habilitado** para sitios _modernos_ y **Deshabilitado** para _sitios clásicos._</span><span class="sxs-lookup"><span data-stu-id="68e29-276">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="68e29-277">Esto depende de la configuración del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="68e29-277">This depends on your tenant settings.</span></span>

<span data-ttu-id="68e29-278">Para obtener más información acerca de estos cmdlets, vea [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) y [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span><span class="sxs-lookup"><span data-stu-id="68e29-278">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span></span>

<span data-ttu-id="68e29-279"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-279"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="68e29-280">Agregar un origen para los activos</span><span class="sxs-lookup"><span data-stu-id="68e29-280">Add an origin for your assets</span></span>

<span data-ttu-id="68e29-281">Use el **cmdlet Add-SPOTenantCdnOrigin** para definir un origen.</span><span class="sxs-lookup"><span data-stu-id="68e29-281">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="68e29-282">Puede definir varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="68e29-282">You can define multiple origins.</span></span> <span data-ttu-id="68e29-283">El origen es una dirección URL que apunta a una biblioteca de SharePoint o la carpeta que contiene los activos que desea que se hospeden mediante la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-283">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="68e29-284">Nunca debe colocar recursos que contengan información de usuario o que se consideren confidenciales para su organización en un origen público.</span><span class="sxs-lookup"><span data-stu-id="68e29-284">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="68e29-285">El valor de _la ruta de_ acceso es la ruta de acceso relativa a la biblioteca o carpeta que contiene los activos.</span><span class="sxs-lookup"><span data-stu-id="68e29-285">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="68e29-286">Puede usar caracteres comodín además de rutas relativas.</span><span class="sxs-lookup"><span data-stu-id="68e29-286">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="68e29-287">Los orígenes admiten caracteres comodín anteponer a la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="68e29-287">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="68e29-288">Esto le permite crear orígenes que abarcan varios sitios.</span><span class="sxs-lookup"><span data-stu-id="68e29-288">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="68e29-289">Por ejemplo, para incluir todos los activos en la carpeta masterpages de todos los sitios como un origen público dentro de la red CDN, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="68e29-289">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="68e29-290">El modificador de caracteres comodín \* solo se puede usar al principio de la ruta de acceso y coincidirá con todos los segmentos de dirección URL en **/** la dirección URL especificada.</span><span class="sxs-lookup"><span data-stu-id="68e29-290">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="68e29-291">La ruta de acceso puede apuntar a una biblioteca de documentos, una carpeta o un sitio.</span><span class="sxs-lookup"><span data-stu-id="68e29-291">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="68e29-292">Por ejemplo, la ruta _de acceso \*/site1_ coincidirá con todas las bibliotecas de documentos del sitio.</span><span class="sxs-lookup"><span data-stu-id="68e29-292">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="68e29-293">Puede agregar un origen con una ruta de acceso relativa específica.</span><span class="sxs-lookup"><span data-stu-id="68e29-293">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="68e29-294">No se puede agregar un origen mediante la ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="68e29-294">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="68e29-295">En este ejemplo se agrega un origen privado de la biblioteca siteassets en un sitio específico:</span><span class="sxs-lookup"><span data-stu-id="68e29-295">This example adds a private origin of the siteassets library on a specific site:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="68e29-296">En este ejemplo se agrega un origen privado de la _carpeta folder1_ en la biblioteca de activos del sitio de la colección de sitios:</span><span class="sxs-lookup"><span data-stu-id="68e29-296">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="68e29-297">Si hay un espacio en la ruta de acceso, puede rodear la ruta entre comillas dobles o reemplazar el espacio con la codificación DE URL %20.</span><span class="sxs-lookup"><span data-stu-id="68e29-297">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="68e29-298">En los ejemplos siguientes se agrega un origen privado de la _carpeta 1_ de la biblioteca de activos del sitio de la colección de sitios:</span><span class="sxs-lookup"><span data-stu-id="68e29-298">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="68e29-299">Para obtener más información acerca de este comando y su sintaxis, vea [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span><span class="sxs-lookup"><span data-stu-id="68e29-299">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="68e29-300">En los orígenes privados, los activos que se comparten desde un origen deben tener una versión principal publicada para poder acceder a ellos desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-300">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="68e29-301">Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="68e29-301">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="68e29-302">Esto puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="68e29-302">This can take up to 15 minutes.</span></span>

<span data-ttu-id="68e29-303"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-303"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="68e29-304">Ejemplo: configurar un origen público para las páginas maestras y para la biblioteca de estilos de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68e29-304">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="68e29-305">Normalmente, estos orígenes se establecen automáticamente cuando habilita la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="68e29-305">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="68e29-306">Sin embargo, si desea habilitarlos manualmente, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="68e29-306">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="68e29-307">Use el **cmdlet Add-SPOTenantCdnOrigin** para definir la biblioteca de estilos como un origen público.</span><span class="sxs-lookup"><span data-stu-id="68e29-307">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="68e29-308">Use el **cmdlet Add-SPOTenantCdnOrigin** para definir las páginas maestras como un origen público.</span><span class="sxs-lookup"><span data-stu-id="68e29-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="68e29-309">Para obtener más información acerca de este comando y su sintaxis, vea [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span><span class="sxs-lookup"><span data-stu-id="68e29-309">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

<span data-ttu-id="68e29-310">Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="68e29-310">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="68e29-311">Esto puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="68e29-311">This can take up to 15 minutes.</span></span>

<span data-ttu-id="68e29-312"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-312"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="68e29-313">Ejemplo: configurar un origen privado para los activos del sitio, las páginas del sitio y las imágenes de publicación para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68e29-313">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="68e29-314">Use el cmdlet **Add-SPOTenantCdnOrigin** para definir la carpeta de activos del sitio como un origen privado.</span><span class="sxs-lookup"><span data-stu-id="68e29-314">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="68e29-315">Use el cmdlet **Add-SPOTenantCdnOrigin** para definir la carpeta de páginas del sitio como un origen privado.</span><span class="sxs-lookup"><span data-stu-id="68e29-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="68e29-316">Use el cmdlet **Add-SPOTenantCdnOrigin** para definir la carpeta de imágenes de publicación como un origen privado.</span><span class="sxs-lookup"><span data-stu-id="68e29-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="68e29-317">Para obtener más información acerca de este comando y su sintaxis, vea [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span><span class="sxs-lookup"><span data-stu-id="68e29-317">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

<span data-ttu-id="68e29-318">Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="68e29-318">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="68e29-319">Esto puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="68e29-319">This can take up to 15 minutes.</span></span>

<span data-ttu-id="68e29-320"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-320"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="68e29-321">Ejemplo: Configurar un origen privado para una colección de sitios para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68e29-321">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="68e29-322">Use el **cmdlet Add-SPOTenantCdnOrigin** para definir una colección de sitios como un origen privado.</span><span class="sxs-lookup"><span data-stu-id="68e29-322">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="68e29-323">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="68e29-323">For example:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="68e29-324">Para obtener más información acerca de este comando y su sintaxis, vea [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span><span class="sxs-lookup"><span data-stu-id="68e29-324">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>
  
<span data-ttu-id="68e29-325">Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="68e29-325">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="68e29-326">Es posible que vea un _mensaje pendiente de_ configuración que se espera a medida que el inquilino de SharePoint Online se conecta al servicio de red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-326">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="68e29-327">Esto puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="68e29-327">This can take up to 15 minutes.</span></span>

<span data-ttu-id="68e29-328"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-328"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="68e29-329">Administrar la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-329">Manage the Office 365 CDN</span></span>

<span data-ttu-id="68e29-330">Una vez que haya configurado la red CDN, puede realizar cambios en la configuración a medida que actualiza el contenido o cuando sus necesidades cambian, como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="68e29-330">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="68e29-331"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-331"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="68e29-332">Agregar, actualizar o quitar activos de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-332">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="68e29-333">Una vez que haya completado los pasos de configuración, puede agregar nuevos activos y actualizar o quitar los activos existentes cuando lo desee.</span><span class="sxs-lookup"><span data-stu-id="68e29-333">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="68e29-334">Solo tiene que realizar los cambios en los activos de la carpeta o biblioteca de SharePoint que identificó como origen.</span><span class="sxs-lookup"><span data-stu-id="68e29-334">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="68e29-335">Si agrega un nuevo activo, estará disponible a través de la red CDN inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="68e29-335">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="68e29-336">Sin embargo, si actualiza el activo, la nueva copia llevará hasta 15 minutos en propagarse y estar disponible en la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-336">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="68e29-337">Si necesita recuperar la ubicación del origen, puede usar el cmdlet **Get-SPOTenantCdnOrigins.**</span><span class="sxs-lookup"><span data-stu-id="68e29-337">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="68e29-338">Para obtener información sobre cómo usar este cmdlet, vea [Get-SPOTenantCdnOrigins](https://technet.microsoft.com/library/mt790770.aspx).</span><span class="sxs-lookup"><span data-stu-id="68e29-338">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](https://technet.microsoft.com/library/mt790770.aspx).</span></span>

<span data-ttu-id="68e29-339"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-339"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="68e29-340">Quitar un origen de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-340">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="68e29-341">Puede quitar el acceso a una carpeta o biblioteca de SharePoint que identificó como origen.</span><span class="sxs-lookup"><span data-stu-id="68e29-341">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="68e29-342">Para ello, use el cmdlet **Remove-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="68e29-342">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="68e29-343">Para obtener información sobre cómo usar este cmdlet, vea [Remove-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790761.aspx).</span><span class="sxs-lookup"><span data-stu-id="68e29-343">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790761.aspx).</span></span>

<span data-ttu-id="68e29-344"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-344"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="68e29-345">Modificar un origen en la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-345">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="68e29-346">No puede modificar un origen que haya creado.</span><span class="sxs-lookup"><span data-stu-id="68e29-346">You cannot modify an origin you've created.</span></span> <span data-ttu-id="68e29-347">En su lugar, quite el origen y, a continuación, agregue uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="68e29-347">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="68e29-348">Para obtener más información, vea Para quitar un origen de la red CDN de [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) y Para agregar un [origen para sus activos.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)</span><span class="sxs-lookup"><span data-stu-id="68e29-348">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="68e29-349"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-349"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="68e29-350">Deshabilitar la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-350">Disable the Office 365 CDN</span></span>

<span data-ttu-id="68e29-351">Use el cmdlet **Set-SPOTenantCdnEnabled** para deshabilitar la red CDN de su organización.</span><span class="sxs-lookup"><span data-stu-id="68e29-351">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="68e29-352">Si tiene los orígenes público y privado habilitados para la red CDN, debe ejecutar el cmdlet dos veces, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="68e29-352">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="68e29-353">Para deshabilitar el uso de orígenes públicos en la red CDN, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="68e29-353">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="68e29-354">Para deshabilitar el uso de los orígenes privados en la red CDN, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="68e29-354">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="68e29-355">Para obtener más información acerca de este cmdlet, [vea Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span><span class="sxs-lookup"><span data-stu-id="68e29-355">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span></span>

</details>

<span data-ttu-id="68e29-356"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-356"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="68e29-357">Configurar y configurar la red CDN de Office 365 con PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="68e29-357">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="68e29-358">Los procedimientos de esta sección requieren que use PnP PowerShell para conectarse a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68e29-358">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="68e29-359">Para obtener instrucciones, consulte [Introducción a PowerShell PnP.](https://github.com/SharePoint/PnP-PowerShell#getting-started)</span><span class="sxs-lookup"><span data-stu-id="68e29-359">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="68e29-360">Siga estos pasos para configurar y configurar la red CDN para hospedar los activos en SharePoint Online con PnP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68e29-360">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="68e29-361">Haga clic para expandir</span><span class="sxs-lookup"><span data-stu-id="68e29-361">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="68e29-362">Permitir que su organización use la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-362">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="68e29-363">Antes de realizar cambios en la configuración de la red CDN del espacio empresarial, debe recuperar el estado actual de la configuración de la red CDN privada en su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="68e29-363">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="68e29-364">Conéctese a su espacio empresarial con PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68e29-364">Connect to your tenant using PnP PowerShell:</span></span>

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="68e29-365">Ahora use el cmdlet **Get-PnPTenantCdnEnabled** para recuperar la configuración de estado de la red CDN del inquilino:</span><span class="sxs-lookup"><span data-stu-id="68e29-365">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="68e29-366">El estado de la red CDN para el CdnType especificado se mostrará en pantalla.</span><span class="sxs-lookup"><span data-stu-id="68e29-366">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="68e29-367">Use el cmdlet **Set-PnPTenantCdnEnabled** para permitir que su organización use la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="68e29-367">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="68e29-368">Puede permitir que su organización use orígenes públicos, privados o ambos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="68e29-368">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="68e29-369">También puede configurar la red CDN para omitir la configuración de los orígenes predeterminados al habilitarla.</span><span class="sxs-lookup"><span data-stu-id="68e29-369">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="68e29-370">Siempre puede agregar estos orígenes más adelante, como se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="68e29-370">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="68e29-371">En PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68e29-371">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="68e29-372">Por ejemplo, para permitir que su organización use orígenes públicos y privados, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="68e29-372">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="68e29-373">Para permitir que su organización use orígenes públicos y privados, pero omita la configuración de los orígenes predeterminados, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="68e29-373">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="68e29-374">Vea los orígenes predeterminados de la red [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) para obtener información sobre los orígenes que se aprovisionan de forma predeterminada al habilitar la red CDN de Office 365 y el posible impacto de omitir la configuración de los orígenes predeterminados.</span><span class="sxs-lookup"><span data-stu-id="68e29-374">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="68e29-375">Para permitir que su organización use orígenes públicos, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="68e29-375">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="68e29-376">Para permitir que su organización use orígenes privados, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="68e29-376">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="68e29-377">Para obtener más información acerca de este cmdlet, [vea Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span><span class="sxs-lookup"><span data-stu-id="68e29-377">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="68e29-378"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-378"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="68e29-379">Cambiar la lista de tipos de archivo para incluir en la red CDN de Office 365 (opcional)</span><span class="sxs-lookup"><span data-stu-id="68e29-379">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="68e29-380">Al definir tipos de archivo mediante el cmdlet **Set-PnPTenantCdnPolicy,** se sobrescribe la lista definida actualmente.</span><span class="sxs-lookup"><span data-stu-id="68e29-380">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="68e29-381">Si desea agregar tipos de archivo adicionales a la lista, use el cmdlet primero para averiguar qué tipos de archivo ya están permitidos e incluirlos en la lista junto con los nuevos.</span><span class="sxs-lookup"><span data-stu-id="68e29-381">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="68e29-382">Use el cmdlet **Set-PnPTenantCdnPolicy** para definir tipos de archivo estáticos que se pueden hospedar en orígenes públicos y privados en la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-382">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="68e29-383">De forma predeterminada, se permiten tipos de activos comunes, por ejemplo .css, .gif, .jpg y .js.</span><span class="sxs-lookup"><span data-stu-id="68e29-383">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="68e29-384">En PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68e29-384">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="68e29-385">Por ejemplo, para habilitar la red CDN para hospedar archivos .css y .png, debe escribir el comando:</span><span class="sxs-lookup"><span data-stu-id="68e29-385">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="68e29-386">Para ver qué tipos de archivo permite actualmente la red CDN, use el cmdlet **Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="68e29-386">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="68e29-387">Para obtener más información acerca de estos cmdlets, vea [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) y [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span><span class="sxs-lookup"><span data-stu-id="68e29-387">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="68e29-388"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-388"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="68e29-389">Cambiar la lista de clasificaciones de sitio que desea excluir de la red CDN de Office 365 (opcional)</span><span class="sxs-lookup"><span data-stu-id="68e29-389">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="68e29-390">Cuando se excluyen las clasificaciones de sitio mediante el cmdlet **Set-PnPTenantCdnPolicy,** se sobrescribe la lista definida actualmente.</span><span class="sxs-lookup"><span data-stu-id="68e29-390">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="68e29-391">Si desea excluir clasificaciones de sitio adicionales, use el cmdlet primero para averiguar qué clasificaciones ya están excluidas y, a continuación, agregarlas junto con las nuevas.</span><span class="sxs-lookup"><span data-stu-id="68e29-391">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="68e29-392">Use el cmdlet **Set-PnPTenantCdnPolicy** para excluir las clasificaciones de sitio que no desea que estén disponibles a través de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-392">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="68e29-393">De forma predeterminada, no se excluyen clasificaciones de sitio.</span><span class="sxs-lookup"><span data-stu-id="68e29-393">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="68e29-394">En PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68e29-394">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="68e29-395">Para ver qué clasificaciones de sitio están restringidas actualmente, use el cmdlet **Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="68e29-395">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="68e29-396">Las propiedades que se devolverán _son IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ y _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="68e29-396">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="68e29-397">La _propiedad IncludeFileExtensions_ contiene la lista de extensiones de archivo que se van a servir desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-397">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="68e29-398">Las extensiones de archivo predeterminadas son diferentes entre pública y privada.</span><span class="sxs-lookup"><span data-stu-id="68e29-398">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="68e29-399">La _propiedad ExcludeRestrictedSiteClassifications_ contiene las clasificaciones de sitio que desea excluir de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-399">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="68e29-400">Por ejemplo, puede excluir  sitios marcados como confidenciales para que el contenido de los sitios con esa clasificación aplicada no se abate desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-400">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="68e29-401">La _propiedad ExcludeIfNoScriptDisabled_ excluye el contenido de la red CDN en función de la configuración de atributos _de NoScript_ en el nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="68e29-401">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="68e29-402">De forma predeterminada, _el atributo NoScript_ se establece en **Habilitado** para sitios _modernos_ y **Deshabilitado** para _sitios clásicos._</span><span class="sxs-lookup"><span data-stu-id="68e29-402">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="68e29-403">Esto depende de la configuración del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="68e29-403">This depends on your tenant settings.</span></span>

<span data-ttu-id="68e29-404">Para obtener más información acerca de estos cmdlets, vea [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) y [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span><span class="sxs-lookup"><span data-stu-id="68e29-404">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="68e29-405"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-405"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="68e29-406">Agregar un origen para los activos</span><span class="sxs-lookup"><span data-stu-id="68e29-406">Add an origin for your assets</span></span>

<span data-ttu-id="68e29-407">Use el **cmdlet Add-PnPTenantCdnOrigin** para definir un origen.</span><span class="sxs-lookup"><span data-stu-id="68e29-407">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="68e29-408">Puede definir varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="68e29-408">You can define multiple origins.</span></span> <span data-ttu-id="68e29-409">El origen es una dirección URL que apunta a una biblioteca de SharePoint o la carpeta que contiene los activos que desea que se hospeden mediante la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-409">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="68e29-410">Nunca debe colocar recursos que contengan información de usuario o que se consideren confidenciales para su organización en un origen público.</span><span class="sxs-lookup"><span data-stu-id="68e29-410">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="68e29-411">El valor de _la ruta de_ acceso es la ruta de acceso relativa a la biblioteca o carpeta que contiene los activos.</span><span class="sxs-lookup"><span data-stu-id="68e29-411">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="68e29-412">Puede usar caracteres comodín además de rutas relativas.</span><span class="sxs-lookup"><span data-stu-id="68e29-412">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="68e29-413">Los orígenes admiten caracteres comodín anteponer a la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="68e29-413">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="68e29-414">Esto le permite crear orígenes que abarcan varios sitios.</span><span class="sxs-lookup"><span data-stu-id="68e29-414">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="68e29-415">Por ejemplo, para incluir todos los activos en la carpeta masterpages de todos los sitios como un origen público dentro de la red CDN, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="68e29-415">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="68e29-416">El modificador de caracteres comodín \* solo se puede usar al principio de la ruta de acceso y coincidirá con todos los segmentos de dirección URL en **/** la dirección URL especificada.</span><span class="sxs-lookup"><span data-stu-id="68e29-416">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="68e29-417">La ruta de acceso puede apuntar a una biblioteca de documentos, una carpeta o un sitio.</span><span class="sxs-lookup"><span data-stu-id="68e29-417">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="68e29-418">Por ejemplo, la ruta _de acceso \*/site1_ coincidirá con todas las bibliotecas de documentos del sitio.</span><span class="sxs-lookup"><span data-stu-id="68e29-418">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="68e29-419">Puede agregar un origen con una ruta de acceso relativa específica.</span><span class="sxs-lookup"><span data-stu-id="68e29-419">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="68e29-420">No se puede agregar un origen mediante la ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="68e29-420">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="68e29-421">En este ejemplo se agrega un origen privado de la biblioteca de activos del sitio en un sitio específico:</span><span class="sxs-lookup"><span data-stu-id="68e29-421">This example adds a private origin of the site assets library on a specific site:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="68e29-422">En este ejemplo se agrega un origen privado de la _carpeta folder1_ en la biblioteca de activos del sitio de la colección de sitios:</span><span class="sxs-lookup"><span data-stu-id="68e29-422">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="68e29-423">Si hay un espacio en la ruta de acceso, puede rodear la ruta entre comillas dobles o reemplazar el espacio con la codificación DE URL %20.</span><span class="sxs-lookup"><span data-stu-id="68e29-423">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="68e29-424">En los ejemplos siguientes se agrega un origen privado de la _carpeta 1_ de la biblioteca de activos del sitio de la colección de sitios:</span><span class="sxs-lookup"><span data-stu-id="68e29-424">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="68e29-425">Para obtener más información acerca de este comando y su sintaxis, vea [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="68e29-425">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="68e29-426">En los orígenes privados, los activos que se comparten desde un origen deben tener una versión principal publicada para poder acceder a ellos desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-426">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="68e29-427">Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="68e29-427">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="68e29-428">Esto puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="68e29-428">This can take up to 15 minutes.</span></span>

<span data-ttu-id="68e29-429"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-429"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="68e29-430">Ejemplo: configurar un origen público para las páginas maestras y para la biblioteca de estilos de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68e29-430">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="68e29-431">Normalmente, estos orígenes se establecen automáticamente cuando habilita la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="68e29-431">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="68e29-432">Sin embargo, si desea habilitarlos manualmente, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="68e29-432">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="68e29-433">Use el cmdlet **Add-PnPTenantCdnOrigin** para definir la biblioteca de estilos como un origen público.</span><span class="sxs-lookup"><span data-stu-id="68e29-433">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="68e29-434">Use el **cmdlet Add-PnPTenantCdnOrigin** para definir las páginas maestras como un origen público.</span><span class="sxs-lookup"><span data-stu-id="68e29-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="68e29-435">Para obtener más información acerca de este comando y su sintaxis, vea [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="68e29-435">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="68e29-436">Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="68e29-436">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="68e29-437">Esto puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="68e29-437">This can take up to 15 minutes.</span></span>

<span data-ttu-id="68e29-438"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-438"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="68e29-439">Ejemplo: configurar un origen privado para los activos del sitio, las páginas del sitio y las imágenes de publicación para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68e29-439">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="68e29-440">Use el cmdlet **Add-PnPTenantCdnOrigin** para definir la carpeta de activos del sitio como un origen privado.</span><span class="sxs-lookup"><span data-stu-id="68e29-440">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="68e29-441">Use el cmdlet **Add-PnPTenantCdnOrigin** para definir la carpeta de páginas del sitio como un origen privado.</span><span class="sxs-lookup"><span data-stu-id="68e29-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="68e29-442">Use el cmdlet **Add-PnPTenantCdnOrigin** para definir la carpeta de imágenes de publicación como un origen privado.</span><span class="sxs-lookup"><span data-stu-id="68e29-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="68e29-443">Para obtener más información acerca de este comando y su sintaxis, vea [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="68e29-443">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="68e29-444">Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="68e29-444">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="68e29-445">Esto puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="68e29-445">This can take up to 15 minutes.</span></span>

<span data-ttu-id="68e29-446"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-446"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="68e29-447">Ejemplo: Configurar un origen privado para una colección de sitios para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68e29-447">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="68e29-448">Use el cmdlet **Add-PnPTenantCdnOrigin** para definir una colección de sitios como un origen privado.</span><span class="sxs-lookup"><span data-stu-id="68e29-448">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="68e29-449">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="68e29-449">For example:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="68e29-450">Para obtener más información acerca de este comando y su sintaxis, vea [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="68e29-450">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="68e29-451">Una vez que haya ejecutado el comando, el sistema sincroniza la configuración en todo el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="68e29-451">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="68e29-452">Es posible que vea un _mensaje pendiente de_ configuración que se espera a medida que el inquilino de SharePoint Online se conecta al servicio de red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-452">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="68e29-453">Esto puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="68e29-453">This can take up to 15 minutes.</span></span>

<span data-ttu-id="68e29-454"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-454"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="68e29-455">Administrar la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-455">Manage the Office 365 CDN</span></span>

<span data-ttu-id="68e29-456">Una vez que haya configurado la red CDN, puede realizar cambios en la configuración a medida que actualiza el contenido o cuando sus necesidades cambian, como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="68e29-456">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="68e29-457"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-457"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="68e29-458">Agregar, actualizar o quitar activos de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-458">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="68e29-459">Una vez que haya completado los pasos de configuración, puede agregar nuevos activos y actualizar o quitar los activos existentes cuando lo desee.</span><span class="sxs-lookup"><span data-stu-id="68e29-459">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="68e29-460">Solo tiene que realizar los cambios en los activos de la carpeta o biblioteca de SharePoint que identificó como origen.</span><span class="sxs-lookup"><span data-stu-id="68e29-460">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="68e29-461">Si agrega un nuevo activo, estará disponible a través de la red CDN inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="68e29-461">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="68e29-462">Sin embargo, si actualiza el activo, la nueva copia llevará hasta 15 minutos en propagarse y estar disponible en la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-462">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="68e29-463">Si necesita recuperar la ubicación del origen, puede usar el cmdlet **Get-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="68e29-463">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="68e29-464">Para obtener información sobre cómo usar este cmdlet, vea [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="68e29-464">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="68e29-465"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-465"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="68e29-466">Quitar un origen de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-466">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="68e29-467">Puede quitar el acceso a una carpeta o biblioteca de SharePoint que identificó como origen.</span><span class="sxs-lookup"><span data-stu-id="68e29-467">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="68e29-468">Para ello, use el cmdlet **Remove-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="68e29-468">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="68e29-469">Para obtener información sobre cómo usar este cmdlet, vea [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="68e29-469">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="68e29-470"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-470"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="68e29-471">Modificar un origen en la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-471">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="68e29-472">No puede modificar un origen que haya creado.</span><span class="sxs-lookup"><span data-stu-id="68e29-472">You cannot modify an origin you've created.</span></span> <span data-ttu-id="68e29-473">En su lugar, quite el origen y, a continuación, agregue uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="68e29-473">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="68e29-474">Para obtener más información, vea Para quitar un origen de la red CDN de [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) y Para agregar un [origen para sus activos.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)</span><span class="sxs-lookup"><span data-stu-id="68e29-474">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="68e29-475"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-475"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="68e29-476">Deshabilitar la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-476">Disable the Office 365 CDN</span></span>

<span data-ttu-id="68e29-477">Use el cmdlet **Set-PnPTenantCdnEnabled** para deshabilitar la red CDN de su organización.</span><span class="sxs-lookup"><span data-stu-id="68e29-477">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="68e29-478">Si tiene los orígenes público y privado habilitados para la red CDN, debe ejecutar el cmdlet dos veces, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="68e29-478">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="68e29-479">Para deshabilitar el uso de orígenes públicos en la red CDN, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="68e29-479">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="68e29-480">Para deshabilitar el uso de los orígenes privados en la red CDN, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="68e29-480">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="68e29-481">Para obtener más información acerca de este cmdlet, [vea Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span><span class="sxs-lookup"><span data-stu-id="68e29-481">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="68e29-482"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-482"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="68e29-483">Instalar y configurar la red CDN de Office 365 con la CLI de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-483">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="68e29-484">Los procedimientos de esta sección requieren que haya instalado la [CLI de Office 365.](https://aka.ms/o365cli)</span><span class="sxs-lookup"><span data-stu-id="68e29-484">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="68e29-485">A continuación, conéctese al inquilino de Office 365 con el comando [de inicio de](https://pnp.github.io/office365-cli/cmd/login/) sesión.</span><span class="sxs-lookup"><span data-stu-id="68e29-485">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="68e29-486">Complete estos pasos para configurar y configurar la red CDN para hospedar sus activos en SharePoint Online mediante la CLI de Office 365.</span><span class="sxs-lookup"><span data-stu-id="68e29-486">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="68e29-487">Haga clic para expandir</span><span class="sxs-lookup"><span data-stu-id="68e29-487">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="68e29-488">Habilitar la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-488">Enable the Office 365 CDN</span></span>

<span data-ttu-id="68e29-489">Puede administrar el estado de la red CDN de Office 365 en su cuenta empresarial con el comando [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/).</span><span class="sxs-lookup"><span data-stu-id="68e29-489">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="68e29-490">Para habilitar la red CDN pública de Office 365 en su cuenta empresarial ejecute:</span><span class="sxs-lookup"><span data-stu-id="68e29-490">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```sh
spo cdn set --type Public --enabled true
```

<span data-ttu-id="68e29-491">Para habilitar la red CDN de SharePoint de Office 365, ejecute:</span><span class="sxs-lookup"><span data-stu-id="68e29-491">To enable the Office 365 SharePoint CDN, execute:</span></span>

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="68e29-492">Vea el estado actual de la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="68e29-492">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="68e29-493">Para comprobar si el tipo concreto de red CDN de Office 365 está habilitado o deshabilitado, use el comando [spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)</span><span class="sxs-lookup"><span data-stu-id="68e29-493">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="68e29-494">Para comprobar si la red CDN pública de Office 365 está habilitada, ejecute:</span><span class="sxs-lookup"><span data-stu-id="68e29-494">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="68e29-495">Ver los orígenes de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-495">View the Office 365 CDN origins</span></span>

<span data-ttu-id="68e29-496">Para ver los orígenes configurados actualmente de la red CDN pública de Office 365, ejecute:</span><span class="sxs-lookup"><span data-stu-id="68e29-496">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```sh
spo cdn origin list --type Public
```

<span data-ttu-id="68e29-497">Vea los orígenes predeterminados de la red [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) para obtener información sobre los orígenes que se aprovisionan de forma predeterminada al habilitar la red CDN de Office 365.</span><span class="sxs-lookup"><span data-stu-id="68e29-497">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="68e29-498">Agregar un origen de red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-498">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="68e29-499">Nunca debe colocar recursos que se consideren confidenciales para su organización en una biblioteca de documentos de SharePoint configurada como un origen público.</span><span class="sxs-lookup"><span data-stu-id="68e29-499">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="68e29-500">Use el comando [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) definir un origen de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-500">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="68e29-501">Puede definir varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="68e29-501">You can define multiple origins.</span></span> <span data-ttu-id="68e29-502">El origen es una dirección URL que apunta a una biblioteca de SharePoint o la carpeta que contiene los activos que desea que se hospeden mediante la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-502">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="68e29-503">Dónde `path` está la ruta de acceso relativa a la carpeta que contiene los activos.</span><span class="sxs-lookup"><span data-stu-id="68e29-503">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="68e29-504">Puede usar caracteres comodín además de rutas relativas.</span><span class="sxs-lookup"><span data-stu-id="68e29-504">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="68e29-505">Para incluir todos los activos en la **Galería de páginas maestras** de todos los sitios como origen público, ejecute:</span><span class="sxs-lookup"><span data-stu-id="68e29-505">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```sh
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="68e29-506">Para configurar un origen privado para una colección de sitios específica, ejecute:</span><span class="sxs-lookup"><span data-stu-id="68e29-506">To configure a private origin for a specific site collection, execute:</span></span>

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="68e29-507">Después de agregar un origen de la red CDN, puede tardar hasta 15 minutos para poder recuperar archivos mediante el servicio de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-507">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="68e29-508">Puede comprobar si ya se ha habilitado el origen particular con el comando [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/).</span><span class="sxs-lookup"><span data-stu-id="68e29-508">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="68e29-509">Quitar un origen de red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-509">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="68e29-510">Use el comando [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) para eliminar un origen de la red CDN para el tipo de red CDN especificado.</span><span class="sxs-lookup"><span data-stu-id="68e29-510">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="68e29-511">Para quitar un origen público de la configuración de la red CDN, ejecute:</span><span class="sxs-lookup"><span data-stu-id="68e29-511">To remove a public origin from the CDN configuration, execute:</span></span>

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="68e29-512">La eliminación de un origen de red CDN no afecta a los archivos almacenados en ninguna biblioteca de documentos que coincida con ese origen.</span><span class="sxs-lookup"><span data-stu-id="68e29-512">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="68e29-513">Si se ha hecho referencia a estos activos mediante su dirección URL de SharePoint, SharePoint volverá automáticamente a la dirección URL original que apunta a la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="68e29-513">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="68e29-514">Sin embargo, si se ha hecho referencia a los activos mediante una dirección URL de red CDN pública, al quitar el origen se romperá el vínculo y tendrá que cambiarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="68e29-514">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="68e29-515">Modificar un origen de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-515">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="68e29-516">No es posible modificar un origen de la red CDN existente.</span><span class="sxs-lookup"><span data-stu-id="68e29-516">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="68e29-517">En su lugar, debe eliminar el origen de la red CDN definido anteriormente con el comando `spo cdn origin remove` y agregar uno nuevo con el comando `spo cdn origin add`.</span><span class="sxs-lookup"><span data-stu-id="68e29-517">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="68e29-518">Cambiar los tipos de archivos que se incluirán en la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-518">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="68e29-519">De forma predeterminada, los siguientes tipos de archivo se incluyen en la red CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff y .woff2_.</span><span class="sxs-lookup"><span data-stu-id="68e29-519">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="68e29-520">Si tiene que incluir otros tipos de archivo en la red CDN, puede cambiar la configuración de la red CDN con el comando [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/).</span><span class="sxs-lookup"><span data-stu-id="68e29-520">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="68e29-521">Al cambiar la lista de tipos de archivo, se sobrescribe la lista definida actualmente.</span><span class="sxs-lookup"><span data-stu-id="68e29-521">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="68e29-522">Si desea incluir otros tipos de archivo, use el comando [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) para averiguar qué tipos de archivos están configurados en este momento.</span><span class="sxs-lookup"><span data-stu-id="68e29-522">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="68e29-523">Para agregar el tipo de archivo _JSON_ a la lista predeterminada de tipos de archivo incluidos en la red CDN pública, ejecute:</span><span class="sxs-lookup"><span data-stu-id="68e29-523">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="68e29-524">Cambiar la lista de clasificaciones de sitio que desea excluir de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-524">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="68e29-525">Use el comando [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) para excluir las clasificaciones de sitio que no desee que estén disponibles en la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-525">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="68e29-526">De forma predeterminada, no se excluyen clasificaciones de sitio.</span><span class="sxs-lookup"><span data-stu-id="68e29-526">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="68e29-527">Al cambiar la lista de clasificaciones de sitio excluidas, se sobrescribe la lista definida actualmente.</span><span class="sxs-lookup"><span data-stu-id="68e29-527">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="68e29-528">Si quiere excluir clasificaciones adicionales, use el comando [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) para averiguar qué clasificaciones están configuradas en este momento.</span><span class="sxs-lookup"><span data-stu-id="68e29-528">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="68e29-529">Para excluir sitios clasificados como _HBI_ de la red CDN pública, ejecute</span><span class="sxs-lookup"><span data-stu-id="68e29-529">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="68e29-530">Deshabilitar la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-530">Disable the Office 365 CDN</span></span>

<span data-ttu-id="68e29-531">Para deshabilitar la red CDN de Office 365, use el comando `spo cdn set`, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="68e29-531">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="68e29-532">Uso de los activos de la red CDN</span><span class="sxs-lookup"><span data-stu-id="68e29-532">Using your CDN assets</span></span>

<span data-ttu-id="68e29-533">Ahora que ha habilitado la red CDN y ha configurado orígenes y directivas, puede empezar a usar los activos de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-533">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="68e29-534">Esta sección le ayudará a comprender cómo usar direcciones URL de red CDN en sus páginas y contenido de SharePoint para que SharePoint redirija las solicitudes de activos en orígenes públicos y privados a la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-534">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="68e29-535">Actualización de vínculos a activos de red CDN</span><span class="sxs-lookup"><span data-stu-id="68e29-535">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="68e29-536">Uso de activos en orígenes públicos</span><span class="sxs-lookup"><span data-stu-id="68e29-536">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="68e29-537">Uso de activos en orígenes privados</span><span class="sxs-lookup"><span data-stu-id="68e29-537">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="68e29-538">Para obtener información sobre cómo usar la red CDN para hospedar elementos web del lado cliente, vea el tema Hospedar el elemento web del lado cliente desde la red CDN de [Office 365 (parte 4](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)de Hello World).</span><span class="sxs-lookup"><span data-stu-id="68e29-538">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="68e29-539">Si agrega la carpeta _ClientSideAssets_ a la lista de orígenes de la red **CDN** privada, los elementos web personalizados hospedados en la red CDN no se representarán.</span><span class="sxs-lookup"><span data-stu-id="68e29-539">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="68e29-540">Los archivos usados por los elementos web de SPFX solo pueden usar la red CDN pública y la carpeta ClientSideAssets es un origen predeterminado para la red CDN pública.</span><span class="sxs-lookup"><span data-stu-id="68e29-540">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="68e29-541">Actualización de vínculos a activos de red CDN</span><span class="sxs-lookup"><span data-stu-id="68e29-541">Updating links to CDN assets</span></span>

<span data-ttu-id="68e29-542">Para usar activos que haya agregado a un origen, simplemente actualice los vínculos al archivo original con la ruta de acceso al archivo en el origen.</span><span class="sxs-lookup"><span data-stu-id="68e29-542">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="68e29-543">Edite la página o el contenido que contiene vínculos a activos que ha agregado a un origen.</span><span class="sxs-lookup"><span data-stu-id="68e29-543">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="68e29-544">También puede usar uno de varios métodos para buscar y reemplazar vínculos de forma global en un sitio o colección de sitios si desea actualizar el vínculo a un activo determinado en cualquier lugar donde aparezca.</span><span class="sxs-lookup"><span data-stu-id="68e29-544">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="68e29-545">Para cada vínculo a un activo en un origen, reemplace la ruta de acceso por la ruta de acceso al archivo en el origen de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-545">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="68e29-546">Puede usar rutas de acceso relativas.</span><span class="sxs-lookup"><span data-stu-id="68e29-546">You can use relative paths.</span></span>
+ <span data-ttu-id="68e29-547">Guarde la página o el contenido.</span><span class="sxs-lookup"><span data-stu-id="68e29-547">Save the page or content.</span></span>

<span data-ttu-id="68e29-548">Por ejemplo, considere la imagen _/site/SiteAssets/images/image.png_, que ha copiado en la carpeta de la biblioteca de documentos _/site/CDN_origins/public/_.</span><span class="sxs-lookup"><span data-stu-id="68e29-548">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="68e29-549">Para usar el activo de red CDN, reemplace la ruta de acceso original a la ubicación del archivo de imagen por la ruta de acceso al origen para que la nueva dirección URL _/site/CDN_origins/public/image.png_.</span><span class="sxs-lookup"><span data-stu-id="68e29-549">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="68e29-550">Si desea usar la dirección URL completa del activo en lugar de una ruta de acceso relativa, cree el vínculo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="68e29-550">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="68e29-551">En general, no debe codificar las direcciones URL directamente a los activos de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-551">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="68e29-552">Sin embargo, puede crear manualmente direcciones URL para activos en orígenes públicos si es necesario.</span><span class="sxs-lookup"><span data-stu-id="68e29-552">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="68e29-553">Para obtener más información, vea [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).</span><span class="sxs-lookup"><span data-stu-id="68e29-553">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).</span></span>

<span data-ttu-id="68e29-554">Para obtener información sobre cómo comprobar que los activos se sirven desde la red CDN, consulte ¿Cómo confirmo que la red [CDN](use-microsoft-365-cdn-with-spo.md#CDNConfirm) proporciona activos? en la sección Solución de problemas de la red CDN de [Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)</span><span class="sxs-lookup"><span data-stu-id="68e29-554">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in the [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) section.</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="68e29-555">Uso de activos en orígenes públicos</span><span class="sxs-lookup"><span data-stu-id="68e29-555">Using assets in public origins</span></span>

<span data-ttu-id="68e29-556">La  característica de publicación en SharePoint Online reescribe automáticamente las direcciones URL de los activos almacenados en orígenes públicos en sus equivalentes de red CDN para que los activos se atenúen desde el servicio de red CDN en lugar de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="68e29-556">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="68e29-557">Si su origen se encuentra en un sitio con la característica de publicación habilitada y los activos que desea descargar a la red CDN se encuentran en una de las siguientes categorías, SharePoint reescribirá automáticamente las direcciones URL de los activos en el origen, siempre que el activo no haya sido excluido por una directiva de red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-557">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="68e29-558">A continuación, se muestra información general sobre los vínculos que la característica de publicación de SharePoint reescribe automáticamente:</span><span class="sxs-lookup"><span data-stu-id="68e29-558">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="68e29-559">URL de IMG/LINK/CSS en respuestas de HTML de página de publicación clásica</span><span class="sxs-lookup"><span data-stu-id="68e29-559">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="68e29-560">Esto incluye imágenes que han agregado autores en el contenido HTML de una página</span><span class="sxs-lookup"><span data-stu-id="68e29-560">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="68e29-561">URL de las imágenes del elemento web de presentación de la biblioteca de imágenes</span><span class="sxs-lookup"><span data-stu-id="68e29-561">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="68e29-562">Campos de imagen de los resultados de la API de REST SPList (RenderListDataAsStream)</span><span class="sxs-lookup"><span data-stu-id="68e29-562">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="68e29-563">Usar la nueva propiedad _ImageFieldsToTryRewriteToCdnUrls_ para proporcionar una lista separada por comas de campos</span><span class="sxs-lookup"><span data-stu-id="68e29-563">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="68e29-564">Admite campos de hipervínculo y campos PublishingImage</span><span class="sxs-lookup"><span data-stu-id="68e29-564">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="68e29-565">Representaciones de imágenes de SharePoint</span><span class="sxs-lookup"><span data-stu-id="68e29-565">SharePoint image renditions</span></span>

<span data-ttu-id="68e29-566">En el siguiente diagrama se muestra el flujo de trabajo cuando SharePoint recibe una solicitud para una página que contiene activos de un origen público.</span><span class="sxs-lookup"><span data-stu-id="68e29-566">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="68e29-567">![Diagrama de flujo de trabajo: recuperar activos de red CDN de Office 365 desde un origen público](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Flujo de trabajo: recuperar activos de red CDN de Office 365 desde un origen público")</span><span class="sxs-lookup"><span data-stu-id="68e29-567">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="68e29-568">Si desea deshabilitar la reescritura automática para direcciones URL específicas de una página, ¿puede des consultar la página y agregar el parámetro de cadena de **consulta? NoAutoReWrites=true** al final de cada vínculo que desea deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="68e29-568">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="hardcoding-cdn-urls-for-public-assets"></a><span data-ttu-id="68e29-569">Hardcoding CDN URLs for public assets</span><span class="sxs-lookup"><span data-stu-id="68e29-569">Hardcoding CDN URLs for public assets</span></span>

<span data-ttu-id="68e29-570">Si  la característica de publicación no está habilitada para un origen público o el activo no es uno de los tipos de vínculo admitidos por la característica de reescritura automática del servicio de red CDN, puede construir manualmente direcciones URL en la ubicación de la red CDN de los activos y usar estas direcciones URL en el contenido.</span><span class="sxs-lookup"><span data-stu-id="68e29-570">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="68e29-571">No puede codificar las direcciones URL de la red CDN en activos de origen privado porque el token de acceso necesario que forma la última sección de la dirección URL se genera en el momento en que se solicita el recurso.</span><span class="sxs-lookup"><span data-stu-id="68e29-571">You cannot hardcode CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span>

<span data-ttu-id="68e29-572">Para los activos de la red CDN pública, el formato de dirección URL tendrá el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="68e29-572">For public CDN assets, the URL format will look like the following:</span></span>

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="68e29-573">Reemplace **TenantHostName por** su nombre de inquilino.</span><span class="sxs-lookup"><span data-stu-id="68e29-573">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="68e29-574">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="68e29-574">Example:</span></span>

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

### <a name="using-assets-in-private-origins"></a><span data-ttu-id="68e29-575">Uso de activos en orígenes privados</span><span class="sxs-lookup"><span data-stu-id="68e29-575">Using assets in private origins</span></span>

<span data-ttu-id="68e29-576">No se requiere ninguna configuración adicional para usar activos en orígenes privados.</span><span class="sxs-lookup"><span data-stu-id="68e29-576">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="68e29-577">SharePoint Online reescribe automáticamente las direcciones URL de los activos en orígenes privados para que las solicitudes de esos activos siempre se atenúe desde la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-577">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="68e29-578">No puede crear manualmente direcciones URL en activos de red CDN en orígenes privados porque estas direcciones URL contienen tokens que SharePoint Online debe generar automáticamente en el momento en que se solicita el activo.</span><span class="sxs-lookup"><span data-stu-id="68e29-578">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="68e29-579">El acceso a los activos en orígenes privados está protegido por tokens generados dinámicamente en función de los permisos de usuario para el origen, con las advertencias descritas en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="68e29-579">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="68e29-580">Los usuarios deben tener al menos **acceso de** lectura a los orígenes para que la red CDN represente contenido.</span><span class="sxs-lookup"><span data-stu-id="68e29-580">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="68e29-581">En el siguiente diagrama se muestra el flujo de trabajo cuando SharePoint recibe una solicitud de una página que contiene activos de un origen privado.</span><span class="sxs-lookup"><span data-stu-id="68e29-581">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="68e29-582">![Diagrama de flujo de trabajo: recuperación de activos de red CDN de Office 365 desde un origen privado](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Flujo de trabajo: recuperar activos de red CDN de Office 365 desde un origen privado")</span><span class="sxs-lookup"><span data-stu-id="68e29-582">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="68e29-583">Autorización basada en tokens en orígenes privados</span><span class="sxs-lookup"><span data-stu-id="68e29-583">Token-based authorization in private origins</span></span>

<span data-ttu-id="68e29-584">El acceso a los activos en orígenes privados en la red CDN de Office 365 se concede mediante tokens generados por SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68e29-584">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="68e29-585">A los usuarios que ya tienen permiso para acceder a la carpeta o biblioteca designada por el origen se les conceden automáticamente tokens que permiten al usuario tener acceso al archivo en función de su nivel de permisos.</span><span class="sxs-lookup"><span data-stu-id="68e29-585">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="68e29-586">Estos tokens de acceso son válidos durante 30 a 90 minutos después de que se generen para ayudar a evitar ataques de reproducción de tokens.</span><span class="sxs-lookup"><span data-stu-id="68e29-586">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="68e29-587">Una vez generado el token de acceso, SharePoint Online devuelve  un URI personalizado al cliente que contiene dos parámetros de autorización (token de autorización perimetral) y _oat_ (token de autorización de origen).</span><span class="sxs-lookup"><span data-stu-id="68e29-587">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="68e29-588">La estructura de cada token es< fecha de expiración en formato de hora de la época >__< la firma _segura >_.</span><span class="sxs-lookup"><span data-stu-id="68e29-588">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="68e29-589">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="68e29-589">For example:</span></span>

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="68e29-590">Cualquier persona que posea el token puede acceder al recurso en la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-590">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="68e29-591">Sin embargo, las direcciones URL que contienen estos tokens de acceso solo se comparten a través de HTTPS, por lo que a menos que un usuario final comparta explícitamente la dirección URL antes de que expire el token, el activo no será accesible para los usuarios no autorizados.</span><span class="sxs-lookup"><span data-stu-id="68e29-591">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="68e29-592">Los permisos de nivel de elemento no se admiten para activos en orígenes privados</span><span class="sxs-lookup"><span data-stu-id="68e29-592">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="68e29-593">Es importante tener en cuenta que SharePoint Online no admite permisos de nivel de elemento para activos en orígenes privados.</span><span class="sxs-lookup"><span data-stu-id="68e29-593">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="68e29-594">Por ejemplo, para un archivo ubicado en , los usuarios tienen acceso efectivo al archivo `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="68e29-594">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="68e29-595">Usuario</span><span class="sxs-lookup"><span data-stu-id="68e29-595">User</span></span>  |<span data-ttu-id="68e29-596">Permissions</span><span class="sxs-lookup"><span data-stu-id="68e29-596">Permissions</span></span>  |<span data-ttu-id="68e29-597">Acceso efectivo</span><span class="sxs-lookup"><span data-stu-id="68e29-597">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="68e29-598">Usuario 1</span><span class="sxs-lookup"><span data-stu-id="68e29-598">User 1</span></span>     |<span data-ttu-id="68e29-599">Tiene acceso a la carpeta1</span><span class="sxs-lookup"><span data-stu-id="68e29-599">Has access to folder1</span></span>         |<span data-ttu-id="68e29-600">Puede obtener image1.jpg desde la red CDN</span><span class="sxs-lookup"><span data-stu-id="68e29-600">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="68e29-601">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="68e29-601">User 2</span></span>     |<span data-ttu-id="68e29-602">No tiene acceso a folder1</span><span class="sxs-lookup"><span data-stu-id="68e29-602">Does not have access to folder1</span></span>         |<span data-ttu-id="68e29-603">No se puede image1.jpg desde la red CDN</span><span class="sxs-lookup"><span data-stu-id="68e29-603">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="68e29-604">Usuario 3</span><span class="sxs-lookup"><span data-stu-id="68e29-604">User 3</span></span>     |<span data-ttu-id="68e29-605">No tiene acceso a folder1, pero se le concede permiso explícito para acceder a image1.jpg en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68e29-605">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="68e29-606">Puede obtener acceso al recurso image1.jpg directamente desde SharePoint Online, pero no desde la red CDN</span><span class="sxs-lookup"><span data-stu-id="68e29-606">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="68e29-607">Usuario 4</span><span class="sxs-lookup"><span data-stu-id="68e29-607">User 4</span></span>     |<span data-ttu-id="68e29-608">Tiene acceso a la carpeta 1, pero se le ha denegado explícitamente el acceso a image1.jpg en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68e29-608">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="68e29-609">No se puede obtener acceso al activo desde SharePoint Online, pero puede acceder al activo desde la red CDN a pesar de que se le deniega el acceso al archivo en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68e29-609">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="68e29-610"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-610"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="68e29-611">Solución de problemas de la red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-611">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="68e29-612"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="68e29-612"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="68e29-613">¿Cómo confirmo que la red CDN sirve los activos?</span><span class="sxs-lookup"><span data-stu-id="68e29-613">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="68e29-614">Una vez que haya agregado vínculos a activos de red CDN a una página, puede confirmar que el activo se sirve desde la red CDN. Para ello, examine la página, haga clic con el botón secundario en la imagen una vez que se haya representado y revise la dirección URL de la imagen.</span><span class="sxs-lookup"><span data-stu-id="68e29-614">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="68e29-615">También puede usar las herramientas de desarrollo del explorador para ver la dirección URL de cada activo en una página o usar una herramienta de seguimiento de red de terceros.</span><span class="sxs-lookup"><span data-stu-id="68e29-615">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="68e29-616">Si usa una herramienta de red como Fiddler para probar los activos fuera de representar el activo desde una página de SharePoint, debe agregar manualmente el encabezado de referencia "Referer: " a la solicitud GET, donde la dirección URL es la dirección URL raíz de su inquilino de `https://yourdomain.sharepoint.com` SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68e29-616">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="68e29-617">No puede probar las direcciones URL de la red CDN directamente en un explorador web porque debe tener un referenciador procedente de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68e29-617">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="68e29-618">Sin embargo, si agrega la dirección URL del activo de red CDN a una página de SharePoint y, a continuación, abre la página en un explorador, verá el activo de red CDN representado en la página.</span><span class="sxs-lookup"><span data-stu-id="68e29-618">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="68e29-619">Para obtener más información sobre el uso de las herramientas de desarrollo en el explorador Microsoft Edge, vea [Microsoft Edge Developer Tools](https://docs.microsoft.com/microsoft-edge/devtools-guide).</span><span class="sxs-lookup"><span data-stu-id="68e29-619">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](https://docs.microsoft.com/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="68e29-620">Para ver un breve vídeo hospedado en el canal de YouTube de modelos y prácticas para desarrolladores de [SharePoint](https://aka.ms/sppnp-videos) que muestra cómo comprobar que la red CDN funciona, consulte Comprobar el uso de la red [CDN](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)y garantizar una conectividad de red óptima.</span><span class="sxs-lookup"><span data-stu-id="68e29-620">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="68e29-621">¿Por qué los activos de un nuevo origen no están disponibles?</span><span class="sxs-lookup"><span data-stu-id="68e29-621">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="68e29-622">Los activos de nuevos orígenes no estarán disponibles inmediatamente para su uso, ya que el registro tarda en propagarse a través de la red CDN y para que los activos se carguen desde el origen al almacenamiento de la red CDN.</span><span class="sxs-lookup"><span data-stu-id="68e29-622">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="68e29-623">El tiempo necesario para que los activos estén disponibles en la red CDN depende de cuántos activos y tamaños de archivos.</span><span class="sxs-lookup"><span data-stu-id="68e29-623">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="68e29-624">Mi elemento web del lado cliente o la solución de SharePoint Framework no funcionan</span><span class="sxs-lookup"><span data-stu-id="68e29-624">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="68e29-625">Cuando habilita la red CDN de Office 365 para orígenes públicos, el servicio de red CDN crea automáticamente estos orígenes predeterminados:</span><span class="sxs-lookup"><span data-stu-id="68e29-625">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="68e29-626">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="68e29-626">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="68e29-627">\*/BIBLIOTECA DE ESTILOS</span><span class="sxs-lookup"><span data-stu-id="68e29-627">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="68e29-628">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="68e29-628">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="68e29-629">Si falta el origen \*/clientsideassets, se producirá un error en las soluciones de SharePoint Framework y no se generarán mensajes de advertencia o error.</span><span class="sxs-lookup"><span data-stu-id="68e29-629">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="68e29-630">Es posible que falte este origen porque la red CDN se habilitó con el parámetro _-NoDefaultOrigins_ establecido en **$true** o porque el origen se eliminó manualmente.</span><span class="sxs-lookup"><span data-stu-id="68e29-630">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="68e29-631">Puedes comprobar qué orígenes están presentes con el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68e29-631">You can check to see which origins are present with the following PowerShell command:</span></span>

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="68e29-632">O puede consultar con la CLI de Office 365:</span><span class="sxs-lookup"><span data-stu-id="68e29-632">Or you can check with the Office 365 CLI:</span></span>

``` powershell
spo cdn origin list
```

<span data-ttu-id="68e29-633">Para agregar el origen en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68e29-633">To add the origin in PowerShell:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="68e29-634">Para agregar el origen en la CLI de Office 365:</span><span class="sxs-lookup"><span data-stu-id="68e29-634">To add the origin in the Office 365 CLI:</span></span>

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="68e29-635">¿Qué módulos de PowerShell y shells de CLI necesito para trabajar con la red CDN de Office 365?</span><span class="sxs-lookup"><span data-stu-id="68e29-635">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="68e29-636">Puede elegir trabajar con la red CDN de Office 365 mediante el módulo de PowerShell del Shell de administración de **SharePoint Online** o la **CLI de Office 365.**</span><span class="sxs-lookup"><span data-stu-id="68e29-636">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="68e29-637">Introducción al Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68e29-637">Getting started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="68e29-638">Instalar Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="68e29-638">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="68e29-639">Vea también</span><span class="sxs-lookup"><span data-stu-id="68e29-639">See also</span></span>

[<span data-ttu-id="68e29-640">Redes de entrega de contenido</span><span class="sxs-lookup"><span data-stu-id="68e29-640">Content Delivery Networks</span></span>](https://aka.ms/o365cdns)

[<span data-ttu-id="68e29-641">Planeamiento de red y ajuste del rendimiento para Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-641">Network planning and performance tuning for Office 365</span></span>](https://aka.ms/tune)

[<span data-ttu-id="68e29-642">Serie de rendimiento de SharePoint: serie de vídeos de red CDN de Office 365</span><span class="sxs-lookup"><span data-stu-id="68e29-642">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
