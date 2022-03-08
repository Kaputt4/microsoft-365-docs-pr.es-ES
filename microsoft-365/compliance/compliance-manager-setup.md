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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: Establezca los permisos y roles de usuario del Administrador de cumplimiento de Microsoft y configure las pruebas automatizadas de las acciones. Administrar el historial de usuarios y filtrar la vista de panel.
ms.openlocfilehash: 070c8fea309ea7c01b82be068acc40a7dcb830ff
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330487"
---
# <a name="get-started-with-compliance-manager"></a>Introducción al Administrador de cumplimiento

**En este artículo:** Este artículo le ayuda a configurar el Administrador de cumplimiento. Obtenga información sobre cómo **obtener acceso al** Administrador de cumplimiento, **establecer roles y permisos y configurar pruebas automáticas** **de acciones de mejora**. Pase por **el panel del Administrador de cumplimiento** y comprenda las páginas principales: la página de acciones de mejora, la página de soluciones, la página de evaluaciones y la página de plantillas de evaluación.

## <a name="who-can-access-compliance-manager"></a>Quién puede tener acceso al Administrador de cumplimiento

El Administrador de cumplimiento está disponible para las organizaciones con licencias Office 365 y Microsoft 365, y para los clientes de Government Community Cloud (GCC) moderados, GCC altos y del Departamento de Defensa (DoD). La disponibilidad de evaluación y las capacidades de administración dependen del contrato de licencia.  [Ver detalles de descripción del servicio](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="before-you-begin"></a>Antes de empezar

El Microsoft 365 global de la organización probablemente será el primer usuario en tener acceso al Administrador de cumplimiento. Se recomienda que el administrador global inicie sesión y establezca los permisos de usuario como se describe a continuación al visitar el Administrador de cumplimiento por primera vez.

## <a name="sign-in"></a>Iniciar sesión

1. Vaya a la <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Centro de cumplimiento de Microsoft 365</a> e **inicie sesión** con su cuenta Microsoft 365 de administrador global.
2. Seleccione **Administrador de cumplimiento** en el panel de navegación izquierdo. Llegarás al panel del Administrador [de cumplimiento](#understand-the-compliance-manager-dashboard).

El vínculo directo para acceder al Administrador de cumplimiento es [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager).

## <a name="set-user-permissions-and-assign-roles"></a>Establecer permisos de usuario y asignar roles

El Administrador de cumplimiento usa un modelo de permisos de control de acceso basado en roles (RBAC). Solo los usuarios a los que se asigna un rol pueden tener acceso al Administrador de cumplimiento y las acciones permitidas por cada usuario están restringidas por tipo [de función](#role-types).

### <a name="where-to-set-permissions"></a>Dónde establecer permisos

La persona que tiene el rol de administrador global de su organización puede establecer permisos de usuario para el Administrador de cumplimiento. Los permisos se pueden establecer en el Centro de cumplimiento de Microsoft 365, así como en Azure Active Directory (Azure AD).

> [!NOTE]
> Los clientes de entornos de Community (GCC) de Administración pública (GCC) y departamento de defensa (DoD) solo pueden establecer permisos de usuario y roles para el Administrador de cumplimiento en Azure AD. Vea a continuación Azure AD instrucciones y definiciones de tipo de función.

Para establecer permisos y asignar roles en el Centro de cumplimiento de Microsoft 365, siga los pasos siguientes:

1. Vaya a la Centro de cumplimiento de Microsoft 365 y seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">**Permisos**</a>.

2. En la lista **desplegable Centro de** cumplimiento, seleccione **Roles**.

3. Busque el grupo de roles al que desea agregar uno o varios usuarios y active la casilla a la izquierda del nombre del grupo. (Vea la [lista de roles y funciones relacionadas a continuación](#role-types). Los nombres de los grupos de roles imitan el nombre del rol).

4. En el panel desplegable de ese grupo, seleccione **Editar en** el **encabezado** Miembros.

5. Seleccione **Elegir miembros**. Aparecerá otra ventana desplegable.

6. Seleccione **+ Agregar** para elegir uno o varios usuarios para agregar al grupo.

7. Seleccione la casilla situada junto a los nombres que desea agregar y, a continuación, seleccione el **botón** Agregar en la parte inferior.

8. Cuando haya terminado de asignar usuarios, seleccione **Listo** y, a continuación, **seleccione Guardar** y, a continuación, **Cerrar**.

#### <a name="more-about-azure-ad"></a>Más información sobre Azure AD

Para asignar roles y establecer permisos en Azure AD, vea [Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

Los usuarios Azure AD identidades que no tienen Office 365 o Microsoft 365 suscripciones no podrán acceder al Administrador de cumplimiento en el Centro de cumplimiento de Microsoft 365. Para obtener ayuda para obtener acceso al Administrador de cumplimiento, póngase [en contacto cmresearch@microsoft.com](mailto:cmresearch@microsoft.com).

### <a name="role-types"></a>Tipos de función

En la tabla siguiente se muestran las funciones permitidas por cada rol en el Administrador de cumplimiento. La tabla también muestra cómo cada [función Azure AD asigna](/azure/active-directory/roles/permissions-reference) a roles del Administrador de cumplimiento. Los usuarios necesitarán al menos el rol de lector administrador de cumplimiento, o Azure AD de lector global, para tener acceso al Administrador de cumplimiento.

| El usuario puede: | Rol Administrador de cumplimiento | Azure AD rol | 
| :------------- | :-------------: | :------------: |
| **Leer pero no editar datos**| Lector de Administrador de cumplimiento  | Azure AD lector global, lector de seguridad |
| **Editar datos**| Contribución del administrador de cumplimiento | Administrador de cumplimiento |
| **Editar resultados de pruebas**| Evaluador de Administrador de cumplimiento | Administrador de cumplimiento |
| **Administrar evaluaciones y datos de plantilla e inquilino**| Administración del administrador de cumplimiento | Administrador de cumplimiento, administrador de datos de cumplimiento, administrador de seguridad  |
| **Asignar usuarios**| Administrador global | Administrador global |

## <a name="start-a-premium-assessments-trial"></a>Iniciar una prueba de evaluaciones premium

La prueba de evaluaciones premium del Administrador de cumplimiento es una excelente manera de configurar rápidamente las evaluaciones más relevantes para su organización. Nuestra biblioteca de más de 300 plantillas se corresponden con las normativas gubernamentales y los estándares del sector en todo el mundo.
Obtenga más información sobre la [prueba de evaluaciones premium](compliance-easy-trials-compliance-manager-assessments.md).

Puede iniciar la prueba directamente desde el Administrador de cumplimiento y configurar las evaluaciones recomendadas siguiendo estos pasos:

1. En la página **Información general del** Administrador de cumplimiento, seleccione **Iniciar prueba**. Escribirá un asistente de activación de prueba que hará preguntas para ayudarnos a recomendar evaluaciones para su organización.

2. En la **página Activar prueba****, seleccione Siguiente** para comenzar la prueba gratuita de evaluaciones premium de 90 días y continuar con la creación de evaluaciones.

3. Seleccione uno o más sectores que identifiquen su organización y, a continuación, **seleccione Siguiente**.

4. Seleccione una o varias regiones para la ubicación de su organización y, a continuación, seleccione **Siguiente**.

5. En la **pantalla Elegir evaluaciones** , seleccione la flecha desplegable junto a **Plantillas** recomendadas para ver la lista de evaluaciones que creemos que se aplican a su organización. Active las casillas situadas junto a las plantillas que desea usar para crear evaluaciones y, a continuación, seleccione **Siguiente**.

6. Revise las selecciones finales y **seleccione Agregar evaluaciones recomendadas** para crear sus nuevas evaluaciones.

Para obtener más información sobre cómo empezar con las evaluaciones, visite la sección [de la página Evaluaciones](#assessments-page) que se muestra a continuación.

## <a name="settings-for-automated-testing-and-user-history"></a>Configuración para pruebas automatizadas e historial de usuarios

La configuración del Administrador de cumplimiento en el Centro de cumplimiento de Microsoft 365 permite habilitar y deshabilitar las pruebas automáticas de las acciones de mejora. La configuración también le permite administrar los datos de los usuarios asociados a acciones de mejora, incluida la capacidad de reasignar acciones de mejora a un usuario diferente.  Solo las personas con un rol de administrador global o administrador de cumplimiento pueden acceder a la configuración del Administrador de cumplimiento.

> [!NOTE]
> La característica de prueba automatizada no está disponible para los clientes en GCC entornos high y doD porque la puntuación segura no está disponible en estos entornos. GCC los clientes de High y DoD tendrán que implementar y probar manualmente sus acciones de mejora.

### <a name="set-up-automated-testing"></a>Configurar pruebas automatizadas

El Administrador de cumplimiento detecta señales de otras soluciones de cumplimiento de Microsoft 365 a las que su organización se suscribe, incluidos el gobierno de la información, la protección de la información, la prevención de pérdida de datos, el cumplimiento de las comunicaciones y la administración de riesgos de información confidencial. En la página de detalles de cada acción de mejora, el campo Lógica de  prueba de la ficha Prueba mostrará lo que se necesita en la otra solución para que la acción pase y gane puntos hacia la puntuación de cumplimiento.

El Administrador de cumplimiento también detecta señales de acciones de mejora complementarias que también son supervisadas por [La puntuación segura de Microsoft](../security/defender/microsoft-secure-score.md). Con estas señales, el Administrador de cumplimiento puede probar automáticamente determinadas acciones de mejora para usted, lo que ayuda a maximizar la eficiencia en sus actividades de cumplimiento. Cuando una acción de mejora se prueba e implementa correctamente, recibes la cantidad completa de puntos, que se acredita en la puntuación general de cumplimiento.

En la página de detalles de cada acción de mejora

Las pruebas automáticas están activadas de forma predeterminada para organizaciones nuevas en el Administrador de cumplimiento. Al implementar por primera vez Microsoft 365 o Office 365, se tarda aproximadamente siete días en recopilar completamente los datos y tener en cuenta la puntuación de cumplimiento. Cuando las pruebas automatizadas están activadas, la fecha de prueba de la acción no se actualizará, pero su estado de prueba se actualizará. Cuando se crean nuevas evaluaciones, las puntuaciones incluyen automáticamente las puntuaciones de control de Microsoft y la integración de puntuación segura.

#### <a name="manage-automated-testing-settings"></a>Administrar la configuración de pruebas automatizadas

El administrador global de su organización puede cambiar la configuración de las pruebas automatizadas en cualquier momento. Puedes desactivar las pruebas automatizadas para acciones de mejora comunes o activarla para acciones individuales. Siga las instrucciones siguientes para cambiar la configuración de las pruebas automatizadas.

1. Seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**Configuración**</a> en el Centro de cumplimiento de Microsoft 365.

2. En la página de configuración, seleccione **Administrador de cumplimiento**.

3. Seleccione **Pruebas automatizadas** en la navegación izquierda.

4. Selecciona el botón aplicable para activar las pruebas automáticas de todas las acciones de mejora, desactivarla para todas las acciones o activarla por acción individual.

5. Si selecciona Activar **por acción de mejora**, una lista mostrará todas las acciones de mejora disponibles para elegir.  Active la casilla situada junto a cualquier acción que desee probar automáticamente.

6. Seleccione **Guardar** para guardar la configuración. Recibirás un mensaje de confirmación en la parte superior de la pantalla que indica que la selección se guardó. Si recibe un aviso de error, inténtelo de nuevo.

**Nota:** Solo el administrador global puede activar o desactivar las actualizaciones automáticas de todas las acciones. El administrador del administrador de cumplimiento puede activar actualizaciones automáticas para acciones individuales, pero no para todas las acciones globalmente.

**Más información**
- [Obtenga más información sobre cómo la supervisión continua contribuye a la puntuación de cumplimiento](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls).
- [Obtenga más información sobre cómo designar un origen de pruebas para una acción de mejora](compliance-manager-improvement-actions.md#update-testing-source).

### <a name="manage-user-history"></a>Administrar el historial de usuarios

La **configuración Administrar historial de** usuarios le ayuda a identificar rápidamente qué usuarios han trabajado con acciones de mejora en el Administrador de cumplimiento. Los datos de usuario identificables asociados con acciones de mejora incluyen cualquier trabajo de implementación y prueba realizado, documentos que cargaron y cualquier nota que introdujeron. Comprender y recuperar este tipo de datos puede ser necesario para las propias necesidades de cumplimiento de su organización.

La configuración del historial de usuarios también le permite reasignar todas las acciones de mejora de un usuario a otro.

**Para buscar la configuración del historial de usuarios:**

1. Seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**Configuración**</a> en el Centro de cumplimiento de Microsoft 365.

2. En la página de configuración, seleccione **Administrador de cumplimiento**.

3. Seleccione **Administrar el historial de usuarios** en la navegación izquierda.

La **página Administrar historial de** usuarios muestra una lista de todos los usuarios por dirección de correo electrónico que están asignados a una acción de mejora. Use el **botón Buscar** para buscar rápidamente un usuario específico escribiendo su dirección de correo electrónico.

A la derecha de la dirección de correo electrónico de cada usuario, el menú desplegable Seleccionar proporciona opciones para exportar un informe, reasignar acciones de mejora o eliminar el historial. Consulta cada sección a continuación para obtener más información sobre cada opción.

#### <a name="export-a-report-of-user-history-data"></a>Exportar un informe de datos de historial de usuarios

Puede exportar un archivo Excel que contenga una lista de acciones de mejora asignadas actualmente a un usuario.  El informe también enumera los archivos de evidencia cargados por ese usuario. Esta información puede ayudarle a reasignar acciones de mejora abiertas.

El informe refleja el estado de la acción de mejora a partir de su fecha de creación. No es un informe histórico de todos los cambios anteriores en su estado o asignación (obtenga información sobre cómo exportar un [informe desde la página de acciones de mejora](compliance-manager-improvement-actions.md#export-a-report)).

**Siga los pasos siguientes para exportar un informe por usuario:**

1. Seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**Configuración**</a> en el Centro de cumplimiento de Microsoft 365.

2. En la página de configuración, seleccione **Administrador de cumplimiento**.

3. Seleccione **Administrar el historial de usuarios** en la navegación a la izquierda.

4. Busque al usuario deseado buscando en las direcciones de correo electrónico de lista o **seleccionando Buscar** y especificando la dirección de correo electrónico del usuario.

5. En el **menú** desplegable Seleccionar, elija **Exportar informe**.

6. Una vez que Excel archivo de informe, puede abrirlo y guardarlo en el equipo local.

#### <a name="reassign-improvement-actions-to-another-user"></a>Asignar acciones de mejora a otro usuario

Puede reasignar acciones de mejora de un usuario a otro. Al reasignar una acción, el historial de carga del documento no cambia, pero el nombre del usuario que carió originalmente la documentación ya no aparece en la acción de mejora.

**Siga los pasos siguientes para reasignar acciones de mejora a otro usuario:**

1. Seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**Configuración**</a> en el Centro de cumplimiento de Microsoft 365.

2. En la página de configuración, seleccione **Administrador de cumplimiento**.

3. Seleccione **Administrar el historial de usuarios** en la navegación a la izquierda.

4. Busque un usuario buscando en las direcciones de correo electrónico de lista o **seleccionando Buscar** y especificando la dirección de correo electrónico de ese usuario.

5. En el **menú** desplegable Seleccionar, elija **Reasignar acciones de mejora**. Aparecerá **el panel desplegable Reasignar** acciones de mejora.

6. En el **campo Buscar usuarios** , escriba el nombre o la dirección de correo electrónico del usuario al que desea asignar las acciones de *mejora*.

7. Cuando vea el nombre del usuario previsto en **Acciones** de mejora se asignarán a, seleccione el usuario y, a continuación, **seleccione Asignar acciones**.

8. Una vez completada la reasignación, verá un mensaje de confirmación en el panel desplegable que confirma que todas las acciones de mejora del usuario anterior se han reasignado al nuevo usuario. Si recibe un aviso de error de reasignación, cierre la ventana e inténtelo de nuevo. Para cerrar el panel desplegable, seleccione **Listo**.

El nuevo destinatario recibe un correo electrónico que se ha asignado a una acción de mejora. El correo electrónico contiene un vínculo directo a la página de detalles de la acción de mejora.

 > [!NOTE]
> Si reasigna una acción que tiene una actualización pendiente, el vínculo directo a la acción en el correo electrónico de reasignación se interrumpirá si la actualización se acepta después de la reasignación. Para solucionar esto, vuelva a asignar la acción al usuario después de aceptar la actualización. Obtenga más información sobre [las actualizaciones de las acciones de mejora](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).

#### <a name="delete-user-history"></a>Eliminar historial de usuarios

Al eliminar el historial de un usuario, se eliminarán como propietarios de las acciones de mejora y se quitará su nombre de todos los demás campos del Administrador de cumplimiento. Al eliminar el historial de un usuario, las acciones de mejora que poseen no mostrarán un valor **Asignado** a hasta que se asigne un nuevo usuario. Los documentos cargados en la acción de mejora mostrarán **Usuario eliminado** en lugar del nombre del usuario eliminado. Eliminar el historial de usuarios es permanente.

Para eliminar el historial de un usuario, siga estos pasos:

1. Seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**Configuración**</a> en el Centro de cumplimiento de Microsoft 365.

2. En la página de configuración, seleccione **Administrador de cumplimiento**.

3. Seleccione **Administrar el historial de usuarios** en la navegación a la izquierda.

4. Busque un usuario buscando en las direcciones de correo electrónico de lista o **seleccionando Buscar** y especificando la dirección de correo electrónico de ese usuario.

5. En el **menú** desplegable Seleccionar, elija **Eliminar historial**.

6. Aparece una ventana que le pide que confirme la eliminación permanente del historial del usuario. Para continuar con la eliminación, seleccione **Eliminar historial**. Para salir sin eliminar el historial, seleccione **Cancelar**.

7. Volverás a la página Administrar historial  de usuarios con un mensaje de confirmación en la parte superior que indica que se eliminó el historial del usuario.

## <a name="understand-the-compliance-manager-dashboard"></a>Comprender el panel del Administrador de cumplimiento

El panel del Administrador de cumplimiento está diseñado para proporcionarle una vista de un vistazo de su posición de cumplimiento actual.

:::image type="content" alt-text="Panel del Administrador de cumplimiento." source="../media/compliance-manager-dashboard.png" lightbox="../media/compliance-manager-dashboard.png":::

### <a name="overall-compliance-score"></a>Puntuación de cumplimiento global

La puntuación de cumplimiento aparece destacadamente en la parte superior. Muestra un porcentaje basado en puntos alcanzables para completar acciones de mejora que abordan estándares y normativas clave de protección de datos. Los puntos [de las acciones de Microsoft](compliance-manager-assessments.md#microsoft-actions-tab), que se administran en Microsoft, también cuentan para la puntuación de cumplimiento.

Cuando llega al Administrador de cumplimiento por primera vez, la puntuación inicial se basa en la línea Microsoft 365 [base de protección de datos](compliance-manager-assessments.md#data-protection-baseline-default-assessment). Esta evaluación de línea base, que está disponible para todas las organizaciones, es un conjunto de controles que incluye normativas y estándares comunes del sector. El Administrador de cumplimiento examina las soluciones Microsoft 365 existentes y le ofrece una evaluación inicial basada en la configuración actual de privacidad y seguridad. A medida que agrega evaluaciones que son relevantes para su organización, la puntuación se vuelve más significativa para usted.

**Obtenga más información:** [Comprenda cómo se calcula la puntuación de cumplimiento](compliance-score-calculation.md).

### <a name="key-improvement-actions"></a>Acciones de mejora claves

En esta sección se enumeran las principales acciones de mejora que puede realizar en este momento para lograr el mayor impacto positivo en la puntuación general de cumplimiento. Selecciona **Ver todas las acciones de mejora** para ir a la página de acciones de mejora.

### <a name="solutions-that-affect-your-score"></a>Soluciones que afectan a su puntuación

En esta sección se destacan las soluciones que contienen acciones de mejora que pueden afectar positivamente a la puntuación y el número de acciones de mejora pendientes en esas soluciones. Seleccione **Ver todas las soluciones** para visitar la página de soluciones.

### <a name="compliance-score-breakdown"></a>Desglose de puntuación de cumplimiento

Esta sección le ofrece una vista más detallada de la puntuación de dos maneras diferentes:

- **Categorías**: muestra el porcentaje de la puntuación general dentro de las categorías de protección de datos, como "proteger la información" o "administrar dispositivos".
- **Evaluaciones**: muestra el porcentaje de su progreso en la administración de evaluaciones para estándares, reglamentos o leyes específicos de cumplimiento y protección de datos, como RGPD o NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtrar la vista de panel

Puede filtrar la vista del panel para ver solo los elementos relacionados con determinadas normativas y estándares, soluciones, tipo de acción, grupos de evaluación o categorías de protección de datos. El filtrado de la vista de esta manera también filtrará la puntuación en el panel, mostrando cuántos puntos has logrado del total de puntos posibles en función de los criterios de filtro.

Para aplicar filtros:

1. Seleccione **Filtrar** en la parte superior derecha del panel.
2. Seleccione los criterios de filtro **en el panel** desplegable Filtros y, a continuación, **seleccione Aplicar**.

Después de aplicar un filtro, verás la puntuación ajustada en tiempo real. El porcentaje de puntuación de cumplimiento y la información de desglose, y las acciones y soluciones de mejora, ahora solo pertenecen a los datos cubiertos por los criterios de filtro. Si inicia sesión en el Administrador de cumplimiento, la vista filtrada permanece al iniciar sesión de nuevo.

Para quitar filtros:

- En el **encabezado Filtros aplicados** encima de la puntuación de cumplimiento, seleccione **la X** junto al filtro individual que desea quitar; o
- Seleccione **Filtrar** en la parte superior derecha del panel y, a continuación,  en el panel desplegable Filtros, seleccione **Borrar filtros**.

## <a name="improvement-actions-page"></a>Página Acciones de mejora

[Las acciones de](compliance-manager-improvement-actions.md) mejora son acciones administradas por la organización. Trabajar con acciones de mejora ayuda a centralizar las actividades de cumplimiento y alinearse con las normativas y estándares de protección de datos. Cada acción de mejora proporciona instrucciones de implementación detalladas y un vínculo para iniciarlo en la solución adecuada. Las acciones de mejora se pueden asignar a los usuarios de la organización para realizar el trabajo de implementación y pruebas. También puede almacenar documentación, notas y registrar actualizaciones de estado dentro de la acción de mejora.

### <a name="view-your-improvement-actions"></a>Ver las acciones de mejora

El panel del Administrador de cumplimiento muestra las principales acciones de mejora. Para ver todas las acciones de mejora, selecciona la pestaña **Acciones de** mejora del panel, que te lleva a la página acciones de mejora. También puedes seleccionar Ver todas las acciones de **mejora** debajo de la lista de acciones de mejora clave del panel para llegar a la página de acciones de mejora.

La página acciones de mejora muestra todas las acciones de mejora administradas por la organización. Las acciones administradas por Microsoft se pueden ver en cada evaluación (obtenga más información sobre [las acciones de Microsoft](compliance-manager-assessments.md#microsoft-actions-tab)).

Si tiene una larga lista de acciones en la página de acciones de mejora, puede resultar útil filtrar la vista. Seleccione **Filtrar** en la esquina superior derecha de la lista de acciones. Cuando aparezca **el** panel desplegable Filtros, seleccione los criterios de las opciones disponibles. También puede personalizar la vista **seleccionando Grupo** en la esquina superior derecha. En el menú desplegable, seleccione para ver por grupo, solución, categoría, tipo de acción o estado.

La vista predeterminada de esta página no muestra acciones de mejora con el estado de prueba **Pasado**. Para ver las acciones que han pasado las pruebas, active la casilla **Pasado** en el panel desplegable Filtros. Solo las acciones con un estado de prueba de **Pasado** cuentan para la puntuación. Algunas acciones pueden mostrar una **etiqueta de actualización pendiente.** Obtenga más información sobre [las actualizaciones de las acciones de mejora](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).

La página de acciones de mejora muestra los siguientes puntos de datos para cada acción de mejora:

- **Productos**: el producto que se está evaluando.
- **Puntos logrados**: el número de puntos obtenidos fuera del total disponible al completar la acción
- **Reglamentos**: los reglamentos o estándares relacionados con la acción
- **Grupo**: el grupo al que asignó la acción
- **Soluciones**: la solución a la que puede ir para realizar la acción
- **Evaluaciones**: las evaluaciones que contienen la acción
- **Categorías**: categoría de protección de datos relacionada (por ejemplo, proteger información, administrar dispositivos, etc.)
- **Estado de la prueba**:
  - **Ninguno** : no se registró ninguna actualización de estado
  - **No evaluado:** las pruebas no se han iniciado
  - **Pasado:** implementación probada correctamente
  - **Riesgo bajo con error** : error en las pruebas, bajo riesgo
  - **Riesgo medio fallido** : error en las pruebas, riesgo medio
  - **Alto riesgo de error** : error en las pruebas, alto riesgo
  - **Fuera del ámbito** : la acción no está en el ámbito de la evaluación y no afecta a la puntuación
  - **Para ser detectado** : para la prueba manual, indica que se ha implementado una acción pero no se ha probado; para la prueba automatizada, indica que una acción está esperando el resultado de automatización
  - **No se pudo detectar** : no se puede determinar el estado automatizado
  - **Prueba parcial:** puntuación automatizada que otorga puntos parciales
- **Tipo de** acción: indica si la acción de mejora es técnica, lo que significa que se puede implementar dentro de una solución o producto, o no técnico, que se implementaría fuera de una solución técnica
- **Asignado a**: la persona a la que se asignó esta acción, si procede
- **Origen de** prueba: indica si el origen de prueba de la acción es manual, automático o heredado de un elemento primario

**Más información: Vea** [cómo asignar y realizar el trabajo en acciones de mejora](compliance-manager-improvement-actions.md).

## <a name="solutions-page"></a>Página Soluciones

La página de soluciones muestra el porcentaje de puntos ganados y potenciales organizados por solución. Ver los puntos restantes y las acciones de mejora desde esta vista le ayuda a comprender qué soluciones necesitan una atención más inmediata.

Para buscar la página de soluciones, seleccione la **pestaña Soluciones** en el panel del Administrador de cumplimiento. También puede seleccionar Ver todas **las soluciones debajo** de **Soluciones que afectan a su puntuación** en la sección superior derecha del panel.

### <a name="filtering-your-solutions-view"></a>Filtrar la vista soluciones

Para filtrar la vista de soluciones:

1. Seleccione **Filtrar** en la esquina superior izquierda de la lista de evaluaciones.
2. En el **panel** desplegable Filtros, coloque una comprobación junto a los criterios deseados (normativas, soluciones, tipos de acción, grupos, categorías).
3. Seleccione el **botón** Aplicar. El panel de filtro se cerrará y verá la vista filtrada.

También puede modificar la vista para ver las evaluaciones por grupo, producto o regulación seleccionando el tipo de agrupación en el menú  desplegable Grupo encima de la lista de evaluaciones.

### <a name="taking-action-from-the-solution-page"></a>Realizar acciones desde la página de solución

La página soluciones muestra las soluciones de su organización que están conectadas a acciones de mejora. La tabla enumera la contribución de cada solución a la puntuación general, los puntos alcanzados y posibles dentro de esa solución y el número restante de acciones de mejora agrupadas en esa solución que pueden aumentar la puntuación.

Hay dos maneras de tomar medidas desde esta pantalla:

1. En la fila de la solución prevista, en la columna **Acciones restantes** , seleccione el número de hipervínculo. Verás una vista filtrada de la pantalla de acciones de mejora que muestra acciones de mejora sin probar para esa solución.

2. En la fila de la solución prevista, en la columna **Abrir solución** , seleccione **Abrir**. Verá la solución o la ubicación en los centros de Microsoft 365 y Office 365 seguridad y cumplimiento donde puede realizar la acción recomendada.

## <a name="assessments-page"></a>Página Evaluaciones

La página evaluaciones enumera todas las [evaluaciones](compliance-manager-assessments.md) que ha configurado para su organización. El denominador de puntuación de cumplimiento viene determinado por todas las evaluaciones de seguimiento. A medida que agregues más evaluaciones, verás más acciones de mejora enumeradas en la página acciones de mejora y aumenta el denominador de puntuación de cumplimiento.

El **contador de plantillas** activadas cerca de la parte superior de la página muestra el número de plantillas de evaluación activas que se usan actualmente del número total de plantillas disponibles para su organización. Consulte [Disponibilidad de plantillas y licencias](compliance-manager-templates.md#template-availability-and-licensing) para obtener más información.

La página de evaluaciones resume la información clave sobre cada evaluación:

- **Evaluación**: nombre de la evaluación
- **Estado**:
  - **Completado** : todos los controles tienen el estado "pasado", o al menos se pasa uno y el resto está "fuera del ámbito"
  - **Incompleto** : al menos un control tiene el estado de "error"
  - **Ninguno** : no se han probado todos los controles
  - **En curso** : las acciones de mejora tienen cualquier otro estado, incluidos "en curso", "crédito parcial" o "sin detectar"
- **Progreso de la** evaluación: el porcentaje del trabajo realizado hasta la finalización, medido por el número de controles probados correctamente
- **Acciones de mejora**: el número de acciones completadas para satisfacer la implementación de los controles
- **Acciones de Microsoft**: el número de acciones completadas para satisfacer la implementación de los controles de Microsoft
- **Grupo**: nombre del grupo al que pertenece la evaluación
- **Producto**: producto asociado, como Microsoft 365 u otro producto definido para evaluación
- **Reglamento**: el estándar normativo, la directiva o la ley que se aplica a la evaluación

### <a name="filtering-your-assessments-view"></a>Filtrar la vista de evaluaciones

Para filtrar la vista de las evaluaciones:

1. Seleccione **Filtrar** en la esquina superior izquierda de la lista de evaluaciones.
2. En el **panel** desplegable Filtros, compruebe los criterios que desee.
3. Seleccione el **botón** Aplicar. El panel de filtro se cerrará y verá la vista filtrada.

También puede modificar la vista para ver las evaluaciones por grupo, producto o regulación seleccionando el tipo de agrupación en el menú  desplegable Grupo encima de la lista de evaluaciones.

### <a name="default-assessment"></a>Evaluación predeterminada

De forma predeterminada, verá la evaluación de línea base de [protección](compliance-manager-assessments.md#data-protection-baseline-default-assessment) de datos en la página evaluaciones. El Administrador de cumplimiento también proporciona varias plantillas predefinidas [para](compliance-manager-templates-list.md) las evaluaciones de creación.

## <a name="assessment-templates-page"></a>Página Plantillas de evaluación

Una plantilla es un marco de directiva para crear una evaluación en el Administrador de cumplimiento. La página de plantillas de evaluación muestra una lista de las plantillas e información clave. La lista incluye plantillas proporcionadas por el Administrador de cumplimiento, así como cualquier plantilla que la organización haya modificado o creado. Puede aplicar filtros para buscar una plantilla basada en la certificación, el ámbito del producto, el país, la industria y quién la creó.

El **contador de plantillas** activadas cerca de la parte superior de la página muestra el número de plantillas de evaluación activas que se usan actualmente del número total de plantillas disponibles para su organización. Consulte [Disponibilidad de plantillas y licencias](compliance-manager-templates.md#template-availability-and-licensing) para obtener más información.

Seleccione una plantilla de su fila para mostrar su página de detalles, que contiene una descripción de la plantilla y más información sobre los detalles de certificación, ámbito y controles. En esta página puede seleccionar los botones adecuados para crear una evaluación, exportar los datos de plantilla a Excel o modificar la plantilla.

**Más información: Lea** [cómo trabajar con plantillas de evaluación](compliance-manager-templates.md).

## <a name="next-step"></a>Paso siguiente

Personalice el Administrador de cumplimiento [configurando evaluaciones](compliance-manager-assessments.md).
