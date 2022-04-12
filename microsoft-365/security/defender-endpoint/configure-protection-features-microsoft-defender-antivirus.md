---
title: Habilitación y configuración de características de protección de Antivirus de Microsoft Defender
description: Habilite la protección basada en comportamientos, heurística y en tiempo real en El antivirus de Microsoft Defender.
keywords: heurístico, aprendizaje automático, monitor de comportamiento, protección en tiempo real, always-on, Antivirus de Microsoft Defender, antimalware, security, defender
ms.prod: m365-security
ms.technology: mde
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
ms.openlocfilehash: 59754ac5186b87045e8126114fd7342f5aa9532c
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788862"
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

Puede configurar cómo usa Antivirus de Microsoft Defender estos métodos con directiva de grupo, System Center Configuration Manage, cmdlets de PowerShell y Windows Management Instrumentation (WMI).

En esta sección se describe la configuración para el examen siempre activo, incluido cómo detectar y bloquear aplicaciones que se consideran no seguras, pero que pueden no detectarse como malware.

Consulte [Uso de tecnologías de Antivirus de Microsoft Defender de última generación a través de la protección](cloud-protection-microsoft-defender-antivirus.md) en la nube para obtener información sobre cómo habilitar y configurar Antivirus de Microsoft Defender protección en la nube.

## <a name="in-this-section"></a>En esta sección

| Tema|Descripción |
|---|---|
| [Detectar y bloquear aplicaciones potencialmente no deseadas](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)| Detectar y bloquear aplicaciones que pueden no ser deseadas en la red, como adware, modificadores de navegador y barras de herramientas, y aplicaciones antivirus falsas o no autorizadas |
| [Habilitación y configuración de funcionalidades de protección de Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md)|Habilitar y configurar la protección en tiempo real, la heurística y otras características de supervisión de Antivirus de Microsoft Defender siempre activadas |

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configuración de características de Defender para punto de conexión en Android](android-configure.md)
> - [Configuración de Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
