---
title: Recopilar registros de soporte técnico en Microsoft Defender para puntos de conexión mediante respuesta en directo
description: Obtenga información sobre cómo recopilar registros mediante la respuesta en directo para solucionar problemas de Microsoft Defender para puntos de conexión
keywords: support, log, collect, troubleshoot, live response, liveanalyzer, analyzer, live, response
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
ms.openlocfilehash: 8b7fe8f0973cabfb5f5268be28ac606dfc4c6387
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183722"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a>Recopilar registros de soporte técnico en Microsoft Defender para endpoint mediante respuesta en directo 


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Al ponerse en contacto con el soporte técnico, es posible que se le pida que proporcione el paquete de salida de la herramienta Analizador de cliente de Microsoft Defender para endpoint.

En este tema se proporcionan instrucciones sobre cómo ejecutar la herramienta mediante Live Response.

1. Descargar el script adecuado
    * Solo los registros del sensor de cliente de Microsoft Defender [ para endpoint:LiveAnalyzer.ps1 script](https://aka.ms/MDELiveAnalyzer).
      - Tamaño aproximado del paquete de resultados: ~100Kb 
    *  Sensor de cliente de Microsoft Defender para endpoint y registros antivirus: [LiveAnalyzer+MDAV.ps1 script](https://aka.ms/MDELiveAnalyzerAV).
       - Tamaño aproximado del paquete de resultados: ~10Mb 
 
2.  Inicie una [sesión de respuesta en](live-response.md#initiate-a-live-response-session-on-a-device) directo en el equipo que necesita investigar.

3.  Seleccione **Cargar archivo en la biblioteca**.

    ![Imagen del archivo de carga](images/upload-file.png)

4. Seleccione **Elegir archivo**.

    ![Imagen del botón elegir archivo1](images/choose-file.png)

5. Seleccione el archivo descargado denominado MDELiveAnalyzer.ps1 y, a continuación, haga clic en **Confirmar**


   ![Imagen del botón elegir archivo2](images/analyzer-file.png)


6. Mientras sigue en la sesión de LiveResponse, use los comandos siguientes para ejecutar el analizador y recopilar el archivo de resultados:

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
    ```

    ![Imagen de comandos](images/analyzer-commands.png)


>[!NOTE]
> - La versión preliminar más reciente de MDEClientAnalyzer se puede descargar aquí: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) .
> 
> - El script LiveAnalyzer descarga el paquete de solución de problemas en el equipo de destino desde: https://mdatpclientanalyzer.blob.core.windows.net .
> 
>   Si no puede permitir que el equipo llegue a la dirección URL anterior, cargue MDEClientAnalyzerPreview.zip archivo en la biblioteca antes de ejecutar el script LiveAnalyzer:
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
>   ```
> 
> - Para obtener más información sobre la recopilación de datos localmente en una máquina en caso de que la máquina no se comunique con Microsoft Defender para los servicios en la nube de endpoints o no aparezca en el portal de Microsoft Defender para endpoints como se esperaba, consulte [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls).
