---
title: Alertas y directivas de alertas del Administrador de cumplimiento de Microsoft Purview
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo crear alertas para actividades en el Administrador de cumplimiento de Microsoft Purview que pueden afectar a la puntuación de cumplimiento.
ms.openlocfilehash: 499d1f005b67b2a9583d7138ce784b2e7ae1c8ad
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66642248"
---
# <a name="microsoft-purview-compliance-manager-alerts-and-alert-policies"></a>Alertas y directivas de alertas del Administrador de cumplimiento de Microsoft Purview

**En este artículo:** Obtenga información sobre cómo **establecer alertas** para determinadas actividades en el Administrador de cumplimiento, cómo administrar alertas y cómo **crear directivas de alertas** para definir condiciones de alerta.

## <a name="overview"></a>Información general
El Administrador de cumplimiento puede alertarle de los cambios en cuanto se produzcan para que pueda seguir el seguimiento de los objetivos de cumplimiento. Por ejemplo, puede configurar alertas para informarle cuando el valor de puntuación de una acción de mejora ha aumentado o disminuido debido a un cambio de configuración en el inquilino, o cuando se ha asignado una acción de mejora a un usuario para realizar el trabajo de implementación o pruebas. Vea los [tipos de eventos para los](#create-an-alert-policy) que puede crear alertas.

Para crear alertas, primero configure una directiva de alertas para describir las condiciones que desencadenan una alerta y la frecuencia de las notificaciones. Cuando detectemos una coincidencia con las condiciones de la directiva, recibirá una notificación por correo electrónico con detalles para que pueda determinar si quiere investigar o realizar más acciones.

Todas las alertas se muestran en la pestaña **Alertas** del Administrador de cumplimiento y todas las directivas de alertas se muestran en la **pestaña Directivas de alerta**.  Todas las organizaciones ya tienen configurada una [directiva de cambio de puntuación predeterminada](#default-score-change-policy) .

## <a name="understanding-the-alerts-and-alert-policies-pages"></a>Descripción de las páginas alertas y directivas de alertas

> [!IMPORTANT]
> Los usuarios deben tener el rol **Lector de seguridad** en Azure Active Directory (AD) para acceder a las páginas **De alertas** y **directivas de alertas** del Administrador de cumplimiento. Se necesitan roles adicionales de administrador de seguridad y cumplimiento para trabajar con alertas y directivas de alertas. Obtenga los detalles siguientes en [Permisos de directiva de alertas](#alert-policy-permissions).

### <a name="alert-policies-page"></a>Página Directivas de alerta

Seleccione la pestaña **Directivas de alerta** en Administrador de cumplimiento para ver y administrar las directivas de alerta. La página **Directivas de alerta** contiene una tabla que enumera todas las directivas creadas por su organización. En esta página, puede crear nuevas directivas, editar las directivas existentes y cambiar el estado de activación y eliminar directivas.

En la **columna Estado**, **Activo** significa que la directiva está en vigor y desencadena alertas cuando se cumplen las condiciones. **Inactivo** significa que la directiva existe, pero no genera alertas. La tabla de directivas también muestra la gravedad de la directiva y la fecha en que se modificó por última vez la directiva.

Para ver los detalles de una directiva individual, seleccione su fila en la tabla. Aparecerá un panel flotante que muestra todos los detalles. Seleccione el botón **Acción** en la parte inferior del panel y seleccione una de las opciones para editar la directiva, ver sus alertas o eliminarla. Los comandos para agregar, editar, eliminar, activar y deshabilitar también están disponibles cerca de la parte superior de la tabla, encima de los filtros.

Para empezar a crear una directiva de alertas, consulte [Creación de una directiva de alertas](#create-an-alert-policy).

### <a name="alerts-page"></a>Página Alertas

Seleccione la pestaña **Alertas** en el Administrador de cumplimiento para ver y administrar las alertas. La página **Alertas** contiene una tabla que enumera cada alerta generada por una directiva de alerta, junto con su gravedad y el evento desencadenante (por ejemplo, el cambio de puntuación de una acción) y la fecha de la alerta.

Para ver una alerta individual, seleccione su fila en la tabla. Aparecerá un panel flotante que muestra todos los detalles de la pestaña **Información general** del panel. La pestaña **Registro de eventos** muestra las acciones realizadas por los usuarios que desencadenaron la alerta.

El botón **Acción** de la parte inferior del panel proporciona opciones para asignar la alerta a un usuario para realizar un seguimiento, enviar un correo electrónico al usuario cuyas acciones generaron la alerta o ver los detalles de la directiva que genera la alerta. También puede realizar las mismas acciones seleccionando el botón de redondeo que aparece a la izquierda del nombre de la alerta al mantener el puntero sobre su fila y, a continuación, seleccionando uno de los botones situados cerca de la parte superior de la tabla, encima de los filtros.

Para empezar a trabajar con alertas, consulte [Visualización y administración de alertas](#viewing-and-managing-alerts).

## <a name="alert-policy-permissions"></a>Permisos de directiva de alertas

En la tabla siguiente se describe qué usuarios pueden crear y editar alertas y directivas de alertas en función de su tipo de rol. Además de tener un rol de Administrador de cumplimiento, los usuarios también necesitan un rol de Azure AD como se indica a continuación:

- Para ver alertas y directivas de alertas: el rol **Lector de seguridad** en Azure AD
- Para crear o actualizar directivas de alertas: el **administrador de cumplimiento**, el **administrador de datos de cumplimiento**, el **administrador de seguridad** o el rol **de operador de seguridad** en Azure AD
 
Obtenga más información sobre [los roles de Azure en la portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#azure-roles-in-the-compliance-portal).


| Role | Puede crear y editar directivas | Puede editar alertas | 
| :------------- | :-------------: | :------------: |
| **Administración del administrador de cumplimiento**| Sí  | Sí | 
| **Evaluador del Administrador de cumplimiento**| Sí | Sí | 
| **Colaborador del Administrador de cumplimiento**| Sí | Sí | 
| **Lector del Administrador de cumplimiento**| No | No | 
| **Administrador global**| Sí | Sí | 

Obtenga información sobre cómo [establecer permisos de usuario y asignar roles para el Administrador de cumplimiento](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

## <a name="create-an-alert-policy"></a>Creación de una directiva de alertas

Puede crear directivas para alertarle cuando se produzcan determinados cambios o eventos relacionados con las acciones de mejora. Los tipos de eventos se enumeran a continuación.

### <a name="alert-event-types"></a>Tipos de eventos de alerta

- **Cambio de puntuación**: aumento o disminución de los puntos concedidos por una acción de mejora debido a los cambios de configuración realizados por alguien de su organización. Por ejemplo, si su organización crea una directiva de administración de riesgos internos, podría aumentar los puntos de una acción determinada en una cantidad determinada.
- **Cambio de asignación**: se ha asignado una acción de mejora a un usuario, se ha vuelto a asignar a otro usuario o se ha desasignado de un usuario.
- **Cambio de estado de implementación**: un usuario ha cambiado el estado de implementación de una acción de mejora.
- **Cambio de estado de prueba**: un usuario ha cambiado el estado de prueba de una acción de mejora.
- **Cambio de evidencia**: un usuario ha cargado o eliminado un documento de evidencia en la pestaña **Documentos** de la acción de mejora.

#### <a name="default-score-change-policy"></a>Directiva de cambio de puntuación predeterminada

El Administrador de cumplimiento configura una directiva de alertas predeterminada para supervisar los cambios de puntuación en las acciones de mejora. La directiva predeterminada generará una alerta cuando cambie la puntuación de una acción de mejora. La mayoría de la configuración de la directiva predeterminada no se puede editar, pero puede agregar destinatarios adicionales para las notificaciones.

Esta es la configuración de la directiva predeterminada:

- Todas las coincidencias que se detecten en un intervalo de 60 minutos se agruparán en una sola alerta para reducir las notificaciones excesivas. Por ejemplo, si cinco acciones de mejora experimentan un cambio de puntuación en una hora, se generará una alerta.

- El nivel de gravedad de estas alertas es **medio**.

- El Administración global de su organización es el destinatario predeterminado de las notificaciones de alerta.

- Puede agregar más destinatarios de alertas siguiendo estos pasos:
    - En la página **Directivas de alerta** , busque la **directiva de alertas predeterminada del Administrador de cumplimiento**.
    - Active la casilla situada a la izquierda de su nombre y seleccione el botón **Editar** situado cerca de la parte superior, encima de los filtros.
    - Seleccione el botón **Siguiente** hasta que llegue a la página **Destinatarios** de alertas.
    - Seleccione **+Seleccionar destinatarios** y active las casillas situadas junto a cada nombre de usuario del panel flotante al que desea recibir la notificación por correo electrónico. Cuando haya terminado, seleccione **Agregar destinatario** y, a continuación, **seleccione Siguiente**.
    - En la página **Revisar y finalizar** , seleccione **Actualizar** para guardar los cambios.

- La directiva predeterminada no se puede eliminar, pero puede deshabilitarla [siguiendo los pasos descritos a continuación](#activate-or-inactivate-a-policy).


### <a name="policy-creation-steps"></a>Pasos de creación de directivas

Para crear una directiva para generar alertas basadas en uno o varios eventos, siga estos pasos:

1. En **el Administrador de cumplimiento**, vaya a la página **Directivas de alerta** y seleccione **+Agregar** para iniciar el asistente para la creación de directivas.

2. En la página **Nombre y descripción** , escriba un nombre para la directiva y una descripción opcional y, a continuación, seleccione **Siguiente**.

3. En la página **Condiciones** , seleccione uno o varios eventos que desencadenarán una alerta. En el encabezado **de la actividad de acción Mejora** , seleccione **Agregar subconsultas** y active la casilla que aparece al mantener el puntero a la izquierda de cada nombre de condición. Puede elegir una o varias condiciones para una directiva: cambio de asignación, cambio de evidencia, cambio de estado de implementación, cambio de puntuación, cambio de estado de prueba. Cuando termine, haga clic en **Siguiente**.

4. En la página **Resultados** , elija lo que ocurre cuando se detecta una coincidencia de directiva:
      - Seleccione un nivel de gravedad para la alerta cuando se detecte una coincidencia: baja, media o alta.
      - Seleccione la frecuencia con la que desea recibir una notificación por correo electrónico cuando se detecte una coincidencia. Puede elegir recibir una notificación con cada coincidencia o elegir un umbral de un número determinado de coincidencias por encima de tres.
      - Si decide recibir una notificación después de tres o más coincidencias, designará el número de minutos en los que se debe alcanzar ese umbral (por ejemplo, 4 coincidencias en un plazo de 90 minutos).
  
    Cuando haya acabado, seleccione **Siguiente**.

5. En la página **Destinatario de la alerta** , seleccione usuarios adicionales de su organización para recibir un correo electrónico cuando se cumplan las condiciones de la directiva. El usuario que crea la directiva es el destinatario predeterminado. Seleccione **+Seleccionar destinatarios** y active las casillas situadas junto a cada nombre de usuario del panel flotante al que desea recibir la notificación por correo electrónico. Cuando haya terminado, seleccione **Agregar destinatarios** y, a continuación, **seleccione Siguiente**.

6. Revise todas las selecciones y realice cualquier cambio en cada sección seleccionando y, a continuación, seleccione **Siguiente**. Cuando haya terminado de revisar, seleccione **Crear directiva**.

7. Cuando se cree la directiva, seleccione **Listo**. Llegará a la página **Directivas de alerta** con el panel flotante de la directiva que acaba de crear ya abierta.

La directiva está activa una vez creada, lo que significa que comenzará a detectar coincidencias y a generar alertas. Consulte la sección **Administración de directivas** a continuación para obtener información sobre cómo desactivar o eliminar directivas.

Puede tardar hasta 24 horas después de crear o actualizar una directiva antes de que esa directiva genere alertas. Consulte [Ver los detalles de alerta](#view-alert-details) a continuación para obtener información sobre cómo desencadenar eventos y agregación de alertas.

## <a name="managing-policies"></a>Administración de directivas

La página **Directivas de alerta** contiene una lista de tabla de todas las directivas. Consulte [la página Directivas de alerta](#alert-policies-page) para comprender mejor esta página. Cualquier usuario de su organización puede ver directivas, pero ciertas acciones están restringidas a determinados roles; consulte [Permisos de directiva de alertas](#alert-policy-permissions).

### <a name="view-policy-details"></a>Visualización de los detalles de la directiva

Seleccione una directiva de su fila en la página **Directivas de alerta** para mostrar un panel flotante que muestre los detalles de la directiva, incluidas sus condiciones de coincidencia, si se envían y cuándo se envían las notificaciones de alerta y a quién, y el nivel de gravedad.

El botón **Acciones** de la parte inferior del panel ofrece opciones para editar la directiva, eliminar la directiva o ver alertas.

### <a name="view-a-policys-alerts"></a>Visualización de las alertas de una directiva

En el panel flotante de la directiva, seleccione **Acciones** y, a continuación, **Ver alertas**. Se le llevará directamente a la página Alertas con una vista filtrada de todas las alertas generadas por esa directiva. Obtenga información sobre cómo [trabajar con alertas](#viewing-and-managing-alerts).

### <a name="edit-a-policy"></a>Editar una directiva

Puede editar cualquier aspecto de una directiva excepto por su nombre. Si desea cambiar su nombre, deberá crear una nueva directiva con un nuevo nombre.

Para editar una directiva, seleccione el botón de redondeo que aparece a la izquierda de su nombre al mantener el puntero sobre su fila en la página **Directivas de alerta** y seleccione el botón **Editar** situado cerca de la parte superior, encima de los filtros.

Se le llevará al Asistente para la creación de directivas, donde podrá realizar y guardar los cambios en la directiva.  También puede seleccionar la directiva para abrir su panel de detalles y, en el botón **Acciones** , seleccione **Editar directiva**. Después de volver a trabajar en el asistente, revise las selecciones y, en el paso final, seleccione **Actualizar** para guardar los cambios.

La directiva actualizada puede tardar hasta 24 horas en generar alertas.

### <a name="activate-or-inactivate-a-policy"></a>Activación o desactivación de una directiva

Las directivas se activan de forma predeterminada en cuanto se crean. Cuando esté activa, una directiva creará una alerta (que se muestra en la página **Alertas** ) cuando se cumplan las condiciones y enviará un correo electrónico de notificación a los destinatarios designados.

Para cambiar una directiva a un estado **inactivo** , lo que significa que no generará alertas, seleccione el botón de redondeo que aparece a la izquierda del nombre de la directiva al mantener el puntero sobre su fila. A continuación, seleccione el comando **Deshabilitar** encima de la tabla. El estado de la directiva ahora leerá Inactivo. Para reactivar la directiva, siga el mismo proceso y seleccione el botón **Activar** situado encima de los filtros.

### <a name="delete-a-policy"></a>Eliminar una directiva

Para eliminar una directiva, puede seleccionar el botón situado junto a su nombre en la página **Directivas de alerta** y seleccionar **Eliminar** cerca de la parte superior de la página. También puede seleccionar la directiva para abrir el panel de detalles y, en el botón **Acciones** , seleccione **Eliminar directiva**.

La eliminación es permanente. Una vez que elimine una directiva, ya no generará alertas ni notificaciones por correo electrónico. Obtenga más información sobre [las alertas conectadas a directivas eliminadas](#when-policies-are-deleted).

## <a name="viewing-and-managing-alerts"></a>Visualización y administración de alertas

La página **Alertas** muestra una tabla con todas las alertas generadas por todas las directivas. Las alertas se generan casi inmediatamente después de que se produzca un evento que coincida con las condiciones de la directiva. El nombre de la alerta es el mismo nombre que la directiva que generó la alerta.

Una alerta solo se puede generar a partir de una directiva activa. Una vez generada una alerta, permanece en la página **Alertas** , independientemente de si la directiva está activa o inactiva.

### <a name="filter-your-view-of-alerts"></a>Filtrar la vista de alertas
Para filtrar la vista de alertas, seleccione el comando **Filtrar** encima de la tabla en la página **Alertas** . En el panel flotante **Filtro** , seleccione entre estas opciones de filtro:

- Tipo de evento
- Severity
- Estado
- Usuario asignado a
- Fecha de detección
- Nombre de la directiva

Después de realizar las selecciones, seleccione **Aplicar**. El panel flotante se cerrará y la página **Alertas** actualizada muestra la vista filtrada. Los filtros se muestran en la parte superior de la tabla, aunque no todas las columnas de filtro pueden mostrarse en la tabla.

### <a name="view-alert-details"></a>Visualización de los detalles de la alerta

Para ver todos los detalles sobre la alerta, incluidos los eventos que la desencadenaron, seleccione su fila en la tabla. Un panel flotante mostrará los detalles de la alerta en la pestaña **Información general** del panel.

La pestaña **Registro de eventos** del panel flotante muestra las actividades que generaron la alerta, como un cambio de puntuación o un cambio de asignación, junto con el nombre del usuario asociado a cada acción y la fecha detectada.

### <a name="alert-events"></a>Eventos de alerta

La columna **Eventos** de la página **Alertas** indica las condiciones de una directiva detectada; es decir, la actividad que generó la alerta. La pestaña **Registro de eventos** del panel de detalles de la alerta muestra cada instancia de un evento, el usuario asociado y la fecha detectada. Los valores de evento se enumeran a continuación:

- **Cambio de puntuación**: muestra el número de aumentos o disminuciones en puntos
- **Cambio de asignación**: se ha asignado una acción de mejora a un usuario, se ha vuelto a asignar a otro usuario o se ha desasignado de un usuario.
- **Cambio de estado de implementación**: un usuario ha cambiado el estado de implementación de una acción de mejora
- **Cambio de estado de prueba**: un usuario ha cambiado el estado de prueba de una acción de mejora.
- **Cambio de evidencia**: un usuario ha cargado o eliminado un documento de evidencia en la pestaña Documentos de la acción de mejora.
- **Varios eventos**: se han detectado varias instancias del mismo tipo de evento; por ejemplo, una única acción de mejora que se ha reasignado varias veces
- **Condición múltiple**: se detectaron varias condiciones dentro de una sola directiva

#### <a name="alert-aggregation-for-multiple-events-within-one-minute"></a>Agregación de alertas para varios eventos en un minuto

Cuando se producen varios eventos que coinciden con las condiciones de una directiva de alertas con un minuto, se agregan a una alerta existente mediante un proceso denominado agregación de alertas.

Por ejemplo, cuando se produce un evento que coincide con una directiva, se genera una alerta y se muestra en la página **Alertas** y se envía una notificación. Si se produce otro evento que coincida con la misma directiva en un minuto del primer evento, el Administrador de cumplimiento agrega detalles sobre el evento adicional en la pestaña **Registro de eventos** de la alerta existente en lugar de desencadenar una nueva alerta. El objetivo de la agregación de alertas es ayudar a reducir la "fatiga" de las alertas y permitirle centrarse y tomar medidas en menos alertas.

### <a name="taking-action-on-alerts"></a>Realizar acciones en alertas

Cuando una de las directivas genera una alerta, puede ver los eventos que provocaron la alerta y determinar si necesita comprobar o investigar más los eventos.

Para realizar una acción en una alerta, seleccione su fila en la página **Alertas** para abrir el panel flotante con sus detalles, seleccione el botón **Acciones** y elija entre las opciones que se enumeran a continuación. También puede realizar acciones seleccionando el botón de redondeo que aparece a la izquierda del nombre de la alerta al mantener el puntero sobre su fila y seleccionando uno de los botones de acción cerca de la parte superior de la página, encima de los filtros.

**Asignar alerta**: es posible que quiera asignar la alerta a un usuario para investigar o comprobar los eventos que provocaron la alerta. Al elegir esta opción, se abre un panel en el que puede seleccionar un usuario de su organización y asignarle la alerta. Para filtrar la vista de alertas, seleccione **Filtros** en la página **Alertas** y escriba el nombre del usuario en el campo **Asignado a** .

**Alerta de correo electrónico**: es posible que quiera enviar un correo electrónico al usuario asociado a la actividad de la alerta para confirmar que ha realizado la acción. Al elegir esta opción, se abre una plantilla de correo electrónico con información básica sobre la alerta, que puede personalizar con instrucciones adicionales y enviar al usuario.

**Ver detalles de la directiva**: es posible que quiera revisar la configuración de la directiva que desencadenó la alerta. Tenga en cuenta que, al seleccionar esta opción, se le llevará directamente a la página **Directivas de alerta** con el panel de detalles de la directiva ya abierto. Ya no estará en la página **Alertas** cuando cierre el panel de detalles de la directiva.

**Cambiar estado**: puede actualizar el estado de la alerta en función de la revisión de su impacto y de si necesita investigar. Obtenga más información sobre los estados de alerta en la sección siguiente.

### <a name="alert-status"></a>Estado de alerta

Cuando se crea una alerta, su estado es **Activo**. Al revisar los detalles de cada alerta, puede actualizar su estado a cualquiera de los estados que se enumeran a continuación:

- **Activo**: estado predeterminado de la alerta hasta que se cambia su estado
- **Investigación**: la alerta está en investigación
- **Resuelto**: la alerta no requiere más investigación ni seguimiento
- **Descartado**: la alerta no es relevante o no necesita investigación

Para asignar o cambiar el estado de una alerta, seleccione una alerta de su fila en la tabla y seleccione **Cambiar estado** cerca de la parte superior de la página, encima de los filtros. En el panel flotante Actualizar estado de alerta, seleccione un estado en el menú desplegable y, a continuación, seleccione **Actualizar alerta**.

Una vez generada una alerta, su estado es independiente del estado de la directiva que generó la alerta. Por ejemplo, es posible tener una alerta **activa** asociada a una directiva **inactiva** y es posible tener un estado de **investigación** en una alerta generada por una directiva que se inactivó o eliminó posteriormente.

### <a name="when-policies-are-deleted"></a>Cuando se eliminan las directivas

Cuando se elimina una directiva, las alertas generadas por esa directiva permanecerán en la página **Alertas** , pero no se generarán nuevas alertas.

## <a name="email-notifications-of-alerts"></a>Notificaciones por correo electrónico de alertas

Al crear una directiva, se envía un correo electrónico al usuario que creó la directiva para avisarle de que se detectó una coincidencia. Puede optar por enviar estas notificaciones por correo electrónico a usuarios adicionales de su organización. Las alertas se producen casi en tiempo real y las notificaciones por correo electrónico se envían en cuanto se genera una alerta. El correo electrónico contendrá el nombre del evento, la gravedad, el tiempo detectado y un vínculo para ver la alerta en el Administrador de cumplimiento.

### <a name="remove-users-from-receiving-alerts"></a>Eliminación de usuarios de la recepción de alertas

Si designa destinatarios de alertas y, después, decide quitarlos, siga los pasos que se indican a continuación. Tenga en cuenta que el creador de directivas seguirá recibiendo notificaciones por correo electrónico cuando se detecten coincidencias de directivas.

1. Comience los pasos para [editar la directiva](#edit-a-policy).
2. Cuando llegue a la pantalla **Destinatarios** de alertas, seleccione **+Seleccionar destinatarios**.
3. En el panel flotante **Seleccionar destinatarios** , busque el usuario que desea quitar de las notificaciones y desactive la casilla situada a la izquierda de su nombre y, a continuación, seleccione el botón **Agregar destinatarios** (que tiene el efecto de guardar la selección).
4. Continúe con el asistente y confirme que el usuario no aparece en **Destinatarios** en la página Revisar y finalizar. Seleccione **Actualizar** para guardar la configuración y finalizar.
