---
title: Detectar y bloquear aplicaciones potencialmente no deseadas con Microsoft Defender para Endpoint en Linux
description: Detectar y bloquear aplicaciones potencialmente no deseadas (PUA) con Microsoft Defender para endpoint en Linux.
keywords: microsoft, defender, atp, linux, pua, pus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9631fc2eb1cb791f48f107482474d1bb8e2fd62b
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903863"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="f13bb-104">Detectar y bloquear aplicaciones potencialmente no deseadas con Microsoft Defender para Endpoint en Linux</span><span class="sxs-lookup"><span data-stu-id="f13bb-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f13bb-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f13bb-105">**Applies to:**</span></span>
- [<span data-ttu-id="f13bb-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f13bb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f13bb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f13bb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f13bb-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f13bb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f13bb-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="f13bb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="f13bb-110">La característica de protección de aplicaciones potencialmente no deseadas (PUA) de Defender para Endpoint para Linux puede detectar y bloquear archivos PUA en puntos de conexión de la red.</span><span class="sxs-lookup"><span data-stu-id="f13bb-110">The potentially unwanted application (PUA) protection feature in Defender for Endpoint for Linux can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="f13bb-111">Estas aplicaciones no se consideran virus, malware u otros tipos de amenazas, pero pueden realizar acciones en puntos de conexión que afecten negativamente a su rendimiento o uso.</span><span class="sxs-lookup"><span data-stu-id="f13bb-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="f13bb-112">PUA también puede hacer referencia a aplicaciones que se consideran de mala reputación.</span><span class="sxs-lookup"><span data-stu-id="f13bb-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="f13bb-113">Estas aplicaciones pueden aumentar el riesgo de que la red se infecte con malware, hacer que las infecciones de malware sean más difíciles de identificar y pueden desperdiciar recursos de TI en la limpieza de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f13bb-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="f13bb-114">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="f13bb-114">How it works</span></span>

<span data-ttu-id="f13bb-115">Defender para Endpoint para Linux puede detectar e informar de archivos PUA.</span><span class="sxs-lookup"><span data-stu-id="f13bb-115">Defender for Endpoint for Linux can detect and report PUA files.</span></span> <span data-ttu-id="f13bb-116">Cuando se configura en modo de bloqueo, los archivos PUA se mueven a la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="f13bb-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="f13bb-117">Cuando se detecta una PUA en un punto de conexión, Defender for Endpoint para Linux mantiene un registro de la infección en el historial de amenazas.</span><span class="sxs-lookup"><span data-stu-id="f13bb-117">When a PUA is detected on an endpoint, Defender for Endpoint for Linux keeps a record of the infection in the threat history.</span></span> <span data-ttu-id="f13bb-118">El historial se puede visualizar desde el portal del Centro de seguridad de Microsoft Defender o a través de la herramienta `mdatp` de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f13bb-118">The history can be visualized from the Microsoft Defender Security Center portal or through the `mdatp` command-line tool.</span></span> <span data-ttu-id="f13bb-119">El nombre de la amenaza contendrá la palabra "Application".</span><span class="sxs-lookup"><span data-stu-id="f13bb-119">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="f13bb-120">Configurar la protección de LA PUA</span><span class="sxs-lookup"><span data-stu-id="f13bb-120">Configure PUA protection</span></span>

<span data-ttu-id="f13bb-121">La protección de PUA en Defender para Endpoint para Linux se puede configurar de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="f13bb-121">PUA protection in Defender for Endpoint for Linux can be configured in one of the following ways:</span></span>

- <span data-ttu-id="f13bb-122">**Desactivado:** la protección de LA PUA está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="f13bb-122">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="f13bb-123">**Auditoría:** los archivos PUA se notifican en los registros del producto, pero no en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="f13bb-123">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="f13bb-124">No se almacena ningún registro de la infección en el historial de amenazas y el producto no toma ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="f13bb-124">No record of the infection is stored in the threat history and no action is taken by the product.</span></span>
- <span data-ttu-id="f13bb-125">**Bloquear:** los archivos PUA se notifican en los registros del producto y en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="f13bb-125">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="f13bb-126">Un registro de la infección se almacena en el historial de amenazas y el producto toma medidas.</span><span class="sxs-lookup"><span data-stu-id="f13bb-126">A record of the infection is stored in the threat history and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="f13bb-127">De forma predeterminada, la protección pua está configurada en **modo auditoría.**</span><span class="sxs-lookup"><span data-stu-id="f13bb-127">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="f13bb-128">Puede configurar cómo se controlan los archivos PUA desde la línea de comandos o desde la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="f13bb-128">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="f13bb-129">Use la herramienta de línea de comandos para configurar la protección pua:</span><span class="sxs-lookup"><span data-stu-id="f13bb-129">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="f13bb-130">En Terminal, ejecute el siguiente comando para configurar la protección pua:</span><span class="sxs-lookup"><span data-stu-id="f13bb-130">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="f13bb-131">Use la consola de administración para configurar la protección pua:</span><span class="sxs-lookup"><span data-stu-id="f13bb-131">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="f13bb-132">En su empresa, puede configurar la protección de PUA desde una consola de administración, como Puppet o Ansible, de forma similar a la configuración de otros productos.</span><span class="sxs-lookup"><span data-stu-id="f13bb-132">In your enterprise, you can configure PUA protection from a management console, such as Puppet or Ansible, similarly to how other product settings are configured.</span></span> <span data-ttu-id="f13bb-133">Para obtener más información, consulta la sección Configuración del [tipo](linux-preferences.md#threat-type-settings) de amenaza del artículo Establecer preferencias [para Defender para Endpoint para Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="f13bb-133">For more information, see the [Threat type settings](linux-preferences.md#threat-type-settings) section of the [Set preferences for Defender for Endpoint for Linux](linux-preferences.md) article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f13bb-134">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="f13bb-134">Related articles</span></span>

- [<span data-ttu-id="f13bb-135">Establecer preferencias para Defender para Endpoint para Linux</span><span class="sxs-lookup"><span data-stu-id="f13bb-135">Set preferences for Defender for Endpoint for Linux</span></span>](linux-preferences.md)
