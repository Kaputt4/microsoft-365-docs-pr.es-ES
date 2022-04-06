---
title: Configurar el proxy de dispositivo y la configuración de conexión a Internet
description: Configure la configuración Microsoft Defender para punto de conexión proxy e Internet para habilitar la comunicación con el servicio en la nube.
keywords: configuración, proxy, Internet, conectividad a Internet, configuración, configuración de proxy, netsh, winhttp, servidor proxy
search.product: eADQiWindows 10XVcnh
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
- m365-initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: cf68afff79a2d719435e9df3d53400584f162618
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507353"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Configurar las opciones de proxy de dispositivo y de conectividad a Internet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

El sensor Defender for Endpoint requiere que Microsoft Windows HTTP (WinHTTP) informe de los datos del sensor y se comunique con el servicio Defender for Endpoint. El sensor de Defender for Endpoint incrustado se ejecuta en el contexto del sistema mediante la cuenta LocalSystem. El sensor usa Microsoft Windows HTTP Services (WinHTTP) para habilitar la comunicación con el servicio en la nube defender para endpoint.

> [!TIP]
> Para las organizaciones que usan servidores proxy de reenvío como puerta de enlace a Internet, puede usar la protección de red para investigar los eventos de conexión que se producen detrás [de los servidores proxy de reenvío](investigate-behind-proxy.md).

La configuración de WinHTTP es independiente de la configuración de proxy de exploración de Windows Internet (WinINet) (vea [WinINet vs. WinHTTP](/windows/win32/wininet/wininet-vs-winhttp)). Solo puede detectar un servidor proxy mediante los siguientes métodos de detección:

