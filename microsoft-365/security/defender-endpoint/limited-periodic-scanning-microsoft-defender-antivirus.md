---
title: Habilitación de la característica de examen de Antivirus de Microsoft Defender periódica limitada
description: El examen periódico limitado le permite usar Antivirus de Microsoft Defender además de los demás proveedores de ANTIVIRUS instalados.
keywords: lps, limited, periodic, scan, scan, compatibility, 3rd party, other av, disable
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 2b9320c5d7086d41be363fd01b786c98ffbc52d5
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2022
ms.locfileid: "65417916"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Usar el análisis rápido limitado en el Antivirus de Windows Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

El examen periódico limitado es un tipo especial de detección y corrección de amenazas que se puede habilitar cuando se ha instalado otro producto antivirus en un dispositivo Windows 10 o Windows 11.

Solo se puede habilitar en determinadas situaciones. Para obtener más información sobre el examen periódico limitado y cómo funciona Antivirus de Microsoft Defender con otros productos antivirus, consulte [compatibilidad Antivirus de Microsoft Defender](microsoft-defender-antivirus-compatibility.md).

**Microsoft no recomienda usar esta característica en entornos empresariales. Se trata de una característica destinada principalmente a los consumidores.** Esta característica solo usa un subconjunto limitado de las capacidades de Antivirus de Microsoft Defender para detectar malware y no podrá detectar la mayoría de malware y software potencialmente no deseado. Además, las funcionalidades de administración e informes estarán limitadas. Microsoft recomienda que las empresas elijan su solución antivirus principal y la usen exclusivamente.

## <a name="how-to-enable-limited-periodic-scanning"></a>Habilitación del examen periódico limitado

De forma predeterminada, Antivirus de Microsoft Defender se habilitará en un Windows 10 o un dispositivo Windows 11 si no hay ningún otro producto antivirus instalado, o si el otro producto está obsoleto, expirado o no funciona correctamente.

Si Antivirus de Microsoft Defender está habilitado, aparecerán las opciones habituales para configurarlo en ese dispositivo:

:::image type="content" source="images/vtp-wdav.png" alt-text="La aplicación Seguridad de Windows que muestra las opciones de Antivirus de Microsoft Defender, incluidas las opciones de examen, la configuración y las opciones de actualización" lightbox="images/vtp-wdav.png":::

Si otro producto antivirus está instalado y funciona correctamente, Antivirus de Microsoft Defender se deshabilitará. La aplicación Seguridad de Windows cambiará la sección **Protección contra amenazas de Virus &** para mostrar el estado del producto antivirus y proporcionar un vínculo a las opciones de configuración del producto.

Debajo de cualquier producto antivirus de terceros, aparecerá un nuevo vínculo como **Antivirus de Microsoft Defender opciones**. Al hacer clic en este vínculo, se expandirá para mostrar el botón de alternancia que permite el examen periódico limitado. Tenga en cuenta que la opción periódica limitada es un botón de alternancia para habilitar o deshabilitar el examen periódico. 

Al deslizar el modificador a **Activado** , se mostrarán las opciones estándar de Antivirus de Microsoft Defender debajo del producto antivirus de terceros. La opción de examen periódico limitado aparecerá en la parte inferior de la página.

## <a name="related-articles"></a>Artículos relacionados

- [Configurar la protección en tiempo real, heurística y de comportamiento](configure-protection-features-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)