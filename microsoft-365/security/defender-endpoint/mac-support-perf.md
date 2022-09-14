---
title: Solución de problemas de rendimiento para Microsoft Defender para punto de conexión en macOS
description: Solución de problemas de rendimiento en Microsoft Defender para punto de conexión en macOS.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, performance
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: afb9955a73e62a2e35a2f0fe4942e970e3c6c29b
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67683173"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Solución de problemas de rendimiento para Microsoft Defender para punto de conexión en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión en macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

En este tema se proporcionan algunos pasos generales que se pueden usar para restringir los problemas de rendimiento relacionados con Microsoft Defender para punto de conexión en macOS.


En función de las aplicaciones que ejecute y de las características del dispositivo, puede experimentar un rendimiento poco óptimo al ejecutar Microsoft Defender para punto de conexión en macOS. En concreto, las aplicaciones o los procesos del sistema que acceden a muchos recursos a través de un intervalo de tiempo corto pueden provocar problemas de rendimiento en Microsoft Defender para punto de conexión en macOS.

>[!WARNING]
>Antes de comenzar, asegúrese de que otros productos de seguridad no se ejecutan actualmente en el dispositivo. Varios productos de seguridad pueden entrar en conflicto e afectar al rendimiento del host. 

## <a name="troubleshoot-performance-issues-using-real-time-protection-statistics"></a>Solución de problemas de rendimiento mediante estadísticas de protección en tiempo real
**Se aplica a:**
- Solo problemas de rendimiento relacionados con AV

La protección en tiempo real (RTP) es una característica de Defender para punto de conexión en macOS que supervisa y protege continuamente el dispositivo frente a amenazas. Consta de supervisión de archivos y procesos y otras heurísticas.

Los pasos siguientes se pueden usar para solucionar y mitigar estos problemas:

1. Deshabilite la protección en tiempo real mediante uno de los métodos siguientes y observe si el rendimiento mejora. Este enfoque ayuda a restringir si Microsoft Defender para punto de conexión en macOS está contribuyendo a los problemas de rendimiento.

      Si su organización no administra el dispositivo, la protección en tiempo real se puede deshabilitar mediante una de las siguientes opciones:

    - Desde la interfaz de usuario. Abra Microsoft Defender para punto de conexión en macOS y vaya a **Administrar configuración**.

      :::image type="content" source="images/mdatp-36-rtp.png" alt-text=" Página Administrar protección en tiempo real" lightbox="images/mdatp-36-rtp.png":::
      

    - Desde el terminal. Por motivos de seguridad, esta operación requiere elevación.

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      Si su organización administra el dispositivo, el administrador puede deshabilitar la protección en tiempo real mediante las instrucciones de [Establecimiento de preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md).

      Si el problema de rendimiento persiste mientras la protección en tiempo real está desactivada, el origen del problema podría ser el componente de detección y respuesta de puntos de conexión. En este caso, póngase en contacto con el servicio de atención al cliente para obtener más instrucciones y mitigación.

2. Abra Finder y vaya a **Utilidades de aplicaciones**\>. Abra **el Monitor de actividad** y analice qué aplicaciones usan los recursos del sistema. Entre los ejemplos típicos se incluyen los compiladores y los actualizadores de software.

3. Para buscar las aplicaciones que desencadenan la mayoría de los exámenes, puede usar estadísticas en tiempo real recopiladas por Defender para punto de conexión en Mac.

      > [!NOTE]
      > Esta característica está disponible en la versión 100.90.70 o posterior.
      Esta característica está habilitada de forma predeterminada en los canales **Dogfood** e **InsiderFast** . Si usa un canal de actualización diferente, esta característica se puede habilitar desde la línea de comandos:

      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      Esta característica requiere que se habilite la protección en tiempo real. Para comprobar el estado de la protección en tiempo real, ejecute el siguiente comando:

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    Compruebe que la entrada **de real_time_protection_enabled** es true. De lo contrario, ejecute el siguiente comando para habilitarlo:

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      Para recopilar estadísticas actuales, ejecute:

      ```bash
      mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
      ```

      > [!NOTE]
      > El uso de **--output json** (tenga en cuenta el guion doble) garantiza que el formato de salida esté listo para el análisis.
      La salida de este comando mostrará todos los procesos y su actividad de examen asociada.

