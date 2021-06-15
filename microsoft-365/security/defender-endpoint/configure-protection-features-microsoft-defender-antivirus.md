---
title: Habilitar y configurar las Antivirus de Microsoft Defender de protección
description: Habilite la protección heurística, heurística y en tiempo real en av. de Microsoft Defender.
keywords: heuristic, machine-learning, behavior monitor, real-time protection, always-on, Antivirus de Microsoft Defender, antimalware, security, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: d8ce2ded8fd3270bcb095022c714f07d8030e1f7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925568"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Configurar la protección en tiempo real, heurística y de comportamiento


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Antivirus de Microsoft Defender varios métodos para proporcionar protección contra amenazas:

- Protección entregada en la nube para la detección casi instantánea y el bloqueo de amenazas nuevas y emergentes
- Análisis siempre en tiempo real, con supervisión del comportamiento de archivos y procesos y otra heurística (también conocida como "protección en tiempo real")
- Actualizaciones de protección dedicadas que se basan en el aprendizaje automático, los análisis humanos y automatizados de macrodatos y el estudio detallado de la resistencia ante amenazas.

Puede configurar cómo Antivirus de Microsoft Defender estos métodos con la directiva de grupo, la administración System Center configuración, los cmdlets de PowerShell y Windows Instrumental de administración (WMI).

En esta sección se describe la configuración del análisis siempre en marcha, incluido cómo detectar y bloquear aplicaciones que se consideran no seguras, pero que no se pueden detectar como malware.

Consulte [Use next-gen Antivirus de Microsoft Defender a través](cloud-protection-microsoft-defender-antivirus.md) de la protección entregada en la nube para obtener información sobre cómo habilitar y configurar la Antivirus de Microsoft Defender de entrega en la nube.

## <a name="in-this-section"></a>En esta sección

 Tema | Descripción
---|---
[Detectar y bloquear aplicaciones potencialmente no deseadas](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Detectar y bloquear aplicaciones que pueden no ser deseadas en la red, como el software publicitario, modificadores de explorador y barras de herramientas, y aplicaciones antivirus falsas o falsas
[Habilitar y configurar las Antivirus de Microsoft Defender de protección](configure-real-time-protection-microsoft-defender-antivirus.md) | Habilitar y configurar la protección en tiempo real, la heurística y otras características de supervisión Antivirus de Microsoft Defender siempre activas
