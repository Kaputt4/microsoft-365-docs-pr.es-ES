---
title: Configuración del proxy de dispositivo y la conexión a Internet
description: Configure el proxy de Microsoft Defender para punto de conexión y la configuración de Internet para habilitar la comunicación con el servicio en la nube.
keywords: configurar, proxy, Internet, conectividad a Internet, configuración, configuración de proxy, netsh, winhttp, servidor proxy
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 51f50014c5a937223ca2ada3f8bf0dac851f5e9a
ms.sourcegitcommit: 4f8200453d347de677461f27eb5a3802ce5cc888
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68543187"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Configurar las opciones de proxy de dispositivo y de conectividad a Internet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

El sensor de Defender para punto de conexión requiere HTTP de Microsoft Windows (WinHTTP) para informar de los datos del sensor y comunicarse con el servicio Defender para punto de conexión. El sensor incrustado de Defender para punto de conexión se ejecuta en el contexto del sistema mediante la cuenta LocalSystem.

> [!TIP]
> En el caso de las organizaciones que usan servidores proxy de reenvío como puerta de enlace a Internet, puede usar la protección de red para [investigar los eventos de conexión que se producen detrás de servidores proxy directos](investigate-behind-proxy.md).

La configuración de WinHTTP es independiente de la configuración del proxy de exploración de Windows Internet (WinINet) (vea [WinINet frente a WinHTTP](/windows/win32/wininet/wininet-vs-winhttp)). Solo puede detectar un servidor proxy mediante los métodos de detección siguientes:

- Métodos de detección automática:

  - Proxy transparente
  
  - Protocolo de detección automática de proxy web (WPAD)

    > [!NOTE]
    > Si usa el proxy transparente o WPAD en la topología de red, no necesita valores de configuración especiales. Para obtener más información sobre las exclusiones de direcciones URL de Defender para punto de conexión en el proxy, consulte [Habilitación del acceso a las direcciones URL del servicio Defender para punto de conexión en el servidor proxy](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).

- Configuración del proxy estático manual:

  - Configuración basada en el registro
  
  - WinHTTP configurado mediante el comando netsh: solo es adecuado para escritorios en una topología estable (por ejemplo, un escritorio en una red corporativa detrás del mismo proxy)

> [!NOTE]
> Los servidores proxy EDR y antivirus de Defender se pueden establecer de forma independiente.  En las secciones siguientes, tenga en cuenta esas distinciones.

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Configurar manualmente el servidor proxy mediante un proxy estático basado en el registro

Configure un proxy estático basado en el Registro para el sensor de detección y respuesta de Defender para punto de conexión (EDR) para informar de los datos de diagnóstico y comunicarse con los servicios de Defender para punto de conexión si un equipo no tiene permiso para conectarse a Internet.

> [!NOTE]
> Al usar esta opción en Windows 10, o Windows 11, o Windows Server 2019 o Windows Server 2022, se recomienda tener el siguiente paquete acumulativo de actualizaciones acumulativas y compilación (o posterior):
>
> - Windows 11
> - Windows 10, versión 1809 o Windows Server 2019 o Windows Server 2022:<https://support.microsoft.com/kb/5001384>
> - Windows 10, versión 1909:<https://support.microsoft.com/kb/4601380>
> - Windows 10, versión 2004:<https://support.microsoft.com/kb/4601382>
> - Windows 10, versión 20H2:<https://support.microsoft.com/kb/4601382>
>
> Estas actualizaciones mejoran la conectividad y confiabilidad del canal CnC (comando y control).

El proxy estático se puede configurar a través de la directiva de grupo (GP), ambos valores de directiva de grupo deben configurarse en el servidor proxy para usar EDR. La directiva de grupo está disponible en Plantillas administrativas.

- **Plantillas administrativas > componentes de Windows > compilaciones de recopilación de datos y versión preliminar > Configurar el uso del proxy autenticado para el servicio de telemetría y experiencia del usuario conectado**.

  Establézcalo **en Habilitado** y seleccione **Deshabilitar el uso del proxy autenticado**.

  :::image type="content" source="images/atp-gpo-proxy1.png" alt-text="Panel de estado directiva de grupo setting1" lightbox="images/atp-gpo-proxy1.png":::

