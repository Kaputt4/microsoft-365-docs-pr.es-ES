---
title: Compilación y administración de evaluaciones en el Administrador de cumplimiento de Microsoft
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
search.appverid:
- MOE150
- MET150
description: Cree evaluaciones en el Administrador de cumplimiento de Microsoft para ayudarle a cumplir los requisitos de las regulaciones y certificaciones que son importantes para su organización.
ms.openlocfilehash: 9fbea59eae103e2ce9715fda6c7b7a97d38eb855
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2022
ms.locfileid: "64759023"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a>Compilación y administración de evaluaciones en el Administrador de cumplimiento

**En este artículo:** Obtenga información sobre cómo personalizar el Administrador de cumplimiento para su organización mediante la creación y administración de **evaluaciones**. En este artículo se explica cómo crear evaluaciones, cómo organizarlas en **grupos**, trabajar con **controles**, aceptar **actualizaciones** y exportar **informes** de evaluación.

## <a name="introduction-to-assessments"></a>Introducción a las evaluaciones

El Administrador de cumplimiento le ayuda a crear evaluaciones que evalúen el cumplimiento con las regulaciones regionales y del sector que se aplican a su organización. Las evaluaciones se basan en el marco de plantillas de evaluación, que contienen los controles necesarios, las acciones de mejora y, si procede, las acciones de Microsoft para completar la evaluación. La configuración de las evaluaciones más relevantes para su organización puede ayudarle a implementar directivas y procedimientos operativos para limitar el riesgo de cumplimiento.

