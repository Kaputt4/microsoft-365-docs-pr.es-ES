---
title: Recopilar registros de soporte técnico en Microsoft Defender para endpoint mediante respuesta en directo
description: Obtenga información sobre cómo recopilar registros mediante la respuesta en directo para solucionar problemas de Puntos de conexión de Microsoft Defender
keywords: support, log, collect, troubleshoot, live response, liveanalyzer, analyzer, live, response
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 138b532e7786a3d142c3cbbe68f668a4b0e05591
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64472581"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a>Recopilar registros de soporte técnico en Microsoft Defender para endpoint mediante respuesta en directo


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)


Al ponerse en contacto con el soporte técnico, es posible que se le pida que proporcione el paquete de salida de la herramienta Analizador de cliente de Microsoft Defender para endpoint.

En este tema se proporcionan instrucciones sobre cómo ejecutar la herramienta mediante Live Response.

1. Descargue y obtenga los scripts necesarios disponibles desde el sub-directorio "Herramientas" del Analizador de cliente de [Microsoft Defender para](https://aka.ms/BetaMDEAnalyzer) endpoints. <br>
Por ejemplo, para obtener el sensor básico y los registros de estado del dispositivo, captura ".. \Tools\MDELiveAnalyzer.ps1".<br>
Si también necesita registros de soporte técnico de Antivirus de Defender (MpSupportFiles.cab), vaya a buscar ".. \Tools\MDELiveAnalyzerAV.ps1" 

2. Inicie una [sesión de respuesta en](live-response.md#initiate-a-live-response-session-on-a-device) directo en el equipo que necesita investigar.

3. Seleccione **Upload archivo a la biblioteca**.

   :::image type="content" source="images/upload-file.png" alt-text="El archivo de carga" lightbox="images/upload-file.png":::

4. Seleccione **Elegir archivo**.

   :::image type="content" source="images/choose-file.png" alt-text="Botón elegir archivo-1" lightbox="images/choose-file.png":::

5. Seleccione el archivo descargado denominado MDELiveAnalyzer.ps1 y, a continuación, haga clic en **Confirmar**

   :::image type="content" source="images/analyzer-file.png" alt-text="Botón elegir archivo-2" lightbox="images/analyzer-file.png":::

6. Mientras sigue en la sesión de LiveResponse, use los comandos siguientes para ejecutar el analizador y recopilar el archivo de resultados:

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
    ```

    [![Imagen de comandos.](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)

> [!NOTE]
>
> - La versión preliminar más reciente de MDEClientAnalyzer se puede descargar aquí: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer).
>
> - El script LiveAnalyzer descarga el paquete de solución de problemas en el equipo de destino desde: https://mdatpclientanalyzer.blob.core.windows.net.
>
>   Si no puede permitir que el equipo llegue a la dirección URL anterior, cargue MDEClientAnalyzerPreview.zip archivo en la biblioteca antes de ejecutar el script LiveAnalyzer:
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
>   ```
>
> - Para obtener más información sobre la recopilación de datos localmente en una máquina en caso de que la máquina no se comunique con Microsoft Defender para servicios en la nube de endpoints o no aparezca en el portal de Microsoft Defender para endpoints como se esperaba, consulte [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls).
> 
> - Tal como se describe en [Ejemplos](live-response-command-examples.md) de comandos de respuesta en directo, es posible que desee usar el símbolo "&" al final del comando para recopilar registros como una acción en segundo plano:
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
