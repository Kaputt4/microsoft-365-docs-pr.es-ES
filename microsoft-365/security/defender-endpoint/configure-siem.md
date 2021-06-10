---
title: Extraer detecciones a las herramientas SIEM desde Microsoft Defender para endpoint
description: Obtenga información sobre cómo usar la API de REST y configurar las herramientas de administración de eventos y información de seguridad admitidas para recibir y extraer detecciones.
keywords: configure siem, security information and events management tools, splunk, arcsight, custom indicators, rest api, alert definitions, indicators of compromise
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
ms.openlocfilehash: 97a64c8537ff2a6f9948ed6ed056b8aa7379ce69
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222340"
---
# <a name="pull-detections-to-your-siem-tools"></a><span data-ttu-id="9caca-104">Extraer detecciones a las herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="9caca-104">Pull detections to your SIEM tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9caca-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9caca-105">**Applies to:**</span></span>
- [<span data-ttu-id="9caca-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="9caca-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9caca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9caca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9caca-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="9caca-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9caca-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="9caca-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a><span data-ttu-id="9caca-110">Extraer detecciones mediante herramientas de administración de eventos y información de seguridad (SIEM)</span><span class="sxs-lookup"><span data-stu-id="9caca-110">Pull detections using security information and events management (SIEM) tools</span></span>

>[!NOTE]
>- <span data-ttu-id="9caca-111">[Microsoft Defender para alerta de](alerts.md) extremo se compone de una o más detecciones.</span><span class="sxs-lookup"><span data-stu-id="9caca-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="9caca-112">[Microsoft Defender para la detección de](api-portal-mapping.md) puntos de conexión se compone del evento sospechoso que se produjo en el dispositivo y sus detalles de alerta relacionados.</span><span class="sxs-lookup"><span data-stu-id="9caca-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="9caca-113">-La API de alertas de punto de conexión de Microsoft Defender es la API más reciente para el consumo de alertas y contiene una lista detallada de pruebas relacionadas para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="9caca-113">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="9caca-114">Para obtener más información, vea [Alert methods and properties y](alerts.md) List [alerts](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="9caca-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="9caca-115">Defender for Endpoint admite las herramientas de administración de eventos y de información de seguridad (SIEM) para extraer detecciones.</span><span class="sxs-lookup"><span data-stu-id="9caca-115">Defender for Endpoint supports security information and event management (SIEM) tools to pull detections.</span></span> <span data-ttu-id="9caca-116">Defender for Endpoint expone alertas a través de un extremo HTTPS hospedado en Azure.</span><span class="sxs-lookup"><span data-stu-id="9caca-116">Defender for Endpoint exposes alerts through an HTTPS endpoint hosted in Azure.</span></span> <span data-ttu-id="9caca-117">El extremo se puede configurar para extraer detecciones del inquilino de la empresa en Azure Active Directory (AAD) mediante el protocolo de autenticación de OAuth 2.0 para una aplicación de AAD que representa el conector SIEM específico instalado en el entorno.</span><span class="sxs-lookup"><span data-stu-id="9caca-117">The endpoint can be configured to pull detections from your enterprise tenant in Azure Active Directory (AAD) using the OAuth 2.0 authentication protocol for an AAD application that represents the specific SIEM connector installed in your environment.</span></span>

<span data-ttu-id="9caca-118">Defender para endpoint actualmente admite las siguientes herramientas de solución SIEM específicas a través de un modelo de integración SIEM dedicado:</span><span class="sxs-lookup"><span data-stu-id="9caca-118">Defender for Endpoint currently supports the following specific SIEM solution tools through a dedicated SIEM integration model:</span></span>

- <span data-ttu-id="9caca-119">IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="9caca-119">IBM QRadar</span></span>
- <span data-ttu-id="9caca-120">Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="9caca-120">Micro Focus ArcSight</span></span>

<span data-ttu-id="9caca-121">Otras soluciones SIEM (como Splunk, RSA NetWitness) se admiten a través de un modelo de integración diferente basado en la nueva API de alertas.</span><span class="sxs-lookup"><span data-stu-id="9caca-121">Other SIEM solutions (such as Splunk, RSA NetWitness) are supported through a different integration model based on the new Alert API.</span></span> <span data-ttu-id="9caca-122">Para obtener más información, vea la [página Aplicación de partners](https://securitycenter.microsoft.com/interoperability/partners) y seleccione la sección Información de seguridad y análisis para obtener información completa.</span><span class="sxs-lookup"><span data-stu-id="9caca-122">For more information, view the [Partner application](https://securitycenter.microsoft.com/interoperability/partners) page and select the Security Information and Analytics section for full details.</span></span>

<span data-ttu-id="9caca-123">Para usar cualquiera de estas herramientas SIEM compatibles, deberá:</span><span class="sxs-lookup"><span data-stu-id="9caca-123">To use either of these supported SIEM tools, you'll need to:</span></span>

- [<span data-ttu-id="9caca-124">Habilitar la integración de SIEM en Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9caca-124">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- <span data-ttu-id="9caca-125">Configurar la herramienta SIEM compatible:</span><span class="sxs-lookup"><span data-stu-id="9caca-125">Configure the supported SIEM tool:</span></span>
     - [<span data-ttu-id="9caca-126">Configurar Micro Focus ArcSight para extraer Defender para detecciones de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="9caca-126">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>](configure-arcsight.md)
     - <span data-ttu-id="9caca-127">Configurar IBM QRadar para extraer Defender para detecciones de puntos de conexión Para obtener más información, vea [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span><span class="sxs-lookup"><span data-stu-id="9caca-127">Configure IBM QRadar to pull Defender for Endpoint detections For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

<span data-ttu-id="9caca-128">Para obtener más información sobre la lista de campos expuestos en la API de detección, vea [Defender for Endpoint Detection fields](api-portal-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="9caca-128">For more information on the list of fields exposed in the Detection API, see [Defender for Endpoint Detection fields](api-portal-mapping.md).</span></span>
