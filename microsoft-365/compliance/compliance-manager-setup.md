---
title: Introducción al Administrador de cumplimiento de Microsoft Purview
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
description: Establezca los roles y permisos de usuario del Administrador de cumplimiento de Microsoft Purview y configure pruebas automatizadas de acciones. Administre el historial de usuarios y filtre la vista del panel.
ms.openlocfilehash: 940396ad6334e646a37a359f4ed73345056f51ef
ms.sourcegitcommit: 06b81b66f13774102bb34556479c1ff890011afb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "67357464"
---
# <a name="get-started-with-compliance-manager"></a>Introducción al Administrador de cumplimiento

**En este artículo:** Este artículo le ayuda a configurar el Administrador de cumplimiento. Obtenga información sobre cómo **acceder** al Administrador de cumplimiento, **establecer roles y permisos** y configurar **pruebas automáticas de acciones de mejora**. Recorra el **panel del Administrador de cumplimiento** y comprenda las páginas principales: la página de acciones de mejora, la página de soluciones, la página de evaluaciones y la página de plantillas de evaluación.

## <a name="who-can-access-compliance-manager"></a>Quién puede acceder al Administrador de cumplimiento

El Administrador de cumplimiento está disponible para las organizaciones con licencias de Office 365 y Microsoft 365, y para los clientes moderados, altos de GCC y del Departamento de Defensa (DoD) de la Comunidad de Gobierno de EE. UU. (GCC). La disponibilidad de la evaluación y las funcionalidades de administración dependen del contrato de licencia.  [Ver los detalles de la descripción del servicio](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-compliance-manager).

## <a name="before-you-begin"></a>Antes de empezar

Es probable que el administrador global de Microsoft 365 para su organización sea el primer usuario en acceder al Administrador de cumplimiento. Se recomienda que el administrador global inicie sesión y establezca los permisos de usuario como se describe a continuación al visitar el Administrador de cumplimiento por primera vez.

## <a name="sign-in"></a>Iniciar sesión

