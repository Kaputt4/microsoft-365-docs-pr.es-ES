---
title: Configurar el proxy de dispositivo y la configuración de conexión a Internet
description: Configure la configuración de Microsoft Defender para proxy de extremo e Internet para habilitar la comunicación con el servicio en la nube.
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 42f21f27e30cc4a2bc4af5a2ecefd07c7353d96a
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "60240229"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Configurar las opciones de proxy de dispositivo y de conectividad a Internet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

El sensor Defender for Endpoint requiere que Microsoft Windows HTTP (WinHTTP) informe de los datos del sensor y se comunique con el servicio Defender for Endpoint.

El sensor de Defender for Endpoint incrustado se ejecuta en el contexto del sistema mediante la cuenta LocalSystem. El sensor usa Microsoft Windows HTTP Services (WinHTTP) para habilitar la comunicación con el servicio en la nube de Defender for Endpoint.

> [!TIP]
> Para las organizaciones que usan servidores proxy de reenvío como puerta de enlace a Internet, puede usar la protección de red para investigar los eventos de conexión que se producen detrás [de servidores proxy de reenvío.](investigate-behind-proxy.md)

La configuración de WinHTTP es independiente de la configuración de proxy de exploración de Windows Internet (WinINet) y solo puede detectar un servidor proxy mediante los siguientes métodos de detección:

