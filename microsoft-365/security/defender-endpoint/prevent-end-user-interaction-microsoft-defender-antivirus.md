---
title: Ocultar la interfaz Antivirus de Microsoft Defender
description: Puede ocultar el icono de protección contra amenazas y virus en la aplicación Seguridad de Windows.
keywords: ui lockdown, headless mode, hide app, hide settings, hide interface
ms.prod: m365-security
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
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: fdd212efd50d55bbcdae80275f5d2ca8a97cdeb3
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787674"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>Impedir que los usuarios vean o interactúen con la interfaz de usuario Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Puede usar directiva de grupo para evitar que los usuarios de los puntos de conexión vean la interfaz de Antivirus de Microsoft Defender. También puede evitar que se pausan los exámenes.

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>Ocultar la interfaz Antivirus de Microsoft Defender

En Windows 10, las versiones 1703, ocultar la interfaz ocultará Antivirus de Microsoft Defender notificaciones e impedirá que el icono de protección contra amenazas virus & aparezca en la aplicación Seguridad de Windows.

Con la configuración establecida en **Habilitado**:

:::image type="content" source="../../media/wdav-headless-mode-off-1703.png" alt-text="El Seguridad de Windows sin el icono de escudo y las secciones de protección contra virus y amenazas" lightbox="../../media/wdav-headless-mode-off-1703.png":::

Con el valor establecido en **Deshabilitado** o no configurado:

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="La Seguridad de Windows con el icono de escudo y las secciones de protección contra amenazas" lightbox="../../media/wdav-headless-mode-1703.png":::

> [!NOTE]
> Ocultar la interfaz también impedirá que aparezcan notificaciones de Antivirus de Microsoft Defender en el punto de conexión. Microsoft Defender para punto de conexión notificaciones seguirán apareciendo. También puede configurar individualmente [las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md).

En versiones anteriores de Windows 10, la configuración ocultará la interfaz de cliente Windows Defender. Si el usuario intenta abrirlo, recibirá una advertencia que indica: "El administrador del sistema tiene acceso restringido a esta aplicación".

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="Mensaje de advertencia cuando el modo sin cabeza está habilitado en Windows 10, versiones anteriores a 1703" lightbox="../../media/wdav-headless-mode-1607.png":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>Uso de directiva de grupo para ocultar la interfaz antivirus de Microsoft Defender a los usuarios

1. En la máquina de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y haga clic en **Editar**.

2. Con el **Editor de administración de directiva de grupo** vaya a **Configuración del equipo**.

3. Haga clic en **Plantillas administrativas**.

4. Expanda el árbol para **Windows componentes > Antivirus de Microsoft Defender > interfaz de cliente**.

5. Haga doble clic en la opción **Habilitar modo de interfaz de usuario sin cabeza** y establezca la opción **en Habilitado**. Haga clic en **Aceptar**.

Consulte [Impedir que los usuarios modifiquen localmente la configuración de la directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md) para obtener más opciones sobre cómo impedir que los usuarios modifiquen la protección en sus equipos.

## <a name="prevent-users-from-pausing-a-scan"></a>Impedir que los usuarios pausan un examen

Puede evitar que los usuarios interrumpan los exámenes, lo que puede resultar útil para garantizar que los exámenes programados o a petición no sean interrumpidos por los usuarios.

> [!NOTE]
> Esta configuración no se admite en Windows 10.

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>Uso de directiva de grupo para evitar que los usuarios pausan un examen

1. En la máquina de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y haga clic en **Editar**.

2. Con el **Editor de administración de directiva de grupo** vaya a **Configuración del equipo**.

3. Haga clic en **Plantillas administrativas**.

4. Expanda el árbol para **Windows componentes** \> **Antivirus de Microsoft Defender** \> **Examen**.

5. Haga doble clic en la opción **Permitir a los usuarios pausar el examen** y establezca la opción **en Deshabilitado**. Haga clic en **Aceptar**.

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configuración de características de Defender para punto de conexión en Android](android-configure.md)
> - [Configuración de Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="related-articles"></a>Artículos relacionados

- [Configurar las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md)
- [Configuración de la interacción del usuario final con Antivirus de Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
