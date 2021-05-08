---
title: Especificar el nivel de protección entregado en la nube para Antivirus de Microsoft Defender
description: Establece el nivel de protección entregada en la nube para Antivirus de Microsoft Defender.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defender, nube, agresividad, nivel de protección
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f441b1bd444cd70fb5b00dfcb5ebcddadf62b220
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274909"
---
# <a name="specify-the-cloud-delivered-protection-level"></a><span data-ttu-id="9dfd9-104">Especificar el nivel de protección proporcionado en la nube</span><span class="sxs-lookup"><span data-stu-id="9dfd9-104">Specify the cloud-delivered protection level</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9dfd9-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9dfd9-105">**Applies to:**</span></span>

- [<span data-ttu-id="9dfd9-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="9dfd9-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9dfd9-107">Puede especificar el nivel de protección entregada en la nube que ofrece Antivirus de Microsoft Defender mediante Microsoft Endpoint Manager (recomendado) o la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-107">You can specify your level of cloud-delivered protection offered by Microsoft Defender Antivirus by using Microsoft Endpoint Manager (recommended) or Group Policy.</span></span>

> [!TIP]
> <span data-ttu-id="9dfd9-108">La protección en la nube no es simplemente protección para los archivos almacenados en la nube.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-108">Cloud protection is not simply protection for files that are stored in the cloud.</span></span> <span data-ttu-id="9dfd9-109">El servicio en la nube de Antivirus de Microsoft Defender es un mecanismo para ofrecer protección actualizada a la red y los dispositivos (también denominados puntos de conexión).</span><span class="sxs-lookup"><span data-stu-id="9dfd9-109">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and devices (also called endpoints).</span></span> <span data-ttu-id="9dfd9-110">La protección en la nube con Microsoft Defender Antivirus usa recursos distribuidos y aprendizaje automático para ofrecer protección a los puntos de conexión a una velocidad mucho más rápida que las actualizaciones de inteligencia de seguridad tradicionales.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-110">Cloud protection with Microsoft Defender Antivirus uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional security intelligence updates.</span></span> <span data-ttu-id="9dfd9-111">Microsoft Intune y Microsoft Endpoint Manager ahora forman parte de [Microsoft Endpoint Manager.](/mem/endpoint-manager-overview)</span><span class="sxs-lookup"><span data-stu-id="9dfd9-111">Microsoft Intune and Microsoft Endpoint Manager are now part of [Microsoft Endpoint Manager](/mem/endpoint-manager-overview).</span></span> 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="9dfd9-112">Usar Microsoft Endpoint Manager para especificar el nivel de protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="9dfd9-112">Use Microsoft Endpoint Manager to specify the level of cloud-delivered protection</span></span>

1. <span data-ttu-id="9dfd9-113">Vaya al Centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-113">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="9dfd9-114">Elija **Endpoint security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-114">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="9dfd9-115">Seleccione un perfil antivirus.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-115">Select an antivirus profile.</span></span> <span data-ttu-id="9dfd9-116">(Si aún no tienes uno o quieres crear un perfil nuevo, consulta Configurar la configuración de restricción de [dispositivos en Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="9dfd9-116">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="9dfd9-117">Seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-117">Select **Properties**.</span></span> <span data-ttu-id="9dfd9-118">A continuación, junto **a Configuración,** elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-118">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="9dfd9-119">Expanda **Protección en la** nube y, a continuación, en la lista Nivel de protección entregado en **la** nube, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9dfd9-119">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>

    1. <span data-ttu-id="9dfd9-120">**High:** aplica un nivel de detección fuerte.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-120">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="9dfd9-121">**High plus:** usa el **nivel alto** y aplica medidas de protección adicionales (puede afectar al rendimiento del cliente).</span><span class="sxs-lookup"><span data-stu-id="9dfd9-121">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="9dfd9-122">**Tolerancia cero:** bloquea todos los ejecutables desconocidos.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-122">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="9dfd9-123">Elija **Revisar + guardar** y, a continuación, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-123">Choose **Review + save**, and then choose **Save**.</span></span> 

> [!TIP]
> <span data-ttu-id="9dfd9-124">¿Necesita ayuda?</span><span class="sxs-lookup"><span data-stu-id="9dfd9-124">Need some help?</span></span> <span data-ttu-id="9dfd9-125">Vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="9dfd9-125">See the following resources:</span></span>
> - [<span data-ttu-id="9dfd9-126">Configurar Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="9dfd9-126">Configure Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [<span data-ttu-id="9dfd9-127">Agregar configuración de protección de puntos de conexión en Intune</span><span class="sxs-lookup"><span data-stu-id="9dfd9-127">Add endpoint protection settings in Intune</span></span>](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="9dfd9-128">Usar la directiva de grupo para especificar el nivel de protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="9dfd9-128">Use Group Policy to specify the level of cloud-delivered protection</span></span>

1.  <span data-ttu-id="9dfd9-129">En el equipo de administración de directivas de grupo, abra la Consola [de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="9dfd9-129">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="9dfd9-130">Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-130">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

3.  <span data-ttu-id="9dfd9-131">En el **Editor de administración de directivas de grupo** vaya a **Configuración** del equipo  >  **Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="9dfd9-131">In the **Group Policy Management Editor** go to **Computer Configuration** > **Administrative templates**.</span></span>

4.  <span data-ttu-id="9dfd9-132">Expande el árbol a **Componentes de Windows** Microsoft Defender  >  **Antivirus**  >  **MpEngine**.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-132">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

5.  <span data-ttu-id="9dfd9-133">Haga doble clic en la **configuración Seleccionar nivel de** protección en la nube y estabóla en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-133">Double-click the **Select cloud protection level** setting and set it to **Enabled**.</span></span> <span data-ttu-id="9dfd9-134">Seleccione el nivel de protección:</span><span class="sxs-lookup"><span data-stu-id="9dfd9-134">Select the level of protection:</span></span>
    - <span data-ttu-id="9dfd9-135">**El nivel de bloqueo predeterminado** proporciona una detección segura sin aumentar el riesgo de detectar archivos legítimos.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-135">**Default blocking level** provides strong detection without increasing the risk of detecting legitimate files.</span></span>
    - <span data-ttu-id="9dfd9-136">**El nivel de bloqueo moderado** proporciona moderación solo para detecciones de elevada confianza</span><span class="sxs-lookup"><span data-stu-id="9dfd9-136">**Moderate blocking level** provides moderate only for high confidence detections</span></span>
    - <span data-ttu-id="9dfd9-137">**El nivel alto de bloqueo** aplica un alto nivel de detección a la vez que optimiza el rendimiento del cliente (pero también puede ofrecer una mayor probabilidad de falsos positivos).</span><span class="sxs-lookup"><span data-stu-id="9dfd9-137">**High blocking level** applies a strong level of detection while optimizing client performance (but can also give you a greater chance of false positives).</span></span>
    - <span data-ttu-id="9dfd9-138">**Alto + nivel de bloqueo** aplica medidas de protección adicionales (puede afectar al rendimiento del cliente y aumentar la probabilidad de falsos positivos).</span><span class="sxs-lookup"><span data-stu-id="9dfd9-138">**High + blocking level** applies additional protection measures (might impact client performance and increase your chance of false positives).</span></span>
    - <span data-ttu-id="9dfd9-139">**El nivel de bloqueo de tolerancia cero** bloquea todos los ejecutables desconocidos.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-139">**Zero tolerance blocking level** blocks all unknown executables.</span></span>
    
    > [!WARNING]
    > <span data-ttu-id="9dfd9-140">Aunque es poco probable, establecer este cambio en **High** o **High +** puede provocar que se detecten algunos archivos legítimos (aunque tendrá la opción de desbloquear o disputar esa detección).</span><span class="sxs-lookup"><span data-stu-id="9dfd9-140">While unlikely, setting this switch to **High** or **High +** may cause some legitimate files to be detected (although you will have the option to unblock or dispute that detection).</span></span>

6. <span data-ttu-id="9dfd9-141">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-141">Click **OK**.</span></span>

7. <span data-ttu-id="9dfd9-142">Implemente el objeto de directiva de grupo actualizado.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-142">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="9dfd9-143">Consulta [Consola de administración de directivas de grupo](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="9dfd9-143">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy)</span></span>

> [!TIP]
> <span data-ttu-id="9dfd9-144">¿Usa objetos de directiva de grupo local?</span><span class="sxs-lookup"><span data-stu-id="9dfd9-144">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="9dfd9-145">Vea cómo se traducen en la nube.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-145">See how they translate in the cloud.</span></span> <span data-ttu-id="9dfd9-146">[Analice los objetos de directiva de grupo locales mediante el](/mem/intune/configuration/group-policy-analytics)análisis de directivas de grupo en Microsoft Endpoint Manager - Versión preliminar .</span><span class="sxs-lookup"><span data-stu-id="9dfd9-146">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="9dfd9-147">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="9dfd9-147">Related articles</span></span>

- [<span data-ttu-id="9dfd9-148">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="9dfd9-148">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="9dfd9-149">Habilitar la protección de entrega en la nube</span><span class="sxs-lookup"><span data-stu-id="9dfd9-149">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9dfd9-150">Cómo crear e implementar directivas antimalware: Servicio de protección en la nube</span><span class="sxs-lookup"><span data-stu-id="9dfd9-150">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)