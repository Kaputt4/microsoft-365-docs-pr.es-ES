---
title: Optimizar la implementación y detecciones de reglas ASR
description: Optimice las reglas de reducción de superficie de ataque (ASR) para identificar y evitar vulnerabilidades de malware típicas.
keywords: onboard, administración de Intune, Microsoft Defender para Endpoint, Microsoft Defender, Windows Defender, reducción de superficie de ataque, ASR, línea base de seguridad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 91295135c833c6b403078bdfd517c7b84ec7d630
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932852"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a><span data-ttu-id="61d94-104">Optimizar la implementación y detecciones de reglas ASR</span><span class="sxs-lookup"><span data-stu-id="61d94-104">Optimize ASR rule deployment and detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="61d94-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="61d94-105">**Applies to:**</span></span>
- [<span data-ttu-id="61d94-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="61d94-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="61d94-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61d94-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="61d94-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="61d94-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="61d94-109">[Registrarse para obtener una versión de prueba gratuita](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="61d94-109">[Sign up for a free trial](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span></span>

<span data-ttu-id="61d94-110">Las reglas de reducción de superficie de ataque [(ASR)](./attack-surface-reduction.md) identifican y evitan vulnerabilidades de malware típicas.</span><span class="sxs-lookup"><span data-stu-id="61d94-110">[Attack surface reduction (ASR) rules](./attack-surface-reduction.md) identify and prevent typical malware exploits.</span></span> <span data-ttu-id="61d94-111">Controlan cuándo y cómo se puede ejecutar el código potencialmente malintencionado.</span><span class="sxs-lookup"><span data-stu-id="61d94-111">They control when and how potentially malicious code can run.</span></span> <span data-ttu-id="61d94-112">Por ejemplo, pueden impedir que JavaScript o VBScript inicien un archivo ejecutable descargado, bloquear llamadas a la API de Win32 desde macros de Office y bloquear procesos que se ejecutan desde unidades USB.</span><span class="sxs-lookup"><span data-stu-id="61d94-112">For example, they can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, and block processes that run from USB drives.</span></span>

<span data-ttu-id="61d94-113">![Tarjeta de administración de superficie de ataque](images/secconmgmt_asr_card.png)</span><span class="sxs-lookup"><span data-stu-id="61d94-113">![Attack surface management card](images/secconmgmt_asr_card.png)</span></span><br>
<span data-ttu-id="61d94-114">*Tarjeta de administración de superficie de ataque*</span><span class="sxs-lookup"><span data-stu-id="61d94-114">*Attack surface management card*</span></span>

<span data-ttu-id="61d94-115">La *tarjeta de administración de* superficie de ataque es un punto de entrada a las herramientas del centro de seguridad de Microsoft 365 que puedes usar para:</span><span class="sxs-lookup"><span data-stu-id="61d94-115">The *Attack surface management card* is an entry point to tools in Microsoft 365 security center that you can use to:</span></span>

* <span data-ttu-id="61d94-116">Comprenda cómo se implementan actualmente las reglas de ASR en su organización.</span><span class="sxs-lookup"><span data-stu-id="61d94-116">Understand how ASR rules are currently deployed in your organization.</span></span>
* <span data-ttu-id="61d94-117">Revise las detecciones de ASR e identifique posibles detecciones incorrectas.</span><span class="sxs-lookup"><span data-stu-id="61d94-117">Review ASR detections and identify possible incorrect detections.</span></span>
* <span data-ttu-id="61d94-118">Analice el impacto de las exclusiones y genere la lista de rutas de archivo que se excluirán.</span><span class="sxs-lookup"><span data-stu-id="61d94-118">Analyze the impact of exclusions and generate the list of file paths to exclude.</span></span>

<span data-ttu-id="61d94-119">Selecciona **Ir a administración de** superficie de ataque Supervisión & informes > reglas de reducción de superficie de ataque > Agregar  >  **exclusiones**.</span><span class="sxs-lookup"><span data-stu-id="61d94-119">Select **Go to attack surface management** > **Monitoring & reports > Attack surface reduction rules > Add exclusions**.</span></span> <span data-ttu-id="61d94-120">Desde allí, puede navegar a otras secciones del Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61d94-120">From there, you can navigate to other sections of Microsoft 365 security center.</span></span>

<span data-ttu-id="61d94-121">![Pestaña Agregar exclusiones en la página Reglas de reducción de superficie de ataque en el Centro de seguridad de Microsoft 365](images/secconmgmt_asr_m365exlusions.png)</span><span class="sxs-lookup"><span data-stu-id="61d94-121">![Add exclusions tab in the Attack surface reduction rules page in Microsoft 365 security center](images/secconmgmt_asr_m365exlusions.png)</span></span><br>
<span data-ttu-id="61d94-122">La pestaña Agregar exclusiones de la página Reglas de reducción de superficie de ataque en el Centro de *seguridad de Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="61d94-122">The ***Add exclusions** tab in the Attack surface reduction rules page in Microsoft 365 security center*</span></span>

> [!NOTE]
> <span data-ttu-id="61d94-123">Para tener acceso al Centro de seguridad de Microsoft 365, necesita una licencia de Microsoft 365 E3 o E5 y una cuenta que tenga determinados roles en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="61d94-123">To access Microsoft 365 security center, you need a Microsoft 365 E3 or E5 license and an account that has certain roles on Azure Active Directory.</span></span> <span data-ttu-id="61d94-124">[Lea acerca de las licencias y permisos necesarios.](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="61d94-124">[Read about required licenses and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="61d94-125">Para obtener más información acerca de la implementación de reglas ASR en el Centro de seguridad de Microsoft 365, vea [Monitor and manage ASR rule deployment and detections](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).</span><span class="sxs-lookup"><span data-stu-id="61d94-125">For more information about ASR rule deployment in Microsoft 365 security center, see [Monitor and manage ASR rule deployment and detections](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).</span></span>

<span data-ttu-id="61d94-126">**Temas relacionados**</span><span class="sxs-lookup"><span data-stu-id="61d94-126">**Related topics**</span></span>

* [<span data-ttu-id="61d94-127">Asegurarse de que los dispositivos estén configurados de manera adecuada</span><span class="sxs-lookup"><span data-stu-id="61d94-127">Ensure your devices are configured properly</span></span>](configure-machines.md)
* [<span data-ttu-id="61d94-128">Obtener dispositivos incorporados a Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="61d94-128">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
* [<span data-ttu-id="61d94-129">Supervisar el cumplimiento de la línea base de seguridad de Microsoft Defender para endpoints</span><span class="sxs-lookup"><span data-stu-id="61d94-129">Monitor compliance to the Microsoft Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
