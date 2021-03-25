---
title: Crear indicadores
ms.reviewer: ''
description: Cree indicadores para un hash de archivo, una dirección IP, direcciones URL o dominios que definan la detección, prevención y exclusión de entidades.
keywords: manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a04f3be1f13fb57cd76cda7115d014f2ba3aa8d6
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198842"
---
# <a name="create-indicators"></a><span data-ttu-id="ababf-104">Crear indicadores</span><span class="sxs-lookup"><span data-stu-id="ababf-104">Create indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ababf-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ababf-105">**Applies to:**</span></span>
- [<span data-ttu-id="ababf-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="ababf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ababf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ababf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> <span data-ttu-id="ababf-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="ababf-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ababf-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="ababf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="ababf-110">El indicador de coincidencia de puntos de conexión (IoCs) es una característica esencial en cada solución de protección de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="ababf-110">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="ababf-111">Esta funcionalidad ofrece a SecOps la capacidad de establecer una lista de indicadores para la detección y para el bloqueo (prevención y respuesta).</span><span class="sxs-lookup"><span data-stu-id="ababf-111">This capability gives SecOps the ability to set a list of indicators for detection and for blocking (prevention and response).</span></span>

<span data-ttu-id="ababf-112">Cree indicadores que definan la detección, prevención y exclusión de entidades.</span><span class="sxs-lookup"><span data-stu-id="ababf-112">Create indicators that define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="ababf-113">Puedes definir la acción que se va a realizar, así como la duración de cuándo aplicar la acción, así como el ámbito del grupo de dispositivos al que aplicarla.</span><span class="sxs-lookup"><span data-stu-id="ababf-113">You can define the action to be taken as well as the duration for when to apply the action as well as the scope of the device group to apply it to.</span></span>

<span data-ttu-id="ababf-114">Los orígenes compatibles actualmente son el motor de detección en la nube de Defender for Endpoint, el motor automatizado de investigación y corrección y el motor de prevención de puntos de conexión (Antivirus de Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="ababf-114">Currently supported sources are the cloud detection engine of Defender for Endpoint, the automated investigation and remediation engine, and the endpoint prevention engine (Microsoft Defender Antivirus).</span></span>

<span data-ttu-id="ababf-115">**Motor de detección de nube**</span><span class="sxs-lookup"><span data-stu-id="ababf-115">**Cloud detection engine**</span></span><br>
<span data-ttu-id="ababf-116">El motor de detección en la nube de Defender for Endpoint examina periódicamente los datos recopilados e intenta coincidir con los indicadores que estableces.</span><span class="sxs-lookup"><span data-stu-id="ababf-116">The cloud detection engine of Defender for Endpoint regularly scans collected data and tries to match the indicators you set.</span></span> <span data-ttu-id="ababf-117">Cuando haya una coincidencia, se realizará una acción de acuerdo con la configuración especificada para IoC.</span><span class="sxs-lookup"><span data-stu-id="ababf-117">When there is a match, action will be taken according to the settings you specified for the IoC.</span></span>

<span data-ttu-id="ababf-118">**Motor de prevención de extremos**</span><span class="sxs-lookup"><span data-stu-id="ababf-118">**Endpoint prevention engine**</span></span><br>
<span data-ttu-id="ababf-119">El agente de prevención respeta la misma lista de indicadores.</span><span class="sxs-lookup"><span data-stu-id="ababf-119">The same list of indicators is honored by the prevention agent.</span></span> <span data-ttu-id="ababf-120">Es decir, si Microsoft Defender AV es el antivirus principal configurado, los indicadores coincidentes se tratarán de acuerdo con la configuración.</span><span class="sxs-lookup"><span data-stu-id="ababf-120">Meaning, if Microsoft Defender AV is the primary AV configured, the matched indicators will be treated according to the settings.</span></span> <span data-ttu-id="ababf-121">Por ejemplo, si la acción es "Alerta y bloqueo", AV de Microsoft Defender impedirá las ejecuciones de archivos (bloquear y corregir) y se genera una alerta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ababf-121">For example, if the action is "Alert and Block", Microsoft Defender AV will prevent file executions (block and remediate) and a corresponding alert will be raised.</span></span> <span data-ttu-id="ababf-122">Por otra parte, si la acción está establecida en "Permitir", AV de Microsoft Defender no detectará ni bloqueará la ejecución del archivo.</span><span class="sxs-lookup"><span data-stu-id="ababf-122">On the other hand, if the Action is set to "Allow", Microsoft Defender AV will not detect nor block the file from being run.</span></span>

<span data-ttu-id="ababf-123">**Motor automatizado de investigación y corrección**</span><span class="sxs-lookup"><span data-stu-id="ababf-123">**Automated investigation and remediation engine**</span></span><BR>
<span data-ttu-id="ababf-124">La investigación automatizada y la corrección se comportan igual.</span><span class="sxs-lookup"><span data-stu-id="ababf-124">The automated investigation and remediation behave the same.</span></span> <span data-ttu-id="ababf-125">Si un indicador está establecido en "Permitir", la investigación automatizada y la corrección omitirán un veredicto "malo" para él.</span><span class="sxs-lookup"><span data-stu-id="ababf-125">If an indicator is set to "Allow", Automated investigation and remediation will ignore a "bad" verdict for it.</span></span> <span data-ttu-id="ababf-126">Si se establece en "Bloquear", la investigación automatizada y la corrección la tratarán como "mala".</span><span class="sxs-lookup"><span data-stu-id="ababf-126">If set to "Block", Automated investigation and remediation will treat it as "bad".</span></span>


<span data-ttu-id="ababf-127">Las acciones admitidas actuales son:</span><span class="sxs-lookup"><span data-stu-id="ababf-127">The current supported actions are:</span></span>
- <span data-ttu-id="ababf-128">Permitir</span><span class="sxs-lookup"><span data-stu-id="ababf-128">Allow</span></span>
- <span data-ttu-id="ababf-129">Solo alerta</span><span class="sxs-lookup"><span data-stu-id="ababf-129">Alert only</span></span>
- <span data-ttu-id="ababf-130">Alerta y bloqueo</span><span class="sxs-lookup"><span data-stu-id="ababf-130">Alert and block</span></span>


<span data-ttu-id="ababf-131">Puede crear un indicador para:</span><span class="sxs-lookup"><span data-stu-id="ababf-131">You can create an indicator for:</span></span>
- [<span data-ttu-id="ababf-132">Files</span><span class="sxs-lookup"><span data-stu-id="ababf-132">Files</span></span>](indicator-file.md)
- [<span data-ttu-id="ababf-133">Direcciones IP, direcciones URL/dominios</span><span class="sxs-lookup"><span data-stu-id="ababf-133">IP addresses, URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="ababf-134">Certificados</span><span class="sxs-lookup"><span data-stu-id="ababf-134">Certificates</span></span>](indicator-certificates.md)


> [!NOTE]
> <span data-ttu-id="ababf-135">Hay un límite de 15.000 indicadores por inquilino.</span><span class="sxs-lookup"><span data-stu-id="ababf-135">There is a limit of 15,000 indicators per tenant.</span></span> <span data-ttu-id="ababf-136">Los indicadores de archivo y certificado no [bloquean las exclusiones definidas para Antivirus de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="ababf-136">File and certificate indicators do not block [exclusions defined for Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="ababf-137">Los indicadores no se admiten en Microsoft Defender Antivirus en modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="ababf-137">Indicators are not supported in Microsoft Defender Antivirus is in passive mode.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="ababf-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ababf-138">Related topics</span></span>

- [<span data-ttu-id="ababf-139">Crear IoC contextual</span><span class="sxs-lookup"><span data-stu-id="ababf-139">Create contextual IoC</span></span>](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [<span data-ttu-id="ababf-140">Usar la API de indicadores de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="ababf-140">Use the Microsoft Defender for Endpoint indicators API</span></span>](ti-indicator.md)
- [<span data-ttu-id="ababf-141">Usar soluciones integradas de partners</span><span class="sxs-lookup"><span data-stu-id="ababf-141">Use partner integrated solutions</span></span>](partner-applications.md)
