---
title: Usar Microsoft Defender para Office 365 junto con Microsoft Defender para endpoint
f1.keywords:
- NOCSH
keywords: integración, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Use Microsoft Defender para Office 365 junto con Microsoft Defender para Endpoint para obtener información más detallada sobre las amenazas contra sus dispositivos y contenido de correo electrónico.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c2e7a3eeb9576b53723a786de85f0c4bece679b4
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205480"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="e36cb-104">Usar Microsoft Defender para Office 365 junto con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="e36cb-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e36cb-105">[Microsoft Defender para Office 365](defender-for-office-365.md) se puede configurar para funcionar con [Microsoft Defender para endpoint](/windows/security/threat-protection).</span><span class="sxs-lookup"><span data-stu-id="e36cb-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="e36cb-106">La integración de Microsoft Defender para Office 365 con Microsoft Defender para endpoint puede ayudar a su equipo de operaciones de seguridad a supervisar y tomar medidas rápidamente si los dispositivos de los usuarios están en riesgo.</span><span class="sxs-lookup"><span data-stu-id="e36cb-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="e36cb-107">Por ejemplo, una vez habilitada la integración, el equipo de operaciones de seguridad podrá ver los dispositivos potencialmente afectados por un mensaje de correo electrónico detectado, así como cuántas alertas recientes se generaron para esos dispositivos en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="e36cb-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="e36cb-108">En la siguiente imagen se muestra el aspecto **de** la pestaña Dispositivos cuando se habilita la integración de Microsoft Defender para endpoints:</span><span class="sxs-lookup"><span data-stu-id="e36cb-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Cuando Microsoft Defender para endpoint está habilitado, puedes ver una lista de dispositivos con alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="e36cb-110">En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico detectado tienen cuatro dispositivos y uno tiene una alerta.</span><span class="sxs-lookup"><span data-stu-id="e36cb-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="e36cb-111">Al hacer clic en el vínculo de un dispositivo, se abre su página en el Centro de seguridad de Microsoft Defender ( <https://securitycenter.windows.com> ).</span><span class="sxs-lookup"><span data-stu-id="e36cb-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="e36cb-112">**[Obtenga más información sobre el Centro de seguridad de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/use)** (también conocido como portal de Microsoft Defender para endpoints).</span><span class="sxs-lookup"><span data-stu-id="e36cb-112">**[Learn more about the Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="e36cb-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e36cb-113">Requirements</span></span>

- <span data-ttu-id="e36cb-114">Su organización debe tener Microsoft Defender para Office 365 (u Office 365 E5) y Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="e36cb-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="e36cb-115">Debe ser un administrador global o tener asignado un rol de administrador de seguridad (como administrador de seguridad) en el Centro de [seguridad & cumplimiento](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="e36cb-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="e36cb-116">(Vea [Permisos en el Centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="e36cb-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="e36cb-117">Debe tener acceso a explorer (o detecciones en tiempo [real)](threat-explorer.md) en el Centro de seguridad & cumplimiento y el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e36cb-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="e36cb-118">Para integrar Microsoft Defender para Office 365 con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="e36cb-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="e36cb-119">La integración de Microsoft Defender para Office 365 con Microsoft Defender para endpoint se configura mediante el Centro de seguridad & cumplimiento y el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e36cb-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="e36cb-120">Como administrador global o administrador de seguridad, vaya a <https://protection.office.com> e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="e36cb-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="e36cb-121">(Esto le llevará al Centro de seguridad y & de Seguridad de Office 365).</span><span class="sxs-lookup"><span data-stu-id="e36cb-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="e36cb-122">En el panel de navegación, elija **Explorador de administración de** \> **amenazas**.</span><span class="sxs-lookup"><span data-stu-id="e36cb-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![Explorador en el menú Administración de amenazas](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="e36cb-124">En la esquina superior derecha de la pantalla, elija **Defender for Endpoint Settings (MDE Settings)**.</span><span class="sxs-lookup"><span data-stu-id="e36cb-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="e36cb-125">En el cuadro de diálogo Conexión de Microsoft Defender para extremo, active **Conectarse a Microsoft Defender para Endpoint**.</span><span class="sxs-lookup"><span data-stu-id="e36cb-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Conexión de Microsoft Defender para endpoint](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="e36cb-127">Vaya al Centro de seguridad de Microsoft Defender ( <https://securitycenter.windows.com> ).</span><span class="sxs-lookup"><span data-stu-id="e36cb-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="e36cb-128">En la barra de navegación, elija **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="e36cb-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="e36cb-129">A continuación, **en General**, elija **Características avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="e36cb-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="e36cb-130">Desplácese hacia abajo hasta La conexión de Inteligencia de amenazas de **Office 365** y active la conexión.</span><span class="sxs-lookup"><span data-stu-id="e36cb-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Conexión de inteligencia de amenazas de Office 365](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="e36cb-132">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="e36cb-132">Related articles</span></span>

[<span data-ttu-id="e36cb-133">Capacidades de investigación y respuesta de amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="e36cb-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="e36cb-134">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e36cb-134">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="e36cb-135">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e36cb-135">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)