---
title: Administración de Microsoft Defender para punto de conexión mediante PowerShell, WMI y MPCmdRun.exe
description: Aprenda a administrar Microsoft Defender para punto de conexión con PowerShell, WMI y MPCmdRun.exe
keywords: posterior a la migración, administración, operaciones, mantenimiento, uso, PowerShell, WMI, MPCmdRun.exe, Microsoft Defender para punto de conexión, edr
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
- m365solution-scenario
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.reviewer: chventou
ms.openlocfilehash: 3976a8bebb1fc37b3a3dbde937064bfbfdee2671
ms.sourcegitcommit: 35f167725bec5fd4fe131781a53d96b060cf232d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "65872944"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>Administración de Microsoft Defender para punto de conexión con PowerShell, WMI y MPCmdRun.exe

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Se recomienda usar [Microsoft Endpoint Manager](/mem) para administrar las características de protección contra amenazas de su organización para dispositivos (también conocidos como puntos de conexión). Endpoint Manager incluye [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction).
>
> - [Más información sobre Endpoint Manager](/mem/endpoint-manager-overview)
> - [Administración conjunta de Microsoft Defender para punto de conexión en dispositivos Windows 10 y Windows 11 con Configuration Manager y Intune](manage-mde-post-migration-intune.md)
> - [Administración de Microsoft Defender para punto de conexión con Intune](manage-mde-post-migration-intune.md)

Puede administrar algunas configuraciones de Antivirus de Microsoft Defender en dispositivos con [PowerShell](#configure-microsoft-defender-for-endpoint-with-powershell), [instrumental de administración de Windows](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) (WMI) y la [utilidad de línea de comandos de Microsoft Malware Protection](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) (MPCmdRun.exe). Por ejemplo, puede administrar algunos Antivirus de Microsoft Defender configuración. Y, en algunos casos, puede personalizar las reglas de reducción de superficie expuesta a ataques y la configuración de protección contra vulnerabilidades de seguridad.

> [!IMPORTANT]
> Las características de protección contra amenazas que configure mediante PowerShell, WMI o MCPmdRun.exe se pueden sobrescribir mediante los valores de configuración que se implementan con Intune o Configuration Manager.

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>Configuración de Microsoft Defender para punto de conexión con PowerShell

Puede usar PowerShell para administrar Antivirus de Microsoft Defender, la protección contra vulnerabilidades de seguridad y las reglas de reducción de la superficie expuesta a ataques.

|Task|Recursos para obtener más información|
|---|---|
|**Administrar Antivirus de Microsoft Defender** <br/><br/> Ver el estado de la protección antimalware, configurar las preferencias de los exámenes antivirus & actualizaciones y realizar otros cambios en la protección antivirus.*|[Uso de cmdlets de PowerShell para configurar y administrar Antivirus de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus) <br/><br/> [Uso de cmdlets de PowerShell para habilitar la protección entregada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)|
|**Configuración de la protección contra vulnerabilidades de seguridad** para mitigar las amenazas en los dispositivos de la organización <br/><br/> *Se recomienda usar la protección contra vulnerabilidades de seguridad en [el modo de auditoría](/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) al principio. De este modo, puede ver cómo afecta la protección contra vulnerabilidades de seguridad a las aplicaciones que usa su organización.*|[Personalizar la protección contra vulnerabilidades de seguridad](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/> [Cmdlets de PowerShell para la protección contra vulnerabilidades de seguridad](/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)|
|**Configuración de reglas de reducción de superficie expuesta a ataques** con PowerShell <br/><br/> *Puede usar PowerShell para excluir archivos y carpetas de las reglas de reducción de la superficie expuesta a ataques.*|[Personalización de reglas de reducción de superficie expuesta a ataques: use PowerShell para excluir archivos & carpetas](/microsoft-365/security/defender-endpoint/enable-attack-surface-reduction) <br/><br/> Además, consulte la [herramienta gráfica de interfaz de usuario de António Vasconcelo para establecer reglas de reducción de superficie expuesta a ataques con PowerShell](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI).|
|**Habilitación de la protección de red** con PowerShell <br/><br/> *Puede usar PowerShell para habilitar la protección de red.*|[Activar la protección de red con PowerShell](/microsoft-365/security/defender-endpoint/enable-network-protection#powershell)|
|**Configuración del acceso controlado a carpetas** para protegerse frente a ransomware <br/><br/> *[El acceso controlado a carpetas](/microsoft-365/security/defender-endpoint/controlled-folders) también se conoce como protección contra antiransomware.*|[Habilitación del acceso controlado a carpetas con PowerShell](/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell)|
|**Configurar Firewall de Microsoft Defender** para bloquear el tráfico de red no autorizado que fluye dentro o fuera de los dispositivos de la organización|[Firewall de Microsoft Defender con Advanced Security Administration mediante Windows PowerShell](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell)|
|**Configure el cifrado y BitLocker** para proteger la información sobre los dispositivos de la organización que ejecutan Windows|[Guía de referencia de PowerShell de BitLocker](/powershell/module/bitlocker/)|

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>Configuración de Microsoft Defender para punto de conexión con instrumental de administración de Windows (WMI)

WMI es una interfaz de scripting que permite recuperar, modificar y actualizar la configuración. Para más información, consulte [Uso de WMI](/windows/win32/wmisdk/using-wmi).<br/><br/>

|Task|Recursos para obtener más información|
|---|---|
|**Habilitación de la protección entregada** en la nube en un dispositivo|[Uso de Windows Management Instruction (WMI) para habilitar la protección entregada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)|
|**Recuperar, modificar y actualizar la configuración de** Antivirus de Microsoft Defender|[Use WMI para configurar y administrar Antivirus de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus <br/><br/> [Revise la lista de clases WMI disponibles y scripts de ejemplo.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <br/><br/> Consulte también la [información de referencia del proveedor de WMIv2 Windows Defender](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN) archivado|

## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Configuración de Microsoft Defender para punto de conexión con microsoft Malware Protection Command-Line Utility (MPCmdRun.exe)

En un dispositivo individual, puede ejecutar un examen, iniciar el seguimiento de diagnóstico, buscar actualizaciones de inteligencia de seguridad y mucho más mediante la herramienta de línea de comandos mpcmdrun.exe. Puede encontrar la utilidad en `%ProgramFiles%\Windows Defender\MpCmdRun.exe`. Ejecútelo desde un símbolo del sistema.

Para más información, consulte [Configuración y administración de Antivirus de Microsoft Defender con mpcmdrun.exe](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus).

## <a name="configure-your-microsoft-365-defender-portal"></a>Configuración del portal de Microsoft 365 Defender

Si aún no lo ha hecho, configure <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">el portal de Microsoft 365 Defender</a> para ver alertas, configurar características de protección contra amenazas y ver información detallada sobre la posición de seguridad general de su organización.

También puede configurar si y qué características pueden ver los usuarios finales en el Centro de seguridad de Microsoft Defender.

- [Introducción a la Centro de seguridad de Microsoft Defender](/microsoft-365/security/defender-endpoint/use)
- [Endpoint Protection: Centro de seguridad de Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Siguientes pasos

- [Introducción a la administración de amenazas y vulnerabilidades](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Visite el panel de operaciones de seguridad de Centro de seguridad de Microsoft Defender](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
- [Administración de Microsoft Defender para punto de conexión con Intune](manage-mde-post-migration-intune.md)
