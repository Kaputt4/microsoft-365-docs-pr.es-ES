---
title: Ejecutar una prueba de detección en un dispositivo para comprobar que se ha incorporado correctamente a Microsoft Defender para endpoint
description: Ejecute el script de prueba de detección en un dispositivo recién incorporado al servicio Microsoft Defender para endpoints para comprobar que se ha agregado correctamente.
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ec9aa659decd6815b00c9d80b2281fd8386bd082
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61163199"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint recién incorporado

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- Windows 11
- Versiones Windows 10 compatibles
- Windows Server 2012 R2
- Windows Server 2016
- Windows server, versión 1803
- Windows Server 2019
- Windows Server 2022
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Cuando agregas un dispositivo al servicio Microsoft Defender para endpoints para la administración, también se denomina dispositivos de incorporación. La incorporación permite a los dispositivos notificar señales sobre su estado de mantenimiento al servicio.

Asegurarse o comprobar que un dispositivo se ha agregado correctamente al servicio es un paso fundamental en todo el proceso de implementación. Asegura que se están administrando todos los dispositivos esperados. 

## <a name="verify-microsoft-defender-for-endpoint-onboarding-of-a-device-using-a-powershell-detection-test"></a>Comprobar microsoft defender para la incorporación de puntos de conexión de un dispositivo mediante una prueba de detección de PowerShell

Ejecute el siguiente script de PowerShell en un dispositivo recién incorporado para comprobar que está informando correctamente al servicio Defender for Endpoint.

1. Cree una carpeta: 'C:\test-MDATP-test'.
2. Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:

   1. Vaya a **Inicio** y escriba **cmd**.

   1. Haga clic con el **botón secundario en Símbolo del sistema** y seleccione Ejecutar como **administrador**.

      ![Window menú Inicio que apunta a Ejecutar como administrador.](images/run-as-admin.png)

3. En el símbolo del sistema, copie y ejecute el siguiente comando:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

La ventana símbolo del sistema se cerrará automáticamente. Si se realiza correctamente, la prueba de detección se marcará como completada y aparecerá una nueva alerta en el portal del dispositivo incorporado en unos 10 minutos.

## <a name="related-topics"></a>Temas relacionados

- [incorporar dispositivos Windows](configure-endpoints.md)
- [Servidores integrados](configure-server-endpoints.md)
- [Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
