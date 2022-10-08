---
title: Administración de la protección contra alteraciones en un dispositivo individual
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: Active o desactive la protección contra alteraciones para un dispositivo individual.
keywords: malware, defender, antivirus, protección contra alteraciones
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom:
- nextgen
- admindeeplinkDEFENDER
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 250d82b4ab61a356c12cb8bee5d03f737c3d0a25
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68221530"
---
# <a name="manage-tamper-protection-on-an-individual-device"></a>Administración de la protección contra alteraciones en un dispositivo individual

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

> [!NOTE]
> La protección contra alteraciones bloquea los intentos de modificar Microsoft Defender configuración del Antivirus a través del Registro.
> Para ayudar a garantizar que la protección contra alteraciones no interfiera con los productos de seguridad que no son de Microsoft ni con scripts de instalación empresarial que modifican esta configuración, vaya a **Seguridad de Windows** y actualice **Security Intelligence** a la versión 1.287.60.0 o posterior. (Consulte [Actualizaciones de inteligencia de seguridad](https://www.microsoft.com/wdsi/definitions)). Después de realizar esta actualización, la protección contra alteraciones continúa protegiendo la configuración del Registro y los registros intentan modificarlas sin devolver errores.

Si es un usuario principal o no está sujeto a la configuración administrada por un equipo de seguridad, puede usar la aplicación Seguridad de Windows para administrar la protección contra alteraciones. Debe tener los permisos de administrador adecuados en el dispositivo para cambiar la configuración de seguridad, como la protección contra alteraciones.

Esto es lo que se ve en la aplicación de Seguridad de Windows:

:::image type="content" source="images/tamperprotectionturnedon.png" alt-text="Activar la protección contra alteraciones en Windows 10 Home" lightbox="images/tamperprotectionturnedon.png":::

1. Seleccione **Inicio** y empiece a escribir *Seguridad*. En los resultados de la búsqueda, seleccione **Seguridad de Windows**.

2. Seleccione **Virus & threat protection** \> **Virus & threat protection settings (Virus & configuración de protección contra amenazas**).

3. Establezca **Protección contra alteraciones** **en Activado** o **Desactivado**.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

