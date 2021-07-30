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
ms.openlocfilehash: a6be4282c2388f8a3aff3cd91bb8385f712bdea3
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "53648908"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a>Solucionar problemas de respuesta en directo de Microsoft Defender para puntos de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

En esta página se proporcionan pasos detallados para solucionar problemas de respuesta en directo.

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a>No se puede tener acceso al archivo durante las sesiones de respuesta en directo

Si al intentar realizar una acción durante una sesión de respuesta en directo, se produce un mensaje de error que indica que no se puede tener acceso al archivo, deberá seguir los pasos siguientes para solucionar el problema.

1. Copie el siguiente fragmento de código de script y guárdelo como un archivo PS1:

    ```powershell
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

2. Agregue el script a la biblioteca de respuestas en directo.
3. Ejecute el script con un parámetro: la ruta de acceso del archivo que se va a copiar.
4. Vaya a la carpeta TEMP.
5. Ejecute la acción que desea realizar en el archivo copiado.

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a>Retrasos o sesiones de respuesta en directo lentas durante las conexiones iniciales

La respuesta en directo aprovecha el registro del sensor defender para puntos de conexión con el servicio WNS en Windows. Si tiene problemas de conectividad con la respuesta en directo, confirme los siguientes detalles:

1. `notify.windows.com` no está bloqueado en el entorno. Para obtener más información, vea [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).
2. WpnService (Windows del sistema de notificaciones de inserción) no está deshabilitado.

Consulte los artículos siguientes para comprender completamente el comportamiento y los requisitos del servicio WpnService:

- [Windows Introducción Notification Services inserción (WNS)](/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [Enterprise Configuraciones de firewall y proxy para admitir tráfico de WNS](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [Intervalos ip públicos del Servicio de notificaciones de inserción de Microsoft (MPNS)](https://www.microsoft.com/download/details.aspx?id=44535)
