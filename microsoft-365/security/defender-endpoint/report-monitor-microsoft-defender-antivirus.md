---
title: Supervisar e informar sobre la Antivirus de Microsoft Defender protección
description: Use Configuration Manager o herramientas de administración de eventos y de información de seguridad (SIEM) para consumir informes y supervisar Microsoft Defender AV con PowerShell y WMI.
keywords: siem, monitor, informe, Av. de Microsoft Defender
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
ms.openlocfilehash: 9e2efd5f5354b84f7a10f1a9284ca812014240a1
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2021
ms.locfileid: "61121966"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Informe en el Antivirus de Windows Defender

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Antivirus de Microsoft Defender está integrado en Windows 10, Windows 11, Windows Server 2019, Windows Server 2022 y Windows Server 2016. Antivirus de Microsoft Defender es de la protección de próxima generación en Microsoft Defender para endpoint. La protección de última generación ayuda a proteger los dispositivos de amenazas de software como virus, malware y spyware en el correo electrónico, las aplicaciones, la nube y la web.

Con Antivirus de Microsoft Defender, tiene varias opciones para revisar el estado de protección y las alertas. Puede usar Microsoft Endpoint Manager para [supervisar Antivirus de Microsoft Defender](/configmgr/protect/deploy-use/monitor-endpoint-protection) o [crear alertas de correo electrónico](/configmgr/protect/deploy-use/endpoint-configure-alerts). O bien, puede supervisar la protección mediante [Microsoft Intune](/intune/introduction-intune).

Si tiene un servidor de administración de eventos (SIEM) y de información de seguridad de terceros, también puede consumir Windows Defender [eventos de cliente](/windows/win32/events/windows-events).

Windows incluyen varios orígenes de eventos de seguridad, incluidos los eventos del Administrador [](/windows/device-security/auditing/security-auditing-overview) de cuentas de seguridad (SAM) (mejorados para[Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), vea también el tema Auditoría de seguridad) y [Windows Defender eventos](troubleshoot-microsoft-defender-antivirus.md).

Estos eventos se pueden agregar de forma centralizada mediante [el recopilador Windows eventos](/windows/win32/wec/windows-event-collector). A menudo, los servidores SIEM tienen conectores para Windows eventos, lo que le permite correlacionar todos los eventos de seguridad del servidor SIEM.

También puede supervisar [eventos de malware mediante la solución de evaluación de malware en Log Analytics](/azure/log-analytics/log-analytics-malware).

Para supervisar o determinar el estado con PowerShell, WMI o Microsoft Azure, vea [la tabla (Opciones](deploy-manage-report-microsoft-defender-antivirus.md#ref2)de implementación, administración e informes).

## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Implementar Antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
