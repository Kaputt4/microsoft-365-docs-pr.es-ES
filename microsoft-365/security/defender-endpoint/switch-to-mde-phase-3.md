---
title: 'Cambiar a Microsoft Defender para punto de conexión: incorporación'
description: Realice el cambio a Microsoft Defender para punto de conexión. Incorpore dispositivos y, a continuación, desinstale la solución que no sea de Microsoft.
keywords: migración, Microsoft Defender para punto de conexión, edr
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-migratetomdatp
- highpri
- tier1
ms.custom:
- migrationguides
- admindeeplinkDEFENDER
ms.topic: conceptual
ms.date: 09/22/2022
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
search.appverid: met150
ms.openlocfilehash: e44e514811940e065988617e772222afaf70b222
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68637538"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Cambiar a Microsoft Defender para punto de conexión- Fase 3: Incorporación

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![Fase 1: Preparación3.](images/phase-diagrams/prepare.png#lightbox)](switch-to-mde-phase-1.md)<br/>[Fase 1: Preparación](switch-to-mde-phase-1.md) | [![Fase 2: Configuración](images/phase-diagrams/setup.png#lightbox)](switch-to-mde-phase-2.md)<br/>[Fase 2: Configuración](switch-to-mde-phase-2.md) | ![Fase 3: Incorporación](images/phase-diagrams/onboard.png#lightbox)<br/>Fase 3: Incorporación |
|--|--|--|
|| |*¡Estás aquí!* |

**Bienvenido a la fase 3 del [cambio a Defender para punto de conexión](switch-to-mde-overview.md#the-migration-process)**. Esta fase de migración incluye los pasos siguientes:

1. [Incorporación de dispositivos a Defender para punto de conexión](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Ejecute una prueba de detección](#run-a-detection-test).
3. [Confirme que Microsoft Defender Antivirus está en modo pasivo en los puntos de conexión](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints).
4. [Obtenga actualizaciones para Microsoft Defender Antivirus](#get-updates-for-microsoft-defender-antivirus).
5. [Desinstale la solución que no es de Microsoft](#uninstall-your-non-microsoft-solution).
6. [Asegúrese de que Defender para punto de conexión funciona correctamente](#make-sure-defender-for-endpoint-is-working-correctly).

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Incorporar dispositivos a Microsoft Defender para punto de conexión

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Elija **Configuración** \> **Incorporación** de **puntos** \> de conexión (en **Administración de dispositivos**).

3. En la lista **Seleccionar sistema operativo para iniciar el proceso de incorporación** , seleccione un sistema operativo.

4. En **Método de implementación**, seleccione una opción. Siga los vínculos y las indicaciones para incorporar los dispositivos de su organización. ¿Necesita ayuda? Consulte [Métodos de incorporación](#onboarding-methods) (en este artículo).

> [!NOTE]
> Si algo sale mal durante la incorporación, consulte [Solución de problemas de incorporación Microsoft Defender para punto de conexión](troubleshoot-onboarding.md). En ese artículo se describe cómo resolver problemas de incorporación y errores comunes en los puntos de conexión.

### <a name="onboarding-methods"></a>Métodos de incorporación

Los métodos de implementación varían según el sistema operativo y los métodos preferidos. En la tabla siguiente se enumeran los recursos que le ayudarán a incorporarse a Defender para punto de conexión:

|Sistemas operativos  |Métodos  |
|---------|---------|
|Windows 10 o posterior<br/><br/>Windows Server 2019 o posterior<br/><br/>Windows Server, versión 1803 o posterior<br/><br/>Windows Server 2012 R2 y 2016<sup>[[1](#fn1)]<sup>  |   [Script local (hasta 10 dispositivos)](configure-endpoints-script.md)<br><br/>   [Directiva de grupo](configure-endpoints-gp.md)<br/><br/>[Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)<br/><br/>[Microsoft Endpoint Manager/Administración de dispositivos móviles (Intune)](configure-endpoints-mdm.md)<br>    [Scripts de VDI](configure-endpoints-vdi.md) <br><br> **NOTA**: Un script local es adecuado para una prueba de concepto, pero no debe usarse para la implementación de producción. Para una implementación de producción, se recomienda usar समूह नीति, Microsoft Endpoint Configuration Manager o Intune. |
|Windows Server 2008 R2 SP1 | [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) o [Microsoft Defender for Cloud](/azure/security-center/security-center-wdatp) <br><br> **NOTA**: Microsoft Monitoring Agent es ahora el agente de Azure Log Analytics. Para más información, consulte [Introducción al agente de Log Analytics](/azure/azure-monitor/platform/log-analytics-agent).  |
|Windows 8.1 Enterprise<br/><br/>Windows 8.1 Pro<br/><br/>Windows 7 SP1 Pro<br/><br/>Windows 7 SP1| [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md) <br><br> **NOTA**: Microsoft Monitoring Agent es ahora el agente de Azure Log Analytics. Para más información, consulte [Introducción al agente de Log Analytics](/azure/azure-monitor/platform/log-analytics-agent).  
| macOS (consulte [Requisitos del sistema)](microsoft-defender-endpoint-mac.md) | [Script local](mac-install-manually.md)<br/><br/>[Microsoft Endpoint Manager](mac-install-with-intune.md)<br/><br/>[JAMF Pro](mac-install-with-jamf.md)<br/><br/>[Administración de dispositivos móviles](mac-install-with-other-mdm.md)   |
| Linux (consulte [Requisitos del sistema](microsoft-defender-endpoint-linux.md#system-requirements)) |  [Script local](linux-install-manually.md) <br><br/> [Marioneta](linux-install-with-puppet.md) <br><br/> [Ansible](linux-install-with-ansible.md)|  
| iOS | [Microsoft Endpoint Manager](ios-install.md)     |
|Android  | [Microsoft Endpoint Manager](android-intune.md)  | 

(<a id="fn1">1</a>) Windows Server 2016 y Windows Server 2012 R2 tendrán que incorporarse mediante las instrucciones de [Incorporación de servidores Windows](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016).

## <a name="run-a-detection-test"></a>Ejecución de una prueba de detección

Para comprobar que los dispositivos incorporados están conectados correctamente a Defender para punto de conexión, puede ejecutar una prueba de detección.

|Sistema operativo|Instrucciones|
|---|---|
|Windows 10 o posterior<br/><br/>Windows Server 2022<br/><br/>Windows Server 2019<br/><br/>Windows Server, versión 1803 o posterior<br/><br/>Windows Server 2016<br/><br/>Windows Server 2012 R2|Consulte [Ejecución de una prueba de detección](run-detection-test.md).|
|macOS (consulte [Requisitos del sistema)](microsoft-defender-endpoint-mac.md)|Descargue y use la aplicación de bricolaje en <https://aka.ms/mdatpmacosdiy>. <br/><br/> Para obtener más información, consulte [Defender para punto de conexión en macOS](microsoft-defender-endpoint-mac.md).|
|Linux (consulte [Requisitos del sistema](microsoft-defender-endpoint-linux.md#system-requirements))|1. Ejecute el siguiente comando y busque un resultado de **1**: `mdatp health --field real_time_protection_enabled`.<br/><br/>2. Abra una ventana terminal y ejecute el siguiente comando: `curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`.<br/><br/>3. Ejecute el siguiente comando para enumerar las amenazas detectadas: `mdatp threat list`.<br/><br/>Para obtener más información, consulte [Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md).|

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>Confirme que Microsoft Defender Antivirus está en modo pasivo en los puntos de conexión.

Ahora que los puntos de conexión se han incorporado a Defender para punto de conexión, el siguiente paso es asegurarse de que Microsoft Defender Antivirus se ejecuta en modo pasivo. Puede usar uno de varios métodos, como se describe en la tabla siguiente:

|Método|Qué hacer|
|---|---|
|Símbolo del sistema|1. En un dispositivo Windows, abra el símbolo del sistema.<br/><br/>2. Escriba `sc query windefend`y presione Entrar.<br/><br/>3. Revise los resultados para confirmar que Microsoft Defender Antivirus se ejecuta en modo pasivo.|
|PowerShell|1. En un dispositivo Windows, abra Windows PowerShell como administrador.<br/><br/>2. Ejecute el siguiente cmdlet de PowerShell: `Get-MpComputerStatus|select AMRunningMode`. <br/><br/>3. Revise los resultados. Debería ver **el modo pasivo**.|
|Aplicación Seguridad de Windows|1. En un dispositivo Windows, abra la aplicación Seguridad de Windows.<br/><br/>2. Seleccione **Virus & protección contra amenazas**.<br/><br/>3. En **¿Quién me protege?** seleccione **Administrar proveedores**.<br/><br/>4. En la página **Proveedores de seguridad**, en **Antivirus**, busque **Microsoft Defender Antivirus está activado**.|
|Administrador de tareas|1. En un dispositivo Windows, abra la aplicación Administrador de tareas.<br/><br/>2. Seleccione la pestaña **Detalles** . Busque **MsMpEng.exe** en la lista.|

> [!NOTE]
> Es posible que vea *Windows डिफेन्डर Antivirus* en lugar de *Microsoft Defender Antivirus* en algunas versiones de Windows.
> Para obtener más información sobre el modo pasivo y el modo activo, consulte [Más detalles sobre Microsoft Defender estados del Antivirus](microsoft-defender-antivirus-compatibility.md#more-details-about-microsoft-defender-antivirus-states).

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>Establecer Microsoft Defender Antivirus en Windows Server en modo pasivo manualmente

Para establecer Microsoft Defender Antivirus en modo pasivo en Windows Server, versión 1803 o posterior, o Windows Server 2019 o Windows Server 2022, siga estos pasos:

1. Abra el Editor del Registro y, a continuación, vaya a `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Edite (o cree) una entrada DWORD denominada **ForceDefenderPassiveMode** y especifique la siguiente configuración:

   - Establezca el valor de DWORD en **1**.

   - En **Base**, seleccione **Hexadecimal**.

> [!NOTE]
> Puede usar otros métodos para establecer la clave del Registro, como las siguientes:
>
> - [Preferencia de समूह नीति](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
> - [Herramienta objeto de समूह नीति local](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
> - [Un paquete en Configuration Manager](/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Inicie Microsoft Defender Antivirus en Windows Server 2016

Si usa Windows Server 2016, es posible que tenga que iniciar Microsoft Defender Antivirus manualmente. Puede realizar esta tarea mediante el cmdlet `mpcmdrun.exe -wdenable` de PowerShell en el dispositivo.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Obtención de actualizaciones para Microsoft Defender Antivirus

Mantener Microsoft Defender Antivirus actualizado es fundamental para garantizar que los dispositivos tengan la tecnología y las características más recientes necesarias para protegerse contra nuevas técnicas de malware y ataques, incluso si Microsoft Defender Antivirus se ejecuta en modo pasivo. (Consulte [compatibilidad con Microsoft Defender Antivirus](microsoft-defender-antivirus-compatibility.md)).

Existen dos tipos de actualizaciones vinculadas a mantener el Antivirus de Microsoft Defender al día:

- Actualizaciones de inteligencia de seguridad

- Actualizaciones de productos

Para obtener las actualizaciones, siga las instrucciones de [Administración de actualizaciones Microsoft Defender Antivirus y aplique líneas base](manage-updates-baselines-microsoft-defender-antivirus.md).

## <a name="uninstall-your-non-microsoft-solution"></a>Desinstalación de la solución que no es de Microsoft

Si en este momento tiene:

- Incorporó los dispositivos de su organización a Defender para punto de conexión y

- Microsoft Defender Antivirus está instalado y habilitado,

A continuación, el siguiente paso consiste en desinstalar la solución antivirus, antimalware y endpoint protection que no sea de Microsoft. Al desinstalar la solución que no es de Microsoft, Microsoft Defender Antivirus cambia del modo pasivo al modo activo. En la mayoría de los casos, esto sucede automáticamente. 

> [!IMPORTANT]
> Si, por alguna razón, Microsoft Defender Antivirus no entra en modo activo después de desinstalar la solución antivirus o antimalware que no es de Microsoft, consulte [Microsoft Defender Antivirus parece estar bloqueado en modo pasivo](switch-to-mde-troubleshooting.md#microsoft-defender-antivirus-seems-to-be-stuck-in-passive-mode).

Para obtener ayuda con la desinstalación de la solución que no es de Microsoft, póngase en contacto con su equipo de soporte técnico.

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>Asegúrese de que Defender para punto de conexión funciona correctamente

Ahora que se ha incorporado a Defender para punto de conexión y ha desinstalado la solución anterior que no es de Microsoft, el siguiente paso es asegurarse de que Defender para punto de conexión funciona correctamente. 

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija Inventario **de** **dispositivos de puntos** >  de conexión. Allí podrá ver el estado de protección de los dispositivos.

Para más información, consulte [Inventario de dispositivos](machines-view-overview.md).

## <a name="next-steps"></a>Pasos siguientes

**¡Enhorabuena**! Ha completado la [migración a Defender para punto de conexión](switch-to-mde-overview.md#the-migration-process).


- [Administrar Defender para punto de conexión, después de la migración](manage-mde-post-migration.md).
