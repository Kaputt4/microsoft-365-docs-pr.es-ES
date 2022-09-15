---
title: Ejecute una prueba de detección en un dispositivo para comprobar que se ha incorporado correctamente a Microsoft Defender para punto de conexión
description: Ejecute el script de prueba de detección en un dispositivo incorporado recientemente al servicio Microsoft Defender para punto de conexión para comprobar que se ha agregado correctamente.
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
ms.date: 09/13/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 37d02195cc3acf9dfbdcae55ceb9534b6d68d722
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67727978"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>Ejecución de una prueba de detección en un dispositivo Microsoft Defender para punto de conexión recién incorporado

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- Windows 11
- Versiones de Windows 10 admitidas
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server, versión 1803
- Windows Server 2019
- Windows Server 2022
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Al agregar un dispositivo al servicio de Microsoft Defender para punto de conexión para la administración, esto también se denomina incorporación de dispositivos. La incorporación permite a los dispositivos notificar señales sobre su estado de mantenimiento al servicio.

Asegurarse o comprobar que un dispositivo se ha agregado al servicio correctamente es un paso fundamental en todo el proceso de implementación. Garantiza que se administran todos los dispositivos esperados. 

## <a name="verify-microsoft-defender-for-endpoint-onboarding-of-a-device-using-a-powershell-detection-test"></a>Comprobación Microsoft Defender para punto de conexión incorporación de un dispositivo mediante una prueba de detección de PowerShell

Ejecute el siguiente script de PowerShell en un dispositivo recién incorporado para comprobar que notifica correctamente al servicio Defender para punto de conexión.

1. Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:

   1. Vaya a **Inicio** y escriba **cmd**.

   1. Haga clic con el botón derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

      :::image type="content" source="images/run-as-admin.png" alt-text="El menú Inicio que apunta a Ejecutar como administrador" lightbox="images/run-as-admin.png":::
    
2. En el símbolo del sistema, copie y ejecute el siguiente comando:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

La ventana del símbolo del sistema se cerrará automáticamente. Si se ejecuta correctamente, aparecerá una nueva alerta en el portal del dispositivo incorporado en unos diez minutos.

## <a name="related-topics"></a>Temas relacionados

- [incorporar dispositivos Windows](configure-endpoints.md)
- [Incorporación de servidores](configure-server-endpoints.md)
- [Solución de problemas de incorporación de Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
