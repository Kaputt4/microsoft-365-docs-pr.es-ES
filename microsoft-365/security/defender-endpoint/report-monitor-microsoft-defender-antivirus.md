---
title: Supervisión e informe sobre Microsoft Defender protección antivirus
description: Use Configuration Manager o herramientas de administración de eventos e información de seguridad (SIEM) para consumir informes y supervisar Microsoft Defender Antivirus con PowerShell y WMI.
keywords: siem, monitor, report, Microsoft Defender AV, Microsoft Defender Antivirus
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.topic: conceptual
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: d05764db303fd06bda8ee178a97009f4875e7b72
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68641301"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Informe en el Antivirus de Windows Defender

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Microsoft Defender Antivirus está integrado en Windows 10, Windows 11, Windows Server 2019, Windows Server 2022 y Windows Server 2016. Microsoft Defender Antivirus es una protección de última generación en Microsoft Defender para punto de conexión. La protección de última generación ayuda a proteger los dispositivos frente a amenazas de software como virus, malware y spyware en el correo electrónico, las aplicaciones, la nube y la web.

Con Microsoft Defender Antivirus, tiene varias opciones para revisar el estado de protección y las alertas. Puede usar Microsoft Endpoint Manager para [supervisar Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) o [crear alertas de correo electrónico](/configmgr/protect/deploy-use/endpoint-configure-alerts). O bien, puede supervisar la protección mediante [Microsoft Intune](/intune/introduction-intune).

Si tiene un servidor de administración de eventos e información de seguridad (SIEM) de terceros, también puede consumir [Windows डिफेन्डर eventos de cliente](/windows/win32/events/windows-events).

Los eventos de Windows constan de varios orígenes de eventos de seguridad, incluidos los eventos del Administrador de cuentas de seguridad (SAM) ([mejorados para Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), también consulte el tema [Auditoría de seguridad](/windows/security/threat-protection/auditing/security-auditing-overview)) y [eventos de Windows डिफेन्डर](troubleshoot-microsoft-defender-antivirus.md).

Estos eventos se pueden agregar centralmente mediante el [recopilador de eventos de Windows](/windows/win32/wec/windows-event-collector). A menudo, los servidores SIEM tienen conectores para eventos de Windows, lo que le permite correlacionar todos los eventos de seguridad en el servidor SIEM.

También puede [supervisar eventos de malware mediante la solución de evaluación de malware en Log Analytics](/security/benchmark/azure/security-control-logging-monitoring).

Para supervisar o determinar el estado con PowerShell, WMI o Microsoft Azure, consulte la [tabla (Implementación, administración y opciones de informes).](deploy-manage-report-microsoft-defender-antivirus.md#ref2)

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)

## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Implementación de Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
