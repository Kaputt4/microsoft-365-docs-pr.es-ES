---
title: Solucionar problemas de respuesta en directo de Microsoft Defender para puntos de conexión
description: Solucionar problemas que pueden surgir al usar la respuesta en directo en Microsoft Defender para endpoint
keywords: solucionar problemas de respuesta en directo, live, response, locked, file
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 99a52188dd5f6eca2f8368aa3c114d0bfb950b10
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844159"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a><span data-ttu-id="0b411-104">Solucionar problemas de respuesta en directo de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="0b411-104">Troubleshoot Microsoft Defender for Endpoint live response issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0b411-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0b411-105">**Applies to:**</span></span>
- [<span data-ttu-id="0b411-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0b411-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0b411-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b411-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0b411-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0b411-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0b411-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="0b411-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="0b411-110">En esta página se proporcionan pasos detallados para solucionar problemas de respuesta en directo.</span><span class="sxs-lookup"><span data-stu-id="0b411-110">This page provides detailed steps to troubleshoot live response issues.</span></span>

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a><span data-ttu-id="0b411-111">No se puede tener acceso al archivo durante las sesiones de respuesta en directo</span><span class="sxs-lookup"><span data-stu-id="0b411-111">File cannot be accessed during live response sessions</span></span>
<span data-ttu-id="0b411-112">Si al intentar realizar una acción durante una sesión de respuesta en directo, se produce un mensaje de error que indica que no se puede tener acceso al archivo, deberá seguir los pasos siguientes para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="0b411-112">If while trying to take an action during a live response session, you encounter an error message stating that the file can't be accessed, you'll need to use the steps below to address the issue.</span></span>

1. <span data-ttu-id="0b411-113">Copie el siguiente fragmento de código de script y guárdelo como un archivo PS1:</span><span class="sxs-lookup"><span data-stu-id="0b411-113">Copy the following script code snippet and save it as a PS1 file:</span></span>

    ```
    $copied_file_path=$args[0] 
    $action=Copy-Item $copied_file_path -Destination $env:TEMP -PassThru -ErrorAction silentlyContinue
        
    if ($action){
         Write-Host "You copied the file specified in $copied_file_path to $env:TEMP Succesfully"
    }
    
    else{
        Write-Output "Error occoured while trying to copy a file, details:"
        Write-Output  $error[0].exception.message
 
    }
    ```


2. <span data-ttu-id="0b411-114">Agregue el script a la biblioteca de respuestas en directo.</span><span class="sxs-lookup"><span data-stu-id="0b411-114">Add the script to the live response library.</span></span>
3. <span data-ttu-id="0b411-115">Ejecute el script con un parámetro: la ruta de acceso del archivo que se va a copiar.</span><span class="sxs-lookup"><span data-stu-id="0b411-115">Run the script with one parameter: the file path of the file to be copied.</span></span>
4. <span data-ttu-id="0b411-116">Vaya a la carpeta TEMP.</span><span class="sxs-lookup"><span data-stu-id="0b411-116">Navigate to your TEMP folder.</span></span>
5. <span data-ttu-id="0b411-117">Ejecute la acción que desea realizar en el archivo copiado.</span><span class="sxs-lookup"><span data-stu-id="0b411-117">Run the action you wanted to take on the copied file.</span></span>

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a><span data-ttu-id="0b411-118">Retrasos o sesiones de respuesta en directo lentas durante las conexiones iniciales</span><span class="sxs-lookup"><span data-stu-id="0b411-118">Slow live response sessions or delays during initial connections</span></span>
<span data-ttu-id="0b411-119">La respuesta en directo aprovecha el registro del sensor defender para puntos de conexión con el servicio WNS en Windows.</span><span class="sxs-lookup"><span data-stu-id="0b411-119">Live response leverages Defender for Endpoint sensor registration with WNS service in Windows.</span></span> <span data-ttu-id="0b411-120">Si tiene problemas de conectividad con la respuesta en directo, confirme los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="0b411-120">If you are having connectivity issues with live response, confirm the following details:</span></span>
1. <span data-ttu-id="0b411-121">`notify.windows.com` no está bloqueado en el entorno.</span><span class="sxs-lookup"><span data-stu-id="0b411-121">`notify.windows.com` is not blocked in your environment.</span></span> <span data-ttu-id="0b411-122">Para obtener más información, vea [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="0b411-122">For more information, see, [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>
2. <span data-ttu-id="0b411-123">WpnService (Windows del sistema de notificaciones de inserción) no está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="0b411-123">WpnService (Windows Push Notifications System Service) is not disabled.</span></span>

<span data-ttu-id="0b411-124">Consulte los artículos siguientes para comprender completamente el comportamiento y los requisitos del servicio WpnService:</span><span class="sxs-lookup"><span data-stu-id="0b411-124">Refer to the articles below to fully understand the WpnService service behavior and requirements:</span></span>
- [<span data-ttu-id="0b411-125">Windows Introducción Notification Services inserción (WNS)</span><span class="sxs-lookup"><span data-stu-id="0b411-125">Windows Push Notification Services (WNS) overview</span></span>](/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [<span data-ttu-id="0b411-126">Enterprise Configuraciones de firewall y proxy para admitir tráfico de WNS</span><span class="sxs-lookup"><span data-stu-id="0b411-126">Enterprise Firewall and Proxy Configurations to Support WNS Traffic</span></span>](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [<span data-ttu-id="0b411-127">Intervalos ip públicos del Servicio de notificaciones de inserción de Microsoft (MPNS)</span><span class="sxs-lookup"><span data-stu-id="0b411-127">Microsoft Push Notifications Service (MPNS) Public IP ranges</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

