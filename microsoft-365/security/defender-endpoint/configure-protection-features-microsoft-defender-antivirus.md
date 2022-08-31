---
title: Habilitación y configuración de las características de protección del Antivirus de Microsoft Defender
description: Habilite la protección basada en comportamientos, heurística y en tiempo real en el Antivirus de Microsoft Defender.
keywords: heurístico, aprendizaje automático, monitor de comportamiento, protección en tiempo real, always-on, Antivirus de Microsoft Defender, antimalware, seguridad, defender
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
ms.openlocfilehash: 52ddae872fbb41c9cab6329a9d9ef4ff8381556f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481512"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Configurar la protección en tiempo real, heurística y de comportamiento


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender 

**Plataformas**
- Windows

Antivirus de Microsoft Defender usa varios métodos para proporcionar protección contra amenazas:

- Protección en la nube para la detección y el bloqueo casi instantáneos de amenazas nuevas y emergentes
- Análisis siempre activado, mediante la supervisión del comportamiento de archivos y procesos y otras heurísticas (también conocida como "protección en tiempo real")
- Actualizaciones de protección dedicadas basadas en el aprendizaje automático, el análisis de macrodatos humanos y automatizados y la investigación en profundidad de la resistencia a amenazas

Puede configurar cómo antivirus de Microsoft Defender usa estos métodos con directiva de grupo, System Center Configuration Manage, cmdlets de PowerShell e Instrumental de administración de Windows (WMI).

En esta sección se describe la configuración para el examen siempre activo, incluido cómo detectar y bloquear aplicaciones que se consideran no seguras, pero que pueden no detectarse como malware.

Consulte [Uso de tecnologías antivirus de Microsoft Defender de última generación a través de la protección](cloud-protection-microsoft-defender-antivirus.md) en la nube para obtener información sobre cómo habilitar y configurar la protección en la nube del Antivirus de Microsoft Defender.

## <a name="in-this-section"></a>En esta sección

| Tema|Descripción |
|---|---|
| [Detectar y bloquear aplicaciones potencialmente no deseadas](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)| Detectar y bloquear aplicaciones que pueden no ser deseadas en la red, como adware, modificadores de navegador y barras de herramientas, y aplicaciones antivirus falsas o no autorizadas |
| [Habilitación y configuración de las funcionalidades de protección del Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md)|Habilitar y configurar la protección en tiempo real, la heurística y otras características de supervisión del Antivirus de Microsoft Defender siempre activadas |

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
