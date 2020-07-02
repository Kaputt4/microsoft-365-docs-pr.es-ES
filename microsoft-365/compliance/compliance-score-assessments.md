---
title: Personalización de la puntuación de cumplimiento de Microsoft con evaluaciones
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
description: Personalización de la puntuación de cumplimiento de Microsoft mediante la creación de evaluaciones que le ayuden a administrar el cumplimiento de la organización.
ms.openlocfilehash: 45a5e76aa4f6581146ded510f75d772c202751ee
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023313"
---
# <a name="customize-compliance-score-preview-with-assessments"></a>Personalización de la puntuación de cumplimiento (versión preliminar) con evaluaciones

**En este artículo:** Obtenga información sobre cómo personalizar la puntuación de cumplimiento mediante la configuración de **evaluaciones**listas para usar. Obtenga información sobre cómo modificar la **plantilla** para una evaluación y cree sus propias evaluaciones personalizadas para que se adapten a las necesidades de su organización. En este artículo también se explica cómo organizar las evaluaciones en **grupos**, trabajar con **controles**y exportar **informes**de evaluación.

## <a name="introduction-to-assessments"></a>Introducción a las evaluaciones

La puntuación de cumplimiento le ayudará a administrar el cumplimiento de las evaluaciones de las regulaciones y las certificaciones que se aplican a su organización. Las evaluaciones son agrupaciones de controles de una normativa, estándar o Directiva específica. La puntuación de cumplimiento permite comenzar fácilmente el seguimiento del cumplimiento, ya que proporciona evaluaciones que cubren una variedad de regulaciones y reglamentaciones regionales y de la industria.

Cada evaluación se crea a partir de una plantilla, que actúa como un marco que contiene los controles necesarios y las acciones de mejora para completar la evaluación. La configuración de las evaluaciones más relevantes para su organización ayuda a asegurarse de que está implementando directivas y procedimientos operativos que pueden limitar el riesgo de cumplimiento.

Todas las evaluaciones se enumeran en la página evaluaciones. [Obtenga más información](compliance-score-setup.md#assessments-page) sobre cómo filtrar la vista de sus evaluaciones e interpretar los Estados de estado.

## <a name="data-protection-baseline-default-assessment"></a>Evaluación predeterminada de línea base de protección de datos

Para empezar, Microsoft proporciona una evaluación **predeterminada** de la puntuación de cumplimiento que contiene la línea base de protección de datos 365 de Microsoft. Esta línea base es un conjunto de controles que incluye normas y estándares clave para la protección de datos y el gobierno de datos general. Esta base dibuja los elementos principalmente desde NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Normalization), así como de FedRAMP (programa federal de administración de riesgos y autorización) y RGPD (norma general de protección de datos de la Unión Europea).

Esta evaluación se usa para calcular el resultado inicial la primera vez que se llega a la puntuación de cumplimiento, antes de configurar otras evaluaciones. La puntuación de cumplimiento recopila señales iniciales de las soluciones de Microsoft 365. Ver? a simple vista sobre el rendimiento de su organización con respecto a los estándares y regulaciones clave de protección de datos y ver las acciones de mejora sugeridas que deben tomarse.

Debido a que cada organización tiene necesidades específicas, la puntuación de cumplimiento depende de que configure y administre sus propias evaluaciones para ayudar a minimizar y mitigar el riesgo de la forma más completa posible.

## <a name="assessment-creation-overview"></a>Información general sobre la creación de evaluaciones

Hay tres formas de configurar evaluaciones:

1. Elija una evaluación lista para usar.
2. Modifique la plantilla de una evaluación para adaptarla a sus necesidades.
3. Cree su propia evaluación personalizada.

