---
title: Configurar Antivirus de Microsoft Defender notificaciones
description: Obtenga información sobre cómo configurar y personalizar tanto las notificaciones estándar como otras Antivirus de Microsoft Defender en los puntos de conexión.
keywords: notificaciones, defender, antivirus, punto de conexión, administración, administrador
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985413"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a>Configurar Antivirus de Microsoft Defender notificaciones que aparecen en los puntos de conexión

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

En Windows 10, las notificaciones de aplicaciones sobre detección y corrección de malware son más sólidas, coherentes y concisos. Antivirus de Microsoft Defender notificaciones aparecen en los puntos de conexión cuando se completan los exámenes y se detectan amenazas. Las notificaciones siguen exámenes programados y activados manualmente. Estas notificaciones también aparecen en el **Centro** de notificaciones y aparecen un resumen de exámenes y detecciones de amenazas en intervalos de tiempo regulares.

Si forma parte del equipo de seguridad de su organización, puede configurar cómo aparecen las notificaciones en los puntos de conexión, como las notificaciones que solicitan un reinicio del sistema o que indican que se ha detectado y corregido una amenaza.

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a>Configurar notificaciones antivirus mediante la directiva de grupo o la Seguridad de Windows aplicación

Puedes configurar la presentación de notificaciones adicionales, como resúmenes recientes de detección de amenazas, en la [aplicación](microsoft-defender-security-center-antivirus.md) Seguridad de Windows y con la directiva de grupo.

> [!NOTE]
> En Windows 10 versión 1607, la característica se denomina **notificaciones mejoradas** y se configuró en Windows Configuración   >  **Actualización & seguridad**  >  **Windows Defender**. En Configuración de directiva de grupo para todas las versiones Windows 10, la característica de notificación se denomina **Notificaciones mejoradas.**

### <a name="use-group-policy-to-disable-additional-notifications"></a>Usar la directiva de grupo para deshabilitar notificaciones adicionales

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.

3. En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**

4. Seleccione **Plantillas administrativas**.

5. Expanda el árbol para **Windows componentes**  >  **Antivirus de Microsoft Defender** > reporting**.

6. Haga doble clic **en Desactivar notificaciones mejoradas** y establezca la opción en **Habilitado**. A continuación, seleccione **Aceptar**. Esto impedirá que aparezcan notificaciones adicionales.

> [!IMPORTANT]
> Deshabilitar notificaciones adicionales no deshabilitará las notificaciones críticas, como alertas de detección de amenazas y de corrección.

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a>Usar la Seguridad de Windows para deshabilitar notificaciones adicionales

1. Abra la aplicación Seguridad de Windows haciendo clic en el icono de escudo de la barra de tareas o buscando en el menú inicio **seguridad**.

2. Seleccione **Icono de protección contra &** virus (o el icono de escudo de la barra de menús izquierda) y, a continuación, seleccione Configuración de protección contra **&** virus

3. Desplácese a la **sección Notificaciones** y seleccione Cambiar configuración **de notificación.**

4. Deslice el conmutador **a Desactivado** o **Encendido para** deshabilitar o habilitar notificaciones adicionales.

> [!IMPORTANT]
> Deshabilitar notificaciones adicionales no deshabilitará las notificaciones críticas, como alertas de detección de amenazas y de corrección.

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a>Configurar notificaciones estándar en puntos de conexión mediante la directiva de grupo

Puede usar la directiva de grupo para:

- Mostrar texto adicional y personalizado en los puntos de conexión cuando el usuario necesita realizar una acción
- Ocultar todas las notificaciones en puntos de conexión
- Ocultar notificaciones de reinicio en puntos de conexión

Ocultar notificaciones puede ser útil en situaciones en las que no se puede ocultar toda la interfaz Antivirus de Microsoft Defender usuario. Consulta [Impedir que los usuarios vean o interactúen con la Antivirus de Microsoft Defender de usuario para](prevent-end-user-interaction-microsoft-defender-antivirus.md) obtener más información. Las notificaciones ocultas solo se producirán en los puntos de conexión en los que se ha implementado la directiva. Las notificaciones relacionadas con las acciones que deben realizarse (como un reinicio) seguirán apareciendo en el panel de supervisión Microsoft Endpoint Manager Endpoint Protection [informes.](/configmgr/protect/deploy-use/monitor-endpoint-protection) 

Para agregar información de contacto personalizada a las notificaciones de punto de conexión, [consulta Personalizar la aplicación Seguridad de Windows para tu organización.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)

### <a name="use-group-policy-to-hide-notifications"></a>Usar la directiva de grupo para ocultar notificaciones

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.

3. En el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo **y,** a continuación, seleccione **Plantillas administrativas.**

4. Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender** interfaz  >    >  **de cliente**. 

5. Haga doble clic **en Suprimir todas las notificaciones** y establezca la opción en **Habilitado**. 

6. Seleccione **Aceptar**. Esto impedirá que aparezcan notificaciones adicionales.

### <a name="use-group-policy-to-hide-reboot-notifications"></a>Usar la directiva de grupo para ocultar las notificaciones de reinicio

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.

2. En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**

3. Haga clic **en Plantillas administrativas**.

4. Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender** interfaz  >    >  **de cliente**.

5. Haz doble clic **en Suprimir notificaciones de reinicio** y establece la opción en **Habilitado**. 

5. Seleccione **Aceptar**. Esto impedirá que aparezcan notificaciones adicionales.

