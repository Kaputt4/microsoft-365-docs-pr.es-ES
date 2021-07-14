---
title: Administrar Windows Defender en su empresa
description: Obtenga información sobre cómo usar la directiva de grupo, Configuration Manager, PowerShell, WMI, Intune y la línea de comandos para administrar Microsoft Defender AV
keywords: directiva de grupo, gpo, administrador de configuración, sccm, scep, powershell, wmi, intune, defender, antivirus, antimalware, seguridad, protección
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/13/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f9ecade23964db88076347b3a89085b25c1b1538
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415568"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a><span data-ttu-id="2dc81-104">Administrar Antivirus de Microsoft Defender en su empresa</span><span class="sxs-lookup"><span data-stu-id="2dc81-104">Manage Microsoft Defender Antivirus in your business</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2dc81-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2dc81-105">**Applies to:**</span></span>

- [<span data-ttu-id="2dc81-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2dc81-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="2dc81-107">Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2dc81-107">Microsoft Defender Antivirus</span></span>](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows)

<span data-ttu-id="2dc81-108">Puede administrar y configurar Antivirus de Microsoft Defender con las siguientes herramientas:</span><span class="sxs-lookup"><span data-stu-id="2dc81-108">You can manage and configure Microsoft Defender Antivirus with the following tools:</span></span>

- <span data-ttu-id="2dc81-109">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (ahora parte de Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="2dc81-109">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (now part of Microsoft Endpoint Manager)</span></span>
- <span data-ttu-id="2dc81-110">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (ahora parte de Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="2dc81-110">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (now part of Microsoft Endpoint Manager)</span></span>
- [<span data-ttu-id="2dc81-111">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="2dc81-111">Group Policy</span></span>](./use-group-policy-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2dc81-112">Cmdlets de PowerShell</span><span class="sxs-lookup"><span data-stu-id="2dc81-112">PowerShell cmdlets</span></span>](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2dc81-113">Instrumental de administración de Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="2dc81-113">Windows Management Instrumentation (WMI)</span></span>](./use-wmi-microsoft-defender-antivirus.md)
- <span data-ttu-id="2dc81-114">Utilidad [de línea de comandos de Microsoft Malware Protection](./command-line-arguments-microsoft-defender-antivirus.md) (denominada utilidad *mpcmdrun.exe* protección contra malware</span><span class="sxs-lookup"><span data-stu-id="2dc81-114">The [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (referred to as the *mpcmdrun.exe* utility</span></span>

<span data-ttu-id="2dc81-115">Los artículos siguientes proporcionan más información, vínculos y recursos para usar estas herramientas para administrar y configurar Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2dc81-115">The following articles provide further information, links, and resources for using these tools to manage and configure Microsoft Defender Antivirus.</span></span>

| <span data-ttu-id="2dc81-116">Artículo</span><span class="sxs-lookup"><span data-stu-id="2dc81-116">Article</span></span> | <span data-ttu-id="2dc81-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="2dc81-117">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="2dc81-118">Administrar Antivirus de Microsoft Defender con Microsoft Intune y Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2dc81-118">Manage Microsoft Defender Antivirus with Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>](use-intune-config-manager-microsoft-defender-antivirus.md)|<span data-ttu-id="2dc81-119">Información sobre cómo usar Intune y Configuration Manager para implementar, administrar, informar y configurar Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2dc81-119">Information about using Intune and Configuration Manager to deploy, manage, report, and configure Microsoft Defender Antivirus</span></span> |
|[<span data-ttu-id="2dc81-120">Administrar Antivirus de Microsoft Defender con la configuración de directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="2dc81-120">Manage Microsoft Defender Antivirus with Group Policy settings</span></span>](use-group-policy-microsoft-defender-antivirus.md)|<span data-ttu-id="2dc81-121">Lista de todas las opciones de configuración de directiva de grupo ubicadas en plantillas ADMX</span><span class="sxs-lookup"><span data-stu-id="2dc81-121">List of all Group Policy settings located in ADMX templates</span></span> |
|[<span data-ttu-id="2dc81-122">Administrar Antivirus de Microsoft Defender con cmdlets de PowerShell</span><span class="sxs-lookup"><span data-stu-id="2dc81-122">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)|<span data-ttu-id="2dc81-123">Instrucciones para usar cmdlets de PowerShell para administrar Antivirus de Microsoft Defender, además de vínculos a documentación para todos los cmdlets y parámetros permitidos</span><span class="sxs-lookup"><span data-stu-id="2dc81-123">Instructions for using PowerShell cmdlets to manage Microsoft Defender Antivirus, plus links to documentation for all cmdlets and allowed parameters</span></span> |
|[<span data-ttu-id="2dc81-124">Administrar Antivirus de Microsoft Defender con Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="2dc81-124">Manage Microsoft Defender Antivirus with Windows Management Instrumentation (WMI)</span></span>](use-wmi-microsoft-defender-antivirus.md)| <span data-ttu-id="2dc81-125">Instrucciones para usar WMI para administrar Antivirus de Microsoft Defender, además de vínculos a la documentación de las API WMIv2 (incluidas todas las clases, métodos y propiedades)</span><span class="sxs-lookup"><span data-stu-id="2dc81-125">Instructions for using WMI to manage Microsoft Defender Antivirus, plus links to documentation for the WMIv2 APIs (including all classes, methods, and properties)</span></span> |
|[<span data-ttu-id="2dc81-126">Administrar Antivirus de Microsoft Defender con la MpCmdRun.exe de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="2dc81-126">Manage Microsoft Defender Antivirus with the MpCmdRun.exe command-line tool</span></span>](command-line-arguments-microsoft-defender-antivirus.md)| <span data-ttu-id="2dc81-127">Instrucciones sobre cómo usar la herramienta de línea de comandos dedicada para administrar y usar Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2dc81-127">Instructions on using the dedicated command-line tool to manage and use Microsoft Defender Antivirus</span></span> |
