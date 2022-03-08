---
title: Directivas de alertas y alertas del Administrador de cumplimiento de Microsoft
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
description: Obtenga información sobre cómo crear alertas para actividades en Microsoft Compliance Manager que pueden afectar a su puntuación de cumplimiento.
ms.openlocfilehash: bb81588be31b2c13113953c585112ee2f5a56875
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319261"
---
# <a name="microsoft-compliance-manager-alerts-and-alert-policies"></a>Directivas de alertas y alertas del Administrador de cumplimiento de Microsoft

**En este artículo:** Obtenga información sobre cómo **establecer alertas** para determinadas actividades en el Administrador de cumplimiento, cómo administrar alertas y cómo crear directivas de **alerta para definir** condiciones de alerta.

## <a name="overview"></a>Información general
El pesebre de cumplimiento puede alertar sobre los cambios tan pronto como se realicen para que pueda mantenerse al tanto de sus objetivos de cumplimiento. Por ejemplo, puede configurar alertas para informarle cuando el valor de puntuación de una acción de mejora ha aumentado o disminuido debido a un cambio de configuración en el inquilino, o cuando se ha asignado una acción de mejora a un usuario para realizar el trabajo de implementación o pruebas. Vea los [tipos de eventos para](#create-an-alert-policy) los que puede crear alertas.

Para crear alertas, primero configure una directiva de alertas para esquematear las condiciones que desencadenan una alerta y la frecuencia de las notificaciones. Cuando detectemos una coincidencia con las condiciones de la directiva, recibirás una notificación por correo electrónico con detalles para que puedas determinar si quieres investigar o tomar medidas adicionales.


Todas las alertas se enumeran **en la pestaña** Alertas del Pesebre de cumplimiento y todas las directivas de alerta se enumeran en la pestaña **Directivas de alerta.**

## <a name="understanding-the-alerts-and-alert-policies-pages"></a>Descripción de las páginas de directivas de alertas y alertas

> [!IMPORTANT]
> Los usuarios deben **tener el rol** lector de seguridad en Azure Active Directory (AD) para tener acceso a las páginas **Directivas** de  alertas y alertas en el Administrador de cumplimiento. Se necesitan roles de seguridad y administrador de cumplimiento adicionales para trabajar con alertas y directivas de alertas. Obtenga más información a continuación en [Permisos de directiva de alerta.](#alert-policy-permissions)

### <a name="alert-policies-page"></a>Página Directivas de alerta

Seleccione la **pestaña Directivas de alerta** en el Pesebre de cumplimiento para ver y administrar las directivas de alerta. La **página Directivas de** alerta contiene una tabla que enumera todas las directivas creadas por su organización. Desde esta página, puede crear nuevas directivas, editar directivas existentes y cambiar el estado de activación y eliminar directivas.

En la **columna Estado**, **Active** significa que la directiva está en vigor y que desencadena alertas cuando se cumplen las condiciones. **Inactivo significa** que la directiva existe pero no genera alertas. La tabla directivas también muestra la gravedad de la directiva y la fecha en que se modificó por última vez.

Para ver los detalles de una directiva individual, seleccione su fila en la tabla. Aparecerá un panel desplegable que muestra todos los detalles. Seleccione el **botón** Acción en la parte inferior del panel y seleccione entre las opciones para editar la directiva, ver sus alertas o eliminarla. Los comandos para agregar, editar, eliminar, activar y deshabilitar también están disponibles cerca de la parte superior de la tabla, encima de los filtros.

Para empezar a crear una directiva de alerta, consulte [Create an alert policy](#create-an-alert-policy).

### <a name="alerts-page"></a>Página alertas

Seleccione la **pestaña Alertas** en el Administrador de cumplimiento para ver y administrar las alertas. La **página** Alertas contiene una tabla que enumera cada alerta generada por una directiva de alerta, junto con su gravedad y el evento desencadenante (por ejemplo, el cambio de puntuación de una acción) y la fecha de la alerta.

Para ver una alerta individual, seleccione su fila en la tabla. Aparecerá un panel desplegable que muestra todos los detalles en la **pestaña** Información general del panel. La **pestaña Registro de** eventos muestra las acciones realizadas por los usuarios que desencadenaron la alerta.

El **botón** Acción en la parte inferior del panel proporciona opciones para asignar la alerta a un usuario para seguimiento, enviar un correo electrónico al usuario cuyas acciones generaron la alerta o ver los detalles de la directiva que genera la alerta. También puede realizar las mismas acciones seleccionando el botón redondo que aparece a la izquierda del nombre de la alerta al pasar el mouse sobre su fila y, a continuación, seleccionando uno de los botones cerca de la parte superior de la tabla, encima de los filtros.

Para empezar a trabajar con alertas, consulte [Visualización y administración de alertas](#viewing-and-managing-alerts).

## <a name="alert-policy-permissions"></a>Permisos de directiva de alerta

En la tabla siguiente se describen los usuarios que pueden crear y editar alertas y directivas de alerta en función de su tipo de función. Además de mantener un rol de Administrador de cumplimiento, los usuarios también necesitan un Azure AD de la siguiente manera:

- Rol **lector de seguridad** en Azure AD para ver alertas y directivas de alertas
- Rol **de administrador de** seguridad en Azure AD para crear o actualizar directivas de alertas
 
Obtenga más información [sobre los roles de Azure en el Centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center-permissions.md#azure-roles-in-the-microsoft-365-compliance-center).


| Rol | Puede crear y editar directivas | Puede editar alertas | 
| :------------- | :-------------: | :------------: |
| **Administración del administrador de cumplimiento**| Sí  | Sí | 
| **Evaluador del Administrador de cumplimiento**| Sí | Sí | 
| **Contribución del administrador de cumplimiento**| Sí | Sí | 
| **Administrador global**| No | No  | 
| **Lector del Administrador de cumplimiento**| No | No | 

Obtenga información sobre cómo [establecer permisos de usuario y asignar roles para el Administrador de cumplimiento](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

## <a name="create-an-alert-policy"></a>Crear una directiva de alerta

Puede crear directivas para alertar cuando se realicen determinados cambios o eventos relacionados con acciones de mejora. A continuación se enumeran los tipos de eventos.

### <a name="alert-event-types"></a>Tipos de eventos de alerta

- **Cambio de puntuación**: aumento o disminución de puntos otorgados por una acción de mejora debido a los cambios de configuración realizados por alguien de su organización. Por ejemplo, si su organización crea una directiva de administración de riesgos de insider, esto podría aumentar los puntos para una determinada acción en una cantidad determinada.
- **Cambio de asignación**: se ha asignado una acción de mejora a un usuario, se ha asignado de nuevo a otro usuario o se ha desasignado de un usuario.
- **Cambio de estado de** implementación: un usuario ha cambiado el estado de implementación de una acción de mejora.
- **Cambio de estado de prueba**: un usuario ha cambiado el estado de prueba de una acción de mejora.
- **Cambio de evidencia**: un usuario ha cargado o eliminado un documento de evidencia en la **pestaña** Documentos de la acción de mejora.

### <a name="policy-creation-steps"></a>Pasos de creación de directivas

Para crear una directiva para generar alertas basadas en uno o varios eventos, siga estos pasos:

1. En **el Administrador de cumplimiento**, vaya a la página **Directivas de alerta** y seleccione **+Agregar** para iniciar el asistente para la creación de directivas.

2. En la **página Nombre y descripción** , escriba un nombre para la directiva y una descripción opcional y, a continuación, **seleccione Siguiente**.

3. En la **página Condiciones** , seleccione uno o varios eventos que desencadenarán una alerta. En el **encabezado Actividad de acción de** mejora, seleccione **Agregar subcondiciones** y active la casilla que aparece al desplazarse a la izquierda de cada nombre de condición. Puede elegir una o más condiciones para una directiva: cambio de asignación, cambio de evidencia, cambio de estado de implementación, cambio de puntuación, cambio de estado de prueba. Cuando haya terminado, seleccione **Siguiente**.

4. En la **página Resultados** , elija lo que sucede cuando se detecta una coincidencia de directiva:
      - Seleccione un nivel de gravedad para la alerta cuando se detecte una coincidencia: baja, mediana o alta.
      - Seleccione la frecuencia con la que desea recibir una notificación por correo electrónico cuando se detecte una coincidencia. Puedes elegir recibir una notificación con cada coincidencia o elegir un umbral de un número determinado de coincidencias por encima de tres.
      - Si decide recibir una notificación después de tres o más coincidencias, designará el número de minutos en los que se debe alcanzar ese umbral (por ejemplo, 4 coincidencias en 90 minutos).
  
    Cuando haya acabado, seleccione **Siguiente**.

5. En la **página Destinatario de alerta** , seleccione usuarios adicionales de la organización para recibir un correo electrónico cuando se cumplen las condiciones de directiva. El usuario que crea la directiva es el destinatario predeterminado. Seleccione **+Seleccionar destinatarios y active las casillas situadas** junto a cada nombre de usuario en el panel desplegable al que desea recibir la notificación por correo electrónico. Cuando haya terminado, **seleccione Agregar destinatarios** y, a continuación, **seleccione Siguiente**.

6. Revise todas las selecciones y realice cualquier cambio en cada sección seleccionando y, a continuación, **seleccione Siguiente**. Cuando termine de revisar, seleccione **Crear directiva**.

7. Cuando se cree la directiva, seleccione **Listo**. Llegará a la **página Directivas de** alerta con el panel desplegable de la directiva que acaba de crear ya abierta.

La directiva está activa una vez que la cree, lo que significa que empezará a detectar coincidencias y a generar alertas. Consulte la **sección Administración de directivas** a continuación para obtener información sobre cómo desactivar o eliminar directivas.

Puede tardar hasta 24 horas después de crear o actualizar una directiva antes de que esa directiva genere alertas. Consulta [Ver detalles de alertas](#view-alert-details) a continuación para obtener información sobre la activación de eventos y la agregación de alertas.

## <a name="managing-policies"></a>Administración de directivas

La **página Directivas de** alerta contiene una lista de tablas de todas las directivas. Consulta [Página Directivas de alerta para](#alert-policies-page) comprender mejor esta página. Cualquier usuario de la organización puede ver directivas, pero determinadas acciones están restringidas a determinados roles; vea [Permisos de directiva de alerta.](#alert-policy-permissions)

### <a name="view-policy-details"></a>Ver detalles de la directiva

Seleccione una directiva de su fila en la  página Directivas de alerta para mostrar un panel desplegable que muestre los detalles de la directiva, incluidas sus condiciones de coincidencia, si se envían y cuándo se envían las notificaciones de alerta y a quién, y el nivel de gravedad.

El **botón** Acciones de la parte inferior del panel le ofrece opciones para editar la directiva, eliminar la directiva o ver alertas.

### <a name="view-a-policys-alerts"></a>Ver alertas de una directiva

En el panel desplegable de la directiva, seleccione **Acciones** y, a continuación **, Ver alertas**. Te llevaremos directamente a la página Alertas con una vista filtrada de todas las alertas generadas por esa directiva. Obtenga información sobre [cómo trabajar con alertas](#viewing-and-managing-alerts).

### <a name="edit-a-policy"></a>Editar una directiva

Puede editar cualquier aspecto de una directiva excepto su nombre. Si desea cambiar su nombre, deberá crear una nueva directiva con un nombre nuevo.

Para editar una directiva, seleccione el botón de redondeo que aparece a la izquierda de su nombre cuando mantenga el mouse sobre su fila  en la página Directivas de alerta  y seleccione el botón Editar cerca de la parte superior, encima de los filtros.

Te llevaremos al Asistente para la creación de directivas donde puedes realizar y guardar cambios en la directiva.  También puede seleccionar la directiva para mostrar su panel de detalles y, **en el botón** Acciones, seleccione **Editar directiva**. Después de volver a trabajar con el asistente, revise las selecciones y, en el paso final, **seleccione Actualizar** para guardar los cambios.

La directiva actualizada puede tardar hasta 24 horas en generar alertas.

### <a name="activate-or-inactivate-a-policy"></a>Activar o desactivar una directiva

Las directivas se activan de forma predeterminada tan pronto como se crean. Cuando está activa, una directiva creará una alerta (que se muestra  en la página Alertas) cuando se cumplen las condiciones y enviará un correo electrónico de notificación a los destinatarios designados.

Para cambiar una directiva a un  estado inactivo, lo que significa que no generará alertas, seleccione el botón de redondeo que aparece a la izquierda del nombre de la directiva al pasar el puntero sobre su fila. A continuación, **seleccione el comando** Deshabilitar encima de la tabla. El estado de la directiva ahora leerá Inactivo. Para reactivar la directiva, siga el mismo proceso y seleccione el **botón Activar** encima de los filtros.

### <a name="delete-a-policy"></a>Eliminar una directiva

Para eliminar una directiva, puede seleccionar el botón situado junto a su nombre en la  página Directivas de alerta y seleccionar **Eliminar** cerca de la parte superior de la página. También puede seleccionar la directiva para mostrar su panel de detalles y, **en el botón** Acciones, seleccione **Eliminar directiva**.

La eliminación es permanente. Una vez que elimine una directiva, ya no generará alertas ni notificaciones por correo electrónico. Obtenga más información sobre [las alertas conectadas a directivas eliminadas](#when-policies-are-deleted).

## <a name="viewing-and-managing-alerts"></a>Visualización y administración de alertas

La **página Alertas** muestra una tabla con todas las alertas generadas por todas las directivas. Las alertas se generan casi inmediatamente después de que se produzca un evento que coincida con las condiciones de la directiva. El nombre de la alerta es el mismo nombre que la directiva que generó la alerta.

Solo se puede generar una alerta desde una directiva activa. Una vez que se genera una alerta, permanece en la  página Alertas independientemente de si la directiva está activa o inactiva.

### <a name="filter-your-view-of-alerts"></a>Filtrar la vista de alertas
Puede filtrar la vista de alertas seleccionando el comando **Filtrar** encima de la tabla de la página **Alertas** . En el **panel** desplegable Filtro, seleccione entre estas opciones de filtro:

- Tipo de evento
- Severity
- Estado
- Usuario asignado a
- Fecha de detección
- Nombre de la directiva

Después de realizar las selecciones, selecciona **Aplicar**. El panel desplegable se cerrará y la página **Alertas** actualizada muestra la vista filtrada. Los filtros se muestran en la parte superior de la tabla, aunque no todas las columnas de filtro pueden mostrarse en la tabla.

### <a name="view-alert-details"></a>Ver detalles de alerta

Para ver todos los detalles sobre la alerta, incluidos los eventos que la desencadenaron, seleccione su fila en la tabla. Un panel desplegable mostrará los detalles de la alerta en la **pestaña** Información general del panel.

La **pestaña Registro** de eventos del panel desplegable enumera las actividades que generaron la alerta, como un cambio de puntuación o un cambio de asignación, junto con el nombre del usuario asociado a cada acción y la fecha detectada.

### <a name="alert-events"></a>Eventos de alerta

La **columna Eventos** de la **página Alertas** indica las condiciones de una directiva que se detectaron; es decir, la actividad que generó la alerta. La **pestaña Registro de** eventos del panel de detalles de la alerta enumera cada instancia de un evento, el usuario asociado y la fecha detectada. Los valores de evento se enumeran a continuación:

- **Cambio de puntuación**: muestra el número de aumento o disminución de puntos
- **Cambio de asignación**: se ha asignado una acción de mejora a un usuario, se ha asignado de nuevo a un usuario diferente o se ha cambiado la asignación de un usuario.
- **Cambio de estado de** implementación: un usuario ha cambiado el estado de implementación de una acción de mejora
- **Cambio de estado de prueba**: un usuario ha cambiado el estado de prueba de una acción de mejora.
- **Cambio de evidencia**: un usuario ha cargado o eliminado un documento de evidencia en la pestaña Documentos de la acción de mejora
- **Multi-event**: se han detectado varias instancias del mismo tipo de evento; por ejemplo, una sola acción de mejora que se ha reasignado varias veces
- **Multi-condition**: se detectaron varias condiciones dentro de una sola directiva

#### <a name="alert-aggregation-for-multiple-events-within-one-minute"></a>Agregación de alertas para varios eventos en un minuto

Cuando se producen varios eventos que coinciden con las condiciones de una directiva de alerta con un minuto, se agregan a una alerta existente mediante un proceso denominado agregación de alertas.

Por ejemplo, cuando se produce un evento que coincide con una directiva, se genera una alerta y se muestra en  la página Alertas y se envía una notificación. Si se produce otro evento que coincide con la misma directiva en un minuto desde el primer evento, el Administrador de cumplimiento agrega detalles sobre el evento adicional  en la pestaña Registro de eventos de la alerta existente en lugar de desencadenar una nueva alerta. El objetivo de la agregación de alertas es ayudar a reducir la "fatiga" de alertas y permitir que te enfoques y tomes medidas en menos alertas.

### <a name="taking-action-on-alerts"></a>Realizar acciones en alertas

Cuando una de sus directivas genera una alerta, puede ver los eventos que provocaron la alerta y determinar si necesita comprobar o investigar más los eventos.

Para realizar una acción en una alerta, seleccione su fila en la  página Alertas para que aparezca el panel desplegable con sus detalles, seleccione el  botón Acciones y elija entre las opciones que se enumeran a continuación. También puede realizar acciones seleccionando el botón de redondeo que aparece a la izquierda del nombre de la alerta al pasar el mouse sobre su fila y seleccionando uno de los botones de acción cerca de la parte superior de la página, encima de los filtros.

**Asignar alerta**: es posible que desee asignar la alerta a un usuario para investigar o comprobar los eventos que provocaron la alerta. Al elegir esta opción, se abre un panel donde puede seleccionar un usuario de su organización y asignarles la alerta. Puede filtrar la vista de alertas seleccionando  Filtros en la  página Alertas y especificando el nombre del usuario en el **campo Asignado a**.

**Alerta de** correo electrónico: es posible que desee enviar un correo electrónico al usuario asociado a la actividad de la alerta para confirmar que realizó la acción. Cuando eliges esta opción, se abre una plantilla de correo electrónico con información básica sobre la alerta, que puedes personalizar con más instrucciones y enviar al usuario.

**Ver detalles de** la directiva: es posible que desee revisar la configuración de la directiva que desencadenó la alerta. Tenga en cuenta que al seleccionar esta opción, se le mostrará directamente a la página  Directivas de alerta con el panel de detalles de la directiva ya abierto. Ya no estará en la **página Alertas** cuando cierre el panel de detalles de la directiva.

**Estado de** cambio: puede actualizar el estado de la alerta en función de su revisión de su impacto y de si necesita investigar. Obtenga más información sobre los estados de alerta en la sección siguiente.

### <a name="alert-status"></a>Estado de alerta

Cuando se crea una alerta, su estado es **Activo**. Al revisar los detalles de cada alerta, puede actualizar su estado a cualquiera de los estados que se enumeran a continuación:

- **Activo**: estado predeterminado de la alerta hasta que se cambia su estado
- **Investigación**: se está investigando la alerta
- **Resuelto**: la alerta no requiere más investigación ni seguimiento
- **Descartado**: la alerta no es relevante o no necesita investigación

Para asignar o cambiar el estado de una alerta, seleccione una alerta de su fila en la tabla, seleccione  Cambiar estado cerca de la parte superior de la página, encima de los filtros. En el panel desplegable Actualizar estado de alerta, seleccione un estado en el menú desplegable y, a continuación, **seleccione Actualizar alerta**.

Una vez generada una alerta, su estado es independiente del estado de la directiva que generó la alerta. Por ejemplo, es posible tener una alerta activa asociada a una directiva inactiva y  es posible tener un estado de investigación en una alerta generada por  una directiva que posteriormente se inactivó o eliminó.

### <a name="when-policies-are-deleted"></a>Cuando se eliminan las directivas

Cuando se elimina una directiva, las alertas generadas por esa directiva permanecerán en la  página Alertas, pero no se generarán alertas nuevas.

## <a name="email-notifications-of-alerts"></a>Notificaciones de alertas por correo electrónico

Al crear una directiva, se envía un correo electrónico al usuario que creó la directiva que le alerta de que se detectó una coincidencia. Puede elegir enviar estas notificaciones por correo electrónico a usuarios adicionales de su organización. Las alertas se producen casi en tiempo real y las notificaciones de correo electrónico se envían tan pronto como se genera una alerta. El correo electrónico contendrá el nombre del evento, la gravedad, el tiempo detectado y un vínculo para ver la alerta en el Administrador de cumplimiento.

### <a name="remove-users-from-receiving-alerts"></a>Quitar usuarios de recibir alertas

Si designa destinatarios de alertas y luego decide quitarlos más adelante, siga los pasos siguientes. Tenga en cuenta que el creador de directivas seguirá recibiendo notificaciones por correo electrónico cuando se detecten coincidencias de directiva.

1. Comience los pasos para [editar la directiva](#edit-a-policy).
2. Cuando llegue a la pantalla **Destinatarios de alerta** , seleccione **+Seleccionar destinatarios**.
3. En el  panel desplegable Seleccionar destinatarios, busque el usuario que desea quitar de las notificaciones y desactive la casilla a la izquierda de su nombre y, a continuación, seleccione  el botón Agregar destinatarios (que tiene el efecto de guardar la selección).
4. Continúe con el asistente y confirme que el usuario no aparece en **Destinatarios** en la página Revisar y finalizar. Selecciona **Actualizar** para guardar la configuración y finalizar.
