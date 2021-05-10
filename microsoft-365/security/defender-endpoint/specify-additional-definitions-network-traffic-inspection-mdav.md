---
title: Especifique conjuntos de definiciones adicionales para la inspección del tráfico de red Antivirus de Microsoft Defender
description: Especifique conjuntos de definiciones adicionales para la inspección del tráfico de red Antivirus de Microsoft Defender.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defensor, inspección de tráfico de red
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300260"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="5bf53-104">Especificar conjuntos de definiciones adicionales para la inspección del tráfico de red</span><span class="sxs-lookup"><span data-stu-id="5bf53-104">Specify additional definition sets for network traffic inspection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5bf53-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="5bf53-105">**Applies to:**</span></span>

- [<span data-ttu-id="5bf53-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="5bf53-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="5bf53-107">Puede especificar conjuntos de definiciones adicionales para la inspección del tráfico de red mediante la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="5bf53-107">You can specify additional definition sets for network traffic inspection using Group Policy.</span></span>

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="5bf53-108">Usar la directiva de grupo para especificar conjuntos de definiciones adicionales para la inspección del tráfico de red</span><span class="sxs-lookup"><span data-stu-id="5bf53-108">Use Group Policy to specify additional definition sets for network traffic inspection</span></span>

1. <span data-ttu-id="5bf53-109">En el extremo de administración de directivas de grupo, abra la Consola [de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="5bf53-109">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="5bf53-110">Vaya a **Windows Components**  >  **Antivirus de Microsoft Defender**  >  **Network Inspection System**.</span><span class="sxs-lookup"><span data-stu-id="5bf53-110">Go to **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="5bf53-111">Seleccione **Especificar conjuntos de definiciones adicionales para la inspección de tráfico de red.**</span><span class="sxs-lookup"><span data-stu-id="5bf53-111">Select **Specify additional definition sets for network traffic inspection**.</span></span> <span data-ttu-id="5bf53-112">De forma predeterminada, esta directiva se establece en **No configurado**.</span><span class="sxs-lookup"><span data-stu-id="5bf53-112">By default, this policy is set to **Not configured**.</span></span> 

4. <span data-ttu-id="5bf53-113">Para editar la directiva, seleccione el vínculo **Editar configuración de** directiva.</span><span class="sxs-lookup"><span data-stu-id="5bf53-113">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="5bf53-114">Seleccione **Habilitado** y, a continuación, en la **sección Opciones,** seleccione **Mostrar...**.</span><span class="sxs-lookup"><span data-stu-id="5bf53-114">Select **Enabled**, and then in the **Options** section, select **Show...**.</span></span>

6. <span data-ttu-id="5bf53-115">Agregue entradas a la lista y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5bf53-115">Add entries to the list, and then select **OK**.</span></span> 

   <span data-ttu-id="5bf53-116">Cada entrada debe aparecer como un par nombre-valor, donde el nombre es una representación de cadena de un GUID del conjunto de definiciones.</span><span class="sxs-lookup"><span data-stu-id="5bf53-116">Each entry must be listed as a name-value pair, where the name is a string representation of a definition set GUID.</span></span> <span data-ttu-id="5bf53-117">Por ejemplo, el GUID del conjunto de definiciones para habilitar la inteligencia de seguridad de pruebas se define como: `{b54b6ac9-a737-498e-9120-6616ad3bf590}` .</span><span class="sxs-lookup"><span data-stu-id="5bf53-117">As an example, the definition set GUID to enable test security intelligence is defined as: `{b54b6ac9-a737-498e-9120-6616ad3bf590}`.</span></span> <span data-ttu-id="5bf53-118">El valor no se usa, por lo que se recomienda establecerlo en `0` .</span><span class="sxs-lookup"><span data-stu-id="5bf53-118">The value is not used, so we recommend setting it to `0`.</span></span> 

7. <span data-ttu-id="5bf53-119">Seleccione **Aceptar** y, a continuación, implemente el objeto de directiva de grupo actualizado.</span><span class="sxs-lookup"><span data-stu-id="5bf53-119">Select **OK**, and then deploy your updated Group Policy Object.</span></span> <span data-ttu-id="5bf53-120">Consulte [Consola de administración de directivas de grupo](/windows/win32/srvnodes/group-policy).</span><span class="sxs-lookup"><span data-stu-id="5bf53-120">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="5bf53-121">¿Usa objetos de directiva de grupo local?</span><span class="sxs-lookup"><span data-stu-id="5bf53-121">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="5bf53-122">Vea cómo se traducen en la nube.</span><span class="sxs-lookup"><span data-stu-id="5bf53-122">See how they translate in the cloud.</span></span> <span data-ttu-id="5bf53-123">[Analice los objetos de directiva de grupo locales mediante el análisis](/mem/intune/configuration/group-policy-analytics)de directivas de grupo en Microsoft Endpoint Manager - Vista previa .</span><span class="sxs-lookup"><span data-stu-id="5bf53-123">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="5bf53-124">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="5bf53-124">Related articles</span></span>

- [<span data-ttu-id="5bf53-125">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="5bf53-125">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="5bf53-126">Habilitar la protección proporcionada en la nube</span><span class="sxs-lookup"><span data-stu-id="5bf53-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="5bf53-127">Cómo crear e implementar directivas antimalware: Servicio de protección en la nube</span><span class="sxs-lookup"><span data-stu-id="5bf53-127">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)