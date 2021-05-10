---
title: Activar el reconocimiento de protocolo para Antivirus de Microsoft Defender
description: Active el reconocimiento de protocolo para Antivirus de Microsoft Defender.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defensor, reconocimiento de protocolos
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
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296494"
---
# <a name="turn-on-protocol-recognition"></a><span data-ttu-id="4ce07-104">Activar el reconocimiento de protocolos</span><span class="sxs-lookup"><span data-stu-id="4ce07-104">Turn on protocol recognition</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4ce07-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4ce07-105">**Applies to:**</span></span>

- [<span data-ttu-id="4ce07-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4ce07-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4ce07-107">Esta configuración de directiva le permite configurar el reconocimiento de protocolos para la protección de red frente a vulnerabilidades conocidas.</span><span class="sxs-lookup"><span data-stu-id="4ce07-107">This policy setting allows you to configure protocol recognition for network protection against exploits of known vulnerabilities.</span></span> <span data-ttu-id="4ce07-108">Si habilita o no configura esta configuración, se habilitará el reconocimiento de protocolos.</span><span class="sxs-lookup"><span data-stu-id="4ce07-108">If you enable or do not configure this setting, protocol recognition will be enabled.</span></span> <span data-ttu-id="4ce07-109">Si deshabilita esta configuración, se deshabilitará el reconocimiento de protocolo.</span><span class="sxs-lookup"><span data-stu-id="4ce07-109">If you disable this setting, protocol recognition will be disabled.</span></span>

## <a name="use-group-policy-to-configure-protocol-recognition"></a><span data-ttu-id="4ce07-110">Usar la directiva de grupo para configurar el reconocimiento de protocolos</span><span class="sxs-lookup"><span data-stu-id="4ce07-110">Use Group Policy to configure protocol recognition</span></span>

1. <span data-ttu-id="4ce07-111">En el extremo de administración de directivas de grupo, abra la Consola [de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="4ce07-111">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="4ce07-112">Vaya a **Configuración del equipo** Plantillas administrativas  >  **Windows** componentes  >    >  **Antivirus de Microsoft Defender** sistema de  >  **inspección de red**.</span><span class="sxs-lookup"><span data-stu-id="4ce07-112">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="4ce07-113">Seleccione **reconocimiento de protocolo**.</span><span class="sxs-lookup"><span data-stu-id="4ce07-113">Select **protocol recognition**.</span></span> <span data-ttu-id="4ce07-114">Esta directiva está habilitada de modo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4ce07-114">By default, this policy is enabled.</span></span> <span data-ttu-id="4ce07-115">Si se establece **No configurado,** la retirada de definiciones está habilitada.</span><span class="sxs-lookup"><span data-stu-id="4ce07-115">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="4ce07-116">Para editar la directiva, seleccione el vínculo **Editar configuración de** directiva.</span><span class="sxs-lookup"><span data-stu-id="4ce07-116">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="4ce07-117">Seleccione **Habilitado** y, a continuación, **seleccione Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4ce07-117">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="4ce07-118">Implemente el objeto de directiva de grupo actualizado.</span><span class="sxs-lookup"><span data-stu-id="4ce07-118">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="4ce07-119">Consulte [Consola de administración de directivas de grupo](/windows/win32/srvnodes/group-policy).</span><span class="sxs-lookup"><span data-stu-id="4ce07-119">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="4ce07-120">¿Usa objetos de directiva de grupo local?</span><span class="sxs-lookup"><span data-stu-id="4ce07-120">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="4ce07-121">Vea cómo se traducen en la nube.</span><span class="sxs-lookup"><span data-stu-id="4ce07-121">See how they translate in the cloud.</span></span> <span data-ttu-id="4ce07-122">[Analice los objetos de directiva de grupo locales mediante el análisis](/mem/intune/configuration/group-policy-analytics)de directivas de grupo en Microsoft Endpoint Manager - Vista previa .</span><span class="sxs-lookup"><span data-stu-id="4ce07-122">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="4ce07-123">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="4ce07-123">Related articles</span></span>

- [<span data-ttu-id="4ce07-124">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="4ce07-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="4ce07-125">Habilitar la protección proporcionada en la nube</span><span class="sxs-lookup"><span data-stu-id="4ce07-125">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="4ce07-126">Cómo crear e implementar directivas antimalware: Servicio de protección en la nube</span><span class="sxs-lookup"><span data-stu-id="4ce07-126">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)