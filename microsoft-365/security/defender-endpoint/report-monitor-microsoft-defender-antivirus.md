---
title: Supervisar e informar sobre la protección antivirus de Microsoft Defender
description: Use Configuration Manager o herramientas de administración de eventos y de información de seguridad (SIEM) para consumir informes y supervisar Microsoft Defender AV con PowerShell y WMI.
keywords: siem, monitor, informe, Av. de Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f0065792f525827ccd1471087b8a707989ef61ef
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691447"
---
# <a name="report-on-microsoft-defender-antivirus"></a><span data-ttu-id="97ddf-104">Informe sobre antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="97ddf-104">Report on Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="97ddf-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="97ddf-105">**Applies to:**</span></span>

- [<span data-ttu-id="97ddf-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="97ddf-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="97ddf-107">Antivirus de Microsoft Defender está integrado en Windows 10, Windows Server 2019 y Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="97ddf-107">Microsoft Defender Antivirus is built into Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="97ddf-108">Antivirus de Microsoft Defender es de su protección de próxima generación en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="97ddf-108">Microsoft Defender Antivirus is of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="97ddf-109">La protección de última generación ayuda a proteger los dispositivos de amenazas de software como virus, malware y spyware en el correo electrónico, las aplicaciones, la nube y la web.</span><span class="sxs-lookup"><span data-stu-id="97ddf-109">Next-generation protection helps protect your devices from software threats like viruses, malware, and spyware across email, apps, the cloud, and the web.</span></span>

<span data-ttu-id="97ddf-110">Con Antivirus de Microsoft Defender, tienes varias opciones para revisar el estado de protección y las alertas.</span><span class="sxs-lookup"><span data-stu-id="97ddf-110">With Microsoft Defender Antivirus, you have several options for reviewing protection status and alerts.</span></span> <span data-ttu-id="97ddf-111">Puede usar Microsoft Endpoint Manager para supervisar [antivirus de Microsoft Defender](/configmgr/protect/deploy-use/monitor-endpoint-protection) o crear [alertas de correo electrónico.](/configmgr/protect/deploy-use/endpoint-configure-alerts)</span><span class="sxs-lookup"><span data-stu-id="97ddf-111">You can use Microsoft Endpoint Manager to [monitor Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) or [create email alerts](/configmgr/protect/deploy-use/endpoint-configure-alerts).</span></span> <span data-ttu-id="97ddf-112">O bien, puede supervisar la protección con [Microsoft Intune](/intune/introduction-intune).</span><span class="sxs-lookup"><span data-stu-id="97ddf-112">Or, you can monitor protection using [Microsoft Intune](/intune/introduction-intune).</span></span>  

<span data-ttu-id="97ddf-113">Microsoft Operations Management Suite tiene un complemento [Update Compliance que](/windows/deployment/update/update-compliance-get-started) informa sobre problemas clave de Antivirus de Microsoft Defender, incluidas las actualizaciones de protección y la configuración de protección en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="97ddf-113">Microsoft Operations Management Suite has an [Update Compliance add-in](/windows/deployment/update/update-compliance-get-started) that reports on key Microsoft Defender Antivirus issues, including protection updates and real-time protection settings.</span></span>

<span data-ttu-id="97ddf-114">Si tiene un servidor de administración de eventos (SIEM) y de información de seguridad de terceros, también puede consumir Windows Defender [eventos de cliente](/windows/win32/events/windows-events).</span><span class="sxs-lookup"><span data-stu-id="97ddf-114">If you have a third-party security information and event management (SIEM) server, you can also consume [Windows Defender client events](/windows/win32/events/windows-events).</span></span> 

<span data-ttu-id="97ddf-115">Los eventos de Windows constan de varios orígenes de eventos de seguridad, incluidos [](/windows/device-security/auditing/security-auditing-overview) los eventos del Administrador de cuentas de seguridad (SAM) (mejorados para[Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), también consulta el tema Auditoría de seguridad) [y Windows Defender eventos](troubleshoot-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="97ddf-115">Windows events comprise several security event sources, including Security Account Manager (SAM) events ([enhanced for Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), also see the [Security auditing](/windows/device-security/auditing/security-auditing-overview) topic) and  [Windows Defender events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="97ddf-116">Estos eventos se pueden agregar de forma centralizada mediante el [recopilador de eventos de Windows](/windows/win32/wec/windows-event-collector).</span><span class="sxs-lookup"><span data-stu-id="97ddf-116">These events can be centrally aggregated using the [Windows event collector](/windows/win32/wec/windows-event-collector).</span></span> <span data-ttu-id="97ddf-117">A menudo, los servidores SIEM tienen conectores para eventos de Windows, lo que te permite correlacionar todos los eventos de seguridad del servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="97ddf-117">Often, SIEM servers have connectors for Windows events, allowing you to correlate all security events in your SIEM server.</span></span> 

<span data-ttu-id="97ddf-118">También puede supervisar [eventos de malware mediante la solución de evaluación de malware en Log Analytics](/azure/log-analytics/log-analytics-malware).</span><span class="sxs-lookup"><span data-stu-id="97ddf-118">You can also [monitor malware events using the Malware Assessment solution in Log Analytics](/azure/log-analytics/log-analytics-malware).</span></span>

<span data-ttu-id="97ddf-119">Para supervisar o determinar el estado con PowerShell, WMI o Microsoft Azure, vea [la tabla (Opciones](deploy-manage-report-microsoft-defender-antivirus.md#ref2)de implementación, administración e informes).</span><span class="sxs-lookup"><span data-stu-id="97ddf-119">For monitoring or determining status with PowerShell, WMI, or Microsoft Azure, see the [(Deployment, management, and reporting options table)](deploy-manage-report-microsoft-defender-antivirus.md#ref2).</span></span>

## <a name="related-articles"></a><span data-ttu-id="97ddf-120">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="97ddf-120">Related articles</span></span>

- [<span data-ttu-id="97ddf-121">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="97ddf-121">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="97ddf-122">Antivirus de Microsoft Defender en Windows Server 2016 y 2019</span><span class="sxs-lookup"><span data-stu-id="97ddf-122">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="97ddf-123">Implementar antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="97ddf-123">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)