---
title: Configurar las funciones del Antivirus de Microsoft Defender
description: Puede configurar las características del Antivirus de Microsoft Defender con Intune, Configuration Manager de punto de conexión de Microsoft, directiva de grupo y PowerShell.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defender, configure, configuration, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, administración de dispositivos móviles, GP, directiva de grupo, PowerShell
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: c0950ead64f39dced48bbdea0e242bdc1d8fe3b6
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479540"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>Configurar las funciones del Antivirus de Microsoft Defender


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Puede configurar antivirus de Microsoft Defender con varias herramientas, como:

- Microsoft Endpoint Manager (que incluye Microsoft Intune y Configuration Manager de punto de conexión de Microsoft)
- Directiva de grupo
- Cmdlets de PowerShell
- Instrumental de administración de Windows (WMI)
- [Asociación de inquilinos](/mem/configmgr/tenant-attach/)

Se pueden configurar las siguientes categorías generales de características:

- Protección entregada en la nube. Consulte [Protección entregada en la nube y Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md)

- Protección en tiempo real always-on, incluida la protección basada en comportamiento, heurística y aprendizaje automático. Consulte [Configuración del comportamiento, la heurística y la protección en tiempo real](configure-protection-features-microsoft-defender-antivirus.md).

- Cómo interactúan los usuarios finales con el cliente en puntos de conexión individuales. Vea los siguientes recursos:
  - [Impedir que los usuarios vean o interactúen con la interfaz de usuario del Antivirus de Microsoft Defender](prevent-end-user-interaction-microsoft-defender-antivirus.md)
  - [Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva del Antivirus de Microsoft Defender](configure-local-policy-overrides-microsoft-defender-antivirus.md)

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
