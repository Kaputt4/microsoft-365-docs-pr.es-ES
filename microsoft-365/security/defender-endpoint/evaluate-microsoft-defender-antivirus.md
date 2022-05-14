---
title: Evaluar Antivirus de Microsoft Defender
description: Las empresas de todos los tamaños pueden usar esta guía para evaluar y probar la protección que ofrece Antivirus de Microsoft Defender en Windows.
keywords: Antivirus de Microsoft Defender, cloud protection, cloud, antimalware, security, defender, evaluate, test, protection, compare, real-time protection
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
ms.openlocfilehash: da13d621b350955a7de93d5abe2ee3f4c0c1b27a
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2022
ms.locfileid: "65416066"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Evaluar Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- Antivirus de Microsoft Defender
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

**Plataformas**
- Windows

Use esta guía para determinar qué tan bien Antivirus de Microsoft Defender le protege frente a virus, malware y aplicaciones potencialmente no deseadas.

> [!TIP]
>También puede visitar el sitio web de demostración de Microsoft Defender para punto de conexión en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que las siguientes características funcionan y ver cómo funcionan:
>
> - Protección entregada en la nube
> - Aprendizaje rápido (incluido Bloquear a primera vista)
> - Bloqueo de aplicaciones potencialmente no deseados

> [!NOTE]
> El sitio de demostración de Defender para punto de conexión en demo.wd.microsoft.com está en desuso y se eliminará en el futuro.

Explica las importantes características de protección de próxima generación de Antivirus de Microsoft Defender disponibles para pequeñas y grandes empresas, y cómo aumentan la detección y protección de malware en toda la red.

Puede elegir configurar y evaluar cada configuración de forma independiente, o todo a la vez. Hemos agrupado una configuración similar en función de los escenarios de evaluación típicos e incluimos instrucciones para usar PowerShell para habilitar la configuración.

La guía está disponible en formato PDF para la visualización sin conexión:

- [Descargar la guía en formato PDF](https://www.microsoft.com/download/details.aspx?id=54795)

También puede descargar una instancia de PowerShell que habilitará todas las opciones de configuración descritas en la guía automáticamente. Puede obtener el script junto con la descarga de PDF anterior, o individualmente de Galería de PowerShell:

- [Descargue el script de PowerShell para configurar automáticamente los valores.](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> La guía está pensada actualmente para la evaluación de una sola máquina de Antivirus de Microsoft Defender. Es posible que la habilitación de todas las opciones de esta guía no sea adecuada para la implementación en el mundo real.
>
> Para obtener las recomendaciones más recientes sobre la implementación y supervisión del mundo real de Antivirus de Microsoft Defender en una red, consulte [Implementación de Antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md).

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="related-topics"></a>Temas relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Implementación de Antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)