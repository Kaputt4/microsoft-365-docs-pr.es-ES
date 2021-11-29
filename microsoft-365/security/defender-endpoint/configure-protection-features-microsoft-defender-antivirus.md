---
title: Habilitar y configurar las Antivirus de Microsoft Defender de protección
description: Habilite la protección heurística, heurística y en tiempo real en av. de Microsoft Defender.
keywords: heuristic, machine-learning, behavior monitor, real-time protection, always-on, Antivirus de Microsoft Defender, antimalware, security, defender
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
ms.openlocfilehash: 374e955641a5b74a36bc506e3dfda32e1081e1a5
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/29/2021
ms.locfileid: "61218615"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Configurar la protección en tiempo real, heurística y de comportamiento


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Antivirus de Microsoft Defender varios métodos para proporcionar protección contra amenazas:

- Protección en la nube para la detección casi instantánea y el bloqueo de amenazas nuevas y emergentes
- Análisis siempre en tiempo real, con supervisión del comportamiento de archivos y procesos y otra heurística (también conocida como "protección en tiempo real")
- Actualizaciones de protección dedicadas que se basan en el aprendizaje automático, los análisis humanos y automatizados de macrodatos y el estudio detallado de la resistencia ante amenazas.

Puede configurar cómo Antivirus de Microsoft Defender estos métodos con la directiva de grupo, la administración System Center configuración, los cmdlets de PowerShell y Windows Instrumental de administración (WMI).

En esta sección se describe la configuración del análisis siempre en marcha, incluido cómo detectar y bloquear aplicaciones que se consideran no seguras, pero que no se pueden detectar como malware.

Consulta [Usar tecnologías de Antivirus de Microsoft Defender de](cloud-protection-microsoft-defender-antivirus.md) última generación a través de la protección en la nube para obtener información sobre cómo habilitar y configurar la Antivirus de Microsoft Defender nube.

## <a name="in-this-section"></a>En esta sección

| Tema|Descripción |
|---|---|
| [Detectar y bloquear aplicaciones potencialmente no deseadas](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)| Detectar y bloquear aplicaciones que pueden no ser deseadas en la red, como el software publicitario, modificadores de explorador y barras de herramientas, y aplicaciones antivirus falsas o falsas |
| [Habilitar y configurar las Antivirus de Microsoft Defender de protección](configure-real-time-protection-microsoft-defender-antivirus.md)|Habilitar y configurar la protección en tiempo real, la heurística y otras características de supervisión Antivirus de Microsoft Defender siempre activas |
