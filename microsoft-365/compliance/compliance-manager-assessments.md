---
title: Creación y administración de evaluaciones en el administrador de cumplimiento de Microsoft
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
description: Cree evaluaciones en el administrador de cumplimiento de Microsoft para ayudarle a cumplir los requisitos de las regulaciones y las certificaciones que son importantes para su organización.
ms.openlocfilehash: 5bbdba66d2288c173827062aade3bbd196d77040
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204541"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a>Creación y administración de evaluaciones en el administrador de cumplimiento

**En este artículo:** Obtenga información sobre cómo personalizar el administrador de cumplimiento para su organización mediante la creación y administración de **evaluaciones**. En este artículo se explica cómo crear evaluaciones, cómo organizarlas en **grupos**, cómo trabajar con **controles**, cómo aceptar **actualizaciones**y cómo exportar **informes**de evaluación.

> [!IMPORTANT]
> Las evaluaciones disponibles para la organización dependen del contrato de licencia. [Revise los detalles](https://go.microsoft.com/fwlink/?linkid=2132371).

## <a name="introduction-to-assessments"></a>Introducción a las evaluaciones

El administrador de cumplimiento le ayuda a administrar el cumplimiento de las evaluaciones de las regulaciones y las certificaciones que se aplican a su organización. Las evaluaciones son agrupaciones de controles de una normativa, estándar o Directiva específica. El administrador de cumplimiento facilita el seguimiento del cumplimiento, ya que proporciona evaluaciones predefinidas que cubren una variedad de normativas y certificaciones regionales y de la industria.

Cada evaluación se crea a partir de una [plantilla de evaluación](compliance-manager-templates.md). Las plantillas sirven como un marco que contiene los controles necesarios, las acciones de mejora y las acciones de Microsoft para completar la evaluación. La configuración de las evaluaciones más relevantes para su organización puede ayudarle a implementar directivas y procedimientos operativos para limitar el riesgo de cumplimiento.

Todas las evaluaciones se enumeran en la página evaluaciones. Obtenga más información sobre [Cómo filtrar la vista de sus evaluaciones e interpretar los Estados de estado](compliance-manager-setup.md#assessments-page).

## <a name="data-protection-baseline-default-assessment"></a>Evaluación predeterminada de línea base de protección de datos

Para empezar, Microsoft proporciona una evaluación **predeterminada** en el administrador de cumplimiento para la **línea base de protección de datos 365 de Microsoft**. Esta evaluación de línea base tiene un conjunto de controles para normas y estándares clave para la protección de datos y el gobierno de datos general. Esta base dibuja los elementos principalmente desde NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Normalization), así como de FedRAMP (programa federal de administración de riesgos y autorización) y RGPD (norma general de protección de datos de la Unión Europea).

Esta evaluación se usa para calcular la puntuación de cumplimiento inicial la primera vez que llega al administrador de cumplimiento, antes de configurar otras evaluaciones. El administrador de cumplimiento recopila las señales iniciales de las soluciones de Microsoft 365. Ver? a simple vista sobre el rendimiento de su organización con respecto a los estándares y regulaciones clave de protección de datos y ver las acciones de mejora sugeridas que deben tomarse.

El administrador de cumplimiento resulta más útil a la hora de crear y administrar sus propias evaluaciones para satisfacer las necesidades específicas de su organización.

## <a name="assessment-creation-overview"></a>Información general sobre la creación de evaluaciones

Hay tres formas de configurar evaluaciones:

1. [Use una evaluación predefinida](#use-a-pre-built-assessment).
2. [Ampliar una evaluación predefinida para ajustarla a sus necesidades](#extend-a-pre-built-assessment).
3. [Cree su propia evaluación personalizada](#create-your-own-custom-assessment).

> [!NOTE]
> Solo los usuarios que tienen un rol de administrador global o de administrador de cumplimiento pueden crear y modificar evaluaciones. Obtenga más información sobre [los roles y los permisos](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

**Usar una evaluación predefinida**

Iniciar rápidamente el viaje de cumplimiento seleccionando una evaluación que ya esté configurada por el administrador de cumplimiento. Proporcionamos una amplia selección de [plantillas](compliance-manager-templates.md) para los reglamentos y las certificaciones que se alinean con las industrias, las regiones y los estándares comunes de protección de datos, como RGPD e ISO 27001. Las plantillas contienen los controles y las acciones de mejora para ayudarle a cumplir los requisitos de una certificación determinada. Se le pedirá que elija una plantilla cuando empiece a [crear una evaluación](#use-a-pre-built-assessment).

**Ampliar una evaluación predefinida para ajustarla a sus necesidades**

Puede modificar una evaluación del administrador de cumplimiento (un proceso al que nos referimos como "extender") agregando sus propios controles y acciones para que se adapten mejor a las necesidades de su organización. Por ejemplo, si por lo general necesita cumplir con la ley HIPAA pero requiere protección de datos o controles de seguridad adicionales, puede ampliar nuestra plantilla de HIPAA agregando sus propios controles a la misma. Vea las instrucciones para [ampliar una evaluación predefinida](#extend-a-pre-built-assessment).

**Crear su propia evaluación personalizada**

Puede crear su propia evaluación completamente desde cero para realizar un seguimiento preciso de las necesidades de su organización. La creación de su propia evaluación requiere que primero cree su propia plantilla para la evaluación en Compliance Manager. Vea las instrucciones para [crear su propia evaluación personalizada](#create-your-own-custom-assessment).

## <a name="understand-groups-before-creating-assessments"></a>Descripción de los grupos antes de crear evaluaciones

Antes de crear o modificar evaluaciones, es importante comprender cómo funcionan los grupos. Al crear una evaluación, deberá asignarla a un grupo durante el proceso. Por ello, recomendamos planificar una estrategia de agrupación para las evaluaciones antes de crear evaluaciones.

### <a name="what-are-groups"></a>¿Qué son los grupos?

Los grupos son contenedores que permiten organizar las evaluaciones. Puede agrupar las evaluaciones de forma lógica para usted, por ejemplo, por año o reglamento, o en función de las divisiones o geografías de su organización. A continuación se muestran ejemplos de dos grupos y sus evaluaciones subyacentes:

- **FFIEC es la evaluación 2020**
  - FFIEC ES
- **Evaluaciones de privacidad y seguridad de datos**
  - ISO 27001:2013
  - ISO 27018:2014

Cuando dos evaluaciones distintas en el mismo grupo comparten acciones de mejora que usted administra, las actualizaciones que realice en los detalles de implementación o el estado de una acción se sincronizarán automáticamente con la misma acción en cualquier otra evaluación del grupo. Esta sincronización le permite implementar una acción de mejora y cumplir varios requisitos en varias regulaciones.

### <a name="how-to-create-a-group"></a>Cómo crear un grupo

Un grupo se crea durante el proceso de [creación de una nueva evaluación](#to-create-an-assessment).

No se pueden crear grupos como entidades independientes. Un grupo debe contener al menos una evaluación. Para crear un grupo, primero debe crear una evaluación para colocarla en el grupo.

### <a name="what-to-know-when-working-with-groups"></a>Qué saber al trabajar con grupos

- Los nombres de grupo deben ser únicos dentro de la organización.
- Los grupos no tienen propiedades de seguridad. Todos los permisos están asociados con evaluaciones.
- Una vez que haya agregado una evaluación a un grupo, no se podrá cambiar la agrupación.
- Los controles de evaluación relacionados en diferentes evaluaciones dentro del mismo grupo se actualizan automáticamente cuando se completan.
- Si agrega una nueva evaluación a un grupo existente, la información común de las evaluaciones de ese grupo se copia en la nueva evaluación.
- Los grupos pueden contener evaluaciones para la misma certificación o reglamentación, pero cada grupo solo puede contener una evaluación para un par de certificación de producto específico. Por ejemplo, un grupo no puede contener dos evaluaciones para Office 365 y NIST CSF. Un grupo puede contener varias evaluaciones para el mismo producto solo si la certificación o el Reglamento correspondiente para cada uno es diferente.
- La eliminación de una evaluación rompe la relación entre esa evaluación y el grupo.
- Los grupos no se pueden eliminar.
- Cuando se realiza un cambio en una mejora que aparece en varios grupos, el cambio se refleja en todas las instancias de dicha acción de mejora.

## <a name="use-a-pre-built-assessment"></a>Usar una evaluación predefinida

Hay dos puntos de partida para crear una evaluación a partir de una plantilla del administrador de cumplimiento.

Puede iniciar el proceso desde la página evaluaciones seleccionando el botón **Agregar evaluación** y, a continuación, trabajando con el Asistente para la creación de la evaluación. A continuación se indican los pasos para este proceso.

También puede empezar desde la página de plantillas de evaluación buscando la plantilla que desea y seleccionándola en la lista para llegar a la página de detalles. En la página Detalles de la plantilla, seleccione **crear evaluación**. A continuación, tendrá que especificar el asistente con la plantilla que ya está seleccionada.

### <a name="to-create-an-assessment"></a>Para crear una evaluación

1. Saber a qué grupo asignará su evaluación o estar preparado para crear uno nuevo para esta evaluación. [Obtenga más información sobre los grupos](#understand-groups-before-creating-assessments).  

2. Vaya a la página **evaluaciones** del administrador de cumplimiento y seleccione **Agregar evaluación**. Un asistente de evaluación aparecerá en un panel flotante de gran tamaño.

3. **Seleccione una plantilla**: elija una plantilla que sirva como base para la evaluación. Seleccione el botón de opción situado junto a la plantilla elegida y, a continuación, seleccione **siguiente**.

4. **Nombre y Grupo:** Escriba un nombre para la evaluación en el campo Nombre de la **evaluación** . Los nombres de evaluación deben ser únicos dentro de los grupos. Si el nombre de la evaluación coincide con el nombre de otra evaluación de un grupo determinado, recibirá un error que le pedirá que cree un nombre diferente.

5. Asigne su evaluación a un grupo. Puede:
    - Seleccione **usar grupo existente** para asignarlo a un grupo que ya ha creado; o
    - Seleccione **crear nuevo grupo** para crear un nuevo grupo y asignarle esta evaluación:
        - Determine un nombre para el grupo y escríbalo en el campo situado debajo del botón de radio.
        - Puede **copiar datos de un grupo existente**, como la implementación y los documentos y los detalles de prueba, seleccionando los cuadros apropiados.

    Cuando termine, seleccione **siguiente**.

6. **Revisión y finalización:** La última pantalla del asistente muestra la plantilla, el nombre y el grupo elegidos para la evaluación. Puede editar cualquiera de estos valores en los vínculos de la pantalla, que le llevarán a los pasos necesarios en el asistente. Cuando esté listo, seleccione **crear evaluación**.

7. La siguiente pantalla confirma que ha creado la nueva evaluación correctamente. Seleccione **listo** para cerrar el asistente y la página de detalles de la nueva evaluación aparecerá en la pantalla.

Si ve que en la pantalla **se ha producido un error** en la evaluación tras seleccionar **crear evaluación**, **Seleccione volver a** crear la evaluación.

Puede cambiar el nombre de la evaluación después de crearla seleccionando el botón **Editar nombre** en la esquina superior derecha de la página de [detalles](#monitor-assessment-progress-and-controls)de la evaluación.

## <a name="extend-a-pre-built-assessment"></a>Ampliación de una evaluación predefinida

Puede modificar una evaluación predefinida agregando sus propios controles y acciones de mejora a la plantilla de la evaluación. Este proceso se denomina "extensión de una plantilla de Microsoft" en el administrador de cumplimiento. Al ampliar la plantilla de una evaluación, recibirá todas las actualizaciones que Microsoft haya lanzado, lo que puede ocurrir cuando se produzcan cambios en la reglamentación o producto relacionado (vea [aceptar actualizaciones para las evaluaciones](#accepting-updates-to-assessments)).

Completará este proceso comenzando por la página de **plantillas de evaluación** en lugar de la página de **evaluaciones** .

**Antes de empezar**

Para preparar este proceso, primero deberá ensamblar una hoja de cálculo de Excel con formato especial para importar los datos de plantilla necesarios. Hay requisitos especiales para los [archivos de Excel con formato](compliance-manager-templates.md#formatting-your-template-data-with-excel) que se usan en el proceso de extensión. Consulte estos puntos adicionales para ayudar a evitar errores en el proceso de importación:

- La hoja de cálculo debe contener solo las acciones y los controles que desea agregar a la evaluación. 
- La hoja de cálculo no puede contener ninguno de los controles o acciones que ya existen en la evaluación que desea modificar.
- Considere la posibilidad de incluir "Extension" en el título de la plantilla, por ejemplo, "RGPD – [nombre de la compañía] extensión". Esto hace que sea más fácil identificar en la lista de la página de **plantillas de evaluación** , como se diferencia de la plantilla estándar proporcionada por Microsoft o de una plantilla personalizada con un nombre similar.

Después de dar formato a la hoja de cálculo, siga los pasos siguientes.

**Pasos para ampliar una plantilla del administrador de cumplimiento**

1. Vaya a la página de **plantillas de evaluación** y seleccione **crear nueva plantilla**. Se abrirá un asistente para la creación de plantillas.

2. Elija el tipo de plantilla que desea crear. En este caso, seleccione **extender una plantilla de Microsoft**y, a continuación, **Seleccione**.

3. Aparece un panel flotante de selección de plantilla en el lado derecho de la pantalla. Usar la **búsqueda** para aplicar filtros para localizar la plantilla que desea

4. Una vez que haya encontrado la plantilla, seleccione el botón de opción a la izquierda del nombre y, a continuación, seleccione **Guardar**.

5. La siguiente pantalla muestra la plantilla que ha seleccionado. Si es correcta, seleccione **siguiente**. (Si es incorrecto, elija **seleccionar una plantilla diferente** para volver a elegir).

6. En la pantalla **Cargar archivo** , seleccione **examinar** para buscar y cargar el archivo de Excel con formato que contiene todos los datos de plantilla necesarios.

7. Si no hay problemas con el archivo, en la pantalla siguiente se muestra el nombre del archivo cargado. Seleccione **siguiente** para continuar (si necesita cambiar el archivo, seleccione **cargar un archivo diferente**).

    - Si hay un problema con el archivo, un mensaje de error en la parte superior explica lo que es incorrecto. Tendrás que corregir y volver a cargar el archivo. Se producirán errores si la hoja de cálculo tiene un formato incorrecto o si hay información no válida en determinados campos.
 
8. La pantalla **revisión y finalización** muestra el número de acciones de mejora y los controles y la puntuación máxima para la plantilla. Cuando esté listo para aprobar, seleccione **siguiente**. (Si necesita realizar cambios, seleccione **cargar un archivo diferente**).

9. La última pantalla confirma que se ha creado una plantilla nueva. Seleccione **listo** para salir del asistente.

10. Llegará a la página de detalles de la nueva plantilla. Desde aquí, puede crear la evaluación seleccionando **crear evaluación**. Para obtener instrucciones, comience en el paso #4 en las instrucciones de creación de la [evaluación anterior](#to-create-an-assessment).

## <a name="create-your-own-custom-assessment"></a>Crear su propia evaluación personalizada

La creación de una evaluación personalizada en el administrador de cumplimiento requiere que cree su propia plantilla. Para crear su propia plantilla, primero debe ensamblar una hoja de cálculo de Excel con formato para importar los datos de plantilla necesarios. También ayuda a decidir por adelantado a qué grupo asignará la evaluación al crearla (Obtenga más información sobre los [grupos](#what-are-groups)).

**Siga los pasos siguientes para crear su evaluación personalizada:**

1. **Dar formato al archivo de Excel.** Comience por dar formato a los datos de la plantilla en una hoja de cálculo de Excel siguiendo [estas instrucciones](compliance-manager-templates.md#formatting-your-template-data-with-excel).

2. **Cree su plantilla** siguiendo [estas instrucciones](compliance-manager-templates.md#create-a-new-template).

3. **Cree la evaluación** a partir de la plantilla. Para empezar, abra la página de detalles de la plantilla y seleccione **crear evaluación**, o vaya a la página **evaluaciones** y seleccione **crear evaluación**.

4. Un asistente para la creación de evaluaciones aparecerá en un panel flotante de gran tamaño. Desde aquí, puede seguir las instrucciones que comienzan en el paso #3 de las [instrucciones de creación](#to-create-an-assessment)de la evaluación, usando su nueva plantilla personalizada para la evaluación.

## <a name="delete-an-assessment"></a>Eliminación de una evaluación

Al eliminar una evaluación, se quita de la lista de la página evaluaciones. Tenga en cuenta estos puntos importantes sobre la eliminación de evaluaciones:

- **La eliminación de una evaluación es permanente; no se puede volver a obtener.** Si desea volver a usar la misma evaluación, tendrá que volver a crearla.
- Si las acciones de mejora de la evaluación no aparecen en ninguna otra evaluación, se eliminarán cuando se elimine la evaluación.
- Le recomendamos que [exporte un informe](#export-an-assessment-report) de la evaluación antes de eliminarlo de forma permanente.

Para eliminar una evaluación, siga los pasos que se indican a continuación:

1. En la página **evaluaciones** , seleccione la evaluación que desea eliminar para abrir la página de detalles de la evaluación.

2. Seleccione **eliminar evaluación** en la esquina superior derecha de la pantalla.

3. Aparecerá una ventana en la que se le pedirá que confirme que desea eliminar la evaluación de forma permanente. Seleccione **eliminar evaluación** para cerrar la ventana. Recibirá una ventana de confirmación de que la evaluación se eliminó del administrador de cumplimiento.

Si elimina la única evaluación en un grupo, ese grupo también se elimina del administrador de cumplimiento.

## <a name="monitor-assessment-progress-and-controls"></a>Supervisión del progreso y los controles de la evaluación

Cada evaluación tiene una página de detalles que ofrece una vista general del progreso para completar la evaluación. La página muestra el progreso de la finalización de los controles y el estado de prueba de las acciones de mejora de claves dentro de esos controles.

### <a name="overview-tab"></a>Ficha Información general

La ficha Información general contiene un gráfico que muestra el porcentaje hacia la finalización de la evaluación. Este gráfico contiene un desglose de los puntos de las acciones que posee, así como los puntos de las acciones que posee Microsoft, para que pueda ver cuántos puntos necesita para completar la evaluación.

Las acciones de mejora clave para los controles de la evaluación se muestran por orden de mayor impacto potencial para obtener puntos. El gráfico asociado detalla el estado de pruebas agregadas de las acciones de mejora para que pueda evaluar rápidamente lo que se ha probado y lo que todavía debe realizarse.

Para acceder a acciones de mejora individuales, visite la pestaña **controles** o la pestaña **acciones de mejora** .

### <a name="controls-tab"></a>Pestaña Controles

La ficha controles muestra información detallada de cada control asignado a la evaluación. El gráfico de **desglose del estado** de un control muestra el estado de los controles por familia, por lo que puede ver de un vistazo qué agrupaciones de controles necesitan atención.

Debajo del gráfico, una tabla muestra información detallada sobre cada control dentro de la evaluación. Los controles se agrupan por familia de controles. Expanda cada nombre de familia para mostrar los controles individuales que contiene. La información que se muestra para cada control incluye:

- **Título del control**
- **Status**: refleja el estado de prueba de las acciones de mejora en el control. 
    - **Passed** : todas las acciones de mejora tienen el estado de prueba "superado" o al menos una se pasa y el resto están "fuera de ámbito"
    -  **Failed** : al menos una acción de mejora tiene un estado de prueba de "error"
    - **Ninguna** : no se han probado todas las acciones de mejora
    - **Fuera de ámbito** : todas las acciones de mejora están fuera del ámbito de esta evaluación
    - Las acciones de mejora del **progreso** tienen un Estado distinto de los enumerados anteriormente, que pueden incluir "en curso", "crédito parcial" o "no detectado"
- **Identificador de control**: el número de identificación del control, asignado por su normativa, estándar o directiva correspondiente.
- **Puntos logrados**: número de puntos obtenidos por la realización de acciones, fuera del número total de puntos alcanzables 
- **Sus acciones**: el número total de acciones realizadas en el número total de acciones que se van a realizar
- **Acciones de Microsoft**: el número de acciones completadas por Microsoft 

Para ver los detalles de un control, selecciónelo en la fila de la tabla. La página de detalles del control muestra un gráfico que indica el estado de prueba de las acciones dentro de ese control. Una tabla debajo del gráfico muestra las acciones de mejora de clave para ese control.

Seleccione una acción de mejora en la lista para profundizar en la página de detalles de la acción de mejora. Las páginas de detalles muestran el estado de la prueba, las notas de implementación y el inicio en la solución recomendada.

### <a name="your-improvement-actions-tab"></a>Ficha acciones de mejora

La pestaña de las acciones de mejora enumera todos los controles de la evaluación que administra la organización. La barra de estado detalla el estado de pruebas agregadas de las acciones de mejora en la evaluación para que pueda evaluar rápidamente lo que se ha probado y lo que todavía debe realizarse. Debajo de la barra se encuentra la lista completa de acciones de mejora y detalles clave, incluidos: el estado de las pruebas, el número de puntos potenciales y obtenidos, las regulaciones y estándares asociados, la solución aplicable, el tipo de acción y la familia de controles. Obtenga más información sobre [cómo las acciones contribuyen a la puntuación de cumplimiento](compliance-score-calculation.md#action-types-and-points).

Seleccione una acción de mejora para ver su página de detalles y seleccione el vínculo **iniciar ahora** para abrir la solución para realizar la acción.

### <a name="microsoft-actions-tab"></a>Ficha acciones de Microsoft

La ficha acciones de Microsoft enumera todas las acciones de la evaluación administradas por Microsoft. La lista muestra los detalles de la acción clave, entre los que se incluyen: estado de prueba, puntos que contribuyen a la puntuación de cumplimiento general, las regulaciones y estándares asociados, la solución aplicable, el tipo de acción y la familia de controles. Seleccione una acción de mejora para ver su página de detalles.

Obtenga más información sobre [cómo se realiza el seguimiento y la puntuación de los controles y las acciones de mejora.](compliance-score-calculation.md)

## <a name="accepting-updates-to-assessments"></a>Aceptar actualizaciones para las evaluaciones

Cuando haya una actualización disponible para una evaluación, verá una notificación y tendrá la opción de aceptar la actualización o aplazarla en un momento posterior.

### <a name="what-causes-an-update"></a>Qué causa una actualización

Una actualización de evaluación se produce cuando hay cambios de plantilla subyacentes que afectan a la puntuación. Los cambios pueden implicar el ajuste de la asignación de control u otras directrices basadas en cambios normativos o cambios en los productos. Las actualizaciones de la evaluación pueden proceder de su organización (por ejemplo, cuando [se modifica una plantilla personalizada](compliance-manager-templates.md#modify-a-template)), así como de Microsoft.

Si Microsoft actualiza una plantilla del administrador de cumplimiento que amplió, su evaluación heredará esas actualizaciones una vez que las acepte. La evaluación conservará los atributos adicionales aplicados a la evaluación cuando la amplió.

Las evaluaciones personalizadas que cree no recibirán ninguna actualización de plantillas de Microsoft. Las evaluaciones personalizadas pueden recibir actualizaciones de acciones de mejora, pero las actualizaciones de Microsoft para controlar la asignación entre las evaluaciones y las acciones de mejora no se aplican a las plantillas personalizadas.

> [!NOTE]
> Las actualizaciones a las evaluaciones solo se aplican en el nivel de grupo. Si tiene dos evaluaciones creadas a partir de la misma plantilla que existen en dos grupos diferentes, cada evaluación tendrá una notificación de actualización pendiente y tendrá que aceptar la actualización de cada evaluación en su grupo respectivo de forma individual.

#### <a name="where-youll-see-assessment-update-notifications"></a>Dónde verá las notificaciones de actualización de evaluación

La página Detalles de la evaluación también muestra una etiqueta de **actualización pendiente** junto a la evaluación con una actualización. Seleccione la evaluación para obtener acceso a la página de detalles.

Un mensaje situado cerca de la parte superior de la página Detalles de la evaluación muestra que hay una actualización disponible para dicha evaluación. Seleccione el botón **Actualizar revisión** en el banner para revisar los cambios específicos y aceptar o aplazar la actualización.

La página Detalles de la evaluación también puede enumerar las acciones de mejora que tienen una etiqueta de **actualización pendiente** junto a ellas. Estas actualizaciones son para cambios específicos a las acciones de mejora y deben aceptarse por separado. Visite [aceptar actualizaciones para mejorar las acciones](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions) para obtener más información.

#### <a name="review-update-to-accept-or-defer"></a>Revisión de la actualización para aceptar o aplazar

Después de seleccionar **revisar actualización** en la página Detalles de la evaluación, aparece un panel flotante en el lado derecho de la pantalla. El panel de control flotante proporciona los detalles de la clave siguiente sobre la actualización pendiente:

- El título de la plantilla
- Origen de la actualización (Microsoft, su organización o un usuario específico)
- La fecha en la que se creó la actualización
- Información general que explica la actualización
- Detalles específicos sobre los cambios, incluido el impacto en la puntuación de cumplimiento, la cantidad de progreso hasta la finalización de la evaluación y el número específico de cambios en las acciones y los controles de mejora.

Al seleccionar el vínculo **plantilla actualizada** se descargará un archivo de Excel que contiene los datos de control para la versión de la plantilla con las actualizaciones pendientes. Al seleccionar el vínculo de la **plantilla actual** , se descarga un archivo de la plantilla existente sin los cambios.

Para aceptar la actualización y realizar los cambios en la evaluación, seleccione **Aceptar actualización**. Los cambios aceptados son permanentes.

Si selecciona **Cancelar**, la actualización no se aplicará a la evaluación. Sin embargo, seguirá viendo la notificación de **actualización pendiente** hasta que acepte la actualización.

**Por qué se recomienda aceptar actualizaciones**

La aceptación de actualizaciones le ayudará a disponer de las instrucciones más actualizadas sobre el uso de soluciones y la realización de las acciones de mejora adecuadas para ayudarle a cumplir los requisitos de la certificación disponibles.

**Por qué es posible que quiera aplazar una actualización**

Si está realizando una evaluación, es posible que desee asegurarse de que ha terminado de trabajar en él antes de aceptar una actualización de la evaluación que pueda interrumpir la asignación de controles. Puede aplazar la actualización para una hora posterior seleccionando **Cancelar** en el panel revisar control flotante de actualización.

## <a name="export-an-assessment-report"></a>Exportación de un informe de evaluación

Puede exportar una evaluación a un archivo de Excel para las partes interesadas de cumplimiento de su organización o para los auditores externos y los reguladores. En la página Detalles de la evaluación, seleccione el botón **generar informe** cerca de la parte superior de la página, que crea un archivo de Excel que puede guardar y compartir.

El informe es una instantánea de la evaluación a partir de la fecha y la hora de la exportación. Contiene los detalles de los controles administrados tanto por usted como por Microsoft, incluidos el estado de la implementación, la fecha de la prueba y los resultados de las pruebas.