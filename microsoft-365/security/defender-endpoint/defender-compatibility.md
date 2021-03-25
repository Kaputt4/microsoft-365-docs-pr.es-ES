---
title: Compatibilidad de Antivirus de Microsoft Defender con Defender para endpoint
description: Obtenga información sobre Windows Defender funciona con Microsoft Defender para Endpoint y cómo funciona cuando se usa un cliente antimalware de terceros.
keywords: Compatibilidad de windows defender, defender, atp de microsoft defender, defender para el punto de conexión, antivirus, mde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 63dca2694dae5dee924c9a0a02a660003907c42b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165966"
---
# <a name="microsoft-defender-antivirus-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="c0486-104">Compatibilidad de Antivirus de Microsoft Defender con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="c0486-104">Microsoft Defender Antivirus compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c0486-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c0486-105">**Applies to:**</span></span>
- [<span data-ttu-id="c0486-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c0486-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c0486-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0486-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="c0486-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c0486-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c0486-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c0486-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="c0486-110">El agente de Microsoft Defender para endpoints depende del Antivirus de Microsoft Defender para algunas funcionalidades, como el examen de archivos.</span><span class="sxs-lookup"><span data-stu-id="c0486-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c0486-111">Defender for Endpoint no se adhiere a la configuración de exclusiones de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c0486-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="c0486-112">Debe configurar las actualizaciones de inteligencia de seguridad en los dispositivos defender para puntos de conexión, independientemente de si Antivirus de Microsoft Defender es el antimalware activo o no.</span><span class="sxs-lookup"><span data-stu-id="c0486-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="c0486-113">Para obtener más información, vea [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="c0486-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="c0486-114">Si un dispositivo incorporado está protegido por un cliente antimalware de terceros, antivirus de Microsoft Defender en ese punto de conexión entrará en modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="c0486-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="c0486-115">Antivirus de Microsoft Defender seguirá recibiendo actualizaciones y el proceso *demspeng.exe* aparecerá como un servicio en ejecución, pero no realizará exámenes y no reemplazará al cliente antimalware de terceros en ejecución.</span><span class="sxs-lookup"><span data-stu-id="c0486-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="c0486-116">La interfaz de Antivirus de Microsoft Defender se deshabilitará y los usuarios del dispositivo no podrán usar Antivirus de Microsoft Defender para realizar exámenes a petición ni configurar la mayoría de las opciones.</span><span class="sxs-lookup"><span data-stu-id="c0486-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="c0486-117">Para obtener más información, vea el tema [de compatibilidad de Microsoft Defender Antivirus y Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span><span class="sxs-lookup"><span data-stu-id="c0486-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
