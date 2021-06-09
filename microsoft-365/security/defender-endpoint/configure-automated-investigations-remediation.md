---
title: Configurar capacidades automatizadas de investigación y corrección
description: Configure las capacidades automatizadas de investigación y corrección en Microsoft Defender para endpoint.
keywords: configure, setup, automated, investigation, detection, alerts, remediation, response
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: bd86458749db4019bb247a3664748b9891965754
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841354"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="68e64-104">Configurar las capacidades automatizadas de investigación y corrección en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="68e64-104">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="68e64-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="68e64-105">**Applies to:**</span></span>
- [<span data-ttu-id="68e64-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="68e64-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="68e64-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68e64-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="68e64-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="68e64-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="68e64-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="68e64-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="68e64-110">Si su organización usa [Microsoft Defender para](/windows/security/threat-protection/) endpoint (Defender para endpoint), las capacidades automatizadas de investigación y corrección pueden ahorrar tiempo y esfuerzo al equipo de operaciones de seguridad. [](/microsoft-365/security/defender-endpoint/automated-investigations)</span><span class="sxs-lookup"><span data-stu-id="68e64-110">If your organization is using [Microsoft Defender for Endpoint](/windows/security/threat-protection/) (Defender for Endpoint), [automated investigation and remediation capabilities](/microsoft-365/security/defender-endpoint/automated-investigations) can save your security operations team time and effort.</span></span> <span data-ttu-id="68e64-111">Como se describe en [esta entrada de blog,](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)estas capacidades imitan los pasos ideales que un analista de seguridad realiza para investigar y corregir amenazas.</span><span class="sxs-lookup"><span data-stu-id="68e64-111">As outlined in [this blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946), these capabilities mimic the ideal steps that a security analyst takes to investigate and remediate threats.</span></span> <span data-ttu-id="68e64-112">[Obtenga más información sobre la investigación automatizada y la corrección](/microsoft-365/security/defender-endpoint/automated-investigations).</span><span class="sxs-lookup"><span data-stu-id="68e64-112">[Learn more about automated investigation and remediation](/microsoft-365/security/defender-endpoint/automated-investigations).</span></span> 

<span data-ttu-id="68e64-113">Para configurar la investigación y corrección automatizadas,</span><span class="sxs-lookup"><span data-stu-id="68e64-113">To configure automated investigation and remediation,</span></span>
1. <span data-ttu-id="68e64-114">[Activar las características](#turn-on-automated-investigation-and-remediation); y</span><span class="sxs-lookup"><span data-stu-id="68e64-114">[Turn on the features](#turn-on-automated-investigation-and-remediation); and</span></span> 
2. <span data-ttu-id="68e64-115">[Configurar grupos de dispositivos](#set-up-device-groups).</span><span class="sxs-lookup"><span data-stu-id="68e64-115">[Set up device groups](#set-up-device-groups).</span></span>

## <a name="turn-on-automated-investigation-and-remediation"></a><span data-ttu-id="68e64-116">Activar la investigación y corrección automatizadas</span><span class="sxs-lookup"><span data-stu-id="68e64-116">Turn on automated investigation and remediation</span></span>

1. <span data-ttu-id="68e64-117">Como administrador global o administrador de seguridad, vaya al Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="68e64-117">As a global administrator or security administrator, go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>
2. <span data-ttu-id="68e64-118">En el panel de navegación, **elija Configuración**.</span><span class="sxs-lookup"><span data-stu-id="68e64-118">In the navigation pane, choose **Settings**.</span></span>
3. <span data-ttu-id="68e64-119">En la **sección General,** seleccione **Características avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="68e64-119">In the **General** section, select **Advanced features**.</span></span>
4. <span data-ttu-id="68e64-120">Active la investigación **automatizada y** resuelva automáticamente **las alertas**.</span><span class="sxs-lookup"><span data-stu-id="68e64-120">Turn on both **Automated Investigation** and **Automatically resolve alerts**.</span></span>

## <a name="set-up-device-groups"></a><span data-ttu-id="68e64-121">Configurar grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="68e64-121">Set up device groups</span></span>

1. <span data-ttu-id="68e64-122">En la Centro de seguridad de Microsoft Defender ( ), en la [https://securitycenter.windows.com](https://securitycenter.windows.com) **página Configuración,** en **Permisos**, seleccione **Grupos de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="68e64-122">In the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)), on the **Settings** page, under **Permissions**, select **Device groups**.</span></span>
2. <span data-ttu-id="68e64-123">Seleccione **+ Agregar grupo de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="68e64-123">Select **+ Add device group**.</span></span>
3. <span data-ttu-id="68e64-124">Crea al menos un grupo de dispositivos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="68e64-124">Create at least one device group, as follows:</span></span>
   - <span data-ttu-id="68e64-125">Especifica un nombre y una descripción para el grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="68e64-125">Specify a name and description for the device group.</span></span>
   - <span data-ttu-id="68e64-126">En la **lista Nivel de automatización,** seleccione un nivel, como **Full – remediar las amenazas automáticamente.**</span><span class="sxs-lookup"><span data-stu-id="68e64-126">In the **Automation level list**, select a level, such as **Full – remediate threats automatically**.</span></span> <span data-ttu-id="68e64-127">El nivel de automatización determina si las acciones de corrección se toman automáticamente o solo tras la aprobación.</span><span class="sxs-lookup"><span data-stu-id="68e64-127">The automation level determines whether remediation actions are taken automatically, or only upon approval.</span></span> <span data-ttu-id="68e64-128">Para obtener más información, vea [Automation levels in automated investigation and remediation](automation-levels.md).</span><span class="sxs-lookup"><span data-stu-id="68e64-128">To learn more, see [Automation levels in automated investigation and remediation](automation-levels.md).</span></span>
   - <span data-ttu-id="68e64-129">En la **sección Miembros,** use una o más condiciones para identificar e incluir dispositivos.</span><span class="sxs-lookup"><span data-stu-id="68e64-129">In the **Members** section, use one or more conditions to identify and include devices.</span></span>
   - <span data-ttu-id="68e64-130">En la **pestaña Acceso de** usuario, selecciona los Azure Active Directory [que](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) deben tener acceso al grupo de dispositivos que estás creando.</span><span class="sxs-lookup"><span data-stu-id="68e64-130">On the **User access** tab, select the [Azure Active Directory groups](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) who should have access to the device group you're creating.</span></span>
4. <span data-ttu-id="68e64-131">Selecciona **Listo** cuando termines de configurar el grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="68e64-131">Select **Done** when you're finished setting up your device group.</span></span>

## <a name="next-steps"></a><span data-ttu-id="68e64-132">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="68e64-132">Next steps</span></span>

- [<span data-ttu-id="68e64-133">Visite el Centro de acciones para ver las acciones de corrección pendientes y completadas</span><span class="sxs-lookup"><span data-stu-id="68e64-133">Visit the Action Center to view pending and completed remediation actions</span></span>](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [<span data-ttu-id="68e64-134">Revisar y aprobar acciones pendientes</span><span class="sxs-lookup"><span data-stu-id="68e64-134">Review and approve pending actions</span></span>](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a><span data-ttu-id="68e64-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="68e64-135">See also</span></span>

- [<span data-ttu-id="68e64-136">Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="68e64-136">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
