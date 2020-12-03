---
title: Usar Microsoft defender para Office 365 junto con Microsoft defender para el punto de conexión
f1.keywords:
- NOCSH
keywords: integración, Microsoft defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Use Microsoft defender para Office 365 junto con Microsoft defender para el punto de conexión para obtener información más detallada sobre las amenazas contra sus dispositivos y contenido de correo electrónico.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8a598dce3a8049d97d43b742477ca8f7a2bfeadb
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561224"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="e0eb8-104">Usar Microsoft defender para Office 365 junto con Microsoft defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e0eb8-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e0eb8-105">[Microsoft defender para Office 365](office-365-atp.md) se puede configurar para que funcione con [Microsoft defender para el punto de conexión](https://docs.microsoft.com/windows/security/threat-protection).</span><span class="sxs-lookup"><span data-stu-id="e0eb8-105">[Microsoft Defender for Office 365](office-365-atp.md) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="e0eb8-106">La integración de Microsoft defender para Office 365 con Microsoft defender para el punto de conexión puede ayudar a su equipo de operaciones de seguridad a supervisar y emprender acciones rápidamente si los dispositivos de los usuarios están expuestos.</span><span class="sxs-lookup"><span data-stu-id="e0eb8-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="e0eb8-107">Por ejemplo, una vez habilitada la integración, el equipo de operaciones de seguridad podrá ver los dispositivos potencialmente afectados por un mensaje de correo electrónico detectado, así como el número de alertas recientes que se generaron para esos dispositivos en Microsoft defender para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e0eb8-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="e0eb8-108">En la siguiente imagen se muestra el aspecto de la ficha **dispositivos** que tiene habilitada la integración de Microsoft defender para extremo:</span><span class="sxs-lookup"><span data-stu-id="e0eb8-108">The following image depicts what the **Devices** tab looks like have Microsoft Defender for Endpoint integration enabled:</span></span>
  
![Cuando Microsoft defender for Endpoint está habilitado, puede ver una lista de dispositivos con alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="e0eb8-110">En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico detectado tienen cuatro dispositivos y uno de ellos tiene una alerta.</span><span class="sxs-lookup"><span data-stu-id="e0eb8-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="e0eb8-111">Al hacer clic en el vínculo de un dispositivo, se abre su página en el centro de seguridad de Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="e0eb8-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="e0eb8-112">**[Obtenga más información sobre el centro de seguridad de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (también conocido como Microsoft defender for Endpoint portal).</span><span class="sxs-lookup"><span data-stu-id="e0eb8-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="e0eb8-113">Requirements</span><span class="sxs-lookup"><span data-stu-id="e0eb8-113">Requirements</span></span>

- <span data-ttu-id="e0eb8-114">Su organización debe tener Microsoft defender para Office 365 (o Office 365 E5) y Microsoft defender para extremo.</span><span class="sxs-lookup"><span data-stu-id="e0eb8-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>
    
- <span data-ttu-id="e0eb8-115">Debe ser administrador global o tener un rol de administrador de seguridad (como administrador de seguridad) asignado en el [centro de seguridad & cumplimiento](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="e0eb8-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="e0eb8-116">(Consulte [permisos en el centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="e0eb8-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="e0eb8-117">Debe tener acceso a [exploradores (o detecciones en tiempo real)](threat-explorer.md) en el centro de seguridad & cumplimiento y el centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="e0eb8-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="e0eb8-118">Para integrar Microsoft defender para Office 365 con Microsoft defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e0eb8-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="e0eb8-119">La integración de Microsoft defender para Office 365 con Microsoft defender para el punto de conexión se configura mediante el centro de seguridad & cumplimiento y el centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="e0eb8-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="e0eb8-120">Como administrador global o administrador de seguridad, vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="e0eb8-120">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="e0eb8-121">(Esto le llevará al centro de cumplimiento de & de seguridad de Office 365).</span><span class="sxs-lookup"><span data-stu-id="e0eb8-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="e0eb8-122">En el panel de navegación, elija **Threat Management**  >  **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="e0eb8-122">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="e0eb8-123">![Explorador en el menú de administración de amenazas](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="e0eb8-123">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="e0eb8-124">En la esquina superior derecha de la pantalla, elija **defender para configuración del extremo**.</span><span class="sxs-lookup"><span data-stu-id="e0eb8-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings**.</span></span>
    
4. <span data-ttu-id="e0eb8-125">En el cuadro de diálogo Microsoft defender para conexión de extremo, Active **conectar con Microsoft defender para el extremo**.</span><span class="sxs-lookup"><span data-stu-id="e0eb8-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span><br><span data-ttu-id="e0eb8-126">![Microsoft defender para conexión de extremo](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="e0eb8-126">![Microsoft Defender for Endpoint connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="e0eb8-127">Vaya al centro de seguridad de Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="e0eb8-127">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="e0eb8-128">En la barra de navegación, elija **configuración**.</span><span class="sxs-lookup"><span data-stu-id="e0eb8-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="e0eb8-129">A continuación, en **General**, elija **características avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="e0eb8-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="e0eb8-130">Desplácese hacia abajo hasta **conexión de inteligencia de amenazas de 365 de Office** y active la conexión.</span><span class="sxs-lookup"><span data-stu-id="e0eb8-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="e0eb8-131">![Conexión de inteligencia de amenazas de Office 365](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="e0eb8-131">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="e0eb8-132">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="e0eb8-132">Related articles</span></span>

[<span data-ttu-id="e0eb8-133">Capacidades de investigación y respuesta de amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="e0eb8-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="e0eb8-134">Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e0eb8-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
  
[<span data-ttu-id="e0eb8-135">Microsoft defender para extremo</span><span class="sxs-lookup"><span data-stu-id="e0eb8-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