- **Plantillas administrativas > componentes de Windows > recopilación de datos y compilaciones en versión preliminar > Configurar telemetría y experiencias de usuario conectadas**:

  Configure el proxy.

  :::image type="content" source="images/atp-gpo-proxy2.png" alt-text="Panel de estado directiva de grupo setting2" lightbox="images/atp-gpo-proxy2.png":::


| Directiva de grupo | Clave del Registro | Entrada del Registro | Valor |
|:---|:---|:---|:---|
| Configuración del uso de proxy autenticado para la experiencia del usuario conectado y el servicio de telemetría | `HKLM\Software\Policies\Microsoft\Windows\DataCollection` | `DisableEnterpriseAuthProxy` | 1 (REG_DWORD) |
| Configuración de telemetría y experiencias de usuario conectadas | `HKLM\Software\Policies\Microsoft\Windows\DataCollection` | `TelemetryProxyServer` | ```servername:port or ip:port``` <br> <br> Por ejemplo: ```10.0.0.6:8080``` (REG_SZ) |

> [!NOTE]
> Si usa la configuración "TelemetryProxyServer" en dispositivos que, de lo contrario, están **completamente sin conexión**, lo que significa que el sistema operativo no puede conectarse para la lista de revocación de certificados en línea o Windows Update, se recomienda agregar la configuración `PreferStaticProxyForHttpRequest` adicional del Registro con un valor de `1`.<br>
> La ubicación de la ruta de acceso del Registro principal para "PreferStaticProxyForHttpRequest" es "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"<br>
> El siguiente comando se puede usar para insertar el valor del Registro en la ubicación correcta:<br>
> ```reg add "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection" /v PreferStaticProxyForHttpRequest /t REG_DWORD /d 1 /f```<br>
> El valor del Registro anterior solo es aplicable a partir de MsSense.exe versión 10.8210.* y posteriores, o la versión 10.8049.* y posteriores (en Windows Server 2012R2/2016 con el agente unificado)



## <a name="configure-a-static-proxy-for-microsoft-defender-antivirus"></a>Configuración de un proxy estático para Microsoft Defender Antivirus

Microsoft Defender [protección antivirus entregada en la nube](cloud-protection-microsoft-defender-antivirus.md) proporciona protección casi instantánea y automatizada contra amenazas nuevas y emergentes. Tenga en cuenta que la conectividad es necesaria para [los indicadores personalizados](manage-indicators.md) cuando Antivirus de Defender es la solución antimalware activa. Para [EDR en modo de bloque](edr-in-block-mode.md) tiene una solución antimalware principal cuando se usa una solución que no es de Microsoft.

Configure el proxy estático mediante el directiva de grupo disponible en Plantillas administrativas:

1. **Plantillas administrativas > componentes de Windows > Microsoft Defender Antivirus > Definir servidor proxy para conectarse a la red**. 

2. Establézcalo en **Habilitado** y defina el servidor proxy. Tenga en cuenta que la dirección URL debe tener http:// o https://. Para ver las versiones admitidas para https://, consulte [Administrar actualizaciones de antivirus de Microsoft Defender](manage-updates-baselines-microsoft-defender-antivirus.md).

   :::image type="content" source="images/proxy-server-mdav.png" alt-text="Servidor proxy para Microsoft Defender Antivirus" lightbox="images/proxy-server-mdav.png":::

3. En la clave `HKLM\Software\Policies\Microsoft\Windows Defender`del Registro , la directiva establece el valor `ProxyServer` del Registro como REG_SZ. 

   El valor `ProxyServer` del Registro tiene el siguiente formato de cadena:

    ```text
    <server name or ip>:<port>

    For example: http://10.0.0.6:8080
    ```

