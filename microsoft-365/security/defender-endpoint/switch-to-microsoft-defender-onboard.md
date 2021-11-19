---
title: Cambiar a Microsoft Defender para endpoint - Onboard
description: Realice el cambio a Microsoft Defender para endpoint. Incorpore dispositivos y, a continuación, desinstale la solución que no es de Microsoft.
keywords: migración, Microsoft Defender para Endpoint, edr
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.custom:
- migrationguides
- admindeeplinkDEFENDER
ms.topic: article
ms.date: 10/07/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 947ea79442eae471aec2afe9963fb3f3670765e6
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111548"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Cambiar a Microsoft Defender para endpoint - Fase 3: Incorporación

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![Fase 1: Prepare3.](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Fase 1: Preparación](switch-to-microsoft-defender-prepare.md) | [![Fase 2: Configuración](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Fase 2: Configuración](switch-to-microsoft-defender-setup.md) | ![Fase 3: Incorporación](images/phase-diagrams/onboard.png)<br/>Fase 3: Incorporación |
|--|--|--|
|| |*¡Estás aquí!* |

**Bienvenido a la fase 3 de [cambio a Defender para endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)**. Esta fase de migración incluye los siguientes pasos:

1. [Incorporar dispositivos a Defender para endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Ejecute una prueba de detección](#run-a-detection-test).
3. [Confirme que Antivirus de Microsoft Defender está en modo pasivo en los puntos de conexión](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints).
4. [Obtener actualizaciones para Antivirus de Microsoft Defender](#get-updates-for-microsoft-defender-antivirus).
5. [Desinstale la solución que no es de Microsoft](#uninstall-your-non-microsoft-solution).
6. [Asegúrese de que Defender for Endpoint funciona correctamente.](#make-sure-defender-for-endpoint-is-working-correctly)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Incorporar dispositivos a Microsoft Defender para punto de conexión

1. Vaya al portal <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender e</a> inicie sesión.

2. Elija **Configuración** \> **incorporación de puntos de** \> **conexión** (en **Administración de dispositivos**).

3. En la lista Seleccionar sistema operativo para iniciar el proceso **de incorporación,** seleccione un sistema operativo.

4. En **Método de implementación,** seleccione una opción. Siga los vínculos y avisos para incorporar los dispositivos de la organización. ¿Necesita ayuda? Vea [Métodos de incorporación](#onboarding-methods) (en este artículo).

> [!NOTE]
> Si algo sale mal durante la incorporación, consulta Solucionar problemas de incorporación de Puntos de conexión [de Microsoft Defender.](troubleshoot-onboarding.md) En ese artículo se describe cómo resolver problemas de incorporación y errores comunes en los puntos de conexión.

### <a name="onboarding-methods"></a>Métodos de incorporación

Los métodos de implementación varían según el sistema operativo y los métodos preferidos. En la tabla siguiente se enumeran los recursos que le ayudarán a incorporarse a Defender for Endpoint:

|Sistemas operativos  |Métodos  |
|---------|---------|
|Windows 10 o posterior<br/><br/>Windows Server 2019 o posterior<br/><br/>Windows server, versión 1803 o posterior<br/><br/>Windows Server 2012 R2 y 2016 <sup> [[1](#fn1)]<sup>  |   [Script local (hasta 10 dispositivos)](configure-endpoints-script.md)<br><br/>   [Directiva de grupo](configure-endpoints-gp.md)<br/><br/>[Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)<br/><br/>[Microsoft Endpoint Manager/ Administración de dispositivos móviles (Intune)](configure-endpoints-mdm.md)<br>    [Scripts VDI](configure-endpoints-vdi.md) <br><br> **NOTA:** Un script local es adecuado para una prueba de concepto, pero no debe usarse para la implementación de producción. Para una implementación de producción, se recomienda usar la directiva de grupo, Microsoft Endpoint Configuration Manager o Intune.
|Windows Server 2008 R2 SP1 | [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) o [Microsoft Defender para la nube](/azure/security-center/security-center-wdatp) <br><br> **NOTA:** Microsoft Monitoring Agent es ahora agente de Azure Log Analytics. Para obtener más información, consulte [Log Analytics agent overview](/azure/azure-monitor/platform/log-analytics-agent).  
|Windows 8.1 Enterprise<br/><br/>Windows 8.1 Pro<br/><br/>Windows 7 SP1 Pro<br/><br/>Windows 7 SP1| [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md) <br><br> **NOTA:** Microsoft Monitoring Agent es ahora agente de Azure Log Analytics. Para obtener más información, consulte [Log Analytics agent overview](/azure/azure-monitor/platform/log-analytics-agent).  
| macOS:<br/>11.3.1 (Big Sur)<br/>10.15 (Catalina)<br/>10.14 (Mojave) | [Script local](mac-install-manually.md)<br/><br/>[Microsoft Endpoint Manager](mac-install-with-intune.md)<br/><br/>[JAMF Pro](mac-install-with-jamf.md)<br/><br/>[Administración de dispositivos móviles](mac-install-with-other-mdm.md)   |
| Linux:<br/>RHEL 7.2+<br/>CentOS Linux 7.2+<br/>Ubuntu 16 LTS o LTS superior<br/>SLES 12+<br/>Debian 9+<br/>Oracle Linux 7.2 |  [Script local](linux-install-manually.md) <br><br/> [Puppet](linux-install-with-puppet.md) <br><br/> [Ansible](linux-install-with-ansible.md)|  
| iOS | [Microsoft Endpoint Manager](ios-install.md)     |
|Android  | [Microsoft Endpoint Manager](android-intune.md)               | 




(<a id="fn1">1</a>) Windows Server 2016 y Windows Server 2012 R2 tendrán que incorporarse con las instrucciones de [Onboard Windows servers](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016).


## <a name="run-a-detection-test"></a>Ejecutar una prueba de detección

Para comprobar que los dispositivos incorporados están correctamente conectados a Defender for Endpoint, puedes ejecutar una prueba de detección.

<br/><br/>

|Sistema operativo|Instrucciones|
|---|---|
|Windows 10 o posterior<br/><br/>Windows Server 2022<br/><br/>Windows Server 2019<br/><br/>Windows server, versión 1803 o posterior<br/><br/>Windows Server 2016<br/><br/>Windows Server 2012 R2|Consulte [Ejecutar una prueba de detección.](run-detection-test.md)<br/><br/>Visite el sitio de escenarios de demostración de Defender for Endpoint ( ) y <https://demo.wd.microsoft.com> pruebe uno o varios de los escenarios. Por ejemplo, pruebe el escenario **de demostración de** protección entregado en la nube.|
|macOS:<br/> 11.3.1 (Big Sur)<br/>10.15 (Catalina)<br/>10.14 (Mojave)|Descargue y use la aplicación DE BRICOLAJE en <https://aka.ms/mdatpmacosdiy> . <br/><br/> Para obtener más información, [vea Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md).|
|Linux:<br/> RHEL 7.2+<br/>CentOS Linux 7.2+<br/>Ubuntu 16 LTS o LTS superior<br/>SLES 12+<br/>Debian 9+<br/>Oracle Linux 7.2|1. Ejecute el siguiente comando y busque un resultado de **1**: `mdatp health --field real_time_protection_enabled` .<br/><br/>2. Abra una ventana terminal y ejecute el siguiente comando: `curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt` .<br/><br/>3. Ejecute el siguiente comando para enumerar las amenazas detectadas: `mdatp threat list` .<br/><br/>Para obtener más información, [vea Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md).|


## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>Confirme que Antivirus de Microsoft Defender está en modo pasivo en los puntos de conexión

Ahora que los puntos de conexión se han incorporado a Defender for Endpoint, el siguiente paso es asegurarse de que Antivirus de Microsoft Defender se está ejecutando en modo pasivo. Puede usar uno de varios métodos, como se describe en la tabla siguiente:

<br/><br/>

|Método|Qué hacer|
|---|---|
|Símbolo del sistema|1. En un dispositivo Windows, abra el símbolo del sistema.<br/><br/>2. Escriba `sc query windefend` y, a continuación, presione ENTRAR.<br/><br/>3. Revise los resultados para confirmar que Antivirus de Microsoft Defender se está ejecutando en modo pasivo.|
|PowerShell|1. En un dispositivo Windows, abra Windows PowerShell como administrador.<br/><br/>2. Ejecute el siguiente cmdlet de PowerShell: `Get-MpComputerStatus|select AMRunningMode` . <br/><br/>3. Revise los resultados. Debería ver **el modo pasivo**.|
|Seguridad de Windows app|1. En un Windows, abra la aplicación Seguridad de Windows usuario.<br/><br/>2. Seleccione **Virus & protección contra amenazas**.<br/><br/>3. **¿Quién está protegiendo?** seleccione **Administrar proveedores**.<br/><br/>4. En la página **Proveedores de** seguridad, en **Antivirus,** busque Antivirus de Microsoft Defender **está activado**.|
|Administrador de tareas|1. En un dispositivo Windows, abra la aplicación Administrador de tareas.<br/><br/>2. Seleccione la **pestaña** Detalles. Busque **MsMpEng.exe** en la lista.|

> [!NOTE]
> Es posible que *Antivirus de Windows Defender* en lugar *de Antivirus de Microsoft Defender* en algunas versiones de Windows.
> Para obtener más información sobre el modo pasivo y el modo activo, vea [Más detalles sobre Antivirus de Microsoft Defender estados](microsoft-defender-antivirus-compatibility.md#more-details-about-microsoft-defender-antivirus-states).

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>Establecer Antivirus de Microsoft Defender en Windows server en modo pasivo manualmente

Para establecer Antivirus de Microsoft Defender en modo pasivo en Windows Server, versión 1803 o posterior, o Windows Server 2019 o Windows Server 2022, siga estos pasos:

1. Abra el Editor del Registro y, a continuación, vaya a:

   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Edite (o cree) una entrada DWORD denominada **ForceDefenderPassiveMode** y especifique la siguiente configuración:
   - Establezca el valor de DWORD en **1**.
   - En **Base**, seleccione **Hexadecimal**.

> [!NOTE]
> Puede usar otros métodos para establecer la clave del Registro, como los siguientes:
>
> - [Preferencia de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
> - [Herramienta Objeto de directiva de grupo local](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
> - [Un paquete en Configuration Manager](/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Inicie Antivirus de Microsoft Defender en Windows Server 2016

Si usas Windows Server 2016, es posible que deba empezar a Antivirus de Microsoft Defender manualmente. Puede realizar esta tarea mediante el cmdlet de PowerShell `mpcmdrun.exe -wdenable` en el dispositivo.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Obtener actualizaciones para Antivirus de Microsoft Defender

Mantener Antivirus de Microsoft Defender actualizado es fundamental para garantizar que los dispositivos tienen la tecnología y las características más recientes necesarias para protegerse contra nuevas técnicas de ataque y malware, incluso si Antivirus de Microsoft Defender se está ejecutando en modo pasivo. (Vea [Antivirus de Microsoft Defender compatibilidad](microsoft-defender-antivirus-compatibility.md).)

Hay dos tipos de actualizaciones relacionadas con mantener Antivirus de Microsoft Defender actualizado:

- Actualizaciones de inteligencia de seguridad
- Actualizaciones de productos

Para obtener las actualizaciones, siga las instrucciones de [Manage Antivirus de Microsoft Defender updates y apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).

## <a name="uninstall-your-non-microsoft-solution"></a>Desinstalar la solución que no es de Microsoft

Si en este momento tiene:

- Incorporó los dispositivos de la organización a Defender for Endpoint y
- Antivirus de Microsoft Defender está instalado y habilitado,

A continuación, el siguiente paso es desinstalar la solución de antivirus, antimalware y endpoint protection que no sea de Microsoft. Al desinstalar la solución que no es de Microsoft, Antivirus de Microsoft Defender pasa del modo pasivo al modo activo. En la mayoría de los casos, esto ocurre automáticamente.

Para obtener ayuda con la desinstalación de la solución que no es de Microsoft, póngase en contacto con su equipo de soporte técnico.

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>Asegúrese de que Defender for Endpoint funciona correctamente

Ahora que has incorporado a Defender for Endpoint y has desinstalado la solución anterior que no es de Microsoft, el siguiente paso es asegurarte de que Defender for Endpoint funciona correctamente. Una buena forma de realizar esta tarea es visitando el sitio de escenarios de demostración de Defender para endpoint ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Pruebe uno o varios de los escenarios de demostración de esa página, incluidos al menos los siguientes:

- Protección entregada en la nube
- Aplicaciones potencialmente no deseadas (PUA)
- Protección de red (NP)

## <a name="next-steps"></a>Siguientes pasos

**¡Enhorabuena!** Ha completado la migración [a Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)!

- [Visite el panel de operaciones de seguridad](security-operations-dashboard.md) en el portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ).
- [Administrar Defender para endpoint, después de la migración](manage-atp-post-migration.md).
