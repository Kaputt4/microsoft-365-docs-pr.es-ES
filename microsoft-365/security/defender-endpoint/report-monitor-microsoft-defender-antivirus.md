---
title: Supervisión e informe sobre la protección Antivirus de Microsoft Defender
description: Use Configuration Manager o herramientas de administración de eventos e información de seguridad (SIEM) para consumir informes y supervisar el antivirus de Microsoft Defender con PowerShell y WMI.
keywords: siem, monitor, report, Av. de Microsoft Defender
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: c36902d6c636c726a42292d7a6e4f0cdec60edb7
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2022
ms.locfileid: "65415115"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Informe en el Antivirus de Windows Defender

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Antivirus de Microsoft Defender está integrado en Windows 10, Windows 11, Windows Server 2019, Windows Server 2022 y Windows Server 2016. Antivirus de Microsoft Defender es la protección de última generación en Microsoft Defender para punto de conexión. La protección de última generación ayuda a proteger los dispositivos frente a amenazas de software como virus, malware y spyware en el correo electrónico, las aplicaciones, la nube y la web.

Con Antivirus de Microsoft Defender, tiene varias opciones para revisar el estado de protección y las alertas. Puede usar Microsoft Endpoint Manager para [supervisar Antivirus de Microsoft Defender](/configmgr/protect/deploy-use/monitor-endpoint-protection) o [crear alertas de correo electrónico](/configmgr/protect/deploy-use/endpoint-configure-alerts). O bien, puede supervisar la protección mediante [Microsoft Intune](/intune/introduction-intune).

Si tiene un servidor de administración de eventos e información de seguridad (SIEM) de terceros, también puede consumir [Windows Defender eventos de cliente](/windows/win32/events/windows-events).

Windows eventos constan de varios orígenes de eventos de seguridad, incluidos los eventos del Administrador de cuentas de seguridad (SAM) ([mejorados para Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), consulte también el tema [Auditoría de seguridad](/windows/device-security/auditing/security-auditing-overview)) y [eventos de Windows Defender](troubleshoot-microsoft-defender-antivirus.md).

Estos eventos se pueden agregar centralmente mediante el [recopilador de eventos de Windows](/windows/win32/wec/windows-event-collector). A menudo, los servidores SIEM tienen conectores para eventos de Windows, lo que le permite correlacionar todos los eventos de seguridad en el servidor SIEM.

También puede [supervisar eventos de malware mediante la solución de evaluación de malware en Log Analytics](/azure/log-analytics/log-analytics-malware).

Para supervisar o determinar el estado con PowerShell, WMI o Microsoft Azure, consulte la [tabla (Implementación, administración y opciones de informes).](deploy-manage-report-microsoft-defender-antivirus.md#ref2)

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)

## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Implementación de Antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