Todas las evaluaciones se muestran en la pestaña evaluaciones del Administrador de cumplimiento. Obtenga más información sobre [cómo filtrar la vista de las evaluaciones e interpretar los estados de estado](compliance-manager-setup.md#assessments-page).

> [!IMPORTANT]
> Las plantillas disponibles para su organización para crear evaluaciones dependen del contrato de licencia. [Revise los detalles de las licencias](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="data-protection-baseline-default-assessment"></a>Evaluación predeterminada de la línea de base de protección de datos

Para empezar, Microsoft proporciona una evaluación **predeterminada** en el Administrador de cumplimiento para la base de referencia **de protección de datos Microsoft 365**. Esta evaluación de línea base tiene un conjunto de controles para las normativas y estándares clave para la protección de datos y la gobernanza general de datos. Esta línea de base extrae elementos principalmente de NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Standardization), así como de FedRAMP (Federal Risk and Authorization Management Program) y RGPD (Reglamento general de protección de datos de la Unión Europea).

Esta evaluación se usa para calcular la puntuación de cumplimiento inicial la primera vez que llega al Administrador de cumplimiento, antes de configurar otras evaluaciones. El Administrador de cumplimiento recopila señales iniciales de las soluciones de Microsoft 365. Verá de un vistazo cómo funciona su organización en relación con los estándares y regulaciones clave de protección de datos, y verá las acciones de mejora sugeridas que debe realizar.

El Administrador de cumplimiento resulta más útil a medida que crea y administra sus propias evaluaciones para satisfacer las necesidades específicas de su organización.

## <a name="understand-groups-before-creating-assessments"></a>Descripción de los grupos antes de crear evaluaciones

Al crear una evaluación, deberá asignarla a un grupo. Los grupos son contenedores que le permiten organizar las evaluaciones de una manera lógica para usted, como por año o reglamento, o en función de las divisiones o zonas geográficas de su organización. Por este motivo, se recomienda planear una estrategia de agrupación antes de crear evaluaciones.

A continuación se muestran ejemplos de dos grupos y sus evaluaciones subyacentes:

- **Evaluación de FFIEC IS 2020**
  - FFIEC IS
- **Evaluaciones de seguridad y privacidad de datos**
  - ISO 27001:2013
  - ISO 27018:2014

Las distintas evaluaciones dentro de un grupo o grupos pueden compartir acciones de mejora. Las acciones de mejora pueden ser cambios que realice dentro de soluciones técnicas asignadas a su inquilino, como activar la autenticación en dos fases o acciones no técnicas que realice fuera del sistema, como la creación de una nueva directiva de área de trabajo. Las actualizaciones en detalles o estado que realice en una acción de mejora técnica se recogerán mediante evaluaciones en todos los grupos. Las evaluaciones del grupo en el que se aplican las actualizaciones de acciones de mejora no técnica se reconocerán. Esto le permite implementar una acción de mejora y cumplir varios requisitos simultáneamente.

### <a name="create-a-group"></a>Crear un grupo

Puede crear un grupo al crear una nueva evaluación. Los grupos no se pueden crear como entidades independientes.

### <a name="what-to-know-when-working-with-groups"></a>Qué saber al trabajar con grupos

- Un grupo debe contener al menos una evaluación.
- Los nombres de grupo deben ser únicos dentro de la organización.
- Los grupos no tienen propiedades de seguridad. Todos los permisos están asociados a evaluaciones.
- Una vez que se agrega una evaluación a un grupo, no se puede cambiar la agrupación.
- Si agrega una nueva evaluación a un grupo existente, la información común de las evaluaciones de ese grupo se copia en la nueva evaluación.
- Los controles de evaluación relacionados en distintas evaluaciones dentro del mismo grupo se actualizan automáticamente cuando se completan.
- Los grupos pueden contener evaluaciones para la misma certificación o regulación, pero cada grupo solo puede contener una evaluación para un par específico de certificación de productos. Por ejemplo, un grupo no puede contener dos evaluaciones para Office 365 y NIST CSF. Un grupo puede contener varias evaluaciones para el mismo producto solo si la certificación o regulación correspondiente para cada uno de ellos es diferente.
- La eliminación de una evaluación rompe la relación entre esa evaluación y el grupo.
- Los grupos no se pueden eliminar.

## <a name="understand-templates-before-creating-assessments"></a>Descripción de las plantillas antes de crear evaluaciones

Las plantillas de evaluación contienen los controles y las recomendaciones de acción para las evaluaciones, basadas en certificaciones para diferentes normas y normas de privacidad. Las plantillas disponibles de su organización pueden incluir una o varias plantillas que se incluyeron como parte del contrato de licencia, junto con las plantillas premium adicionales que haya comprado.

Cada plantilla, ya sea incluida o premium, existe en dos versiones: una para su uso con Microsoft 365 (u otros productos de Microsoft según esté disponible) y una versión universal que se puede adaptar para evaluar otros productos que use. Puede elegir el tipo de plantilla adecuado para el producto que desea evaluar.

Para más información sobre las plantillas, consulte [Trabajar con plantillas de evaluación](compliance-manager-templates.md).

## <a name="create-assessments"></a>Creación de evaluaciones

> [!NOTE]
> Solo los usuarios que tienen un rol de administrador global, administración del administrador de cumplimiento o asesor del administrador de cumplimiento pueden crear y modificar evaluaciones. Obtenga más información sobre [los roles y permisos](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

Antes de empezar, asegúrese de saber a qué grupo le asignará o esté preparado para crear un nuevo grupo para esta evaluación. Lea los detalles sobre [los grupos y las evaluaciones](#understand-groups-before-creating-assessments).

Para crear una evaluación, usará un proceso guiado para seleccionar una plantilla y designar el producto asociado. En **la página Evaluaciones** , le recomendamos que empiece por **Agregar evaluaciones recomendadas**, lo que le ayudará a identificar y configurar rápidamente las evaluaciones más relevantes para su organización a la vez. También puede configurar evaluaciones de uno en uno seleccionando **Agregar evaluación**. Siga los pasos que se indican a continuación para empezar a crear evaluaciones.

#### <a name="create-assessments-based-on-recommendations-for-your-org-type"></a>Creación de evaluaciones basadas en recomendaciones para el tipo de organización

El Administrador de cumplimiento puede indicar qué evaluaciones pueden ser más relevantes para su organización. Cuando proporcione información básica sobre el sector y las ubicaciones de su organización, se recomienda qué plantillas usar desde nuestra biblioteca de más de 300 plantillas. Simplemente elija entre las plantillas recomendadas para configurar rápidamente varias evaluaciones a la vez.

Para crear una o varias evaluaciones basadas en nuestras recomendaciones, seleccione **Agregar evaluaciones recomendadas** en la página **Evaluaciones** y siga estos pasos:

- Seleccione uno o varios sectores que identifiquen su organización y, a continuación, seleccione **Siguiente**.
- Seleccione una o varias regiones para la ubicación de la organización y, a continuación, seleccione **Siguiente.**
- En la pantalla **Elegir evaluación** , seleccione la flecha desplegable situada junto a **Plantillas recomendadas** para ver la lista de evaluaciones que creemos que se aplican a su organización. Active las casillas situadas junto a las plantillas que desea usar para crear evaluaciones y, a continuación, seleccione **Siguiente**.
- Revise las selecciones finales y seleccione **Agregar evaluaciones recomendadas** para crear las nuevas evaluaciones.

#### <a name="create-an-assessment-using-a-guided-process"></a>Creación de una evaluación mediante un proceso guiado

1. En **la página Evaluaciones** , seleccione **Agregar evaluación**. Esto le pondrá en el asistente para la creación de evaluaciones.

2. En la pantalla **Plantilla base** , seleccione **Seleccionar plantilla** para elegir la plantilla para la evaluación.

3. En el panel flotante, elija la plantilla para la regulación o certificación en la que basar la evaluación. La lista de plantillas dividida en categorías incluidas y premium ([obtener detalles](compliance-manager-templates.md#template-availability-and-licensing)). El contador **Plantillas activadas o con licencia** en la parte superior del panel flotante muestra cómo se pueden usar las plantillas que se usan fuera del número total disponible o de su organización para usarlas ([más información](compliance-manager-templates.md#active-and-inactive-templates)). Seleccione el botón de radio situado junto a la plantilla elegida y, a continuación, seleccione **Guardar**. Volverá a la pantalla **Plantilla base** , donde puede revisar los detalles de la plantilla y, a continuación, seleccione **Siguiente**.

4. **Producto, nombre y grupo:** Establezca estas propiedades para identificar la evaluación, elegir el producto que va a evaluar y asignarla a un grupo.

    - **Producto**: seleccione el producto al que desea que se aplique la evaluación. Si usa una plantilla de Microsoft, como una diseñada para Microsoft 365, este campo se rellenará para indicar el producto adecuado y no se puede cambiar. Si usa una plantilla universal, seleccione si va a crear esta evaluación para un nuevo producto o un producto personalizado que ya haya definido en el Administrador de cumplimiento. Si elige un nuevo producto, escriba su nombre. Tenga en cuenta que no puede seleccionar un producto de Microsoft predefinido cuando se usa una plantilla universal.
    - **Nombre de la evaluación**: escriba un nombre para la evaluación en el campo **Nombre de la evaluación** . Los nombres de evaluación deben ser únicos dentro de los grupos. Si el nombre de la evaluación coincide con el nombre de otra evaluación en un grupo determinado, recibirá un error que le pedirá que cree un nombre diferente.
    - **Grupo**: asigne la evaluación a un grupo. Puede:
        - Seleccione **Usar grupo existente** para asignarlo a un grupo que ya ha creado; O
        - Seleccione **Crear nuevo grupo** para crear un nuevo grupo y asignarle esta evaluación:
            - Determine un nombre para el grupo y introdúzcalo en el campo situado debajo del botón de radio.
            - Puede **copiar datos de un grupo existente**, como detalles y documentos de implementación y pruebas, seleccionando los cuadros adecuados.

    Cuando termine, seleccione **Siguiente**.

5. **Revisar y finalizar:** Revise las selecciones y realice las modificaciones necesarias. Cuando esté satisfecho, seleccione **Crear evaluación**.

La siguiente pantalla confirma que se ha creado la evaluación. Cuando seleccione **Listo**, se le llevará a la página de detalles de la nueva evaluación.

Si ve una pantalla **evaluación errónea** después de seleccionar **Crear evaluación**, seleccione **Probar de nuevo** para volver a crear la evaluación.

Puede cambiar el nombre de la evaluación después de crearla seleccionando el botón **Editar nombre** en la esquina superior derecha de la [página de detalles de la evaluación](#monitor-assessment-progress-and-controls).

## <a name="monitor-assessment-progress-and-controls"></a>Supervisión del progreso y los controles de la evaluación

Cada evaluación tiene una página de detalles que proporciona una vista general del progreso al completar la evaluación. En la página se muestra el progreso en la finalización de los controles y el estado de prueba de las acciones de mejora clave dentro de esos controles.

### <a name="overview-tab"></a>Pestaña Información general

La pestaña información general contiene un gráfico que muestra el porcentaje hacia la finalización de la evaluación. Este gráfico contiene un desglose de los puntos de las acciones que posee y los puntos de las acciones propiedad de Microsoft, por lo que puede ver cuántos puntos más necesita para completar la evaluación.

Las principales acciones de mejora de los controles de la evaluación se enumeran en orden de mayor impacto potencial para ganar puntos. El gráfico asociado detalla el estado de prueba agregado de las acciones de mejora para que pueda medir rápidamente lo que se ha probado y lo que todavía debe realizarse.

Para acceder a las acciones de mejora individuales, visite la pestaña **Controles** o la pestaña **Acciones de mejora** .

### <a name="controls-tab"></a>Pestaña Controles

La pestaña controles muestra información detallada para cada control asignado a la evaluación. Un gráfico de **desglose de estado de control** muestra el estado de los controles por familia, por lo que puede ver de un vistazo qué agrupaciones de controles necesitan atención.

Debajo del gráfico, una tabla muestra información detallada sobre cada control dentro de la evaluación. Los controles se agrupan por familia de controles. Expanda cada nombre de familia para mostrar los controles individuales que contiene. La información que se muestra para cada control incluye:

- **Título del control**
- **Estado**: refleja el estado de prueba de las acciones de mejora dentro del control
  - **Pasado** : todas las acciones de mejora tienen un estado de prueba de "pasado", o al menos una se pasa y el resto está "fuera del ámbito".
  - **Error** : al menos una acción de mejora tiene un estado de prueba de "error".
  - **Ninguno** : no se han probado todas las acciones de mejora
  - **Fuera del ámbito:** todas las acciones de mejora están fuera del ámbito de esta evaluación
  - **En curso** : las acciones de mejora tienen un estado distinto de las enumeradas anteriormente, que podría incluir "en curso", "crédito parcial" o "no detectado".
- **Identificador de control**: número de identificación del control, asignado por su regulación, estándar o directiva correspondientes
- **Puntos obtenidos**: el número de puntos obtenidos al completar acciones, del número total de puntos alcanzables
- **Acciones**: el número de acciones completadas del número total de acciones que se van a realizar
- **Acciones de Microsoft**: el número de acciones completadas por Microsoft

Para ver los detalles de un control, selecciónelo de su fila en la tabla. La página de detalles del control muestra un gráfico que indica el estado de prueba de las acciones dentro de ese control. Una tabla debajo del gráfico muestra las acciones de mejora clave para ese control.

Seleccione una acción de mejora de la lista para profundizar en la página de detalles de la acción de mejora. En la página de detalles se muestran las notas de estado y de implementación de la prueba, y se inicia en la solución recomendada.

### <a name="your-improvement-actions-tab"></a>Pestaña Acciones de mejora

En la pestaña de las acciones de mejora se enumeran todos los controles de la evaluación administrados por su organización. En la barra de estado se detalla el estado de prueba agregado de las acciones de mejora en la evaluación para que pueda medir rápidamente lo que se ha probado y lo que todavía debe realizarse. Debajo de la barra se encuentra la lista completa de acciones de mejora y detalles clave, incluidos: estado de la prueba, número de puntos potenciales y ganados, regulaciones y estándares asociados, solución aplicable, tipo de acción y familia de control. Obtenga más información sobre [cómo las acciones contribuyen a la puntuación de cumplimiento](compliance-score-calculation.md#action-types-and-points).

Seleccione una acción de mejora para ver su página de detalles y seleccione el vínculo **Iniciar ahora** para abrir la solución para realizar acciones.

### <a name="microsoft-actions-tab"></a>Pestaña Acciones de Microsoft

La pestaña Acciones de Microsoft aparece para las evaluaciones basadas en plantillas que admiten productos de Microsoft. Enumera todas las acciones de la evaluación administradas por Microsoft. En la lista se muestran los detalles clave de la acción, incluidos: estado de prueba, puntos que contribuyen a la puntuación de cumplimiento general, normativas y estándares asociados, solución aplicable, tipo de acción y familia de control. Seleccione una acción de mejora para ver su página de detalles.

Obtenga más información sobre [cómo se realiza el seguimiento y la puntuación de los controles y las acciones de mejora.](compliance-score-calculation.md)

## <a name="accept-updates-to-assessments"></a>Aceptar actualizaciones de evaluaciones

Cuando una actualización esté disponible para una evaluación, verá una notificación y tendrá la opción de aceptar la actualización o aplazarla más adelante.

Las actualizaciones están disponibles para evaluaciones basadas en plantillas de Microsoft, como las diseñadas para su uso con Microsoft 365. Si su organización usa plantillas universales para evaluar otros productos, es posible que no se admita la herencia. Para obtener más información, consulte [Extensión de plantillas de evaluación](compliance-manager-templates-extend.md).

### <a name="what-causes-an-update"></a>¿Qué provoca una actualización?

Una actualización de evaluación se produce cuando hay cambios de plantilla subyacentes que afectan a la puntuación. Los cambios pueden implicar el ajuste de la asignación de controles u otras instrucciones basadas en cambios normativos o cambios en el producto. Las actualizaciones de evaluación pueden originarse desde su organización (por ejemplo, cuando [se modifica una plantilla personalizada](compliance-manager-templates-modify.md)) y desde Microsoft.

Si Microsoft actualiza una plantilla del Administrador de cumplimiento que ha extendido, la evaluación heredará esas actualizaciones una vez que las acepte. La evaluación conservará los atributos adicionales que aplicó a la evaluación cuando la extendió.

Las evaluaciones personalizadas que cree no reciben ninguna actualización de plantilla de Microsoft. Las evaluaciones personalizadas pueden recibir actualizaciones de acciones de mejora, pero las actualizaciones de Microsoft para controlar la asignación entre evaluaciones y acciones de mejora no se aplican a las plantillas personalizadas.

> [!NOTE]
> Las actualizaciones de las evaluaciones solo se aplican en el nivel de grupo. Si tiene dos evaluaciones compiladas a partir de la misma plantilla que existen en dos grupos diferentes, cada evaluación tendrá una notificación de actualización pendiente y tendrá que aceptar la actualización de cada evaluación de su grupo respectivo individualmente.

#### <a name="where-youll-see-assessment-update-notifications"></a>Donde verá las notificaciones de actualización de evaluación

La página de detalles de la evaluación también muestra una etiqueta **de actualización pendiente** junto a la evaluación con una actualización. Seleccione esa evaluación para acceder a su página de detalles.

Un mensaje situado cerca de la parte superior de la página de detalles de la evaluación muestra que hay una actualización disponible para esa evaluación. Seleccione el botón **Revisar actualización** del banner para revisar los cambios específicos y aceptar o aplazar la actualización.

La página de detalles de la evaluación también puede enumerar las acciones de mejora que tienen una etiqueta **de actualización Pendiente** junto a ellas. Estas actualizaciones son para cambios específicos en las propias acciones de mejora y deben aceptarse por separado. Visite [Aceptación de actualizaciones para acciones de mejora](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions) para obtener más información.

#### <a name="review-update-to-accept-or-defer"></a>Revisión de la actualización para aceptar o aplazar

Después de seleccionar **Revisar actualización** en la página de detalles de la evaluación, aparece un panel flotante en el lado derecho de la pantalla. El panel flotante proporciona los detalles clave siguientes sobre la actualización pendiente:

- Título de la plantilla
- Origen de la actualización (Microsoft, su organización o un usuario específico)
- Fecha de creación de la actualización
- Información general que explica la actualización
- Detalles específicos sobre los cambios, incluido el impacto en la puntuación de cumplimiento, la cantidad de progreso hacia la finalización de la evaluación y el número específico de cambios en las acciones y controles de mejora.

Al seleccionar el vínculo **Plantilla actualizada**, se descargará un archivo Excel que contiene datos de control para la versión de la plantilla con las actualizaciones pendientes. Al seleccionar el vínculo **Plantilla actual** se descarga un archivo de la plantilla existente sin los cambios.

Para aceptar la actualización y realizar los cambios en la evaluación, seleccione **Aceptar actualización**. Los cambios aceptados son permanentes.

Si selecciona **Cancelar**, la actualización no se aplicará a la evaluación. Sin embargo, seguirá viendo la notificación **De actualización pendiente** hasta que acepte la actualización.

**Por qué se recomienda aceptar actualizaciones**

Aceptar actualizaciones ayuda a garantizar que tiene las instrucciones más actualizadas sobre el uso de soluciones y la adopción de las acciones de mejora adecuadas para ayudarle a cumplir los requisitos de la certificación en cuestión.

**Por qué es posible que quiera aplazar una actualización**

Si está en medio de completar una evaluación, es posible que desee asegurarse de que ha terminado de trabajar en ella antes de aceptar una actualización de la evaluación que podría interrumpir la asignación de controles. Para aplazar la actualización más adelante, seleccione **Cancelar** en el panel flotante Revisar actualización.

## <a name="export-an-assessment-report"></a>Exportación de un informe de evaluación

Puede exportar una evaluación a un archivo de Excel para las partes interesadas de cumplimiento de su organización o para auditores y reguladores externos. En la página de detalles de la evaluación, seleccione el botón **Generar informe** situado cerca de la parte superior de la página, que crea un archivo Excel que puede guardar y compartir.

El informe es una instantánea de la evaluación a partir de la fecha y hora de la exportación. Contiene los detalles de los controles administrados por usted y Microsoft, incluidos el estado de implementación, la fecha de prueba y los resultados de las pruebas.

## <a name="delete-an-assessment"></a>Eliminación de una evaluación

Al eliminar una evaluación, se quita de la lista de la página de evaluaciones. Tenga en cuenta estos puntos importantes sobre la eliminación de evaluaciones:

- **La eliminación de una evaluación es permanente; no puedes recuperarlo.** Si quiere volver a usar la misma evaluación, tendrá que volver a crearla.
- Si las acciones de mejora de la evaluación no aparecen en ninguna otra evaluación, se eliminarán cuando se elimine la evaluación.
- Se recomienda [exportar un informe](#export-an-assessment-report) de la evaluación antes de eliminarlo de forma permanente.

Para eliminar una evaluación, siga estos pasos:

1. En **la página de evaluaciones** , seleccione la evaluación que desea eliminar para abrir la página de detalles de esa evaluación.

2. Seleccione **Eliminar evaluación** en la esquina superior derecha de la pantalla.

3. Aparecerá una ventana que le pedirá que confirme que desea eliminar permanentemente la evaluación. Seleccione **Eliminar evaluación** para cerrar la ventana. Obtendrá una ventana de confirmación de que la evaluación se eliminó del Administrador de cumplimiento.

> [!NOTE]
> No puede eliminar todas las evaluaciones. Las organizaciones necesitan al menos una evaluación para que el Administrador de cumplimiento funcione correctamente. Si la evaluación que desea eliminar es la única, agregue otra evaluación antes de eliminar la otra.
