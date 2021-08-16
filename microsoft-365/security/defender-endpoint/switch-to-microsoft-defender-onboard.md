---
title: Cambiar a Microsoft Defender para endpoint - Onboard
description: Esta es la fase 3, Incorporación, para migrar desde una solución que no es de Microsoft a Microsoft Defender para endpoint.
keywords: migración, Microsoft Defender para Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.custom: migrationguides
ms.topic: article
ms.date: 08/12/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 4a3ab70906b7fd01a2687afc7022f11a5451dc17
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58255492"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Cambiar a Microsoft Defender para endpoint - Fase 3: Incorporación

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![Fase 1: Prepare3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Fase 1: Preparación](switch-to-microsoft-defender-prepare.md) | [![Fase 2: Configuración](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Fase 2: Configuración](switch-to-microsoft-defender-setup.md) | ![Fase 3: Incorporación](images/phase-diagrams/onboard.png)<br/>Fase 3: Incorporación |
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

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.

2. Elija **Configuración**  >  **incorporación de puntos de**  >  **conexión** (en **Administración de dispositivos**). 

3. En la lista Seleccionar sistema operativo para iniciar el proceso **de incorporación,** seleccione un sistema operativo. 

4. En **Método de implementación,** seleccione una opción. Siga los vínculos y avisos para incorporar los dispositivos de la organización. ¿Necesita ayuda? Vea [Métodos de incorporación](#onboarding-methods) (en este artículo).

> [!NOTE]
> Si algo sale mal durante la incorporación, consulta Solucionar problemas de incorporación de Puntos de conexión [de Microsoft Defender.](troubleshoot-onboarding.md) En ese artículo se describe cómo resolver problemas de incorporación y errores comunes en los puntos de conexión.

### <a name="onboarding-methods"></a>Métodos de incorporación
 
Los métodos de implementación varían según el sistema operativo y los métodos preferidos. En la tabla siguiente se enumeran los recursos que le ayudarán a incorporarse a Defender for Endpoint:

|Sistemas operativos  |Métodos  |
|---------|---------|
| Windows 10     | [Directiva de grupo](configure-endpoints-gp.md)<br/>[Configuration Manager](configure-endpoints-sccm.md)<br/>[Administración de dispositivos móviles (Intune)](configure-endpoints-mdm.md)<br/>[Script local](configure-endpoints-script.md)<br/><br/>**NOTA:** Un script local es adecuado para una prueba de concepto, pero no debe usarse para la implementación de producción. Para una implementación de producción, se recomienda usar la directiva de grupo, Microsoft Endpoint Configuration Manager o Intune.         |
| Windows 8.1 Enterprise <br/>Windows 8.1 Pro <br/>Windows 7 SP1 Enterprise <br/>Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md)<br/><br/>**NOTA:** Microsoft Monitoring Agent es ahora agente de Azure Log Analytics. Para obtener más información, consulte [Log Analytics agent overview](/azure/azure-monitor/platform/log-analytics-agent).        |
| Windows Server 2019 y versiones posteriores <br/>Windows Edición principal de Server 2019 <br/>Windows Versión 1803 del servidor y versiones posteriores | [Script local](configure-endpoints-script.md) <br/>[Directiva de grupo](configure-endpoints-gp.md) <br/>[Configuration Manager](configure-endpoints-sccm.md) <br/>[System Center Configuration Manager](configure-endpoints-sccm.md) <br/>[Scripts de incorporación de VDI para dispositivos no persistentes](configure-endpoints-vdi.md) <br/><br/>**NOTA:** Un script local es adecuado para una prueba de concepto, pero no debe usarse para la implementación de producción. Para una implementación de producción, se recomienda usar la directiva de grupo, Microsoft Endpoint Configuration Manager o Intune.    |
| Windows Server 2016 <br/>Windows Server 2012 R2 <br/>Windows Server 2008 R2 SP1  | [Portal de Microsoft 365 Defender](configure-server-endpoints.md)<br/>[Azure Defender](/azure/security-center/security-center-wdatp) |
| macOS: 11.3.1 (Big Sur); 10.15 (Catalina); 10.14 (Mojave) | [Incorporar dispositivos que no tienen Windows](configure-endpoints-non-windows.md)  |
| iOS | [Incorporar dispositivos que no tienen Windows](configure-endpoints-non-windows.md)  |
| Linux: RHEL 7.2+; CentOS Linux 7.2+; Ubuntu 16 LTS o LTS superior; SLES 12+; Debian 9+; Oracle Linux 7.2 | [Incorporar dispositivos que no tienen Windows](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Ejecutar una prueba de detección

Para comprobar que los dispositivos incorporados están correctamente conectados a Defender for Endpoint, puedes ejecutar una prueba de detección.

|Sistema operativo  |Instrucciones  |
|---------|---------|
| Windows 10 <br/> Windows Server 2019<br/> Windows Servidor, versión 1803 o posterior<br/> Windows Server 2016<br/> Windows Server 2012 R2  | Consulte [Ejecutar una prueba de detección.](run-detection-test.md) <br/><br/>Visite el sitio de escenarios de demostración de Defender for Endpoint ( ) y [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) pruebe uno o varios de los escenarios. Por ejemplo, pruebe el escenario **de demostración de** protección entregado en la nube.    |
| macOS: 11.3.1 (Big Sur); 10.15 (Catalina); 10.14 (Mojave)    | Descargue y use la aplicación DE BRICOLAJE en [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <br/><br/>Para obtener más información, [vea Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md).        |
| Linux: RHEL 7.2+; CentOS Linux 7.2+; Ubuntu 16 LTS o LTS superior; SLES 12+; Debian 9+; Oracle Linux 7.2 | 1. Ejecute el siguiente comando y busque un resultado de **1**: <br/>`mdatp health --field real_time_protection_enabled`. <br/> 2. Abra una ventana terminal y ejecute el siguiente comando: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/> 3. Ejecute el siguiente comando para enumerar las amenazas detectadas: <br/>`mdatp threat list`. <br/><br/>Para obtener más información, [vea Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md). |

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>Confirme que Antivirus de Microsoft Defender está en modo pasivo en los puntos de conexión

Ahora que los puntos de conexión se han incorporado a Defender for Endpoint, el siguiente paso es asegurarse de que Antivirus de Microsoft Defender se está ejecutando en modo pasivo. Puede usar uno de varios métodos, como se describe en la tabla siguiente:

| Método  | Qué hacer  |
|:-------|:-------|
|Símbolo del sistema     | 1. En un dispositivo Windows, abra el símbolo del sistema. <br/> 2. Escriba `sc query windefend` y, a continuación, presione ENTRAR. <br/> 3. Revise los resultados para confirmar que Antivirus de Microsoft Defender se está ejecutando en modo pasivo.         |
| PowerShell     | 1. En un dispositivo Windows, abra Windows PowerShell como administrador. <br/> 2. Ejecute el siguiente cmdlet de PowerShell: `Get-MpComputerStatus | select AMRunningMode` . <br/> Revisar los resultados. Debería ver **el modo pasivo**.  |
| Seguridad de Windows app | 1. En un Windows, abra la aplicación Seguridad de Windows usuario. <br/>2. Seleccione **Virus & protección contra amenazas**.<br/>3. **¿Quién está protegiendo?** seleccione **Administrar proveedores**. <br/>4. En la página **Proveedores de** seguridad, en **Antivirus,** debería ver Antivirus de Microsoft Defender **está activado**. |
| Administrador de tareas | 1. En un dispositivo Windows, abra la aplicación Administrador de tareas. <br/>2. Seleccione la **pestaña** Detalles.<br/>3. Busque **MsMpEng.exe** en la lista. |

> [!NOTE]
> Es posible que *Antivirus de Windows Defender* en lugar *de Antivirus de Microsoft Defender* en algunas versiones de Windows.
> Para obtener más información sobre el modo pasivo y el modo activo, vea [Más detalles sobre Antivirus de Microsoft Defender estados](microsoft-defender-antivirus-compatibility.md#more-details-about-microsoft-defender-antivirus-states).

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>Establecer Antivirus de Microsoft Defender en Windows server en modo pasivo manualmente

Para establecer Antivirus de Microsoft Defender en modo pasivo en Windows Server, versión 1803 o posterior, o Windows Server 2019, siga estos pasos:

1. Abra el Editor del Registro y, a continuación, vaya a <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Edite (o cree) una entrada DWORD denominada **ForceDefenderPassiveMode** y especifique la siguiente configuración:
   - Establezca el valor de DWORD en **1**.
   - En **Base**, seleccione **Hexadecimal**.

> [!NOTE]
> Puede usar otros métodos para establecer la clave del Registro, como los siguientes:
>- [Preferencia de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Herramienta Objeto de directiva de grupo local](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Un paquete en Configuration Manager](/mem/configmgr/apps/deploy-use/packages-and-programs)

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

A continuación, el siguiente paso es desinstalar la solución de protección de puntos de conexión que no es de Microsoft. 

Para obtener ayuda con esta tarea, llegue al equipo de soporte técnico del proveedor de soluciones.

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>Asegúrese de que Defender for Endpoint funciona correctamente

Ahora que has incorporado a Defender for Endpoint y has desinstalado la solución anterior que no es de Microsoft, el siguiente paso es asegurarte de que Defender for Endpoint funciona correctamente. Una buena forma de realizar esta tarea es visitando el sitio de escenarios de demostración de Defender para endpoint ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Pruebe uno o varios de los escenarios de demostración de esa página, incluidos al menos los siguientes:

- Protección entregada en la nube
- Aplicaciones potencialmente no deseadas (PUA)
- Protección de red (NP)

## <a name="next-steps"></a>Siguientes pasos

**¡Enhorabuena!** Ha completado la migración [a Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)! 

- [Visite el panel de operaciones de seguridad](security-operations-dashboard.md) en el portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ). 
- [Administrar Defender para endpoint, después de la migración](manage-atp-post-migration.md).
