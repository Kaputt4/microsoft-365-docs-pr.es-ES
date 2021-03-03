---
title: Trabajar con plantillas de evaluación en Microsoft Compliance Manager
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
description: Comprenda cómo usar y administrar plantillas para crear evaluaciones en El Administrador de cumplimiento de Microsoft. Cree y modifique plantillas con un archivo de Excel con formato.
ms.openlocfilehash: 9f76ff6202ff9ad4a876c57209748dd7c98877b4
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405834"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>Trabajar con plantillas de evaluación en el Administrador de cumplimiento

**En este artículo:** Comprenda **cómo funcionan las plantillas** y cómo **administrarlas desde** la página de plantillas de evaluación. Obtenga instrucciones para **crear nuevas** plantillas, **modificar** plantillas existentes, dar formato a los datos de la plantilla **con Excel** y exportar informes de **plantilla**.

> [!IMPORTANT]
> Las plantillas de evaluación que están disponibles para su organización dependen del contrato de licencia. [Revise los detalles](https://go.microsoft.com/fwlink/?linkid=2132371).

## <a name="templates-overview"></a>Introducción a plantillas

Una plantilla es un marco de controles para crear una evaluación en el Administrador de cumplimiento. Nuestro conjunto completo de plantillas puede ayudar a su organización a cumplir con los requisitos nacionales, regionales y específicos del sector que rigen la recopilación y el uso de datos. Nos referimos a plantillas con el mismo nombre que su certificación o reglamento subyacentes, como la plantilla RGPD de la UE y la plantilla ISO 27001:2013.

 Ver la [lista completa de plantillas](compliance-manager-templates-list.md).

## <a name="template-types-included-and-premium-active-and-inactive"></a>Tipos de plantilla: incluidos y premium, activos e inactivos

#### <a name="included-and-premium-templates"></a>Plantillas incluidas y premium

Las plantillas disponibles para su uso se basan en el contrato de licencia de su organización ([ver detalles de licencias](https://go.microsoft.com/fwlink/?linkid=2132371)). Hay dos categorías de plantillas: incluidas y premium.

1. **Las plantillas incluidas** están disponibles para su uso como parte del contrato de licencia de su organización.
2. **Las plantillas** Premium deben adquirirse para crear evaluaciones a partir de ellas. Una vez comprado, puede crear tantas evaluaciones de una plantilla como sea necesario.

#### <a name="active-and-inactive-templates"></a>Plantillas activas e inactivas

Las plantillas mostrarán un estado de activación como activo o inactivo:

- Una plantilla se considera **activa** una vez que se crea una evaluación a partir de esa plantilla.
- Una plantilla se considera **inactiva** si la organización no la usa como marco para una evaluación.

Al comprar una plantilla premium y crear una evaluación a partir de ella, esa plantilla está activa durante un año. La compra se renovará automáticamente a menos que canceles la renovación.

**Contador de plantillas activadas**

La página de evaluación y la página de plantillas de evaluación tienen **un contador de plantillas activadas** cerca de la parte superior. El contador muestra el número de plantillas en uso fuera del número apto para usar de acuerdo con el contrato de licencia.

Por ejemplo, si el contador muestra 2/5, esto significa que su organización ha activado 2 plantillas de las 5 que están disponibles para usar.

Si el contador muestra 5/2, esto indica que su organización supera sus límites y necesita comprar 3 de las plantillas premium en uso.

Consulte [Compliance Manager licensing guidance (Guía de licencias del Administrador de cumplimiento)](https://go.microsoft.com/fwlink/?linkid=2132371) para obtener más información.

## <a name="viewing-and-managing-templates-from-the-assessment-templates-page"></a>Visualización y administración de plantillas desde la página plantillas de evaluación

La página plantillas de evaluación del Administrador de cumplimiento muestra una lista de plantillas y detalles clave. La lista incluye plantillas proporcionadas por el Administrador de cumplimiento, así como cualquier plantilla que la organización haya modificado o creado. Puede aplicar filtros para buscar una plantilla basada en la certificación, el ámbito del producto, el país, la industria, quién la creó y si la plantilla está habilitada para la creación de evaluaciones.

Seleccione una plantilla de su fila para mostrar su página de detalles. Esta página contiene una descripción de la plantilla y más información sobre los detalles de certificación, ámbito y controles. En esta página puede seleccionar los botones adecuados para crear una evaluación, exportar los datos de plantilla a Excel o modificar la plantilla.

## <a name="creating-and-modifying-templates-overview"></a>Introducción a la creación y modificación de plantillas

Para modificar una plantilla existente o crear su propia plantilla nueva, usará una hoja de cálculo de Excel con un formato especial ([descargue](https://go.microsoft.com/fwlink/?linkid=2124865)un ejemplo ) para ensamblar los datos de control necesarios. Después de completar la hoja de cálculo, se importa en el Administrador de cumplimiento durante el proceso de creación o modificación de una plantilla.

> [!NOTE]
> La hoja de cálculo tiene un formato y un esquema específicos que deben usarse o no se importarán correctamente en el Administrador de cumplimiento. A [continuación se muestran las](#formatting-your-template-data-with-excel) instrucciones de formato.

**Roles obligatorios**

Solo los usuarios que tienen un rol de administrador global o administrador de cumplimiento pueden crear y modificar plantillas. Obtenga más información [sobre roles y permisos](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

## <a name="create-a-new-template"></a>Crear una plantilla nueva

Para crear su propia plantilla nueva (usada para crear evaluaciones personalizadas), siga los pasos siguientes.

1. Vaya a la página **plantillas de evaluación** en el Administrador de cumplimiento.
2. Seleccione **Crear nueva plantilla**. Se abrirá un asistente para la creación de plantillas.
3. Elija el tipo de plantilla que desea crear. En este caso, seleccione **Crear una plantilla personalizada** y, a continuación, seleccione **Siguiente**.
4. En la **pantalla** Cargar  archivo, seleccione Examinar para buscar y cargar el archivo de Excel con formato que contiene todos los datos de plantilla necesarios (vea las instrucciones para dar el formato correcto [al archivo](#formatting-your-template-data-with-excel)).
5. Si no hay ningún problema con el archivo, se mostrará el nombre del archivo cargado. Seleccione **Siguiente** para continuar. (Si necesita cambiar el archivo, seleccione **Cargar un archivo diferente**).
    - Si hay un error en el archivo, un mensaje de error en la parte superior explica lo que está mal. Tendrás que corregir el archivo y cargarlo de nuevo. Los errores se producen si la hoja de cálculo tiene un formato incorrecto o si hay información no válida en determinados campos (consulte de nuevo las instrucciones [de formato).](#formatting-your-template-data-with-excel)  
    
6. La **pantalla Revisar y finalizar** muestra el número de acciones y controles de mejora y la puntuación máxima de la plantilla. Cuando esté listo para aprobar, seleccione **Crear plantilla.** (Si necesita realizar cambios, seleccione **Atrás**.)
7. La última pantalla confirma que se ha creado una plantilla nueva. Seleccione **Listo** para salir del asistente.
8. Llegará a la página de detalles de la nueva plantilla, donde puede [crear la evaluación](compliance-manager-assessments.md#create-your-own-custom-assessment).

## <a name="formatting-your-template-data-with-excel"></a>Dar formato a los datos de la plantilla con Excel

La hoja de cálculo de Excel usada para crear plantillas contiene cuatro pestañas, tres de las cuales son necesarias:

1. [Plantilla](#template-tab) (obligatorio)
2. [ControlFamily](#controlfamily-tab) (obligatorio)
3. [Acciones](#actions-tab) (obligatorio)
4. [Dimensiones](#dimensions-tab) (opcional)

Al rellenar la hoja de cálculo con datos de plantilla, la hoja de cálculo debe incluir las  **pestañas** en el orden indicado anteriormente, de lo contrario, los datos no se importarán correctamente a una plantilla.

##### <a name="template-tab"></a>Ficha Plantilla

Se **requiere la pestaña** Plantilla. La información de esta pestaña proporciona metadatos sobre la plantilla. Hay cuatro columnas necesarias. Las columnas deben conservar el orden en la hoja de Excel como se muestra a continuación. Puede agregar su propia columna después **de** las cuatro columnas para proporcionar sus propias dimensiones. Si lo hace, asegúrese de agregarlos a la pestaña **Dimensiones** con las [instrucciones siguientes](#dimensions-tab).

- **title:** este es el título de la plantilla, que debe ser único. No puede compartir un nombre con otra plantilla que tenga en el Administrador de cumplimiento, incluidas sus propias plantillas o una plantilla de Administrador de cumplimiento.

- **product:** se trata de una dimensión necesaria. Enumerar el producto asociado a la plantilla.

- **certificación:** este es el reglamento que está usando para la plantilla.

- **inScopeServices:** estos son los servicios del producto que aborda esta evaluación (por ejemplo, si enumera Office 365 como el producto, Microsoft Teams podría ser un servicio en el ámbito). Puede enumerar varios servicios separados por dos puntos y comas.

> [!NOTE]
> Los datos que inserte  en las celdas **de** producto y certificación no se pueden editar después de importar la hoja de cálculo para crear o personalizar una plantilla. Además, un grupo no puede contener dos evaluaciones que tengan la misma **combinación de producto y** certificación. Puede tener varias plantillas con la misma combinación de producto y certificación.

##### <a name="controlfamily-tab"></a>Ficha ControlFamily

Se **requiere la pestaña ControlFamily.**  Las columnas necesarias en esta pestaña, que deben seguir el orden proporcionado en la hoja de cálculo de ejemplo, son:

- **controlName:** este es el nombre del control de la certificación, estándar o regulación, que suele ser algún tipo de identificador. Los nombres de control deben ser únicos dentro de una plantilla. No puede tener varios controles con el mismo nombre en la hoja de cálculo.

- **controlFamily:** proporcione una palabra o frase para el controlFamily, que identifica una amplia agrupación de controles. Un controlFamily no tiene que ser único; puede aparecer más de una vez en una hoja de cálculo. El mismo controlFamily también se puede enumerar en varias plantillas, aunque no tienen relación entre sí. Cada controlFamily debe asignarse a al menos un control.

- **controlTitle:** proporcione un título para el control. Mientras que controlName es un código de referencia, el título es un formato de texto enriquecido que se suele ver en las regulaciones.

- **controlDescription:** proporcione una descripción del control.

- **controlActionTitle:** este es el título de una acción que desea relacionar con este control. Puede agregar varias acciones separando dos puntos y comas sin espacio entre ellos. Cada control que enumeras debe incluir al menos una acción y la acción debe  existir (lo que significa que puedes enumerar una acción que enumeras en la pestaña Acciones de la misma hoja de cálculo, una acción que existe en una plantilla diferente o una acción creada por Microsoft). Diferentes controles pueden hacer referencia a la misma acción.

##### <a name="actions-tab"></a>Pestaña Acciones

Se **requiere la pestaña** Acciones.  Designa acciones de mejora administradas por su organización y no las de Microsoft, que ya existen en el Administrador de cumplimiento. Las columnas necesarias para esta pestaña, que deben seguir el orden proporcionado en la hoja de cálculo de ejemplo, son:

- **actionTitle:** este es el título de la acción y es un campo obligatorio. El título que proporciones debe ser único. **Importante:** si hace referencia a una acción de su propiedad que ya existe (como en otra plantilla) y modifica cualquiera de sus elementos en las columnas posteriores, esos cambios se propagarán a la misma acción en otras plantillas.

- **implementationType:** en este campo obligatorio, enumera uno de los tres tipos de implementación siguientes:
    - **Operativo:** acciones implementadas por personas y procesos para proteger la confidencialidad, integridad y disponibilidad de los sistemas organizativos, activos, datos y personal (por ejemplo: sensibilización y formación en materia de seguridad)
    - **Técnicas:** acciones completadas mediante el uso de tecnología y mecanismos contenidos en los componentes de hardware, software o firmware del sistema de información para proteger la confidencialidad, integridad y disponibilidad de los sistemas y datos de la organización (por ejemplo: autenticación multifactor)
    - **Documentación:** acciones implementadas a través de directivas y procedimientos documentados que establecen y definen los controles necesarios para proteger la confidencialidad, integridad y disponibilidad de los sistemas organizativos, activos, datos y personal (por ejemplo, una directiva de seguridad de la información)

- **actionScore:** en este campo obligatorio, proporcione un valor de puntuación numérico para la acción. Debe ser un número entero que va de 1 a 99; no puede ser 0, nulo o en blanco. Cuanto mayor sea el número, mayor será su valor para mejorar la posición de cumplimiento. En la imagen siguiente se muestra cómo puntua el Administrador de cumplimiento los controles:

![El Administrador de cumplimiento controla los valores de puntos](../media/compliance-score-action-scoring.png "El Administrador de cumplimiento controla los valores de puntos")

- **actionDescriptionTitle:** este es el título de la descripción y es obligatorio. Este título de descripción te permite tener la misma acción en varias plantillas y mostrar una descripción diferente en cada plantilla.  Este campo le ayuda a aclarar la plantilla a la que hace referencia la descripción. En la mayoría de los casos, puede colocar el nombre de la plantilla que está creando en este campo.

- **actionDescription:** proporcione una descripción de la acción. Puede aplicar formato, como texto en negrita e hipervínculos. Este campo es obligatorio.

- **dimension-Action Purpose:** se trata de un campo opcional. Si lo incluye, el encabezado debe incluir el prefijo "dimension-". Las dimensiones que incluyas aquí se usarán como filtros en el Administrador de cumplimiento y aparecerán en la página de detalles de las acciones de mejora en el Administrador de cumplimiento.

##### <a name="dimensions-tab"></a>Ficha Dimensiones

La **pestaña Dimensiones** es opcional. Sin embargo, si hace referencia a una dimensión en otro lugar, debe especificarla aquí si no existe en una plantilla que ya haya creado o en una plantilla de Microsoft. Las columnas de esta pestaña se enumeran a continuación:

- **dimensionKey:** list as "product", "certifications", "action purpose"
- **dimensionValue:** ejemplos: Office 365, HIPPA, Preventative, Detective

Puede ver las dimensiones existentes yendo a **Administración de** inquilinos y seleccionando la **pestaña Dimensiones.** Además, cada vez que exporte una plantilla existente, la hoja de cálculo exportada tendrá la pestaña **Dimensiones,** que enumera todas las dimensiones usadas en la plantilla.

## <a name="modify-a-template"></a>Modificar una plantilla

Es posible que desee modificar una plantilla que ya ha creado, como agregar controles o agregar o quitar acciones de mejora. El proceso es similar al proceso de creación de plantillas en el que cargará un archivo de Excel con formato con los datos de la plantilla.

Sin embargo, hay detalles concretos que debe tener en cuenta a medida que da formato al archivo con cambios en los datos de plantilla existentes. **Te recomendamos que revises estas instrucciones cuidadosamente para asegurarte de que no sobrescriba los datos existentes que quieras conservar.**

### <a name="template-modification-process-steps"></a>Pasos del proceso de modificación de plantillas

Para modificar una plantilla, siga los pasos siguientes:

1. En la **página plantillas de** evaluación, seleccione la plantilla que desea modificar, que mostrará su página de detalles.
2. Seleccione **Exportar a Excel**. Se descargará un archivo de Excel con todos los datos de la plantilla. Guarde el archivo en el equipo local.
3. Realice los cambios de plantilla [modificando el archivo de Excel con las instrucciones siguientes](#formatting-your-excel-file-to-modify-a-template).
4. Cuando haya terminado de realizar cambios en el archivo de Excel, guarde el archivo.
5. En la página de detalles de la plantilla, seleccione **Modificar plantilla** para iniciar el asistente de modificación. 
6. En la **pantalla Cargar archivo,** seleccione **Examinar** para buscar y cargar el archivo de Excel.
7. Si no hay ningún problema con el archivo, en la siguiente pantalla se muestra el nombre del archivo cargado. Seleccione **Siguiente** para continuar (si necesita cambiar el archivo, seleccione **Cargar un archivo diferente**).
    - Si hay un problema con el archivo, un mensaje de error en la parte superior explica lo que está mal. Tendrás que corregir el archivo y cargarlo de nuevo. Los errores se producen si la hoja de cálculo tiene un formato incorrecto o si hay información no válida en determinados campos.

8. La **pantalla Revisar y finalizar** muestra el número de acciones y controles de mejora y la puntuación máxima de la plantilla. Cuando esté listo para aprobar, seleccione **Siguiente**.
9. La última pantalla confirma que la plantilla se ha modificado. Seleccione **Listo** para salir del asistente.

La plantilla ahora incluirá los cambios realizados. Las evaluaciones que usen esta plantilla modificada ahora mostrarán actualizaciones pendientes y deberá aceptar las actualizaciones de las evaluaciones para reflejar los cambios realizados en la plantilla. Obtenga más información sobre [las actualizaciones de las evaluaciones](compliance-manager-assessments.md#accepting-updates-to-assessments).

> [!NOTE]
> Si usa el Administrador de cumplimiento en un idioma distinto del inglés, observará que algún texto aparece en inglés al exportar una plantilla a Excel. Los títulos de las acciones (tanto las acciones de mejora como las acciones de Microsoft) deben estar en inglés para ser reconocidos por los controles. Si realiza cambios en un título de acción, asegúrese de escribirlo en inglés para que el archivo se importe correctamente.

### <a name="formatting-your-excel-file-to-modify-a-template"></a>Dar formato al archivo de Excel para modificar una plantilla

Vaya a una sección a continuación para encontrar rápidamente las instrucciones que necesita:

- [Editar los atributos de plantilla principales](#edit-the-main-template-attributes)
- [Agregar una acción de mejora](#add-an-improvement-action)
- [Editar la información de una acción de mejora](#edit-an-improvement-actions-information)
- [Cambiar el nombre de una acción de mejora](#change-an-improvement-actions-name)
- [Quitar una acción de mejora](#remove-an-improvement-action)
- [Quitar un control](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>Editar los atributos de plantilla principales

En la **pestaña** Plantillas, puede editar cualquier elemento de la columna **de** título, la columna **inScopeServices** y cualquier otra columna que haya agregado. Sin embargo, no puede editar nada en las columnas **de producto** **o** certificación.

#### <a name="add-an-improvement-action"></a>Agregar una acción de mejora

1. Vaya a la **pestaña** Acciones. Agregue la información en los campos necesarios en la primera fila vacía debajo de las acciones existentes.
2. Vaya a la **pestaña ControlFamily.** Busque la fila que contiene el control al que se asigna la acción de mejora. Agregue la nueva acción a la **columna controlActionTitle** de esa fila (recuerde separar varias acciones en este campo con dos puntos y comas, sin espacio entre).
3. Guarde la hoja de cálculo.

#### <a name="edit-an-improvement-actions-information"></a>Editar la información de una acción de mejora

Puede cambiar la información de cualquier acción de mejora *excepto por su título*. Puede editar cualquier celda de las columnas B en adelante y, al volver a importar el archivo a la plantilla, las acciones de mejora de esa plantilla ahora contendrán los datos actualizados.

No puede editar **actionTitle** (columna A) porque, si lo hace, el Administrador de cumplimiento considera que se trata de una nueva acción de mejora. Si quieres cambiar el nombre de una acción de mejora, consulta las instrucciones que aparecen a continuación.

#### <a name="change-an-improvement-actions-name"></a>Cambiar el nombre de una acción de mejora

Si desea cambiar el nombre de una acción de mejora, debe designar explícitamente en la hoja de cálculo que va a reemplazar un nombre existente por un nuevo nombre. Siga estos pasos:

1. En la **pestaña Acciones** de la hoja de cálculo, agregue una nueva columna a la hoja de cálculo después de la columna A.
2. En esta nueva columna, que ahora es la columna B, se coloca como su encabezado en la fila 1: **oldActionTitle**.
3. Copie el contenido de la columna A y péguelo en la columna B. Esto coloca los títulos de acción de mejora existentes, que es lo que desea cambiar, en la columna B.
4. En la columna A, **actionTitle**, elimine el nombre antiguo y reemplácelo por el nuevo nombre de la acción de mejora.

Tenga en cuenta que los títulos de acción, tanto para las acciones de mejora como para las acciones de Microsoft, deben escribirse en inglés para que se reconozcan cuando se hace referencia en controles.

#### <a name="remove-an-improvement-action"></a>Quitar una acción de mejora

Para quitar una acción de mejora de una plantilla, tendrás que quitarla de cada control que haga referencia a ella. Siga los pasos siguientes para modificar la hoja de cálculo:

1. En la **pestaña ControlFamily,** busque el título de la acción de mejora que desea quitar.
2. Elimine el título de la acción de mejora en las celdas donde aparece. Si la acción de mejora es la única acción de esa fila, elimine toda la fila (que quita el control).
3. En la **pestaña** Acciones, elimine la fila que contiene la acción de mejora que está eliminando.
4. Guarde la hoja de cálculo.

Al volver a importar la hoja de cálculo a la plantilla, la acción de mejora se quitará de la plantilla.

Quitar una acción de mejora de una plantilla no quita completamente la acción de mejora del Administrador de cumplimiento. Otra plantilla puede hacer referencia a esa acción.

#### <a name="remove-a-control"></a>Quitar un control

Para quitar un control, modifique la hoja de cálculo siguiendo los pasos siguientes y vuelva a importar la hoja de cálculo:

1. En la **pestaña ControlFamily,** busque el control que desea quitar en la **columna controlName.**
2. Elimine la fila de ese control.
    - Si este control eliminado contiene acciones de mejora a las que ningún otro control hace referencia, deberá quitar esas acciones de mejora de la **pestaña** Acciones. De lo contrario, recibirá un error de validación.

3. Guarde la hoja de cálculo.

Al volver a importar la hoja de cálculo a la plantilla, el control se quitará de la plantilla.

## <a name="export-a-template"></a>Exportar una plantilla

Puede exportar un archivo de Excel que contenga todos los datos de una plantilla. Tendrás que exportar una plantilla para modificar la plantilla, ya que este será el archivo de Excel que edites y cargas en el [proceso de modificación.](#modify-a-template)

Para exportar la plantilla, vaya a la página de detalles de la plantilla y seleccione el **botón Exportar a Excel.**

Tenga en cuenta que al exportar una plantilla que extendió desde una plantilla del Administrador de cumplimiento, el archivo exportado solo contendrá los atributos que agregó a la plantilla. El archivo exportado no incluirá los datos de plantilla originales proporcionados por Microsoft. Para obtener dicho informe, vea las instrucciones para [exportar un informe de evaluación](compliance-manager-assessments.md#export-an-assessment-report).