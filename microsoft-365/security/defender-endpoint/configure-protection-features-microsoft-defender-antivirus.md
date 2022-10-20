---
title: Habilitación y configuración de Microsoft Defender características de protección antivirus
description: Habilite la protección basada en comportamientos, heurística y en tiempo real en Microsoft Defender Antivirus.
keywords: heurística, aprendizaje automático, monitor de comportamiento, protección en tiempo real, always-on, Microsoft Defender Antivirus, antimalware, seguridad, defender
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
ms.openlocfilehash: 4fb7f87f755b443c6765a1782b4e9794bb38d716
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68643457"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Configurar la protección en tiempo real, heurística y de comportamiento


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender 

**Plataformas**
- Windows

Microsoft Defender Antivirus usa varios métodos para proporcionar protección contra amenazas:

- Protección en la nube para la detección y el bloqueo casi instantáneos de amenazas nuevas y emergentes
- Análisis siempre activado, mediante la supervisión del comportamiento de archivos y procesos y otras heurísticas (también conocida como "protección en tiempo real")
- Actualizaciones de protección dedicadas basadas en el aprendizaje automático, el análisis de macrodatos humanos y automatizados y la investigación en profundidad de la resistencia a amenazas

Puede configurar cómo Microsoft Defender Antivirus usa estos métodos con समूह नीति, System Center Configuration Manage, cmdlets de PowerShell e Instrumental de administración de Windows (WMI).

En esta sección se describe la configuración para el examen siempre activo, incluido cómo detectar y bloquear aplicaciones que se consideran no seguras, pero que pueden no detectarse como malware.

Consulte [Uso de tecnologías de Microsoft Defender Antivirus de última generación a través de la protección](cloud-protection-microsoft-defender-antivirus.md) en la nube para obtener información sobre cómo habilitar y configurar la protección en la nube de Microsoft Defender Antivirus.

## <a name="in-this-section"></a>En esta sección

| Tema|Descripción |
|---|---|
| [Detectar y bloquear aplicaciones potencialmente no deseadas](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)| Detectar y bloquear aplicaciones que pueden no ser deseadas en la red, como adware, modificadores de navegador y barras de herramientas, y aplicaciones antivirus falsas o no autorizadas |
| [Habilitación y configuración de Microsoft Defender funcionalidades de protección antivirus](configure-real-time-protection-microsoft-defender-antivirus.md)|Habilitar y configurar la protección en tiempo real, la heurística y otras características de supervisión de Microsoft Defender Antivirus siempre activadas |

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
