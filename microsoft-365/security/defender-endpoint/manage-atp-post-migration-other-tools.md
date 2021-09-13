---
title: Administrar Microsoft Defender para endpoint con PowerShell, WMI y MPCmdRun.exe
description: Obtenga información sobre cómo administrar Microsoft Defender para endpoint con PowerShell, WMI y MPCmdRun.exe
keywords: post-migration, manage, operations, maintenance, utilization, PowerShell, WMI, MPCmdRun.exe, Microsoft Defender for Endpoint, edr
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
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: b20107b33a0bff72375885b11f205fa915a3b718
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59166979"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>Administrar Microsoft Defender para endpoint con PowerShell, WMI y MPCmdRun.exe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Se recomienda usar [Microsoft Endpoint Manager](/mem) para administrar las características de protección contra amenazas de la organización para dispositivos (también denominados puntos de conexión). Endpoint Manager incluye [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction).
>
> - [Obtenga más información sobre Endpoint Manager](/mem/endpoint-manager-overview)
> - [Co-administrar Microsoft Defender para endpoint en Windows 10 dispositivos con Configuration Manager e Intune](manage-atp-post-migration-intune.md)
> - [Administrar Microsoft Defender para endpoint con Intune](manage-atp-post-migration-intune.md)

Puede administrar algunas opciones Antivirus de Microsoft Defender en dispositivos con [PowerShell](#configure-microsoft-defender-for-endpoint-with-powershell), instrumental de administración de [Windows](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) (WMI) y la utilidad de línea de comandos de Protección contra malware de [Microsoft](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) (MPCmdRun.exe). Por ejemplo, puede administrar algunas opciones Antivirus de Microsoft Defender configuración. Y, en algunos casos, puedes personalizar las reglas de reducción de superficie de ataque y la configuración de protección contra vulnerabilidades.

> [!IMPORTANT]
> Las características de protección contra amenazas que configure mediante PowerShell, WMI o MCPmdRun.exe pueden sobrescribirse mediante las opciones de configuración implementadas con Intune o Configuration Manager.

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>Configurar Microsoft Defender para endpoint con PowerShell

Puede usar PowerShell para administrar el Antivirus de Microsoft Defender, la protección contra vulnerabilidades y las reglas de reducción de superficie de ataque.

|Tarea|Recursos para obtener más información|
|---|---|
|**Administrar Antivirus de Microsoft Defender** <p> Ver el estado de la protección antimalware, configurar las preferencias para los exámenes antivirus & actualizaciones y realizar otros cambios en la protección antivirus.*|[Use cmdlets de PowerShell para configurar y administrar Antivirus de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus) <p> [Usar cmdlets de PowerShell para habilitar la protección entregada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)|
|**Configurar la protección contra vulnerabilidades** de seguridad para mitigar las amenazas en los dispositivos de la organización <p> *Se recomienda usar la protección contra vulnerabilidades de seguridad en [el modo de auditoría](/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) al principio. De este modo, puede ver cómo la protección contra vulnerabilidades afecta a las aplicaciones que usa su organización.*|[Personalizar la protección contra vulnerabilidades de seguridad](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <p> [Cmdlets de PowerShell para protección contra vulnerabilidades](/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)|
|**Configurar reglas de reducción de superficie de ataque** con PowerShell <p> *Puede usar PowerShell para excluir archivos y carpetas de las reglas de reducción de superficie de ataque.*|[Personalizar reglas de reducción de superficie de ataque: usar PowerShell para excluir archivos & carpetas](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders) <p> Vea también la herramienta de interfaz gráfica de usuario de [António Vasconcelo](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)para establecer reglas de reducción de superficie de ataque con PowerShell .|
|**Habilitar la protección de red** con PowerShell <p> *Puede usar PowerShell para habilitar La protección de red.*|[Activar la protección de red con PowerShell](/microsoft-365/security/defender-endpoint/enable-network-protection#powershell)|
|**Configurar el acceso controlado a carpetas** para proteger contra ransomware <p> *[El acceso controlado a](/microsoft-365/security/defender-endpoint/controlled-folders) carpetas también se conoce como protección antiransomware.*|[Habilitar el acceso controlado a carpetas con PowerShell](/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell)|
|**Configurar Firewall de Microsoft Defender para** bloquear el tráfico de red no autorizado que entra o sale de los dispositivos de la organización|[Firewall de Microsoft Defender con administración avanzada de seguridad mediante Windows PowerShell](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell)|
|**Configurar el cifrado y BitLocker** para proteger la información en los dispositivos de la organización que se ejecutan Windows|[Guía de referencia de PowerShell de BitLocker](/powershell/module/bitlocker/)|

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>Configurar Microsoft Defender para endpoint con Windows Management Instrumentation (WMI)

WMI es una interfaz de scripting que permite recuperar, modificar y actualizar la configuración. Para obtener más información, vea [Using WMI](/windows/win32/wmisdk/using-wmi).

|Tarea|Recursos para obtener más información|
|---|---|
|**Habilitar la protección de entrega en la nube** en un dispositivo|[Use Windows Management Instruction (WMI) para habilitar la protección entregada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)|
|**Recuperar, modificar y actualizar la configuración** de Antivirus de Microsoft Defender|[Usar WMI para configurar y administrar Antivirus de Microsoft Defender] (/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus <p> [Revisar la lista de clases WMI disponibles y scripts de ejemplo](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <p> Vea también la información de referencia [Windows Defender de proveedor WMIv2 archivada](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)|

## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Configurar Microsoft Defender para endpoint con Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe)

En un dispositivo individual, puede ejecutar un examen, iniciar el seguimiento de diagnóstico, comprobar si hay actualizaciones de inteligencia de seguridad y mucho más con la mpcmdrun.exe de línea de comandos. Puede encontrar la utilidad en `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Ejecutarlo desde un símbolo del sistema.

|Tarea|Recursos para obtener más información|
|---|---|
|**Administrar Antivirus de Microsoft Defender**|[Configurar y administrar Antivirus de Microsoft Defender con mpcmdrun.exe](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)|

## <a name="configure-your-microsoft-365-defender-portal"></a>Configurar el portal Microsoft 365 Defender web

Si aún no lo ha hecho, configure el portal de [Microsoft 365 Defender](https://security.microsoft.com/) para ver alertas, configurar características de protección contra amenazas y ver información detallada sobre la posición de seguridad general de su organización.

También puede configurar si los usuarios finales pueden ver y qué características pueden ver en el Centro de seguridad de Microsoft Defender.

- [Información general sobre el Centro de seguridad de Microsoft Defender](/microsoft-365/security/defender-endpoint/use)

- [Protección de extremo: Centro de seguridad de Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Pasos siguientes

- [Introducción a la administración de amenazas y vulnerabilidades](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visite el panel Centro de seguridad de Microsoft Defender operaciones de seguridad](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Administrar Microsoft Defender para endpoint con Intune](manage-atp-post-migration-intune.md)
