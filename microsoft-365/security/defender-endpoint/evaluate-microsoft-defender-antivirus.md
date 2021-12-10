---
title: Evaluar Antivirus de Microsoft Defender
description: Las empresas de todos los tamaños pueden usar esta guía para evaluar y probar la protección que ofrece Antivirus de Microsoft Defender en Windows.
keywords: Antivirus de Microsoft Defender, protección en la nube, nube, antimalware, seguridad, defender, evaluar, probar, proteger, comparar, protección en tiempo real
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 91c64e1df7468ec259e6202bdff879efce445ac0
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168227"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Evaluar Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

Use esta guía para determinar qué tan bien Antivirus de Microsoft Defender protege contra virus, malware y aplicaciones potencialmente no deseadas.

> [!TIP]
>También puede visitar el sitio web de demostración de Microsoft Defender para endpoint en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que las siguientes características funcionan y ver cómo funcionan:
>
> - Protección entregada en la nube
> - Aprendizaje rápido (incluido Bloquear a primera vista)
> - Bloqueo de aplicaciones potencialmente no deseado

Explica las características importantes de protección de próxima generación de Antivirus de Microsoft Defender disponibles para pequeñas y grandes empresas, y cómo aumentan la detección y protección de malware en toda la red.

Puede elegir configurar y evaluar cada configuración de forma independiente o todo a la vez. Hemos agrupado configuraciones similares en función de escenarios de evaluación típicos e incluye instrucciones para usar PowerShell para habilitar la configuración.

La guía está disponible en formato PDF para la visualización sin conexión:

- [Descargar la guía en formato PDF](https://www.microsoft.com/download/details.aspx?id=54795)

También puede descargar un PowerShell que habilitará automáticamente todas las opciones descritas en la guía. Puede obtener el script junto con la descarga de PDF anterior o individualmente desde la Galería de PowerShell:

- [Descargar el script de PowerShell para configurar automáticamente la configuración](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> La guía está diseñada actualmente para la evaluación de una sola máquina de Antivirus de Microsoft Defender. Es posible que la habilitación de toda la configuración de esta guía no sea adecuada para la implementación en el mundo real.
>
> Para obtener las recomendaciones más recientes para la implementación real y la supervisión de Antivirus de Microsoft Defender en una red, vea [Deploy Antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md).

## <a name="related-topics"></a>Temas relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Implementar Antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)