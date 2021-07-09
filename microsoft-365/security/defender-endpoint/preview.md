---
title: Características de vista previa de Microsoft Defender para puntos de conexión
description: Obtenga información sobre cómo obtener acceso a las características de vista previa de Microsoft Defender para puntos de conexión.
keywords: vista previa, experiencia de vista previa, Microsoft Defender para endpoint, características, actualizaciones
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0b6edbdcda61eaf402275ae0b6dc9a38c5fe19f7
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339495"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="2ac21-104">Características de vista previa de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="2ac21-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2ac21-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2ac21-105">**Applies to:**</span></span>
- [<span data-ttu-id="2ac21-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2ac21-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2ac21-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ac21-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2ac21-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="2ac21-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2ac21-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2ac21-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="2ac21-110">El servicio Defender for Endpoint se actualiza constantemente para incluir nuevas mejoras y funcionalidades de características.</span><span class="sxs-lookup"><span data-stu-id="2ac21-110">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="2ac21-111">Obtén información sobre las nuevas características en la versión preliminar de Defender para endpoint y sé uno de los primeros en probar las próximas características al activar la experiencia de vista previa.</span><span class="sxs-lookup"><span data-stu-id="2ac21-111">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="2ac21-112">Reciba una notificación cuando se actualice esta página copiando y pegando la siguiente dirección URL en el lector de fuentes: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span><span class="sxs-lookup"><span data-stu-id="2ac21-112">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span></span>

<span data-ttu-id="2ac21-113">Para obtener más información sobre las nuevas funcionalidades que están disponibles en general, vea [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span><span class="sxs-lookup"><span data-stu-id="2ac21-113">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

 ## <a name="what-you-need-to-know"></a><span data-ttu-id="2ac21-114">Lo que necesita saber</span><span class="sxs-lookup"><span data-stu-id="2ac21-114">What you need to know</span></span>

<span data-ttu-id="2ac21-115">Al trabajar con características en versión preliminar pública, estas características:</span><span class="sxs-lookup"><span data-stu-id="2ac21-115">When working with features in public preview, these features:</span></span>

- <span data-ttu-id="2ac21-116">Puede que tenga funciones restringidas o limitadas.</span><span class="sxs-lookup"><span data-stu-id="2ac21-116">May have restricted or limited functionality.</span></span> <span data-ttu-id="2ac21-117">Por ejemplo, la característica solo puede aplicarse a una plataforma.</span><span class="sxs-lookup"><span data-stu-id="2ac21-117">For example, the feature may only apply to one platform.</span></span>
- <span data-ttu-id="2ac21-118">Normalmente, pasan por los cambios de características antes de que estén generalmente disponibles (GA).</span><span class="sxs-lookup"><span data-stu-id="2ac21-118">Typically go through feature changes before they're generally available (GA).</span></span>
- <span data-ttu-id="2ac21-119">Son totalmente compatibles con Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ac21-119">Are fully supported by Microsoft.</span></span>
- <span data-ttu-id="2ac21-120">Solo puede estar disponible en regiones geográficas seleccionadas o entornos en la nube.</span><span class="sxs-lookup"><span data-stu-id="2ac21-120">May only be available in selected geographic regions or cloud environments.</span></span> <span data-ttu-id="2ac21-121">Por ejemplo, es posible que la característica no exista en la nube del gobierno.</span><span class="sxs-lookup"><span data-stu-id="2ac21-121">For example, the feature may not exist in the government cloud.</span></span>
- <span data-ttu-id="2ac21-122">Las características individuales de la versión preliminar pueden tener más restricciones de uso y compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="2ac21-122">Individual features in preview may have more usage and support restrictions.</span></span> <span data-ttu-id="2ac21-123">Si es así, esta información se indica normalmente en la documentación de características.</span><span class="sxs-lookup"><span data-stu-id="2ac21-123">If so, this information is typically noted in the feature documentation.</span></span>
- <span data-ttu-id="2ac21-124">Las versiones preliminares se proporcionan con un nivel de soporte estándar y se pueden usar para entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="2ac21-124">The preview versions are provided with a standard support level, and can be used for production environments.</span></span> 



## <a name="turn-on-preview-features"></a><span data-ttu-id="2ac21-125">Activar la versión preliminar de las características</span><span class="sxs-lookup"><span data-stu-id="2ac21-125">Turn on preview features</span></span>

<span data-ttu-id="2ac21-126">Tendrás acceso a las próximas características sobre las que puedes proporcionar comentarios para mejorar la experiencia general antes de que las características estén disponibles en general.</span><span class="sxs-lookup"><span data-stu-id="2ac21-126">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="2ac21-127">Active la configuración de la experiencia de la versión preliminar para estar entre los primeros en probar las próximas características.</span><span class="sxs-lookup"><span data-stu-id="2ac21-127">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="2ac21-128">En el panel de navegación, **seleccione Configuración** Características avanzadas Características  >    >  **de vista previa**.</span><span class="sxs-lookup"><span data-stu-id="2ac21-128">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="2ac21-129">Alterna la configuración entre **Activar** y **Desactivar** y selecciona **Guardar preferencias**.</span><span class="sxs-lookup"><span data-stu-id="2ac21-129">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="2ac21-130">Versión preliminar de las características</span><span class="sxs-lookup"><span data-stu-id="2ac21-130">Preview features</span></span>

<span data-ttu-id="2ac21-131">En la versión preliminar se incluyen las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="2ac21-131">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="2ac21-132">Filtrado de contenido web</span><span class="sxs-lookup"><span data-stu-id="2ac21-132">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="2ac21-133">El filtrado de contenido web forma parte de las funciones de protección web en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="2ac21-133">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="2ac21-134">Permite a la organización realizar un seguimiento y regular el acceso a sitios web en función de sus categorías de contenido.</span><span class="sxs-lookup"><span data-stu-id="2ac21-134">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="2ac21-135">Muchos de estos sitios web, aunque no son malintencionados, pueden ser problemáticos debido a las normativas de cumplimiento, el uso del ancho de banda u otras preocupaciones.</span><span class="sxs-lookup"><span data-stu-id="2ac21-135">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="2ac21-136">Cumplimiento normativo y estado del dispositivo</span><span class="sxs-lookup"><span data-stu-id="2ac21-136">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="2ac21-137">El informe de cumplimiento y estado del dispositivo proporciona información de alto nivel sobre los dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="2ac21-137">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="2ac21-138">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="2ac21-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2ac21-139">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2ac21-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
