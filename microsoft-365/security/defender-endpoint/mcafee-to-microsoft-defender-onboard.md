---
title: McAfee to Microsoft Defender for Endpoint - Onboard
description: Esta es la fase 3, Incorporación, para migrar de McAfee a Microsoft Defender para endpoint.
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
- m365solution-McAfeemigrate
- m365solution-scenario
ms.custom: migrationguides
ms.topic: article
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: c30a552b4a2abcea9ceff4968c2a9e7e32ff2450
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862084"
---
# <a name="migrate-from-mcafee---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>Migrar desde McAfee- Fase 3: Incorporación a Microsoft Defender para endpoint

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


|[![Fase 1: Preparación](images/phase-diagrams/prepare.png)](mcafee-to-microsoft-defender-prepare.md)<br/>[Fase 1: Preparación](mcafee-to-microsoft-defender-prepare.md) |[![Fase 2: Configuración](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[Fase 2: Configuración](mcafee-to-microsoft-defender-setup.md) |![Fase 3: Incorporación](images/phase-diagrams/onboard.png)<br/>Fase 3: Incorporación |
|--|--|--|
|| |*¡Estás aquí!* |

Bienvenido a la fase 3 de migración de **[McAfee Endpoint Security (McAfee) a Protección](mcafee-to-microsoft-defender-migration.md#the-migration-process)** contra amenazas avanzada de Microsoft Defender (Microsoft Defender para endpoint). Esta fase de migración incluye los siguientes pasos:

1. [Incorporar dispositivos a Microsoft Defender para endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Ejecute una prueba de detección](#run-a-detection-test).
3. [Desinstalar McAfee](#uninstall-mcafee).
4. [Asegúrese de que Microsoft Defender para endpoint está en modo activo](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode).

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Incorporar dispositivos a Microsoft Defender para punto de conexión

1. Vaya al Centro de seguridad de Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) e inicie sesión.

2. Elija **Configuración**  >  **Administración de**  >  **dispositivos Incorporación**. 

3. En la lista Seleccionar sistema operativo para iniciar el proceso **de incorporación,** seleccione un sistema operativo. 

4. En **Método de implementación,** seleccione una opción. Siga los vínculos y avisos para incorporar los dispositivos de la organización. ¿Necesita ayuda? Vea [Métodos de incorporación](#onboarding-methods) (en este artículo).

### <a name="onboarding-methods"></a>Métodos de incorporación
 
Los métodos de implementación varían según el sistema operativo seleccionado. Consulte los recursos enumerados en la tabla siguiente para obtener ayuda con la incorporación.

|Sistema operativo  |Método  |
|---------|---------|
|Windows 10     |- [Directiva de grupo](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)<br/>- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)<br/>- [Administración de dispositivos móviles (Intune)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-mdm)<br/>- [Script local](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/><br/>**NOTA:** Un script local es adecuado para una prueba de concepto, pero no debe usarse para la implementación de producción. Para una implementación de producción, se recomienda usar la directiva de grupo, Microsoft Endpoint Configuration Manager o Intune.         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Agente de supervisión de Microsoft](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-atp)<br/><br/>**NOTA:** Microsoft Monitoring Agent es ahora agente de Azure Log Analytics. Para obtener más información, consulte [Log Analytics agent overview](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).        |
|- Windows Server 2019 y versiones posteriores <br/>- Edición principal de Windows Server 2019 <br/>- Windows Server versión 1803 y versiones posteriores |- [Script local](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/>- [Directiva de grupo](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp) <br/>- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm) <br/>- [System Center Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#onboard-windows-10-devices-using-earlier-versions-of-system-center-configuration-manager) <br/>- [Scripts de incorporación de VDI para dispositivos no persistentes](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi) <br/><br/>**NOTA:** Un script local es adecuado para una prueba de concepto, pero no debe usarse para la implementación de producción. Para una implementación de producción, se recomienda usar la directiva de grupo, Microsoft Endpoint Configuration Manager o Intune.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Centro de seguridad de Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#option-1-onboard-servers-through-microsoft-defender-security-center)<br/>- [Centro de seguridad de Azure](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (Sierra Alta)<br/><br/>iOS<br/><br/>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS o LTS superior<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Incorporar dispositivos que no tienen Windows](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-non-windows)  |

## <a name="run-a-detection-test"></a>Ejecutar una prueba de detección

Para comprobar que los dispositivos incorporados están correctamente conectados a Microsoft Defender para Endpoint, puede ejecutar una prueba de detección.


|Sistema operativo  |Instrucciones  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, versión 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |Consulte [Ejecutar una prueba de detección.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test) <br/><br/>Visite el sitio de escenarios de demostración de Microsoft Defender para puntos de conexión ( ) y [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) pruebe uno o varios de los escenarios. Por ejemplo, pruebe el escenario **de demostración de** protección entregado en la nube.         |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (Sierra Alta)     |Descargue y use la aplicación DE BRICOLAJE en [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <br/><br/>Para obtener más información, vea [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac).        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS o LTS superior<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. Ejecute el siguiente comando y busque un resultado de **1**: <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. Abra una ventana terminal y ejecute el siguiente comando: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. Ejecute el siguiente comando para enumerar las amenazas detectadas: <br/>`mdatp threat list`. <br/><br/>Para obtener más información, vea [Microsoft Defender for Endpoint for Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux). |

## <a name="uninstall-mcafee"></a>Desinstalar McAfee

Ahora que ha incorporado los dispositivos de su organización a Microsoft Defender para Endpoint, el siguiente paso es desinstalar McAfee.

Para obtener ayuda con este paso, vaya a su McAfee ServicePortal ( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) ).

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Asegúrese de que Microsoft Defender para endpoint está en modo activo

Ahora que ha desinstalado McAfee, el siguiente paso es asegurarse de que el Antivirus de Microsoft Defender y la detección y respuesta de puntos de conexión están habilitados y en modo activo.

Para ello, visite el sitio de escenarios de demostración de Microsoft Defender para endpoint ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Pruebe uno o varios de los escenarios de demostración de esa página, incluidos al menos los siguientes:
- Protección entregada en la nube
- Aplicaciones potencialmente no deseadas (PUA)
- Protección de red (NP)

> [!IMPORTANT]
> Si usas Windows Server 2016, es posible que debas iniciar Antivirus de Microsoft Defender manualmente. Para ello, use el cmdlet de PowerShell `mpcmdrun.exe -wdenable` en el dispositivo.

## <a name="next-steps"></a>Siguientes pasos

**¡Enhorabuena!** Ha completado la migración [de McAfee a Microsoft Defender para Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)! 

- [Visite el panel de operaciones de seguridad](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard) en el Centro de seguridad de Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Administrar protección contra amenazas avanzada de Microsoft Defender, después de la migración](manage-atp-post-migration.md).
