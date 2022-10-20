---
title: Configurar las funciones del Antivirus de Microsoft Defender
description: Puede configurar características Microsoft Defender Antivirus con Intune, Microsoft Endpoint Configuration Manager, समूह नीति y PowerShell.
keywords: Microsoft Defender Antivirus, antimalware, security, defender, configure, configuration, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, administración de dispositivos móviles, GP, directiva de grupo, PowerShell
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: conceptual
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 13777ebdc54c27814dfefc2ea81efa4d6e66d042
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68620489"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>Configurar las funciones del Antivirus de Microsoft Defender


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Puede configurar Microsoft Defender Antivirus con varias herramientas, como:

- Microsoft Endpoint Manager (que incluye Microsoft Intune y Microsoft Endpoint Configuration Manager)
- Directiva de grupo
- Cmdlets de PowerShell
- Instrumental de administración de Windows (WMI)
- [Asociación de inquilinos](/mem/configmgr/tenant-attach/)

Se pueden configurar las siguientes categorías generales de características:

- Protección entregada en la nube. Consulte [Protección entregada en la nube y antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md)

- Protección en tiempo real always-on, incluida la protección basada en comportamiento, heurística y aprendizaje automático. Consulte [Configuración del comportamiento, la heurística y la protección en tiempo real](configure-protection-features-microsoft-defender-antivirus.md).

- Cómo interactúan los usuarios finales con el cliente en puntos de conexión individuales. Vea los siguientes recursos:
  - [Impedir que los usuarios vean o interactúen con la interfaz de usuario Microsoft Defender Antivirus](prevent-end-user-interaction-microsoft-defender-antivirus.md)
  - [Impedir o permitir que los usuarios modifiquen localmente Microsoft Defender configuración de directivas antivirus](configure-local-policy-overrides-microsoft-defender-antivirus.md)

> [!TIP]
> Revise [los temas de referencia de las herramientas de administración y configuración](configuration-management-reference-microsoft-defender-antivirus.md).
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
