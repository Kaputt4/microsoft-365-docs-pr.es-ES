---
title: Introducción al Administrador de cumplimiento de Microsoft
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Establecer roles y permisos de usuario del Administrador de cumplimiento de Microsoft y configurar pruebas automatizadas de acciones. Administrar el historial de usuarios y filtrar la vista de panel.
ms.openlocfilehash: e130fc3438fc8b4674b752e25fc473ee0dd55ae4
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870915"
---
# <a name="get-started-with-compliance-manager"></a>Introducción al Administrador de cumplimiento

**En este artículo:** Este artículo le ayuda a configurar el Administrador de cumplimiento. Obtenga información sobre cómo obtener **acceso al** Administrador de cumplimiento, establecer roles y permisos, y configurar **pruebas automáticas** **de acciones de mejora.** Pase por **el panel del Administrador** de cumplimiento y comprenda las páginas principales: la página de acciones de mejora, la página de soluciones, la página de evaluaciones y la página de plantillas de evaluación.

## <a name="who-can-access-compliance-manager"></a>Quién puede acceder al Administrador de cumplimiento

El Administrador de cumplimiento está disponible para las organizaciones con licencias de Office 365 y Microsoft 365, y para los clientes de Us Government Community Cloud (GCC) Moderate y GCC High. La disponibilidad de evaluación y las capacidades de administración dependen del contrato de licencia.  [Ver detalles de descripción del servicio.](https://go.microsoft.com/fwlink/?linkid=2132371)

## <a name="before-you-begin"></a>Antes de empezar

Es probable que el administrador global de Microsoft 365 de su organización sea el primer usuario en tener acceso al Administrador de cumplimiento. Se recomienda que el administrador global inicie sesión y establezca los permisos de usuario como se indica a continuación al visitar el Administrador de cumplimiento por primera vez.

## <a name="sign-in"></a>Iniciar sesión

1. Vaya al Centro [de cumplimiento de Microsoft 365](https://compliance.microsoft.com/) e inicie **sesión** con su cuenta de administrador global de Microsoft 365.
2. Seleccione **El Administrador de cumplimiento en** el panel de navegación izquierdo. Llegará al panel del Administrador [de cumplimiento.](#understand-the-compliance-manager-dashboard)

El vínculo directo para acceder al Administrador de cumplimiento es [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) .

## <a name="set-user-permissions-and-assign-roles"></a>Establecer permisos de usuario y asignar roles

El Administrador de cumplimiento usa un modelo de permisos de control de acceso basado en roles (RBAC). Solo los usuarios a los que se les asigna un rol pueden tener acceso al Administrador de cumplimiento y las acciones permitidas por cada usuario están restringidas por tipo [de función.](#role-types)

### <a name="where-to-set-permissions"></a>Dónde establecer permisos

La persona que tiene el rol de administrador global de su organización puede establecer permisos de usuario para el administrador de COmpliance. Los permisos se pueden establecer en el Centro de seguridad y & cumplimiento de Office 365, así como en Azure Active Directory (Azure AD).

> [!NOTE]
> Los clientes de entornos de us Government Community (GCC) High solo pueden establecer permisos de usuario y roles para el Administrador de cumplimiento en Azure AD. Consulta a continuación las instrucciones de Azure AD y las definiciones de tipo de rol.

Para establecer permisos y asignar roles en el Centro de seguridad y & cumplimiento de Office 365, siga los pasos siguientes:

1. Vaya al Centro de seguridad y & cumplimiento de [Office 365](https://protection.office.com/) y seleccione **Permisos** en el panel de navegación izquierdo.

2. Busque el grupo de roles al que desea agregar uno o más usuarios y active la casilla a la izquierda del nombre del grupo. (Vea la lista [de roles y funciones relacionadas a continuación.](#role-types) Los nombres de los grupos de roles imitan el nombre del rol).

3. En el panel desplegable de ese grupo, seleccione **Editar en** el **encabezado** Miembros.

4. Seleccione **Elegir miembros.** Aparecerá otra ventana emergente.

5. Seleccione **+ Agregar** para elegir uno o más usuarios para agregar al grupo.

6. Seleccione la casilla situada junto a los nombres que desea agregar y, a continuación, seleccione el botón **Agregar** en la parte inferior.

7. Cuando haya terminado de asignar usuarios, seleccione **Listo** y, a continuación, seleccione **Guardar** y, a continuación, **Cerrar.**

##### <a name="more-about-the-office-365-security--compliance-center"></a>Más información sobre el Centro de seguridad y cumplimiento & Office 365

Obtenga más información sobre los permisos en el Centro de seguridad & [cumplimiento de Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

Si no tiene acceso al Centro de seguridad y cumplimiento de Office 365, o si necesita tener acceso a la versión clásica del Administrador de cumplimiento en el Portal de confianza de servicios de Microsoft, la configuración de administración en el Portal de confianza de servicios proporciona otra forma de asignar roles[(ver](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users)instrucciones). Tenga en cuenta que estos roles son más limitados en su funcionalidad.

##### <a name="more-about-azure-ad"></a>Más información sobre Azure AD

Para asignar roles y establecer permisos en Azure AD, vea Asignar roles de administrador y no administrador a usuarios [con Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

Los usuarios con identidades de Azure AD que no tengan suscripciones a Office 365 o Microsoft 365 no podrán acceder al Administrador de cumplimiento en el Centro de cumplimiento de Microsoft 365. Para obtener ayuda para obtener acceso al Administrador de cumplimiento, póngase en [contacto cmresearch@microsoft.com](mailto:cmresearch@microsoft.com).

### <a name="role-types"></a>Tipos de roles

En la tabla siguiente se muestran las funciones permitidas por cada rol en el Administrador de cumplimiento. La tabla también muestra cómo cada rol [de Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) se asigna a los roles del Administrador de cumplimiento. Los usuarios necesitarán al menos el rol de lector administrador de cumplimiento o el rol de lector global de Azure AD para acceder al Administrador de cumplimiento.


| El usuario puede: | Rol Administrador de cumplimiento | Rol de Azure AD | 
| :------------- | :-------------: | :------------: |
| **Leer pero no editar datos**| Lector de Administrador de cumplimiento  | Lector global de Azure AD, lector de seguridad | 
| **Editar datos**| Contribución del Administrador de cumplimiento | Administrador de cumplimiento | 
| **Editar los resultados de las pruebas**| Evaluación del Administrador de cumplimiento | Administrador de cumplimiento | 
| **Administrar evaluaciones y datos de plantillas e inquilinos**| Administración del Administrador de cumplimiento | Administrador de cumplimiento, administrador de datos de cumplimiento, administrador de seguridad  | 
| **Asignar usuarios**| Administrador global | Administrador global | 

## <a name="settings-for-automated-testing-and-user-history"></a>Configuración de pruebas automatizadas e historial de usuarios

La configuración del Administrador de cumplimiento en el Centro de cumplimiento de Microsoft 365 le permite habilitar y deshabilitar las pruebas automáticas de acciones de mejora. La configuración también le permite administrar los datos de los usuarios asociados a acciones de mejora, incluida la capacidad de reasignar acciones de mejora a un usuario diferente.  Solo las personas con un rol de administrador global o administrador del Administrador de cumplimiento pueden acceder a la configuración del Administrador de cumplimiento.

> [!NOTE]
> La característica de prueba automatizada no está disponible para los clientes en entornos GCC High porque puntuación segura no está disponible en estos entornos. Los clientes de GCC High tendrán que implementar y probar manualmente sus acciones de mejora.

### <a name="set-up-automated-testing"></a>Configurar pruebas automatizadas

Algunas acciones de mejora en el Administrador de cumplimiento también se supervisan mediante [la puntuación de seguridad de Microsoft.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) Puede configurar pruebas automatizadas de acciones que se supervisan conjuntamente, lo que significa que cuando una acción se prueba y actualiza en puntuación segura, esos resultados se sincronizan con las mismas acciones en el Administrador de cumplimiento y cuentan para su puntuación de cumplimiento.

Las pruebas automáticas están activadas de forma predeterminada para las organizaciones nuevas en el Administrador de cumplimiento. Cuando implementa Microsoft 365 u Office 365 por primera vez, la puntuación de seguridad tarda aproximadamente siete días en recopilar completamente los datos y factor guardarlos en la puntuación de cumplimiento.  Cuando las pruebas automatizadas están activadas, la fecha de prueba de la acción no se actualizará, pero su estado de prueba se actualizará. Cuando se crean nuevas evaluaciones, las puntuaciones incluyen automáticamente las puntuaciones de control de Microsoft y la integración de puntuación segura.

El administrador global de su organización puede cambiar la configuración de las pruebas automatizadas en cualquier momento. Puedes desactivar las pruebas automatizadas para acciones de mejora comunes o activarla para acciones individuales. Siga las instrucciones siguientes para cambiar la configuración de las pruebas automatizadas.

#### <a name="to-manage-your-automated-testing-settings"></a>Para administrar la configuración de prueba automatizada:

1. Seleccione **Configuración en** el panel de navegación izquierdo desde cualquier lugar del Centro de cumplimiento de Microsoft [365.](https://compliance.microsoft.com/)

2. En la página de configuración, seleccione **Administrador de cumplimiento.**

3. Selecciona **Pruebas automatizadas** en el panel de navegación izquierdo.

4. Selecciona el botón aplicable para activar las pruebas automáticas de todas las acciones de mejora, desactivarla para todas las acciones o activarla mediante una acción individual.

5. Si selecciona Activar **por acción de mejora,** una lista mostrará todas las acciones de mejora disponibles para elegir.  Activa la casilla situada junto a cualquier acción que quieras probar automáticamente.

6. Seleccione **Guardar para** guardar la configuración. Recibirá un mensaje de confirmación en la parte superior de la pantalla en el que se guardará la selección. Si recibe un aviso de error, inténtelo de nuevo.

**Nota:** Solo el administrador global puede activar o desactivar las actualizaciones automáticas de todas las acciones. El administrador del Administrador de cumplimiento puede activar actualizaciones automáticas para acciones individuales, pero no para todas las acciones de forma global.

### <a name="manage-user-history"></a>Administrar el historial de usuarios

La **configuración Administrar el historial** de usuarios le ayuda a identificar rápidamente qué usuarios han trabajado con acciones de mejora en el Administrador de cumplimiento. Los datos de usuario identificables asociados con acciones de mejora incluyen cualquier trabajo de implementación y prueba realizado, los documentos que cargaron y las notas que introdujeron. Comprender y recuperar este tipo de datos puede ser necesario para las necesidades de cumplimiento de su organización.

La configuración del historial de usuarios también le permite reasignar todas las acciones de mejora de un usuario a otro.

**Para encontrar la configuración del historial de usuarios:**

1. Seleccione Configuración en el panel de navegación izquierdo desde cualquier lugar del Centro [de cumplimiento de Microsoft 365.](https://compliance.microsoft.com/)

2. En la página de configuración, seleccione **Administrador de cumplimiento.**

3. Seleccione **Administrar el historial de usuarios** en el panel de navegación izquierdo.

La **página administrar el historial de** usuarios muestra una lista de todos los usuarios por dirección de correo electrónico que están asignados a una acción de mejora. Use el **botón** Buscar para buscar rápidamente un usuario específico escribiendo en su dirección de correo electrónico.

A la derecha de la dirección  de correo electrónico de cada usuario, el menú desplegable Seleccionar proporciona opciones para exportar un informe, reasignar acciones de mejora o eliminar el historial. Consulta cada sección a continuación para obtener más información sobre cada opción.

#### <a name="export-a-report-of-user-history-data"></a>Exportar un informe de datos de historial de usuarios

Puede exportar un archivo de Excel que contenga una lista de acciones de mejora asignadas actualmente a un usuario.  El informe también enumera los archivos de evidencia cargados por ese usuario. Esta información puede ayudarle a reasignar acciones de mejora abiertas.

El informe refleja el estado de la acción de mejora en la fecha de creación. No es un informe histórico de todos los cambios anteriores en su estado o asignación (aprenda a exportar un informe desde la página de acciones [de mejora).](compliance-manager-improvement-actions.md#export-a-report)

**Siga los pasos siguientes para exportar un informe por usuario:**

1. Seleccione **Configuración en** el panel de navegación izquierdo desde cualquier lugar del Centro de cumplimiento de Microsoft [365.](https://compliance.microsoft.com/)

2. En la página de configuración, seleccione **Administrador de cumplimiento.**

3. Seleccione **Administrar el historial de usuarios** en la navegación de la izquierda.

4. Busque el usuario deseado buscando en las direcciones de correo electrónico de la lista o **seleccionando Buscar** y especificando la dirección de correo electrónico del usuario.

5. En el **menú** desplegable Seleccionar, elija **Exportar informe.**

6. Una vez generado el archivo de Excel del informe, puede abrirlo y guardarlo en el equipo local.

#### <a name="reassign-improvement-actions-to-another-user"></a>Reasignar acciones de mejora a otro usuario

Puede reasignar acciones de mejora de un usuario a otro. Al reasignar una acción, el historial de carga de documentos no cambia, pero el nombre del usuario que cartó originalmente la documentación ya no aparece dentro de la acción de mejora.

**Siga los pasos siguientes para reasignar acciones de mejora a otro usuario:**

1. Seleccione **Configuración en** el panel de navegación izquierdo desde cualquier lugar del Centro de cumplimiento de Microsoft [365.](https://compliance.microsoft.com/)

2. En la página de configuración, seleccione **Administrador de cumplimiento.**

3. Seleccione **Administrar el historial de usuarios** en la navegación de la izquierda.

4. Busque un usuario buscando en las direcciones de correo electrónico de la lista o **seleccionando Buscar** y especificando la dirección de correo electrónico del usuario.

5. En el **menú desplegable** Seleccionar, elija **Reasignar acciones de mejora.** Aparecerá **el panel desplegable Reasignar** acciones de mejora.

6. En el **campo Buscar usuarios,** escriba el nombre o la dirección de correo electrónico del usuario al que desea asignar las acciones de *mejora.*

7. Cuando vea el nombre de su usuario previsto en Acciones de mejora se asignará **a**, seleccione el usuario y, a continuación, seleccione **Asignar acciones.**

8. Una vez completada la reasignación, verá un mensaje de confirmación en el panel desplegable que confirma que todas las acciones de mejora del usuario anterior se han reasignado al nuevo usuario. Si recibe un aviso de error de reasignación, cierre la ventana e inténtelo de nuevo. Para cerrar el panel desplegable, seleccione **Listo**.

El nuevo usuario al que se asigna recibe un correo electrónico que se le ha asignado para una acción de mejora. El correo electrónico contiene un vínculo directo a la página de detalles de la acción de mejora.
 
 > [!NOTE]
> Si reasigna una acción que tiene una actualización pendiente, el vínculo directo a la acción en el correo electrónico de reasignación se interrumpirá si la actualización se acepta después de reasignación. Para corregir esto, vuelve a asignar la acción al usuario después de aceptar la actualización. Obtenga más información sobre [las actualizaciones de las acciones de mejora.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)

#### <a name="delete-user-history"></a>Eliminar historial de usuarios

Al eliminar el historial de un usuario, se quitarán como propietarios de las acciones de mejora y se quitará su nombre de todos los demás campos del Administrador de cumplimiento. Al eliminar el historial de un usuario, las acciones  de mejora que poseen no mostrarán un valor Asignado a hasta que se asigne un nuevo usuario. Los documentos cargados en la acción de mejora mostrarán el usuario **quitado** en lugar del nombre del usuario eliminado. La eliminación del historial de usuarios es permanente.

Para eliminar el historial de un usuario, siga los pasos siguientes:

1. Seleccione **Configuración en** el panel de navegación izquierdo desde cualquier lugar del Centro de cumplimiento de Microsoft [365.](https://compliance.microsoft.com/)

2. En la página de configuración, seleccione **Administrador de cumplimiento.**

3. Seleccione **Administrar el historial de usuarios** en la navegación de la izquierda.

4. Busque un usuario buscando en las direcciones de correo electrónico de la lista o **seleccionando Buscar** y especificando la dirección de correo electrónico del usuario.

5. En el **menú** desplegable Seleccionar, elija **Eliminar historial.**

6. Aparece una ventana que le pide que confirme la eliminación permanente del historial del usuario. Para continuar con la eliminación, seleccione **Eliminar historial.** Para salir sin eliminar el historial, seleccione **Cancelar**.

7. Volverá a la página  Administrar historial de usuarios con un mensaje de confirmación en la parte superior que indica que se eliminó el historial del usuario.

## <a name="understand-the-compliance-manager-dashboard"></a>Información sobre el panel del Administrador de cumplimiento

El panel del Administrador de cumplimiento está diseñado para proporcionarle una vista rápida de su posición de cumplimiento actual.

![Administrador de cumplimiento: panel](../media/compliance-manager-dashboard.png "Panel del Administrador de cumplimiento")

### <a name="overall-compliance-score"></a>Puntuación de cumplimiento general

La puntuación de cumplimiento se destaca en la parte superior. Muestra un porcentaje basado en puntos posibles para completar acciones de mejora que abordan normas y normativas clave de protección de datos. Los puntos [de las acciones de Microsoft,](compliance-manager-assessments.md#microsoft-actions-tab)que son administrados por Microsoft, también se cuentan para su puntuación de cumplimiento.

Cuando llegue al Administrador de cumplimiento por primera vez, la puntuación inicial se basa en la línea base de protección de datos [de Microsoft 365.](compliance-manager-assessments.md#data-protection-baseline-default-assessment) Esta evaluación de línea base, que está disponible para todas las organizaciones, es un conjunto de controles que incluye estándares y normativas comunes del sector. El Administrador de cumplimiento examina las soluciones de Microsoft 365 existentes y le ofrece una evaluación inicial basada en la configuración de privacidad y seguridad actual. A medida que agregue evaluaciones relevantes para su organización, su puntuación será más significativa para usted.

**Obtenga más información: Comprenda** [cómo se calcula la puntuación de cumplimiento.](compliance-score-calculation.md)

### <a name="key-improvement-actions"></a>Acciones de mejora clave

En esta sección se enumeran las principales acciones de mejora que puede realizar en este momento para lograr el mayor impacto positivo en la puntuación de cumplimiento general. Seleccione **Ver todas las acciones de mejora** para ir a la página de acciones de mejora.

### <a name="solutions-that-affect-your-score"></a>Soluciones que afectan a la puntuación

En esta sección se destacan las soluciones que contienen acciones de mejora que pueden afectar positivamente a su puntuación y el número de acciones de mejora pendientes en esas soluciones. Seleccione **Ver todas las soluciones** para visitar la página de soluciones.

### <a name="compliance-score-breakdown"></a>Desglose de la puntuación de cumplimiento

En esta sección se ofrece una vista más detallada de la puntuación de dos maneras diferentes:

- **Categorías:** muestra el porcentaje de la puntuación general dentro de las categorías de protección de datos, como "proteger la información" o "administrar dispositivos".
- **Evaluaciones:** muestra el porcentaje de su progreso en la administración de evaluaciones para normas, normativas o leyes de cumplimiento y protección de datos particulares, como RGPD o NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtrar la vista de panel

Puede filtrar la vista de panel para ver solo los elementos relacionados con normativas y estándares concretos, soluciones, tipo de acción, grupos de evaluación o categorías de protección de datos. Filtrar la vista de esta forma también filtrará la puntuación en el panel, mostrando cuántos puntos ha logrado del total de puntos posibles en función de los criterios de filtro.

Para aplicar filtros:

1. Seleccione **Filtro** en la parte superior derecha del panel.
2. Seleccione los criterios de filtro en **el** panel desplegable Filtros y, a continuación, **seleccione Aplicar**.

Después de aplicar un filtro, verás que la puntuación se ajusta en tiempo real. El porcentaje de puntuación de cumplimiento y la información detallada, así como las acciones y soluciones de mejora, ahora solo pertenecen a los datos cubiertos por los criterios de filtro. Si sale del Administrador de cumplimiento, la vista filtrada permanece cuando vuelve a iniciar sesión.

Para quitar filtros:

- En el **encabezado Filtros aplicados** encima de la puntuación de cumplimiento, seleccione la **X** junto al filtro individual que desea quitar; o
- Seleccione **Filtro** en la parte superior derecha del  panel y, a continuación, en el panel desplegable Filtros, **seleccione Borrar filtros.**

## <a name="improvement-actions-page"></a>Página de acciones de mejora

[Las acciones de](compliance-manager-improvement-actions.md) mejora son acciones administradas por la organización. Trabajar con acciones de mejora ayuda a centralizar las actividades de cumplimiento y a alinearse con las normas y normativas de protección de datos. Cada acción de mejora ofrece instrucciones detalladas de implementación y un vínculo para iniciarlo en la solución adecuada. Las acciones de mejora se pueden asignar a los usuarios de la organización para realizar el trabajo de implementación y pruebas. También puede almacenar documentación, notas y registrar actualizaciones de estado dentro de la acción de mejora.

### <a name="view-your-improvement-actions"></a>Ver las acciones de mejora

El panel del Administrador de cumplimiento muestra las **acciones de mejora clave.** Para ver todas las acciones de mejora, seleccione la pestaña Acciones de mejora en el panel, que le lleva a la página de acciones de mejora. También puedes seleccionar Ver todas las acciones de mejora debajo de la lista de acciones de mejora clave en el panel para acceder a la página de acciones de mejora.

La página de acciones de mejora muestra todas las acciones de mejora que administra la organización. Las acciones administradas por Microsoft se pueden ver en cada evaluación (obtenga más información sobre [las acciones de Microsoft).](compliance-manager-assessments.md#microsoft-actions-tab)

Si tiene una larga lista de acciones en la página de acciones de mejora, puede resultar útil filtrar la vista. Seleccione **Filtro** en la esquina superior derecha de la lista de acciones. Cuando aparezca **el panel** desplegable Filtros, seleccione los criterios según normativas y estándares, soluciones y grupos. También puede personalizar la vista seleccionando **Grupo** en la esquina superior derecha. En el menú desplegable, seleccione para ver por grupo, solución, categoría, tipo de acción o estado.

La vista predeterminada de esta página no muestra acciones de mejora con el estado de prueba **Pasado.** Para ver las acciones que han superado las pruebas, active la casilla **Pasado** en el panel desplegable Filtros. Solo las acciones con un estado de prueba de **Pasado** cuentan para tu puntuación. Algunas acciones pueden mostrar una **etiqueta de actualización pendiente.** Obtenga más información sobre [las actualizaciones de las acciones de mejora.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)

La página de acciones de mejora muestra los siguientes puntos de datos para cada acción de mejora:

- **Puntos logrados:** el número de puntos obtenidos del total disponible al completar la acción
- **Normativas:** normativas o estándares relativos a la acción
- **Grupo:** el grupo al que asignó la acción
- **Soluciones:** la solución a la que puede ir para realizar la acción
- **Evaluaciones:** las evaluaciones que contienen la acción
- **Categorías:** categoría de protección de datos relacionada (por ejemplo, proteger la información, administrar dispositivos, etc.)
- **Estado de la prueba:**
    - **Ninguno:** no se registró ninguna actualización de estado
    - **No evaluado:** las pruebas no se han iniciado
    - **Pasado:** implementación probada correctamente
    - **Error de bajo riesgo:** error en las pruebas, bajo riesgo
    - **Riesgo medio con error:** error en las pruebas, riesgo medio
    - **Alto riesgo fallido:** error en las pruebas, alto riesgo
    - **Fuera del ámbito:** la acción no está en el ámbito de la evaluación y no afecta a la puntuación
    - **Para ser detectado:** para la prueba manual, indica que se ha implementado una acción pero no se ha probado; para la prueba automatizada, indica que una acción está esperando el resultado de automatización
    - **No se pudo detectar:** no se puede determinar el estado automatizado
    - **Parcialmente probado:** puntuación automatizada que otorga puntos parciales

**Obtenga más información:** [Vea cómo asignar y realizar el trabajo en acciones de mejora.](compliance-manager-improvement-actions.md)

## <a name="solutions-page"></a>Página soluciones

La página de soluciones muestra el recurso compartido de puntos ganados y posibles organizados por solución. Ver los puntos restantes y las acciones de mejora desde esta vista le ayuda a comprender qué soluciones necesitan una atención más inmediata.

Busque la página soluciones seleccionando la **pestaña Soluciones** en el panel del Administrador de cumplimiento. También puedes seleccionar Ver todas **las soluciones debajo** de **Soluciones que afectan a tu puntuación** en la sección superior derecha del panel.

### <a name="filtering-your-solutions-view"></a>Filtrar la vista de soluciones

Para filtrar la vista de soluciones:

1. Seleccione **Filtro** en la esquina superior izquierda de la lista de evaluaciones.
2. En el **panel** desplegable Filtros, coloque una comprobación junto a los criterios deseados (estándares y normativas, solución, tipo de acción, grupo administrador de cumplimiento, categoría).
3. Seleccione el **botón** Aplicar. El panel de filtro se cerrará y verá la vista filtrada.

También puede modificar la vista para ver las evaluaciones por grupo, producto o  reglamento seleccionando el tipo de agrupación en el menú desplegable Grupo encima de la lista de evaluaciones.

### <a name="taking-action-from-the-solution-page"></a>Tomar medidas desde la página de solución

La página de soluciones muestra las soluciones de su organización que están conectadas a acciones de mejora. La tabla enumera la contribución de cada solución a la puntuación general, los puntos logrados y posibles dentro de esa solución y el número restante de acciones de mejora agrupadas en esa solución que pueden aumentar la puntuación.

Hay dos formas de tomar medidas desde esta pantalla:

1. En la fila de la solución prevista, en **la** columna Acciones restantes, seleccione el número de hipervínculo. Verá una vista filtrada de la pantalla de acciones de mejora que muestra las acciones de mejora no probados para esa solución.

2. En la fila de la solución prevista, en la columna Abrir **solución,** seleccione **Abrir**. Verá la solución o ubicación en los centros de seguridad y cumplimiento de Microsoft 365 y Office 365, donde puede realizar la acción recomendada.

## <a name="assessments-page"></a>Página evaluaciones

En la página de evaluaciones se [enumeran](compliance-manager-assessments.md) todas las evaluaciones que ha configurado para su organización. El denominador de puntuación de cumplimiento viene determinado por todas las evaluaciones de seguimiento. A medida que agregue más evaluaciones, verá más acciones de mejora en la página de acciones de mejora y el denominador de puntuación de cumplimiento aumenta.

La página de evaluaciones resume la información clave sobre cada evaluación:

- **Evaluación:** nombre de la evaluación
- **Estado:**
    - **Completado:** todos los controles tienen el estado "pasado" o se pasa al menos uno y el resto están "fuera del ámbito"
    - **Incompleto:** al menos un control tiene el estado "failed"
    - **Ninguno:** no se han probado todos los controles
    - **En curso:** las acciones de mejora tienen cualquier otro estado, incluido "en curso", "crédito parcial" o "no detectado
- **Progreso de la** evaluación: porcentaje del trabajo realizado hacia la finalización, medido por el número de controles probados correctamente
- **Las acciones de mejora:** el número de acciones completadas para satisfacer la implementación de los controles
- **Acciones de Microsoft:** número de acciones completadas para satisfacer la implementación de los controles de Microsoft
- **Grupo:** nombre del grupo al que pertenece la evaluación
- **Producto:** servicio asociado de Microsoft 365
- **Reglamento:** la norma, directiva o ley reglamentaria que se aplica a la evaluación

### <a name="filtering-your-assessments-view"></a>Filtrar la vista de evaluaciones

Para filtrar la vista de evaluaciones:

1. Seleccione **Filtro** en la esquina superior izquierda de la lista de evaluaciones.
2. En el **panel** desplegable Filtros, compruebe los criterios que desee.
3. Seleccione el **botón** Aplicar. El panel de filtro se cerrará y verá la vista filtrada.

También puede modificar la vista para ver las evaluaciones por grupo, producto o  reglamento seleccionando el tipo de agrupación en el menú desplegable Grupo encima de la lista de evaluaciones.

### <a name="default-assessment"></a>Evaluación predeterminada

De forma predeterminada, verá la evaluación [de](compliance-manager-assessments.md#data-protection-baseline-default-assessment) línea base de protección de datos en la página de evaluaciones. El Administrador de cumplimiento también proporciona varias plantillas [predefinidas para](compliance-manager-templates-list.md) crear evaluaciones.

## <a name="assessment-templates-page"></a>Página de plantillas de evaluación

Una plantilla es un marco para crear una evaluación en el Administrador de cumplimiento. La página de plantillas de evaluación muestra una lista de plantillas y detalles clave. La lista incluye plantillas proporcionadas por el Administrador de cumplimiento, así como cualquier plantilla que la organización haya modificado o creado. Puede aplicar filtros para buscar una plantilla basada en la certificación, el ámbito del producto, el país, la industria y quién la creó.

Seleccione una plantilla de su fila para mostrar su página de detalles, que contiene una descripción de la plantilla y más información sobre la certificación, el ámbito y los detalles de los controles. En esta página puede seleccionar los botones adecuados para crear una evaluación, exportar los datos de plantilla a Excel o modificar la plantilla.

**Obtenga más información:** [obtenga información sobre cómo trabajar con plantillas de evaluación.](compliance-manager-templates.md)

## <a name="next-step"></a>Paso siguiente
Personalice el Administrador de cumplimiento [configurando evaluaciones.](compliance-manager-assessments.md)
