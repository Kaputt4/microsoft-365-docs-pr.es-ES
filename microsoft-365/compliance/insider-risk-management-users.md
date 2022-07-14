---
title: Panel usuarios de administración de riesgos internos
description: Más información sobre el panel usuarios de administración de riesgos internos en Microsoft Purview
keywords: Microsoft 365, Microsoft Purview, riesgo interno, administración de riesgos, cumplimiento
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
ms.openlocfilehash: 14c0d5127f4b370d78b54512d8780d1cc7dfbf67
ms.sourcegitcommit: 221212fff9737e0ea386755deb8fed62ae9c254b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66787658"
---
# <a name="insider-risk-management-users-dashboard"></a>Panel usuarios de administración de riesgos internos

El **panel Usuarios** es una herramienta importante en el flujo de trabajo de administración de riesgos internos y ayuda a los investigadores y analistas a comprender mejor las actividades de riesgo. Este panel ofrece vistas y características de administración para satisfacer las necesidades administrativas entre la creación de directivas de administración de riesgos internos y la administración de casos de administración de riesgos internos.

Una vez que los usuarios se agregan a las directivas de administración de riesgos internos, los procesos en segundo plano evalúan automáticamente las actividades del usuario para [desencadenar indicadores](insider-risk-management-settings.md#indicators). Una vez que los indicadores desencadenantes están presentes, a las actividades del usuario se les asignan puntuaciones de riesgo. Algunas de estas actividades pueden dar lugar a una alerta de riesgo interno, pero es posible que algunas actividades no cumplan un nivel mínimo de puntuación de riesgo y no se cree una alerta de riesgo interno. El **panel Usuarios** le permite ver los usuarios con estos tipos de indicadores y puntuaciones de riesgo, así como los usuarios que tienen alertas de riesgo internos activas.

Obtenga más información sobre cómo el panel Usuarios muestra a los usuarios en los siguientes escenarios:

- Usuarios con alertas de directivas de riesgo internas activas
- Usuarios con eventos desencadenantes
- Usuarios agregados temporalmente a las directivas

## <a name="users-with-active-insider-risk-policy-alerts"></a>Usuarios con alertas de directivas de riesgo internas activas

El **panel Usuarios** muestra automáticamente todos los usuarios con alertas de directivas de riesgo internas activas. Estos usuarios con alertas tienen un indicador desencadenante y una puntuación de riesgo de actividad que cumple los requisitos para crear una alerta de riesgo interno. Para ver las actividades de estos usuarios, seleccione el usuario en el **panel Usuarios** y vaya a la pestaña **Actividad de usuario** .

## <a name="users-with-triggering-events"></a>Usuarios con eventos desencadenantes

El **panel Usuarios** muestra automáticamente todos los usuarios con eventos desencadenantes, pero que no tienen una puntuación de riesgo de actividad que crearía una alerta de riesgo interno. Por ejemplo, se muestra un usuario con una fecha de renuncia notificada porque esta actividad es un evento desencadenante, pero no es una actividad que tiene una puntuación de riesgo. Para ver las actividades de estos usuarios, seleccione el usuario en el **panel Usuarios** y vaya a la pestaña **Actividad de usuario** .

## <a name="users-added-temporarily-to-policies"></a>Usuarios agregados temporalmente a las directivas

El **panel Usuarios** incluye usuarios agregados a directivas de administración de riesgos internos después de un evento inusual fuera del flujo de trabajo de administración de riesgos internos. Agregar usuarios temporalmente (desde el panel Directivas) también es una manera de empezar a puntuar la actividad de usuario para una directiva de administración de riesgos internos para probar la directiva, incluso si no se configura un conector necesario.

Cuando un usuario se agrega manualmente a una directiva, las actividades de usuario de los 90 días anteriores se puntúan y se agregan a la escala de tiempo **de actividad de usuario** . Por ejemplo, tiene un usuario que no tiene actualmente puntuaciones de riesgo asignadas para una directiva de riesgo interno y el usuario tiene actividades de pérdida de datos notificadas al departamento legal de su organización. El departamento legal recomienda configurar nuevos requisitos de detección a corto plazo para el usuario. Puede asignar temporalmente el usuario a la directiva *de pérdidas de datos* durante un período de tiempo designado (ventana de activación). Todos los usuarios agregados temporalmente se muestran en el **panel Usuarios** porque se renuncia a los requisitos de eventos desencadenantes.

> [!NOTE]
> Los nuevos usuarios agregados manualmente pueden tardar varias horas en aparecer en el **panel Usuarios**. Las actividades de los 90 días anteriores de estos usuarios pueden tardar hasta 24 horas en aparecer. Para ver las actividades de los usuarios agregados manualmente, seleccione el usuario en el **panel Usuarios** y abra la pestaña **Actividad de usuario** en el panel de detalles.

El usuario se quita automáticamente del **panel Usuarios** y la puntuación se detiene cuando la hora definida en la **ventana Activación** expira si:

- el usuario no tiene ningún evento desencadenante adicional ni alertas de directivas de riesgo internos, y
- si la duración de la **ventana de activación** definida manualmente es mayor que la duración de la **ventana de activación** de la directiva global.

La configuración **de la ventana Activación** con la duración más larga siempre invalida la configuración de **la ventana Activación** con una duración más corta. Por ejemplo, ha configurado la **ventana Activación** en la pestaña **Períodos de tiempo de directiva globales** en la configuración global de administración de riesgos internos durante 15 días, que se aplica automáticamente a todas las directivas de riesgo internos.

Agregue temporalmente un usuario a la directiva de riesgo de *pérdidas de datos* internas y defina 30 días como la **ventana Activación** para este usuario. La configuración global de **la ventana Activación** de 15 días se invalida al definir la configuración de ventana **Activación** de 30 días para el usuario agregado temporalmente. El usuario agregado temporalmente permanecerá en el **panel Usuarios** y estará en el ámbito de la directiva durante 30 días.

En el escenario opuesto en el que la configuración de **la ventana de activación** global es más larga que la configuración de **la ventana Activación** definida para un usuario agregado temporalmente, la configuración de **la ventana de activación** global invalidaría la configuración de **la ventana Activación** para el usuario agregado temporalmente. El usuario agregado temporalmente permanecerá en el **panel Usuarios** y estará en el ámbito de la directiva durante el número de días definido en la configuración de la **ventana de activación** global.

## <a name="view-user-information-on-the-users-dashboard"></a>Visualización de la información del usuario en el panel Usuarios

Cada usuario que se muestra en el **panel Usuarios** tiene la siguiente información:

- **Usuarios**: nombre de usuario de un usuario. Este campo se anonimiza si la configuración de anonimización global para la administración de riesgos internos está habilitada.
- **Nivel de riesgo**: el nivel de riesgo calculado actual del usuario. Esta puntuación se calcula cada 24 horas y usa las puntuaciones de riesgo de alerta de todas las alertas activas asociadas al usuario. En el caso de los usuarios con solo indicadores desencadenantes, el nivel de riesgo es cero.
- **Alertas activas**: número de alertas activas para todas las directivas.
- **Infracciones confirmadas**: el número de casos resueltos como *infracción de directiva confirmada* para el usuario.
- **Caso**: el caso activo actual del usuario.

Para localizar rápidamente un usuario específico, use **Buscar** en la parte superior derecha del panel Usuario. Al buscar usuarios, debe usar el nombre principal de usuario (UPN). Por ejemplo, al buscar un usuario llamado "Tiara Hidayah" que tenga un UPN de "thidayah" en su organización, escribiría "thidayah" o alguna parte del UPN en **La búsqueda**.

![Panel de usuarios de administración de riesgos internos.](../media/insider-risk-users-dashboard.png)

> [!NOTE]
> El número de usuarios que se muestra en el **panel Usuarios** puede estar limitado en algunos casos, en función del volumen de alertas activas y las directivas de coincidencia. Los usuarios con alertas activas se muestran en el **panel Usuarios** a medida que se generan las alertas y puede haber casos poco frecuentes cuando se alcanza el número máximo de usuarios mostrados. Si se produce este límite, los usuarios con alertas activas que no se muestran se agregarán al **panel Usuarios** a medida que se triagen las alertas de usuario existentes.

## <a name="view-user-details"></a>Ver los detalles del usuario

Para ver más detalles sobre la actividad de riesgo de un usuario, abra el panel de detalles del usuario haciendo doble clic en un usuario en el **panel Usuarios**. En el panel de detalles, puede ver la siguiente información:

- **Pestaña Perfil de usuario**
  - **Nombre y título**: nombre y título de posición para el usuario de Azure Active Directory. Estos campos de usuario se anonimizarán o estarán vacíos si la configuración de anonimización global para la administración de riesgos internos está habilitada.
  - **Correo electrónico** del usuario: la dirección de correo electrónico del usuario.
  - **Alias**: alias de red para el usuario.
  - **Organización o departamento**: la organización o el departamento del usuario.

- **Pestaña Actividad de usuario**
  - **Historial de actividad reciente del usuario**: enumera tanto los indicadores desencadenantes como los indicadores de riesgo interno para las actividades del usuario hasta los últimos 180 días. Todas las actividades pertinentes a los indicadores de riesgo internos también se puntúan, aunque las actividades pueden haber generado o no una alerta de riesgo interno. Los ejemplos de indicadores desencadenantes pueden ser una fecha de renuncia o la última fecha programada de trabajo para el usuario. Los indicadores de riesgo internos son actividades que se determinan para tener un elemento de riesgo y se definen en las directivas en las que se incluye el usuario. Las actividades de evento y riesgo se enumeran en primer lugar con el elemento más reciente.

## <a name="remove-users-from-in-scope-assignment-to-policies"></a>Eliminación de usuarios de la asignación en el ámbito a las directivas

Puede haber escenarios en los que tenga que dejar de asignar puntuaciones de riesgo a la actividad de un usuario en directivas de administración de riesgos internos. Use **Quitar usuarios** en la página **Del panel Usuarios** para dejar de asignar puntuaciones de riesgo a uno o más usuarios de todas las directivas de administración de riesgos internos para las que están actualmente en el ámbito. Esta acción no quita a los usuarios de la asignación general de directivas (al agregar usuarios o grupos a una configuración de directiva), sino que simplemente quita a los usuarios del procesamiento activo por directivas después de los eventos desencadenantes actuales. Si los usuarios tienen otro evento desencadenante en el futuro, las puntuaciones de riesgo de las directivas comenzarán a asignarse automáticamente a los usuarios de nuevo. No se quitarán las alertas o casos existentes para este usuario.

> [!NOTE]
> La eliminación de un usuario de una directiva puede tardar varios minutos en completarse. Una vez completado, el usuario ya no aparecerá en la página Usuarios. Si el usuario quitado tiene alertas o casos activos, el usuario permanecerá en la página Usuarios y los detalles del usuario mostrarán que ya no están en el ámbito de una directiva.

Para quitar manualmente los usuarios del estado dentro del ámbito en todas las directivas de administración de riesgos internos, siga estos pasos:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **Usuarios**.
2. En el **panel Usuarios**, seleccione el usuario o los usuarios que desea quitar de estar en el ámbito de las directivas de administración de riesgos internos.
3. Seleccione **Quitar usuarios**.
4. En el panel **Quitar usuario** , seleccione **Quitar** o **Cancelar** para descartar los cambios y cerrar el cuadro de diálogo.
5. Seleccione **Quitar** en el panel de confirmación para quitar el usuario.

## <a name="run-automated-tasks-with-power-automate-flows-for-a-user"></a>Ejecución de tareas automatizadas con flujos de Power Automate para un usuario

Con los flujos recomendados de Power Automate, los investigadores y analistas de riesgo pueden tomar medidas rápidamente para:

- Notificar a los usuarios cuando se agregan a una directiva de riesgo interno

Para ejecutar, administrar o crear flujos de Power Automate para un usuario de administración de riesgos internos:

1. Seleccione **Automatizar** en la barra de herramientas de acciones del usuario.
2. Elija el flujo de Power Automate que se va a ejecutar y, a continuación, seleccione **Ejecutar flujo**.
3. Una vez completado el flujo, seleccione **Listo**.

Para más información sobre los flujos de Power Automate para la administración de riesgos internos, consulte [Introducción a la configuración de administración de riesgos internos](insider-risk-management-settings.md#power-automate-flows-preview).
