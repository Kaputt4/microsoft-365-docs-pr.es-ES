---
title: Configuración de la puntuación de cumplimiento de Microsoft (versión preliminar)
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
description: Obtenga información sobre cómo configurar y empezar a usar la puntuación de cumplimiento de Microsoft, que ayuda a simplificar y automatizar las evaluaciones de riesgos.
ms.openlocfilehash: f7a501d0ede0d7635e20581774ce51a599dde65b
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016195"
---
# <a name="compliance-score-preview-setup"></a>Configuración de la puntuación de cumplimiento (vista previa)

**En este artículo:** Obtenga información sobre cómo **obtener acceso a** la puntuación de cumplimiento, establecer **roles y permisos**y configurar **actualizaciones de calificaciones seguras automáticas**. En este artículo también se explican las páginas de puntuación de cumplimiento principales: **su panel**, la página acciones de mejora, la página soluciones y la página evaluaciones.

## <a name="before-you-begin"></a>Antes de empezar

El administrador global de Microsoft 365 para su organización probablemente será el primer usuario para obtener acceso a la puntuación de cumplimiento. Se recomienda el inicio de sesión de administrador global y la configuración de los permisos de usuario, como se describe a continuación, al visitar la puntuación de cumplimiento por primera vez.

## <a name="sign-in"></a>Iniciar sesión

