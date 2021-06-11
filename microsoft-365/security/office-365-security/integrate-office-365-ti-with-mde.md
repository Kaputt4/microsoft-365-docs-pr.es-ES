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
ms.openlocfilehash: 63ae9f8c1136a973e4fccb63ecfbaee2639c3f6f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904085"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="a84fb-104">Usar Microsoft Defender para Office 365 junto con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="a84fb-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a84fb-105">[Microsoft Defender para Office 365](defender-for-office-365.md) puede configurarse para funcionar con [Microsoft Defender para endpoint](/windows/security/threat-protection).</span><span class="sxs-lookup"><span data-stu-id="a84fb-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="a84fb-106">La integración de Microsoft Defender para Office 365 con Microsoft Defender para endpoint puede ayudar a su equipo de operaciones de seguridad a supervisar y tomar medidas rápidamente si los dispositivos de los usuarios están en riesgo.</span><span class="sxs-lookup"><span data-stu-id="a84fb-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="a84fb-107">Por ejemplo, una vez habilitada la integración, el equipo de operaciones de seguridad podrá ver los dispositivos potencialmente afectados por un mensaje de correo electrónico detectado, así como cuántas alertas recientes se generaron para esos dispositivos en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="a84fb-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="a84fb-108">En la siguiente imagen se muestra el aspecto **de** la pestaña Dispositivos cuando se habilita la integración de Microsoft Defender para endpoints:</span><span class="sxs-lookup"><span data-stu-id="a84fb-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Cuando Microsoft Defender para endpoint está habilitado, puedes ver una lista de dispositivos con alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="a84fb-110">En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico detectado tienen cuatro dispositivos y uno tiene una alerta.</span><span class="sxs-lookup"><span data-stu-id="a84fb-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="a84fb-111">Al hacer clic en el vínculo de un dispositivo, se abre su [página en Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (anteriormente el Centro de seguridad de Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="a84fb-111">Clicking the link for a device opens its page in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center).</span></span>

> [!TIP]
> <span data-ttu-id="a84fb-112">El portal Microsoft 365 Defender reemplaza al Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a84fb-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="a84fb-113">Consulta [Microsoft Defender para Endpoint en Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="a84fb-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="a84fb-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a84fb-114">Requirements</span></span>

- <span data-ttu-id="a84fb-115">Su organización debe tener Microsoft Defender para Office 365 (o Office 365 E5) y Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="a84fb-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="a84fb-116">Debe ser un administrador global o tener un rol de administrador de seguridad (como administrador de seguridad) asignado en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a84fb-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="a84fb-117">(Vea [Permisos en el Centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="a84fb-117">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="a84fb-118">Debe tener acceso al [Explorador (o detecciones en tiempo real).](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="a84fb-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="a84fb-119">Para integrar Microsoft Defender para Office 365 con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="a84fb-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="a84fb-120">La integración de Microsoft Defender para Office 365 con Microsoft Defender para endpoint se configura en Defender para Endpoint y Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="a84fb-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="a84fb-121">Como administrador global o administrador de seguridad, vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="a84fb-121">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="a84fb-122">(Esto le lleva al Centro de Office 365 seguridad & cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="a84fb-122">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="a84fb-123">En el panel de navegación, elija **Explorador de administración de** \> **amenazas**.</span><span class="sxs-lookup"><span data-stu-id="a84fb-123">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![Explorador en el menú Administración de amenazas](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="a84fb-125">En la esquina superior derecha de la pantalla, elija **Defender para Endpoint Configuración (MDE Configuración).**</span><span class="sxs-lookup"><span data-stu-id="a84fb-125">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="a84fb-126">En el cuadro de diálogo Conexión de Microsoft Defender para endpoint, active **Conectar a Microsoft Defender para Endpoint**.</span><span class="sxs-lookup"><span data-stu-id="a84fb-126">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Conexión de Microsoft Defender para endpoint](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="a84fb-128">Vaya al portal Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="a84fb-128">Go to the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com).</span></span>

6. <span data-ttu-id="a84fb-129">En la barra de navegación, **elija Configuración**.</span><span class="sxs-lookup"><span data-stu-id="a84fb-129">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="a84fb-130">A continuación, **en General**, elija **Características avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="a84fb-130">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="a84fb-131">Desplácese hacia abajo **hasta Office 365 de inteligencia** de amenazas y active la conexión.</span><span class="sxs-lookup"><span data-stu-id="a84fb-131">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 de inteligencia de amenazas](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="a84fb-133">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="a84fb-133">Related articles</span></span>

[<span data-ttu-id="a84fb-134">Capacidades de investigación y respuesta de amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="a84fb-134">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="a84fb-135">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a84fb-135">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="a84fb-136">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="a84fb-136">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
