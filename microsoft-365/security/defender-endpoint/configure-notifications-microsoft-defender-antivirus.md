---
title: Configuración de notificaciones de Antivirus de Microsoft Defender
description: Obtenga información sobre cómo configurar y personalizar las notificaciones estándar y otras Antivirus de Microsoft Defender en los puntos de conexión.
keywords: notificaciones, defender, antivirus, punto de conexión, administración, administrador
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: e38a8e9de3bef132dfdf3d2a088190a5038a2941
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790204"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a>Configuración Antivirus de Microsoft Defender notificaciones que aparecen en los puntos de conexión

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

En Windows 10 y Windows 11, las notificaciones de aplicación sobre la detección y corrección de malware son más sólidas, coherentes y concisas. Antivirus de Microsoft Defender las notificaciones aparecen en los puntos de conexión cuando se completan los exámenes y se detectan amenazas. Las notificaciones siguen los exámenes programados y desencadenados manualmente. Estas notificaciones también aparecen en el **Centro de notificaciones** y aparecen un resumen de exámenes y detecciones de amenazas a intervalos de tiempo regulares.

Si forma parte del equipo de seguridad de su organización, puede configurar cómo aparecen las notificaciones en los puntos de conexión, como las notificaciones que solicitan un reinicio del sistema o que indican que se ha detectado y corregido una amenaza.

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a>Configuración de notificaciones antivirus mediante directiva de grupo o la aplicación de Seguridad de Windows

Puede configurar la visualización de notificaciones adicionales, como resúmenes de detección de amenazas recientes, en la [aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md) y con directiva de grupo.

> [!NOTE]
> En Windows 10, la versión 1607 la característica se **denominaba Notificaciones mejoradas** y se configuraba en **Windows Configuración** \> Windows Defender de **seguridad** \> update &. En directiva de grupo configuración para todas las versiones de Windows 10 y Windows 11, la característica de notificación se denomina **Notificaciones mejoradas**.

### <a name="use-group-policy-to-disable-additional-notifications"></a>Uso de directiva de grupo para deshabilitar notificaciones adicionales

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y, a continuación, seleccione **Editar**.

3. En el **Editor de administración de directiva de grupo** vaya a **Configuración del equipo**.

4. Seleccione **Plantillas administrativas**.

5. Expanda el árbol para **Windows componentes** \> **Antivirus de Microsoft Defender** >  **Reporting**.

6. Haga doble clic en **Desactivar notificaciones mejoradas** y establezca la opción **en Habilitado**. A continuación, seleccione **Aceptar**. Esto impedirá que aparezcan notificaciones adicionales.

> [!IMPORTANT]
> Deshabilitar notificaciones adicionales no deshabilitará las notificaciones críticas, como las alertas de detección y corrección de amenazas.

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a>Uso de la aplicación Seguridad de Windows para deshabilitar notificaciones adicionales

1. Abra la aplicación Seguridad de Windows haciendo clic en el icono de escudo en la barra de tareas o buscando en el menú inicio **seguridad**.

2. Seleccione **el icono protección contra amenazas de Virus &** (o el icono de escudo en la barra de menús de la izquierda) y, a continuación, seleccione **Virus & configuración de protección contra amenazas**.

3. Desplácese hasta la sección **Notificaciones** y seleccione **Cambiar configuración de notificación**.

4. Deslice el conmutador a **Desactivado** o **Activado** para deshabilitar o habilitar notificaciones adicionales.

> [!IMPORTANT]
> Deshabilitar notificaciones adicionales no deshabilitará las notificaciones críticas, como las alertas de detección y corrección de amenazas.

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a>Configuración de notificaciones estándar en puntos de conexión mediante directiva de grupo

Puede usar directiva de grupo para:

- Mostrar texto adicional personalizado en los puntos de conexión cuando el usuario necesita realizar una acción
- Ocultar todas las notificaciones en puntos de conexión
- Ocultar notificaciones de reinicio en puntos de conexión

Ocultar notificaciones puede ser útil en situaciones en las que no se puede ocultar toda la interfaz de Antivirus de Microsoft Defender. Consulte [Impedir que los usuarios vean o interactúen con la interfaz de usuario de Antivirus de Microsoft Defender](prevent-end-user-interaction-microsoft-defender-antivirus.md) para obtener más información. La ocultación de notificaciones solo se producirá en los puntos de conexión en los que se ha implementado la directiva. Las notificaciones relacionadas con las acciones que se deben realizar (como un reinicio) seguirán apareciendo en el [panel de supervisión y los informes de Microsoft Endpoint Manager Endpoint Protection](/configmgr/protect/deploy-use/monitor-endpoint-protection). 

Para agregar información de contacto personalizada a las notificaciones de punto de conexión, consulte [Personalización de la aplicación de Seguridad de Windows para su organización](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center).

### <a name="use-group-policy-to-hide-notifications"></a>Uso de directiva de grupo para ocultar notificaciones

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y, a continuación, seleccione **Editar**.

3. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y, a continuación, seleccione **Plantillas administrativas**.

4. Expanda el árbol para **Windows componentes** \> **Antivirus de Microsoft Defender** \> **interfaz de cliente**. 

5. Haga doble clic en **Suprimir todas las notificaciones** y establezca la opción **en Habilitado**. 

6. Seleccione **Aceptar**. Esto impedirá que aparezcan notificaciones adicionales.

### <a name="use-group-policy-to-hide-reboot-notifications"></a>Uso de directiva de grupo para ocultar las notificaciones de reinicio

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y, a continuación, seleccione **Editar**.

2. En el **Editor de administración de directiva de grupo** vaya a **Configuración del equipo**.

3. Haga clic en **Plantillas administrativas**.

4. Expanda el árbol para **Windows componentes** \> **Antivirus de Microsoft Defender** \> **interfaz de cliente**.

5. Haga doble clic en **Suprimir notificaciones de reinicio** y establezca la opción **en Habilitado**. 

5. Seleccione **Aceptar**. Esto impedirá que aparezcan notificaciones adicionales.

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configuración de características de Defender para punto de conexión en Android](android-configure.md)
> - [Configuración de Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)