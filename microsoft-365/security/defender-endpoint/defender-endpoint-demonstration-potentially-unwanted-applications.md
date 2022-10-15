---
title: Microsoft Defender para punto de conexión demostración de aplicaciones potencialmente no deseadas (PUA)
description: Demostración para mostrar cómo la característica de protección de aplicaciones potencialmente no deseadas (PUA) puede identificar y impedir que las PUA se descarguen e instalen en puntos de conexión.
keywords: Microsoft Defender para punto de conexión, aplicaciones potencialmente no deseadas, (PUA), protección de aplicaciones dañinas, demostración
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: evaluation
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 8d98c1a74f771aee15d8b02ce9b16c8dd3b4fd7b
ms.sourcegitcommit: 1f4c51d022d1cfb6c194bf0f0af9c2841c781d68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2022
ms.locfileid: "68573359"
---
# <a name="potentially-unwanted-applications-pua-demonstration"></a>Demostración de aplicaciones potencialmente no deseadas (PUA)

La característica de protección de aplicaciones potencialmente no deseadas (PUA) de Microsoft Defender Antivirus puede identificar y impedir que las PUA se descarguen e instalen en los puntos de conexión de la red. Estas aplicaciones no se consideran virus, malware u otros tipos de amenazas, pero pueden realizar acciones en puntos de conexión que afecten negativamente a su rendimiento o uso.

## <a name="scenario-requirements-and-setup"></a>Requisitos y configuración del escenario

- Windows 10, Windows 11

- Habilite la protección pua. Consulte el artículo [Detectar y bloquear aplicaciones potencialmente no deseadas](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) para obtener más información.
- También puede [descargar y usar el script de PowerShell](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings/) para habilitar esta configuración y otras.

## <a name="scenario"></a>Escenario

1. Vete a [http://www.amtso.org/feature-settings-check-potentially-unwanted-applications/](http://www.amtso.org/feature-settings-check-potentially-unwanted-applications/)
2. Haga clic en el vínculo "Descargar el archivo de prueba de la aplicación potencialmente no deseada".
3. Después de descargar el archivo, se bloquea automáticamente y se impide que se ejecute.

## <a name="see-also"></a>Vea también

[Detectar y bloquear aplicaciones potencialmente no deseadas](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)

[Microsoft Defender para punto de conexión: escenarios de demostración](defender-endpoint-demonstrations.md)
