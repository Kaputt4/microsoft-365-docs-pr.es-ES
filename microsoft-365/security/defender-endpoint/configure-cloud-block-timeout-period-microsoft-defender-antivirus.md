---
title: Configurar el período Antivirus de Microsoft Defender de tiempo de espera del bloque de nube
description: Puede configurar cuánto tiempo Antivirus de Microsoft Defender bloqueará la ejecución de un archivo mientras espera una determinación de nube.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defender, nube, tiempo de espera, bloqueo, punto, segundos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789092"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="be571-104">Configurar el período de espera de bloqueo en la nube</span><span class="sxs-lookup"><span data-stu-id="be571-104">Configure the cloud block timeout period</span></span>

<span data-ttu-id="be571-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="be571-105">**Applies to:**</span></span>

- [<span data-ttu-id="be571-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="be571-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="be571-107">Cuando Antivirus de Microsoft Defender encuentra un archivo sospechoso, puede impedir que el archivo se ejecute mientras consulta el servicio [Antivirus de Microsoft Defender nube](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="be571-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="be571-108">El período predeterminado de bloqueo del [archivo](configure-block-at-first-sight-microsoft-defender-antivirus.md) es de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="be571-108">The default period that the file is [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="be571-109">Si es administrador de seguridad, puede especificar más tiempo para esperar antes de que se pueda ejecutar el archivo.</span><span class="sxs-lookup"><span data-stu-id="be571-109">If you're a security administrator, you can specify more time to wait before the file is allowed to run.</span></span> <span data-ttu-id="be571-110">Extender el período de tiempo de espera de bloqueo de nube puede ayudar a garantizar que hay tiempo suficiente para recibir una determinación adecuada del servicio de nube Antivirus de Microsoft Defender nube.</span><span class="sxs-lookup"><span data-stu-id="be571-110">Extending the cloud block timeout period can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="be571-111">Requisitos previos para usar el tiempo de espera extendido del bloque de nube</span><span class="sxs-lookup"><span data-stu-id="be571-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="be571-112">[Bloquear a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) y sus requisitos previos deben estar habilitados para poder especificar un período de tiempo de espera extendido.</span><span class="sxs-lookup"><span data-stu-id="be571-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a><span data-ttu-id="be571-113">Especifique el período de tiempo de espera extendido mediante Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="be571-113">Specify the extended timeout period using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="be571-114">Puede especificar el período de tiempo de espera de bloqueo de nube con una [directiva de seguridad de extremo en Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).</span><span class="sxs-lookup"><span data-stu-id="be571-114">You can specify the cloud block timeout period with an [endpoint security policy in Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).</span></span>

1. <span data-ttu-id="be571-115">Vaya al Centro Endpoint Manager de administración ( [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="be571-115">Go to the Endpoint Manager admin center ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) and sign in.</span></span>

2. <span data-ttu-id="be571-116">Seleccione **Seguridad de extremo** y, a continuación, en **Administrar**, elija **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="be571-116">Select **Endpoint security**, and then under **Manage**, choose **Antivirus**.</span></span>

3. <span data-ttu-id="be571-117">Seleccione (o cree) una directiva antivirus.</span><span class="sxs-lookup"><span data-stu-id="be571-117">Select (or create) an antivirus policy.</span></span>

4. <span data-ttu-id="be571-118">En la **sección Configuración,** expanda **Protección de nube**.</span><span class="sxs-lookup"><span data-stu-id="be571-118">In the **Configuration settings** section, expand **Cloud protection**.</span></span> <span data-ttu-id="be571-119">A continuación, en el cuadro Tiempo de espera extendido de la nube de **Defender en** segundos, especifique más tiempo, en segundos, de 1 segundo a 50 segundos.</span><span class="sxs-lookup"><span data-stu-id="be571-119">Then, in the **Defender Cloud Extended Timeout In Seconds** box, specify the more time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="be571-120">Lo que especifique se agrega al valor predeterminado de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="be571-120">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="be571-121">(Este paso es opcional) Realice cualquier otro cambio en la directiva de antivirus.</span><span class="sxs-lookup"><span data-stu-id="be571-121">(This step is optional) Make any other changes to your antivirus policy.</span></span> <span data-ttu-id="be571-122">(¿Necesita ayuda?</span><span class="sxs-lookup"><span data-stu-id="be571-122">(Need help?</span></span> <span data-ttu-id="be571-123">Vea [Configuración para obtener Antivirus de Microsoft Defender directiva en Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)</span><span class="sxs-lookup"><span data-stu-id="be571-123">See [Settings for Microsoft Defender Antivirus policy in Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)</span></span>

6. <span data-ttu-id="be571-124">Elija **Siguiente** y termine de configurar la directiva.</span><span class="sxs-lookup"><span data-stu-id="be571-124">Choose **Next**, and finish configuring your policy.</span></span>

## <a name="specify-the-extended-timeout-period-using-group-policy"></a><span data-ttu-id="be571-125">Especificar el período de tiempo de espera extendido mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="be571-125">Specify the extended timeout period using Group Policy</span></span>

<span data-ttu-id="be571-126">Puede usar la directiva de grupo para especificar un tiempo de espera extendido para las comprobaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="be571-126">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="be571-127">En el equipo de administración de directivas de grupo, abra la Consola [de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="be571-127">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span></span>

2. <span data-ttu-id="be571-128">Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="be571-128">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

3. <span data-ttu-id="be571-129">En el **Editor de administración de directivas de** grupo, vaya a Configuración **del** equipo y, a continuación, seleccione **Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="be571-129">In the **Group Policy Management Editor**, go to **Computer configuration**, and then select **Administrative templates**.</span></span>

3. <span data-ttu-id="be571-130">Expanda el árbol para **Windows componentes**  >  **Antivirus de Microsoft Defender**  >  **MpEngine**.</span><span class="sxs-lookup"><span data-stu-id="be571-130">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

4. <span data-ttu-id="be571-131">Haga doble clic en **Configurar la comprobación de nube extendida** y asegúrese de que la opción está habilitada.</span><span class="sxs-lookup"><span data-stu-id="be571-131">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> 

   <span data-ttu-id="be571-132">Especifique la cantidad de tiempo adicional para evitar que el archivo se ejecute mientras espera una determinación de nube.</span><span class="sxs-lookup"><span data-stu-id="be571-132">Specify the extra amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="be571-133">Especifica el tiempo adicional, en segundos, de 1 segundo a 50 segundos.</span><span class="sxs-lookup"><span data-stu-id="be571-133">Specify the extra time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="be571-134">Lo que especifique se agrega al valor predeterminado de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="be571-134">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="be571-135">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="be571-135">Select **OK**.</span></span>

 