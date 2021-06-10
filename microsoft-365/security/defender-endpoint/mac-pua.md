---
title: Detectar y bloquear aplicaciones potencialmente no deseadas con Microsoft Defender para Endpoint en Mac
description: Detectar y bloquear aplicaciones potencialmente no deseadas (PUA) con Microsoft Defender en endpoint para Mac.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, pua, pus
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2d32dd96cd506ebf1752e48d2b7c66208b1abc11
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934542"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="833f8-104">Detectar y bloquear aplicaciones potencialmente no deseadas con Microsoft Defender para endpoint en macOS</span><span class="sxs-lookup"><span data-stu-id="833f8-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="833f8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="833f8-105">**Applies to:**</span></span>
- [<span data-ttu-id="833f8-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="833f8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="833f8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="833f8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="833f8-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="833f8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="833f8-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="833f8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="833f8-110">La característica de protección de aplicaciones potencialmente no deseadas (PUA) en Microsoft Defender para endpoint en macOS puede detectar y bloquear archivos PUA en puntos de conexión de la red.</span><span class="sxs-lookup"><span data-stu-id="833f8-110">The potentially unwanted application (PUA) protection feature in Microsoft Defender for Endpoint on macOS can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="833f8-111">Estas aplicaciones no se consideran virus, malware u otros tipos de amenazas, pero pueden realizar acciones en puntos de conexión que afecten negativamente a su rendimiento o uso.</span><span class="sxs-lookup"><span data-stu-id="833f8-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="833f8-112">PUA también puede hacer referencia a aplicaciones que se consideran de mala reputación.</span><span class="sxs-lookup"><span data-stu-id="833f8-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="833f8-113">Estas aplicaciones pueden aumentar el riesgo de que la red se infecte con malware, hacer que las infecciones de malware sean más difíciles de identificar y pueden desperdiciar recursos de TI en la limpieza de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="833f8-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="833f8-114">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="833f8-114">How it works</span></span>

<span data-ttu-id="833f8-115">Microsoft Defender para endpoint en macOS puede detectar e informar de archivos PUA.</span><span class="sxs-lookup"><span data-stu-id="833f8-115">Microsoft Defender for Endpoint on macOS can detect and report PUA files.</span></span> <span data-ttu-id="833f8-116">Cuando se configura en modo de bloqueo, los archivos PUA se mueven a la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="833f8-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="833f8-117">Cuando se detecta una PUA en un punto de conexión, Microsoft Defender para Endpoint en macOS presenta una notificación al usuario, a menos que se hayan deshabilitado las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="833f8-117">When a PUA is detected on an endpoint, Microsoft Defender for Endpoint on macOS presents a notification to the user, unless notifications have been disabled.</span></span> <span data-ttu-id="833f8-118">El nombre de la amenaza contendrá la palabra "Application".</span><span class="sxs-lookup"><span data-stu-id="833f8-118">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="833f8-119">Configurar la protección de LA PUA</span><span class="sxs-lookup"><span data-stu-id="833f8-119">Configure PUA protection</span></span>

<span data-ttu-id="833f8-120">La protección de PUA en Microsoft Defender para endpoint en macOS se puede configurar de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="833f8-120">PUA protection in Microsoft Defender for Endpoint on macOS can be configured in one of the following ways:</span></span>

- <span data-ttu-id="833f8-121">**Desactivado:** la protección de LA PUA está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="833f8-121">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="833f8-122">**Auditoría:** los archivos PUA se notifican en los registros del producto, pero no en Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="833f8-122">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="833f8-123">No se presenta ninguna notificación al usuario y el producto no hace ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="833f8-123">No notification is presented to the user and no action is taken by the product.</span></span>
- <span data-ttu-id="833f8-124">**Bloquear:** los archivos PUA se notifican en los registros del producto y en Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="833f8-124">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="833f8-125">El usuario recibe una notificación y el producto toma una acción.</span><span class="sxs-lookup"><span data-stu-id="833f8-125">The user is presented with a notification and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="833f8-126">De forma predeterminada, la protección pua está configurada en **modo auditoría.**</span><span class="sxs-lookup"><span data-stu-id="833f8-126">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="833f8-127">Puede configurar cómo se controlan los archivos PUA desde la línea de comandos o desde la consola de administración.</span><span class="sxs-lookup"><span data-stu-id="833f8-127">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="833f8-128">Use la herramienta de línea de comandos para configurar la protección pua:</span><span class="sxs-lookup"><span data-stu-id="833f8-128">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="833f8-129">En Terminal, ejecute el siguiente comando para configurar la protección pua:</span><span class="sxs-lookup"><span data-stu-id="833f8-129">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="833f8-130">Use la consola de administración para configurar la protección pua:</span><span class="sxs-lookup"><span data-stu-id="833f8-130">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="833f8-131">En su empresa, puede configurar la protección de PUA desde una consola de administración, como JAMF o Intune, de forma similar a la configuración de otros productos.</span><span class="sxs-lookup"><span data-stu-id="833f8-131">In your enterprise, you can configure PUA protection from a management console, such as JAMF or Intune, similarly to how other product settings are configured.</span></span> <span data-ttu-id="833f8-132">Para obtener más información, consulta la sección Configuración del [tipo](mac-preferences.md#threat-type-settings) de amenaza del tema Establecer preferencias [para Microsoft Defender para Endpoint en macOS.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="833f8-132">For more information, see the [Threat type settings](mac-preferences.md#threat-type-settings) section of the [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md) topic.</span></span>

## <a name="related-topics"></a><span data-ttu-id="833f8-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="833f8-133">Related topics</span></span>

- [<span data-ttu-id="833f8-134">Establecer preferencias para Microsoft Defender para endpoint en macOS</span><span class="sxs-lookup"><span data-stu-id="833f8-134">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>](mac-preferences.md)
