---
title: 'Symantec a Microsoft Defender para endpoint: fase 3, incorporación'
description: Esta es la fase 3, Incorporación, de migración de Symantec a Microsoft Defender para endpoint
keywords: migración, protección contra amenazas avanzada de Windows Defender, atp, edr
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
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: cc005c559e0f91f1c5888f8d7e4e7a2a420894db
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218705"
---
# <a name="migrate-from-symantec---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>Migrar desde Symantec- Fase 3: Incorporación a Microsoft Defender para endpoint

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: Preparar](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[Fase 1: Preparar](symantec-to-microsoft-defender-atp-prepare.md) |[![Fase 2: Configurar](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Fase 2: Configurar](symantec-to-microsoft-defender-atp-setup.md) |![Fase 3: Incorporación](images/phase-diagrams/onboard.png)<br/>Fase 3: Incorporación |
|--|--|--|
|| |*¡Estás aquí!* |


**Bienvenido a la fase 3 de [migración de Symantec a Microsoft Defender para Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)**. Esta fase de migración incluye los siguientes pasos:

1. [Incorporar dispositivos a Microsoft Defender para endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Ejecute una prueba de detección](#run-a-detection-test).
3. [Desinstalar Symantec](#uninstall-symantec).
4. [Asegúrese de que Microsoft Defender para endpoint está en modo activo](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode).

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Incorporación de dispositivos a Microsoft Defender para endpoint

1. Vaya al Centro de seguridad de Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) e inicie sesión.
2. Elija **Configuración**  >  **Administración de**  >  **dispositivos Incorporación**. 
3. En la lista Seleccionar sistema operativo para iniciar el proceso **de incorporación,** seleccione un sistema operativo. 
4. En **Método de implementación,** seleccione una opción. Siga los vínculos y avisos para incorporar los dispositivos de la organización. ¿Necesita ayuda? Vea [Métodos de incorporación](#onboarding-methods) (en este artículo).

### <a name="onboarding-methods"></a>Métodos de incorporación
 
Los métodos de implementación varían según el sistema operativo seleccionado. Consulte los recursos enumerados en la tabla siguiente para obtener ayuda con la incorporación.

|Sistema operativo  |Método  |
|---------|---------|
|Windows 10     |- [Directiva de grupo](configure-endpoints-gp.md)<br/>- [Configuration Manager](configure-endpoints-sccm.md)<br/>- [Administración de dispositivos móviles (Intune)](configure-endpoints-mdm.md)<br/>- [Script local](configure-endpoints-script.md) <br/><br/>**NOTA:** Un script local es adecuado para una prueba de concepto, pero no debe usarse para la implementación de producción. Para una implementación de producción, se recomienda usar la directiva de grupo, Microsoft Endpoint Configuration Manager o Intune.         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Agente de supervisión de Microsoft](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)<br/><br/>**NOTA:** Microsoft Monitoring Agent es ahora agente de Azure Log Analytics. Para obtener más información, consulte [Log Analytics agent overview](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).        |
|- Windows Server 2019 y versiones posteriores <br/>- Edición principal de Windows Server 2019 <br/>- Windows Server versión 1803 y versiones posteriores |- [Script local](configure-endpoints-script.md) <br/>- [Directiva de grupo](configure-endpoints-gp.md) <br/>- [Configuration Manager](/configure-endpoints-sccm.md) <br/>- [System Center Configuration Manager](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)<br/>- [Scripts de incorporación de VDI para dispositivos no persistentes](configure-endpoints-vdi.md) <br/><br/>**NOTA:** Un script local es adecuado para una prueba de concepto, pero no debe usarse para la implementación de producción. Para una implementación de producción, se recomienda usar la directiva de grupo, Microsoft Endpoint Configuration Manager o Intune.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Centro de seguridad de Microsoft Defender](configure-server-endpoints.md)<br/>- [Centro de seguridad de Azure](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (Sierra Alta)<br/><br/>iOS<br/><br/>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS o LTS superior<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Incorporación de dispositivos que no son de Windows](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Ejecutar una prueba de detección

Para comprobar que los dispositivos incorporados están correctamente conectados a Microsoft Defender para Endpoint, puede ejecutar una prueba de detección.

|Sistema operativo  |Instrucciones  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, versión 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |Consulte [Ejecutar una prueba de detección.](run-detection-test.md) <br/><br/>Visite el sitio de escenarios de demostración de Microsoft Defender para puntos de conexión ( ) y [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) pruebe uno o varios de los escenarios. Por ejemplo, pruebe el escenario **de demostración de** protección entregado en la nube.         |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (Sierra Alta)     |Descargue y use la aplicación DE BRICOLAJE en [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <br/><br/>Para obtener más información, vea [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md).        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS o LTS superior<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. Ejecute el siguiente comando y busque un resultado de **1**: <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. Abra una ventana terminal y ejecute el siguiente comando: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. Ejecute el siguiente comando para enumerar las amenazas detectadas: <br/>`mdatp threat list`. <br/><br/>Para obtener más información, vea [Microsoft Defender for Endpoint for Linux](microsoft-defender-endpoint-linux.md). |

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
   - Dispositivos Windows: desinstalar manualmente los clientes [de Endpoint Protection 14 en Windows](https://knowledge.broadcom.com/external/article?articleId=170040)
   - equipos macOS: [quitar software de Symantec para Mac con RemoveSymantecMacFiles](https://knowledge.broadcom.com/external/article?articleId=151387)
   - Dispositivos Linux: [preguntas más frecuentes para Endpoint Protection para Linux](https://knowledge.broadcom.com/external/article?articleId=162054)

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Asegúrese de que Microsoft Defender para endpoint está en modo activo

Ahora que ha desinstalado Symantec, el siguiente paso es asegurarse de que Antivirus de Microsoft Defender y Microsoft Defender para endpoint estén habilitados y en modo activo.

Para ello, visite el sitio de escenarios de demostración de Microsoft Defender para endpoint ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Pruebe uno o varios de los escenarios de demostración de esa página, incluidos al menos los siguientes:
- Protección entregada en la nube
- Aplicaciones potencialmente no deseadas (PUA)
- Protección de red (NP)

> [!IMPORTANT]
> Si usas Windows Server 2016, es posible que debas iniciar Antivirus de Microsoft Defender manualmente. Para ello, use el cmdlet de PowerShell `mpcmdrun.exe -wdenable` en el dispositivo.

## <a name="next-steps"></a>Pasos siguientes

**¡Enhorabuena!** Ha completado la migración [de Symantec a Microsoft Defender para Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)! 
- [Visite el panel de operaciones de seguridad](security-operations-dashboard.md) en el Centro de seguridad de Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Administrar Microsoft Defender para endpoint, post migration](manage-atp-post-migration.md).
