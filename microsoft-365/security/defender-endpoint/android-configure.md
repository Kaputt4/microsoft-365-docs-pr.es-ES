---
title: Configurar ATP de Microsoft Defender para características de Android
description: Describe cómo configurar ATP de Microsoft Defender para Android
keywords: microsoft, defender, atp, android, configuration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4325020e653f14898ece4192e03cbf8b90131136
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163452"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a><span data-ttu-id="fd9bf-104">Configurar Defender para las características de Endpoint para Android</span><span class="sxs-lookup"><span data-stu-id="fd9bf-104">Configure Defender for Endpoint for Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fd9bf-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="fd9bf-105">**Applies to:**</span></span>
- [<span data-ttu-id="fd9bf-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="fd9bf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fd9bf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd9bf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a><span data-ttu-id="fd9bf-108">Acceso condicional con Defender para endpoint para Android</span><span class="sxs-lookup"><span data-stu-id="fd9bf-108">Conditional Access with Defender for Endpoint for Android</span></span>  
<span data-ttu-id="fd9bf-109">Microsoft Defender para Endpoint para Android, junto con Microsoft Intune y Azure Active Directory, permite aplicar el cumplimiento de dispositivos y las directivas de acceso condicional en función de los niveles de riesgo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-109">Microsoft Defender for Endpoint for Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="fd9bf-110">Defender for Endpoint es una solución de Mobile Threat Defense (MTD) que puedes implementar para aprovechar esta funcionalidad a través de Intune.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="fd9bf-111">Para obtener más información acerca de cómo configurar Defender para Endpoint para Android y acceso condicional, vea [Defender for Endpoint e Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="fd9bf-111">For more information about how to set up Defender for Endpoint for Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="fd9bf-112">Configurar indicadores personalizados</span><span class="sxs-lookup"><span data-stu-id="fd9bf-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="fd9bf-113">Defender para Endpoint para Android solo admite la creación de indicadores personalizados para direcciones IP y direcciones URL/dominios.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-113">Defender for Endpoint for Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="fd9bf-114">Defender para Endpoint para Android permite a los administradores configurar indicadores personalizados para admitir dispositivos Android también.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-114">Defender for Endpoint for Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="fd9bf-115">Para obtener más información sobre cómo configurar indicadores personalizados, vea [Administrar indicadores](manage-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="fd9bf-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="fd9bf-116">Configurar la protección web</span><span class="sxs-lookup"><span data-stu-id="fd9bf-116">Configure web protection</span></span>
<span data-ttu-id="fd9bf-117">Defender para Endpoint para Android permite a los administradores de TI configurar la característica de protección web.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-117">Defender for Endpoint for Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="fd9bf-118">Esta funcionalidad está disponible en el Centro de administración de Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="fd9bf-119">Defender para Endpoint para Android usaría una VPN para proporcionar la característica de Protección web.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-119">Defender for Endpoint for Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="fd9bf-120">No se trata de una VPN normal y es una VPN local o auto-looping que no toma tráfico fuera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fd9bf-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="fd9bf-121">Para obtener más información, vea [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span><span class="sxs-lookup"><span data-stu-id="fd9bf-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fd9bf-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="fd9bf-122">Related topics</span></span>
- [<span data-ttu-id="fd9bf-123">Información general sobre Microsoft Defender para endpoint para Android</span><span class="sxs-lookup"><span data-stu-id="fd9bf-123">Overview of Microsoft Defender for Endpoint for Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="fd9bf-124">Implementar Microsoft Defender para endpoint para Android con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fd9bf-124">Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune</span></span>](android-intune.md)
