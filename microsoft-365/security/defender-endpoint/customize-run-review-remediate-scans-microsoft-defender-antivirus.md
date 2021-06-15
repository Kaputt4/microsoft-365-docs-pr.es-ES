---
title: Ejecute y personalice exámenes programados y a petición.
description: Personalizar e iniciar exámenes Antivirus de Microsoft Defender en puntos de conexión en toda la red
keywords: análisis, programación, personalización, exclusiones, excluir archivos, corrección, resultados del examen, cuarentena, eliminación de amenazas, examen rápido, examen completo, Antivirus de Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: bce3fe1b6490803cb571a1a8a2387c19cc589114
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926252"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a><span data-ttu-id="9b4bc-104">Personalizar, iniciar y revisar los resultados de Antivirus de Microsoft Defender análisis y corrección</span><span class="sxs-lookup"><span data-stu-id="9b4bc-104">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9b4bc-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9b4bc-105">**Applies to:**</span></span>

- [<span data-ttu-id="9b4bc-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="9b4bc-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9b4bc-107">Puede usar la directiva de grupo, PowerShell y Windows Management Instrumentation (WMI) para configurar Antivirus de Microsoft Defender exámenes.</span><span class="sxs-lookup"><span data-stu-id="9b4bc-107">You can use Group Policy, PowerShell, and Windows Management Instrumentation (WMI) to configure Microsoft Defender Antivirus scans.</span></span> 

## <a name="in-this-section"></a><span data-ttu-id="9b4bc-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9b4bc-108">In this section</span></span>

<span data-ttu-id="9b4bc-109">Tema</span><span class="sxs-lookup"><span data-stu-id="9b4bc-109">Topic</span></span> | <span data-ttu-id="9b4bc-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b4bc-110">Description</span></span>
---|---
[<span data-ttu-id="9b4bc-111">Configurar y validar exclusiones de archivos, carpetas y archivos abiertos por proceso en Antivirus de Microsoft Defender exámenes</span><span class="sxs-lookup"><span data-stu-id="9b4bc-111">Configure and validate file, folder, and process-opened file exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md) | <span data-ttu-id="9b4bc-112">Puede excluir archivos (incluidos los archivos modificados por procesos especificados) y carpetas de exámenes a petición, exámenes programados y supervisión y análisis de protección siempre en tiempo real</span><span class="sxs-lookup"><span data-stu-id="9b4bc-112">You can exclude files (including files modified by specified processes) and folders from on-demand scans, scheduled scans, and always-on real-time protection monitoring and scanning</span></span>
[<span data-ttu-id="9b4bc-113">Configurar opciones de análisis del Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9b4bc-113">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md) | <span data-ttu-id="9b4bc-114">Puede configurar Antivirus de Microsoft Defender para incluir determinados tipos de archivos de almacenamiento de correo electrónico, puntos de copia de seguridad o reanúrlo, y archivos archivados (como .zip archivos) en los exámenes.</span><span class="sxs-lookup"><span data-stu-id="9b4bc-114">You can configure Microsoft Defender Antivirus to include certain types of email storage files, back-up or reparse points, and archived files (such as .zip files) in scans.</span></span> <span data-ttu-id="9b4bc-115">También puede habilitar el examen de archivos de red</span><span class="sxs-lookup"><span data-stu-id="9b4bc-115">You can also enable network file scanning</span></span>
[<span data-ttu-id="9b4bc-116">Configurar la corrección para exámenes</span><span class="sxs-lookup"><span data-stu-id="9b4bc-116">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md) | <span data-ttu-id="9b4bc-117">Configurar qué Antivirus de Microsoft Defender debe hacer cuando detecta una amenaza y cuánto tiempo deben conservarse los archivos en cuarentena en la carpeta de cuarentena</span><span class="sxs-lookup"><span data-stu-id="9b4bc-117">Configure what Microsoft Defender Antivirus should do when it detects a threat, and how long quarantined files should be retained in the quarantine folder</span></span>
[<span data-ttu-id="9b4bc-118">Configurar exámenes programados</span><span class="sxs-lookup"><span data-stu-id="9b4bc-118">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | <span data-ttu-id="9b4bc-119">Configurar exámenes periódicos (programados), incluso cuándo deben ejecutarse y si se ejecutan como exámenes rápidos o completos</span><span class="sxs-lookup"><span data-stu-id="9b4bc-119">Set up recurring (scheduled) scans, including when they should run and whether they run as full or quick scans</span></span>
[<span data-ttu-id="9b4bc-120">Configurar y ejecutar exámenes</span><span class="sxs-lookup"><span data-stu-id="9b4bc-120">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md) | <span data-ttu-id="9b4bc-121">Ejecutar y configurar exámenes a petición con PowerShell, Windows Management Instrumentation o individualmente en puntos de conexión con la Seguridad de Windows aplicación</span><span class="sxs-lookup"><span data-stu-id="9b4bc-121">Run and configure on-demand scans using PowerShell, Windows Management Instrumentation, or individually on endpoints with the Windows Security app</span></span>
[<span data-ttu-id="9b4bc-122">Revisar los resultados del examen</span><span class="sxs-lookup"><span data-stu-id="9b4bc-122">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md) | <span data-ttu-id="9b4bc-123">Revisar los resultados de los exámenes mediante Microsoft Endpoint Configuration Manager, Microsoft Intune o la aplicación Seguridad de Windows examen</span><span class="sxs-lookup"><span data-stu-id="9b4bc-123">Review the results of scans using  Microsoft Endpoint Configuration Manager, Microsoft Intune, or the Windows Security app</span></span>