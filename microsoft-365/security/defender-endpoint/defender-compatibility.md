---
title: Compatibilidad de soluciones antivirus con Defender para endpoint
description: Obtenga información sobre Windows Defender funciona con Microsoft Defender para Endpoint y cómo funciona cuando se usa un cliente antimalware de terceros.
keywords: Compatibilidad de windows Defender, defender, Microsoft Defender para endpoint, defender para endpoint, antivirus, mde
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
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: f5a0db755f919cb47c4cd284857ddf4e27d16996
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782890"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="23713-104">Compatibilidad de soluciones antivirus con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="23713-104">Antivirus solution compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="23713-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="23713-105">**Applies to:**</span></span>
- [<span data-ttu-id="23713-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="23713-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="23713-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23713-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="23713-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="23713-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="23713-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="23713-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="23713-110">El agente de Microsoft Defender para endpoint depende Antivirus de Microsoft Defender para algunas funcionalidades, como el examen de archivos.</span><span class="sxs-lookup"><span data-stu-id="23713-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="23713-111">Defender for Endpoint no se adhiere a la configuración Antivirus de Microsoft Defender exclusiones.</span><span class="sxs-lookup"><span data-stu-id="23713-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="23713-112">Debe configurar las actualizaciones de inteligencia de seguridad en los dispositivos defender para puntos de conexión Antivirus de Microsoft Defender es el antimalware activo o no.</span><span class="sxs-lookup"><span data-stu-id="23713-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="23713-113">Para obtener más información, vea [Manage Antivirus de Microsoft Defender updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="23713-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="23713-114">Si un dispositivo incorporado está protegido por un cliente antimalware de terceros, Antivirus de Microsoft Defender en ese punto de conexión entrará en modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="23713-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="23713-115">Antivirus de Microsoft Defender seguirá recibiendo actualizaciones y el proceso de *mspeng.exe* aparecerá como un servicio en ejecución, pero no realizará exámenes y no reemplazará al cliente antimalware de terceros en ejecución.</span><span class="sxs-lookup"><span data-stu-id="23713-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="23713-116">La Antivirus de Microsoft Defender se deshabilitará y los usuarios del dispositivo no podrán usar Antivirus de Microsoft Defender realizar exámenes a petición ni configurar la mayoría de las opciones.</span><span class="sxs-lookup"><span data-stu-id="23713-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="23713-117">Para obtener más información, vea [el tema Antivirus de Microsoft Defender y defender para la](microsoft-defender-antivirus-compatibility.md)compatibilidad de extremos .</span><span class="sxs-lookup"><span data-stu-id="23713-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](microsoft-defender-antivirus-compatibility.md).</span></span>
