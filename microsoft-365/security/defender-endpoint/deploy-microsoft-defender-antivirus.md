---
title: Implementación y habilitación en el Antivirus de Windows Defender
description: Implemente Antivirus de Microsoft Defender protección de los puntos de conexión con Microsoft Intune, Microsoft Endpoint Configuration Manager, directiva de grupo, cmdlets de PowerShell o WMI.
keywords: implementar, habilitar, Antivirus de Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 88a5401818c3d6f2b35675830a38b266db9627e4
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274501"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a><span data-ttu-id="f1147-104">Implementación y habilitación en el Antivirus de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="f1147-104">Deploy and enable Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f1147-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f1147-105">**Applies to:**</span></span>

- [<span data-ttu-id="f1147-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f1147-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f1147-107">Según la herramienta de administración que use, es posible que deba habilitar o configurar específicamente la protección Antivirus de Microsoft Defender administración.</span><span class="sxs-lookup"><span data-stu-id="f1147-107">Depending on the management tool you are using, you may need to specifically enable or configure Microsoft Defender Antivirus protection.</span></span> 

<span data-ttu-id="f1147-108">Consulte la tabla de [Implementar,](deploy-manage-report-microsoft-defender-antivirus.md#ref2) administrar e informar sobre Antivirus de Microsoft Defender para obtener instrucciones sobre cómo habilitar la protección con Microsoft Intune, Microsoft Endpoint Configuration Manager, directiva de grupo, Active Directory, Microsoft Azure, cmdlets de PowerShell e instrucción de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="f1147-108">See the table in [Deploy, manage, and report on Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md#ref2) for instructions on how to enable protection with Microsoft Intune, Microsoft Endpoint Configuration Manager, Group Policy, Active Directory, Microsoft Azure, PowerShell cmdlets, and Windows Management Instruction (WMI).</span></span>

<span data-ttu-id="f1147-109">Algunos escenarios requieren más instrucciones sobre cómo implementar o configurar correctamente la protección Antivirus de Microsoft Defender, como Infraestructura de escritorio virtual (VDI).</span><span class="sxs-lookup"><span data-stu-id="f1147-109">Some scenarios require more guidance on how to successfully deploy or configure Microsoft Defender Antivirus protection, such as Virtual Desktop Infrastructure (VDI) environments.</span></span>

<span data-ttu-id="f1147-110">El artículo restante de esta sección proporciona consejos completos y procedimientos recomendados para configurar Antivirus de Microsoft Defender en máquinas virtuales (VM) en un entorno de VDI o servicios de escritorio remoto [(RDS).](deployment-vdi-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f1147-110">The remaining article in this section provides end-to-end advice and best practices for [setting up Microsoft Defender Antivirus on virtual machines (VMs) in a VDI or Remote Desktop Services (RDS) environment](deployment-vdi-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="f1147-111">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="f1147-111">Related articles</span></span>

- [<span data-ttu-id="f1147-112">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="f1147-112">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="f1147-113">Implementar, administrar actualizaciones e informar sobre Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f1147-113">Deploy, manage updates, and report on Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f1147-114">Guía de implementación del Antivirus de Microsoft Defender en un entorno de infraestructura de escritorio virtual</span><span class="sxs-lookup"><span data-stu-id="f1147-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)