> [!NOTE]
>
> Para fines de resistencia y la naturaleza en tiempo real de la protección entregada en la nube, Microsoft Defender Antivirus almacenará en caché el último proxy de trabajo conocido. Asegúrese de que la solución de proxy no realiza la inspección SSL. Esto interrumpirá la conexión segura a la nube. 
>
> Microsoft Defender Antivirus no usará el proxy estático para conectarse a Windows Update o Microsoft Update para descargar actualizaciones. En su lugar, usará un proxy de todo el sistema si está configurado para usar Windows Update o el origen de actualización interno configurado según el [orden de reserva configurado](manage-protection-updates-microsoft-defender-antivirus.md). 
>
> Si es necesario, puede usar **plantillas administrativas > componentes de Windows > Microsoft Defender Antivirus > Definir configuración automática de proxy (.pac)** para conectarse a la red. Si necesita configurar configuraciones avanzadas con varios servidores proxy, use **Plantillas administrativas > Componentes de Windows > Microsoft Defender Antivirus > Definir direcciones** para omitir el servidor proxy e impedir que Microsoft Defender Antivirus use un servidor proxy para esos destinos. 
>
> Puede usar PowerShell con el `Set-MpPreference` cmdlet para configurar estas opciones: 
>
> - ProxyBypass 
> - ProxyPacUrl 
> - ProxyServer 

> [!NOTE]
> Para usar el proxy correctamente, configure estos tres valores de proxy diferentes:
>  - Microsoft Defender para punto de conexión (MDE)
>  - AV (Antivirus)
>  - Detección y respuesta de puntos de conexión (EDR)

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Configuración manual del servidor proxy mediante el comando netsh

Use netsh para configurar un proxy estático en todo el sistema.

> [!NOTE]
>
> - Esto afectará a todas las aplicaciones, incluidos los servicios de Windows que utilicen WinHTTP con el proxy predeterminado.</br>

1. Abra un símbolo del sistema con privilegios elevados:
   1. Vaya a **Inicio** y escriba **cmd**.
   1. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente comando y presione **Entrar**:

   ```command prompt
   netsh winhttp set proxy <proxy>:<port>
   ```

   Por ejemplo: `netsh winhttp set proxy 10.0.0.6:8080`

Para restablecer el servidor proxy winhttp, escriba el siguiente comando y presione **Entrar**:

```command prompt
netsh winhttp reset proxy
```

Para obtener más información, vea [Sintaxis de comando Netsh, contextos y formatos](/windows-server/networking/technologies/netsh/netsh-contexts).

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a>Habilitación del acceso a direcciones URL de servicio de Microsoft Defender para punto de conexión en el servidor proxy

De forma predeterminada, si un proxy o firewall bloquea todo el tráfico de forma predeterminada y solo permite dominios específicos, agregue los dominios enumerados en la hoja descargable a la lista de dominios permitidos.

En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas que la red debe poder conectarse. Asegúrese de que no hay reglas de filtrado de red ni de firewall para denegar el acceso a estas direcciones URL. Opcional, es posible que tenga que crear una regla *de permiso* específicamente para ellos.

<br>

