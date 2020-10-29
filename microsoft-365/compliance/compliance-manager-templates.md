---
title: Trabajar con plantillas de evaluación en el administrador de cumplimiento de Microsoft
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
description: Aprenda a usar y administrar plantillas para crear evaluaciones en el administrador de cumplimiento de Microsoft. Cree y modifique plantillas con un archivo de Excel con formato.
ms.openlocfilehash: cc3092e486e4f25fa1edad1ff64e638410cf3a63
ms.sourcegitcommit: ccbb405227880f40581c3cdfb974368a29d496f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48791816"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>Trabajar con plantillas de evaluación en el administrador de cumplimiento

**En este artículo:** Comprenda **Cómo funcionan las plantillas** y **Cómo administrarlas** desde la página de plantillas de evaluación. Obtenga instrucciones para **crear** plantillas nuevas, **modificar** plantillas existentes, **dar formato a los datos de plantilla con Excel** y exportar **informes** de plantillas.

> [!IMPORTANT]
> Las plantillas de evaluación que están disponibles para su organización dependen del contrato de licencia. [Revise los detalles](https://go.microsoft.com/fwlink/?linkid=2132371).

## <a name="templates-overview"></a>Información general de plantillas

Una plantilla es un marco para crear una evaluación en el administrador de cumplimiento. Contienen los controles para cumplir con los requisitos de una certificación que usa un producto determinado. El administrador de cumplimiento proporciona un conjunto completo de plantillas para ayudar a su organización a cumplir con los requisitos nacionales, regionales y de la industria que rigen la recopilación y el uso de los datos.

## <a name="list-of-pre-built-templates-for-assessments"></a>Lista de plantillas predefinidas para evaluaciones

El administrador de cumplimiento proporciona plantillas para crear evaluaciones que le ayuden a cumplir con diversas regulaciones y estándares. Ver la [lista de plantillas](compliance-manager-templates-list.md) que proporciona el administrador de cumplimiento. Las plantillas nuevas se agregan de forma regular, así que consulte la lista con frecuencia.

## <a name="viewing-and-managing-templates-from-the-assessment-templates-page"></a>Visualización y administración de plantillas desde la página plantillas de evaluación

La página plantillas de evaluación del administrador de cumplimiento muestra una lista de plantillas y los detalles clave. La lista incluye las plantillas proporcionadas por el administrador de cumplimiento, así como todas las plantillas que la organización haya modificado o creado. Puede aplicar filtros para buscar una plantilla basada en la certificación, el ámbito del producto, el país, la industria, el usuario que la ha creado y si la plantilla está habilitada para la creación de la evaluación.

Seleccione una plantilla de la fila para que aparezca la página de detalles. Esta página contiene una descripción de la plantilla e información adicional acerca de los detalles de certificación, ámbito y controles. En esta página, puede seleccionar los botones apropiados para crear una evaluación, exportar los datos de la plantilla a Excel o modificar la plantilla.

## <a name="creating-and-modifying-templates-overview"></a>Información general sobre la creación y modificación de plantillas

Para modificar una plantilla existente o crear una nueva, use una hoja de cálculo de Excel con formato especial ([Descargue un ejemplo](https://go.microsoft.com/fwlink/?linkid=2124865)) para ensamblar los datos de control necesarios. Después de completar la hoja de cálculo, debe importarla en el administrador de cumplimiento durante el proceso de creación o modificación de una plantilla.

> [!NOTE]
> La hoja de cálculo tiene un formato y un esquema específicos que deben usarse, o no se importará correctamente en el administrador de cumplimiento. Las [instrucciones de formato](#formatting-your-template-data-with-excel) se encuentran a continuación.

**Roles necesarios**

Solo los usuarios que tienen un rol de administrador global o de administrador de cumplimiento pueden crear y modificar plantillas. Obtenga más información sobre [los roles y los permisos](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

## <a name="create-a-new-template"></a>Crear una nueva plantilla

Para crear su propia plantilla (que se usa para crear evaluaciones personalizadas), siga los pasos que se indican a continuación.

1. Vaya a la página de **plantillas de evaluación** en el administrador de cumplimiento.
2. Seleccione **crear nueva plantilla** . Se abrirá un asistente para la creación de plantillas.
3. Elija el tipo de plantilla que desea crear. En este caso, seleccione **crear una plantilla personalizada** y, a continuación, seleccione **siguiente** .
4. En la pantalla **Cargar archivo** , seleccione **examinar** para buscar y cargar el archivo de Excel con formato que contiene todos los datos de plantilla necesarios (consulte las [instrucciones para aplicar el formato adecuado al archivo](#formatting-your-template-data-with-excel)).
5. Si no hay problemas con el archivo, se mostrará el nombre del archivo cargado. Seleccione **siguiente** para continuar. (Si necesita cambiar el archivo, seleccione **cargar un archivo diferente** ).
    - Si hay un error en el archivo, un mensaje de error en la parte superior explica lo que es incorrecto. Deberá corregir el archivo y cargarlo de nuevo. Se producirán errores si la hoja de cálculo tiene un formato incorrecto o si hay información no válida en determinados campos (consulte de nuevo las [instrucciones de formato](#formatting-your-template-data-with-excel)).  
    
6. La pantalla **revisión y finalización** muestra el número de acciones de mejora y los controles y la puntuación máxima para la plantilla. Cuando esté listo para aprobar, seleccione **Crear plantilla.** (Si necesita realizar cambios, seleccione **atrás** ).
7. La última pantalla confirma que se ha creado una plantilla nueva. Seleccione **listo** para salir del asistente.
8. Llegará a la página de detalles de la nueva plantilla, donde podrá [crear la evaluación](compliance-manager-assessments.md#create-your-own-custom-assessment).

## <a name="formatting-your-template-data-with-excel"></a>Dar formato a los datos de la plantilla con Excel

La hoja de cálculo de Excel utilizada para crear plantillas contiene cuatro pestañas, tres de las cuales son necesarias:

1. [Plantilla](#template-tab) (obligatorio)
2. [ControlFamily](#controlfamily-tab) (obligatorio)
3. [Acciones](#actions-tab) (obligatorio)
4. [Dimensiones](#dimensions-tab) (opcional)

Al rellenar la hoja de cálculo con datos de plantilla, la hoja  **de cálculo debe incluir las pestañas en el orden indicado anteriormente** ; de lo contrario, los datos no se importarán correctamente a una plantilla.

##### <a name="template-tab"></a>Ficha plantilla

La ficha **plantilla** es obligatoria. La información de esta ficha proporciona metadatos sobre la plantilla. Hay cuatro columnas obligatorias. Las columnas deben conservar el orden en la hoja de cálculo de Excel como se indica a continuación. Puede agregar su propia columna **después** de las cuatro columnas para proporcionar sus propias dimensiones. Si hace esto, asegúrese de agregarlos a la pestaña **dimensiones** siguiendo las instrucciones que se [indican a continuación](#dimensions-tab).

- **title** : el título de la plantilla, que debe ser único. No puede compartir un nombre con otra plantilla que tenga en el administrador de cumplimiento, incluidas sus propias plantillas o una plantilla del administrador de cumplimiento.

- **producto** : es una dimensión requerida. Enumerar el producto asociado a la plantilla.

- **certificación** : esta es la regla que está usando para la plantilla.

- **inScopeServices** : Estos son los servicios del producto que trata esta evaluación (por ejemplo, si ha incluido Office 365 como producto, Microsoft Teams podría ser un servicio dentro del ámbito). Puede enumerar varios servicios separados por dos puntos y comas.

> [!NOTE]
> Los datos que se insertan en las celdas **producto** y **certificación** no se pueden editar después de importar la hoja de cálculo para crear o personalizar una plantilla. Además, un grupo no puede contener dos evaluaciones que tengan la misma combinación **producto/certificación** . Puede tener varias plantillas con la misma combinación producto/certificación.

##### <a name="controlfamily-tab"></a>Pestaña ControlFamily

La ficha **ControlFamily** es obligatoria.  Las columnas necesarias en esta ficha, que deben seguir el orden proporcionado en la hoja de cálculo de muestra, son:

- **nombrecontrol** : es el nombre del control de la certificación, el estándar o la regla, que suele ser algún tipo de identificador. Los nombres de los controles deben ser únicos dentro de una plantilla. No puede tener varios controles con el mismo nombre en la hoja de cálculo.

- **controlFamily** : proporcione una palabra o frase para controlFamily, que identifica una amplia agrupación de controles. Un controlFamily no tiene que ser único; puede aparecer más de una vez en una hoja de cálculo. El mismo controlFamily también puede aparecer en varias plantillas, aunque no tienen relación entre sí. Cada controlFamily debe asignarse a al menos un control.

- **controlTitle** : proporcione un título para el control. Mientras que nombrecontrol es un código de referencia, el título es un formato de texto enriquecido que normalmente aparece en las regulaciones.

- **controlDescription** : proporcione una descripción del control.

- **controlActionTitle** : es el título de una acción que desea relacionar con este control. Puede agregar varias acciones separando dos puntos y coma sin espacio entre ellas. Cada control que lista debe incluir al menos una acción y la acción debe existir (lo que significa que puede enumerar una acción que se enumera en la ficha **acciones** de la misma hoja de cálculo, una acción que existe en otra plantilla o una acción creada por Microsoft). Los diferentes controles pueden hacer referencia a la misma acción.

##### <a name="actions-tab"></a>Ficha acciones

La ficha **acciones** es obligatoria.  Designa acciones de mejora administradas por la organización y no las de Microsoft, que ya existen en el administrador de cumplimiento. Las columnas necesarias para esta ficha, que deben seguir el orden proporcionado en la hoja de cálculo de muestra, son:

- **actionTitle** : se trata del título de la acción y es un campo obligatorio. El título que proporcione debe ser único. **Importante** : Si hace referencia a una acción que ya existe (como en otra plantilla) y modifica cualquiera de sus elementos en las columnas siguientes, dichos cambios se propagarán a la misma acción en otras plantillas.

- **implementationType** : en este campo obligatorio, enumere uno de los tres tipos de implementación siguientes:
    - Acciones **operativas** implementadas por personas y procesos para proteger la confidencialidad, la integridad y la disponibilidad de los sistemas, los datos y el personal de la organización (ejemplo: reconocimiento y formación de seguridad)
    - Acciones **técnicas** realizadas mediante el uso de tecnología y mecanismos contenidos en los componentes de hardware, software o firmware del sistema de información para proteger la confidencialidad, la integridad y la disponibilidad de los datos y sistemas de la organización (ejemplo: multi-factor Authentication)
    - **Documentación** : acciones que se implementan mediante directivas y procedimientos documentados que establecen y definen los controles necesarios para proteger la confidencialidad, integridad y disponibilidad de los sistemas, datos y personal de la organización (ejemplo: una directiva de seguridad de la información)

- **actionScore** : en este campo obligatorio, especifique un valor de puntuación numérica para la acción. Debe ser un número entero comprendido entre 1 y 99; no puede ser 0, nulo o en blanco. Cuanto mayor sea el número, mayor será su valor hacia la mejora de la postura de cumplimiento. La imagen siguiente muestra cómo el administrador de cumplimiento puntúa los controles:

![Valores de punto de controles del administrador de cumplimiento](../media/compliance-score-action-scoring.png "Valores de punto de controles del administrador de cumplimiento")

- **actionDescriptionTitle** : es el título de la descripción y es obligatorio. Este título de Descripción le permite tener la misma acción en varias plantillas y exponer una descripción diferente en cada plantilla.  Este campo ayuda a clarificar a qué plantilla hace referencia la descripción. En la mayoría de los casos, puede poner el nombre de la plantilla que está creando en este campo.

- **actionDescription** : proporcione una descripción de la acción. Puede aplicar formato como texto en negrita e hipervínculos. Este campo es obligatorio.

- **dimensión-acción propósito** : este es un campo opcional. Si lo incluye, el encabezado debe incluir el prefijo "Dimension-". Las dimensiones que incluya aquí se utilizarán como filtros en el administrador de cumplimiento y aparecerán en la página de detalles de acciones de mejora en el administrador de cumplimiento.

##### <a name="dimensions-tab"></a>Pestaña dimensiones

La pestaña **dimensiones** es opcional. Sin embargo, si hace referencia a una dimensión en otro lugar, debe especificarla aquí si no existe en una plantilla que ya ha creado o en una plantilla de Microsoft. A continuación se enumeran las columnas de esta pestaña:

- **dimensionKey** : List como "producto", "certificaciones", "propósito de la acción"
- **dimensionValue** : ejemplos: Office 365, HIPPA, preventivo, detective

Puede ver las dimensiones existentes yendo a administración de **inquilinos** y seleccionando la pestaña **dimensiones** . Además, cada vez que exporte una plantilla existente, la hoja de cálculo exportada tendrá la ficha **dimensiones** , que enumera todas las dimensiones utilizadas en la plantilla.

## <a name="modify-a-template"></a>Modificar una plantilla

Es posible que desee modificar una plantilla que ya ha creado, como agregar controles o agregar o quitar acciones de mejora. El proceso es similar al proceso de creación de plantillas en el que se cargará un archivo de Excel con formato con los datos de la plantilla.

Sin embargo, hay detalles específicos que debe tener en cuenta a medida que da formato al archivo con los cambios realizados en los datos de la plantilla existente. **Le recomendamos que revise atentamente estas instrucciones para asegurarse de no sobrescribir los datos existentes que desee conservar.**

### <a name="template-modification-process-steps"></a>Pasos del proceso de modificación de plantillas

Para modificar una plantilla, siga los pasos que se indican a continuación:

1. En la página de **plantillas de evaluación** , seleccione la plantilla que desea modificar, que mostrará la página de detalles.
2. Seleccione **exportar a Excel** . Se descargará un archivo de Excel con todos los datos de la plantilla. Guarde el archivo en el equipo local.
3. Haga los cambios en la plantilla [modificando el archivo de Excel siguiendo las instrucciones que se indican a continuación](#formatting-your-excel-file-to-modify-a-template).
4. Cuando haya terminado de realizar cambios en el archivo de Excel, guarde el archivo.
5. En la página de detalles de la plantilla, seleccione **modificar plantilla** para iniciar el Asistente para modificación. 
6. En la pantalla **Cargar archivo** , seleccione **examinar** para buscar y cargar el archivo de Excel.
7. Si no hay problemas con el archivo, en la pantalla siguiente se muestra el nombre del archivo cargado. Seleccione **siguiente** para continuar (si necesita cambiar el archivo, seleccione **cargar un archivo diferente** ).
    - Si hay un problema con el archivo, un mensaje de error en la parte superior explica lo que es incorrecto. Deberá corregir el archivo y cargarlo de nuevo. Se producirán errores si la hoja de cálculo tiene un formato incorrecto o si hay información no válida en determinados campos.

8. La pantalla **revisión y finalización** muestra el número de acciones de mejora y los controles y la puntuación máxima para la plantilla. Cuando esté listo para aprobar, seleccione **siguiente** .
9. La última pantalla confirma que se ha modificado la plantilla. Seleccione **listo** para salir del asistente.

La plantilla incluirá ahora los cambios realizados. Las evaluaciones que usen esta plantilla modificada mostrarán ahora actualizaciones pendientes y tendrá que aceptar las actualizaciones de las evaluaciones para reflejar los cambios realizados en la plantilla. Obtenga más información sobre [las actualizaciones a las evaluaciones](compliance-manager-assessments.md#accepting-updates-to-assessments).

> [!NOTE]
> Si usa el administrador de cumplimiento en un idioma que no sea el inglés, se dará cuenta de que parte del texto aparece en inglés cuando se exporta una plantilla a Excel. Los títulos de las acciones (tanto las acciones de mejora como las acciones de Microsoft) deben estar en inglés para que las reconozcan los controles. Si realiza cambios en un título de acción, asegúrese de escribirlo en inglés para que el archivo se importe correctamente.

### <a name="formatting-your-excel-file-to-modify-a-template"></a>Dar formato al archivo de Excel para modificar una plantilla

Saltar a una sección a continuación para encontrar rápidamente las instrucciones necesarias:

- [Edición de los atributos principales de la plantilla](#edit-the-main-template-attributes)
- [Adición de una acción de mejora](#add-an-improvement-action)
- [Editar la información de una acción de mejora](#edit-an-improvement-actions-information)
- [Cambiar el nombre de una acción de mejora](#change-an-improvement-actions-name)
- [Quitar una acción de mejora](#remove-an-improvement-action)
- [Quitar un control](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>Edición de los atributos principales de la plantilla

En la ficha **plantillas** , puede modificar cualquier cosa en la columna **título** , la columna **inScopeServices** y en cualquier otra columna que haya agregado. Sin embargo, no puede editar nada en las columnas **producto** o **certificación** .

#### <a name="add-an-improvement-action"></a>Adición de una acción de mejora

1. Vaya a la ficha **acciones** . Agregue la información en los campos obligatorios de la primera fila vacía debajo de las acciones existentes.
2. Vaya a la pestaña **ControlFamily** . Busque la fila que contiene el control al que se asigna la acción de mejora. Agregue la nueva acción a la columna **controlActionTitle** de esa fila (Recuerde que debe separar varias acciones en este campo con dos puntos y comas, sin espacio entre ellas).
3. Guarde la hoja de cálculo.

#### <a name="edit-an-improvement-actions-information"></a>Editar la información de una acción de mejora

Puede cambiar la información de la acción de mejora *excepto el título* . Puede editar cualquier celda de las columnas B o o cuando vuelva a importar el archivo a la plantilla, las acciones de mejora de esa plantilla ahora contendrán los datos actualizados.

No se puede editar la **actionTitle** (columna A) porque, si lo hace, el administrador de cumplimiento considera que esta es una nueva acción de mejora. Si desea cambiar el nombre de una acción de mejora, consulte las instrucciones que se indican a continuación.

#### <a name="change-an-improvement-actions-name"></a>Cambiar el nombre de una acción de mejora

Si desea cambiar el nombre de una acción de mejora, debe designar explícitamente en la hoja de cálculo que va a reemplazar un nombre existente por un nombre nuevo. Siga estos pasos:

1. En la ficha **acciones** de la hoja de cálculo, agregue una nueva columna a la hoja de cálculo después de la columna a.
2. En esta nueva columna, que ahora es la columna B, Put como encabezado en la fila 1: **oldActionTitle** .
3. Copie el contenido de la columna A y péguelos en la columna B. Esto hace que los títulos de acciones de mejora existentes, que son lo que desea cambiar, se coloquen en la columna B.
4. En la columna A, **actionTitle** , elimine el nombre antiguo y reemplácelo con el nuevo nombre para la acción de mejora.

Tenga en cuenta que los títulos de acción, tanto para las acciones de mejora como para las acciones de Microsoft, deben escribirse en inglés para que se reconozcan cuando se haga referencia a ellos en los controles.

#### <a name="remove-an-improvement-action"></a>Quitar una acción de mejora

La eliminación de una acción de mejora de una fila en **una hoja de cálculo no quita** la acción de la plantilla que se está editando. En su lugar, siga el proceso siguiente:

1. En la ficha **acciones** , inserte una nueva columna como la columna a y la **operación** put en la fila de encabezado, que es la fila número uno.
2. En la fila de la acción de mejora que desea quitar, coloque **eliminar** en la columna a para esa fila.
3. Asegúrese de que ya no se hace referencia a esta acción de mejora mediante un control. Vaya a la pestaña **ControlFamily** y busque el título de la acción de mejora en la columna F, que es **controlActionTitle** .
4. Cuando encuentre la acción de mejora que aparece en la columna **controlActionTitle** , elimínela.
5. Guarde la hoja de cálculo.

Cuando vuelva a importar la hoja de cálculo a la plantilla, la acción se quitará de la plantilla. Quitar una acción de una plantilla no quita completamente la acción. Todavía puede hacer referencia a esa acción en otra plantilla.

Si va a quitar la última acción de mejora a la que hace referencia un control, debe quitar el control.

#### <a name="remove-a-control"></a>Quitar un control

Para quitar un control, siga el mismo proceso para quitar una acción de mejora, como se ha descrito anteriormente. En la pestaña **ControlFamily** , agregue una columna **Operation** y coloque **eliminar** junto al control que desea quitar.

## <a name="export-a-template"></a>Exportar una plantilla

Puede exportar un archivo de Excel que contenga todos los datos de una plantilla. Deberá exportar una plantilla para modificar la plantilla, ya que será el archivo de Excel que edite y cargue en el [proceso de modificación](#modify-a-template).

Para exportar la plantilla, vaya a la página de detalles de la plantilla y seleccione el botón **exportar a Excel** .

Tenga en cuenta que, al exportar una plantilla que ha ampliado desde una plantilla del administrador de cumplimiento, el archivo exportado solo contendrá los atributos que agregó a la plantilla. El archivo exportado no incluirá los datos de plantilla originales proporcionados por Microsoft. Para obtener un informe de este tipo, consulte las instrucciones para [exportar un informe de evaluación](compliance-manager-assessments.md#export-an-assessment-report).