---
title: Panel de usuarios de administración de riesgos de Insider
description: Obtenga información sobre el panel de usuarios de administración de riesgos de Insider en Microsoft 365
keywords: Microsoft 365, administración de riesgos de Insider, administración de riesgos, cumplimiento
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
# <a name="insider-risk-management-users-dashboard"></a>Panel de usuarios de administración de riesgos de Insider

El **Panel de usuarios** es una herramienta importante en el flujo de trabajo de administración de riesgos de Insider y ayuda a los investigadores y analistas a comprender mejor las actividades de riesgo. Este panel ofrece vistas y características de administración para satisfacer las necesidades administrativas entre la creación de directivas de administración de riesgos de Insider y la administración de casos de administración de riesgos de Insider.

Una vez que se agregan usuarios a las directivas de administración de riesgos de Insider, los procesos en segundo plano evalúan automáticamente las actividades de usuario para [desencadenar indicadores](insider-risk-management-settings.md#indicators). Una vez que se han desencadenado los indicadores, se les asignan los resultados de las actividades de usuario. Algunas de estas actividades pueden dar como resultado una alerta de riesgo de Insider, pero algunas actividades podrían no cumplir un nivel de puntuación de riesgo mínimo y no se creará una alerta de riesgo de Insider. El **Panel de usuarios** le permite ver los usuarios con estos tipos de indicadores y puntuaciones de riesgos, así como los usuarios que tienen alertas activas de riesgo de Insider.

Además, puede haber escenarios en los que necesite agregar temporalmente usuarios a directivas de riesgo de Insider después de que se informe de un evento inusual fuera del flujo de trabajo de administración de riesgos de Insider. El **Panel de usuarios** le permite agregar manualmente un usuario a una directiva de riesgos de Insider durante un período de tiempo específico y omitir el requisito de que un usuario tenga un indicador de activación. Estos usuarios siempre se muestran en el panel usuarios cuando se asigna activamente a una directiva.

Obtenga más información sobre cómo el panel de usuarios muestra a los usuarios en los siguientes escenarios:

- Usuarios del panel con alertas de directiva de riesgos de Insider activos
- Usuarios del panel con indicadores de activación
- Usuarios de panel agregados temporalmente a directivas

## <a name="dashboard-users-with-active-insider-risk-policy-alerts"></a>Usuarios del panel con alertas de directiva de riesgos de Insider activos

El **Panel usuarios** muestra automáticamente todos los usuarios con alertas de directiva de riesgos de Insider activos. Estos usuarios con alertas tienen un indicador de desencadenamiento y una puntuación de riesgo de actividad que cumple los requisitos para crear una alerta de riesgo de Insider. Para ver las actividades de estos usuarios, seleccione el usuario en el **Panel usuarios** y vaya a la pestaña **actividad de usuario** .

## <a name="dashboard-users-with-triggering-indicators"></a>Usuarios del panel con indicadores de activación

El **Panel usuarios** muestra automáticamente todos los usuarios con indicadores de desencadenamiento, pero que no tienen una puntuación de riesgo de actividad que crearía una alerta de riesgo de Insider. Por ejemplo, se muestra un usuario con una fecha de retirada notificada porque este evento es un indicador de activación pero no es una actividad que tiene una puntuación de riesgo. Para ver las actividades de estos usuarios, seleccione el usuario en el **Panel usuarios** y vaya a la pestaña **actividad de usuario** .

## <a name="dashboard-users-added-temporarily-to-policies"></a>Usuarios de panel agregados temporalmente a directivas

El **Panel de usuarios** le permite agregar temporalmente usuarios a una directiva de administración de riesgos de Insider existente después de un evento inusual fuera del flujo de trabajo de administración de riesgos de Insider. Agregar usuarios temporalmente también es una forma de agregar usuarios a una directiva de administración de riesgos de Insider para probar la Directiva, incluso si no se ha configurado un conector necesario.

Cuando se agrega manualmente un usuario a una directiva, las actividades de usuario de los 90 días anteriores se puntuan y se agregan a la escala de tiempo de **actividad del usuario** . Por ejemplo, si un usuario no está actualmente en una directiva de riesgo de Insider y el usuario tiene actividades de pérdida de datos que se notifican al departamento legal de la organización. El departamento jurídico recomienda configurar nuevos requisitos de supervisión a corto plazo para el usuario. Puede asignar temporalmente el usuario a la Directiva de *pérdidas de datos* durante un período de tiempo designado (ventana de activación). Todos los usuarios agregados temporalmente se muestran en el **Panel usuarios** , ya que se condonan los requisitos del indicador de activación.

>[!NOTE]
>Puede tardar varias horas en aparecer nuevos usuarios agregados manualmente en el **Panel de usuarios**. Las actividades de los 90 días anteriores para estos usuarios pueden tardar hasta 24 horas en mostrarse. Para ver las actividades de los usuarios agregados manualmente, seleccione el usuario en el **Panel de usuarios** y abra la ficha **actividad de usuario** en el panel de detalles.

El usuario se quita automáticamente de la Directiva de Insider y del **Panel de usuarios** cuando la hora definida en la **ventana de activación** expira si:

- el usuario no tiene indicadores ni alertas de directiva de riesgos de Insider.
- Si la duración de la **ventana de activación** definida manualmente es superior a la duración de la ventana de **activación** de directiva global. 

La configuración de la **ventana de activación** con la duración más larga siempre invalida la configuración de la **ventana de activación** con una duración menor. Por ejemplo, ha configurado la **ventana de activación** en la pestaña **intervalos de tiempo** global de la Directiva de la configuración global de administración de riesgos de Insider durante 15 días, que se aplica automáticamente a todas las directivas de riesgo de Insider. 

Se agrega temporalmente a un usuario a sus *datos pérdidas* de directiva de riesgo de Insider y se definen 30 días como **ventana de activación** para este usuario. La configuración de 15 días de la **ventana de activación** global se reemplaza definiendo la configuración de la **ventana de activación** de 30 días para el usuario agregado temporalmente. El usuario agregado temporalmente permanecerá en el **Panel usuarios** y estará en el ámbito de la Directiva durante 30 días.

En el escenario opuesto donde la configuración de la **ventana de activación** global es más larga que la configuración de la **ventana de activación** definida para un usuario agregado temporalmente, la configuración de la ventana de **activación** global invalidará la configuración de la **ventana de activación** del usuario agregado temporalmente. El usuario agregado temporalmente permanecerá en el **Panel usuarios** y estará en el ámbito de la Directiva durante el número de días definido en la configuración de la **ventana de activación** global.

## <a name="view-user-information-on-the-users-dashboard"></a>Ver información de usuario en el panel de usuarios

Cada usuario que se muestra en el **Panel de usuarios** tiene la siguiente información:

- **Users**: el nombre de usuario de un usuario. Este campo es anonimizan si está habilitada la configuración de anonymization global para la administración de riesgos de Insider.
- **Nivel de riesgo**: el nivel de riesgo calculado actual del usuario. Esta puntuación se calcula cada 24 horas y usa los resultados de riesgo de alertas de todas las alertas activas asociadas al usuario. Para los usuarios que solo tengan indicadores desencadenantes, el nivel de riesgo es cero.
- **Alertas activas**: el número de alertas activas para todas las directivas.
- **Infracciones confirmadas**: el número de casos resueltos como *infracción de la Directiva confirmada* para el usuario.
- **Caso**: el caso activo actual para el usuario.

![Panel de usuarios de administración de riesgos de Insider](../media/insider-risk-users-dashboard.png)

>[!NOTE]
>El número de usuarios que se muestran en el **Panel usuarios** puede estar limitado en algunos casos, según el volumen de alertas activas y las directivas coincidentes. Los usuarios con alertas activas se muestran en el **Panel de usuarios** a medida que se generan las alertas y es posible que haya casos raros en los que se alcance el número máximo de usuarios mostrados. Si esto ocurre, los usuarios con alertas activas que no se muestran se agregarán al **Panel usuarios** , ya que las alertas de usuario existentes se evaluarán.

## <a name="view-user-details"></a>Ver detalles del usuario

Para ver más detalles sobre la actividad de riesgos para un usuario, abra el panel de detalles del usuario haciendo doble clic en un usuario en el **Panel de usuarios**. En el panel de detalles, puede ver la siguiente información:

- Ficha **Perfil de usuario**
    - **Nombre y título**: el nombre y el título de la ubicación del usuario de Azure Active Directory. Estos campos de usuario estarán anonimizan o estarán vacíos si está habilitada la configuración de anonymization global para la administración de riesgos de Insider.
    - **Correo electrónico del usuario**: la dirección de correo electrónico del usuario.
    - **Alias**: el alias de red del usuario.
    - **Organización o departamento**: la organización o el Departamento del usuario.

- Ficha **actividad del usuario**
    - **Historial de la actividad reciente de los usuarios**: enumera los indicadores desencadenadores y los indicadores de riesgo Insider para las actividades de usuario hasta los últimos 180 días. También se puntuan todas las actividades pertinentes a los indicadores de riesgo de Insider, aunque es posible que las actividades hayan generado una alerta de riesgo de Insider. Los ejemplos de indicador de activación pueden ser una fecha de retirada o la fecha del último trabajo programado del usuario. Los indicadores de riesgo de Insider son actividades que se determinan que tienen un elemento de riesgo y que se definen en las directivas en las que se incluye el usuario. Las actividades de eventos y riesgos se muestran con el elemento más reciente enumerado primero.

## <a name="temporarily-add-a-user-to-a-policy"></a>Agregar temporalmente un usuario a una directiva

Para agregar temporalmente un usuario a una directiva de administración de riesgos de Insider, use la pestaña **usuarios** de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365. Los usuarios agregan manualmente los requisitos del indicador de omisión de desencadenadores para la Directiva a la que se agregan y se muestran en el **Panel de usuarios**. Para agregar de forma permanente un usuario a una directiva de administración de riesgos de Insider, use el Asistente para directivas.

Complete los siguientes pasos para agregar un usuario a una directiva de riesgos de Insider existente:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **usuarios** .
2. Seleccione **Agregar un usuario a una directiva** en la barra de herramientas.
3. En el cuadro de diálogo **Agregar un nuevo usuario** , empiece a escribir un nombre de usuario en el campo **usuario** . Seleccione el usuario que desea agregar a una directiva.
4. Seleccione la flecha desplegable del campo de **Directiva** para mostrar las directivas de administración de riesgos de Insider configuradas. Seleccione la Directiva a la que desea agregar el usuario.
5. Use el control deslizante de la **ventana de activación** para definir el tiempo que el usuario se incluye en una directiva y se muestra en el panel usuarios. El tiempo que especifique determina cuánto tiempo estará activa la Directiva para este usuario y se iniciará cuando se genere la primera alerta o se detecte un indicador de desencadenamiento (como una coincidencia de directiva DLP). El intervalo para la **ventana de activación** es de 5 a 30 días.
6. Seleccione **Agregar** y **confirme** para agregar el usuario a la Directiva.

>[!NOTE]
>Puede tardar varias horas en aparecer nuevos usuarios agregados manualmente en el **Panel de usuarios**. Las actividades de los 90 días anteriores para estos usuarios pueden tardar hasta 24 horas en mostrarse. Para ver las actividades de los usuarios agregados manualmente, seleccione el usuario en el **Panel de usuarios** y abra la ficha **actividad de usuario** en el panel de detalles.

## <a name="run-automated-tasks-with-power-automate-flows-for-a-user"></a>Ejecutar tareas automatizadas con los flujos de alimentación automatizada para un usuario

Mediante el uso de flujos de energía recomendados, los investigadores y analistas de riesgos pueden tomar medidas rápidamente para:

- Notificar a los usuarios cuando se les agregue a una directiva de riesgos de Insider

Para ejecutar, administrar o crear flujos de alimentación automatizada para un usuario de administración de riesgos de Insider:

1. Seleccione **automatizar** en la barra de herramientas acción del usuario.
2. Elija el flujo de automatización de energía que se va a ejecutar y, a continuación, seleccione **flujo de ejecución**.
3. Una vez completado el flujo, seleccione **listo**.

Para obtener más información sobre los flujos de alimentación automatizada para la administración de riesgos de Insider, vea [Introducción a la configuración de administración de riesgos de Insider](insider-risk-management-settings.md#power-automate-flows-preview).
