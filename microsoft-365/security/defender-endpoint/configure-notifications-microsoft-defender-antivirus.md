---
title: Configurar notificaciones de Antivirus de Microsoft Defender
description: Aprenda a configurar y personalizar notificaciones de Antivirus de Microsoft Defender estándar y adicionales en los puntos de conexión.
keywords: notificaciones, defensor, antivirus, punto de conexión, administración, administración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572350"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>Configure las notificaciones que aparecen en los puntos de conexión

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

En Windows 10, las notificaciones de aplicaciones sobre detección y corrección de malware son más robustas, consistentes y concisas.

Las notificaciones aparecen en los puntos de conexión cuando se activan manualmente y se completan los exámenes programados y se detectan amenazas. Estas notificaciones también aparecen en el Centro de **notificaciones** y aparece un resumen de los exámenes y detecciones de amenazas a intervalos de tiempo regulares.

También puede configurar cómo aparecen las notificaciones estándar en los puntos de conexión, como las notificaciones para el reinicio o cuándo se ha detectado y corrige una amenaza.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>Configure las notificaciones adicionales que aparecen en los puntos de conexión

Puede configurar la visualización de notificaciones adicionales, como resúmenes recientes de detección de amenazas, en la [aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md) y con directiva de grupo.

> [!NOTE]
> En Windows 10, la versión 1607 la característica se denomina **notificaciones mejoradas** y se podía configurar en **Windows Configuración** Actualizar & Windows Defender  >  **de seguridad.**  >   En la configuración de directiva de grupo en todas las versiones de Windows 10, se denomina **Notificaciones mejoradas**.

> [!IMPORTANT]
> Deshabilitar notificaciones adicionales no deshabilitará las notificaciones críticas, como las alertas de detección y corrección de amenazas.

**Utilice la aplicación Seguridad de Windows para deshabilitar notificaciones adicionales:**

1. Abra la aplicación Seguridad de Windows haciendo clic en el icono de escudo en la barra de tareas o buscando en el menú inicio **de Seguridad**.

2. Seleccione Virus & icono **de protección contra amenazas** (o el icono de escudo en la barra de menús izquierda) y, a continuación, seleccione Virus & configuración de protección contra **amenazas**

3. Desplázate hasta la sección **Notificaciones** y haz clic en **Cambiar configuración de notificación.**

4. Deslice el interruptor a **Desactivado** o **Activado** para deshabilitar o habilitar notificaciones adicionales.

**Utilice la directiva de grupo para deshabilitar notificaciones adicionales:**

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón derecho en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directivas de** grupo vaya a Configuración del **equipo.**

3. Haga clic en **Plantillas administrativas**.

4. Expanda el árbol a **componentes Windows > Antivirus de Microsoft Defender > Informes**.

5. Haga doble clic en **Desactivar notificaciones mejoradas** y establezca la opción **en Habilitado**. Haga clic en **Aceptar**. Esto evitará que aparezcan notificaciones adicionales.

## <a name="configure-standard-notifications-on-endpoints"></a>Configurar notificaciones estándar en puntos de conexión

Puede utilizar la directiva de grupo para:

- Mostrar texto adicional y personalizado en los puntos de conexión cuando el usuario necesita realizar una acción
- Ocultar todas las notificaciones en los puntos de conexión
- Ocultar notificaciones de reinicio en puntos de conexión

Ocultar notificaciones puede ser útil en situaciones en las que no se puede ocultar toda la interfaz Antivirus de Microsoft Defender. Consulte [Impedir que los usuarios vean o interactúen con la interfaz de usuario Antivirus de Microsoft Defender](prevent-end-user-interaction-microsoft-defender-antivirus.md) para obtener más información. 

> [!NOTE]
> La ocultación de notificaciones solo se producirá en los puntos de conexión a los que se ha implementado la directiva. Las notificaciones relacionadas con las acciones que se deben realizar (como un reinicio) seguirán apareciendo en el [panel de supervisión Microsoft Endpoint Manager Endpoint Protection y los informes.](/configmgr/protect/deploy-use/monitor-endpoint-protection) 

Consulte [Personalizar la aplicación Seguridad de Windows para su organización](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) para obtener instrucciones para agregar información de contacto personalizada a las notificaciones que los usuarios ven en sus equipos.

**Utilice la directiva de grupo para ocultar las notificaciones:**

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón derecho en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directivas de** grupo vaya a Configuración del **equipo** y haga clic en **Plantillas administrativas**.

3. Expanda el árbol a **componentes Windows > Antivirus de Microsoft Defender > interfaz cliente**. 

4. Haga doble clic en **Suprimir todas las notificaciones** y establezca la opción **en Habilitado**. Haga clic en **Aceptar**. Esto evitará que aparezcan notificaciones adicionales.

**Utilice la directiva de grupo para ocultar las notificaciones de reinicio:**

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón derecho en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directivas de** grupo vaya a Configuración del **equipo.**

3. Haga clic en **Plantillas administrativas**.

4. Expanda el árbol a **componentes Windows > Antivirus de Microsoft Defender > interfaz cliente**.

5. Haga doble clic en **Suprime las notificaciones de reinicio** y establezca la opción **en Habilitado**. Haga clic en **Aceptar**. Esto evitará que aparezcan notificaciones adicionales.

## <a name="related-topics"></a>Temas relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Configurar la interacción del usuario final con Antivirus de Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md)
