---
title: Configurar El antivirus de Microsoft Defender con WMI
description: Obtenga información sobre cómo configurar y administrar Antivirus de Microsoft Defender mediante scripts WMI para recuperar, modificar y actualizar la configuración en Microsoft Defender para endpoint.
keywords: wmi, scripts, instrumental de administración de windows, configuración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 25518383131e4f7ecb7451965ef7a42b1c6eee4b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764068"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="41e7a-104">Usar Instrumental de administración de Windows (WMI) para configurar y administrar Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="41e7a-104">Use Windows Management Instrumentation (WMI) to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="41e7a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="41e7a-105">**Applies to:**</span></span>

- [<span data-ttu-id="41e7a-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="41e7a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="41e7a-107">Instrumental de administración de Windows (WMI) es una interfaz de scripting que permite recuperar, modificar y actualizar la configuración.</span><span class="sxs-lookup"><span data-stu-id="41e7a-107">Windows Management Instrumentation (WMI) is a scripting interface that allows you to retrieve, modify, and update settings.</span></span>

<span data-ttu-id="41e7a-108">Obtenga más información sobre WMI en la biblioteca de administración del sistema de [Microsoft Developer Network.](/windows/win32/wmisdk/wmi-start-page)</span><span class="sxs-lookup"><span data-stu-id="41e7a-108">Read more about WMI at the [Microsoft Developer Network System Administration library](/windows/win32/wmisdk/wmi-start-page).</span></span>

<span data-ttu-id="41e7a-109">Antivirus de Microsoft Defender tiene una serie de clases WMI específicas que se pueden usar para realizar la mayoría de las mismas funciones que la directiva de grupo y otras herramientas de administración.</span><span class="sxs-lookup"><span data-stu-id="41e7a-109">Microsoft Defender Antivirus has a number of specific WMI classes that can be used to perform most of the same functions as Group Policy and other management tools.</span></span> <span data-ttu-id="41e7a-110">Muchas de las clases son análogas a los [cmdlets de PowerShell de Defender.](use-powershell-cmdlets-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="41e7a-110">Many of the classes are analogous to [Defender PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="41e7a-111">La biblioteca de Windows Defender de referencia del proveedor [WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) de MSDN muestra las clases WMI disponibles para Antivirus de Microsoft Defender e incluye scripts de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="41e7a-111">The [MSDN Windows Defender WMIv2 Provider reference library](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) lists the available WMI classes for Microsoft Defender Antivirus, and includes example scripts.</span></span>

<span data-ttu-id="41e7a-112">Los cambios realizados con WMI afectarán a la configuración local en el punto de conexión donde se implementan o realizan los cambios.</span><span class="sxs-lookup"><span data-stu-id="41e7a-112">Changes made with WMI will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="41e7a-113">Esto significa que las implementaciones de directivas con directiva de grupo, Microsoft Endpoint Configuration Manager o Microsoft Intune pueden sobrescribir los cambios realizados con WMI.</span><span class="sxs-lookup"><span data-stu-id="41e7a-113">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with WMI.</span></span> 

<span data-ttu-id="41e7a-114">Puede configurar [qué opciones se pueden invalidar localmente con invalidaciones de directiva local.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="41e7a-114">You can [configure which settings can be overridden locally  with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="41e7a-115">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="41e7a-115">Related topics</span></span>

- [<span data-ttu-id="41e7a-116">Temas de referencia para herramientas de administración y configuración</span><span class="sxs-lookup"><span data-stu-id="41e7a-116">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="41e7a-117">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="41e7a-117">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)