---
title: Administración de la protección contra alteraciones mediante la asociación de inquilinos con Configuration Manager, versión 2006
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: Active o desactive la protección contra alteraciones mediante la asociación de inquilinos con Configuration Manager.
keywords: malware, defender, antivirus, protección contra alteraciones, Configuration Manager
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
ms.openlocfilehash: 2f05fb723ba4b868bec871d9bde6f57107cd656d
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68627091"
---
# <a name="manage-tamper-protection-using-tenant-attach-with-configuration-manager-version-2006"></a>Administración de la protección contra alteraciones mediante la asociación de inquilinos con Configuration Manager, versión 2006

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Si usa la [versión 2006 de Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006), puede administrar la configuración de protección contra alteraciones en Windows 10, Windows 10 Enterprise sesiones múltiples, Windows 11, Windows 11 Empresas multisesión, Windows Server 2012 R2 , Windows Server 2016, Windows Server 2019 y Windows Server 2022 mediante un método denominado *asociación de inquilinos*. La asociación de inquilinos permite sincronizar los dispositivos de Configuration Manager solo locales en el Centro de administración de Microsoft Endpoint Manager y, a continuación, entregar directivas de configuración de seguridad de punto de conexión a colecciones locales & dispositivos.

> [!NOTE]
> El procedimiento se puede usar para ampliar la protección contra alteraciones a los dispositivos que ejecutan Windows 10, Windows 10 Enterprise sesiones múltiples, Windows 11, Windows 11 Empresas sesiones múltiples, Windows Server 2019 y Windows Server 2022. Asegúrese de revisar los requisitos previos y otra información de los recursos mencionados en este procedimiento. Para Windows Server 2012 R2 se requiere la [versión 2203 de la](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2203) solución moderna y unificada de Configuration Manager.

1. Configurar la asociación de inquilinos. Para más información, consulte [Introducción: Creación e implementación de directivas de seguridad de puntos de conexión desde el Centro de administración](/mem/configmgr/tenant-attach/endpoint-security-get-started).

2. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Antivirus** de **seguridad** \> de puntos de conexión y, a continuación, elija **+ Crear directiva**.

   - En la lista **Plataforma**, seleccione **Windows 10, Windows 11 y Windows Server (ConfigMgr)**.
   - En la lista **Perfil**, seleccione **Seguridad de Windows experiencia (versión preliminar).**

3. Implemente la directiva en la colección de dispositivos.

## <a name="need-help-with-this-method"></a>¿Necesita ayuda con este método?

Vea los siguientes recursos:

- [Configuración del perfil de experiencia de Seguridad de Windows en Microsoft Intune](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [Blog de la comunidad tecnológica: Anuncio de la protección contra alteraciones para clientes de asociación de inquilinos de Configuration Manager](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)