4. En el sistema Mac, descargue el analizador de Python de ejemplo high_cpu_parser.py mediante el comando :

    ```bash
    curl -O https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    La salida de este comando debe ser similar a la siguiente:

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.
    mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in
    0s
    ```

5. A continuación, escriba los siguientes comandos:

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      La salida de la anterior es una lista de los principales colaboradores de los problemas de rendimiento. La primera columna es el identificador de proceso (PID), la segunda columna es el nombre del proceso de te y la última columna es el número de archivos escaneados, ordenados por impacto.

      Por ejemplo, la salida del comando será similar a la siguiente:

      ```output
        ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
        27432 None 76703
        73467 actool     1249
        73914 xcodebuild 1081
        73873 bash 1050
        27475 None 836
        1    launchd    407
        73468 ibtool     344
        549  telemetryd_v1   325
        4764 None 228
        125  CrashPlanService 164
      ```

      Para mejorar el rendimiento de Defender para punto de conexión en Mac, busque el que tenga el número más alto en la fila Total de archivos examinados y agréguele una exclusión. Para obtener más información, vea [Configurar y validar exclusiones de Defender para punto de conexión en macOS](mac-exclusions.md).

      > [!NOTE]
      > La aplicación almacena estadísticas en memoria y solo realiza un seguimiento de la actividad del archivo desde que se inició y se ha habilitado la protección en tiempo real. Los procesos que se iniciaron antes o durante períodos en los que la protección en tiempo real estaba desactivada no se cuentan. Además, solo se cuentan los eventos que desencadenaron exámenes.
      >
6. Configure Microsoft Defender para punto de conexión en macOS con exclusiones para los procesos o ubicaciones de disco que contribuyen a los problemas de rendimiento y vuelvan a habilitar la protección en tiempo real.

     Consulte [Configuración y validación de exclusiones para Microsoft Defender para punto de conexión en macOS](mac-exclusions.md) para obtener más información.


## <a name="troubleshoot-performance-issues-using-microsoft-defender-for-endpoint-client-analyzer"></a>Solución de problemas de rendimiento mediante Microsoft Defender para punto de conexión Analizador de cliente

**Se aplica a:**
- Problemas de rendimiento de todos los componentes disponibles de Defender para punto de conexión, como AV y EDR  

El Microsoft Defender para punto de conexión Client Analyzer (MDECA) puede recopilar seguimientos, registros e información de diagnóstico para solucionar problemas de rendimiento en [dispositivos incorporados](/microsoft-365/security/defender-endpoint/onboard-configure) en macOS.

> [!NOTE]
>- Los servicios de soporte al cliente (CSS) de Microsoft usan periódicamente la herramienta Microsoft Defender para punto de conexión Client Analyzer para recopilar información como direcciones IP, nombres de PC que le ayudarán a solucionar problemas que pueda estar experimentando. Microsoft Defender para punto de conexión. Para obtener más información sobre nuestra declaración de privacidad, consulte [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).
>- Como procedimiento recomendado general, se recomienda actualizar el [agente de Microsoft Defender para punto de conexión a la  versión](linux-whatsnew.md)  más reciente disponible y confirmar que el problema persiste antes de investigar más. 

Para ejecutar el analizador de cliente para solucionar problemas de rendimiento, consulte [Ejecución del analizador de cliente en macOS y Linux](run-analyzer-macos-linux.md).

>[!NOTE]
>En caso de que después de seguir los pasos anteriores, el problema de rendimiento persiste, póngase en contacto con el soporte técnico para obtener más instrucciones y mitigación. 


## <a name="see-also"></a>Vea también

- [Investigar problemas de estado del agente](health-status.md)
