---
title: Configurar exclusiones para exámenes antivirus de Microsoft Defender
description: Puede excluir los archivos (incluidos los archivos modificados por procesos especificados) y las carpetas que microsoft Defender AV examina. Valide las exclusiones con PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 47db9b4451a885c92ca4fda0f87f0150415d3338
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691507"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="df3c5-104">Configurar y validar exclusiones para exámenes de Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="df3c5-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="df3c5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="df3c5-105">**Applies to:**</span></span>

- [<span data-ttu-id="df3c5-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="df3c5-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="df3c5-107">Puede excluir determinados archivos, carpetas, procesos y archivos abiertos por procesos de los exámenes del Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="df3c5-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="df3c5-108">Estas exclusiones se aplican [a los exámenes programados,](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [](run-scan-microsoft-defender-antivirus.md)a los exámenes a petición y a la protección y supervisión siempre activas en tiempo [real.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="df3c5-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="df3c5-109">Las exclusiones de los archivos abiertos por proceso solo se aplican a la protección en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="df3c5-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="df3c5-110">Configurar y validar exclusiones</span><span class="sxs-lookup"><span data-stu-id="df3c5-110">Configure and validate exclusions</span></span>

<span data-ttu-id="df3c5-111">Para configurar y validar exclusiones, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="df3c5-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="df3c5-112">[Configurar y validar exclusiones según el nombre de archivo, la extensión y la ubicación de la carpeta](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="df3c5-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="df3c5-113">Esto le permite excluir archivos de exámenes de Antivirus de Microsoft Defender en función de su extensión de archivo, nombre de archivo o ubicación.</span><span class="sxs-lookup"><span data-stu-id="df3c5-113">This enables you to exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="df3c5-114">[Configurar y validar exclusiones para los archivos abiertos por procesos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="df3c5-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="df3c5-115">Esto permite excluir archivos de los exámenes abiertos por un proceso específico.</span><span class="sxs-lookup"><span data-stu-id="df3c5-115">This enables you to exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="df3c5-116">Recomendaciones para definir exclusiones</span><span class="sxs-lookup"><span data-stu-id="df3c5-116">Recommendations for defining exclusions</span></span>

<span data-ttu-id="df3c5-117">La definición de exclusiones reduce la protección que ofrece Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="df3c5-117">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="df3c5-118">Siempre debe evaluar los riesgos asociados con la implementación de exclusiones y solo debe excluir los archivos que confía en que no son malintencionados.</span><span class="sxs-lookup"><span data-stu-id="df3c5-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="df3c5-119">A continuación se muestra una lista de recomendaciones que debe tener en cuenta al definir exclusiones:</span><span class="sxs-lookup"><span data-stu-id="df3c5-119">The following is a list of recommendations that you should keep in mind when defining exclusions:</span></span>  

- <span data-ttu-id="df3c5-120">Las exclusiones son técnicamente un vacío de protección: considere siempre mitigaciones adicionales al definir exclusiones.</span><span class="sxs-lookup"><span data-stu-id="df3c5-120">Exclusions are technically a protection gap—always consider additional mitigations when defining exclusions.</span></span> <span data-ttu-id="df3c5-121">Las mitigaciones adicionales podrían ser tan sencillas como asegurarse de que la ubicación excluida tenga las listas de control de acceso (ACL) adecuadas, la directiva de auditoría, se procesa mediante un software actualizado, etc.</span><span class="sxs-lookup"><span data-stu-id="df3c5-121">Additional mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="df3c5-122">Revise las exclusiones periódicamente.</span><span class="sxs-lookup"><span data-stu-id="df3c5-122">Review the exclusions periodically.</span></span> <span data-ttu-id="df3c5-123">Vuelva a comprobar y volver a aplicar las mitigaciones como parte del proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="df3c5-123">Re-check and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="df3c5-124">Lo ideal es evitar definir exclusiones proactivas.</span><span class="sxs-lookup"><span data-stu-id="df3c5-124">Ideally, avoid defining proactive exclusions.</span></span> <span data-ttu-id="df3c5-125">Por ejemplo, no excluyas algo solo porque crees que podría ser un problema en el futuro.</span><span class="sxs-lookup"><span data-stu-id="df3c5-125">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="df3c5-126">Use exclusiones solo para problemas específicos, principalmente en torno al rendimiento o, en ocasiones, a la compatibilidad de aplicaciones que las exclusiones podrían mitigar.</span><span class="sxs-lookup"><span data-stu-id="df3c5-126">Use exclusions only for specific issues—mostly around performance, or sometimes around application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="df3c5-127">Audite los cambios de la lista de exclusión.</span><span class="sxs-lookup"><span data-stu-id="df3c5-127">Audit the exclusion list changes.</span></span> <span data-ttu-id="df3c5-128">El administrador de seguridad debe conservar suficiente contexto en torno a por qué se agregó una exclusión determinada.</span><span class="sxs-lookup"><span data-stu-id="df3c5-128">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="df3c5-129">Debería poder proporcionar una respuesta con un razonamiento específico sobre por qué se excluyó una determinada ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="df3c5-129">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="df3c5-130">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="df3c5-130">Related articles</span></span>

- [<span data-ttu-id="df3c5-131">Exclusiones de Antivirus de Microsoft Defender en Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="df3c5-131">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="df3c5-132">Errores comunes que se deben evitar al definir exclusiones</span><span class="sxs-lookup"><span data-stu-id="df3c5-132">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)