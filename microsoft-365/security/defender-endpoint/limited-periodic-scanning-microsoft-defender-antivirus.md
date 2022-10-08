---
title: Habilitación de la característica limitada de examen periódico Microsoft Defender Antivirus
description: El examen periódico limitado le permite usar Microsoft Defender Antivirus, además de otros proveedores de ANTIVIRUS instalados.
keywords: lps, limited, periodic, scan, scan, compatibility, 3rd party, other av, disable
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.collection:
- m365-security
- tier3
search.appverid: met150
ms.openlocfilehash: 5f897e84e5ce174e88565b9cce5712cb66e00819
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68224940"
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

Solo se puede habilitar en determinadas situaciones. Para obtener más información sobre el examen periódico limitado y cómo funciona Microsoft Defender Antivirus con otros productos antivirus, consulte [Microsoft Defender Compatibilidad con antivirus](microsoft-defender-antivirus-compatibility.md).

**Microsoft no recomienda usar esta característica en entornos empresariales. Se trata de una característica destinada principalmente a los consumidores.** Esta característica solo usa un subconjunto limitado de las funcionalidades Microsoft Defender Antivirus para detectar malware y no podrá detectar la mayoría de malware y software potencialmente no deseado. Además, las funcionalidades de administración e informes estarán limitadas. Microsoft recomienda que las empresas elijan su solución antivirus principal y la usen exclusivamente.

## <a name="how-to-enable-limited-periodic-scanning"></a>Habilitación del examen periódico limitado

De forma predeterminada, Microsoft Defender Antivirus se habilitará en un Windows 10 o un dispositivo Windows 11 si no hay ningún otro producto antivirus instalado, o si el otro producto está obsoleto, expirado o no funciona correctamente.

Si Microsoft Defender Antivirus está habilitado, aparecerán las opciones habituales para configurarlo en ese dispositivo:

:::image type="content" source="images/vtp-wdav.png" alt-text="La aplicación Seguridad de Windows que muestra Microsoft Defender opciones de Antivirus, incluidas las opciones de examen, la configuración y las opciones de actualización" lightbox="images/vtp-wdav.png":::

Si otro producto antivirus está instalado y funciona correctamente, Microsoft Defender Antivirus se deshabilitará a sí mismo. La aplicación Seguridad de Windows cambiará la sección **Protección contra amenazas de Virus &** para mostrar el estado del producto antivirus y proporcionar un vínculo a las opciones de configuración del producto.

Debajo de cualquier producto antivirus de terceros, aparecerá un nuevo vínculo como **Microsoft Defender opciones de Antivirus**. Al hacer clic en este vínculo, se expandirá para mostrar el botón de alternancia que permite el examen periódico limitado. Tenga en cuenta que la opción periódica limitada es un botón de alternancia para habilitar o deshabilitar el examen periódico. 

Al deslizar el conmutador a **Activado**, se mostrarán las opciones estándar Microsoft Defender Antivirus debajo del producto antivirus de terceros. La opción de examen periódico limitado aparecerá en la parte inferior de la página.

## <a name="related-articles"></a>Artículos relacionados

- [Configurar la protección en tiempo real, heurística y de comportamiento](configure-protection-features-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)