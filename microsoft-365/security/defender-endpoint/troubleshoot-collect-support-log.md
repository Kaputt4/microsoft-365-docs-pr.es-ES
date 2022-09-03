---
title: Recopilación de registros de soporte técnico en Microsoft Defender para punto de conexión mediante respuesta dinámica
description: Obtenga información sobre cómo recopilar registros mediante la respuesta activa para solucionar problemas de Microsoft Defender para punto de conexión
keywords: support, log, collect, troubleshooting, live response, liveanalyzer, analyzer, live, response
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
ms.openlocfilehash: 4c9afb98ff4e9cc5b78a15c798da1451487ff744
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67584185"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a>Recopilación de registros de soporte técnico en Microsoft Defender para punto de conexión mediante respuesta dinámica


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)


Al ponerse en contacto con el soporte técnico, es posible que se le pida que proporcione el paquete de salida de la herramienta Microsoft Defender para punto de conexión Client Analyzer.

En este tema se proporcionan instrucciones sobre cómo ejecutar la herramienta a través de Live Response.

1. Descargue y capture los scripts necesarios disponibles desde el subdirectorio "Herramientas" del [analizador de cliente de Microsoft Defender para punto de conexión](https://aka.ms/BetaMDEAnalyzer). <br>
Por ejemplo, para obtener los registros básicos de estado del dispositivo y del sensor, capture ".. \Tools\MDELiveAnalyzer.ps1".<br>
Si también necesita registros de soporte técnico de Antivirus de Defender (MpSupportFiles.cab), busque ".. \Tools\MDELiveAnalyzerAV.ps1" 

2. Inicie una [sesión de live response](live-response.md#initiate-a-live-response-session-on-a-device) en la máquina que necesita investigar.

3. Seleccione **Cargar archivo en la biblioteca**.

   :::image type="content" source="images/upload-file.png" alt-text="El archivo de carga" lightbox="images/upload-file.png":::

4. Seleccione **Elegir archivo**.

   :::image type="content" source="images/choose-file.png" alt-text="Botón elegir archivo-1" lightbox="images/choose-file.png":::

5. Seleccione el archivo descargado denominado MDELiveAnalyzer.ps1 y haga clic en **Confirmar**.

   :::image type="content" source="images/analyzer-file.png" alt-text="Botón elegir archivo-2" lightbox="images/analyzer-file.png":::

6. Mientras sigue en la sesión de LiveResponse, use los comandos siguientes para ejecutar el analizador y recopilar el archivo de resultados:

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
    ```

    [![Imagen de los comandos.](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)

> [!NOTE]
>
> - La versión preliminar más reciente de MDEClientAnalyzer se puede descargar aquí: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer).
>
> - El script LiveAnalyzer descarga el paquete de solución de problemas en la máquina de destino desde: https://mdatpclientanalyzer.blob.core.windows.net.
>
>   Si no puede permitir que la máquina alcance la dirección URL anterior, cargue MDEClientAnalyzerPreview.zip archivo en la biblioteca antes de ejecutar el script LiveAnalyzer:
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
>   ```
>
> - Para obtener más información sobre la recopilación de datos localmente en una máquina en caso de que la máquina no se comunique con Microsoft Defender para punto de conexión servicios en la nube o no aparezca en Microsoft Defender para punto de conexión portal según lo previsto, consulte Comprobación de la [conectividad de cliente con Microsoft Defender para punto de conexión direcciones URL del servicio](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls).
> 
> - Como se describe en [Ejemplos de comandos de respuesta](live-response-command-examples.md) dinámica, es posible que desee usar el símbolo "&" al final del comando para recopilar registros como una acción en segundo plano:
>   ```console
>   Run MDELiveAnalyzer.ps1&
>   ```


## <a name="see-also"></a>Vea también
- [Información general del Analizador de clientes](overview-client-analyzer.md)
- [Descargar y ejecutar el Analizador de clientes](download-client-analyzer.md)
- [Ejecutar el Analizador de clientes en Windows](run-analyzer-windows.md)
- [Ejecutar el Analizador de clientes en macOS o Linux](run-analyzer-macos-linux.md)
- [ Recopilación de datos para solucionar problemas avanzados en Windows](data-collection-analyzer.md)
- [Comprender el informe HTML del analizador](analyzer-report.md)
