---
title: Usar Microsoft Defender para Office 365 junto con Microsoft Defender para endpoint
f1.keywords:
- NOCSH
keywords: integrate, Microsoft Defender, Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Usa Microsoft Defender para Office 365 junto con Microsoft Defender para Endpoint para obtener información más detallada sobre las amenazas contra los dispositivos y el contenido de correo electrónico.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d54e4ec40c636b8b3ea319e79cbad5005850952
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029272"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="4d3de-104">Usar Microsoft Defender para Office 365 junto con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="4d3de-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4d3de-105">[Microsoft Defender para Office 365](defender-for-office-365.md) puede configurarse para funcionar con [Microsoft Defender para endpoint](/windows/security/threat-protection).</span><span class="sxs-lookup"><span data-stu-id="4d3de-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="4d3de-106">La integración de Microsoft Defender para Office 365 con Microsoft Defender para endpoint puede ayudar a su equipo de operaciones de seguridad a supervisar y tomar medidas rápidamente si los dispositivos de los usuarios están en riesgo.</span><span class="sxs-lookup"><span data-stu-id="4d3de-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="4d3de-107">Por ejemplo, una vez habilitada la integración, el equipo de operaciones de seguridad podrá ver los dispositivos potencialmente afectados por un mensaje de correo electrónico detectado, así como cuántas alertas recientes se generaron para esos dispositivos en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="4d3de-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="4d3de-108">En la siguiente imagen se muestra el aspecto **de** la pestaña Dispositivos cuando se habilita la integración de Microsoft Defender para endpoints:</span><span class="sxs-lookup"><span data-stu-id="4d3de-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Cuando Microsoft Defender para endpoint está habilitado, puedes ver una lista de dispositivos con alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="4d3de-110">En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico detectado tienen cuatro dispositivos y uno tiene una alerta.</span><span class="sxs-lookup"><span data-stu-id="4d3de-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="4d3de-111">Al hacer clic en el vínculo de un dispositivo, se abre su [página en Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (anteriormente el Centro de seguridad de Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="4d3de-111">Clicking the link for a device opens its page in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender security center).</span></span>

> [!TIP]
> <span data-ttu-id="4d3de-112">El portal Microsoft 365 Defender reemplaza al Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="4d3de-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="4d3de-113">Consulta [Microsoft Defender para Endpoint en Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="4d3de-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="4d3de-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d3de-114">Requirements</span></span>

- <span data-ttu-id="4d3de-115">Su organización debe tener Microsoft Defender para Office 365 (o Office 365 E5) y Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="4d3de-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="4d3de-116">Debe ser un administrador global o tener un rol de administrador de seguridad (como administrador de seguridad) asignado en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4d3de-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="4d3de-117">Para obtener más información, vea [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="4d3de-117">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="4d3de-118">Debe tener acceso al [Explorador (o detecciones en tiempo real).](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="4d3de-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="4d3de-119">Para integrar Microsoft Defender para Office 365 con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="4d3de-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="4d3de-120">La integración de Microsoft Defender para Office 365 con Microsoft Defender para endpoint se configura en Defender para Endpoint y Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="4d3de-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="4d3de-121">Como administrador global o como administrador de seguridad, <https://security.microsoft.com/threatexplorer> .</span><span class="sxs-lookup"><span data-stu-id="4d3de-121">As a global administrator or a security administrator,<https://security.microsoft.com/threatexplorer>.</span></span>

2. <span data-ttu-id="4d3de-122">En el panel de navegación, elija **Correo & explorador de** \> **colaboración**.</span><span class="sxs-lookup"><span data-stu-id="4d3de-122">In the navigation pane, choose **Email & collaboration** \> **Explorer**.</span></span>

3. <span data-ttu-id="4d3de-123">En la **página Explorador,** en la esquina superior derecha de la pantalla, haga clic en **MDE Configuración**.</span><span class="sxs-lookup"><span data-stu-id="4d3de-123">On the **Explorer** page, in the upper right corner of the screen, click **MDE Settings**.</span></span>

4. <span data-ttu-id="4d3de-124">En el control desplegable de conexión de **Microsoft Defender** para puntos de conexión que aparece, activa Conectar a Microsoft **Defender para** Endpoint ( Toggle on ) y, a continuación, haz clic en Cerrar ![ icono ](../../media/scc-toggle-on.png) ![ ](../../media/m365-cc-sc-close-icon.png) **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="4d3de-124">In the **Microsoft Defender for Endpoint connection** flyout that appears, turn on **Connect to Microsoft Defender for Endpoint** (![Toggle on](../../media/scc-toggle-on.png)) and then click ![Close icon](../../media/m365-cc-sc-close-icon.png) **Close**.</span></span>

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="Conexión MDE":::

5. <span data-ttu-id="4d3de-126">En el panel de navegación, elija **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="4d3de-126">Back in the navigation pane, choose **Settings**.</span></span> <span data-ttu-id="4d3de-127">En la **Configuración,** elija **Extremos**</span><span class="sxs-lookup"><span data-stu-id="4d3de-127">On the **Settings** page, choose **Endpoints**</span></span>

6. <span data-ttu-id="4d3de-128">En la **página Extremos que** se abre, elija Características **avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="4d3de-128">On the **Endpoints** page that opens, choose **Advanced features**.</span></span>

7. <span data-ttu-id="4d3de-129">Desplácese hacia abajo **hasta Office 365 de inteligencia** de amenazas y actóla ( Activar ![ ](../../media/scc-toggle-on.png) ).</span><span class="sxs-lookup"><span data-stu-id="4d3de-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn it on (![Toggle on](../../media/scc-toggle-on.png)).</span></span>

   <span data-ttu-id="4d3de-130">Cuando haya terminado, haga clic en **Guardar preferencias**.</span><span class="sxs-lookup"><span data-stu-id="4d3de-130">When you're finished, click **Save preferences**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4d3de-131">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="4d3de-131">Related articles</span></span>

[<span data-ttu-id="4d3de-132">Capacidades de investigación y respuesta de amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="4d3de-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="4d3de-133">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="4d3de-133">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="4d3de-134">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4d3de-134">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