- Métodos de detección automática:

  - Proxy transparente
  
  - Protocolo de detección automática de proxy web (WPAD)

    > [!NOTE]
    > Si usas proxy transparente o WPAD en la topología de red, no necesitas opciones de configuración especiales. Para obtener más información sobre las exclusiones de url de extremo de Defender en el proxy, vea Habilitar el acceso a las direcciones URL del servicio defender para puntos de conexión [en el servidor proxy.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

- Configuración del proxy estático manual:

  - Configuración basada en el registro
  
  - WinHTTP configurado mediante el comando netsh: adecuado solo para escritorios en una topología estable (por ejemplo: un escritorio en una red corporativa detrás del mismo proxy)

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Configurar manualmente el servidor proxy mediante un proxy estático basado en el registro

Configure un proxy estático basado en el Registro para el sensor Defender for Endpoint detection and response (EDR) para informar de datos de diagnóstico y comunicarse con Defender for Endpoint services si un equipo no tiene permiso para conectarse a Internet.

> [!NOTE]
> Al usar esta opción en Windows 10, Windows 11, Windows Server 2019 o Windows Server 2022, se recomienda tener la siguiente compilación (o posterior) y el paquete acumulativo de actualizaciones acumulativas:
>
> - Windows 11
> - Windows 10, versión 1809 o Windows Server 2019 o Windows Server 2022 :<https://support.microsoft.com/kb/5001384>
> - Windows 10, versión 1909 -<https://support.microsoft.com/kb/4601380>
> - Windows 10, versión 2004 -<https://support.microsoft.com/kb/4601382>
> - Windows 10, versión 20H2 -<https://support.microsoft.com/kb/4601382>
>
> Estas actualizaciones mejoran la conectividad y la confiabilidad del canal CnC (comando y control).

El proxy estático también se puede configurar a través de la directiva de grupo (GP). La directiva de grupo se puede encontrar aquí:

- **Plantillas administrativas > Windows componentes >** recopilación de datos y versiones preliminares > Configurar el uso de proxy autenticado para el servicio de telemetría y experiencia del usuario conectado.

  Estabilizelo **en Habilitado** y seleccione **Deshabilitar el uso de proxy autenticado.**

  ![Imagen de configuración de directiva de grupo1.](images/atp-gpo-proxy1.png)

- **Plantillas administrativas > Windows componentes > recopilación** de datos y compilaciones de vista previa > Configurar la telemetría y las experiencias de usuario conectadas:

  Configurar el servidor proxy

  ![Imagen de configuración de directiva de grupo2.](images/atp-gpo-proxy2.png)


| Directiva de grupo | Clave del Registro | Entrada del Registro | Valor |
|:---|:---|:---|:---|
| Configurar el uso de proxy autenticado para la experiencia del usuario conectado y el servicio de telemetría | `HKLM\Software\Policies\Microsoft\Windows\DataCollection` | `DisableEnterpriseAuthProxy` | 1 (REG_DWORD) |
| Configurar la telemetría y las experiencias de usuario conectados | `HKLM\Software\Policies\Microsoft\Windows\DataCollection` | `TelemetryProxyServer` | ```http://servername or ip:port``` <br> <br> Por ejemplo: ```http://10.0.0.6:8080``` (REG_SZ) |

## <a name="configure-a-static-proxy-for-microsoft-defender-antivirus"></a>Configurar un proxy estático para Antivirus de Microsoft Defender

Antivirus de Microsoft Defender protección [entregada en la nube](cloud-protection-microsoft-defender-antivirus.md) proporciona protección automatizada casi instantánea contra amenazas nuevas y emergentes. Tenga en cuenta que la conectividad es necesaria para [los indicadores personalizados](manage-indicators.md) cuando Defender Antivirus es la solución antimalware activa; y para [EDR en modo de bloqueo](edr-in-block-mode.md) incluso cuando se usa una solución que no es microsoft como la solución antimalware principal.

Configure el proxy estático mediante la directiva de grupo que se encuentra aquí:

1. **Plantillas administrativas > Windows componentes > Antivirus de Microsoft Defender > Definir servidor proxy para conectarse a la red**. 

2. Esta opción se **establece en Habilitado** y defina el servidor proxy. Tenga en cuenta que la dirección URL debe tener http:// o https://. Para obtener versiones compatibles para https://, vea [Manage Antivirus de Microsoft Defender updates](manage-updates-baselines-microsoft-defender-antivirus.md).

   :::image type="content" source="images/proxy-server-mdav.png" alt-text="Servidor proxy para Antivirus de Microsoft Defender.":::

3. En la clave del  `HKLM\Software\Policies\Microsoft\Windows Defender` Registro, la directiva establece el valor del  `ProxyServer`   Registro como REG_SZ. 

   El valor del  `ProxyServer`   Registro tiene el siguiente formato de cadena:

    ```text
    <server name or ip>:<port>

    For example: http://10.0.0.6:8080
    ```

> [!NOTE]
>
> Por motivos de resistencia y la naturaleza en tiempo real de la protección entregada en la nube, Antivirus de Microsoft Defender almacenará en caché el último proxy de trabajo conocido. Asegúrese de que la solución de proxy no realiza la inspección SSL, ya que esto interrumpirá la conexión en la nube segura. 
>
> Antivirus de Microsoft Defender usar el proxy estático para conectarse a Windows Update o Microsoft Update para descargar actualizaciones. En su lugar, usará un proxy para todo el sistema si está configurado para usar Windows Update o el origen de actualización interno configurado según el orden de reserva [configurado.](manage-protection-updates-microsoft-defender-antivirus.md) 
>
> Si es necesario, puede usar Plantillas administrativas > Windows Componentes > Antivirus de Microsoft Defender > Definir configuración automática **de proxy (.pac)** para conectarse a la red si necesita configurar configuraciones avanzadas con varios servidores proxy, Use Plantillas administrativas > Windows Componentes **> Antivirus de Microsoft Defender >** Definir direcciones para omitir el servidor proxy para evitar que Antivirus de Microsoft Defender use un servidor proxy para esos destinos. 
>
> También puede usar PowerShell con el `Set-MpPreference` cmdlet para configurar estas opciones: 
>
> - ProxyBypass 
> - ProxyPacUrl 
> - ProxyServer 

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Configurar el servidor proxy manualmente mediante el comando netsh

Use netsh para configurar un proxy estático en todo el sistema.

> [!NOTE]
>
> - Esto afectará a todas las aplicaciones, incluidos los servicios de Windows que utilicen WinHTTP con el proxy predeterminado.</br>
> - Los portátiles que cambian la topología (por ejemplo: de la oficina a la casa) no funcionan correctamente con netsh. Use la configuración de proxy estático basada en el registro.

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

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a>Habilitar el acceso a las direcciones URL del servicio de punto de conexión de Microsoft Defender en el servidor proxy

Si un servidor proxy o firewall bloquea todo el tráfico de forma predeterminada y permite únicamente el acceso a dominios específicos, agregue los dominios que aparecen en la hoja descargable a la lista de dominios permitidos.

En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse. Asegúrese de que no hay reglas de filtrado de red o firewall que denieguen el acceso *a* estas direcciones URL, o puede que necesite crear una regla de permitido específicamente para ellas.

<br>

**** 
|Hoja de cálculo de la lista de dominios|Descripción|
|---|---|
|![Imagen digital de la hoja de cálculo de direcciones URL de Microsoft Defender para puntos de conexión.](images/mdatp-urls.png)|Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo. <p> [Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)|
|

Si un servidor proxy o firewall tiene habilitada la detección HTTPS (inspección SSL), excluya los dominios que aparecen en la tabla anterior de la detección HTTPS.
En el firewall, abra todas las direcciones URL donde la columna de geografía es WW. Para las filas en las que la columna de geografía no es WW, abra las direcciones URL en la ubicación de datos específica. Para comprobar la configuración de ubicación de datos, vea [Verify data storage location and update data retention settings for Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/data-retention-settings).

> [!NOTE]
> settings-win.data.microsoft.com solo es necesario si tienes Windows dispositivos que ejecutan la versión 1803 o anterior.<br>
>
> Las direcciones URL que incluyen v20 en ellas solo son necesarias si Windows dispositivos que ejecutan la versión 1803 o posterior. Por ejemplo, es necesario para un dispositivo Windows que ejecute la versión 1803 o posterior y se incorpore a la región de datos `us-v20.events.data.microsoft.com` Storage ESTADOS UNIDOS.
>
> Si está usando Antivirus de Microsoft Defender en su entorno, vea [Configure network connections to the Antivirus de Microsoft Defender cloud service](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).

Si un proxy o firewall bloquea el tráfico anónimo, ya que el sensor Defender for Endpoint se conecta desde el contexto del sistema, asegúrese de que el tráfico anónimo está permitido en las direcciones URL enumeradas anteriormente.

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a>Microsoft Monitoring Agent (MMA): requisitos de proxy y firewall para versiones anteriores de Windows cliente o Windows server

La siguiente información enumera la información de configuración de proxy y firewall necesaria para comunicarse con el agente de Log Analytics (a menudo denominado Microsoft Monitoring Agent) para las versiones anteriores de Windows como Windows 7 SP1, Windows 8.1 y Windows Server 2008 R2*

<br>

****

|Recurso del agente|Puertos|Dirección|Omitir la inspección HTTP|
|---|---|---|---|
|*.ods.opinsights.azure.com|Puerto 443|Salida|Yes|
|*.oms.opinsights.azure.com|Puerto 443|Salida|Yes|
|*.blob.core.windows.net|Puerto 443|Salida|Yes|
|*.azure-automation.net|Puerto 443|Salida|Yes|

>[!NOTE]
>*Estos requisitos de conectividad también se aplican al anterior Microsoft Defender para endpoint para Windows Server 2016 y Windows Server 2012 R2 que requiere la MMA. Las instrucciones para incorporar estos sistemas operativos con la nueva solución unificada se encuentran en Onboard [Windows servers](configure-server-endpoints.md), o para migrar a la nueva solución no fiada en [escenarios](/microsoft-365/security/defender-endpoint/server-migration)de migración de servidor en Microsoft Defender para endpoint .

> [!NOTE]
> Como solución basada en la nube, el intervalo IP puede cambiar. Se recomienda pasar a la configuración de resolución de DNS.

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a>Confirmar Microsoft Monitoring Agent url de servicio (MMA) 

 Consulte las siguientes instrucciones para eliminar el requisito de comodín (*) para su entorno específico al usar el Microsoft Monitoring Agent (MMA) para versiones anteriores de Windows.

1.  Incorporar un sistema operativo anterior con el Microsoft Monitoring Agent (MMA) en Defender para endpoint (para obtener más información, vea [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and Onboard Windows [servers](configure-server-endpoints.md).

2. Asegúrese de que la máquina se está informando correctamente en el portal Microsoft 365 Defender usuario.

3. Ejecute la herramienta TestCloudConnection.exe desde "C:\Program Files\Microsoft Monitoring Agent\Agent" para validar la conectividad y ver las direcciones URL necesarias para su área de trabajo específica.

4. Compruebe la lista de direcciones URL de punto de conexión de Microsoft Defender para obtener la lista completa de requisitos para su región (consulte la hoja de cálculo de direcciones URL de [servicio](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).

    ![Imagen del administrador en Windows PowerShell.](images/admin-powershell.png)

Los caracteres comodín ( ) usados en los extremos de dirección \* \* URL \* .ods.opinsights.azure.com, .oms.opinsights.azure.com y .agentsvc.azure-automation.net se pueden reemplazar por el identificador de área de \* trabajo específico. El identificador de área de trabajo es específico de su entorno y área de trabajo y se puede encontrar en la sección Incorporación del espacio empresarial en el portal de Microsoft 365 Defender área de trabajo.

El extremo de dirección URL .blob.core.windows.net se puede reemplazar por las direcciones URL mostradas en la sección "Regla de \* firewall: \* .blob.core.windows.net" de los resultados de la prueba.

> [!NOTE]
> En el caso de la incorporación a través de Azure Defender, se pueden usar varias áreas de trabajo. Deberá realizar el procedimiento de TestCloudConnection.exe anterior en una máquina integrada de cada área de trabajo (para determinar si hay cambios en las direcciones URL *.blob.core.windows.net entre las áreas de trabajo).

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a>Comprobar la conectividad del cliente a Microsoft Defender para las direcciones URL del servicio endpoint

Compruebe que la configuración del proxy se ha completado correctamente, que WinHTTP puede detectar y comunicarse mediante el servidor proxy en su entorno y que el servidor proxy permite el tráfico a las direcciones URL del servicio de Defender para punto de conexión.

1. Descargue la [herramienta Analizador de cliente](https://aka.ms/mdeanalyzer) de Microsoft Defender para puntos de conexión en el equipo en el que se ejecuta el sensor Defender for Endpoint.

2. Extrae el contenido de MDEClientAnalyzer.zip en el dispositivo.

3. Abra un símbolo del sistema con privilegios elevados:
   1. Vaya a **Inicio** y escriba **cmd**.
   1. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

4. Escriba el siguiente comando y presione **Entrar**:

    ```PowerShell
    HardDrivePath\MDEClientAnalyzer.cmd
    ```

    Reemplace *HardDrivePath por* la ruta de acceso en la que se descargó la herramienta MDEClientAnalyzer, por ejemplo:

    ```PowerShell
    C:\Work\tools\MDEClientAnalyzer\MDEClientAnalyzer.cmd
    ```

5. Extraiga el *MDEClientAnalyzerResult.zip* creado por la herramienta en la carpeta usada en *HardDrivePath*.

6. Abra *MDEClientAnalyzerResult.txt* y compruebe que ha realizado los pasos de configuración de proxy para habilitar la detección de servidores y el acceso a las direcciones URL del servicio.

   La herramienta comprueba la conectividad de las direcciones URL del servicio de Defender para punto de conexión con las que el cliente está configurado para interactuar. A continuación, imprime los resultados en el archivo *MDEClientAnalyzerResult.txt* para cada dirección URL que se pueda usar potencialmente para comunicarse con defender para los servicios de extremo. Por ejemplo:

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

Si al menos una de las opciones de conectividad devuelve un estado (200), el cliente de Defender para punto de conexión puede comunicarse con la URL probada correctamente con este método de conectividad.

Pero si los resultados de la comprobación de conectividad indican un error, se mostrará un error HTTP (vea los códigos de estado HTTP). A continuación, puede usar las direcciones URL de la tabla que se muestra en Habilitar el acceso a las direcciones URL del servicio defender para puntos de conexión [en el servidor proxy](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server). Las direcciones URL que usará dependerán de la región seleccionada durante el procedimiento de incorporación.

> [!NOTE]
> Las comprobaciones de conectividad en la nube de la herramienta Analizador de conectividad no son compatibles con la regla reducción de superficie de ataque Bloquear creaciones de proceso originadas a partir [de comandos PSExec y WMI](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules.md#block-process-creations-originating-from-psexec-and-wmi-commands). Tendrá que deshabilitar temporalmente esta regla para ejecutar la herramienta de conectividad. Como alternativa, puede agregar temporalmente [exclusiones de ASR](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction.md#exclude-files-and-folders) al ejecutar el analizador.
>
> Cuando se establece TelemetryProxyServer, en el Registro o a través de la directiva de grupo, Defender for Endpoint volverá a dirigirse si no puede tener acceso al proxy definido.

## <a name="related-topics"></a>Temas relacionados

- [Configurar y validar las conexiones de red del Antivirus de Windows Defender](configure-network-connections-microsoft-defender-antivirus.md)
- [Usar la configuración de directiva de grupo para configurar y administrar Antivirus de Microsoft Defender](use-group-policy-microsoft-defender-antivirus.md)
- [incorporar dispositivos Windows](configure-endpoints.md)
- [Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender](troubleshoot-onboarding.md)