|Hoja de cálculo de la lista de dominios| Descripción|
|---|---|
|Microsoft Defender para punto de conexión lista de direcciones URL para clientes comerciales| Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo para clientes comerciales. <p> [Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx) <p> Tenga en cuenta que Microsoft Defender para punto de conexión Plan 1 y Plan 2 comparten las mismas direcciones URL del servicio proxy.
| Microsoft Defender para punto de conexión lista de direcciones URL de Gov/GCC/DoD | Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo para clientes de Gov/GCC/DoD. <p> [Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

Si un servidor proxy o firewall tiene habilitada la detección HTTPS (inspección SSL), excluya los dominios que aparecen en la tabla anterior de la detección HTTPS.
En el firewall, abra todas las direcciones URL donde la columna geography es WW. Para las filas en las que la columna geography no es WW, abra las direcciones URL a la ubicación de datos específica. Para comprobar la configuración de ubicación de datos, consulte [Comprobación de la ubicación del almacenamiento de datos y actualización de la configuración de retención de datos para Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/data-retention-settings).

> [!NOTE]
> Los dispositivos Windows que se ejecutan con la versión 1803 o versiones anteriores necesitan `settings-win.data.microsoft.com`.  <br>
>
> Las direcciones URL que incluyen v20 en ellas solo son necesarias si tiene dispositivos Windows que ejecutan la versión 1803 o posterior. Por ejemplo, `us-v20.events.data.microsoft.com` es necesario para un dispositivo Windows que ejecute la versión 1803 o posterior y se incorpore a la región DE ALMACENAMIENTO DE DATOS DE EE. UU.
>

Si un proxy o firewall bloquea el tráfico anónimo como sensor de Defender para punto de conexión y se conecta desde el contexto del sistema para asegurarse de que se permite el tráfico anónimo en las direcciones URL enumeradas anteriormente.

> [!NOTE]
> Microsoft no proporciona un servidor proxy. Estas direcciones URL son accesibles a través del servidor proxy que configure.

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a>Microsoft Monitoring Agent (MMA): requisitos de proxy y firewall para versiones anteriores del cliente Windows o Windows Server

La información de la lista de información de configuración de proxy y firewall es necesaria para comunicarse con el agente de Log Analytics (a menudo denominado Microsoft Monitoring Agent) para versiones anteriores de Windows, como Windows 7 SP1, Windows 8.1 y Windows Server 2008 R2*.

<br>

****

|Recurso del agente|Puertos|Dirección|Omitir la inspección HTTP|
|---|---|---|---|
|*.ods.opinsights.azure.com|Puerto 443|Salida|Yes|
|*.oms.opinsights.azure.com|Puerto 443|Salida|Yes|
|*.blob.core.windows.net|Puerto 443|Salida|Yes|
|*.azure-automation.net|Puerto 443|Salida|Yes|

> [!NOTE]
> *Estos requisitos de conectividad se aplican a la Microsoft Defender para punto de conexión anterior de Windows Server 2016 y Windows Server 2012 R2 que requiere MMA. Las instrucciones para incorporar estos sistemas operativos con la nueva solución unificada se encuentran en [Incorporación de servidores Windows](configure-server-endpoints.md) o migración a la nueva solución unificada [en escenarios de migración del servidor en Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/server-migration).

> [!NOTE]
> Como solución basada en la nube, el intervalo IP puede cambiar. Se recomienda pasar a la configuración de resolución de DNS.

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a>Confirmación de los requisitos de dirección URL del servicio Microsoft Monitoring Agent (MMA) 

 Consulte las instrucciones siguientes para eliminar el requisito de caracteres comodín (*) para su entorno específico al usar Microsoft Monitoring Agent (MMA) para versiones anteriores de Windows.

1. Incorporación de un sistema operativo anterior con Microsoft Monitoring Agent (MMA) a Defender para punto de conexión (para obtener más información, consulte [Incorporación de versiones anteriores de Windows on Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2010326) e [Incorporación de servidores Windows](configure-server-endpoints.md)).

2. Asegúrese de que la máquina informa correctamente en el portal de Microsoft 365 Defender.

3. Ejecute la herramienta TestCloudConnection.exe desde "C:\Archivos de programa\Microsoft Monitoring Agent\Agent" para validar la conectividad y obtener las direcciones URL necesarias para el área de trabajo específica.

4. Compruebe la lista de direcciones URL de Microsoft Defender para punto de conexión para obtener la lista completa de requisitos de su región (consulte la [hoja de cálculo](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx) direcciones URL del servicio).

   :::image type="content" source="images/admin-powershell.png" alt-text="El administrador de Windows PowerShell" lightbox="images/admin-powershell.png":::

Los caracteres comodín (\*) usados en \*los puntos de conexión de dirección URL .ods.opinsights.azure.com, \*.oms.opinsights.azure.com y \*.agentsvc.azure-automation.net se pueden reemplazar por el identificador de área de trabajo específico. El identificador del área de trabajo es específico del entorno y del área de trabajo. Se puede encontrar en la sección Incorporación del inquilino en el portal de Microsoft 365 Defender.

El \*punto de conexión de dirección URL .blob.core.windows.net se puede reemplazar por las direcciones URL que se muestran en la sección "Regla de firewall: \*.blob.core.windows.net" de los resultados de la prueba.

> [!NOTE]
> En el caso de la incorporación a través de Microsoft Defender for Cloud, se pueden usar varias áreas de trabajo. Tendrá que realizar el procedimiento de TestCloudConnection.exe en la máquina incorporada desde cada área de trabajo (para determinar si hay cambios en las direcciones URL *.blob.core.windows.net entre las áreas de trabajo).

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a>Comprobación de la conectividad de cliente con direcciones URL de servicio de Microsoft Defender para punto de conexión

Compruebe que la configuración del proxy se ha completado correctamente. A continuación, WinHTTP puede detectar y comunicarse a través del servidor proxy del entorno y, a continuación, el servidor proxy permitirá el tráfico a las direcciones URL del servicio Defender para punto de conexión.

1. Descargue la [herramienta Microsoft Defender para punto de conexión Client Analyzer](https://aka.ms/mdeanalyzer) en el equipo, donde se ejecuta el sensor de Defender para punto de conexión. En el caso de los servidores de nivel inferior, use la edición de versión preliminar más reciente disponible para descargar [Microsoft Defender para punto de conexión herramienta Del analizador de cliente beta](https://aka.ms/BetaMDEAnalyzer).

2. Extraiga el contenido de MDEClientAnalyzer.zip en el dispositivo.

3. Abra un símbolo del sistema con privilegios elevados:
   1. Vaya a **Inicio** y escriba **cmd**.
   1. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

4. Escriba el siguiente comando y presione **Entrar**:

    ```command prompt
    HardDrivePath\MDEClientAnalyzer.cmd
    ```

    Reemplace *HardDrivePath* por la ruta de acceso donde se descargó la herramienta MDEClientAnalyzer. Por ejemplo:

    ```command prompt
    C:\Work\tools\MDEClientAnalyzer\MDEClientAnalyzer.cmd
    ```

5. La herramienta crea y extrae el archivo *MDEClientAnalyzerResult.zip* de la carpeta que se va a usar en *HardDrivePath*.

6. Abra *MDEClientAnalyzerResult.txt* y compruebe que ha realizado los pasos de configuración del proxy para habilitar la detección de servidores y el acceso a las direcciones URL del servicio.

   La herramienta comprueba la conectividad de las direcciones URL de servicio de Defender para punto de conexión. Asegúrese de que el cliente de Defender para punto de conexión está configurado para interactuar. La herramienta imprimirá los resultados en el archivo *deMDEClientAnalyzerResult.txt* para cada dirección URL que se pueda usar potencialmente para comunicarse con los servicios de Defender para punto de conexión. Por ejemplo:

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

Si alguna de las opciones de conectividad devuelve un estado (200), el cliente de Defender para punto de conexión puede comunicarse con la dirección URL probada correctamente mediante este método de conectividad.

Pero si los resultados de la comprobación de conectividad indican un error, se mostrará un error HTTP (vea los códigos de estado HTTP). A continuación, puede usar las direcciones URL de la tabla que se muestra en [Habilitar el acceso a las direcciones URL del servicio Defender para punto de conexión en el servidor proxy](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server). Las direcciones URL disponibles para su uso dependerán de la región seleccionada durante el procedimiento de incorporación.

> [!NOTE]
> Las comprobaciones de conectividad en la nube de la herramienta Analizador de conectividad no son compatibles con la regla de reducción de superficie [expuesta a ataques Las creaciones de procesos de bloqueo se originaron a partir de comandos PSExec y WMI](attack-surface-reduction-rules-reference.md#block-process-creations-originating-from-psexec-and-wmi-commands). Tendrá que deshabilitar temporalmente esta regla para ejecutar la herramienta de conectividad. Como alternativa, puede agregar temporalmente [exclusiones de ASR](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules) al ejecutar el analizador.
>
> Cuando TelemetryProxyServer se establece en el Registro o a través de directiva de grupo, Defender para punto de conexión se revertirá, no podrá acceder al proxy definido.

## <a name="related-articles"></a>Artículos relacionados

- [Usar directiva de grupo configuración para configurar y administrar Microsoft Defender Antivirus](use-group-policy-microsoft-defender-antivirus.md)
- [incorporar dispositivos Windows](configure-endpoints.md)
- [Solución de problemas de incorporación de Microsoft Defender para punto de conexión](troubleshoot-onboarding.md)
