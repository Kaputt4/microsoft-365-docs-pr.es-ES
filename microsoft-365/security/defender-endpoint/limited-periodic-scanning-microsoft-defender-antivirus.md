---
title: Habilitar la característica de análisis periódica limitada de Antivirus de Microsoft Defender
description: El análisis periódico limitado te permite usar Antivirus de Microsoft Defender además de tus otros proveedores de ANTIVIRUS instalados
keywords: lps, limited, periodic, scan, scanning, compatibility, 3rd party, other av, disable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 64b65363ff53773f73cbbdc33b05a0a1beaf7f92
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691248"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Usar análisis periódico limitado en Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

El examen periódico limitado es un tipo especial de detección y corrección de amenazas que se puede habilitar cuando se instala otro producto antivirus en un dispositivo Windows 10.

Solo se puede habilitar en determinadas situaciones. Para obtener más información sobre el examen periódico limitado y cómo funciona Antivirus de Microsoft Defender con otros productos antivirus, vea [Compatibilidad de Antivirus de Microsoft Defender.](microsoft-defender-antivirus-compatibility.md)

**Microsoft no recomienda usar esta característica en entornos empresariales. Esta es una característica destinada principalmente a los consumidores.** Esta característica solo usa un subconjunto limitado de las capacidades de Antivirus de Microsoft Defender para detectar malware y no podrá detectar la mayoría de malware y software potencialmente no deseado. Además, las capacidades de administración e informes serán limitadas. Microsoft recomienda a las empresas elegir su solución antivirus principal y usarla exclusivamente.

## <a name="how-to-enable-limited-periodic-scanning"></a>Cómo habilitar el examen periódico limitado

De forma predeterminada, Antivirus de Microsoft Defender se habilitará en un dispositivo Windows 10 si no hay ningún otro producto antivirus instalado, o si el otro producto está des actualizado, expirado o no funciona correctamente.

Si Antivirus de Microsoft Defender está habilitado, aparecerán las opciones habituales para configurarlo en ese dispositivo:

![Aplicación de Seguridad de Windows que muestra las opciones de ANTIVIRUS de Microsoft Defender, incluidas las opciones de examen, la configuración y las opciones de actualización](images/vtp-wdav.png)

Si otro producto antivirus está instalado y funciona correctamente, Antivirus de Microsoft Defender se deshabilitará a sí mismo. La aplicación Seguridad de Windows cambiará la sección Protección contra **&** virus para mostrar el estado del producto ANTIVIRUS y proporcionar un vínculo a las opciones de configuración del producto.

Debajo de cualquier producto ANTIVIRUS de terceros, aparecerá un nuevo vínculo como opciones **de Antivirus de Microsoft Defender.** Al hacer clic en este vínculo, se expandirá para mostrar la alternancia que habilita el examen periódico limitado. Tenga en cuenta que la opción periódica limitada es una alternancia para habilitar o deshabilitar el examen periódico. 

Al deslizar el conmutador a **On,** se mostrarán las opciones estándar de Antivirus de Microsoft Defender debajo del producto ANTIVIRUS de terceros. La opción de examen periódico limitado aparecerá en la parte inferior de la página.

## <a name="related-articles"></a>Artículos relacionados

- [Configurar la protección de comportamiento, heurística y en tiempo real](configure-protection-features-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)