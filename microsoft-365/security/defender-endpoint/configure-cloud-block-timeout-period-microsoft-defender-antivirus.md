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
ms.openlocfilehash: 02b8ee1c73116718d771847a43d6334e0723bd5c
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275317"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="23085-104">Configurar el período de espera de bloqueo en la nube</span><span class="sxs-lookup"><span data-stu-id="23085-104">Configure the cloud block timeout period</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="23085-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="23085-105">**Applies to:**</span></span>

- [<span data-ttu-id="23085-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="23085-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="23085-107">Cuando Antivirus de Microsoft Defender encuentra un archivo sospechoso, puede impedir que el archivo se ejecute mientras consulta el servicio [Antivirus de Microsoft Defender nube](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="23085-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="23085-108">El período predeterminado en el que se [bloqueará el archivo](configure-block-at-first-sight-microsoft-defender-antivirus.md) es de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="23085-108">The default period that the file will be [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="23085-109">Puede especificar un período de tiempo adicional para esperar antes de que se pueda ejecutar el archivo.</span><span class="sxs-lookup"><span data-stu-id="23085-109">You can specify an additional period of time to wait before the file is allowed to run.</span></span> <span data-ttu-id="23085-110">Esto puede ayudar a garantizar que hay suficiente tiempo para recibir una determinación adecuada del servicio Antivirus de Microsoft Defender nube.</span><span class="sxs-lookup"><span data-stu-id="23085-110">This can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="23085-111">Requisitos previos para usar el tiempo de espera extendido del bloque de nube</span><span class="sxs-lookup"><span data-stu-id="23085-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="23085-112">[Bloquear a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) y sus requisitos previos deben estar habilitados para poder especificar un período de tiempo de espera extendido.</span><span class="sxs-lookup"><span data-stu-id="23085-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period"></a><span data-ttu-id="23085-113">Especificar el período de tiempo de espera extendido</span><span class="sxs-lookup"><span data-stu-id="23085-113">Specify the extended timeout period</span></span>

<span data-ttu-id="23085-114">Puede usar la directiva de grupo para especificar un tiempo de espera extendido para las comprobaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="23085-114">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="23085-115">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="23085-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="23085-116">En el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo **y** haga clic en **Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="23085-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="23085-117">Expanda el árbol para Windows **componentes > Antivirus de Microsoft Defender > MpEngine**</span><span class="sxs-lookup"><span data-stu-id="23085-117">Expand the tree to **Windows components > Microsoft Defender Antivirus > MpEngine**</span></span>

4. <span data-ttu-id="23085-118">Haga doble clic en **Configurar la comprobación de nube extendida** y asegúrese de que la opción está habilitada.</span><span class="sxs-lookup"><span data-stu-id="23085-118">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> <span data-ttu-id="23085-119">Especifique la cantidad de tiempo adicional para evitar que el archivo se ejecute mientras espera una determinación de nube.</span><span class="sxs-lookup"><span data-stu-id="23085-119">Specify the additional amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="23085-120">Puede especificar el tiempo adicional, en segundos, de 1 segundo a 50 segundos.</span><span class="sxs-lookup"><span data-stu-id="23085-120">You can specify the additional time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="23085-121">Esta vez se agregará al valor predeterminado de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="23085-121">This time will be added to the default 10 seconds.</span></span>

5. <span data-ttu-id="23085-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="23085-122">Click **OK**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="23085-123">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="23085-123">Related topics</span></span>

- [<span data-ttu-id="23085-124">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="23085-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="23085-125">Usar tecnologías antivirus de última generación a través de la protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="23085-125">Use next-generation antivirus technologies through cloud-delivered protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="23085-126">Configurar bloque a primera vista</span><span class="sxs-lookup"><span data-stu-id="23085-126">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="23085-127">Habilitar la protección de entrega en la nube</span><span class="sxs-lookup"><span data-stu-id="23085-127">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)