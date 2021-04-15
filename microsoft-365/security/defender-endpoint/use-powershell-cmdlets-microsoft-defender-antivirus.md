---
title: Usar cmdlets de PowerShell para configurar y ejecutar MICROSOFT Defender AV
description: En Windows 10, puedes usar cmdlets de PowerShell para ejecutar exámenes, actualizar inteligencia de seguridad y cambiar la configuración en Antivirus de Microsoft Defender.
keywords: scan, línea de comandos, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: d6fb8dc510e004fa88bf99583cc2cc33ae8c63bb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765304"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="09b94-104">Usar cmdlets de PowerShell para configurar y administrar Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="09b94-104">Use PowerShell cmdlets to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="09b94-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="09b94-105">**Applies to:**</span></span>

- [<span data-ttu-id="09b94-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="09b94-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="09b94-107">Puede usar PowerShell para realizar varias funciones en Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="09b94-107">You can use PowerShell to perform various functions in Windows Defender.</span></span> <span data-ttu-id="09b94-108">Al igual que el símbolo del sistema o la línea de comandos, PowerShell es un shell de línea de comandos basado en tareas y un lenguaje de scripting diseñado especialmente para la administración del sistema.</span><span class="sxs-lookup"><span data-stu-id="09b94-108">Similar to the command prompt or command line, PowerShell is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="09b94-109">Puede leer más sobre él en el centro [de PowerShell en MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="09b94-109">You can read more about it at the [PowerShell hub on MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).</span></span>

<span data-ttu-id="09b94-110">Para obtener una lista de los cmdlets y sus funciones y parámetros disponibles, consulte el [tema Cmdlets de](/powershell/module/defender) Defender.</span><span class="sxs-lookup"><span data-stu-id="09b94-110">For a list of the cmdlets and their functions and available parameters, see the [Defender cmdlets](/powershell/module/defender) topic.</span></span>

<span data-ttu-id="09b94-111">Los cmdlets de PowerShell son más útiles en entornos de Windows Server que no dependen de una interfaz gráfica de usuario (GUI) para configurar software.</span><span class="sxs-lookup"><span data-stu-id="09b94-111">PowerShell cmdlets are most useful in Windows Server environments that don't rely on a graphical user interface (GUI) to configure software.</span></span>

> [!NOTE]
> <span data-ttu-id="09b94-112">Los cmdlets de PowerShell no deben usarse como reemplazo de una infraestructura de administración de directivas de red completa, como [Microsoft Endpoint Configuration Manager,](/configmgr) [la](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Consola de administración de directivas de grupo o las plantillas ADMX de directiva de grupo antivirus de [Microsoft Defender.](https://www.microsoft.com/download/101445)</span><span class="sxs-lookup"><span data-stu-id="09b94-112">PowerShell cmdlets should not be used as a replacement for a full network policy management infrastructure, such as [Microsoft Endpoint Configuration Manager](/configmgr), [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), or [Microsoft Defender Antivirus Group Policy ADMX templates](https://www.microsoft.com/download/101445).</span></span>

<span data-ttu-id="09b94-113">Los cambios realizados con PowerShell afectarán a la configuración local en el punto de conexión donde se implementan o realizan los cambios.</span><span class="sxs-lookup"><span data-stu-id="09b94-113">Changes made with PowerShell will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="09b94-114">Esto significa que las implementaciones de directivas con directiva de grupo, Microsoft Endpoint Configuration Manager o Microsoft Intune pueden sobrescribir los cambios realizados con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09b94-114">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with PowerShell.</span></span>

<span data-ttu-id="09b94-115">Puede configurar [qué opciones se pueden invalidar localmente con invalidaciones de directiva local.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="09b94-115">You can [configure which settings can be overridden locally with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="09b94-116">PowerShell normalmente se instala en la carpeta `%SystemRoot%\system32\WindowsPowerShell` .</span><span class="sxs-lookup"><span data-stu-id="09b94-116">PowerShell is typically installed under the folder `%SystemRoot%\system32\WindowsPowerShell`.</span></span>

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a><span data-ttu-id="09b94-117">Usar cmdlets de PowerShell antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="09b94-117">Use Microsoft Defender Antivirus PowerShell cmdlets</span></span>

1. <span data-ttu-id="09b94-118">En la barra de búsqueda de Windows, escriba **powershell**.</span><span class="sxs-lookup"><span data-stu-id="09b94-118">In the Windows search bar, type **powershell**.</span></span>
2. <span data-ttu-id="09b94-119">Seleccione **Windows PowerShell** de los resultados para abrir la interfaz.</span><span class="sxs-lookup"><span data-stu-id="09b94-119">Select **Windows PowerShell** from the results to open the interface.</span></span>
3. <span data-ttu-id="09b94-120">Escriba el comando de PowerShell y los parámetros.</span><span class="sxs-lookup"><span data-stu-id="09b94-120">Enter the PowerShell command and any parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="09b94-121">Es posible que necesite abrir PowerShell en modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="09b94-121">You may need to open PowerShell in administrator mode.</span></span> <span data-ttu-id="09b94-122">Haga clic con el botón secundario en el elemento del menú Inicio, haga clic **en Ejecutar como administrador** y haga clic en Sí **en** el símbolo del sistema de permisos.</span><span class="sxs-lookup"><span data-stu-id="09b94-122">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span>

<span data-ttu-id="09b94-123">Para abrir la ayuda en línea para cualquiera de los cmdlets, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="09b94-123">To open online help for any of the cmdlets type the following:</span></span>

```PowerShell
Get-Help <cmdlet> -Online
```

<span data-ttu-id="09b94-124">Omita el `-online` parámetro para obtener ayuda almacenada localmente en caché.</span><span class="sxs-lookup"><span data-stu-id="09b94-124">Omit the `-online` parameter to get locally cached help.</span></span>

## <a name="related-topics"></a><span data-ttu-id="09b94-125">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="09b94-125">Related topics</span></span>

- [<span data-ttu-id="09b94-126">Temas de referencia para herramientas de administración y configuración</span><span class="sxs-lookup"><span data-stu-id="09b94-126">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="09b94-127">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="09b94-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="09b94-128">Microsoft Defender Antivirus Cmdlets</span><span class="sxs-lookup"><span data-stu-id="09b94-128">Microsoft Defender Antivirus Cmdlets</span></span>](/powershell/module/defender)