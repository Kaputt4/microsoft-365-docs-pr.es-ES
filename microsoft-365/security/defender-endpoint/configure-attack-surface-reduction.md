---
title: Configurar capacidades de reducción de superficie de ataque
description: Use Microsoft Intune, Microsoft Endpoint Configuration Manager, cmdlets de PowerShell y directiva de grupo para configurar la reducción de superficie de ataque.
keywords: asr, reducción de superficie de ataque, Windows Defender, Microsoft Defender, antivirus, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: d2f984e21338e2f9a4ed579cde2d74339031d649
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770966"
---
# <a name="configure-attack-surface-reduction-capabilities"></a>Configurar capacidades de reducción de superficie de ataque

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> ¿Desea experimentar Defender for Endpoint? [Registrarse para obtener una versión de prueba gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).

Defender for Endpoint incluye varias capacidades de reducción de superficie de ataque. Para obtener más información, vea [Overview of attack surface reduction capabilities](overview-attack-surface-reduction.md). Para configurar la reducción de superficie de ataque en el entorno, siga estos pasos: 

1. [Habilitar el aislamiento basado en hardware para Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).

2. Habilitar el control de aplicaciones. 

   1. Revise las directivas base en Windows. Vea [el ejemplo de directivas base](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).
   2. Consulte la [guía de diseño del control de aplicaciones](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).
   3. Consulte la guía [de diseño del control de aplicaciones](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).

3. [Habilitar el acceso controlado a carpetas](enable-controlled-folders.md).

4. [Activar Protección de red](enable-network-protection.md).

5. [Habilitar protección contra vulnerabilidades](enable-exploit-protection.md)de seguridad .

6. [Configurar reglas de reducción de superficie de ataque](enable-attack-surface-reduction.md).

7. Configurar el firewall de red.

   1. Obtenga una introducción a [Firewall de Windows Defender con seguridad avanzada](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).
   2. Use la [Firewall de Windows Defender de diseño para](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) decidir cómo desea diseñar las directivas de firewall.
   3. Use la [Firewall de Windows Defender de implementación para](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) configurar el firewall de su organización con seguridad avanzada. 

> [!TIP]
> En la mayoría de los casos, al configurar las capacidades de reducción de superficie de ataque, puedes elegir entre varios métodos:
> - Microsoft Endpoint Manager (que ahora incluye Microsoft Intune y Microsoft Endpoint Configuration Manager)
> - Directiva de grupo
> - Cmdlets de PowerShell
