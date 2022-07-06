---
title: Dar formato a los datos de la plantilla de evaluación en Excel para el Administrador de cumplimiento de Microsoft Purview
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.custom: admindeeplinkMAC
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Comprenda cómo trabajar con datos de Excel para las plantillas de evaluación en el Administrador de cumplimiento de Microsoft Purview.
ms.openlocfilehash: 6c94d79fec8ff59419854c34755a7402f841cfe8
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66631235"
---
# <a name="format-assessment-template-data-in-excel-for-microsoft-purview-compliance-manager"></a>Dar formato a los datos de la plantilla de evaluación en Excel para el Administrador de cumplimiento de Microsoft Purview

Al [crear](compliance-manager-templates-create.md), [modificar](compliance-manager-templates-modify.md) o [ampliar](compliance-manager-templates-extend.md) plantillas de evaluación en el Administrador de cumplimiento, trabajará con hojas de cálculo de Excel que usan un formato y un esquema específicos. Estas especificaciones deben seguirse para que los archivos se importen correctamente.

## <a name="download-example-spreadsheet"></a>Descargar hoja de cálculo de ejemplo

Para ver una hoja de cálculo de ejemplo, [descargue un archivo de ejemplo](https://go.microsoft.com/fwlink/?linkid=2124865). Puede usarlo como referencia para crear su propio archivo.

Si tiene previsto modificar una plantilla existente, empiece por ver los detalles de la plantilla en el Administrador de cumplimiento y descargar su archivo de Excel.

## <a name="spreadsheet-format"></a>Formato de hoja de cálculo

La hoja de cálculo de Excel contiene cuatro pestañas, tres de las cuales son necesarias:

1. [Plantilla](#template-tab) (obligatorio)
2. [ControlFamily](#controlfamily-tab) (obligatorio)
3. [Acciones](#actions-tab) (obligatorio)
4. [Dimensiones](#dimensions-tab) (opcional)

Al rellenar la hoja de cálculo con datos de plantilla, la hoja **de cálculo debe incluir las pestañas en el orden indicado anteriormente**; de lo contrario, los datos no se importarán correctamente a una plantilla.

### <a name="template-tab"></a>Pestaña Plantilla

Se requiere la pestaña **Plantilla** . La información de esta pestaña proporciona metadatos sobre la plantilla. Hay cuatro columnas necesarias. Las columnas deben conservar el orden en la hoja de Excel como se muestra a continuación. Puede agregar su propia columna **después de** las cuatro columnas para proporcionar sus propias dimensiones. Si lo hace, asegúrese de agregarlos a la pestaña **Dimensiones** .

- **title**: este es el título de la plantilla, que debe ser único. No puede compartir un nombre con otra plantilla que tenga en el Administrador de cumplimiento, incluidas sus propias plantillas o una plantilla de Administrador de cumplimiento.

- **producto**: se trata de una dimensión necesaria. Enumere el producto asociado a la plantilla.

- **certificación**: esta es la regulación que se usa para la plantilla.

- **inScopeServices**: estos son los servicios del producto a los que se dirige esta evaluación (por ejemplo, si aparece Office 365 como producto, Microsoft Teams podría ser un servicio dentro del ámbito). Puede enumerar varios servicios separados por dos puntos y comas.

> [!NOTE]
> Los datos que se insertan en las celdas **de producto** y **certificación** no se pueden editar después de importar la hoja de cálculo para crear o personalizar una plantilla. Además, un grupo no puede contener dos evaluaciones que tengan la misma combinación **de producto o certificación** . Puede tener varias plantillas con la misma combinación de producto o certificación.

### <a name="controlfamily-tab"></a>Pestaña ControlFamily

Se requiere la pestaña **ControlFamily** .  Las columnas necesarias de esta pestaña, que deben seguir el orden proporcionado en la hoja de cálculo de ejemplo, son:

- **controlName**: este es el nombre de control de la certificación, estándar o regulación, que suele ser algún tipo de identificador. Los nombres de control deben ser únicos dentro de una plantilla. No puede tener varios controles con el mismo nombre en la hoja de cálculo.

- **controlFamily**: proporcione una palabra o frase para el controlFamily, que identifica una amplia agrupación de controles. Un controlFamily no tiene que ser único; se puede enumerar más de una vez en una hoja de cálculo. El mismo controlFamily también se puede enumerar en varias plantillas, aunque no tienen ninguna relación entre sí. Cada controlFamily debe asignarse a al menos un control.

- **controlTitle**: proporcione un título para el control. Mientras que controlName es un código de referencia, el título es un formato de texto enriquecido que se suele ver en las regulaciones.

- **controlDescription**: proporcione una descripción del control.

- **controlActionTitle**: este campo relaciona el control con una o varias acciones, enumeradas por su actionTitle. Puede agregar varias acciones separándolas con dos puntos y comas sin espacio entre sí. Cada control que enumera debe incluir al menos una acción existente y la acción puede definirse en la pestaña **Acciones** de la misma hoja de cálculo, estar en una plantilla diferente o crearla Microsoft. Los distintos controles pueden hacer referencia a la misma acción.

### <a name="actions-tab"></a>Pestaña Acciones

Se requiere **la pestaña Acciones** .  Designa las acciones de mejora administradas por su organización y no las de Microsoft, que ya existen en el Administrador de cumplimiento. Las columnas necesarias para esta pestaña, que deben seguir el orden proporcionado en la hoja de cálculo de ejemplo, son:

- **actionTitle**: este es el título de la acción y es un campo obligatorio. El título que proporcione debe ser único. **Importante**: si hace referencia a una acción de su propiedad que ya existe (por ejemplo, en otra plantilla) y modifica cualquiera de sus elementos en las columnas posteriores, esos cambios se propagarán a la misma acción en otras plantillas.

- **implementationType**: en este campo obligatorio, enumera uno de los tres tipos de implementación siguientes: 
  1) **Operativo** : acciones implementadas por personas y procesos para proteger la confidencialidad, integridad y disponibilidad de los sistemas, recursos, datos y personal de la organización (por ejemplo, reconocimiento y entrenamiento de seguridad).      
  2) **Técnica** : acciones completadas mediante el uso de tecnología y mecanismos contenidos en los componentes de hardware, software o firmware del sistema de información para proteger la confidencialidad, integridad y disponibilidad de los sistemas y datos de la organización (por ejemplo, la autenticación multifactor).
  3) **Documentación** : acciones implementadas a través de directivas y procedimientos documentados que establecen y definen los controles necesarios para proteger la confidencialidad, integridad y disponibilidad de los sistemas, activos, datos y personal de la organización (por ejemplo, una directiva de seguridad de la información).

- **actionScore**: en este campo obligatorio, proporcione un valor de puntuación numérica para la acción. El valor debe ser un número entero comprendido entre 1 y 99; no puede ser 0, null o en blanco. Cuanto mayor sea el número, mayor será su valor para mejorar la posición de cumplimiento. En la imagen siguiente se muestra cómo el Administrador de cumplimiento puntua los controles:

  ![El Administrador de cumplimiento controla los valores de punto.](../media/compliance-score-action-scoring.png "El Administrador de cumplimiento controla los valores de punto")

- **actionDescriptionTitle**: este es el título de la descripción y es necesario. Este título de descripción le permite tener la misma acción en varias plantillas y exponer una descripción diferente en cada plantilla.  Este campo le ayuda a aclarar a qué plantilla hace referencia la descripción. En la mayoría de los casos, puede colocar el nombre de la plantilla que va a crear en este campo.

- **actionDescription**: proporcione una descripción de la acción. Puede aplicar formato como texto en negrita e hipervínculos. Este campo es obligatorio.

- **dimension-Action Purpose**: se trata de un campo opcional. Si lo incluye, el encabezado debe incluir el prefijo "dimension-". Las dimensiones que incluya aquí se usarán como filtros en el Administrador de cumplimiento y aparecerán en la página de detalles de acciones de mejora del Administrador de cumplimiento.

### <a name="dimensions-tab"></a>Pestaña Dimensiones

La pestaña **Dimensiones** es opcional. Sin embargo, si hace referencia a una dimensión en otro lugar, debe especificarla aquí si no existe en una plantilla que ya haya creado o en una plantilla de Microsoft. Las columnas de esta pestaña se enumeran a continuación:

- **dimensionKey**: list as "product", "certifications", "action purpose"
- **dimensionValue**: ejemplos: Office 365, HIPPA, Preventative, Detective

Al exportar una plantilla existente, la hoja de cálculo exportada tendrá la pestaña **Dimensiones** , que enumera todas las dimensiones usadas en la plantilla.
