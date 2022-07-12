---
title: Evaluar Antivirus de Microsoft Defender
description: Las empresas de todos los tamaños pueden usar esta guía para evaluar y probar la protección que ofrece antivirus de Microsoft Defender en Windows.
keywords: Antivirus de Microsoft Defender, protección en la nube, nube, antimalware, seguridad, defender, evaluación, prueba, protección, comparación, protección en tiempo real
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
ms.openlocfilehash: 89da56c0230772dab59ad02a751c3bb1ada164e7
ms.sourcegitcommit: c314e989202dc1c9c260fffd459d53bc1f08514e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2022
ms.locfileid: "66717810"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Evaluar Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- Antivirus de Microsoft Defender
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

**Plataformas**
- Windows

Use esta guía para determinar qué tan bien antivirus de Microsoft Defender le protege frente a virus, malware y aplicaciones potencialmente no deseadas. Explica las importantes características de protección de próxima generación del Antivirus de Microsoft Defender disponibles para pequeñas y grandes empresas, y cómo aumentan la detección y protección de malware en toda la red.

Puede elegir configurar y evaluar cada configuración de forma independiente, o todo a la vez. Hemos agrupado una configuración similar en función de los escenarios de evaluación típicos e incluimos instrucciones para usar PowerShell para habilitar la configuración.

La guía está disponible en formato PDF para la visualización sin conexión:

- [Descargar la guía en formato PDF](https://www.microsoft.com/download/details.aspx?id=54795)

También puede descargar una instancia de PowerShell que habilitará todas las opciones de configuración descritas en la guía automáticamente. Puede obtener el script junto con la descarga de PDF anterior, o individualmente de Galería de PowerShell:

- [Descargue el script de PowerShell para configurar automáticamente los valores.](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> La guía está pensada actualmente para la evaluación de un solo equipo del Antivirus de Microsoft Defender. Es posible que la habilitación de todas las opciones de esta guía no sea adecuada para la implementación en el mundo real.
>
> Para obtener las recomendaciones más recientes para la implementación y supervisión en el mundo real del Antivirus de Microsoft Defender a través de una red, consulte [Implementación del Antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md).

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="related-topics"></a>Temas relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Implementación del Antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)