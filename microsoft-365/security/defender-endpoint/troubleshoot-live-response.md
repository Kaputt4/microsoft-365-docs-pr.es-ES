---
title: Solucionar problemas de respuesta en directo de ATP de Microsoft Defender
description: Solucionar problemas que pueden surgir al usar la respuesta en directo en ATP de Microsoft Defender
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
ms.openlocfilehash: 62525548be777a3187cea5ed4be622ac9d42079b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183828"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a>Solucionar problemas de respuesta en directo de Microsoft Defender para puntos de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

En esta página se proporcionan pasos detallados para solucionar problemas de respuesta en directo.

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a>No se puede tener acceso al archivo durante las sesiones de respuesta en directo
Si al intentar realizar una acción durante una sesión de respuesta en directo, se produce un mensaje de error que indica que no se puede tener acceso al archivo, deberá seguir los pasos siguientes para solucionar el problema.

1. Copie el siguiente fragmento de código de script y guárdelo como un archivo PS1:

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


2. Agregue el script a la biblioteca de respuestas en directo.
3. Ejecute el script con un parámetro: la ruta de acceso del archivo que se va a copiar.
4. Vaya a la carpeta TEMP.
5. Ejecute la acción que desea realizar en el archivo copiado.

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a>Retrasos o sesiones de respuesta en directo lentas durante las conexiones iniciales
La respuesta en directo aprovecha el registro del sensor defender para puntos de conexión con el servicio WNS en Windows. Si tiene problemas de conectividad con la respuesta en directo, confirme los siguientes detalles:
1. `notify.windows.com` no está bloqueado en el entorno. Para obtener más información, vea [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).
2. WpnService (Windows Push Notifications System Service) no está deshabilitado.

Consulte los artículos siguientes para comprender completamente el comportamiento y los requisitos del servicio WpnService:
- [Información general Notification Services Windows Push (WNS)](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [Configuraciones de proxy y firewall de empresa para admitir el tráfico WNS](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [Intervalos ip públicos del Servicio de notificaciones de inserción de Microsoft (MPNS)](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