1. Vaya al [centro de cumplimiento de microsoft 365](https://compliance.microsoft.com/) e **inicie sesión** con su cuenta de administrador global de Microsoft 365.
2. Seleccione **puntuación de cumplimiento** en el panel de navegación izquierdo. A continuación, debería ver el [Panel de puntuación de cumplimiento con su puntuación](#understand-the-compliance-score-dashboard).

El vínculo directo para obtener acceso a la puntuación de cumplimiento es [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore) .

## <a name="set-user-permissions-and-assign-roles"></a>Establecimiento de permisos de usuario y asignación de roles

La puntuación de cumplimiento usa un modelo de permisos de control de acceso basado en roles (RBAC). Solo los usuarios a los que se les asigna un rol pueden obtener acceso a la puntuación de cumplimiento y las acciones permitidas por cada usuario están restringidas por el tipo de función.

### <a name="where-to-set-permissions"></a>Dónde establecer permisos

La persona que asume el rol de administrador global de su organización puede establecer permisos de usuario en [Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) o en el [Administrador de cumplimiento](compliance-manager-overview.md#permissions). Una vez que las funciones se establecen en cualquiera de estas ubicaciones, los usuarios pueden acceder a la puntuación de cumplimiento y al administrador de cumplimiento.

### <a name="role-types"></a>Tipos de funciones

En la tabla siguiente se muestra cómo cada [rol de Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) se asigna a los roles del administrador de cumplimiento existentes y las funciones permitidas por cada rol. Los usuarios necesitarán, al menos, el rol de lector global de Azure AD para obtener acceso a la puntuación de cumplimiento.


| El usuario puede: | Rol de Azure AD | Rol de administrador de cumplimiento | 
| :------------- | :-------------: | :------------: |
| **Leer los datos pero no modificarlos**| Lector global de Azure AD  | Lector global de Azure AD | 
| **Leer los datos pero no modificarlos**| Lector de seguridad | Lector del administrador de cumplimiento  | 
| **Editar datos**| Administrador de cumplimiento | Colaborador del administrador de cumplimiento | 
| **Editar los resultados de la prueba**| Administrador de cumplimiento | Asesor del administrador de cumplimiento | 
| **Administrar evaluaciones y datos de plantilla y espacio empresarial**| Administrador de cumplimiento<br>Administrador de datos de cumplimiento<br>Administrador de seguridad | Administrador del administrador de cumplimiento | 
| **Asignar usuarios**| Administrador global | Administrador del portal | 

> [!NOTE]
> Cuando pase de la puntuación de cumplimiento al administrador de cumplimiento para completar una tarea durante la versión preliminar pública, el explorador abrirá una nueva pestaña y aparecerá un cuadro de diálogo. En la sección superior con el encabezado, "¿ya es un cliente de Microsoft Cloud Services? Inicie sesión en su cuenta, "seleccione **iniciar sesión** para obtener acceso al administrador de cumplimiento. No tendrá que volver a escribir sus credenciales.

## <a name="configure-automatic-secure-score-updates"></a>Configurar actualizaciones de calificación segura automáticas

De forma predeterminada, todos los nuevos inquilinos tienen activada la opción actualizaciones automáticas de [puntuación segura](../security/mtp/microsoft-secure-score-new.md) . Todas las acciones que se supervisan con calificación segura actualizarán automáticamente el estado de la misma acción en la puntuación de cumplimiento.

El administrador global puede administrar esta configuración para desactivar las actualizaciones automáticas para todas las acciones, o bien establecer actualizaciones para las acciones de forma individual.

Durante la versión preliminar pública, tendrá que ir al portal de confianza del servicio de Microsoft (donde está ubicado el administrador de cumplimiento) para administrar las actualizaciones de puntuación segura.

Para administrar las actualizaciones de calificaciones seguras automáticas, siga estos pasos:

1. Inicie sesión en el [portal de confianza de servicios](https://servicetrust.microsoft.com) con su cuenta de administrador global.

2. En la barra de menús del portal de confianza del servicio superior, en **más**, seleccione **Administrador** y, después, seleccione **configuración**.

3. En la ficha **puntuación segura** , seleccione el botón correspondiente para **activar todas las acciones**, **desactivar para todas las acciones**o **establecer por acción.**

Si elige **establecer por acción,** siga estos pasos adicionales para activar las actualizaciones de puntuación segura para acciones individuales:

4. Seleccione **Administrador de cumplimiento** en el menú superior (no seleccione "Administrador de cumplimiento (clásico)").

5. Seleccione **Administración de inquilinos** en la esquina superior derecha de la pantalla.

6. En el panel **acciones del cliente** , busque la acción prevista con puntos suspensivos (**...**) en la columna **acciones afectadas** . Haga clic en los puntos suspensivos y seleccione **Editar.**

7. Cambie el conmutador de alternancia de **actualización continua de puntuación segura** a **activado.**

8. Seleccione **Guardar.** Puntuación segura la supervisión continua ahora está activada para esa acción.

**Nota:** Solo el administrador global puede activar o desactivar las actualizaciones automáticas para todas las acciones. El administrador del administrador de cumplimiento puede activar actualizaciones automáticas para acciones individuales, pero no para todas las acciones de forma global.

#### <a name="learn-more"></a>Más información

[Lea acerca de la administración de actualizaciones de calificaciones seguras](compliance-manager-release-notes.md#secure-score).

## <a name="understand-the-compliance-score-dashboard"></a>Descripción del panel de calificaciones de cumplimiento

El panel de calificaciones de cumplimiento está diseñado para proporcionar una vista inmediata de la postura de cumplimiento actual.

![Puntuación de cumplimiento: panel](../media/compliance-score-dashboard.png "Panel de calificaciones de cumplimiento")

### <a name="overall-compliance-score"></a>Puntuación de cumplimiento general

La puntuación de cumplimiento se presenta destacadamente en la parte superior. Muestra un porcentaje basado en puntos que se alcanzan para completar acciones de mejora que abordan los estándares y regulaciones clave de protección de datos.

Cuando llega a la puntuación de cumplimiento por primera vez, su puntuación inicial se basa en la [línea de base de protección de datos de Microsoft 365](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)integrada: un conjunto de controles que incluye normas y estándares comunes de la industria. La puntuación de cumplimiento examina las soluciones de Microsoft 365 existentes y le ofrece una evaluación inicial en función de la configuración de privacidad y seguridad actual. A medida que agregue evaluaciones relevantes para su organización, su puntuación será más significativa para usted.

#### <a name="learn-more"></a>Más información
[Comprenda cómo se calcula la puntuación de cumplimiento](compliance-score-methodology.md).

### <a name="key-improvement-actions"></a>Acciones para la mejora de claves

En esta sección se enumeran las acciones de mejora más importantes que puede realizar ahora para hacer el mayor impacto positivo en la puntuación de cumplimiento general.

### <a name="solutions-that-affect-your-score"></a>Soluciones que afectan a su calificación

En esta sección se muestran soluciones que contienen acciones con la mayor oportunidad de afectar positivamente su puntuación y el número de acciones de mejora pendientes en cada solución.

### <a name="compliance-score-breakdown"></a>Desglose de puntuación de cumplimiento

En esta sección se ofrece una vista más detallada de su puntuación de dos maneras diferentes:

- **Categorías**: muestra el porcentaje de la puntuación general dentro de las categorías de protección de datos, como "proteger la información" o "administrar dispositivos".
- **Evaluaciones**: muestra el porcentaje de su progreso en la administración de las evaluaciones para normas, regulaciones o leyes de protección de datos y cumplimiento en particular, como RGPD o NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtrar la vista del panel

Puede filtrar la vista del panel para ver solo los elementos relacionados con normas y estándares concretos, soluciones, tipo de acción, grupos de evaluación o categorías de protección de datos. Filtrar la vista de esta manera también filtrará la puntuación en el panel, indicando cuántos puntos ha obtenido del total de puntos posibles en función de los criterios del filtro.

Para aplicar filtros:

1. Seleccione **filtrar** en la parte superior derecha del panel.
2. Seleccione los criterios de filtro en el panel desplegable **filtros** y, después, seleccione **aplicar**.

Después de aplicar un filtro, verá su puntuación ajustada en tiempo real. El porcentaje de puntuación de cumplimiento e información desglosada, y las acciones y soluciones de mejora, ahora solo pertenecen a los datos cubiertos por los criterios de filtro. Si sale de la puntuación de cumplimiento, la vista filtrada permanecerá cuando vuelva a iniciar sesión.

Para quitar filtros:

- En el encabezado de **filtros aplicados** encima de la puntuación de cumplimiento, seleccione la **X** junto al filtro individual que quiera quitar; o
- Seleccione **filtrar** en la parte superior derecha del panel y, a continuación, seleccione **Borrar filtros**.

## <a name="improvement-actions-page"></a>Página acciones de mejora

[Las acciones de mejora](compliance-score-improvement-actions.md) centralizan las actividades de cumplimiento y le ayudan a alinearse con las normas y estándares de protección de datos. Cada acción de mejora proporciona una guía de implementación detallada y un vínculo para iniciarla en la solución adecuada. Se pueden asignar acciones a los usuarios de su organización para realizar tareas de implementación y pruebas. También puede almacenar la documentación, las notas y las actualizaciones de estado de registro dentro de la acción de mejora.

### <a name="view-your-improvement-actions"></a>Ver las acciones de mejora

El panel de calificaciones de cumplimiento muestra las **acciones de mejora de clave**, que son las que tienen los puntos más disponibles para solucionar los problemas más importantes.

Para ver todas las acciones de mejora, seleccione la pestaña **acciones de mejora** del panel. O bien, seleccione **ver todas las acciones de mejora** , debajo de la lista de acciones de mejora de clave en el panel.

Si tiene una larga lista de acciones, puede resultar útil filtrar la vista. Seleccione **filtro** en la esquina superior derecha de la lista acciones. Cuando aparezca el panel desplegable **filtros** , seleccione los criterios en función de las regulaciones y los estándares, la solución y el grupo. También puede personalizar la vista seleccionando **Grupo** en la esquina superior derecha. En el menú desplegable, seleccione Ver por grupo, solución, categoría, tipo de acción o estado.

La vista predeterminada de esta página no muestra acciones de mejora con el estado de prueba **aprobado**. Para ver las acciones que han superado la prueba, active la casilla **aprobado** en el panel flotante de filtros. Solo acciones con un estado de prueba de recuento **aprobado** hacia su calificación.

La página acciones de mejora muestra los siguientes puntos de datos para cada acción de mejora:

- **Impacto del resultado**: los puntos por los que aumentará la puntuación general al completar la acción.
- **Regulaciones**: el Reglamento o el estándar que pertenece a la acción
- **Grupo**: el grupo al que asignó la acción
- **Soluciones**: la solución en la que puede realizar la acción.
- **Evaluaciones**: la evaluación (que organiza los controles para cumplir un determinado objetivo de cumplimiento) en el que reside la acción.
- **Categorías**: categoría de protección de datos relacionada (por ejemplo, proteger la información, administrar dispositivos, etc.)
- **Estado**de la prueba:
    - **None** : no se ha grabado ninguna actualización del estado
    - **No evaluado: no** se han iniciado las pruebas
    - **Aprobada** : la implementación se ha probado correctamente
    - Error en la prueba de **riesgo bajo** , riesgo bajo
    - **Riesgo medio fallido** : no se pudieron probar las pruebas, riesgo medio
    - Error en la prueba de **riesgo alto** , riesgo alto
    - **No en ámbito** : la acción no está en el ámbito de la evaluación y no afecta a su calificación.
    - **Para ser detectado** -para una prueba manual, indica que se ha implementado una acción pero no se ha probado; para la prueba automatizada, indica que una acción está esperando el resultado de automatización
    - **No se pudo detectar** : no se puede determinar el estado automatizado
    - **Probada parcialmente** : puntuación automatizada que premia puntos parciales
- **Puntos logrados**: número de puntos que se obtuvieron del máximo posible

#### <a name="learn-more"></a>Más información
[Consulte Cómo asignar y realizar tareas de trabajo en las acciones de mejora](compliance-score-improvement-actions.md).

## <a name="solutions-page"></a>Página de soluciones

La página soluciones muestra el recurso compartido de puntos potenciales y ganados organizados por solución. Ver los puntos y acciones de mejora restantes en esta vista ayuda a comprender qué soluciones necesitan atención más inmediata.

Para buscar la página soluciones, seleccione la pestaña **soluciones** en el panel de calificaciones de cumplimiento. También puede seleccionar **ver todas las soluciones** debajo de **soluciones que afectan a su calificación** en la sección superior derecha del panel.

### <a name="filtering-your-solutions-view"></a>Filtrar la vista de soluciones

Para filtrar la vista de soluciones:

1. Seleccione **filtrar** en la esquina superior izquierda de la lista de evaluaciones.
2. En el panel flotante de **filtros** , active las casillas de verificación junto a los criterios que desee (normas y regulaciones, solución, tipo de acción, grupo administrador de cumplimiento, categoría).
3. Seleccione el botón **aplicar** . El panel de filtros se cerrará y verá la vista filtrada.

También puede modificar la vista para ver las evaluaciones por grupo, producto o regla seleccionando el tipo de agrupación en el menú desplegable de **grupos** situado encima de la lista de evaluaciones.

### <a name="taking-actions-from-the-solution-page"></a>Realizar acciones desde la página de solución

La página soluciones muestra las soluciones de su organización que están conectadas a acciones de mejora. En la tabla se muestra la contribución de cada solución a la puntuación general, los puntos de mejora de la puntuación alcanzados y posibles dentro de esa solución y el número restante de acciones de mejora agrupadas en esa solución que pueden aumentar la puntuación.

Hay dos formas de realizar acciones en esta pantalla:

1. En la fila de la solución deseada, en la columna **acciones restantes** , seleccione el número de hipervínculo. Verá una vista filtrada de la pantalla acciones de mejora que muestra acciones de mejora no probadas para dicha solución.

2. En la fila de la solución deseada, en la columna **Abrir solución** , seleccione **abrir**. Verá la solución o la ubicación en los centros de seguridad y cumplimiento de Microsoft 365 y Office 365 donde puede llevar a cabo la acción recomendada.

## <a name="assessments-page"></a>Página evaluaciones

La página evaluaciones enumera todas las [evaluaciones](compliance-score-assessments.md) que ha configurado para su organización. El denominador de puntuación de cumplimiento se determina por todas las evaluaciones con seguimiento. Cuanto más evaluaciones agregue, más acciones de mejora verá en la página acciones de mejora y mayor será el denominador de puntuación.

En esta página se resume la información clave de cada evaluación:

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
3. Seleccione el botón aplicar. El panel de filtros se cerrará y verá la vista filtrada.

También puede modificar la vista para ver las evaluaciones por grupo, producto o regla seleccionando el tipo de agrupación en el menú desplegable de **grupos** situado encima de la lista de evaluaciones.

### <a name="default-assessment"></a>Evaluación predeterminada

De forma predeterminada, verá la evaluación de [línea base de protección de datos 365 de Microsoft](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline) en la página evaluaciones. La puntuación de cumplimiento también proporciona varias [plantillas](compliance-score-templates.md) listas para usar para crear evaluaciones.

## <a name="next-step"></a>Paso siguiente
Personalice la puntuación de cumplimiento mediante la [configuración de evaluaciones](compliance-score-assessments.md).