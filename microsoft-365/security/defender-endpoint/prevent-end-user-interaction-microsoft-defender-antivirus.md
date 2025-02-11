---
title: Ocultar la interfaz Microsoft Defender Antivirus
description: Puede ocultar el icono de protección contra amenazas y virus en la aplicación Seguridad de Windows.
keywords: ui lockdown, headless mode, hide app, hide settings, hide interface
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.topic: conceptual
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 54f0e592cc389402ca1d148437f208c229828c34
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68637758"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>Impedir que los usuarios vean o interactúen con la interfaz de usuario Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Puede usar समूह नीति para evitar que los usuarios de los puntos de conexión vean la interfaz Microsoft Defender Antivirus. También puede evitar que se pausan los exámenes.

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>Ocultar la interfaz Microsoft Defender Antivirus

En Windows 10, las versiones 1703, ocultar la interfaz ocultará Microsoft Defender notificaciones antivirus e impedirá que el icono de protección contra amenazas de Virus & aparezca en la aplicación Seguridad de Windows.

Con la configuración establecida en **Habilitado**:

:::image type="content" source="../../media/wdav-headless-mode-off-1703.png" alt-text="El Seguridad de Windows sin el icono de escudo y las secciones de protección contra virus y amenazas" lightbox="../../media/wdav-headless-mode-off-1703.png":::

Con el valor establecido en **Deshabilitado** o no configurado:

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="La Seguridad de Windows con el icono de escudo y las secciones de protección contra amenazas" lightbox="../../media/wdav-headless-mode-1703.png":::

> [!NOTE]
> Ocultar la interfaz también impedirá que aparezcan Microsoft Defender notificaciones antivirus en el punto de conexión. Microsoft Defender para punto de conexión notificaciones seguirán apareciendo. También puede configurar individualmente [las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md).

En versiones anteriores de Windows 10, la configuración ocultará la interfaz de cliente Windows डिफेन्डर. Si el usuario intenta abrirlo, recibirá una advertencia que indica: "El administrador del sistema tiene acceso restringido a esta aplicación".

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="Mensaje de advertencia cuando el modo sin cabeza está habilitado en Windows 10, versiones anteriores a 1703" lightbox="../../media/wdav-headless-mode-1607.png":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-antivirus-interface-from-users"></a>Uso de समूह नीति para ocultar la interfaz Microsoft Defender Antivirus a los usuarios

1. En la máquina de administración de समूह नीति, abra la [consola de administración de समूह नीति](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), haga clic con el botón derecho en el objeto de समूह नीति que desea configurar y haga clic en **Editar**.

2. Con el **Editor de administración de समूह नीति** vaya a **Configuración del equipo**.

3. Haga clic en **Plantillas administrativas**.

4. Expanda el árbol a **componentes de Windows > Microsoft Defender antivirus > interfaz de cliente**.

5. Haga doble clic en la opción **Habilitar modo de interfaz de usuario sin cabeza** y establezca la opción **en Habilitado**. Haga clic en **Aceptar**.

Consulte [Impedir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) para obtener más opciones sobre cómo impedir que los usuarios modifiquen la protección en sus equipos.

## <a name="prevent-users-from-pausing-a-scan"></a>Impedir que los usuarios pausan un examen

Puede evitar que los usuarios interrumpan los exámenes, lo que puede resultar útil para garantizar que los exámenes programados o a petición no sean interrumpidos por los usuarios.

> [!NOTE]
> Esta configuración no se admite en Windows 10.

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>Uso de समूह नीति para evitar que los usuarios detenten un examen

1. En la máquina de administración de समूह नीति, abra la [consola de administración de समूह नीति](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), haga clic con el botón derecho en el objeto de समूह नीति que desea configurar y haga clic en **Editar**.

2. Con el **Editor de administración de समूह नीति** vaya a **Configuración del equipo**.

3. Haga clic en **Plantillas administrativas**.

4. Expanda el árbol a **componentes** \> **de Windows Microsoft Defender Antivirus** \> **Scan**.

5. Haga doble clic en la opción **Permitir a los usuarios pausar el examen** y establezca la opción **en Deshabilitado**. Haga clic en **Aceptar**.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="related-articles"></a>Artículos relacionados

- [Configurar las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md)
- [Configuración de la interacción del usuario final con Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
