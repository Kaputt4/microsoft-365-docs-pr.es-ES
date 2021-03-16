---
title: Panel de usuarios de administración de riesgos de Insider
description: Información sobre la administración de riesgos insider Panel de usuarios en Microsoft 365
keywords: Microsoft 365, administración de riesgos insider, administración de riesgos, cumplimiento
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: e59fb8a32275a2ef7c4865e93400b97ad5560df5
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "50820009"
---
# <a name="insider-risk-management-users-dashboard"></a>Panel de usuarios de administración de riesgos de Insider

El **panel Usuarios es** una herramienta importante en el flujo de trabajo de administración de riesgos de insider y ayuda a los investigadores y analistas a comprender mejor las actividades de riesgo. Este panel ofrece vistas y características de administración para satisfacer las necesidades administrativas entre la creación de directivas de administración de riesgos internas y la administración de casos de administración de riesgos de información interna.

Después de agregar usuarios a directivas de administración de riesgos internas, los procesos en segundo plano evalúan automáticamente las actividades de los usuarios para [desencadenar indicadores](insider-risk-management-settings.md#indicators). Después de activar los indicadores, se asignan puntuaciones de riesgo a las actividades del usuario. Algunas de estas actividades pueden dar como resultado una alerta de riesgo insider, pero es posible que algunas actividades no cumplan un nivel mínimo de puntuación de riesgo y no se cree una alerta de riesgo de información interna. El **panel Usuarios** le permite ver usuarios con estos tipos de indicadores y puntuaciones de riesgo, así como los usuarios que tienen alertas de riesgo insider activas.

Obtenga más información sobre cómo el panel Usuarios muestra a los usuarios en los siguientes escenarios:

- Usuarios con alertas de directiva de riesgo de insider activas
- Usuarios con eventos desencadenados
- Usuarios agregados temporalmente a directivas

## <a name="users-with-active-insider-risk-policy-alerts"></a>Usuarios con alertas de directiva de riesgo de insider activas

El **panel Usuarios muestra** automáticamente todos los usuarios con alertas activas de directiva de riesgos de insider. Estos usuarios con alertas tienen un indicador de activación y una puntuación de riesgo de actividad que cumple los requisitos para crear una alerta de riesgo de información interna. Las actividades de estos usuarios se ven  seleccionando el usuario en el panel Usuarios y navegando a la **pestaña Actividad del** usuario.

## <a name="users-with-triggering-events"></a>Usuarios con eventos desencadenados

El **panel Usuarios** muestra automáticamente todos los usuarios con eventos desencadenados, pero que no tienen una puntuación de riesgo de actividad que crearía una alerta de riesgo de insider. Por ejemplo, se muestra un usuario con una fecha de dimisión notificada porque esta actividad es un evento desencadenante, pero no es una actividad que tiene una puntuación de riesgo. Las actividades de estos usuarios se ven  seleccionando el usuario en el panel Usuarios y navegando a la **pestaña Actividad del** usuario.

## <a name="users-added-temporarily-to-policies"></a>Usuarios agregados temporalmente a directivas

El **panel Usuarios incluye** usuarios agregados a directivas de administración de riesgos de insider después de un evento inusual fuera del flujo de trabajo de administración de riesgos de insider. Agregar temporalmente usuarios (desde el panel Directivas) también es una forma de empezar a puntuar la actividad del usuario para una directiva de administración de riesgos de insider para probar la directiva, incluso si no se ha configurado un conector necesario.

Cuando un usuario se agrega manualmente a una directiva, las actividades de usuario de los 90 días anteriores se puntuan y se agregan a la escala **de tiempo de actividad del** usuario. Por ejemplo, actualmente no se le asignan puntuaciones de riesgo a un usuario para una directiva de riesgo de insider y el usuario tiene actividades de pérdida de datos notificadas al departamento legal de su organización. El departamento legal recomienda configurar nuevos requisitos de supervisión a corto plazo para el usuario. Puede asignar temporalmente al usuario a la *directiva de* pérdida de datos durante un período de tiempo designado (ventana de activación). Todos los usuarios agregados temporalmente  se muestran en el panel Usuarios porque se renuncia a los requisitos de eventos desencadenados.

>[!NOTE]
>Los nuevos usuarios agregados manualmente pueden tardar varias horas en aparecer en el panel **Usuarios.** Las actividades de los 90 días anteriores para estos usuarios pueden tardar hasta 24 horas en mostrarse. Para ver las actividades de los usuarios agregados manualmente, seleccione el usuario en el panel Usuarios y abra la pestaña **Actividad de** usuario en el panel de detalles. 

El usuario se quita  automáticamente del panel Usuarios y la puntuación se detiene cuando expira el tiempo definido en la **ventana** Activación si:

- el usuario no tiene eventos de desencadenamiento adicionales ni alertas de directiva de riesgo interno, y
- si la duración de la ventana **Activación** definida manualmente es mayor que la duración de la ventana **de activación de directiva** global.

El **valor de la ventana** Activación con la duración más larga siempre invalida la configuración **de** la ventana Activación con una duración más corta. Por ejemplo, ha configurado  la ventana Activación en la pestaña **Períodos** de tiempo de la directiva global en la configuración global de administración de riesgos de insider durante 15 días, que se aplica automáticamente a todas las directivas de riesgo de insider. 

Se agrega temporalmente un usuario a la directiva de riesgos de *pérdidas* de datos y se definen 30 días como la ventana **activación** para este usuario. La configuración **de la** ventana de activación global  de 15 días se invalida definiendo la configuración de la ventana Activación de 30 días para el usuario agregado temporalmente. El usuario agregado temporalmente permanecerá  en el panel Usuarios y estará en el ámbito de la directiva durante 30 días.

En el escenario opuesto en el que  la configuración de la ventana Activación **global** es  más larga que  la configuración de la ventana Activación definida para un usuario agregado temporalmente, la configuración global de la ventana Activación invalidaría la configuración de la ventana Activación del usuario agregado temporalmente. El usuario agregado temporalmente permanecerá  en el panel Usuarios y estará en el ámbito de la directiva para el número de días definidos en la configuración global **de la ventana Activación.**

## <a name="view-user-information-on-the-users-dashboard"></a>Ver información de usuario en el panel Usuarios

Cada usuario que se muestra en el **panel Usuarios** tiene la siguiente información:

- **Usuarios:** el nombre de usuario de un usuario. Este campo se anonimiza si la configuración de anonimización global para la administración de riesgos de insider está habilitada.
- **Nivel de riesgo:** el nivel de riesgo calculado actual del usuario. Esta puntuación se calcula cada 24 horas y usa las puntuaciones de riesgo de alerta de todas las alertas activas asociadas al usuario. Para los usuarios que solo tienen indicadores desencadenantes, el nivel de riesgo es cero.
- **Alertas activas:** número de alertas activas para todas las directivas.
- **Infracciones confirmadas:** el número de casos resueltos como *infracción de directiva confirmada* para el usuario.
- **Case:** el caso activo actual del usuario.

![Panel de usuarios de administración de riesgos de Insider](../media/insider-risk-users-dashboard.png)

>[!NOTE]
>El número de usuarios que se muestran en el **panel** Usuarios puede ser limitado en algunos casos, según el volumen de alertas activas y las directivas de coincidencia. Los usuarios con alertas  activas se muestran en el panel Usuarios a medida que se generan las alertas y puede haber casos raros cuando se alcanza el número máximo de usuarios mostrados. Si se produce este límite, los usuarios con alertas activas que no se muestran se agregarán al panel Usuarios a medida que se triagen las alertas de usuario existentes. 

## <a name="view-user-details"></a>Ver detalles del usuario

Para ver más detalles sobre la actividad de riesgo de un usuario, abra el panel de detalles del usuario haciendo doble clic en un usuario en el panel **Usuarios**. En el panel de detalles, puede ver la siguiente información:

- **Pestaña Perfil de** usuario
    - **Nombre y título:** el nombre y el título de posición del usuario de Azure Active Directory. Estos campos de usuario se anonimizarán o vaciarán si la configuración de anonimización global para la administración de riesgos de insider está habilitada.
    - **Correo electrónico del** usuario: la dirección de correo electrónico del usuario.
    - **Alias:** alias de red para el usuario.
    - **Organización o departamento:** la organización o el departamento del usuario.

- **Pestaña Actividad del** usuario
    - **Historial de actividad de usuario reciente:** enumera los indicadores desencadenantes y los indicadores de riesgo interno de las actividades del usuario hasta los últimos 180 días. Todas las actividades pertinentes a los indicadores de riesgo de insider también se puntuan, aunque las actividades pueden o no haber generado una alerta de riesgo de información interna. Los ejemplos de indicadores desencadenantes pueden ser una fecha de dimisión o la última fecha de trabajo programada para el usuario. Los indicadores de riesgo insider son actividades determinadas que tienen un elemento de riesgo y se definen en las directivas en las que está incluido el usuario. Las actividades de eventos y riesgos se enumeran con el elemento más reciente que aparece primero.

## <a name="remove-users-from-in-scope-assignment-to-policies"></a>Quitar usuarios de la asignación en el ámbito a directivas

Puede haber escenarios en los que tenga que dejar de asignar puntuaciones de riesgo a la actividad de un usuario en directivas de administración de riesgos internas. Use Quitar usuarios  **en** la página Panel de usuarios para dejar de asignar puntuaciones de riesgo para uno o más usuarios de todas las directivas de administración de riesgos internas para las que están actualmente en el ámbito. Esta acción no quita usuarios de la asignación general de directivas (al agregar usuarios o grupos a una configuración de directiva), sino que simplemente quita a los usuarios del procesamiento activo mediante directivas después de eventos de activación actuales. Si los usuarios tienen otro evento desencadenante en el futuro, las puntuaciones de riesgo de las directivas empezarán a asignarse automáticamente a los usuarios de nuevo. No se quitarán las alertas o casos existentes para este usuario.

>[!NOTE]
>La eliminación de un usuario de una directiva puede tardar varios minutos en completarse. Una vez completado, el usuario ya no aparecerá en la página Usuarios. Si el usuario eliminado tiene alertas o casos activos, el usuario permanecerá en la página Usuarios y los detalles del usuario mostrarán que ya no están en el ámbito de una directiva.

Para quitar manualmente los usuarios del estado del ámbito en todas las directivas de administración de riesgos internas, siga estos pasos:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña** Usuarios.
2. En el **panel Usuarios,** seleccione el usuario o los usuarios que desea quitar de estar en el ámbito en las directivas de administración de riesgos internas.
3. Seleccione **Quitar usuarios**.
4. En el **panel Quitar usuario,** **seleccione** Quitar o **Cancelar** para descartar los cambios y cerrar el cuadro de diálogo.
5. Seleccione **Quitar** en el panel de confirmación para quitar al usuario.

## <a name="run-automated-tasks-with-power-automate-flows-for-a-user"></a>Ejecutar tareas automatizadas con flujos de Power Automate para un usuario

Con los flujos recomendados de Power Automate, los investigadores y analistas de riesgos pueden tomar medidas rápidamente para:

- Notificar a los usuarios cuando se agregan a una directiva de riesgo de insider

Para ejecutar, administrar o crear flujos de Power Automate para un usuario de administración de riesgos interno:

1. Seleccione **Automatizar en** la barra de herramientas de acciones del usuario.
2. Elija el flujo de Power Automate que se ejecutará y, a continuación, **seleccione Ejecutar flujo**.
3. Una vez completado el flujo, seleccione **Listo**.

Para obtener más información sobre los flujos de Power Automate para la administración de riesgos de insider, consulte Introducción a la configuración de administración de riesgos [insider](insider-risk-management-settings.md#power-automate-flows-preview).