- Métodos de detección automática:

  - Proxy transparente
  
  - Protocolo de detección automática de proxy web (WPAD)

    > [!NOTE]
    > Si usas proxy transparente o WPAD en la topología de red, no necesitas opciones de configuración especiales. Para obtener más información sobre las exclusiones de url de extremo de Defender en el proxy, vea [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

- Configuración del proxy estático manual:

  - Configuración basada en el registro
  
  - WinHTTP configurado mediante el comando netsh: adecuado solo para escritorios en una topología estable (por ejemplo: un escritorio en una red corporativa detrás del mismo proxy)

> [!NOTE]
> Los servidores proxy EDR y antivirus de Defender se pueden establecer de forma independiente.  En las secciones siguientes, tenga en cuenta estas distinciones.

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Configurar manualmente el servidor proxy mediante un proxy estático basado en el registro

Configure un proxy estático basado en el Registro para el sensor Defender for Endpoint detection and response (EDR) para informar de los datos de diagnóstico y comunicarse con Defender for Endpoint services si un equipo no tiene permiso para conectarse a Internet.

> [!NOTE]
> Al usar esta opción en Windows 10, Windows 11 o Windows Server 2019 o Windows Server 2022, se recomienda tener la siguiente compilación (o posterior) y el paquete acumulativo de actualizaciones acumulativas:
>
> - Windows 11
> - Windows 10, versión 1809 o Windows Server 2019 o Windows Server 2022 :<https://support.microsoft.com/kb/5001384>
> - Windows 10, versión 1909 -<https://support.microsoft.com/kb/4601380>
> - Windows 10, versión 2004 -<https://support.microsoft.com/kb/4601382>
> - Windows 10, versión 20H2 -<https://support.microsoft.com/kb/4601382>
>
> Estas actualizaciones mejoran la conectividad y la confiabilidad del canal CnC (comando y control).

El proxy estático se puede configurar a través de la directiva de grupo (GP), tanto la configuración de los valores de directiva de grupo debe configurarse en el servidor proxy para usar EDR. La directiva de grupo está disponible en Plantillas administrativas.

- **Plantillas administrativas > Windows componentes >** recopilación de datos y versiones preliminares > configurar el uso de proxy autenticado para el servicio de telemetría y experiencia del usuario conectado.

  Estabilizelo **en Habilitado** y seleccione **Deshabilitar el uso de proxy autenticado**.

  :::image type="content" source="images/atp-gpo-proxy1.png" alt-text="Panel de directiva de grupo de estado de configuración1" lightbox="images/atp-gpo-proxy1.png":::

- **Plantillas administrativas > Windows componentes > recopilación** de datos y versiones preliminares > Configurar la telemetría y las experiencias de usuario conectadas:

  Configure el proxy.

  :::image type="content" source="images/atp-gpo-proxy2.png" alt-text="Panel de directiva de grupo estado de configuración2" lightbox="images/atp-gpo-proxy2.png":::


| Directiva de grupo | Clave del Registro | Entrada del Registro | Valor |
|:---|:---|:---|:---|
| Configurar el uso de proxy autenticado para la experiencia del usuario conectado y el servicio de telemetría | `HKLM\Software\Policies\Microsoft\Windows\DataCollection` | `DisableEnterpriseAuthProxy` | 1 (REG_DWORD) |
| Configurar la telemetría y las experiencias de usuario conectados | `HKLM\Software\Policies\Microsoft\Windows\DataCollection` | `TelemetryProxyServer` | ```servername:port or ip:port``` <br> <br> Por ejemplo: ```10.0.0.6:8080``` (REG_SZ) |

## <a name="configure-a-static-proxy-for-microsoft-defender-antivirus"></a>Configurar un proxy estático para Antivirus de Microsoft Defender

Antivirus de Microsoft Defender [protección entregada en la nube](cloud-protection-microsoft-defender-antivirus.md) proporciona protección automatizada casi instantánea contra amenazas nuevas y emergentes. Tenga en cuenta que la conectividad es necesaria para los [indicadores personalizados](manage-indicators.md) cuando Defender Antivirus es la solución antimalware activa. Por [EDR en modo de bloqueo](edr-in-block-mode.md) tiene una solución antimalware principal cuando se usa una solución que no es de Microsoft.

Configure el proxy estático mediante el directiva de grupo disponible en Plantillas administrativas:

1. **Plantillas administrativas > Windows componentes > Antivirus de Microsoft Defender > Definir servidor proxy para conectarse a la red**. 

2. Esta opción se **establece en Habilitado** y defina el servidor proxy. Tenga en cuenta que la dirección URL debe tener http:// o https://. Para obtener versiones compatibles para https://, vea [Administrar Antivirus de Microsoft Defender actualizaciones](manage-updates-baselines-microsoft-defender-antivirus.md).

   :::image type="content" source="images/proxy-server-mdav.png" alt-text="El servidor proxy para Antivirus de Microsoft Defender" lightbox="images/proxy-server-mdav.png":::

3. En la clave del Registro `HKLM\Software\Policies\Microsoft\Windows Defender`, la directiva establece el valor del Registro `ProxyServer` como REG_SZ. 

   El valor del Registro `ProxyServer` tiene el siguiente formato de cadena:

    ```text
    <server name or ip>:<port>

    For example: http://10.0.0.6:8080
    ```

> [!NOTE]
>
> Por motivos de resistencia y la naturaleza en tiempo real de la protección entregada en la nube, Antivirus de Microsoft Defender almacenará en caché el último proxy de trabajo conocido. Asegúrese de que la solución de proxy no realiza la inspección SSL. Esto interrumpirá la conexión en la nube segura. 
>
> Antivirus de Microsoft Defender usar el proxy estático para conectarse a Windows Update o Microsoft Update para descargar actualizaciones. En su lugar, usará un proxy de todo el sistema si está configurado para usar Windows Update, o el origen de actualización interno configurado de acuerdo con el orden [de reserva configurado](manage-protection-updates-microsoft-defender-antivirus.md). 
>
> Si es necesario, puede usar plantillas administrativas > Windows **componentes > Antivirus de Microsoft Defender > Definir configuración automática de proxy (.pac)** para conectarse a la red. Si necesita configurar configuraciones avanzadas con varios servidores proxy, use Plantillas administrativas **> Windows Componentes > Antivirus de Microsoft Defender >** Definir direcciones para omitir el servidor proxy e impedir que Antivirus de Microsoft Defender use un servidor proxy para esos destinos. 
>
> Puede usar PowerShell con el `Set-MpPreference` cmdlet para configurar estas opciones: 
>
> - ProxyBypass 
> - ProxyPacUrl 
> - ProxyServer 

> [!NOTE]
> Para usar el proxy correctamente, configure estas tres opciones de proxy diferentes:
>  - Microsoft Defender para punto de conexión (MDE)
>  - AV (Antivirus)
>  - Detección y respuesta de puntos de conexión (EDR)

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Configurar el servidor proxy manualmente mediante el comando netsh

Use netsh para configurar un proxy estático en todo el sistema.

> [!NOTE]
>
> - Esto afectará a todas las aplicaciones, incluidos los servicios de Windows que utilicen WinHTTP con el proxy predeterminado.</br>
> - Los equipos portátiles que cambian la topología (por ejemplo: de la oficina a la casa) no funcionan correctamente con el comando netsh. Use la configuración de proxy estático basada en el registro.

1. Abra un símbolo del sistema con privilegios elevados:
   1. Vaya a **Inicio** y escriba **cmd**.
   1. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente comando y presione **Entrar**:

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   Por ejemplo: `netsh winhttp set proxy 10.0.0.6:8080`

Para restablecer el servidor proxy winhttp, escriba el siguiente comando y presione **Entrar**:

```PowerShell
netsh winhttp reset proxy
```

Para obtener más información, vea [Sintaxis de comando Netsh, contextos y formatos](/windows-server/networking/technologies/netsh/netsh-contexts).

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a>Habilitar el acceso a Microsoft Defender para punto de conexión de servicio en el servidor proxy

De forma predeterminada, si un proxy o firewall bloquea todo el tráfico de forma predeterminada y solo permite dominios específicos, agregue los dominios enumerados en la hoja descargable a la lista de dominios permitidos.

En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas que la red debe poder conectar. Asegúrese de que no hay reglas de filtrado de red o firewall para denegar el acceso a estas direcciones URL. Opcional, es posible que deba crear una *regla de* permitir específicamente para ellos.

<br>

|Hoja de cálculo de la lista de dominios| Descripción|
|---|---|
|Microsoft Defender para punto de conexión url para clientes comerciales| Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo para clientes comerciales. <p> [Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Microsoft Defender para punto de conexión url de Gov/GCC/DoD | Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sos para clientes gov/GCC/DoD. <p> [Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

Si un servidor proxy o firewall tiene habilitada la detección HTTPS (inspección SSL), excluya los dominios que aparecen en la tabla anterior de la detección HTTPS.
En el firewall, abra todas las direcciones URL donde la columna de geografía es WW. Para las filas en las que la columna de geografía no es WW, abra las direcciones URL en la ubicación de datos específica. Para comprobar la configuración de la ubicación de datos, consulte [Verify data storage location and update data retention settings for Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/data-retention-settings).

> [!NOTE]
> Windows dispositivos que se ejecutan con la versión 1803 o necesidades anteriores`settings-win.data.microsoft.com`.  <br>
>
> Las direcciones URL que incluyen v20 solo son necesarias si Windows dispositivos que ejecutan la versión 1803 o posterior. Por ejemplo, es `us-v20.events.data.microsoft.com` necesario para un dispositivo Windows que ejecute la versión 1803 o posterior y se incorpore a la región de datos Storage ESTADOS UNIDOS.
>

Si un proxy o firewall bloquea el tráfico anónimo como sensor defender para el extremo y se conecta desde el contexto del sistema para asegurarse de que el tráfico anónimo está permitido en las direcciones URL enumeradas anteriormente.

> [!NOTE]
> Microsoft no proporciona un servidor proxy. Estas direcciones URL son accesibles a través del servidor proxy que configure.

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a>Microsoft Monitoring Agent (MMA): requisitos de proxy y firewall para versiones anteriores de Windows cliente o Windows server

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
> *Estos requisitos de conectividad se aplican a la Microsoft Defender para punto de conexión anterior de Windows Server 2016 y Windows Server 2012 R2 que requiere MMA. Las instrucciones para incorporar estos sistemas operativos con la nueva solución unificada se encuentran en [Onboard Windows servers](configure-server-endpoints.md) o migrar a la nueva solución unificada en escenarios de migración de [servidores en Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/server-migration).

> [!NOTE]
> Como solución basada en la nube, el intervalo IP puede cambiar. Se recomienda pasar a la configuración de resolución de DNS.

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a>Confirmar Microsoft Monitoring Agent url de servicio (MMA) 

 Consulte las siguientes instrucciones para eliminar el requisito de comodín (*) para su entorno específico al usar el Microsoft Monitoring Agent (MMA) para versiones anteriores de Windows.

1. Incorpore un sistema operativo anterior con el Microsoft Monitoring Agent (MMA) en Defender for Endpoint (para obtener más información, vea [Onboard previous versions of Windows on Defender for Endpoint and](https://go.microsoft.com/fwlink/p/?linkid=2010326) [Onboard Windows servers](configure-server-endpoints.md)).

2. Asegúrese de que el equipo se está informando correctamente en el portal Microsoft 365 Defender usuario.

3. Ejecute la herramienta TestCloudConnection.exe desde "C:\Program Files\Microsoft Monitoring Agent\Agent" para validar la conectividad y obtener las direcciones URL necesarias para su área de trabajo específica.

4. Compruebe la lista Microsoft Defender para punto de conexión direcciones URL para obtener la lista completa de requisitos para su región (consulte la hoja de cálculo de direcciones URL de [servicio](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).

   :::image type="content" source="images/admin-powershell.png" alt-text="El administrador de Windows PowerShell" lightbox="images/admin-powershell.png":::

Los caracteres comodín (\*) \*usados en los puntos de conexión de dirección URL .ods.opinsights.azure.com, \*\*.oms.opinsights.azure.com y .agentsvc.azure-automation.net pueden reemplazarse por el identificador de área de trabajo específico. El identificador de área de trabajo es específico de su entorno y área de trabajo. Puede encontrarse en la sección Incorporación del espacio empresarial en el portal Microsoft 365 Defender cliente.

El \*extremo de dirección URL .blob.core.windows.net se puede reemplazar por las direcciones URL mostradas en la sección "Regla de firewall: \*.blob.core.windows.net" de los resultados de la prueba.

> [!NOTE]
> En el caso de la incorporación mediante Microsoft Defender for Cloud, se pueden usar varias áreas de trabajo. Deberá realizar el procedimiento TestCloudConnection.exe en el equipo incorporado desde cada área de trabajo (para determinar si hay algún cambio en las direcciones URL *.blob.core.windows.net entre las áreas de trabajo).

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a>Comprobar la conectividad del cliente Microsoft Defender para punto de conexión direcciones URL de servicio

Compruebe que la configuración del proxy se completó correctamente. A continuación, WinHTTP puede detectar y comunicarse a través del servidor proxy del entorno y, a continuación, el servidor proxy permitirá el tráfico a las direcciones URL del servicio Defender for Endpoint.

1. Descargue la [Microsoft Defender para punto de conexión analizador de cliente](https://aka.ms/mdeanalyzer) en el equipo, donde se está ejecutando el sensor Defender for Endpoint. Para servidores de nivel inferior, use la última edición de vista previa disponible para descargar la [Microsoft Defender para punto de conexión analizador de cliente Beta](https://aka.ms/BetaMDEAnalyzer).

2. Extrae el contenido de MDEClientAnalyzer.zip en el dispositivo.

3. Abra un símbolo del sistema con privilegios elevados:
   1. Vaya a **Inicio** y escriba **cmd**.
   1. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

4. Escriba el siguiente comando y presione **Entrar**:

    ```PowerShell
    HardDrivePath\MDEClientAnalyzer.cmd
    ```

    Reemplace *HardDrivePath por* la ruta de acceso, donde se descargó la herramienta MDEClientAnalyzer. Por ejemplo:

    ```PowerShell
    C:\Work\tools\MDEClientAnalyzer\MDEClientAnalyzer.cmd
    ```

5. La herramienta crea y extrae *elMDEClientAnalyzerResult.zipen* la carpeta que se usará en *HardDrivePath*.

6. Abra *MDEClientAnalyzerResult.txt* y compruebe que ha realizado los pasos de configuración de proxy para habilitar la detección de servidores y el acceso a las direcciones URL de servicio.

   La herramienta comprueba la conectividad de las direcciones URL del servicio defender para puntos de conexión. Asegúrese de que el cliente de Defender for Endpoint está configurado para interactuar. La herramienta imprimirá los resultados en el archivo *MDEClientAnalyzerResult.txt* para cada dirección URL que se pueda usar potencialmente para comunicarse con los servicios de Defender for Endpoint. Por ejemplo:

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

Si alguna de las opciones de conectividad devuelve un estado (200), el cliente de Defender for Endpoint puede comunicarse con la dirección URL probada correctamente mediante este método de conectividad.

Pero si los resultados de la comprobación de conectividad indican un error, se mostrará un error HTTP (vea los códigos de estado HTTP). A continuación, puede usar las direcciones URL de la tabla que se muestra en Habilitar el acceso a las direcciones URL del servicio defender para puntos de conexión [en el servidor proxy](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server). Las direcciones URL disponibles para su uso dependerán de la región seleccionada durante el procedimiento de incorporación.

> [!NOTE]
> Las comprobaciones de conectividad en la nube de la herramienta Analizador de conectividad no son compatibles con la regla reducción de superficie de ataque Bloquear las creaciones de procesos que se originen a partir [de comandos PSExec y WMI](attack-surface-reduction-rules-reference.md#block-process-creations-originating-from-psexec-and-wmi-commands). Deberá deshabilitar temporalmente esta regla para ejecutar la herramienta de conectividad. Como alternativa, puede agregar temporalmente [exclusiones de ASR](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules) al ejecutar el analizador.
>
> Cuando telemetryProxyServer se establece en el Registro o a través de directiva de grupo, Defender for Endpoint se resaltó, no se puede obtener acceso al proxy definido.

## <a name="related-articles"></a>Artículos relacionados

- [Use directiva de grupo configuración para configurar y administrar Antivirus de Microsoft Defender](use-group-policy-microsoft-defender-antivirus.md)
- [incorporar dispositivos Windows](configure-endpoints.md)
- [Solucionar Microsoft Defender para punto de conexión problemas de incorporación](troubleshoot-onboarding.md)
