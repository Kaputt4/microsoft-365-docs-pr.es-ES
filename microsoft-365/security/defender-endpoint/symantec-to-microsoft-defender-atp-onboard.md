---
title: 'Symantec a Microsoft Defender para endpoint: fase 3, incorporación'
description: Esta es la fase 3, Incorporación, de migración de Symantec a Microsoft Defender para endpoint
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 05/14/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: f2b2d5ca9f841e36df37f025a9b5856fc7e2dc6a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538368"
---
# <a name="migrate-from-symantec---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>Migrar desde Symantec- Fase 3: Incorporación a Microsoft Defender para endpoint

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: Preparación](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[Fase 1: Preparación](symantec-to-microsoft-defender-atp-prepare.md) |[![Fase 2: Configuración](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Fase 2: Configuración](symantec-to-microsoft-defender-atp-setup.md) |![Fase 3: Incorporación](images/phase-diagrams/onboard.png)<br/>Fase 3: Incorporación |
|--|--|--|
|| |*¡Estás aquí!* |


**Bienvenido a la fase 3 de [migración de Symantec a Microsoft Defender para Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)**. Esta fase de migración incluye los siguientes pasos:

1. [Incorporar dispositivos a Microsoft Defender para endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).

2. [Ejecute una prueba de detección](#run-a-detection-test).

3. [Confirme que Antivirus de Microsoft Defender está en modo pasivo en los puntos de conexión](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints).

4. [Obtener actualizaciones para Antivirus de Microsoft Defender](#get-updates-for-microsoft-defender-antivirus).

5. [Desinstalar Symantec](#uninstall-symantec).

6. [Asegúrese de que Microsoft Defender para endpoint funciona correctamente.](#make-sure-microsoft-defender-for-endpoint-is-working-correctly)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Incorporar dispositivos a Microsoft Defender para punto de conexión

1. Vaya al Centro de seguridad de Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) e inicie sesión.

2. Elija **Configuración**  >  **incorporación de administración de**  >  **dispositivos**. 

3. En la lista Seleccionar sistema operativo para iniciar el proceso **de incorporación,** seleccione un sistema operativo. 

4. En **Método de implementación,** seleccione una opción. Siga los vínculos y avisos para incorporar los dispositivos de la organización. ¿Necesita ayuda? Vea [Métodos de incorporación](#onboarding-methods) (en este artículo).

### <a name="onboarding-methods"></a>Métodos de incorporación
 
Los métodos de implementación varían según el sistema operativo seleccionado. Consulte los recursos enumerados en la tabla siguiente para obtener ayuda con la incorporación.

|Sistema operativo  |Método  |
|---------|---------|
|Windows 10     | [Directiva de grupo](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[Administración de dispositivos móviles (Intune)](configure-endpoints-mdm.md)<p>[Script local](configure-endpoints-script.md) <br/>**NOTA:** Un script local es adecuado para una prueba de concepto, pero no debe usarse para la implementación de producción. Para una implementación de producción, se recomienda usar la directiva de grupo, Microsoft Endpoint Configuration Manager o Intune.         |
| Windows 8.1 Enterprise <p>Windows 8.1 Pro <p>Windows 7 SP1 Enterprise<p>Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)<br/>**NOTA:** Microsoft Monitoring Agent es ahora agente de Azure Log Analytics. Para obtener más información, consulte [Log Analytics agent overview](/azure/azure-monitor/platform/log-analytics-agent).        |
| Windows Server 2019 y versiones posteriores <p>Windows Edición principal de Server 2019<p>Windows Server version 1803 and later | [Script local](configure-endpoints-script.md)<p>[Directiva de grupo](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[System Center Configuration Manager](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)<p>[Scripts de incorporación de VDI para dispositivos no persistentes](configure-endpoints-vdi.md) <br/>**NOTA:** Un script local es adecuado para una prueba de concepto, pero no debe usarse para la implementación de producción. Para una implementación de producción, se recomienda usar la directiva de grupo, Microsoft Endpoint Configuration Manager o Intune.    |
| Windows Server 2016<p>Windows Server 2012 R2<p>Windows Server 2008 R2 SP1  | [Centro de seguridad de Microsoft Defender](configure-server-endpoints.md)<p>[Azure Defender](/azure/security-center/security-center-wdatp) |
|macOS<p>11.3.1 (Big Sur) <p>10.15 (Catalina)<p>10.14 (Mojave) |[Incorporar dispositivos que no tienen Windows](configure-endpoints-non-windows.md)  |
|iOS |[Incorporar dispositivos que no tienen Windows](configure-endpoints-non-windows.md)  |
|Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS o LTS superior<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 |[Incorporar dispositivos que no tienen Windows](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Ejecutar una prueba de detección

Para comprobar que los dispositivos incorporados están correctamente conectados a Microsoft Defender para Endpoint, puede ejecutar una prueba de detección.

|Sistema operativo  |Instrucciones  |
|---------|---------|
| Windows 10<p>Windows Server 2019<p>Windows Servidor, versión 1803<p>Windows Server 2016<p>Windows Server 2012 R2     |Consulte [Ejecutar una prueba de detección.](run-detection-test.md) <p>Visite el sitio de escenarios de demostración de Microsoft Defender para puntos de conexión ( ) y [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) pruebe uno o varios de los escenarios. Por ejemplo, pruebe el escenario **de demostración de** protección entregado en la nube.         |
|macOS:<p>11.3.1 (Big Sur)<p>10.15 (Catalina)<p>10.14 (Mojave)     |Descargue y use la aplicación DE BRICOLAJE en [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <p>Para obtener más información, vea [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md).        |
|Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS o LTS superior<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 |1. Ejecute el siguiente comando y busque un resultado de **1**: <br/>`mdatp health --field real_time_protection_enabled`. <p>2. Abra una ventana terminal y ejecute el siguiente comando: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. Ejecute el siguiente comando para enumerar las amenazas detectadas: <br/>`mdatp threat list`. <p>Para obtener más información, vea [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md). |

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>Confirme que Antivirus de Microsoft Defender está en modo pasivo en los puntos de conexión

Ahora que los puntos de conexión se han incorporado a Defender for Endpoint, el siguiente paso es asegurarse de que Antivirus de Microsoft Defender se está ejecutando en modo pasivo. Puede usar el símbolo del sistema o PowerShell para realizar esta tarea, como se describe en la tabla siguiente:

| Método    | Qué hacer |
|:--|:--|
| Símbolo del sistema    | 1. En un dispositivo Windows, abra el símbolo del sistema como administrador. <p>2. Escriba `sc query windefend` y, a continuación, presione ENTRAR. <p>3. Revise los resultados para confirmar que Antivirus de Microsoft Defender se está ejecutando en modo pasivo. |
|PowerShell | 1. En un dispositivo Windows, abra Windows PowerShell como administrador. <p>2. Ejecute el `Get-MpComputerStatus` cmdlet. <p>3. En la lista de resultados, busque **AMRunningMode: Passive Mode** o **AMRunningMode: SxS Passive Mode**. |

> [!NOTE]
> Es posible que Antivirus de Windows Defender en lugar de Antivirus de Microsoft Defender en algunas versiones de Windows.

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>Establecer Antivirus de Microsoft Defender en Windows server en modo pasivo manualmente

Para establecer Antivirus de Microsoft Defender en modo pasivo en Windows Server, versión 1803 o posterior, o Windows Server 2019, siga estos pasos:

1. Abra el Editor del Registro y, a continuación, vaya a `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` .

2. Edite (o cree) una entrada DWORD denominada **ForcePassiveMode** y especifique la siguiente configuración:

   - Establezca el valor de DWORD en 1.
   - En Base, seleccione Hexadecimal.

> [!NOTE]
> Puede usar otros métodos para establecer la clave del Registro, como los siguientes:
> - Preferencia de directiva de grupo
> - Herramienta Objeto de directiva de grupo local
> - Un paquete en Configuration Manager

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Inicie Antivirus de Microsoft Defender en Windows Server 2016

Si usas Windows Server 2016, es posible que deba empezar a Antivirus de Microsoft Defender manualmente. Para ello, use el cmdlet de PowerShell `mpcmdrun.exe -wdenable` en el dispositivo.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Obtener actualizaciones para Antivirus de Microsoft Defender

Mantener Antivirus de Microsoft Defender actualizado es fundamental para garantizar que los dispositivos tienen la tecnología y las características más recientes necesarias para protegerse contra nuevas técnicas de ataque y malware, incluso si Antivirus de Microsoft Defender se está ejecutando en modo pasivo.

Hay dos tipos de actualizaciones relacionadas con mantener Antivirus de Microsoft Defender actualizado:

- Actualizaciones de inteligencia de seguridad
- Actualizaciones de productos

Para obtener las actualizaciones, siga las instrucciones de [Manage Antivirus de Microsoft Defender updates y apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).

## <a name="uninstall-symantec"></a>Desinstalar Symantec

Ahora que ha incorporado los dispositivos de su organización a Microsoft Defender para Endpoint, el siguiente paso es desinstalar Symantec.

1. [Deshabilitar la protección contra alteraciones](https://knowledge.broadcom.com/external/article?legacyId=tech192023) en Symantec.

2. Elimine la contraseña de desinstalación de Symantec:<br/>

   1. En los dispositivos Windows, abra el Editor del Registro como administrador.

   2. Vaya a `HKEY_LOCAL_MACHINE\SOFTWARE\Symantec\Symantec Endpoint Protection\SMC`.

   3. Busque una entrada denominada **SmcInstData**. 

   4. Haga clic con el botón secundario en el elemento y, a continuación, **elija Eliminar**. 

3. Quite Symantec de los dispositivos. Si necesita ayuda con esto, consulte la documentación de Broadcom. Estos son algunos recursos de Broadcom: 

   - [Desinstalar Symantec Endpoint Protection](https://knowledge.broadcom.com/external/article/156148/uninstall-symantec-endpoint-protection.html)

   - Windows dispositivos: [desinstale manualmente Endpoint Protection 14 clientes en Windows](https://knowledge.broadcom.com/external/article?articleId=170040)
   
   - equipos macOS: [quitar software de Symantec para Mac con RemoveSymantecMacFiles](https://knowledge.broadcom.com/external/article?articleId=151387)
   
   - Dispositivos Linux: [preguntas más frecuentes Endpoint Protection en Linux](https://knowledge.broadcom.com/external/article?articleId=162054)

## <a name="make-sure-microsoft-defender-for-endpoint-is-working-correctly"></a>Asegúrese de que Microsoft Defender para endpoint funciona correctamente

Ahora que ha desinstalado Symantec, el siguiente paso es asegurarse de que Defender for Endpoint funciona correctamente. Visite el sitio de escenarios de demostración de Microsoft Defender para endpoint ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Pruebe uno o varios de los escenarios de demostración de esa página, incluidos al menos los siguientes:
- Protección entregada en la nube
- Aplicaciones potencialmente no deseadas (PUA)
- Protección de red (NP)

## <a name="next-steps"></a>Pasos siguientes

**¡Enhorabuena!** Ha completado la migración [de Symantec a Microsoft Defender para Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)! 
- [Visite el panel de operaciones de seguridad](security-operations-dashboard.md) en el Centro de seguridad de Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Administrar Microsoft Defender para endpoint, post migration](manage-atp-post-migration.md).
