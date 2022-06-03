---
title: Incorporación de versiones anteriores de Windows en Microsoft Defender para punto de conexión
description: Incorporación de versiones anteriores compatibles de dispositivos Windows para que puedan enviar datos del sensor al sensor de Microsoft Defender para punto de conexión
keywords: onboard, windows, 7, 81, oms, sp1, enterprise, pro, down level
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8ca88340ae90889c0e45c5905863373d930949b2
ms.sourcegitcommit: 35f167725bec5fd4fe131781a53d96b060cf232d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "65872970"
---
# <a name="onboard-previous-versions-of-windows"></a>Incorporar versiones anteriores de Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataformas**

- Windows 7 SP1 Enterprise
- Windows 7 SP1 Pro
- Windows 8.1 Pro
- Windows 8.1 Enterprise
- Windows Server 2008 R2 SP1

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-downlevel-abovefoldlink)

Defender for Endpoint amplía la compatibilidad para incluir sistemas operativos de nivel inferior, lo que proporciona funcionalidades avanzadas de detección e investigación de ataques en las versiones de Windows compatibles.

Para incorporar puntos de conexión de cliente de nivel inferior Windows a Defender para punto de conexión, deberá:

- [Configuración y actualización de clientes System Center Endpoint Protection](#configure-and-update-system-center-endpoint-protection-clients)
- [Instalación y configuración de Microsoft Monitoring Agent (MMA) para informar de los datos del sensor](#install-and-configure-microsoft-monitoring-agent-mma)

Para Windows Server 2008 R2 SP1, tiene la opción de [incorporar a través de Microsoft Defender for Cloud](#onboard-windows-servers-through-microsoft-defender-for-cloud).

> [!NOTE]
> Se requiere una licencia de servidor independiente de Defender para punto de conexión, por nodo, para incorporar un servidor de Windows a través de Microsoft Monitoring Agent (opción 1). Como alternativa, se requiere una licencia de Microsoft Defender para servidores, por nodo, para incorporar un servidor Windows a través de Microsoft Defender for Cloud (opción 2), consulte [Características admitidas disponibles en Microsoft Defender for Cloud](/azure/defender-for-cloud/supported-machines-endpoint-solutions-clouds-servers).

> [!TIP]
> Después de incorporar el dispositivo, puede optar por ejecutar una prueba de detección para comprobar que está incorporado correctamente al servicio. Para obtener más información, consulte [Ejecución de una prueba de detección en un punto de conexión de Defender para punto de conexión recién incorporado](run-detection-test.md).

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>Configuración y actualización de clientes System Center Endpoint Protection

> [!IMPORTANT]
> Este paso solo es necesario si la organización usa System Center Endpoint Protection (SCEP).

Defender para punto de conexión se integra con System Center Endpoint Protection para proporcionar visibilidad a las detecciones de malware y detener la propagación de un ataque en su organización mediante la prohibición de archivos potencialmente malintencionados o sospechas de malware.

Los pasos siguientes son necesarios para habilitar esta integración:

- Instalación de la [actualización de la plataforma antimalware de enero de 2017 para clientes Endpoint Protection](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)
- Configuración de la pertenencia del servicio de protección en la nube del cliente SCEP a la configuración **avanzada**
- Configure la red para permitir conexiones a la nube de Antivirus de Microsoft Defender. Para obtener más información, consulte [Configuración y validación de conexiones de red Antivirus de Microsoft Defender](/microsoft-365/security/defender-endpoint/configure-network-connections-microsoft-defender-antivirus)

## <a name="install-and-configure-microsoft-monitoring-agent-mma"></a>Instalación y configuración de Microsoft Monitoring Agent (MMA)

### <a name="before-you-begin"></a>Antes de empezar

Revise los detalles siguientes para comprobar los requisitos mínimos del sistema:

- Instalación del [paquete acumulativo de actualizaciones mensual de febrero de 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

  > [!NOTE]
  > Solo se aplica a Windows Server 2008 R2, Windows 7 SP1 Enterprise y Windows 7 SP1 Pro.

- Instalación de la [actualización para la experiencia del cliente y la telemetría de diagnóstico](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- Instale [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o posterior) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > Solo se aplica a Windows Server 2008 R2, Windows 7 SP1 Enterprise y Windows 7 SP1 Pro.
    >
    > No instale .NET Framework 4.0.x, ya que negará la instalación anterior.
    >
    > La instalación de .NET 4.5 puede requerir que reinicie el equipo después de la instalación.

- Cumpla los requisitos mínimos del sistema del agente de Azure Log Analytics. Para obtener más información, consulte [Recopilación de datos de equipos de su entorno con Log Analytics](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites).

### <a name="installation-steps"></a>Pasos de la instalación

1. Descargue el archivo de instalación del agente: [Windows agente de 64 bits](https://go.microsoft.com/fwlink/?LinkId=828603) o [Windows agente de 32 bits](https://go.microsoft.com/fwlink/?LinkId=828604).

    >[!NOTE]
    >Debido al [desuso de la compatibilidad con SHA-1 por parte del agente mma](/azure/azure-monitor/agents/agent-windows#sha-2-code-signing-support-requirement), el agente de MMA debe ser la versión 10.20.18029 o posterior.
    

2. Obtenga el identificador del área de trabajo:
   - En el panel de navegación de Defender para punto de conexión, seleccione **Configuración > Administración de dispositivos > Incorporación**
   - Seleccionar el sistema operativo
   - Copia del identificador del área de trabajo y la clave del área de trabajo

3. Con el identificador del área de trabajo y la clave del área de trabajo, elija cualquiera de los métodos de instalación siguientes para instalar el agente:
    - [Instale manualmente el agente mediante el programa de instalación](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).

      En la página **Opciones de configuración del agente**, seleccione **Conectar el agente a Azure Log Analytics (OMS)**

    - [Instale el agente mediante la línea de comandos](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).
    - [Configure el agente mediante un script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).

   > [!NOTE]
   > Si es un [cliente de Us Government](gov.md), en "Azure Cloud" tendrá que elegir "Azure US Government" si usa el asistente para la instalación o si usa una línea de comandos o un script: establezca el parámetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" en 1.

4. Si usa un proxy para conectarse a Internet, consulte la sección Configuración de proxy y conectividad a Internet.

Una vez completado, debería ver los puntos de conexión incorporados en el portal en un plazo de una hora.

## <a name="configure-proxy-and-internet-connectivity-settings"></a>Configurar las opciones del proxy y de conectividad a Internet
Si los servidores necesitan usar un proxy para comunicarse con Defender para punto de conexión, use uno de los métodos siguientes para configurar mma para usar el servidor proxy:

- [Configuración de MMA para usar un servidor proxy](/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [Configuración de Windows para usar un servidor proxy para todas las conexiones](configure-proxy-internet.md)

Si se usa un proxy o firewall, asegúrese de que los servidores puedan acceder a todas las direcciones URL de servicio de Microsoft Defender para punto de conexión directamente y sin interceptación SSL. Para obtener más información, consulte [Habilitación del acceso a las direcciones URL del servicio Defender para punto de conexión](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server). El uso de la intercepción SSL impedirá que el sistema se comunique con el servicio Defender para punto de conexión.

Una vez completado, debería ver los servidores de Windows incorporados en el portal en un plazo de una hora.

## <a name="onboard-windows-servers-through-microsoft-defender-for-cloud"></a>Incorporación de servidores Windows a través de Microsoft Defender for Cloud

1. En el panel de navegación Microsoft 365 Defender, seleccione **Configuración** >  **Inscripción de administración** > **de dispositivos**.

2. Seleccione **Windows Server 2008 R2 SP1** como sistema operativo.

3. Haga clic **en Incorporar servidores en Microsoft Defender for Cloud**.

4. Siga las instrucciones de incorporación de [Microsoft Defender para punto de conexión con Microsoft Defender for Cloud](/azure/security-center/security-center-wdatp) y, si usa Azure ARC, siga las instrucciones de incorporación en [Habilitación de Microsoft Defender para punto de conexión integración](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).

Después de completar los pasos de incorporación, deberá [configurar y actualizar System Center Endpoint Protection clientes](#configure-and-update-system-center-endpoint-protection-clients).

> [!NOTE]
>
> - Para que la incorporación a través de Microsoft Defender para que los servidores funcionen según lo previsto, el servidor debe tener un área de trabajo y una clave adecuadas configuradas dentro de la configuración de Microsoft Monitoring Agent (MMA).
> - Una vez configurado, el módulo de administración en la nube adecuado se implementa en la máquina y el proceso del sensor (MsSenseS.exe) se implementará e iniciará.
> - Esto también es necesario si el servidor está configurado para usar un servidor de puerta de enlace de OMS como proxy.



## <a name="verify-onboarding"></a>Comprobación de la incorporación

Compruebe que el Antivirus de Microsoft Defender y Microsoft Defender para punto de conexión están en ejecución. 

> [!NOTE]
> No es necesario ejecutar el antivirus de Microsoft Defender, pero se recomienda. Si otro producto de proveedor de antivirus es la solución de endpoint protection principal, puede ejecutar Antivirus de Defender en modo pasivo. Solo puede confirmar que el modo pasivo está activado después de comprobar que se está ejecutando Microsoft Defender para punto de conexión sensor (SENSE). 

1. Ejecute el siguiente comando para comprobar que el Antivirus de Microsoft Defender está instalado:

   ```sc.exe query Windefend```

    Si el resultado es "El servicio especificado no existe como un servicio instalado", deberá instalar El antivirus de Microsoft Defender. Para obtener más información, consulte [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-windows.md).

    Para obtener información sobre cómo usar directiva de grupo para configurar y administrar Antivirus de Microsoft Defender en los servidores de Windows, consulte [Uso de directiva de grupo configuración para configurar y administrar Antivirus de Microsoft Defender](use-group-policy-microsoft-defender-antivirus.md).


2. Ejecute el siguiente comando para comprobar que Microsoft Defender para punto de conexión se está ejecutando:

    ```sc.exe query sense```
    
    El resultado debe mostrar que se está ejecutando. Si tiene problemas con la incorporación, consulte [Solución de problemas de incorporación](troubleshoot-onboarding.md).

## <a name="run-a-detection-test"></a>Ejecución de una prueba de detección
Siga los pasos descritos en [Ejecutar una prueba de detección en un dispositivo recién incorporado](run-detection-test.md) para comprobar que el servidor informa a Defender para el servicio de punto de conexión.





## <a name="onboarding-endpoints-with-no-management-solution"></a>Incorporación de puntos de conexión sin solución de administración 

### <a name="using-group-policy"></a>Uso de directiva de grupo

**Paso 1: Descargue el udpate correspondiente para el punto de conexión.**

1. Vaya a c:\windows\sysvol\domain\scripts (podría ser necesario cambiar el control en uno de los controladores de dominio).
1. Cree una carpeta denominada MMA.
1. Descargue lo siguiente y colóquelos en la carpeta MMA:
   
    - Actualización de la experiencia del cliente y la telemetría de diagnóstico:
      - [Para Windows Server 2008 R2 x64](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)
     
    Para Windows Server 2008 R2 SP1, también se requieren las siguientes actualizaciones:

    Acumulación mensual de febrero de 2018: KB4074598 (Windows Server 2008 R2)

    [Catálogo de Microsoft Update](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4074598)<br>
    Descarga de actualizaciones para Windows Server 2008 R2 x64
    
    .NET Framework 3.5.1 (KB315418)<br>
    [Para Windows Server 2008 R2 x64](/iis/install/installing-iis-7/install-windows-server-2008-and-windows-server-2008-r2)
    
    >[!NOTE]
    > En este artículo se supone que usa servidores basados en x64 (agente MMA .exe versión compatible con x64 New SHA-2).


**Paso 2: Crear un nombre de archivo DeployMMA.cmd (mediante el Bloc de notas)** Agregue las líneas siguientes al archivo cmd. Tenga en cuenta que necesitará el identificador de área de trabajo y la clave.

El siguiente comando es un ejemplo. Reemplace los valores siguientes:
- KB: use la KB aplicable pertinente para el punto de conexión que va a incorporar.
- Id. de área de trabajo y CLAVE: use el identificador y la clave


```dos
@echo off 
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" ( 
exit
) ELSE (

wusa.exe C:\Windows\MMA\Windows6.1-KB3080149-x64.msu /quiet /norestart
wusa.exe C:\Windows\MMA\Windows6.1-KB4074598-x64.msu /quiet /norestart
wusa.exe C:\Windows\MMA\Windows6.1-KB3154518-x64.msu /quiet /norestart
wusa.exe C:\Windows\MMA\Windows8.1-KB3080149-x64.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /c /t: "C:\Windows\MMA"c:\windows\MMA\ setup.exe /qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID="<your workspace ID>"
OPINSIGHTS_WORKSPACE_KEY="<your workspace key>" AcceptEndUserLicenseAgreement=1
)

)
```





### <a name="group-policy-configuration"></a>configuración de directiva de grupo

Cree una nueva directiva de grupo específicamente para la incorporación de dispositivos, como "incorporación de Microsoft Defender para punto de conexión".

- Cree una carpeta directiva de grupo denominada "c:\windows\MMA"

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="Ubicación de las carpetas" lightbox="images/grppolicyconfig1.png":::

    **Esto agregará una nueva carpeta en cada servidor que obtiene el GPO aplicado, denominado MMA, y se almacenará en c:\windows. Contendrá los archivos de instalación de MMA, los requisitos previos y el script de instalación.**

- Cree una preferencia de directiva de grupo Files para cada uno de los archivos almacenados en el inicio de sesión de Net.

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="La directiva de grupo: 1" lightbox="images/grppolicyconfig2.png":::

Copia los archivos de DOMAIN\NETLOGON\MMA\filename en C:\windows\MMA\filename, **por lo que los archivos de instalación son locales para el servidor**:

:::image type="content" source="images/deploymma.png" alt-text="Propiedades de deploy mma cmd" lightbox="images/deploymma.png":::

Repita el proceso, pero cree la segmentación de nivel de elemento en la pestaña COMMON, por lo que el archivo solo se copia en la versión adecuada del sistema operativo o de la plataforma en el ámbito:

:::image type="content" source="images/targeteditor.png" alt-text="Editor de destino" lightbox="images/targeteditor.png":::

Para Windows Server 2008 R2 necesitará (y solo se copiará) lo siguiente:
- Windows6.1-KB3080149-x64.msu
- Windows6.1-KB3154518-x64.msu
- Windows6.1-KB4075598-x64.msu


Una vez hecho esto, deberá crear una directiva de script de inicio:

:::image type="content" source="images/startupprops.png" alt-text="Propiedades de inicio" lightbox="images/startupprops.png":::

El nombre del archivo que se va a ejecutar aquí es c:\windows\MMA\DeployMMA.cmd.
Una vez que el servidor se reinicie como parte del proceso de inicio, instalará la base de datos De actualización para la experiencia del cliente y la telemetría de diagnóstico, y, a continuación, instalará el agente mma, al establecer el identificador del área de trabajo y la clave, y el servidor se incorporará.

También puede usar una **tarea inmediata** para ejecutar deployMMA.cmd si no desea reiniciar todos los servidores.

Esto podría hacerse en dos fases. En primer lugar, cree **los archivos y la carpeta en** GPO: dé tiempo al sistema para asegurarse de que se ha aplicado el GPO y que todos los servidores tienen los archivos de instalación. A continuación, agregue la tarea inmediata. Esto logrará el mismo resultado sin necesidad de reiniciar.

Dado que el script tiene un método de salida y no se volverá a ejecutar si el MMA está instalado, también podría usar una tarea programada diaria para lograr el mismo resultado. De forma similar a una directiva de cumplimiento Configuration Manager, se comprobará diariamente para asegurarse de que el MMA está presente.

:::image type="content" source="images/schtask.png" alt-text="tarea de programación" lightbox="images/schtask.png":::

:::image type="content" source="images/newtaskprops.png" alt-text="Las nuevas propiedades de tarea" lightbox="images/newtaskprops.png":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="Propiedades de descarga de deploy mma" lightbox="images/deploymmadowmload.png":::

:::image type="content" source="images/tasksch.png" alt-text="Programador de tareas" lightbox="images/tasksch.png":::

Como se mencionó en la documentación de incorporación de Server específicamente en torno a Server 2008 R2, consulte a continuación: Para Windows Server 2008 R2 SP1, asegúrese de cumplir los siguientes requisitos:

- Instalación del [paquete acumulativo de actualizaciones mensual de febrero de 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
- Instale [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o posterior) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

Compruebe que los KB están presentes antes de incorporar Windows Server 2008 R2. Este proceso le permite incorporar todos los servidores si no tiene Configuration Manager administrar servidores.


## <a name="offboard-endpoints"></a>Puntos de conexión fuera del panel

Tiene dos opciones para desconectar Windows puntos de conexión desde el servicio:

- Desinstalación del agente mma
- Quitar la configuración del área de trabajo de Defender para punto de conexión

> [!NOTE]
> La retirada hace que el punto de conexión de Windows deje de enviar datos del sensor al portal, pero los datos del punto de conexión, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.

### <a name="uninstall-the-mma-agent"></a>Desinstalación del agente mma

Para desconectar el punto de conexión Windows, puede desinstalar el agente de MMA o desasociarlo de los informes al área de trabajo de Defender para punto de conexión. Después de quitar el agente, el punto de conexión ya no enviará datos del sensor a Defender para punto de conexión.
Para obtener más información, consulte [Para deshabilitar un agente](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a>Quitar la configuración del área de trabajo de Defender para punto de conexión

Puede usar cualquiera de los métodos siguientes:

- Quitar la configuración del área de trabajo de Defender para punto de conexión del agente de MMA
- Ejecución de un comando de PowerShell para quitar la configuración

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a>Quitar la configuración del área de trabajo de Defender para punto de conexión del agente de MMA

1. En propiedades **de Microsoft Monitoring Agent**, seleccione la pestaña **Azure Log Analytics (OMS).**

2. Seleccione el área de trabajo Defender para punto de conexión y haga clic en **Quitar**.

    :::image type="content" source="images/atp-mma.png" alt-text="Panel Áreas de trabajo" lightbox="images/atp-mma.png":::

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a>Ejecución de un comando de PowerShell para quitar la configuración

1. Obtenga el identificador del área de trabajo:

   1. En el panel de navegación, seleccione **Configuración** >  **Onboarding**.

   1. Seleccione el sistema operativo correspondiente y obtenga el identificador del área de trabajo.

    
2. Abra una instancia de PowerShell con privilegios elevados y ejecute el siguiente comando. Use el identificador de área de trabajo que obtuvo y reemplace `WorkspaceID`:

    ```   
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace("WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```
