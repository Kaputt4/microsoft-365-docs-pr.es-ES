---
title: Solucionar problemas de rendimiento de ATP de Microsoft Defender para Mac
description: Solucionar problemas de rendimiento en ATP de Microsoft Defender para Mac.
keywords: microsoft, defender, atp, mac, performance
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dbd82bae86ac4181497ecc87bc74181f7a502e15
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070259"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="4ff9b-104">Solucionar problemas de rendimiento de Microsoft Defender para Endpoint para Mac</span><span class="sxs-lookup"><span data-stu-id="4ff9b-104">Troubleshoot performance issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4ff9b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4ff9b-105">**Applies to:**</span></span>

- [<span data-ttu-id="4ff9b-106">Microsoft Defender para endpoint para Mac</span><span class="sxs-lookup"><span data-stu-id="4ff9b-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="4ff9b-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4ff9b-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="4ff9b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ff9b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4ff9b-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="4ff9b-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4ff9b-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="4ff9b-111">En este tema se proporcionan algunos pasos generales que se pueden usar para limitar los problemas de rendimiento relacionados con Microsoft Defender para Endpoint para Mac.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="4ff9b-112">La protección en tiempo real (RTP) es una característica de Microsoft Defender para Endpoint para Mac que supervisa y protege continuamente el dispositivo contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint for Mac that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="4ff9b-113">Consiste en la supervisión de archivos y procesos y otras heurísticas.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="4ff9b-114">Según las aplicaciones que ejecutes y las características del dispositivo, es posible que experimentes un rendimiento subóptimo al ejecutar Microsoft Defender para Endpoint para Mac.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-114">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="4ff9b-115">En particular, las aplicaciones o los procesos del sistema que tienen acceso a muchos recursos en un período de tiempo corto pueden provocar problemas de rendimiento en Microsoft Defender para Endpoint para Mac.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="4ff9b-116">Se pueden usar los siguientes pasos para solucionar y mitigar estos problemas:</span><span class="sxs-lookup"><span data-stu-id="4ff9b-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="4ff9b-117">Deshabilite la protección en tiempo real con uno de los siguientes métodos y observe si el rendimiento mejora.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="4ff9b-118">Este enfoque ayuda a reducir si Microsoft Defender para Endpoint para Mac está contribuyendo a los problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-118">This approach helps narrow down whether Microsoft Defender for Endpoint for Mac is contributing to the performance issues.</span></span>

    <span data-ttu-id="4ff9b-119">Si su organización no administra el dispositivo, la protección en tiempo real se puede deshabilitar mediante una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4ff9b-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="4ff9b-120">Desde la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-120">From the user interface.</span></span> <span data-ttu-id="4ff9b-121">Abra Microsoft Defender para Endpoint para Mac y vaya a **Administrar la configuración**.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-121">Open Microsoft Defender for Endpoint for Mac and navigate to **Manage settings**.</span></span>

      ![Administrar la captura de pantalla de protección en tiempo real](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-36-rtp)

    - <span data-ttu-id="4ff9b-123">Desde el terminal.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-123">From the Terminal.</span></span> <span data-ttu-id="4ff9b-124">Por motivos de seguridad, esta operación requiere elevación.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    <span data-ttu-id="4ff9b-125">Si su organización administra el dispositivo, el administrador puede deshabilitar la protección en tiempo real con las instrucciones de Establecer preferencias para [Microsoft Defender para](mac-preferences.md)Endpoint para Mac .</span><span class="sxs-lookup"><span data-stu-id="4ff9b-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

2. <span data-ttu-id="4ff9b-126">Abra Finder y vaya a  >  **Utilidades de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-126">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="4ff9b-127">Abra **El Monitor de** actividad y analice qué aplicaciones usan los recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-127">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="4ff9b-128">Algunos ejemplos típicos son los actualizadores de software y los compiladores.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-128">Typical examples include software updaters and compilers.</span></span>

3. <span data-ttu-id="4ff9b-129">Configure Microsoft Defender para Endpoint para Mac con exclusiones para los procesos o ubicaciones de disco que contribuyen a los problemas de rendimiento y vuelva a habilitar la protección en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-129">Configure Microsoft Defender for Endpoint for Mac with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="4ff9b-130">Consulta [Configurar y validar exclusiones para Microsoft Defender para Endpoint para Mac](mac-exclusions.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4ff9b-130">See [Configure and validate exclusions for Microsoft Defender for Endpoint for Mac](mac-exclusions.md) for details.</span></span>
