---
title: Administrar Microsoft Defender para endpoint con PowerShell, WMI y MPCmdRun.exe
description: Obtenga información sobre cómo administrar Microsoft Defender para endpoint con PowerShell, WMI y MPCmdRun.exe
keywords: post-migration, manage, operations, maintenance, utilization, PowerShell, WMI, MPCmdRun.exe, protección contra amenazas avanzada de Windows Defender, atp, edr
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
ms.openlocfilehash: 3d76beed9cb63fdbd56f9a97f925a99cbc01e1b8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070240"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>Administrar Microsoft Defender para endpoint con PowerShell, WMI y MPCmdRun.exe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Se recomienda usar [Microsoft Endpoint Manager para](https://docs.microsoft.com/mem) administrar las características de protección contra amenazas de su organización para dispositivos (también denominados puntos de conexión). Endpoint Manager incluye [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) y Microsoft Endpoint [Configuration Manager.](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) 
> - [Obtenga más información sobre Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview)
> - [Administrar Microsoft Defender para endpoint en dispositivos Windows 10 con Configuration Manager e Intune](manage-atp-post-migration-intune.md)
> - [Administrar Microsoft Defender para endpoint con Intune](manage-atp-post-migration-intune.md) 

Puedes administrar algunas opciones de configuración de Antivirus de Microsoft Defender en dispositivos con [PowerShell,](#configure-microsoft-defender-for-endpoint-with-powershell)Instrumental de administración de  [Windows](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) (WMI) y la Utilidad de línea de comandos de [Microsoft Malware Protection](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) (MPCmdRun.exe). Por ejemplo, puedes administrar algunas opciones de configuración de Antivirus de Microsoft Defender. Y, en algunos casos, puedes personalizar las reglas de reducción de superficie de ataque y la configuración de protección contra vulnerabilidades. 

> [!IMPORTANT]
> Las características de protección contra amenazas que configure mediante PowerShell, WMI o MCPmdRun.exe pueden sobrescribirse mediante las opciones de configuración implementadas con Intune o Configuration Manager.

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>Configurar Microsoft Defender para endpoint con PowerShell

Puede usar PowerShell para administrar el Antivirus de Microsoft Defender, la protección contra vulnerabilidades de seguridad y las reglas de reducción de superficie de ataque.

|Tarea  |Recursos para obtener más información  |
|---------|---------|
|**Administrar antivirus de Microsoft Defender** <br/><br/>*Ver el estado de la protección contra malware, configurar las preferencias de los exámenes antivirus & actualizaciones y realizar otros cambios en la protección antivirus.*    |[Usar cmdlets de PowerShell para configurar y administrar Antivirus de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus)  <br/><br/>[Usar cmdlets de PowerShell para habilitar la protección entregada en la nube](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)       |
|**Configurar la protección contra vulnerabilidades** de seguridad para mitigar las amenazas en los dispositivos de la organización<br/><br/> *Se recomienda usar la protección contra vulnerabilidades de seguridad en [el modo de auditoría](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) al principio. De este modo, puede ver cómo la protección contra vulnerabilidades afecta a las aplicaciones que usa su organización.*     | [Personalizar protección contra vulnerabilidades](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection)<br/><br/>[Cmdlets de PowerShell para protección contra vulnerabilidades](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)        |
|**Configurar reglas de reducción de superficie de ataque** con PowerShell <br/><br/>*Puede usar PowerShell para excluir archivos y carpetas de las reglas de reducción de superficie de ataque.* |[Personalizar reglas de reducción de superficie de ataque: usar PowerShell para excluir archivos & carpetas](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders)<br/><br/>Vea también la herramienta de interfaz gráfica de usuario de [António Vasconcelo](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)para establecer reglas de reducción de superficie de ataque con PowerShell . |
|**Habilitar la protección de red** con PowerShell <br/><br/>*Puede usar PowerShell para habilitar La protección de red.* |[Activar la protección de red con PowerShell](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#powershell) |
|**Configurar el acceso controlado a carpetas** para proteger contra ransomware <br/><br/>*[El acceso controlado a](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) carpetas también se conoce como protección antiransomware.* |[Habilitar el acceso controlado a carpetas con PowerShell](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell) |
|**Configurar Firewall de Microsoft Defender para** bloquear el tráfico de red no autorizado que entra o sale de los dispositivos de la organización |[Firewall de Microsoft Defender con administración avanzada de seguridad mediante Windows PowerShell](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell) |
|**Configurar el cifrado y BitLocker para** proteger la información en los dispositivos de la organización que ejecutan Windows |[Guía de referencia de PowerShell de BitLocker](https://docs.microsoft.com/powershell/module/bitlocker/?view=win10-ps&preserve-view=true) |

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>Configurar Microsoft Defender para endpoint con Instrumental de administración de Windows (WMI)

WMI es una interfaz de scripting que permite recuperar, modificar y actualizar la configuración. Para obtener más información, vea [Using WMI](https://docs.microsoft.com/windows/win32/wmisdk/using-wmi). 

|Tarea  |Recursos para obtener más información  |
|---------|---------|
|**Habilitar la protección de entrega en la nube** en un dispositivo    |[Usar Instrucciones de administración de Windows (WMI) para habilitar la protección entregada en la nube](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)       |
|**Recuperar, modificar y actualizar la configuración** del Antivirus de Microsoft Defender     | [Usar WMI para configurar y administrar Antivirus de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus)<br/><br/>[Revisar la lista de clases WMI disponibles y scripts de ejemplo](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <br/><br/>Vea también la información de referencia [Windows Defender de proveedor WMIv2 archivada](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)   |


## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Configurar Microsoft Defender para endpoint con Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe)

En un dispositivo individual, puede ejecutar un examen, iniciar el seguimiento de diagnóstico, comprobar si hay actualizaciones de inteligencia de seguridad y mucho más con la mpcmdrun.exe de línea de comandos. Puede encontrar la utilidad en `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Ejecutarlo desde un símbolo del sistema.

|Tarea  |Recursos para obtener más información  |
|---------|---------|
|**Administrar antivirus de Microsoft Defender**  |[Configurar y administrar Antivirus de Microsoft Defender con mpcmdrun.exe](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)        |

## <a name="configure-your-microsoft-defender-security-center"></a>Configurar el Centro de seguridad de Microsoft Defender

Si aún no lo ha hecho, configure el Centro de seguridad de **Microsoft Defender** ( ) para ver alertas, configurar características de protección contra amenazas y ver información detallada sobre la posición de seguridad general de su [https://securitycenter.windows.com](https://securitycenter.windows.com) organización. 

También puede configurar si los usuarios finales pueden ver y qué características pueden ver en el Centro de seguridad de Microsoft Defender.

- [Información general del Centro de seguridad de Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Protección de puntos de conexión: Centro de seguridad de Microsoft Defender](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)


## <a name="next-steps"></a>Pasos siguientes

- [Obtener información general sobre la administración de amenazas y vulnerabilidades](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visite el panel de operaciones de seguridad del Centro de seguridad de Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Administrar Microsoft Defender para endpoint con Intune](manage-atp-post-migration-intune.md)
