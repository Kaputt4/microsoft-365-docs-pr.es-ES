---
title: Panel usuarios de administración de riesgos de Insider
description: Obtenga información sobre el panel usuarios de administración de riesgos interno en Microsoft 365
keywords: Microsoft 365, administración de riesgos interno, administración de riesgos, cumplimiento
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
ms.openlocfilehash: 224221950104b5dee6a6e8f179db34ee6fad014e
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208776"
---
# <a name="insider-risk-management-users-dashboard"></a>Panel usuarios de administración de riesgos de Insider

El **panel Usuarios es** una herramienta importante en el flujo de trabajo de administración de riesgos de Insider y ayuda a los investigadores y analistas a comprender mejor las actividades de riesgo. Este panel ofrece vistas y características de administración para satisfacer las necesidades administrativas entre la creación de directivas de administración de riesgos internas y la administración de casos de administración de riesgos internas.

Después de agregar usuarios a las directivas de administración de riesgos internos, los procesos en segundo plano evalúan automáticamente las actividades de los usuarios para activar [indicadores.](insider-risk-management-settings.md#indicators) Después de que los indicadores desencadenantes estén presentes, se asignan puntuaciones de riesgo a las actividades del usuario. Algunas de estas actividades pueden dar como resultado una alerta de riesgo interno, pero es posible que algunas actividades no cumplan un nivel mínimo de puntuación de riesgo y no se cree una alerta de riesgo interno. El **panel Usuarios** te permite ver usuarios con estos tipos de indicadores y puntuaciones de riesgo, así como los usuarios que tienen alertas de riesgo insider activas.

Además, puede haber escenarios en los que necesite agregar temporalmente usuarios a directivas de riesgo interno después de que se notifica un evento inusual fuera del flujo de trabajo de administración de riesgos de Insider. El **panel Usuarios** permite agregar manualmente un usuario a una directiva de riesgo interno durante un período de tiempo específico y omitir el requisito de que un usuario tenga un indicador desencadenante. Estos usuarios siempre se muestran en el panel Usuarios cuando se asignan activamente a una directiva.

Obtenga más información sobre cómo el panel Usuarios muestra los usuarios en los siguientes escenarios:

- Usuarios de panel con alertas activas de directiva de riesgo interno
- Usuarios del panel con indicadores desencadenantes
- Usuarios de panel agregados temporalmente a las directivas

## <a name="dashboard-users-with-active-insider-risk-policy-alerts"></a>Usuarios de panel con alertas activas de directiva de riesgo interno

El **panel Usuarios muestra** automáticamente todos los usuarios con alertas activas de directiva de riesgo interno. Estos usuarios con alertas tienen un indicador desencadenante y una puntuación de riesgo de actividad que cumple los requisitos para crear una alerta de riesgo interno. Las actividades de estos usuarios se ven  seleccionando el usuario en el panel Usuarios y navegando a la **pestaña Actividad del** usuario.

## <a name="dashboard-users-with-triggering-indicators"></a>Usuarios del panel con indicadores desencadenantes

El **panel Usuarios** muestra automáticamente todos los usuarios con indicadores desencadenantes, pero que no tienen una puntuación de riesgo de actividad que crearía una alerta de riesgo interno. Por ejemplo, se muestra un usuario con una fecha de dimisión notificada porque este evento es un indicador desencadenante, pero no es una actividad que tiene una puntuación de riesgo. Las actividades de estos usuarios se ven  seleccionando el usuario en el panel Usuarios y navegando a la **pestaña Actividad del** usuario.

## <a name="dashboard-users-added-temporarily-to-policies"></a>Usuarios de panel agregados temporalmente a las directivas

El **panel Usuarios permite** agregar temporalmente usuarios a una directiva de administración de riesgos interno existente después de un evento inusual fuera del flujo de trabajo de administración de riesgos interno. La adición temporal de usuarios también es una forma de agregar usuarios a una directiva de administración de riesgos internas para probar la directiva, incluso si no se ha configurado un conector necesario.

Cuando un usuario se agrega manualmente a una directiva, las actividades de usuario de los 90 días anteriores se puntuan y se agregan a la escala de tiempo **de actividad de** usuario. Por ejemplo, tiene un usuario que no está actualmente en el ámbito de una directiva de riesgo interno y el usuario tiene actividades de pérdida de datos notificadas al departamento legal de su organización. El departamento legal recomienda configurar nuevos requisitos de supervisión a corto plazo para el usuario. Puede asignar temporalmente al usuario a la directiva *de pérdidas* de datos durante un período de tiempo designado (ventana de activación). Todos los usuarios agregados temporalmente  se muestran en el panel Usuarios porque no se cumplen los requisitos del indicador desencadenante.

>[!NOTE]
>Los nuevos usuarios agregados manualmente pueden tardar varias horas en aparecer en el panel **Usuarios.** Las actividades de los 90 días anteriores para estos usuarios pueden tardar hasta 24 horas en mostrarse. Para ver las actividades de los usuarios agregados manualmente,  seleccione el usuario en el panel Usuarios y abra la pestaña Actividad del usuario en el panel de detalles. 

El usuario se quita automáticamente de la  directiva insider y el  panel Usuarios cuando expira el tiempo definido en la ventana Activación si:

- el usuario no tiene indicadores desencadenantes ni alertas de directiva de riesgo interno, y
- si la duración  de la ventana Activación definida manualmente es mayor que la duración de la ventana **Activación de directiva** global. 

La **configuración de la ventana** Activación con  la duración más larga siempre invalida la configuración de la ventana Activación con una duración más corta. Por ejemplo, has configurado  la ventana Activación en la pestaña **Períodos** de tiempo de directiva global en la configuración global de administración de riesgos de Insider durante 15 días, que se aplica automáticamente a todas las directivas de riesgo de Insider. 

Se agrega temporalmente un usuario a la directiva de *pérdidas* de datos de riesgo interno y se definen 30 días como la ventana Activación **para** este usuario. La configuración de **la ventana** Activación global de  15 días se reemplaza definiendo la configuración de la ventana Activación de 30 días para el usuario agregado temporalmente. El usuario agregado temporalmente permanecerá  en el panel Usuarios y estará dentro del ámbito de la directiva durante 30 días.

En el escenario opuesto en el que  la configuración de la ventana Activación **global** es más larga que  la configuración de la ventana Activación definida para un usuario agregado temporalmente, la configuración de la ventana Activación **global** invalidaría la configuración de la ventana Activación para el usuario agregado temporalmente. El usuario agregado temporalmente permanecerá  en el panel Usuarios y estará dentro del ámbito de la directiva para el número de días definidos en la configuración de la ventana de **activación** global.

## <a name="view-user-information-on-the-users-dashboard"></a>Ver información de usuario en el panel Usuarios

Cada usuario que se muestra en el **panel Usuarios** tiene la siguiente información:

- **Usuarios:** el nombre de usuario de un usuario. Este campo se anonimiza si la configuración de anonimización global para la administración de riesgos interno está habilitada.
- **Nivel de** riesgo: el nivel de riesgo calculado actual del usuario. Esta puntuación se calcula cada 24 horas y usa las puntuaciones de riesgo de alerta de todas las alertas activas asociadas al usuario. Para los usuarios que solo activan indicadores, el nivel de riesgo es cero.
- **Alertas activas:** número de alertas activas para todas las directivas.
- **Infracciones confirmadas:** el número de casos resueltos como *infracción de directiva confirmada* para el usuario.
- **Caso:** el caso activo actual para el usuario.

![Panel de usuarios de administración de riesgos de Insider](../media/insider-risk-users-dashboard.png)

>[!NOTE]
>El número de usuarios  que se muestra en el panel Usuarios puede estar limitado en algunos casos, en función del volumen de alertas activas y las directivas de coincidencia. Los usuarios con alertas  activas se muestran en el panel Usuarios a medida que se generan las alertas y puede haber casos excepcionales cuando se alcanza el número máximo de usuarios mostrados. Si esto ocurre, los usuarios con alertas activas que  no se muestran se agregarán al panel Usuarios, ya que se clasifican las alertas de usuario existentes.

## <a name="view-user-details"></a>Ver detalles del usuario

Para ver más detalles sobre la actividad de riesgo de un usuario, abra el panel de detalles del usuario haciendo doble clic en un usuario en el panel **Usuarios.** En el panel de detalles, puede ver la siguiente información:

- **Pestaña Perfil de** usuario
    - **Nombre y título:** el nombre y el título de posición del usuario de Azure Active Directory. Estos campos de usuario se anonimizarán o estarán vacíos si la configuración de anonimización global para la administración de riesgos interno está habilitada.
    - **Correo electrónico del** usuario: la dirección de correo electrónico del usuario.
    - **Alias:** alias de red para el usuario.
    - **Organización o departamento:** la organización o el departamento del usuario.

- **Pestaña Actividad del** usuario
    - **Historial de actividad de usuario** reciente: enumera los indicadores desencadenantes y los indicadores de riesgo interno de las actividades del usuario hasta los últimos 180 días. También se puntuan todas las actividades pertinentes para los indicadores de riesgo interno, aunque las actividades pueden o no haber generado una alerta de riesgo interno. Los ejemplos de indicadores desencadenantes pueden ser una fecha de dimisión o la última fecha de trabajo programada para el usuario. Los indicadores de riesgo de Insider son actividades determinadas que tienen un elemento de riesgo y se definen en las directivas en las que está incluido el usuario. Las actividades de eventos y riesgos se enumeran con el elemento más reciente en primer lugar.

## <a name="temporarily-add-a-user-to-a-policy"></a>Agregar temporalmente un usuario a una directiva

Para agregar temporalmente un usuario a una directiva de  administración de riesgos de **Insider,** usará la pestaña Usuarios en la solución de administración de riesgos de Insider en el Centro de cumplimiento de Microsoft 365. Los usuarios agregados omiten manualmente los requisitos de indicador desencadenante para la directiva a la que se agregan y se muestran en el panel **Usuarios.** Para agregar permanentemente un usuario a una directiva de administración de riesgos interno, usarás el asistente para directivas.

Complete los pasos siguientes para agregar un usuario a una directiva de riesgo interno existente:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña** Usuarios.
2. Seleccione **Agregar un usuario a una directiva en** la barra de herramientas.
3. En el **cuadro de diálogo Agregar un nuevo** usuario, empiece a escribir un nombre de usuario en el **campo** Usuario. Seleccione el usuario que desea agregar a una directiva.
4. Seleccione la flecha desplegable del **campo** Directiva para mostrar las directivas de administración de riesgos internas configuradas. Seleccione la directiva a la que desea agregar el usuario.
5. Usa el **control deslizante de la ventana** Activación para definir cuánto tiempo se incluye al usuario en una directiva y se muestra en el panel Usuarios. El tiempo que especifique determina cuánto tiempo está activa la directiva para este usuario y se inicia cuando se genera la primera alerta o se detecta un indicador desencadenante (como una coincidencia de directiva DLP). El intervalo de la **ventana Activación es** de 5 a 30 días.
6. Seleccione **Agregar** y, **a continuación,** confirme para agregar el usuario a la directiva.

>[!NOTE]
>Los nuevos usuarios agregados manualmente pueden tardar varias horas en aparecer en el panel **Usuarios.** Las actividades de los 90 días anteriores para estos usuarios pueden tardar hasta 24 horas en mostrarse. Para ver las actividades de los usuarios agregados manualmente,  seleccione el usuario en el panel Usuarios y abra la pestaña Actividad del usuario en el panel de detalles. 

## <a name="run-automated-tasks-with-power-automate-flows-for-a-user"></a>Ejecutar tareas automatizadas con flujos de Power Automate para un usuario

Con los flujos recomendados de Power Automate, los analistas y los investigadores de riesgos pueden tomar medidas rápidamente para:

- Notificar a los usuarios cuando se agregan a una directiva de riesgo interno

Para ejecutar, administrar o crear flujos de Power Automate para un usuario de administración de riesgos interno:

1. Seleccione **Automatizar en la** barra de herramientas de acciones del usuario.
2. Elija el flujo de Power Automate que desea ejecutar y, a continuación, **seleccione Ejecutar flujo.**
3. Una vez completado el flujo, seleccione **Listo.**

Para obtener más información sobre los flujos de Power Automate para la administración de riesgos interno, consulte Introducción a la configuración de administración de [riesgos de Insider.](insider-risk-management-settings.md#power-automate-flows-preview)
