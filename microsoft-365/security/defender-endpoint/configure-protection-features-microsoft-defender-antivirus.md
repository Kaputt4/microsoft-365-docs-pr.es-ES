---
title: Habilitar y configurar las características de protección antivirus de Microsoft Defender
description: Habilite la protección heurística, heurística y en tiempo real en av. de Microsoft Defender.
keywords: heuristic, machine-learning, behavior monitor, real-time protection, always-on, Microsoft Defender Antivirus, antimalware, security, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 53b1e1474e0870388ec1cfaf214190eb0bdf7beb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274615"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Configurar la protección en tiempo real, heurística y de comportamiento

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Antivirus de Microsoft Defender usa varios métodos para proporcionar protección contra amenazas:

- Protección entregada en la nube para la detección casi instantánea y el bloqueo de amenazas nuevas y emergentes
- Análisis siempre en tiempo real, con supervisión del comportamiento de archivos y procesos y otra heurística (también conocida como "protección en tiempo real")
- Actualizaciones de protección dedicadas que se basan en el aprendizaje automático, los análisis humanos y automatizados de macrodatos y el estudio detallado de la resistencia ante amenazas.

Puede configurar el modo en que Antivirus de Microsoft Defender usa estos métodos con la directiva de grupo, administración de configuración de System Center, cmdlets de PowerShell e Instrumental de administración de Windows (WMI).

En esta sección se describe la configuración del análisis siempre en marcha, incluido cómo detectar y bloquear aplicaciones que se consideran no seguras, pero que no se pueden detectar como malware.

Consulta [Usar tecnologías antivirus](cloud-protection-microsoft-defender-antivirus.md) de Microsoft Defender de última generación a través de la protección entregada en la nube para obtener información sobre cómo habilitar y configurar la protección en la nube de Antivirus de Microsoft Defender.

## <a name="in-this-section"></a>En esta sección

 Tema | Descripción
---|---
[Detectar y bloquear aplicaciones potencialmente no deseadas](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Detectar y bloquear aplicaciones que pueden no ser deseadas en la red, como el software publicitario, modificadores de explorador y barras de herramientas, y aplicaciones antivirus falsas o falsas
[Habilitar y configurar las capacidades de protección de Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md) | Habilitar y configurar la protección en tiempo real, la heurística y otras características de supervisión de Antivirus de Microsoft Defender siempre activas