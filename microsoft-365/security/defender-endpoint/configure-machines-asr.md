---
title: Optimizar la implementación y las detecciones de reglas de ASR
description: Optimice las reglas de reducción de la superficie expuesta a ataques (ASR) para identificar y evitar vulnerabilidades de seguridad típicas de malware.
keywords: onboard, Intune management, Microsoft Defender para punto de conexión, Microsoft Defender, Windows डिफेन्डर, attack surface reduction, ASR, security baseline
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: e5acd0b84ffbfa654c00407c134388651b117efc
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68623309"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>Optimizar la implementación y las detecciones de reglas de ASR

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

[Las reglas de reducción de la superficie expuesta a ataques (ASR)](./attack-surface-reduction.md) identifican y evitan vulnerabilidades de seguridad típicas de malware. Controlan cuándo y cómo se puede ejecutar código potencialmente malintencionado. Por ejemplo, pueden impedir que JavaScript o VBScript inicien un archivo ejecutable descargado, bloqueen las llamadas API de Win32 desde macros de Office y bloqueen los procesos que se ejecutan desde unidades USB.


:::image type="content" source="../../media/attack-surface-mgmt.png" alt-text="Tarjeta de administración de superficie expuesta a ataques" lightbox="../../media/attack-surface-mgmt.png":::
<br>
*Tarjeta de administración de superficie expuesta a ataques*

La *tarjeta de administración de superficie* expuesta a ataques es un punto de entrada a las herramientas de <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a> que puede usar para:

* Comprenda cómo se implementan actualmente las reglas de ASR en su organización.
* Revise las detecciones de ASR e identifique posibles detecciones incorrectas.
* Analice el impacto de las exclusiones y genere la lista de rutas de acceso de archivo que se excluirán.

Seleccione **Ir a administración de superficies expuestas a ataques** **Informes Reglas** \> \> de **reducción de superficie** **expuesta a ataques Agregar exclusiones**.\> Desde allí, puede navegar a otras secciones de Microsoft 365 Defender portal.

:::image type="content" source="images/secconmgmt_asr_m365exlusions.png" alt-text="Pestaña Agregar exclusiones en la página Reglas de reducción de superficie expuesta a ataques en el portal de Microsoft 365 Defender" lightbox="images/secconmgmt_asr_m365exlusions.png":::<br>
La *pestaña **Agregar exclusiones** de la página Reglas de reducción de superficie expuesta a ataques en Microsoft 365 Defender portal*

> [!NOTE]
> Para acceder a Microsoft 365 Defender portal, necesita una licencia de Microsoft 365 E3 o E5 y una cuenta que tenga determinados roles en Azure Active Directory. [Obtenga información sobre las licencias y permisos necesarios](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).

Para obtener más información sobre la implementación de reglas de ASR en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>, consulte [Supervisión y administración de detecciones e implementación de reglas de ASR](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).

**Temas relacionados**

* [Asegurarse de que los dispositivos estén configurados de manera adecuada](configure-machines.md)
* [Incorporación de dispositivos a Microsoft Defender para punto de conexión](configure-machines-onboarding.md)
* [Supervisión del cumplimiento de la línea de base de seguridad Microsoft Defender para punto de conexión](configure-machines-security-baseline.md)
