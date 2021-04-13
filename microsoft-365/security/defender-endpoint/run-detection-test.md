---
title: Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint recién incorporado
description: Ejecute el script de detección en un dispositivo recién incorporado para comprobar que está incorporado correctamente al servicio de Microsoft Defender para endpoints.
keywords: prueba de detección, detección, powershell, script, comprobación, incorporación, Microsoft Defender para incorporación de puntos de conexión, clientes, servidores, prueba
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 89b8ac7d99cfcd4c5e5e647e5ba54e14184ef0bd
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688122"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint recién incorporado 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- Versiones compatibles de Windows 10
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server, versión 1803
- Windows Server, 2019
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Ejecute el siguiente script de PowerShell en un dispositivo recién incorporado para comprobar que está informando correctamente al servicio Defender for Endpoint.

1. Cree una carpeta: 'C:\test-MDATP-test'.
2. Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:

   1. Vaya a **Inicio** y escriba **cmd**.

   1. Haga clic con el **botón secundario en Símbolo del sistema** y seleccione Ejecutar como **administrador**.

      ![Menú Inicio de ventana que apunta a Ejecutar como administrador](images/run-as-admin.png)

3. En el símbolo del sistema, copie y ejecute el siguiente comando:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference= 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

La ventana símbolo del sistema se cerrará automáticamente. Si se realiza correctamente, la prueba de detección se marcará como completada y aparecerá una nueva alerta en el portal del dispositivo incorporado en aproximadamente 10 minutos.

## <a name="related-topics"></a>Temas relacionados
- [Incorporar dispositivos Windows 10 mediante la directiva de grupo](configure-endpoints.md)
- [Servidores integrados](configure-server-endpoints.md)
- [Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
