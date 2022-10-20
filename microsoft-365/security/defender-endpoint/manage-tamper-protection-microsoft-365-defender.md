---
title: Administración de la protección contra alteraciones para la organización mediante Microsoft 365 Defender
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: Active o desactive la protección contra alteraciones para el inquilino mediante el portal de Microsoft 365 Defender.
keywords: malware, defender, antivirus, protección contra alteraciones, Microsoft 365 Defender
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: conceptual
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
ms.openlocfilehash: ce36dacb8b16e068dbe6dec483eacbe82ba30fc2
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68627047"
---
# <a name="manage-tamper-protection-for-your-organization-using-microsoft-365-defender-portal"></a>Administración de la protección contra alteraciones de la organización mediante Microsoft 365 Defender portal

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

La protección contra alteraciones se puede activar o desactivar para el inquilino mediante el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). Estos son algunos puntos a tener en cuenta:

- Actualmente, la opción para administrar la "protección contra alteraciones" en el portal de Microsoft 365 Defender está activada de forma predeterminada para las nuevas implementaciones. En el caso de las implementaciones existentes, la "protección contra alteraciones" está disponible de forma opcional. Para participar, en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>, elija **Configuración** \> **Puntos de conexión** Características \> **avanzadas** **Protección contra alteraciones**\>.
- Cuando se usa el portal de Microsoft 365 Defender para administrar la "protección contra alteraciones", no es necesario usar Intune ni el método de asociación de inquilinos.
- Al administrar la "protección contra alteraciones" en el portal de Microsoft 365 Defender, la configuración se aplica en todo el inquilino, lo que afecta a todos los dispositivos que ejecutan Windows 10, Windows 10 Enterprise sesiones múltiples, Windows 11, Windows 11 Empresas  sesiones múltiples, Windows Server 2012 R2, Windows Server 2016, Windows Server 2019 o Windows Server 2022. Para ajustar la "protección contra alteraciones" (por ejemplo, tener la protección contra alteraciones activada para algunos dispositivos pero desactivada para otros), use [Administrar la protección contra alteraciones de su organización mediante Microsoft Endpoint Manager](manage-tamper-protection-microsoft-endpoint-manager.md) o [Administrar la protección contra alteraciones mediante la asociación de inquilinos con Configuration Manager, versión 2006](manage-tamper-protection-configuration-manager.md).
- Si tiene un entorno híbrido, los valores de protección contra alteraciones configurados en Intune tienen prioridad sobre los valores configurados en el portal de Microsoft 365 Defender.

## <a name="requirements-for-managing-tamper-protection-in-the-microsoft-365-defender-portal"></a>Requisitos para administrar la protección contra alteraciones en el portal de Microsoft 365 Defender

- Debe tener asignados [los permisos](/microsoft-365/security/defender-endpoint/assign-portal-access) adecuados, como el administrador global, el administrador de seguridad o las operaciones de seguridad.

- Los dispositivos Windows deben ejecutar una de las siguientes versiones de Windows:
  
  - Windows 11
  - Sesión múltiple de Windows 11 Enterprise 
  - Windows 10
  - Sesión múltiple de Windows 10 Enterprise
  - Windows Server 2022
  - Windows Server 2019
  - Windows Server, versión 1803 o posterior
  - Windows Server 2016
  - Windows Server 2012 R2

Para obtener más información sobre las versiones, consulte [Windows 10 información de la versión](/windows/release-health/release-information).

- Los dispositivos deben [incorporarse a Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/onboarding).
- Los dispositivos deben usar la versión `4.18.2010.7` de la plataforma antimalware (o superior) y la versión `1.1.17600.5` del motor antimalware (o superior). ([Administrar Microsoft Defender actualizaciones del Antivirus y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md)).
- [La protección entregada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) debe estar activada.

> [!NOTE]
> Cuando se habilita la protección contra alteraciones a través del portal de Microsoft 365 Defender, se requiere la protección entregada en la nube, de modo que se pueda controlar el estado habilitado de la protección contra alteraciones.  
> A partir de la actualización de noviembre de 2021 (versión `4.18.2111.5`de la plataforma), si la protección proporcionada en la nube no está activada para un dispositivo y la protección contra alteraciones está activada en el portal de Microsoft 365 Defender, la protección entregada en la nube se activará automáticamente para ese dispositivo junto con la protección contra alteraciones.   

## <a name="turn-tamper-protection-on-or-off-in-the-microsoft-365-defender-portal"></a>Activar o desactivar la protección contra alteraciones en el portal de Microsoft 365 Defender

:::image type="content" source="../../media/mde-turn-tamperprotectionon.png" alt-text="Activar la protección contra alteraciones en el portal de Microsoft 365 Defender" lightbox="../../media/mde-turn-tamperprotectionon.png":::

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Elija Puntos **de conexión de** **configuración**\>.

3. Vaya a **Características avanzadas** **generales** \> y active la protección contra alteraciones.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)