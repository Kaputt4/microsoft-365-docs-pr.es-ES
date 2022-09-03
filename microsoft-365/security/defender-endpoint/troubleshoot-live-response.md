---
title: Solución de problemas de Microsoft Defender para punto de conexión respuesta activa
description: Solución de problemas que pueden surgir al usar la respuesta activa en Microsoft Defender para punto de conexión
keywords: solución de problemas de respuesta en vivo, en directo, respuesta, bloqueado, archivo
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.subservice: mde
ms.openlocfilehash: fa266b94dd6f3a8972fd08ddb3a3d473fed4997e
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67580561"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a>Solución de problemas de Microsoft Defender para punto de conexión respuesta activa

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

En esta página se proporcionan pasos detallados para solucionar problemas de respuesta en vivo.

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a>No se puede acceder al archivo durante las sesiones de respuesta en directo

Si al intentar realizar una acción durante una sesión de respuesta activa, encuentra un mensaje de error que indica que no se puede acceder al archivo, deberá seguir los pasos siguientes para solucionar el problema.

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

2. Agregue el script a la biblioteca de respuestas dinámicas.
3. Ejecute el script con un parámetro: la ruta de acceso del archivo que se va a copiar.
4. Vaya a la carpeta TEMP.
5. Ejecute la acción que quería realizar en el archivo copiado.

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a>Sesiones de respuesta dinámica lentas o retrasos durante las conexiones iniciales

La respuesta en vivo aprovecha el registro del sensor de Defender para punto de conexión con el servicio WNS en Windows. Si tiene problemas de conectividad con la respuesta en vivo, confirme los detalles siguientes:

1. WpnService (Servicio del sistema de notificaciones push de Windows) no está deshabilitado.
2. La conectividad de WpnService con la nube de WNS no está deshabilitada a través de la directiva de grupo o la configuración de MDM. ["Desactivar el uso de la red de notificaciones"](/windows/client-management/mdm/policy-csp-notifications) no debe establecerse en "1".

Consulte los artículos siguientes para comprender completamente el comportamiento y los requisitos del servicio WpnService:

- [Introducción a Windows Push Notification Services (WNS)](/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [Configuraciones de firewall y proxy de empresa para admitir el tráfico de WNS](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [Intervalos de direcciones IP públicas de Microsoft Push Notifications Service (MPNS)](https://www.microsoft.com/download/details.aspx?id=44535)
