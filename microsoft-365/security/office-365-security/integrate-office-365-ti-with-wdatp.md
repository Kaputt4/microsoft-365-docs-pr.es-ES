---
title: Integrar Office 365 ATP con Protección contra amenazas avanzada de Microsoft Defender
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integre Office 365 Advanced Threat Protection con la protección contra amenazas avanzada de Microsoft defender para ver información más detallada sobre la administración de amenazas.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0906b8b44922084a65999dd9ab10a09c827605c2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201976"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="4f636-103">Integración de la protección contra amenazas avanzada de Office 365 con la protección contra amenazas avanzada de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="4f636-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4f636-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) se puede configurar para que funcione con la [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection) (ATP de Microsoft defender).</span><span class="sxs-lookup"><span data-stu-id="4f636-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) can be configured to work with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span></span>

<span data-ttu-id="4f636-105">La integración de Office 365 ATP con Microsoft defender ATP puede ayudar a su equipo de operaciones de seguridad a supervisar y emprender acciones rápidamente si los dispositivos de los usuarios están expuestos.</span><span class="sxs-lookup"><span data-stu-id="4f636-105">Integrating Office 365 ATP with Microsoft Defender ATP can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="4f636-106">Por ejemplo, una vez que la integración está habilitada, el equipo de operaciones de seguridad podrá ver los dispositivos que pueden verse afectados por un mensaje de correo electrónico detectado, así como el número de alertas recientes que dichos dispositivos tienen en ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="4f636-106">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts those devices have in Microsoft Defender ATP.</span></span> 

<span data-ttu-id="4f636-107">En la siguiente imagen se muestra el aspecto de la ficha **dispositivos** que tiene habilitada la integración de Microsoft defender ATP:</span><span class="sxs-lookup"><span data-stu-id="4f636-107">The following image depicts what the **Devices** tab looks like have Microsoft Defender ATP integration enabled:</span></span>
  
![Cuando ATP de Microsoft defender está habilitada, puede ver una lista de dispositivos con alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="4f636-109">En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico detectado tienen cuatro dispositivos y uno de ellos tiene una alerta.</span><span class="sxs-lookup"><span data-stu-id="4f636-109">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="4f636-110">Al hacer clic en el vínculo de un dispositivo, se abre su página en el centro de seguridad de Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="4f636-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="4f636-111">**[Obtenga más información sobre el centro de seguridad de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (también conocido como el portal ATP de Microsoft defender).</span><span class="sxs-lookup"><span data-stu-id="4f636-111">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender ATP portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="4f636-112">Requirements</span><span class="sxs-lookup"><span data-stu-id="4f636-112">Requirements</span></span>

- <span data-ttu-id="4f636-113">Su organización debe tener Office 365 ATP plan 2 (o Office 365 E5) y ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="4f636-113">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="4f636-114">Debe ser administrador global o tener un rol de administrador de seguridad (como administrador de seguridad) asignado en el [centro de seguridad y &amp; cumplimiento](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="4f636-114">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="4f636-115">(Consulte [permisos en el centro de seguridad y &amp; cumplimiento](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="4f636-115">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="4f636-116">Debe tener acceso a [exploradores (o detecciones en tiempo real)](threat-explorer.md) en el centro de seguridad & cumplimiento y el centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="4f636-116">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="4f636-117">Para integrar Office 365 ATP con Microsoft defender ATP</span><span class="sxs-lookup"><span data-stu-id="4f636-117">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="4f636-118">Integración de Office 365 ATP con Microsoft defender ATP se configura mediante el centro de seguridad & cumplimiento y el centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="4f636-118">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="4f636-119">Como administrador global o administrador de seguridad, vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="4f636-119">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="4f636-120">(Esto le llevará al centro de cumplimiento de & de seguridad de Office 365).</span><span class="sxs-lookup"><span data-stu-id="4f636-120">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="4f636-121">En el panel de navegación, elija **Threat Management**  >  **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="4f636-121">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="4f636-122">![Explorador en el menú de administración de amenazas](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="4f636-122">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="4f636-123">En la esquina superior derecha de la pantalla, elija **WDATP de configuración**.</span><span class="sxs-lookup"><span data-stu-id="4f636-123">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="4f636-124">En el cuadro de diálogo conexión ATP de Microsoft defender, Active **conectarse a ATP de Windows**.</span><span class="sxs-lookup"><span data-stu-id="4f636-124">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="4f636-125">![Conexión ATP de Microsoft defender](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="4f636-125">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="4f636-126">Vaya al centro de seguridad de Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="4f636-126">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="4f636-127">En la barra de navegación, elija **configuración**.</span><span class="sxs-lookup"><span data-stu-id="4f636-127">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="4f636-128">A continuación, en **General**, elija **características avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="4f636-128">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="4f636-129">Desplácese hacia abajo hasta **conexión de inteligencia de amenazas de 365 de Office**y active la conexión.</span><span class="sxs-lookup"><span data-stu-id="4f636-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="4f636-130">![Conexión de inteligencia de amenazas de Office 365](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="4f636-130">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="4f636-131">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="4f636-131">Related articles</span></span>

[<span data-ttu-id="4f636-132">Capacidades de investigación y respuesta de amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="4f636-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="4f636-133">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="4f636-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="4f636-134">ATP de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4f636-134">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
