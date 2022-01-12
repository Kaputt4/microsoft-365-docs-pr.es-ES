---
title: Incorporar versiones anteriores de Windows en Microsoft Defender para endpoint
description: Incorporar versiones anteriores compatibles de Windows dispositivos para que puedan enviar datos del sensor al sensor de Microsoft Defender para endpoint
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
ms.openlocfilehash: 60fd10024be0b214aed4cbc7ae89d7129df99e79
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61867829"
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

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-downlevel-abovefoldlink)

Defender for Endpoint amplía la compatibilidad para incluir sistemas operativos de nivel inferior, lo que proporciona capacidades avanzadas de detección de ataques e investigación en versiones Windows compatibles.

Para incorporar puntos de conexión Windows cliente a Defender for Endpoint, deberás:

- [Configurar y actualizar System Center Endpoint Protection clientes](#configure-and-update-system-center-endpoint-protection-clients)
- [Instalar y configurar Microsoft Monitoring Agent (MMA) para informar de los datos del sensor](#install-and-configure-microsoft-monitoring-agent-mma)

Para Windows Server 2008 R2 SP1, tiene la opción de incorporarse a través de [Microsoft Defender para la nube.](#onboard-windows-servers-through-microsoft-defender-for-cloud)

> [!NOTE]
> La licencia de servidor independiente de Defender for Endpoint es necesaria, por nodo, para incorporar un servidor Windows a través de Microsoft Monitoring Agent (opción 1). Como alternativa, se requiere una licencia de Microsoft Defender para servidores, por nodo, para incorporar un servidor de Windows a través de Microsoft Defender para la nube (opción 2), consulte Características admitidas disponibles en [Microsoft Defender para](/azure/security-center/security-center-services)la nube.

> [!TIP]
> Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que está correctamente incorporado al servicio. Para obtener más información, vea [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>Configurar y actualizar System Center Endpoint Protection clientes

> [!IMPORTANT]
> Este paso solo es necesario si la organización usa System Center Endpoint Protection (SCEP).

Defender for Endpoint se integra con System Center Endpoint Protection para proporcionar visibilidad a las detecciones de malware y detener la propagación de un ataque en su organización mediante la prohibición de archivos potencialmente malintencionados o malware sospechoso.

Se requieren los siguientes pasos para habilitar esta integración:

- Instalar la actualización de la plataforma antimalware de enero de [2017 para Endpoint Protection cliente](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)
- Configurar la pertenencia del servicio de protección en la nube del cliente SCEP a la **configuración** Avanzada
- Configure la red para permitir conexiones a la Antivirus de Microsoft Defender nube. Para obtener más información, vea [Configure and validate Antivirus de Microsoft Defender network connections](/microsoft-365/security/defender-endpoint/configure-network-connections-microsoft-defender-antivirus)

## <a name="install-and-configure-microsoft-monitoring-agent-mma"></a>Instalar y configurar Microsoft Monitoring Agent (MMA)

### <a name="before-you-begin"></a>Antes de empezar

Revise los siguientes detalles para comprobar los requisitos mínimos del sistema:

- Instalar el paquete acumulativo de actualizaciones [mensuales de febrero de 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

  > [!NOTE]
  > Solo se aplica Windows Server 2008 R2, Windows 7 SP1 Enterprise y Windows 7 SP1 Pro.

- Instalar la actualización [para la experiencia del cliente y telemetría de diagnóstico](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- Instalar [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o posterior) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > Solo se aplica Windows Server 2008 R2, Windows 7 SP1 Enterprise y Windows 7 SP1 Pro.
    >
    > No instales .NET Framework 4.0.x, ya que anulará la instalación anterior.
    >
    > La instalación de .NET 4.5 puede requerir que reinicie el equipo después de la instalación.

- Cumpla los requisitos mínimos del sistema del agente de Azure Log Analytics. Para obtener más información, vea [Recopilar datos de equipos en su entorno con Log Analytics](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)

### <a name="installation-steps"></a>Pasos de la instalación

1. Descargue el archivo de instalación del agente: Windows agente de [64](https://go.microsoft.com/fwlink/?LinkId=828603) bits o Windows agente de [32 bits](https://go.microsoft.com/fwlink/?LinkId=828604).

2. Obtenga el identificador del área de trabajo:
   - En el panel de navegación Defender para endpoint, **seleccione Configuración > Administración de dispositivos > incorporación**
   - Seleccionar el sistema operativo
   - Copiar el identificador del área de trabajo y la clave del área de trabajo

3. Con el identificador de área de trabajo y la clave Área de trabajo, elija cualquiera de los siguientes métodos de instalación para instalar el agente:
    - [Instale manualmente el agente mediante el programa de instalación](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).

      En la **página Opciones de configuración del** agente, seleccione Conectar el agente a Azure Log Analytics **(OMS)**

    - [Instale el agente mediante la línea de comandos](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).
    - [Configure el agente mediante un script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).

   > [!NOTE]
   > Si es cliente de [Us Government](gov.md), en "Azure Cloud" tendrá que elegir "Azure US Government" si usa el asistente para la instalación, o si usa una línea de comandos o un script: establezca el parámetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" en 1.

4. Si usa un proxy para conectarse a Internet, consulte la sección Configurar proxy y configuración de conectividad a Internet.

Una vez completado, debería ver puntos de conexión incorporados en el portal en una hora.

## <a name="configure-proxy-and-internet-connectivity-settings"></a>Configurar las opciones del proxy y de conectividad a Internet
Si los servidores necesitan usar un proxy para comunicarse con Defender for Endpoint, use uno de los métodos siguientes para configurar la MMA para usar el servidor proxy:

- [Configurar la MMA para usar un servidor proxy](/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [Configurar Windows usar un servidor proxy para todas las conexiones](configure-proxy-internet.md)

Si hay un proxy o firewall en uso, asegúrese de que los servidores puedan tener acceso a todas las direcciones URL del servicio de Microsoft Defender para endpoints directamente y sin interceptación SSL. Para obtener más información, vea [habilitar el acceso a las direcciones URL del servicio defender para puntos de conexión](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server). El uso de la interceptación SSL impedirá que el sistema se comunique con el servicio Defender for Endpoint.

Una vez completado, debería ver los servidores Windows incorporados en el portal en una hora.

## <a name="onboard-windows-servers-through-microsoft-defender-for-cloud"></a>Incorporación de Windows a través de Microsoft Defender para la nube

1. En el panel Microsoft 365 Defender navegación, **seleccione Configuración**  >  **Incorporación de administración de**  >  **dispositivos**.

2. Seleccione **Windows Server 2008 R2 SP1** como sistema operativo.

3. Haga **clic en Incorporar servidores en Microsoft Defender para la nube.**

4. Siga las instrucciones de incorporación en Microsoft Defender para endpoint con [Microsoft Defender para](/azure/security-center/security-center-wdatp) la nube y si usa Azure ARC, siga las instrucciones de incorporación en Habilitar la integración de Microsoft Defender para [endpoints](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).

Después de completar los pasos de incorporación, deberá configurar y actualizar los [System Center Endpoint Protection cliente.](#configure-and-update-system-center-endpoint-protection-clients)

> [!NOTE]
>
> - Para que la incorporación a través de Microsoft Defender para que los servidores funcionen según lo esperado, el servidor debe tener una clave y un área de trabajo adecuadas configuradas dentro de la configuración de Microsoft Monitoring Agent (MMA).
> - Una vez configurado, el módulo de administración de nube adecuado se implementa en el equipo y el proceso de sensor (MsSenseS.exe) se implementará e iniciará.
> - Esto también es necesario si el servidor está configurado para usar un servidor de puerta de enlace OMS como proxy.



## <a name="verify-onboarding"></a>Comprobar la incorporación

Compruebe que se estén ejecutando Microsoft Defender AV y Microsoft Defender para Endpoint. 

> [!NOTE]
> No es necesario ejecutar Microsoft Defender AV, pero se recomienda. Si otro producto de proveedor de antivirus es la solución principal de protección de puntos de conexión, puede ejecutar Defender Antivirus en modo pasivo. Solo puedes confirmar que el modo pasivo está activo después de comprobar que se está ejecutando el sensor de Microsoft Defender para endpoints (SENSE). 

1. Ejecute el siguiente comando para comprobar que Microsoft Defender AV está instalado:

   ```sc.exe query Windefend```

    Si el resultado es "El servicio especificado no existe como servicio instalado", tendrá que instalar Microsoft Defender AV. Para obtener más información, [vea Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-windows.md).

    Para obtener información sobre cómo usar la directiva de grupo para configurar y administrar Antivirus de Microsoft Defender en los servidores de Windows, vea [Use Group Policy settings to configure and manage Antivirus de Microsoft Defender](use-group-policy-microsoft-defender-antivirus.md).


2. Ejecute el siguiente comando para comprobar que se está ejecutando Microsoft Defender para endpoint:

    ```sc.exe query sense```
    
    El resultado debe mostrar que se está ejecutando. Si tiene problemas con la incorporación, consulte [Solucionar problemas de incorporación.](troubleshoot-onboarding.md)

## <a name="run-a-detection-test"></a>Ejecutar una prueba de detección
Siga los pasos descritos en Ejecutar una prueba de detección en un dispositivo recién incorporado para comprobar que el servidor está informando [a](run-detection-test.md) Defender para el servicio de extremo.





## <a name="onboarding-endpoints-with-no-management-solution"></a>Puntos de conexión de incorporación sin solución de administración 

### <a name="using-group-policy"></a>Uso de la directiva de grupo

**Paso 1: Descargar el udpate correspondiente para el punto de conexión.**

1. Vaya a c:\windows\sysvol\domain\scripts (podría ser necesario el control de cambio en uno de los controladores de dominio).
1. Cree una carpeta denominada MMA.
1. Descargue lo siguiente y colócalos en la carpeta MMA:
   
    - Actualización de la telemetría de diagnóstico y experiencia del cliente:
      - [Para Windows Server 2008 R2 x64](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)
     
    Para Windows Server 2008 R2 SP1, también son necesarias las siguientes actualizaciones:

    Actualización mensual de febrero de 2018: KB4074598 (Windows Server 2008 R2)

    [Catálogo de Microsoft Update](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4074598)<br>
    Descargar actualizaciones para Windows Server 2008 R2 x64
    
    .NET Framework 3.5.1 (KB315418)<br>
    [Para Windows Server 2008 R2 x64](https://download.microsoft.com/download/6/8/0/680ee424-358c-4fdf-a0de-b45dee07b711/windows6.1-kb3154518-x64.msu)
    
    >[!NOTE]
    > En este artículo se supone que usa servidores basados en x64 (agente mma .exe versión compatible con SHA-2 nueva de x64).


**Paso 2: Crear un nombre de archivo DeployMMA.cmd (con bloc de notas)** Agregue las siguientes líneas al archivo cmd. Ten en cuenta que necesitarás el identificador de área de trabajo y la clave.

El siguiente comando es un ejemplo. Reemplace los siguientes valores:
- KB: use la KB correspondiente al punto de conexión que está incorporando
- Identificador de área de trabajo y CLAVE: use el identificador y la clave


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





### <a name="group-policy-configuration"></a>Configuración de directiva de grupo

Crea una nueva directiva de grupo específicamente para los dispositivos de incorporación, como "Microsoft Defender para la incorporación de puntos de conexión".

- Crear una carpeta de directiva de grupo denominada "c:\windows\MMA"

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="carpetas":::

    **Esto agregará una nueva carpeta en cada servidor que obtiene el GPO aplicado, denominado MMA, y se almacenará en c:\windows. Esto contendrá los archivos de instalación del MMA, los requisitos previos y el script de instalación.**

- Cree una preferencia de archivos de directiva de grupo para cada uno de los archivos almacenados en el inicio de sesión de red.

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="imagen de directiva de grupo1":::

Copia los archivos de DOMAIN\NETLOGON\MMA\filename a C:\windows\MMA\filename, por lo que los archivos de instalación son **locales en el servidor:**

:::image type="content" source="images/deploymma.png" alt-text="implementar mma cmd":::

Repita el proceso pero cree la selección de destino de nivel de elemento en la pestaña COMMON, por lo que el archivo solo se copia en la versión de plataforma o sistema operativo correspondiente en el ámbito:

:::image type="content" source="images/targeteditor.png" alt-text="editor de destino":::

Para Windows Server 2008 R2 necesitará (y solo se copiará hacia abajo) lo siguiente:
- Windows6.1-KB3080149-x64.msu
- Windows6.1-KB3154518-x64.msu
- Windows6.1-KB4075598-x64.msu


Una vez hecho esto, deberá crear una directiva de script de inicio:

:::image type="content" source="images/startupprops.png" alt-text="propiedades de inicio":::

El nombre del archivo que se va a ejecutar aquí es c:\windows\MMA\DeployMMA.cmd.
Una vez reiniciado el servidor como parte del proceso de inicio, se instalará la actualización de la experiencia del cliente y la telemetría de diagnóstico KB y, a continuación, se instalará el agente mma, mientras se establece el identificador de área de trabajo y la clave, y se incorporará el servidor.

También puede usar una **tarea inmediata para** ejecutar deployMMA.cmd si no desea reiniciar todos los servidores.

Esto se podría hacer en dos fases. En primer **lugar,** cree los archivos y la carpeta en GPO: dé tiempo al sistema para asegurarse de que se ha aplicado el GPO y de que todos los servidores tienen los archivos de instalación. A continuación, agregue la tarea inmediata. Esto logrará el mismo resultado sin necesidad de reiniciar.

Dado que el script tiene un método exit y no se vuelve a ejecutar si está instalado el MMA, también puede usar una tarea programada diariamente para lograr el mismo resultado. De forma similar a una directiva de cumplimiento de Configuration Manager, se comprobará diariamente para asegurarse de que la MMA está presente.

:::image type="content" source="images/schtask.png" alt-text="tarea de programación":::

:::image type="content" source="images/newtaskprops.png" alt-text="nuevas propiedades de tarea":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="implementar aplicaciones de descarga de mma":::

:::image type="content" source="images/tasksch.png" alt-text="programador de tareas":::

Como se mencionó en la documentación de incorporación de Server específicamente en torno a Server 2008 R2, vea a continuación: Para Windows Server 2008 R2 SP1, asegúrese de cumplir los siguientes requisitos:

- Instalar el paquete acumulativo de actualizaciones [mensuales de febrero de 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
- Instalar [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o posterior) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

Compruebe que los KB están presentes antes de incorporar Windows Server 2008 R2. Este proceso le permite incorporar todos los servidores si no tiene Configuration Manager managing Servers.


## <a name="offboard-endpoints"></a>Puntos de conexión offboard

Tiene dos opciones para desactivar los Windows desde el servicio:

- Desinstalar el agente mma
- Quitar la configuración del área de trabajo de Defender for Endpoint

> [!NOTE]
> La offboarding hace que el extremo de Windows deje de enviar datos del sensor al portal, pero los datos del extremo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.

### <a name="uninstall-the-mma-agent"></a>Desinstalar el agente mma

Para desactivar el punto Windows, puede desinstalar el agente mma o desasoyérselo del informe al área de trabajo de Defender para endpoint. Después de salir del agente, el punto de conexión ya no enviará datos del sensor a Defender para Endpoint.
Para obtener más información, vea [Para deshabilitar un agente](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a>Quitar la configuración del área de trabajo de Defender for Endpoint

Puede usar cualquiera de los siguientes métodos:

- Quitar la configuración del área de trabajo de Defender for Endpoint del agente mma
- Ejecutar un comando de PowerShell para quitar la configuración

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a>Quitar la configuración del área de trabajo de Defender for Endpoint del agente mma

1. En el **Microsoft Monitoring Agent ,** seleccione la pestaña Azure Log **Analytics (OMS).**

2. Seleccione el área de trabajo Defender para extremo y haga clic en **Quitar**.

    ![Imagen de Microsoft Monitoring Agent propiedades](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a>Ejecutar un comando de PowerShell para quitar la configuración

1. Obtener el id. de área de trabajo:

   1. En el panel de navegación, **seleccione Configuración**  >  **Incorporación**.

   1. Seleccione el sistema operativo correspondiente y obtenga el identificador de área de trabajo.

    
2. Abra un PowerShell con privilegios elevados y ejecute el siguiente comando. Use el identificador de área de trabajo que obtuvo y reemplace `WorkspaceID` :

    ```   
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace("WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```
