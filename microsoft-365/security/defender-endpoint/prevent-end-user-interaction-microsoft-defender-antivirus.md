---
title: Ocultar la Antivirus de Microsoft Defender interfaz
description: Puedes ocultar el icono de protección contra virus y amenazas en la Seguridad de Windows aplicación.
keywords: bloqueo de ui, modo sin cabeza, ocultar aplicación, ocultar configuración, ocultar interfaz
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 06ee2f1cb68df0a957818e1fccb45628487c39fd
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274921"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>Impedir que los usuarios vean o interactúen con la interfaz Antivirus de Microsoft Defender usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puede usar la directiva de grupo para impedir que los usuarios de los puntos de conexión vean la interfaz Antivirus de Microsoft Defender usuario. También puede evitar que pauten los exámenes.

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>Ocultar la Antivirus de Microsoft Defender interfaz

En Windows 10, versión 1703, ocultar la interfaz ocultará las notificaciones de Antivirus de Microsoft Defender e impedirá que el icono protección contra amenazas de Virus & aparezca en la aplicación Seguridad de Windows.

Con la configuración establecida en **Enabled**:

![Captura de pantalla Seguridad de Windows sin el icono de escudo y la sección protección contra virus y amenazas](images/defender/wdav-headless-mode-1703.png)

Con la configuración establecida en **Deshabilitado** o no configurada:

![Captura de pantalla Seguridad de Windows muestra el icono de escudo y la sección protección contra virus y amenazas](images/defender/wdav-headless-mode-off-1703.png)

>[!NOTE]
>Ocultar la interfaz también impedirá que Antivirus de Microsoft Defender notificaciones en el punto de conexión. Las notificaciones de Microsoft Defender para puntos de conexión seguirán apareciendo. También puede configurar [individualmente las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md)

En versiones anteriores de Windows 10, la configuración ocultará la interfaz Windows Defender cliente. Si el usuario intenta abrirlo, recibirá una advertencia que indica: "El administrador del sistema ha restringido el acceso a esta aplicación".

![Mensaje de advertencia cuando el modo sin cabeza está habilitado Windows 10 versiones anteriores a 1703](images/defender/wdav-headless-mode-1607.png)

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>Usar la directiva de grupo para ocultar la interfaz av de Microsoft Defender a los usuarios

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. Con el **Editor de administración de directivas de grupo,** vaya a Configuración del **equipo**.

3. Haga clic **en Plantillas administrativas**.

4. Expanda el árbol para Windows **componentes > Antivirus de Microsoft Defender > interfaz de cliente**.

5. Haz doble clic en **la opción Habilitar modo de interfaz de** usuario sin cabeza y establece la opción en **Habilitado**. Haga clic en **Aceptar**. 

Consulta [Impedir que los usuarios modifiquen localmente](configure-local-policy-overrides-microsoft-defender-antivirus.md) la configuración de directiva para obtener más opciones sobre cómo impedir que los usuarios forme parte de la protección de sus equipos.

## <a name="prevent-users-from-pausing-a-scan"></a>Impedir que los usuarios pauten un examen

Puede impedir que los usuarios pauten los exámenes, lo que puede ser útil para garantizar que los usuarios no interrumpan los exámenes programados o a petición.

> [!NOTE]
> Esta configuración no se admite en Windows 10.

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>Usar la directiva de grupo para evitar que los usuarios pauten un examen

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. Con el **Editor de administración de directivas de grupo,** vaya a Configuración del **equipo**.

3. Haga clic **en Plantillas administrativas**.

4. Expanda el árbol para Windows **componentes**  >  **Antivirus de Microsoft Defender**  >  **Scan**.

5. Haga doble clic en **la opción Permitir a los usuarios pausar el** examen y establezca la opción en **Deshabilitado**. Haga clic en **Aceptar**. 

## <a name="related-articles"></a>Artículos relacionados

- [Configurar las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md)

- [Configurar la interacción del usuario final con Antivirus de Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)