1. Vaya a la <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a> e **inicie sesión** con su cuenta de administrador global de Microsoft 365.
2. Seleccione **Administrador de cumplimiento** en el panel de navegación izquierdo. Llegará al [panel del Administrador de cumplimiento](#understand-the-compliance-manager-dashboard).

El vínculo directo para acceder al Administrador de cumplimiento es [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager).

## <a name="set-user-permissions-and-assign-roles"></a>Establecimiento de permisos de usuario y asignación de roles

El Administrador de cumplimiento usa un modelo de permisos de control de acceso basado en rol (RBAC). Solo los usuarios a los que se les asigna un rol pueden acceder al Administrador de cumplimiento y las acciones permitidas por cada usuario están restringidas por [tipo de rol](#role-types).

### <a name="where-to-set-permissions"></a>Dónde establecer permisos

La persona que tiene el rol de administrador global para su organización puede establecer permisos de usuario para el Administrador de cumplimiento. Los permisos se pueden establecer en el portal de cumplimiento Microsoft Purview, así como en Azure Active Directory (Azure AD).

> [!NOTE]
> Los clientes de los entornos de alta y departamento de defensa (DoD) de la Comunidad gubernamental de EE. UU. (GCC) solo pueden establecer permisos y roles de usuario para el Administrador de cumplimiento en Azure AD. Consulte a continuación las instrucciones de Azure AD y las definiciones de tipo de rol.

Para establecer permisos y asignar roles en el portal de cumplimiento Microsoft Purview, siga estos pasos:

1. Vaya al portal de cumplimiento Microsoft Purview y seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">**Permisos**</a>.

2. En la lista desplegable del portal de cumplimiento, seleccione **Roles**.

3. Busque el grupo de roles al que desea agregar uno o varios usuarios y active la casilla situada a la izquierda del nombre del grupo. (Consulte la [lista de roles y funciones relacionadas a continuación](#role-types). Los nombres del grupo de roles imitan el nombre del rol).

4. En el panel flotante de ese grupo, seleccione **Editar** en el encabezado **Miembros** .

5. Seleccione **Elegir miembros**. Aparecerá otra ventana flotante.

6. Seleccione **+ Agregar** para elegir uno o varios usuarios para agregar al grupo.

7. Seleccione la casilla situada junto a los nombres que desea agregar y, a continuación, seleccione el botón **Agregar** en la parte inferior.

8. Cuando haya terminado de asignar usuarios, seleccione **Listo**, **Guardar y** **Cerrar**.

#### <a name="more-about-azure-ad"></a>Más información sobre Azure AD

Para asignar roles y establecer permisos en Azure AD, consulte [Asignación de roles de administrador y no administrador a usuarios con Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

Los usuarios con identidades de Azure AD que no tengan suscripciones de Office 365 o Microsoft 365 no podrán acceder al Administrador de cumplimiento en el portal de cumplimiento Microsoft Purview. Para obtener ayuda para acceder al Administrador de cumplimiento, póngase en contacto con [cmresearch@microsoft.com](mailto:cmresearch@microsoft.com).

### <a name="role-types"></a>Tipos de rol

En la tabla siguiente se muestran las funciones permitidas por cada rol en el Administrador de cumplimiento. En la tabla también se muestra cómo se asigna cada [rol de Azure AD](/azure/active-directory/roles/permissions-reference) a los roles del Administrador de cumplimiento. Los usuarios necesitarán al menos el rol de lector del Administrador de cumplimiento, o rol de lector global de Azure AD, para acceder al Administrador de cumplimiento.

| El usuario puede: | Rol administrador de cumplimiento | Rol de Azure AD | 
| :------------- | :-------------: | :------------: |
| **Leer pero no editar datos**| Lector de Administrador de cumplimiento  | Lector global de Azure AD, lector de seguridad |
| **Editar datos**| Contribución del administrador de cumplimiento | Administrador de cumplimiento |
| **Edición de los resultados de las pruebas**| Evaluador de Administrador de cumplimiento | Administrador de cumplimiento |
| **Administrar evaluaciones, plantillas y datos de inquilino; asignar acciones de mejora**| Administración del administrador de cumplimiento | Administrador de cumplimiento, Administrador de datos de cumplimiento, Administrador de seguridad  |

## <a name="start-a-premium-assessments-trial"></a>Inicio de una evaluación premium

La evaluación premium del Administrador de cumplimiento es una excelente manera de configurar rápidamente las evaluaciones que son más relevantes para su organización. Nuestra biblioteca de más de 300 plantillas se corresponde con las regulaciones gubernamentales y los estándares del sector en todo el mundo.
Obtenga más información sobre la [evaluación premium](compliance-easy-trials-compliance-manager-assessments.md).

Puede iniciar la evaluación directamente desde el Administrador de cumplimiento y configurar las evaluaciones recomendadas siguiendo estos pasos:

1. En la página **Información general** del Administrador de cumplimiento, seleccione **Iniciar prueba**. Escribirá un asistente de activación de prueba que hará preguntas para ayudarnos a recomendar evaluaciones para su organización.

2. En la página **Activar evaluación** , seleccione **Siguiente** para comenzar la evaluación gratuita de las evaluaciones premium de 90 días y continuar con la creación de evaluaciones.

3. Seleccione uno o varios sectores que identifiquen su organización y, a continuación, seleccione **Siguiente**.

4. Seleccione una o varias regiones para la ubicación de la organización y, a continuación, seleccione **Siguiente**.

5. En la pantalla **Elegir evaluaciones** , seleccione la flecha desplegable situada junto a **Plantillas recomendadas** para ver la lista de evaluaciones que creemos que se aplican a su organización. Active las casillas situadas junto a las plantillas que desea usar para crear evaluaciones y, a continuación, seleccione **Siguiente**.

6. Revise las selecciones finales y seleccione **Agregar evaluaciones recomendadas** para crear las nuevas evaluaciones.

Para obtener más información sobre cómo empezar a trabajar con las evaluaciones, visite la [sección de la página Evaluaciones](#assessments-page) a continuación.

## <a name="settings-for-automated-testing-and-user-history"></a>Configuración de pruebas automatizadas e historial de usuarios

La configuración del Administrador de cumplimiento de la portal de cumplimiento Microsoft Purview le permite habilitar y deshabilitar las pruebas automáticas de las acciones de mejora. La configuración también le permite administrar los datos de los usuarios asociados a acciones de mejora, incluida la capacidad de reasignar acciones de mejora a otro usuario.  Solo las personas con un rol de administrador global o administrador de administrador de cumplimiento pueden acceder a la configuración del Administrador de cumplimiento.

> [!NOTE]
> La característica de pruebas automatizadas no está disponible para los clientes en entornos GCC High y DoD porque La puntuación segura no está disponible en estos entornos. Los clientes de GCC High y DoD tendrán que implementar y probar manualmente sus acciones de mejora.

### <a name="set-up-automated-testing"></a>Configuración de pruebas automatizadas

El Administrador de cumplimiento detecta señales de otras soluciones de Microsoft Purview a las que su organización puede suscribirse, incluida la administración del ciclo de vida de los datos, la protección de la información, la Prevención de pérdida de datos de Microsoft Purview, el cumplimiento de las comunicaciones y la administración de riesgos internos. El Administrador de cumplimiento también detecta señales de acciones de mejora complementarias supervisadas por [Puntuación de seguridad de Microsoft](../security/defender/microsoft-secure-score.md).

Con estas señales, el Administrador de cumplimiento puede probar automáticamente determinadas acciones de mejora, lo que ayuda a maximizar la eficacia en las actividades de cumplimiento. Cuando una acción de mejora se prueba e implementa correctamente, recibe la cantidad completa de puntos, que se [acreditan en la puntuación de cumplimiento general](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls).

**Las pruebas automáticas están activadas de forma predeterminada para las organizaciones que no están en el Administrador de cumplimiento.** La primera vez que implemente Microsoft 365 o Office 365, se tarda aproximadamente siete días en recopilar datos por completo y factorizarlos en la puntuación de cumplimiento. Cuando se activa la prueba automatizada, la fecha de prueba de la acción no se actualizará, pero se actualizará su estado de prueba. Cuando se crean nuevas evaluaciones, las puntuaciones incluyen automáticamente las puntuaciones de control de Microsoft y la integración de puntuación segura. Consulte [Administración de la configuración de pruebas automatizadas](#manage-automated-testing-settings) a continuación para editar o desactivar esta configuración.

#### <a name="how-to-tell-which-actions-are-tested-automatically"></a>Cómo saber qué acciones se prueban automáticamente

En la página **Acciones de mejora** , busque la columna **De prueba de origen** . Si el valor aparece como **Automático**, el Administrador de cumplimiento probará automáticamente la acción.  Si el valor es **Manual**, la organización probará la acción. Si el valor es **Parent**, la acción hereda el estado de prueba de otra acción a la que está vinculada. Obtenga detalles sobre el [origen de pruebas de acciones de mejora](compliance-manager-improvement-actions.md#update-testing-source).

#### <a name="which-actions-cant-be-tested-automatically"></a>Qué acciones no se pueden probar automáticamente

Las acciones de mejora en plantillas que no tienen como ámbito Microsoft 365 actualmente no son aptas para las pruebas automáticas. Por ejemplo, las plantillas universales o una plantilla para Microsoft Azure o Microsoft Dynamics no tendrán acciones que se puedan probar automáticamente. Obtenga más información sobre [las plantillas de evaluación](compliance-manager-templates.md).

#### <a name="manage-automated-testing-settings"></a>Administración de la configuración de pruebas automatizadas

El administrador global de su organización puede cambiar la configuración de las pruebas automatizadas en cualquier momento. Puede desactivar las pruebas automatizadas para acciones de mejora comunes o activarla para acciones individuales. Siga las instrucciones siguientes para cambiar la configuración de pruebas automatizadas.

1. Seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**Configuración**</a> en el portal de cumplimiento Microsoft Purview.

2. En la página de configuración, seleccione **Administrador de cumplimiento**.

3. Seleccione **Probar origen** en el panel de navegación izquierdo.

4. Seleccione el botón correspondiente para activar las pruebas automáticas de todas las acciones de mejora, desactivarla para todas las acciones o activarla por acción individual.

5. Si selecciona **Activar por acción de mejora**, una lista mostrará todas las acciones de mejora disponibles entre las que elegir.  Active la casilla situada junto a cualquier acción que desee probar automáticamente.

6. Seleccione **Guardar** para guardar la configuración. Recibirá un mensaje de confirmación en la parte superior de la pantalla de que se guardó la selección. Si recibe un aviso de error, inténtelo de nuevo.

> [!NOTE]
> Solo el administrador global puede activar o desactivar las actualizaciones automáticas para todas las acciones. El administrador del administrador de cumplimiento puede activar actualizaciones automáticas para acciones individuales, pero no para todas las acciones globalmente.

### <a name="manage-user-history"></a>Administrar el historial de usuarios

La configuración **Administrar historial de usuarios** le ayuda a identificar rápidamente qué usuarios han trabajado con acciones de mejora en el Administrador de cumplimiento. Los datos de usuario identificables asociados a las acciones de mejora incluyen cualquier trabajo de implementación y pruebas realizado, los documentos que cargaron y las notas que escribieron. Comprender y recuperar este tipo de datos puede ser necesario para las propias necesidades de cumplimiento de su organización.

La configuración del historial de usuarios también le permite reasignar todas las acciones de mejora de un usuario a otro.

**Para buscar la configuración del historial de usuarios:**

1. Seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**Configuración**</a> en el portal de cumplimiento Microsoft Purview.

2. En la página de configuración, seleccione **Administrador de cumplimiento**.

3. Seleccione **Administrar historial de usuarios** en el panel de navegación izquierdo.

En la página **Administrar historial de usuarios** se muestra una lista de todos los usuarios por dirección de correo electrónico que están asignados a una acción de mejora. Use el botón **Buscar** para encontrar rápidamente un usuario específico escribiendo su dirección de correo electrónico.

A la derecha de la dirección de correo electrónico de cada usuario, el menú desplegable **Seleccionar** proporciona opciones para exportar un informe, reasignar acciones de mejora o eliminar el historial. Consulte cada sección siguiente para obtener más información sobre cada opción.

#### <a name="export-a-report-of-user-history-data"></a>Exportación de un informe de datos del historial de usuarios

Puede exportar un archivo de Excel que contenga una lista de acciones de mejora asignadas actualmente a un usuario.  El informe también enumera los archivos de evidencia cargados por ese usuario. Esta información puede ayudarle a reasignar acciones de mejora abiertas.

El informe refleja el estado de la acción de mejora a partir de su fecha de creación. No es un informe histórico de todos los cambios anteriores en su estado o asignación (obtenga información sobre cómo [exportar un informe desde la página de acciones de mejora](compliance-manager-improvement-actions.md#export-a-report)).

**Siga los pasos siguientes para exportar un informe por usuario:**

1. Seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**Configuración**</a> en el portal de cumplimiento Microsoft Purview.

2. En la página de configuración, seleccione **Administrador de cumplimiento**.

3. Seleccione **Administrar historial de usuarios** en el panel de navegación de la izquierda.

4. Busque el usuario deseado buscando en las direcciones de correo electrónico de la lista o seleccionando **Buscar** y escribiendo la dirección de correo electrónico del usuario.

5. En el menú desplegable **Seleccionar** , elija **Exportar informe**.

6. Una vez generado el archivo de Excel del informe, puede abrirlo y guardarlo en el equipo local.

#### <a name="reassign-improvement-actions-to-another-user"></a>Asignar acciones de mejora a otro usuario

Puede reasignar acciones de mejora de un usuario a otro. Al reasignar una acción, el historial de carga del documento no cambia, pero el nombre del usuario que cargó originalmente la documentación ya no aparece dentro de la acción de mejora.

**Siga los pasos siguientes para reasignar las acciones de mejora a otro usuario:**

1. Seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**Configuración**</a> en el portal de cumplimiento Microsoft Purview.

2. En la página de configuración, seleccione **Administrador de cumplimiento**.

3. Seleccione **Administrar historial de usuarios** en el panel de navegación de la izquierda.

4. Busque un usuario mediante la búsqueda en las direcciones de correo electrónico de la lista o seleccione **Buscar** e introduzca la dirección de correo electrónico de ese usuario.

5. En el menú desplegable **Seleccionar** , elija **Reasignar acciones de mejora**. Aparecerá el panel flotante **Reasignar acciones de mejora** .

6. En el campo **Buscar usuarios** , escriba el nombre o la dirección de correo electrónico del usuario al que desea asignar las acciones *de* mejora.

7. Cuando vea el nombre del usuario previsto en Acciones de **mejora,** seleccione el usuario y, a continuación, seleccione **Asignar acciones**.

8. Una vez completada la reasignación, verá un mensaje de confirmación en el panel flotante que confirma que todas las acciones de mejora del usuario anterior se han reasignado al nuevo usuario. Si recibe un aviso de error de reasignación, cierre la ventana e inténtelo de nuevo. Para cerrar el panel flotante, seleccione **Listo**.

El nuevo asignado recibe un correo electrónico que se le ha asignado a una acción de mejora. El correo electrónico contiene un vínculo directo a la página de detalles de la acción de mejora.

 > [!NOTE]
> Si reasigna una acción que tiene una actualización pendiente, el vínculo directo a la acción en el correo electrónico de reasignación se interrumpirá si la actualización se acepta después de la reasignación. Para corregirlo, vuelva a asignar la acción al usuario después de aceptar la actualización. Obtenga más información sobre [las actualizaciones de las acciones de mejora](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).

#### <a name="delete-user-history"></a>Eliminar historial de usuarios

Al eliminar el historial de un usuario, se quitará como propietario de las acciones de mejora y se quitará su nombre de todos los demás campos del Administrador de cumplimiento. Al eliminar el historial de un usuario, las acciones de mejora que poseen no mostrarán un valor **Asignado a** hasta que se asigne un nuevo usuario. Los documentos cargados en la acción de mejora mostrarán **el usuario eliminado** en lugar del nombre del usuario eliminado. La eliminación del historial de usuarios es permanente.

Para eliminar el historial de un usuario, siga estos pasos:

1. Seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**Configuración**</a> en el portal de cumplimiento Microsoft Purview.

2. En la página de configuración, seleccione **Administrador de cumplimiento**.

3. Seleccione **Administrar historial de usuarios** en el panel de navegación de la izquierda.

4. Busque un usuario mediante la búsqueda en las direcciones de correo electrónico de la lista o seleccione **Buscar** e introduzca la dirección de correo electrónico de ese usuario.

5. En el menú desplegable **Seleccionar** , elija **Eliminar historial**.

6. Aparece una ventana que le pide que confirme la eliminación permanente del historial del usuario. Para continuar con la eliminación, seleccione **Eliminar historial**. Para salir sin eliminar el historial, seleccione **Cancelar**.

7. Volverá a la página Administrar historial de **usuarios** con un mensaje de confirmación en la parte superior que indica que se eliminó el historial del usuario.

## <a name="understand-the-compliance-manager-dashboard"></a>Comprender el panel del Administrador de cumplimiento

El panel del Administrador de cumplimiento está diseñado para proporcionar una vista general de la posición de cumplimiento actual.

:::image type="content" alt-text="Panel del Administrador de cumplimiento." source="../media/compliance-manager-dashboard.png" lightbox="../media/compliance-manager-dashboard.png":::

### <a name="overall-compliance-score"></a>Puntuación de cumplimiento global

La puntuación de cumplimiento aparece destacadamente en la parte superior. Muestra un porcentaje en función de los puntos que se puedan lograr para completar las acciones de mejora que abordan los estándares y regulaciones clave de protección de datos. Los puntos de [las acciones de Microsoft](compliance-manager-assessments.md#microsoft-actions-tab), que se administran mi Microsoft, también cuentan para la puntuación de cumplimiento.

Cuando llega al Administrador de cumplimiento por primera vez, la puntuación inicial se basa en la [línea base de protección de datos de Microsoft 365](compliance-manager-assessments.md#data-protection-baseline-default-assessment). Esta evaluación de línea base, que está disponible para todas las organizaciones, es un conjunto de controles que incluye normas y regulaciones comunes del sector. El Administrador de cumplimiento examina las soluciones existentes de Microsoft 365 y le ofrece una evaluación inicial basada en la configuración de privacidad y seguridad actual. A medida que agrega evaluaciones que son relevantes para su organización, la puntuación se vuelve más significativa para usted.

**Más información:** [Comprender cómo se calcula la puntuación de cumplimiento](compliance-score-calculation.md).

### <a name="key-improvement-actions"></a>Acciones de mejora claves

En esta sección se enumeran las principales acciones de mejora que puede realizar ahora mismo para lograr el mayor impacto positivo en la puntuación de cumplimiento general. Seleccione **Ver todas las acciones de mejora** para ir a la página de acciones de mejora.

### <a name="solutions-that-affect-your-score"></a>Soluciones que afectan a su puntuación

En esta sección se resaltan las soluciones que contienen acciones de mejora que pueden afectar positivamente a la puntuación y el número de acciones de mejora pendientes en esas soluciones. Seleccione **Ver todas las soluciones** para visitar la página de soluciones.

### <a name="compliance-score-breakdown"></a>Desglose de puntuación de cumplimiento

En esta sección se proporciona una vista más detallada de la puntuación de dos maneras diferentes:

- **Categorías**: muestra el porcentaje de la puntuación general dentro de las categorías de protección de datos, como "proteger información" o "administrar dispositivos".
- **Evaluaciones**: muestra el porcentaje de su progreso en la administración de evaluaciones para estándares, reglamentos o leyes específicos de cumplimiento y protección de datos, como RGPD o NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtrado de la vista del panel

Puede filtrar la vista del panel para ver solo los elementos relacionados con determinados reglamentos y estándares, soluciones, tipo de acción, grupos de evaluación o categorías de protección de datos. El filtrado de la vista de esta manera también filtrará la puntuación en el panel, mostrando cuántos puntos ha logrado del total de puntos posibles en función de los criterios de filtro.

Para aplicar filtros:

1. Seleccione **Filtrar** en la parte superior derecha del panel.
2. Seleccione los criterios de filtro en el panel flotante **Filtros** y, a continuación, seleccione **Aplicar**.

Después de aplicar un filtro, verá la puntuación ajustada en tiempo real. El porcentaje de puntuación de cumplimiento y la información de desglose, así como las acciones y soluciones de mejora, ahora solo pertenecen a los datos cubiertos por los criterios de filtro. Si cierra la sesión del Administrador de cumplimiento, la vista filtrada permanece al volver a iniciar sesión.

Para quitar filtros:

- En el encabezado **Filtros aplicados** situado encima de la puntuación de cumplimiento, seleccione la **X** junto al filtro individual que desea quitar; O
- Seleccione **Filtrar** en la parte superior derecha del panel y, en el panel flotante **Filtros** , seleccione **Borrar filtros**.

## <a name="improvement-actions-page"></a>Página Acciones de mejora

[Las acciones de mejora](compliance-manager-improvement-actions.md) son acciones administradas por su organización. Trabajar con acciones de mejora ayuda a centralizar las actividades de cumplimiento y a alinearse con las normativas y estándares de protección de datos. Cada acción de mejora proporciona instrucciones de implementación detalladas y un vínculo para iniciarlo en la solución adecuada. Las acciones de mejora se pueden asignar a los usuarios de la organización para realizar el trabajo de implementación y pruebas. También puede almacenar la documentación, las notas y registrar las actualizaciones de estado dentro de la acción de mejora.

### <a name="view-your-improvement-actions"></a>Visualización de las acciones de mejora

El panel del Administrador de cumplimiento muestra las acciones de mejora clave. Para ver todas las acciones de mejora, seleccione la pestaña **Acciones de mejora** en el panel, que le llevará a la página acciones de mejora. También puede seleccionar **Ver todas las acciones de mejora** debajo de la lista de acciones de mejora clave en el panel para ir a la página de acciones de mejora.

La página acciones de mejora muestra todas las acciones de mejora administradas por su organización. Las acciones administradas por Microsoft se pueden ver dentro de cada evaluación (obtenga más información sobre [las acciones de Microsoft](compliance-manager-assessments.md#microsoft-actions-tab)).

Si tiene una larga lista de acciones en la página de acciones de mejora, puede ser útil filtrar la vista. Seleccione **Filtrar** en la esquina superior derecha de la lista de acciones. Cuando aparezca el panel flotante **Filtros** , seleccione los criterios de las opciones disponibles. También puede personalizar la vista seleccionando **Agrupar** en la esquina superior derecha. En el menú desplegable, seleccione para ver por grupo, solución, categoría, tipo de acción o estado.

La vista predeterminada de esta página no muestra acciones de mejora con un estado de prueba de **Pasado**. Para ver las acciones que han pasado las pruebas, active la casilla **Pasado** en el panel flotante Filtros. Solo las acciones con un estado de prueba de **Recuento pasado** para la puntuación. Algunas acciones pueden mostrar una **etiqueta de actualización pendiente.** Obtenga más información sobre [las actualizaciones de las acciones de mejora](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).

La página acciones de mejora muestra los siguientes puntos de datos para cada acción de mejora:

- **Productos**: el producto que se está evaluando.
- **Puntos alcanzados**: el número de puntos obtenidos del total disponible completando la acción
- **Reglamentos**: las regulaciones o estándares relativos a la acción
- **Grupo**: el grupo al que asignó la acción
- **Soluciones**: la solución a la que puede ir para realizar la acción
- **Evaluaciones**: las evaluaciones que contienen la acción
- **Categorías**: la categoría de protección de datos relacionada (por ejemplo, proteger información, administrar dispositivos, etc.)
- **Estado de la prueba**:
  - **Ninguno** : no se registró ninguna actualización de estado
  - **No evaluado** : las pruebas no se han iniciado
  - **Pasado** : implementación probada correctamente
  - **Error de bajo riesgo** : error en las pruebas, bajo riesgo
  - **Riesgo medio fallido** : error en las pruebas, riesgo medio
  - **Alto riesgo fallido** : error en las pruebas, alto riesgo
  - **Fuera del ámbito** : la acción no está en el ámbito de la evaluación y no afecta a la puntuación.
  - **Para ser detectado** : para la prueba manual, indica que se ha implementado una acción pero no se ha probado; para la prueba automatizada, indica que una acción está esperando el resultado de la automatización
  - **No se pudo detectar** : no se puede determinar el estado automatizado.
  - **Parcialmente probado** : puntuación automatizada que concede puntos parciales
- **Tipo de acción**: indica si la acción de mejora es técnica, lo que significa que se puede implementar dentro de una solución o producto, o no técnica, que se implementaría fuera de una solución técnica.
- **Asignado a**: la persona a la que se ha asignado esta acción, si procede
- **Origen de la prueba**: indica si el origen de prueba de la acción es manual, automático o heredado de un elemento primario

**Más información:** [Consulte cómo asignar y realizar trabajos en acciones de mejora](compliance-manager-improvement-actions.md).

## <a name="solutions-page"></a>Página Soluciones

En la página de soluciones se muestra el porcentaje de puntos ganados y potenciales organizados por la solución. Ver los puntos restantes y las acciones de mejora desde esta vista le ayuda a comprender qué soluciones necesitan una atención más inmediata.

Para buscar la página de soluciones, seleccione la pestaña **Soluciones** en el panel del Administrador de cumplimiento. También puede seleccionar **Ver todas las soluciones** **debajo de Soluciones que afectan a la puntuación** en la sección superior derecha del panel.

### <a name="filtering-your-solutions-view"></a>Filtrado de la vista de soluciones

Para filtrar la vista de soluciones:

1. Seleccione **Filtrar** en la esquina superior izquierda de la lista de evaluaciones.
2. En el panel flotante **Filtros** , coloque una comprobación junto a los criterios deseados (reglamentos, soluciones, tipos de acción, grupos, categorías).
3. Seleccione el botón **Aplicar** . El panel de filtro se cerrará y verá la vista filtrada.

También puede modificar la vista para ver las evaluaciones por grupo, producto o reglamento seleccionando el tipo de agrupación en el menú desplegable **Grupo** situado encima de la lista de evaluaciones.

### <a name="taking-action-from-the-solution-page"></a>Realizar acciones desde la página de la solución

En la página soluciones se muestran las soluciones de la organización que están conectadas a acciones de mejora. En la tabla se muestra la contribución de cada solución a la puntuación general, los puntos alcanzados y posibles dentro de esa solución y el número restante de acciones de mejora agrupadas en esa solución que pueden aumentar la puntuación.

Hay dos maneras de realizar acciones desde esta pantalla:

1. En la fila de la solución prevista, en la columna **Acciones restantes** , seleccione el número con hipervínculo. Verá una vista filtrada de la pantalla de acciones de mejora que muestra las acciones de mejora no probadas para esa solución.

2. En la fila de la solución prevista, en la columna **Abrir solución** , seleccione **Abrir**. Verá la solución o ubicación en los centros de seguridad y cumplimiento de Microsoft 365 y Office 365, donde puede realizar la acción recomendada.

## <a name="assessments-page"></a>Página Evaluaciones

En la página evaluaciones se enumeran todas las [evaluaciones](compliance-manager-assessments.md) que configuró para su organización. El denominador de puntuación de cumplimiento viene determinado por todas las evaluaciones de seguimiento. A medida que agregue más evaluaciones, verá más acciones de mejora en la página de acciones de mejora y el denominador de puntuación de cumplimiento aumenta.

El contador **de plantillas activadas** situado cerca de la parte superior de la página muestra el número de plantillas de evaluación activas actualmente en uso del número total de plantillas disponibles para su organización. Consulte [Disponibilidad y licencias de plantillas](compliance-manager-templates.md#template-availability-and-licensing) para obtener más información.

En la página de evaluaciones se resume la información clave sobre cada evaluación:

- **Evaluación**: nombre de la evaluación
- **Estado**:
  - **Completado** : todos los controles tienen el estado "pasado", o al menos uno se pasa y el resto está "fuera del ámbito".
  - **Incompleto** : al menos un control tiene el estado "error".
  - **Ninguno** : no se han probado todos los controles
  - **En curso** : las acciones de mejora tienen cualquier otro estado, incluido "en curso", "crédito parcial" o "no detectado"
- **Progreso** de la evaluación: porcentaje del trabajo realizado hacia la finalización, medido por el número de controles probados correctamente
- **Acciones de mejora**: el número de acciones completadas para satisfacer la implementación de los controles
- **Acciones de Microsoft**: el número de acciones completadas para satisfacer la implementación de controles de Microsoft
- **Grupo**: nombre del grupo al que pertenece la evaluación
- **Producto**: producto asociado, como Microsoft 365 u otro producto definido para la evaluación
- **Reglamento**: el estándar normativo, la política o la ley que se aplica a la evaluación

### <a name="filtering-your-assessments-view"></a>Filtrado de la vista de evaluaciones

Para filtrar la vista de las evaluaciones:

1. Seleccione **Filtrar** en la esquina superior izquierda de la lista de evaluaciones.
2. En el panel flotante **Filtros** , compruebe los criterios deseados.
3. Seleccione el botón **Aplicar** . El panel de filtro se cerrará y verá la vista filtrada.

También puede modificar la vista para ver las evaluaciones por grupo, producto o reglamento seleccionando el tipo de agrupación en el menú desplegable **Grupo** situado encima de la lista de evaluaciones.

### <a name="default-assessment"></a>Evaluación predeterminada

De forma predeterminada, verá la evaluación de base de [referencia de protección de datos](compliance-manager-assessments.md#data-protection-baseline-default-assessment) en la página evaluaciones. El Administrador de cumplimiento también proporciona varias [plantillas](compliance-manager-templates-list.md) pregeneradas para crear evaluaciones.

## <a name="assessment-templates-page"></a>Página Plantillas de evaluación

Una plantilla es un marco de directiva para crear una evaluación en el Administrador de cumplimiento. La página de plantillas de evaluación muestra una lista de las plantillas e información clave. La lista incluye plantillas proporcionadas por el Administrador de cumplimiento, así como las plantillas que su organización haya modificado o creado. Puede aplicar filtros para buscar una plantilla basada en la certificación, el ámbito del producto, el país, el sector y quién la creó.

El contador **de plantillas activadas** situado cerca de la parte superior de la página muestra el número de plantillas de evaluación activas actualmente en uso del número total de plantillas disponibles para su organización. Consulte [Disponibilidad y licencias de plantillas](compliance-manager-templates.md#template-availability-and-licensing) para obtener más información.

Seleccione una plantilla de su fila para mostrar su página de detalles, que contiene una descripción de la plantilla y más información sobre la certificación, el ámbito y los detalles de los controles. En esta página puede seleccionar los botones adecuados para crear una evaluación, exportar los datos de plantilla a Excel o modificar la plantilla.

**Más información:** [Lea cómo trabajar con plantillas de evaluación](compliance-manager-templates.md).

## <a name="next-step"></a>Paso siguiente

Personalice el Administrador de cumplimiento [mediante la configuración de evaluaciones](compliance-manager-assessments.md).
