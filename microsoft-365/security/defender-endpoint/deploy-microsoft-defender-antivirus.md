---
title: Implementar y habilitar Antivirus de Microsoft Defender
description: Implemente Antivirus de Microsoft Defender para proteger los puntos de conexión con Microsoft Intune, Microsoft Endpoint Configuration Manager, directiva de grupo, cmdlets de PowerShell o WMI.
keywords: implementar, habilitar, Antivirus de Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 146447f4036d800832c75c7a59978e9571253a17
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764824"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a><span data-ttu-id="d830c-104">Implementar y habilitar Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d830c-104">Deploy and enable Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d830c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d830c-105">**Applies to:**</span></span>

- [<span data-ttu-id="d830c-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d830c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d830c-107">Según la herramienta de administración que use, es posible que deba habilitar o configurar específicamente la protección antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="d830c-107">Depending on the management tool you are using, you may need to specifically enable or configure Microsoft Defender Antivirus protection.</span></span> 

<span data-ttu-id="d830c-108">Consulta la tabla de [Implementar,](deploy-manage-report-microsoft-defender-antivirus.md#ref2) administrar e informar sobre Antivirus de Microsoft Defender para obtener instrucciones sobre cómo habilitar la protección con Microsoft Intune, Microsoft Endpoint Configuration Manager, Directiva de grupo, Active Directory, Microsoft Azure, cmdlets de PowerShell e Instrucciones de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="d830c-108">See the table in [Deploy, manage, and report on Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md#ref2) for instructions on how to enable protection with Microsoft Intune, Microsoft Endpoint Configuration Manager, Group Policy, Active Directory, Microsoft Azure, PowerShell cmdlets, and Windows Management Instruction (WMI).</span></span>

<span data-ttu-id="d830c-109">Algunos escenarios requieren más instrucciones sobre cómo implementar o configurar correctamente la protección antivirus de Microsoft Defender, como entornos de infraestructura de escritorio virtual (VDI).</span><span class="sxs-lookup"><span data-stu-id="d830c-109">Some scenarios require more guidance on how to successfully deploy or configure Microsoft Defender Antivirus protection, such as Virtual Desktop Infrastructure (VDI) environments.</span></span>

<span data-ttu-id="d830c-110">El artículo restante de esta sección proporciona consejos completos y procedimientos recomendados para configurar Microsoft Defender Antivirus en máquinas virtuales (VM) en un entorno de VDI o servicios de escritorio remoto [(RDS).](deployment-vdi-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d830c-110">The remaining article in this section provides end-to-end advice and best practices for [setting up Microsoft Defender Antivirus on virtual machines (VMs) in a VDI or Remote Desktop Services (RDS) environment](deployment-vdi-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="d830c-111">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="d830c-111">Related articles</span></span>

- [<span data-ttu-id="d830c-112">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="d830c-112">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="d830c-113">Implementar, administrar actualizaciones e informar sobre antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d830c-113">Deploy, manage updates, and report on Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d830c-114">Guía de implementación para Antivirus de Microsoft Defender en un entorno de infraestructura de escritorio virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="d830c-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)