Los usuarios deben poseer una función de administrador global, administrador de cumplimiento, administrador de datos de cumplimiento o administrador de seguridad para poder crear o modificar evaluaciones. Obtenga más información sobre [los roles y los permisos](compliance-score-setup.md#set-user-permissions-and-assign-roles).

> [!NOTE]
> Las evaluaciones creadas o modificadas en la puntuación de cumplimiento también se reflejarán en el administrador de cumplimiento. Obtenga más información sobre la [relación entre la puntuación de cumplimiento y el administrador de cumplimiento](compliance-score.md#relationship-to-compliance-manager).

### <a name="ready-to-use-assessments"></a>Listo para usar evaluaciones

Iniciar rápidamente el viaje de cumplimiento eligiendo entre la puntuación de cumplimiento de la selección de [plantillas](compliance-score-templates.md) para crear evaluaciones. Las plantillas contienen los controles y las acciones de mejora necesarias para cada evaluación en particular. Las plantillas de puntuación de cumplimiento cubren los reglamentos y las certificaciones que se alinean con las industrias, las regiones y los estándares comunes de protección de datos, como RGPD e ISO 27001.

**Para configurar una evaluación**, elija una de las plantillas cuando empiece [a crear la evaluación desde el asistente](#create-an-assessment).

### <a name="modify-the-template-of-an-assessment"></a>Modificación de la plantilla de una evaluación

Puede modificar las plantillas de puntuación de cumplimiento para las evaluaciones a fin de que se adapten mejor a las necesidades de su organización. Por ejemplo, si por lo general necesita cumplir con HIPAA pero requiere protección de datos adicional o controles de seguridad, puede tomar nuestra plantilla HIPAA y agregar sus propios campos personalizados para crear una nueva evaluación que supervise el progreso en las formas que necesite. Durante la versión preliminar pública, tendrá que ir a administrador de cumplimiento para modificar las plantillas.

**Para modificar la plantilla de una evaluación**, siga estas instrucciones:

1. Vea la lista de [las plantillas](compliance-score-templates.md) disponibles en puntuación de cumplimiento para determinar cuál desea modificar.
2. Vea las [instrucciones del administrador de cumplimiento para personalizar una plantilla mediante el proceso de extensión](working-with-compliance-manager.md#customize-a-template-through-the-extension-process).
3. Una vez que haya creado la plantilla y la haya importado en Compliance Manager, podrá crear la nueva evaluación con la puntuación de cumplimiento. Siga el proceso de creación de la evaluación mediante el [Asistente para la creación de evaluaciones](#create-an-assessment).

> [!NOTE]
> Obtenga más información sobre la [relación entre la puntuación de cumplimiento y el administrador de cumplimiento](compliance-score.md#relationship-to-compliance-manager) durante la versión preliminar pública.

### <a name="create-your-own-custom-assessment"></a>Crear su propia evaluación personalizada

Puede crear su propia evaluación completamente desde cero para realizar un seguimiento preciso de las necesidades de su organización. Como en el proceso de modificación descrito anteriormente, para crear su propia evaluación es necesario que primero cree su propia plantilla para la evaluación en el administrador de cumplimiento.

**Para crear su propia evaluación personalizada**, siga estas instrucciones:

1. Lea cómo [crear su propia plantilla en el administrador de cumplimiento](working-with-compliance-manager.md#create-your-own-template-and-import-it-into-compliance-manager).
2. Una vez que haya creado la plantilla y la haya importado en Compliance Manager, podrá crear la nueva evaluación con la puntuación de cumplimiento. Siga el proceso de creación de la evaluación mediante el [Asistente para la creación de evaluaciones](#create-an-assessment).

## <a name="understand-groups-before-creating-assessments"></a>Descripción de los grupos antes de crear evaluaciones

Antes de crear o modificar evaluaciones, es importante comprender cómo funcionan los grupos. Al crear una evaluación, deberá asignarla a un grupo durante ese proceso. Por lo tanto, recomendamos planificar una estrategia de agrupación para las evaluaciones antes de crear evaluaciones.

### <a name="what-are-groups"></a>¿Qué son los grupos?

Los grupos son contenedores que permiten organizar las evaluaciones. Puede agrupar las evaluaciones de forma lógica para usted, por ejemplo, por año o reglamento, o en función de las divisiones o geografías de su organización. A continuación se muestran ejemplos de dos grupos y sus evaluaciones subyacentes:

- **FFIEC es evaluaciones 2020**
  - Office 365 + FFIEC es
  - Intune + FFIEC es
- **Evaluaciones de privacidad y seguridad de datos**
  - Office 365 + ISO 27001:2013
  - Office 365 + ISO 27018:2014

Cuando dos evaluaciones distintas en el mismo grupo comparten acciones de mejora que usted administra, las actualizaciones que realice en los detalles de implementación o el estado de una acción se sincronizarán automáticamente con la misma acción en cualquier otra evaluación del grupo. Esta sincronización le permite implementar una acción de mejora y cumplir varios requisitos en varias regulaciones.

### <a name="how-to-create-a-group"></a>Cómo crear un grupo

Un grupo se crea durante el proceso de [creación de una nueva evaluación](#create-an-assessment).

No se pueden crear grupos como entidades independientes; un grupo debe contener al menos una evaluación. Para crear un grupo, primero debe crear una evaluación para colocarla en el grupo.

### <a name="what-to-know-when-working-with-groups"></a>Qué saber al trabajar con grupos

- Los nombres de grupo deben ser únicos dentro de la organización.
- Los grupos no tienen propiedades de seguridad. Todos los permisos están asociados con evaluaciones.
- Una vez que agregue una evaluación a un grupo, no se podrá cambiar la agrupación.
- Los controles de evaluación relacionados en diferentes evaluaciones dentro del mismo grupo se actualizan automáticamente cuando se completan.
- Si agrega una nueva evaluación a un grupo existente, la información común de las evaluaciones de ese grupo se copia en la nueva evaluación.
- Los grupos pueden contener evaluaciones para la misma certificación o reglamentación, pero cada grupo solo puede contener una evaluación para un par de certificación de producto específico. Por ejemplo, un grupo no puede contener dos evaluaciones para Office 365 y NIST CSF. Un grupo puede contener varias evaluaciones para el mismo producto solo si la certificación o el Reglamento correspondiente para cada uno es diferente.
- La eliminación de una evaluación rompe la relación entre esa evaluación y el grupo.
- Los grupos no se pueden eliminar.
- Cuando se realiza un cambio en una mejora que aparece en varios grupos, el cambio se refleja en todas las instancias de dicha acción de mejora.

## <a name="create-an-assessment"></a>Crear una evaluación

Para crear una evaluación en la puntuación de cumplimiento, siga los pasos que se indican a continuación:

1. En la página evaluaciones, seleccione **Agregar evaluación**. Un asistente de evaluación aparecerá en un panel flotante de gran tamaño.

2. **Seleccione una plantilla:** Elija una plantilla que sirva como base para la evaluación. Puede elegir una plantilla preparada para usar o una plantilla que haya modificado o creado. Seleccione el botón de opción situado junto a la plantilla elegida y, a continuación, seleccione **siguiente**.

> [!NOTE]
> Consulte [las instrucciones para crear y modificar plantillas](working-with-compliance-manager.md#templates), un proceso controlado en el administrador de cumplimiento.

3. **Nombre y Grupo:** Escriba un nombre para la evaluación en el campo Nombre de la **evaluación** . Los nombres de evaluación deben ser únicos dentro de los grupos. Si el nombre de la evaluación coincide con el nombre de otra evaluación de un grupo determinado, recibirá un error que le pedirá que cree un nombre diferente.

4. Asigne su evaluación a un grupo. Puede:
    - Seleccione **usar grupo existente** para asignarlo a un grupo que ya ha creado; o
    - Seleccione **crear nuevo grupo** para crear un nuevo grupo y asignarle esta evaluación. Determine un nombre para el grupo y escríbalo en el campo situado debajo del botón de radio.

5. **Revisión y finalización:** La última pantalla del asistente muestra la plantilla, el nombre y el grupo elegidos para la evaluación. Puede editar cualquiera de estos valores en los vínculos de la pantalla, que le llevarán a los pasos necesarios en el asistente. Cuando esté satisfecho con la configuración, seleccione **crear evaluación**.

6. La siguiente pantalla confirma que ha creado la nueva evaluación correctamente. Seleccione **listo** para cerrar el asistente y la página de detalles de la nueva evaluación aparecerá en la pantalla.

Si ve que en la pantalla **se ha producido un error** en la evaluación tras seleccionar **crear evaluación**, **Seleccione volver a** crear la evaluación.

## <a name="delete-an-assessment"></a>Eliminación de una evaluación

Al eliminar una evaluación, se quita de la lista de la página evaluaciones. **La eliminación de una evaluación es permanente; no se puede volver a obtener.** Si desea volver a realizar la misma evaluación, debe volver a crearla desde cero. Si las acciones de mejora en la evaluación no aparecen en ninguna otra evaluación, se eliminarán cuando se elimine la evaluación. Le recomendamos que exporte un informe de la evaluación antes de eliminarlo de forma permanente.

Para eliminar una evaluación, siga los pasos que se indican a continuación:

1. En la página evaluaciones, seleccione la evaluación que desea eliminar para abrir la página de detalles de la evaluación.
2. Seleccione **eliminar evaluación** en la esquina superior derecha de la pantalla.
3. Aparecerá una ventana en la que se le pedirá que confirme que desea eliminar la evaluación de forma permanente. Seleccione **eliminar evaluación** para cerrar la ventana. Recibirá una ventana de confirmación de que la evaluación se eliminó de la puntuación de cumplimiento.

Si elimina la única evaluación en un grupo, ese grupo también se elimina de la puntuación de cumplimiento.

## <a name="monitor-assessment-progress-and-controls"></a>Supervisión del progreso y los controles de la evaluación

Cada evaluación tiene una página de detalles que ofrece una vista general del progreso para completar la evaluación. La página muestra el progreso de la finalización de los controles y el estado de prueba de las acciones de mejora de claves dentro de esos controles.

### <a name="overview-tab"></a>Ficha Información general

La ficha Información general contiene un gráfico que muestra el porcentaje hacia la finalización de la evaluación. Este gráfico contiene un desglose de los puntos de las acciones que posee, así como los puntos de las acciones que posee Microsoft, para que pueda ver cuántos puntos necesita para completar la evaluación.

Las acciones de mejora clave para los controles de la evaluación se muestran por orden de mayor impacto potencial para obtener puntos. El gráfico asociado detalla el estado de pruebas agregadas de las acciones de mejora para que pueda evaluar rápidamente lo que se ha probado y lo que todavía debe realizarse.

Para acceder a acciones de mejora individuales, vaya a la pestaña controles.

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

#### <a name="learn-more"></a>Más información
[Comprenda cómo se realiza el seguimiento y la puntuación de los controles y las acciones de mejora mediante la puntuación de cumplimiento.](compliance-score-methodology.md)

## <a name="export-an-assessment-report"></a>Exportación de un informe de evaluación

Puede exportar una evaluación a un archivo de Excel para las partes interesadas de cumplimiento de su organización o para los auditores externos y los reguladores siguiendo [estas instrucciones](working-with-compliance-manager.md#reports). Deberá visitar el administrador de cumplimiento para exportar el informe.

El informe es una instantánea de la evaluación a partir de la fecha y la hora de la exportación. Contiene los detalles de los controles administrados tanto por usted como por Microsoft, incluidos el estado de la implementación, la fecha de la prueba, los resultados de la prueba y los vínculos a documentos de evidencia cargados.