---
title: Activar la retirada de definiciones Antivirus de Microsoft Defender
description: Active la retirada de definiciones Antivirus de Microsoft Defender.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defensa, retiro de definiciones
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
ms.openlocfilehash: 66b2e882a0f6de21e27dabb3a4bfe2fe113bcb32
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296497"
---
# <a name="turn-on-definition-retirement"></a><span data-ttu-id="4a798-104">Activar la retirada de definiciones</span><span class="sxs-lookup"><span data-stu-id="4a798-104">Turn on definition retirement</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4a798-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4a798-105">**Applies to:**</span></span>

- [<span data-ttu-id="4a798-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4a798-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4a798-107">Puede configurar la retirada de definiciones mediante la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="4a798-107">You can configure definition retirement using Group Policy.</span></span> <span data-ttu-id="4a798-108">La definición de retirada comprueba si un equipo tiene las actualizaciones de seguridad necesarias para protegerlo contra una vulnerabilidad determinada.</span><span class="sxs-lookup"><span data-stu-id="4a798-108">Definition retirement checks to see if a computer has the required security updates necessary to protect it against a particular vulnerability.</span></span> <span data-ttu-id="4a798-109">Si el sistema no es vulnerable a la vulnerabilidad detectada por una definición, esa definición se "retirará".</span><span class="sxs-lookup"><span data-stu-id="4a798-109">If the system is not vulnerable to the exploit detected by a definition, then that definition is "retired".</span></span> <span data-ttu-id="4a798-110">Si se retira toda la inteligencia de seguridad de un protocolo determinado, ese protocolo ya no se analiza.</span><span class="sxs-lookup"><span data-stu-id="4a798-110">If all security intelligence for a given protocol are retired then that protocol is no longer parsed.</span></span> <span data-ttu-id="4a798-111">Habilitar esta característica ayuda a mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4a798-111">Enabling this feature helps to improve performance.</span></span> <span data-ttu-id="4a798-112">En un equipo actualizado con todas las actualizaciones de seguridad más recientes, la protección de red no tendrá ningún impacto en el rendimiento de la red.</span><span class="sxs-lookup"><span data-stu-id="4a798-112">On a computer that is up-to-date with all the latest security updates, network protection will have no impact on network performance.</span></span>

## <a name="use-group-policy-to-configure-definition-retirement"></a><span data-ttu-id="4a798-113">Usar la directiva de grupo para configurar la retirada de definiciones</span><span class="sxs-lookup"><span data-stu-id="4a798-113">Use Group Policy to configure definition retirement</span></span>

1. <span data-ttu-id="4a798-114">En el extremo de administración de directivas de grupo, abra la Consola [de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="4a798-114">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="4a798-115">Vaya a **Configuración del equipo** Plantillas administrativas  >  **Windows** componentes  >    >  **Antivirus de Microsoft Defender** sistema de  >  **inspección de red**.</span><span class="sxs-lookup"><span data-stu-id="4a798-115">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="4a798-116">Seleccione **Activar la retirada de definiciones**.</span><span class="sxs-lookup"><span data-stu-id="4a798-116">Select **Turn on definition retirement**.</span></span> <span data-ttu-id="4a798-117">Esta directiva está habilitada de modo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4a798-117">By default, this policy is enabled.</span></span> <span data-ttu-id="4a798-118">Si se establece **No configurado,** la retirada de definiciones está habilitada.</span><span class="sxs-lookup"><span data-stu-id="4a798-118">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="4a798-119">Para editar la directiva, seleccione el vínculo **Editar configuración de** directiva.</span><span class="sxs-lookup"><span data-stu-id="4a798-119">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="4a798-120">Seleccione **Habilitado** y, a continuación, **seleccione Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4a798-120">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="4a798-121">Implemente el objeto de directiva de grupo actualizado.</span><span class="sxs-lookup"><span data-stu-id="4a798-121">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="4a798-122">Consulte [Consola de administración de directivas de grupo](/windows/win32/srvnodes/group-policy).</span><span class="sxs-lookup"><span data-stu-id="4a798-122">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="4a798-123">¿Usa objetos de directiva de grupo local?</span><span class="sxs-lookup"><span data-stu-id="4a798-123">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="4a798-124">Vea cómo se traducen en la nube.</span><span class="sxs-lookup"><span data-stu-id="4a798-124">See how they translate in the cloud.</span></span> <span data-ttu-id="4a798-125">[Analice los objetos de directiva de grupo locales mediante el análisis](/mem/intune/configuration/group-policy-analytics)de directivas de grupo en Microsoft Endpoint Manager - Vista previa .</span><span class="sxs-lookup"><span data-stu-id="4a798-125">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="4a798-126">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="4a798-126">Related articles</span></span>

- [<span data-ttu-id="4a798-127">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="4a798-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="4a798-128">Habilitar la protección proporcionada en la nube</span><span class="sxs-lookup"><span data-stu-id="4a798-128">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="4a798-129">Cómo crear e implementar directivas antimalware: Servicio de protección en la nube</span><span class="sxs-lookup"><span data-stu-id="4a798-129">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)