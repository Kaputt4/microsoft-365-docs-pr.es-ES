---
title: Configurar las funciones del Antivirus de Microsoft Defender
description: Puede configurar las Antivirus de Microsoft Defender con Intune, Microsoft Endpoint Configuration Manager, directiva de grupo y PowerShell.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defender, configurar, configuración, Administrador de configuración, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, administración de dispositivos móviles, GP, directiva de grupo, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 7fa5959ede9f0c71c75cefafc0fcb0d4376a1a4f
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925400"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="606a3-104">Configurar las funciones del Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="606a3-104">Configure Microsoft Defender Antivirus features</span></span>


<span data-ttu-id="606a3-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="606a3-105">**Applies to:**</span></span>

- [<span data-ttu-id="606a3-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="606a3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="606a3-107">Puede configurar Antivirus de Microsoft Defender con una serie de herramientas, como:</span><span class="sxs-lookup"><span data-stu-id="606a3-107">You can configure Microsoft Defender Antivirus with a number of tools, such as:</span></span>

- <span data-ttu-id="606a3-108">Microsoft Endpoint Manager (que incluye Microsoft Intune y Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="606a3-108">Microsoft Endpoint Manager (which includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
- <span data-ttu-id="606a3-109">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="606a3-109">Group Policy</span></span>
- <span data-ttu-id="606a3-110">Cmdlets de PowerShell</span><span class="sxs-lookup"><span data-stu-id="606a3-110">PowerShell cmdlets</span></span>
- <span data-ttu-id="606a3-111">Instrumental de administración de Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="606a3-111">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="606a3-112">Se pueden configurar las siguientes categorías generales de características:</span><span class="sxs-lookup"><span data-stu-id="606a3-112">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="606a3-113">Protección entregada en la nube.</span><span class="sxs-lookup"><span data-stu-id="606a3-113">Cloud-delivered protection.</span></span> <span data-ttu-id="606a3-114">Consulte [Protección entregada en la nube y Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="606a3-114">See [Cloud-delivered protection and Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span></span>
 
- <span data-ttu-id="606a3-115">Protección siempre activa en tiempo real, incluida la protección basada en el comportamiento, la heurística y la de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="606a3-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection.</span></span> <span data-ttu-id="606a3-116">Consulte [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="606a3-116">See [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).</span></span>

- <span data-ttu-id="606a3-117">Cómo interactúan los usuarios finales con el cliente en puntos de conexión individuales.</span><span class="sxs-lookup"><span data-stu-id="606a3-117">How end users interact with the client on individual endpoints.</span></span> <span data-ttu-id="606a3-118">Vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="606a3-118">See the following resources:</span></span>
   
   - [<span data-ttu-id="606a3-119">Impedir que los usuarios vean o interactúen con la interfaz Antivirus de Microsoft Defender usuario</span><span class="sxs-lookup"><span data-stu-id="606a3-119">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md)

   - [<span data-ttu-id="606a3-120">Impedir o permitir que los usuarios modifiquen localmente Antivirus de Microsoft Defender configuración de directiva</span><span class="sxs-lookup"><span data-stu-id="606a3-120">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) 

> [!TIP]
> <span data-ttu-id="606a3-121">Revisar [temas de referencia para herramientas de administración y configuración](configuration-management-reference-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="606a3-121">Review [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md).</span></span>
