---
title: Introducción al administrador de cumplimiento de Microsoft
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Establezca los permisos y los roles de usuario de Microsoft Compliance Manager y configure las pruebas automatizadas de las acciones. Administrar el historial del usuario y filtrar la vista del panel.
ms.openlocfilehash: ead4fe60a11bcf78a318601c1de6d72f2490c567
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204530"
---
# <a name="get-started-with-compliance-manager"></a>Introducción al administrador de cumplimiento

**En este artículo:** Este artículo le ayudará a configurar el administrador de cumplimiento. Obtenga información sobre cómo **obtener acceso** al administrador de cumplimiento, **establecer roles y permisos**y configurar la **prueba automática de acciones de mejora**. Recorra el **panel del administrador de cumplimiento** y comprenda las páginas principales: la página acciones de mejora, la página soluciones, la página evaluaciones y la página plantillas de evaluación.

## <a name="who-can-access-compliance-manager"></a>Quién puede obtener acceso al administrador de cumplimiento

El administrador de cumplimiento está disponible para las organizaciones con las licencias de Office 365 y Microsoft 365. La disponibilidad y las capacidades de administración de la evaluación dependen del contrato de licencia.  [Ver los detalles](https://go.microsoft.com/fwlink/?linkid=2132371)de la descripción del servicio.

## <a name="before-you-begin"></a>Antes de empezar

El administrador global de Microsoft 365 para su organización será probablemente el primer usuario que tenga acceso al administrador de cumplimiento. Le recomendamos que inicie sesión con el administrador global y establezca los permisos de usuario tal y como se describe a continuación cuando visite el administrador de cumplimiento por primera vez.

## <a name="sign-in"></a>Iniciar sesión

1. Vaya al [centro de cumplimiento de microsoft 365](https://compliance.microsoft.com/) e **inicie sesión** con su cuenta de administrador global de Microsoft 365.
2. Seleccione **Administrador de cumplimiento** en el panel de navegación izquierdo. Llegará a su [panel del administrador de cumplimiento](#understand-the-compliance-manger-dashboard).

El vínculo directo para obtener acceso al administrador de cumplimiento es [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) .

## <a name="set-user-permissions-and-assign-roles"></a>Establecimiento de permisos de usuario y asignación de roles

El administrador de cumplimiento usa un modelo de permisos de control de acceso basado en roles (RBAC). Solo los usuarios a los que se les asigna un rol pueden tener acceso al administrador de cumplimiento y las acciones permitidas por cada usuario están restringidas por el [tipo de función](#role-types).

### <a name="where-to-set-permissions"></a>Dónde establecer permisos

La persona que asume el rol de administrador global de su organización puede establecer permisos de usuario en el centro de cumplimiento de Microsoft 365, así como en Azure Active Directory (Azure AD).

Para establecer permisos y asignar roles desde dentro del centro de cumplimiento de Microsoft 365, siga los pasos que se indican a continuación:

1. Seleccione **permisos** en el panel de navegación izquierdo desde cualquier lugar del [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/).

2. Cerca de la parte superior, seleccione el vínculo en **"para ver y administrar roles en Office 365, vaya aquí".** Se abrirá una nueva pestaña en el centro de seguridad & cumplimiento de Office 365 ([sepa por qué se le ha redirigido](microsoft-365-compliance-center.md#frequently-asked-questions)).

3. Busque el grupo de roles al que desea agregar uno o más usuarios y active la casilla a la izquierda del nombre del grupo. (Consulte la [lista de funciones y las funciones relacionadas a continuación](#role-types). Los nombres de los grupos de funciones imitan el nombre de la función.

4. En el panel flotante de ese grupo, seleccione **Editar** en el encabezado **miembros** .

5. Seleccione **elegir miembros**. Aparecerá otra ventana de flotante.

6. Seleccione **+ Agregar** para elegir uno o más usuarios para agregar al grupo.

7. Active la casilla de verificación situada junto a los nombres que desea agregar y, a continuación, seleccione el botón **Agregar** en la parte inferior.

8. Cuando termine de asignar usuarios, seleccione **listo**, seleccione **Guardar**y, después, **cerrar**.

##### <a name="more-about-the-office-365-secruity--compliance-center"></a>Más información sobre el centro de cumplimiento de & de Office 365 secruity

Obtenga más información sobre [los permisos en el centro de seguridad & cumplimiento de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).

Si no tiene acceso al centro de seguridad y cumplimiento de Office 365 o si necesita tener acceso a la versión clásica del administrador de cumplimiento en el portal de confianza de servicios de Microsoft, la configuración de administración del portal de confianza de servicios proporciona otra forma de asignar roles (instrucciones de la[vista](/meet-data-protection-and-regulatory-reqs-using-microsoft-cloud?view=o365-worldwide.md#assigning-compliance-manager-roles-to-users)). Tenga en cuenta que estos roles están más limitados en su funcionalidad.

##### <a name="more-about-azure-ad"></a>Más información sobre Azure AD

Para asignar roles y establecer permisos en Azure AD, consulte [asignar roles de administrador y no administrador a los usuarios con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

Los usuarios con identidades de Azure AD que no tengan suscripciones de Office 365 o Microsoft 365 no podrán obtener acceso al administrador de cumplimiento en el centro de cumplimiento de Microsoft 365. Para buscar ayuda en el acceso al administrador de cumplimiento, póngase en contacto con [cmresearch@microsoft.com](mailto:cmresearch@microsoft.com).

### <a name="role-types"></a>Tipos de funciones

En la tabla siguiente se muestran las funciones permitidas por cada función en el administrador de cumplimiento. En la tabla también se muestra cómo cada [rol de Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) se asigna a los roles de administrador de cumplimiento. Los usuarios necesitarán al menos el rol de lector del administrador de cumplimiento, o el rol de Azure AD global Reader, para obtener acceso al administrador de cumplimiento.


| El usuario puede: | Rol de administrador de cumplimiento | Rol de Azure AD | 
| :------------- | :-------------: | :------------: |
| **Leer los datos pero no modificarlos**| Lector del Administrador de cumplimiento  | Lector global de Azure AD, lector de seguridad | 
| **Editar datos**| Contribución del administrador de cumplimiento | Administrador de cumplimiento | 
| **Editar los resultados de la prueba**| Evaluación del administrador de cumplimiento | Administrador de cumplimiento | 
| **Administrar evaluaciones y datos de plantilla y espacio empresarial**| Administración del administrador de cumplimiento | Administrador de cumplimiento, administrador de datos de cumplimiento, administrador de seguridad  | 
| **Asignar usuarios**| Administrador global | Administrador global | 

## <a name="settings-for-automated-testing-and-user-history"></a>Configuración de pruebas automatizadas e historial del usuario

La configuración del administrador de cumplimiento en el centro de cumplimiento de Microsoft 365 permite habilitar y deshabilitar la prueba automática de acciones de mejora. La configuración también le permite administrar los datos de los usuarios asociados a las acciones de mejora, incluida la capacidad de reasignar acciones de mejora a un usuario diferente.  Solo las personas con un administrador global o un rol de administrador del administrador de cumplimiento pueden tener acceso a la configuración del administrador de cumplimiento.

### <a name="set-up-automated-testing"></a>Configurar pruebas automatizadas

Las acciones de mejora del administrador de cumplimiento también se supervisan con la [puntuación segura de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score). Puede configurar la prueba automatizada de las acciones que se supervisan conjuntamente, lo que significa que cuando se prueba y se actualiza una acción en calificación segura, los resultados se sincronizan con las mismas acciones en el administrador de cumplimiento y se recuentan hacia la puntuación de cumplimiento.

Las pruebas automáticas están activadas de forma predeterminada para las organizaciones nuevas en el administrador de cumplimiento. La primera vez que implemente Microsoft 365 u Office 365, tardará aproximadamente siete días en recibir una puntuación segura para recopilar los datos por completo y factorizarlos en la puntuación de cumplimiento.  Cuando la prueba automatizada está activada, la fecha de prueba de la acción no se actualizará, pero su estado de prueba se actualizará. Cuando se crean nuevas evaluaciones, las puntuaciones incluyen automáticamente los resultados de los controles de Microsoft y la integración de la puntuación segura.

El administrador global de su organización puede cambiar la configuración de las pruebas automatizadas en cualquier momento. Puede desactivar las pruebas automatizadas para acciones de mejora comunes o activarlas para acciones individuales. Siga las instrucciones siguientes para cambiar la configuración de la prueba automatizada.

#### <a name="to-manage-your-automated-testing-settings"></a>Para administrar la configuración de pruebas automatizadas:

1. Seleccione **configuración** en la navegación izquierda desde cualquier lugar del [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/).

2. En la página Configuración, seleccione **Administrador de cumplimiento**.

3. Seleccione **prueba automatizada** desde el panel de navegación izquierdo.

4. Seleccione el botón aplicable para activar las pruebas automáticas para todas las acciones de mejora, desactivarlas para todas las acciones o activarlas por acción individual.

5. Si selecciona **activar por acción de mejora**, una lista mostrará todas las acciones de mejora disponibles que puede elegir.  Active la casilla junto a cualquier acción que desee que se pruebe automáticamente.

6. Seleccione **Guardar** para guardar la configuración. Recibirá un mensaje de confirmación en la parte superior de la pantalla en el que se guardó la selección. Si recibe un aviso de error, inténtelo de nuevo.

**Nota:** Solo el administrador global puede activar o desactivar las actualizaciones automáticas para todas las acciones. El administrador del administrador de cumplimiento puede activar actualizaciones automáticas para acciones individuales, pero no para todas las acciones de forma global.

### <a name="manage-user-history"></a>Administrar el historial del usuario

La configuración de **Manage User History** le ayuda a identificar rápidamente qué usuarios han trabajado con acciones de mejora en el administrador de cumplimiento. Los datos de usuario identificables asociados con acciones de mejora incluyen cualquier trabajo de implementación y pruebas realizado, los documentos que se cargan y las notas que hayan escrito. Es posible que sea necesario comprender y recuperar este tipo de datos para satisfacer las necesidades de cumplimiento propias de su organización.

La configuración del historial del usuario también le permite reasignar todas las acciones de mejora de un usuario a otro.

**Para buscar la configuración del historial del usuario:**

1. Seleccione configuración en la navegación izquierda desde cualquier lugar del [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/).

2. En la página Configuración, seleccione **Administrador de cumplimiento**.

3. Seleccione **administrar el historial del usuario** desde el panel de navegación izquierdo.

La página **administrar historial de usuarios** muestra una lista de todos los usuarios por dirección de correo electrónico asignada a una acción de mejora. Use el botón **Buscar** para encontrar rápidamente un usuario específico escribiendo en su dirección de correo electrónico.

A la derecha de la dirección de correo electrónico de cada usuario, el menú desplegable **seleccionar** proporciona opciones para exportar un informe, reasignar acciones de mejora o eliminar el historial. Consulte cada una de las secciones siguientes para obtener más información sobre cada opción.

#### <a name="export-a-report-of-user-history-data"></a>Exportar un informe de datos del historial del usuario

Puede exportar un archivo de Excel que contenga una lista de acciones de mejora actualmente asignadas a un usuario.  El informe también enumera los archivos de evidencia cargados por el usuario. Esta información puede ayudarle a reasignar acciones de mejora abiertas.

El informe refleja el estado de la acción de mejora a partir de su fecha de creación. No se trata de un informe histórico de todos los cambios anteriores realizados en su estado o asignación (Obtenga información sobre cómo [exportar un informe de la página acciones de mejora](compliance-manager-improvement-actions.md#export-a-report)).

**Siga los pasos a continuación para exportar un informe por usuario:**

1. Seleccione **configuración** en la navegación izquierda desde cualquier lugar del [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/).

2. En la página Configuración, seleccione **Administrador de cumplimiento**.

3. Seleccione **administrar el historial del usuario** en la navegación de la izquierda.

4. Busque el usuario deseado en la lista de direcciones de correo electrónico o seleccione **Buscar** y escriba la dirección de correo electrónico del usuario.

5. En el menú desplegable **seleccionar** , elija **exportar Informe**.

6. Una vez que se haya generado el archivo de Excel del informe, puede abrirlo y guardarlo en el equipo local.

#### <a name="reassign-improvement-actions-to-another-user"></a>Reasignar acciones de mejora a otro usuario

Puede reasignar acciones de mejora de un usuario a otro. Cuando se reasigna una acción, el historial de carga del documento no cambia, pero el nombre del usuario que cargó originalmente la documentación ya no aparece en la acción de mejora.

**Siga los pasos siguientes para reasignar acciones de mejora a otro usuario:**

1. Seleccione **configuración** en la navegación izquierda desde cualquier lugar del [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/).

2. En la página Configuración, seleccione **Administrador de cumplimiento**.

3. Seleccione **administrar el historial del usuario** en la navegación de la izquierda.

4. Busque un usuario en la lista de direcciones de correo electrónico o seleccione **Buscar** y escriba la dirección de correo electrónico del usuario.

5. En el menú desplegable **seleccionar** , elija **reasignar acciones de mejora**. Aparecerá el panel flotante **acciones de mejora** para volver a asignar.

6. En el campo **Buscar usuarios** , escriba el nombre o la dirección de correo electrónico del usuario *al*que desea asignar las acciones de mejora.

7. Cuando vea el nombre del usuario previsto en acciones de **mejora se asignará a**, seleccione el usuario y, a continuación, seleccione **asignar acciones**.

8. Una vez completada la reasignación, verá un mensaje de confirmación en el panel de flotante en el que se confirma que se han reasignado todas las acciones de mejora del usuario anterior al nuevo usuario. Si recibe un aviso de error de reasignación, cierre la ventana y vuelva a intentarlo. Para cerrar el panel de flotante, seleccione **listo**.

El nuevo encargado recibe un correo electrónico que se le ha asignado a una acción de mejora. El correo electrónico contiene un vínculo directo en la página de detalles de la acción de mejora.
 
 > [!NOTE]
> Si reasigna una acción que tiene una actualización pendiente, el vínculo directo a la acción en el correo electrónico de reasignación se interrumpirá si la actualización se acepta después de la reasignación. Para solucionar esto, puede volver a asignar la acción al usuario una vez aceptada la actualización. Obtenga más información sobre [las actualizaciones de las acciones de mejora](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).

#### <a name="delete-user-history"></a>Eliminar el historial del usuario

Si se elimina el historial de un usuario, se quitará como propietario de acciones de mejora y se quitará el nombre de los demás campos en el administrador de cumplimiento. Al eliminar el historial de un usuario, las acciones de mejora que poseían no mostrarán un valor **asignado a** hasta que se asigne un nuevo usuario. Los documentos cargados en la acción de mejora mostrarán al **usuario eliminado** en vez del nombre del usuario eliminado. Eliminar el historial del usuario es permanente.

Para eliminar el historial de un usuario, siga los pasos que se indican a continuación:

1. Seleccione **configuración** en la navegación izquierda desde cualquier lugar del [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/).

2. En la página Configuración, seleccione **Administrador de cumplimiento**.

3. Seleccione **administrar el historial del usuario** en la navegación de la izquierda.

4. Busque un usuario en la lista de direcciones de correo electrónico o seleccione **Buscar** y escriba la dirección de correo electrónico del usuario.

5. En el menú desplegable **seleccionar** , elija **eliminar historial**.

6. Aparecerá una ventana en la que se le pedirá que confirme la eliminación permanente del historial del usuario. Para continuar con la eliminación, seleccione **eliminar historial**. Para salir sin eliminar el historial, seleccione **Cancelar**.

7. Volverá a la página **administrar historial de usuarios** con un mensaje de confirmación en la parte superior en el que se eliminó el historial del usuario.

## <a name="understand-the-compliance-manger-dashboard"></a>Descripción del panel del administrador de cumplimiento

El panel del administrador de cumplimiento está diseñado para proporcionar una vista inmediata de la postura de cumplimiento actual.

![Administrador de cumplimiento: panel](../media/compliance-manager-dashboard.png "Panel del administrador de cumplimiento")

### <a name="overall-compliance-score"></a>Puntuación de cumplimiento general

La puntuación de cumplimiento se presenta destacadamente en la parte superior. Muestra un porcentaje basado en puntos que se alcanzan para completar acciones de mejora que abordan los estándares y regulaciones clave de protección de datos. Los puntos de [las acciones de Microsoft](compliance-manager-assessments.md#microsoft-actions-tab), que son administrados por mi Microsoft, también cuentan para la puntuación de cumplimiento.

Cuando llegue al administrador de cumplimiento por primera vez, su puntuación inicial se basa en la [línea base de protección de datos 365 de Microsoft](compliance-manager-assessments.md#data-protection-baseline-default-assessment). Esta evaluación de línea base, que está disponible para todas las organizaciones, es un conjunto de controles que incluye las normas y estándares comunes de la industria. El administrador de cumplimiento examina las soluciones de Microsoft 365 existentes y le proporciona una evaluación inicial en función de la configuración de privacidad y seguridad actual. A medida que agregue evaluaciones relevantes para su organización, su puntuación será más significativa para usted.

**Obtenga más información:** [comprenda cómo se calcula la puntuación de cumplimiento](compliance-score-calculation.md).

### <a name="key-improvement-actions"></a>Acciones para la mejora de claves

En esta sección se enumeran las acciones de mejora más importantes que puede realizar ahora para hacer el mayor impacto positivo en la puntuación de cumplimiento general. Seleccione **ver todas las acciones de mejora** para ir a la página acciones de mejora.

### <a name="solutions-that-affect-your-score"></a>Soluciones que afectan a su calificación

En esta sección se destacan soluciones que contienen acciones de mejora que pueden afectar positivamente su puntuación y el número de acciones de mejora pendientes en esas soluciones. Seleccione **ver todas las soluciones** para visitar su página de soluciones.

### <a name="compliance-score-breakdown"></a>Desglose de puntuación de cumplimiento

En esta sección se ofrece una vista más detallada de su puntuación de dos maneras diferentes:

- **Categorías**: muestra el porcentaje de la puntuación general dentro de las categorías de protección de datos, como "proteger la información" o "administrar dispositivos".
- **Evaluaciones**: muestra el porcentaje de su progreso en la administración de las evaluaciones para normas, regulaciones o leyes de protección de datos y cumplimiento en particular, como RGPD o NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtrar la vista del panel

Puede filtrar la vista del panel para ver solo los elementos relacionados con normas y estándares concretos, soluciones, tipo de acción, grupos de evaluación o categorías de protección de datos. Filtrar la vista de esta manera también filtrará la puntuación en el panel, indicando cuántos puntos ha obtenido del total de puntos posibles en función de los criterios del filtro.

Para aplicar filtros:

1. Seleccione **filtrar** en la parte superior derecha del panel.
2. Seleccione los criterios de filtro en el panel desplegable **filtros** y, después, seleccione **aplicar**.

Después de aplicar un filtro, verá su puntuación ajustada en tiempo real. El porcentaje de puntuación de cumplimiento e información desglosada, y las acciones y soluciones de mejora, ahora solo pertenecen a los datos cubiertos por los criterios de filtro. Si cierre sesión en el administrador de cumplimiento, la vista filtrada permanecerá cuando vuelva a iniciar sesión.

Para quitar filtros:

- En el encabezado de **filtros aplicados** encima de la puntuación de cumplimiento, seleccione la **X** junto al filtro individual que quiera quitar; o
- Seleccione **filtrar** en la parte superior derecha del panel y, a continuación, en el panel flotante de **filtros** , seleccione **Borrar filtros**.

## <a name="improvement-actions-page"></a>Página acciones de mejora

Las [acciones de mejora](compliance-manager-improvement-actions.md) son acciones administradas por la organización. Trabajar con acciones de mejora ayuda a centralizar las actividades de cumplimiento y a alinearse con las normas y estándares de protección de datos. Cada acción de mejora proporciona una guía de implementación detallada y un vínculo para iniciarla en la solución adecuada. Las acciones de mejora se pueden asignar a los usuarios de su organización para realizar tareas de implementación y pruebas. También puede almacenar la documentación, las notas y las actualizaciones de estado de registro dentro de la acción de mejora.

### <a name="view-your-improvement-actions"></a>Ver las acciones de mejora

El panel del administrador de cumplimiento muestra las **acciones de mejora de clave.** Para ver todas las acciones de mejora, seleccione la pestaña acciones de mejora del panel, que le proporciona a la página acciones de mejora. También puede seleccionar ver todas las acciones de mejora debajo de la lista de acciones de mejora de clave en el panel para ir a la página acciones de mejora.

La página acciones de mejora muestra todas las acciones de mejora que administra la organización. Las acciones que Microsoft administra se pueden ver en cada evaluación (Obtenga más información sobre [las acciones de Microsoft](compliance-manager-assessments.md#microsoft-actions-tab)).

Si tiene una larga lista de acciones en la página acciones de mejora, puede resultar útil filtrar la vista. Seleccione **filtro** en la esquina superior derecha de la lista acciones. Cuando aparezca el panel desplegable **filtros** , seleccione los criterios en función de las regulaciones y los estándares, la solución y el grupo. También puede personalizar la vista seleccionando **Grupo** en la esquina superior derecha. En el menú desplegable, seleccione Ver por grupo, solución, categoría, tipo de acción o estado.

La vista predeterminada de esta página no muestra acciones de mejora con el estado de prueba **aprobado**. Para ver las acciones que han superado la prueba, active la casilla **aprobado** en el panel flotante de filtros. Solo acciones con un estado de prueba de recuento **aprobado** hacia su calificación. Algunas acciones pueden mostrar una **etiqueta de actualización pendiente.** Obtenga más información sobre [las actualizaciones de las acciones de mejora](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).

La página acciones de mejora muestra los siguientes puntos de datos para cada acción de mejora:

- **Puntos logrados**: el número de puntos que se obtiene del total disponible al completar la acción.
- **Regulaciones**: normas o normas relativas a la acción
- **Grupo**: el grupo al que asignó la acción
- **Soluciones**: la solución en la que puede realizar la acción.
- **Evaluaciones**: las evaluaciones que contienen la acción
- **Categorías**: categoría de protección de datos relacionada (por ejemplo, proteger la información, administrar dispositivos, etc.)
- **Estado**de la prueba:
    - **None** : no se ha grabado ninguna actualización del estado
    - **No evaluado: no** se han iniciado las pruebas
    - **Aprobada** : la implementación se ha probado correctamente
    - Error en la prueba de **riesgo bajo** , riesgo bajo
    - **Riesgo medio fallido** : no se pudieron probar las pruebas, riesgo medio
    - Error en la prueba de **riesgo alto** , riesgo alto
    - **Fuera del ámbito** : la acción no está en el ámbito de la evaluación y no afecta a su calificación.
    - **Para ser detectado** -para una prueba manual, indica que se ha implementado una acción pero no se ha probado; para la prueba automatizada, indica que una acción está esperando el resultado de automatización
    - **No se pudo detectar** : no se puede determinar el estado automatizado
    - **Probada parcialmente** : puntuación automatizada que premia puntos parciales

**Más información:** [vea cómo asignar y realizar tareas de trabajo en las acciones de mejora](compliance-manager-improvement-actions.md).

## <a name="solutions-page"></a>Página de soluciones

La página soluciones muestra el recurso compartido de puntos potenciales y ganados organizados por solución. Ver los puntos y acciones de mejora restantes en esta vista ayuda a comprender qué soluciones necesitan atención más inmediata.

Para buscar la página soluciones, seleccione la ficha **soluciones** en el panel del administrador de cumplimiento. También puede seleccionar **ver todas las soluciones** debajo de **soluciones que afectan a su calificación** en la sección superior derecha del panel.

### <a name="filtering-your-solutions-view"></a>Filtrar la vista de soluciones

Para filtrar la vista de soluciones:

1. Seleccione **filtrar** en la esquina superior izquierda de la lista de evaluaciones.
2. En el panel flotante de **filtros** , active las casillas de verificación junto a los criterios que desee (normas y regulaciones, solución, tipo de acción, grupo administrador de cumplimiento, categoría).
3. Seleccione el botón **aplicar** . El panel de filtros se cerrará y verá la vista filtrada.

También puede modificar la vista para ver las evaluaciones por grupo, producto o regla seleccionando el tipo de agrupación en el menú desplegable de **grupos** situado encima de la lista de evaluaciones.

### <a name="taking-action-from-the-solution-page"></a>Realizar acciones desde la página de la solución

La página soluciones muestra las soluciones de su organización que están conectadas a acciones de mejora. La tabla muestra la contribución de cada solución a la puntuación general, los puntos logrados y posibles dentro de esa solución y el número restante de acciones de mejora agrupadas en esa solución que pueden aumentar la puntuación.

Hay dos formas de realizar acciones en esta pantalla:

1. En la fila de la solución deseada, en la columna **acciones restantes** , seleccione el número de hipervínculo. Verá una vista filtrada de la pantalla acciones de mejora que muestra acciones de mejora no probadas para dicha solución.

2. En la fila de la solución deseada, en la columna **Abrir solución** , seleccione **abrir**. Verá la solución o la ubicación en los centros de seguridad y cumplimiento de Microsoft 365 y Office 365 donde puede llevar a cabo la acción recomendada.

## <a name="assessments-page"></a>Página evaluaciones

La página evaluaciones enumera todas las [evaluaciones](compliance-manager-assessments.md) que ha configurado para su organización. El denominador de puntuación de cumplimiento se determina por todas las evaluaciones con seguimiento. A medida que agregue más evaluaciones, verá acciones de más mejora en la lista de la página acciones de mejora y el denominador de puntuación de cumplimiento aumenta.

La página evaluaciones resume la información clave de cada evaluación:

- **Evaluación**: nombre de la evaluación
- **Estado**:
    - **Completo** : todos los controles tienen un estado de "Passed" o al menos uno se pasa y el resto están "fuera de ámbito"
    - **Incompleto** : al menos un control tiene un estado de "error"
    - **Ninguno** : no se han probado todos los controles
    - Las acciones **de mejora del progreso** tienen cualquier otro Estado, incluidos "en curso" "crédito parcial" o "no detectado
- **Progreso**de la evaluación: porcentaje del trabajo realizado hasta la finalización, medido por el número de controles correctamente probados
- Las **acciones de mejora**: el número de acciones completadas para satisfacer la implementación de los controles
- **Acciones de Microsoft**: el número de acciones completadas para satisfacer la implementación de los controles de Microsoft
- **Grupo**: nombre del grupo al que pertenece la evaluación
- **Producto**: servicio de Microsoft 365 asociado
- **Reglamento**: el estándar normativo, la política o la legislación que se aplica a la evaluación

### <a name="filtering-your-assessments-view"></a>Filtrar la vista de evaluaciones

Para filtrar la vista de las evaluaciones:

1. Seleccione **filtrar** en la esquina superior izquierda de la lista de evaluaciones.
2. En el panel desplegable de **filtros** , compruebe los criterios que desee.
3. Seleccione el botón **aplicar** . El panel de filtros se cerrará y verá la vista filtrada.

También puede modificar la vista para ver las evaluaciones por grupo, producto o regla seleccionando el tipo de agrupación en el menú desplegable de **grupos** situado encima de la lista de evaluaciones.

### <a name="default-assessment"></a>Evaluación predeterminada

De forma predeterminada, verá la evaluación de [línea base de protección de datos](compliance-manager-assessments.md#data-protection-baseline-default-assessment) en la página evaluaciones. El administrador de cumplimiento también proporciona varias [plantillas](compliance-manager-templates-list.md) predefinidas para crear evaluaciones.

## <a name="assessment-templates-page"></a>Página de plantillas de evaluación

Una plantilla es un marco para crear una evaluación en el administrador de cumplimiento. La página plantillas de evaluación muestra una lista de plantillas y los detalles clave. La lista incluye las plantillas proporcionadas por el administrador de cumplimiento, así como todas las plantillas que la organización haya modificado o creado. Puede aplicar filtros para buscar una plantilla en función de la certificación, el ámbito del producto, el país, la industria y quién la ha creado.

Seleccione una plantilla de la fila para que aparezca la página de detalles, que contiene una descripción de la plantilla e información adicional acerca de los detalles de certificación, ámbito y controles. En esta página, puede seleccionar los botones apropiados para crear una evaluación, exportar los datos de la plantilla a Excel o modificar la plantilla.

**Obtenga más información:** [Lea cómo trabajar con plantillas de evaluación](compliance-manager-templates.md).

## <a name="next-step"></a>Paso siguiente
Personalización del administrador de cumplimiento mediante la [configuración de evaluaciones](compliance-manager-assessments.md).