---
title: Protección proporcionada en la nube y Antivirus de Windows Defender
description: Obtenga información sobre la protección y la protección entregadas en la nube Antivirus de Microsoft Defender
keywords: Antivirus de Microsoft Defender, tecnologías de última generación, av de última generación, aprendizaje automático, antimalware, seguridad, defender, nube, protección entregada en la nube
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 06/03/2021
ms.openlocfilehash: ce54f8205e62b953022fd2518caac058f4f9bab2
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788804"
---
# <a name="cloud-delivered-protection-and-microsoft-defender-antivirus"></a>Protección proporcionada en la nube y Antivirus de Windows Defender

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)
- Antivirus de Microsoft Defender

Las tecnologías de última Antivirus de Microsoft Defender proporcionan protección automatizada casi instantánea contra amenazas nuevas y emergentes. Para identificar las nuevas amenazas de forma dinámica, las tecnologías de próxima generación funcionan con grandes conjuntos de datos interconectados en los sistemas de inteligencia artificial (IA) de Microsoft Intelligent Security Graph y potentes basados en modelos avanzados de aprendizaje automático. Antivirus de Microsoft Defender varias tecnologías de detección y prevención para ofrecer una protección precisa, en tiempo real e inteligente. 

> [!TIP]
> ¿Quiere obtener más información? Consulta la entrada de blog Get [to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).

Antivirus de Microsoft Defender funciona sin problemas con los servicios en la nube de Microsoft. Estos servicios de protección en la nube, también denominados Servicio de protección avanzada de Microsoft (MAPS), mejoran la protección estándar en tiempo real, proporcionando posiblemente la mejor defensa antivirus. 

> [!NOTE]
> El Antivirus de Microsoft Defender en la nube es un mecanismo para ofrecer protección actualizada a la red y los puntos de conexión. Como servicio en la nube, no es simplemente protección para los archivos almacenados en la nube; En su lugar, el servicio en la nube usa recursos distribuidos y aprendizaje automático para ofrecer protección a los puntos de conexión a una velocidad mucho más rápida que las actualizaciones de inteligencia de seguridad tradicionales.

Con la protección entregada en la nube, las tecnologías de última generación proporcionan una identificación rápida de las nuevas amenazas, a veces incluso antes de que una sola máquina se infecte. En las siguientes entradas de blog se muestra cómo funciona la protección entregada en la nube:

- [Por Antivirus de Microsoft Defender es el más implementado en la empresa](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 
- [La supervisión del comportamiento combinada con el aprendizaje automático estropea una campaña masiva de extracción de monedas](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)
- [Cómo la inteligencia artificial detuvo un brote de "Emotet"](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)
- [Detonar un conejito malo: defensas Antivirus de Microsoft Defender aprendizaje automático en capas](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)
- [Antivirus de Microsoft Defender de protección en la nube: defensa avanzada en tiempo real contra malware nunca visto](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 
 
## <a name="how-to-get-cloud-delivered-protection"></a>Cómo obtener protección entregada en la nube 

La protección entregada en la nube está habilitada de forma predeterminada. Sin embargo, es posible que deba volver a habilitarlo si se ha deshabilitado como parte de directivas organizativas anteriores. Para obtener más información, [vea Activar la protección entregada en la nube.](enable-cloud-protection-microsoft-defender-antivirus.md)

Las organizaciones que Windows 10 E5 también pueden aprovechar las actualizaciones de inteligencia dinámica de emergencia, que proporcionan protección casi en tiempo real frente a amenazas emergentes. Al activar la protección entregada en la nube, las correcciones para problemas de malware se pueden entregar a través de la nube en cuestión de minutos, en lugar de esperar a la siguiente actualización. Configure Antivirus de Microsoft Defender para recibir automáticamente nuevas actualizaciones de [protección basadas en informes de nuestro servicio en la nube.](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)

> [!TIP]
> Visita el sitio Windows Defender testground en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que la característica funciona y ver cómo funciona.

## <a name="next-steps"></a>Pasos siguientes

1. [Habilitar la protección entregada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md). Puede habilitar la protección entregada en la nube con Microsoft Endpoint Manager (que ahora incluye Microsoft Endpoint Configuration Manager y Microsoft Intune), directiva de grupo o cmdlets de PowerShell.

2. [Especifique el nivel de protección entregado en la nube.](specify-cloud-protection-level-microsoft-defender-antivirus.md) Puede especificar el nivel de protección ofrecido por la nube mediante Microsoft Endpoint Manager o directiva de grupo. El nivel de protección afecta a la cantidad de información compartida con la nube y a la forma agresiva en que se bloquean los nuevos archivos.

3. [Configurar y validar conexiones de red para Antivirus de Microsoft Defender](configure-network-connections-microsoft-defender-antivirus.md). Hay determinadas direcciones URL de Microsoft a las que la red y los puntos de conexión deben poder conectarse para que la protección entregada en la nube funcione de forma eficaz. En este artículo se enumeran las direcciones URL que se deben permitir mediante firewall o reglas de filtrado de red, e instrucciones para confirmar que la red está correctamente inscrita en la protección entregada en la nube.

4. [Configurar la característica "bloquear a primera vista".](configure-block-at-first-sight-microsoft-defender-antivirus.md) La característica "bloquear a primera vista" puede bloquear malware nuevo en cuestión de segundos, sin tener que esperar horas para la inteligencia de seguridad tradicional. Puede habilitarla y configurarla mediante Microsoft Endpoint Manager o directiva de grupo.

5. [Configurar el período de tiempo de espera del bloque de nube.](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) Antivirus de Microsoft Defender bloquear la ejecución de archivos sospechosos mientras consulta nuestro servicio de protección entregado en la nube. Puede configurar la cantidad de tiempo que se impedirá que el archivo se ejecute mediante Microsoft Endpoint Manager o directiva de grupo.