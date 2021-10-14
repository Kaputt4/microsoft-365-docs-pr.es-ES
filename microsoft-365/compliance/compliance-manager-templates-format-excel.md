---
title: Dar formato a los datos de plantilla de evaluación Excel microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
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
description: Comprenda cómo trabajar con los Excel para plantillas de evaluación en Microsoft Compliance Manager.
ms.openlocfilehash: 899dd42401bb4c7acceb1db5bfe5816b383ae16b
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2021
ms.locfileid: "60335663"
---
# <a name="format-assessment-template-data-in-excel-for-microsoft-compliance-manager"></a>Dar formato a los datos de plantilla de evaluación Excel microsoft Compliance Manager

Al [crear,](compliance-manager-templates-create.md) [modificar](compliance-manager-templates-modify.md) [](compliance-manager-templates-extend.md) o ampliar plantillas de evaluación en el Administrador de cumplimiento, trabajará con Excel hojas de cálculo que usan un esquema y un formato específicos. Estas especificaciones deben seguirse para que los archivos se importen correctamente.

## <a name="download-example-spreadsheet"></a>Descargar hoja de cálculo de ejemplo

Para ver una hoja de cálculo de ejemplo, [descargue un archivo de ejemplo](https://go.microsoft.com/fwlink/?linkid=2124865). Puede usar esto como referencia para crear su propio archivo.

Si tiene previsto modificar una plantilla existente, comience viendo los detalles de la plantilla en el Administrador de cumplimiento y descargando su Excel plantilla.

## <a name="spreadsheet-format"></a>Formato de hoja de cálculo

La Excel de cálculo contiene cuatro pestañas, tres de las cuales son necesarias:

1. [Plantilla](#template-tab) (obligatorio)
2. [ControlFamily](#controlfamily-tab) (obligatorio)
3. [Acciones](#actions-tab) (obligatorio)
4. [Dimensiones](#dimensions-tab) (opcional)

Al rellenar la hoja de cálculo con datos de plantilla, la hoja de cálculo debe incluir las **pestañas** en el orden indicado anteriormente, de lo contrario, los datos no se importarán correctamente a una plantilla.

### <a name="template-tab"></a>Ficha Plantilla

Se **requiere la pestaña** Plantilla. La información de esta pestaña proporciona metadatos sobre la plantilla. Hay cuatro columnas necesarias. Las columnas deben conservar el orden en la Excel como se muestra a continuación. Puede agregar su propia columna después **de** las cuatro columnas para proporcionar sus propias dimensiones. Si lo hace, asegúrese de agregarlos a la **pestaña Dimensiones.**

- **title:** este es el título de la plantilla, que debe ser único. No puede compartir un nombre con otra plantilla que tenga en el Administrador de cumplimiento, incluidas sus propias plantillas o una plantilla de Administrador de cumplimiento.

- **product:** se trata de una dimensión necesaria. Enumerar el producto asociado a la plantilla.

- **certificación:** este es el reglamento que está usando para la plantilla.

- **inScopeServices:** estos son los servicios del producto que aborda esta evaluación (por ejemplo, si aparece Office 365 como el producto, Microsoft Teams podría ser un servicio en el ámbito). Puede enumerar varios servicios separados por dos puntos y comas.

> [!NOTE]
> Los datos que inserte  en las celdas **de** producto y certificación no se pueden editar después de importar la hoja de cálculo para crear o personalizar una plantilla. Además, un grupo no puede contener dos evaluaciones que tengan la misma **combinación de producto y** certificación. Puede tener varias plantillas con la misma combinación de producto y certificación.

### <a name="controlfamily-tab"></a>Ficha ControlFamily

Se **requiere la pestaña ControlFamily.**  Las columnas necesarias en esta pestaña, que deben seguir el orden proporcionado en la hoja de cálculo de ejemplo, son:

- **controlName:** este es el nombre del control de la certificación, estándar o regulación, que suele ser algún tipo de identificador. Los nombres de control deben ser únicos dentro de una plantilla. No puede tener varios controles con el mismo nombre en la hoja de cálculo.

- **controlFamily:** proporcione una palabra o frase para el controlFamily, que identifica una amplia agrupación de controles. Un controlFamily no tiene que ser único; puede aparecer más de una vez en una hoja de cálculo. El mismo controlFamily también se puede enumerar en varias plantillas, aunque no tienen relación entre sí. Cada controlFamily debe asignarse a al menos un control.

- **controlTitle:** proporcione un título para el control. Mientras que controlName es un código de referencia, el título es un formato de texto enriquecido que se suele ver en las regulaciones.

- **controlDescription:** proporcione una descripción del control.

- **controlActionTitle:** este campo relaciona el control con una o más acciones, enumeradas por su actionTitle. Puede agregar varias acciones si las separa con dos puntos y coma sin espacio entre ellos. Cada control que enumera debe incluir al menos una acción existente  y la acción puede definirse en la pestaña Acciones de la misma hoja de cálculo, estar en una plantilla diferente o crearla Microsoft. Diferentes controles pueden hacer referencia a la misma acción.

### <a name="actions-tab"></a>Pestaña Acciones

Se **requiere la pestaña** Acciones.  Designa acciones de mejora administradas por su organización y no las de Microsoft, que ya existen en el Administrador de cumplimiento. Las columnas necesarias para esta pestaña, que deben seguir el orden proporcionado en la hoja de cálculo de ejemplo, son:

- **actionTitle:** este es el título de la acción y es un campo obligatorio. El título que proporciones debe ser único. **Importante:** si hace referencia a una acción de su propiedad que ya existe (como en otra plantilla) y modifica cualquiera de sus elementos en las columnas posteriores, esos cambios se propagarán a la misma acción en otras plantillas.

- **implementationType:** en este campo obligatorio, enumera uno de los tres tipos de implementación siguientes:
- **Operativo:** acciones implementadas por personas y procesos para proteger la confidencialidad, integridad y disponibilidad de los sistemas organizativos, activos, datos y personal (por ejemplo: sensibilización y formación en materia de seguridad)
- **Técnicas:** acciones completadas con tecnología y mecanismos contenidos en los componentes de hardware, software o firmware del sistema de información para proteger la confidencialidad, integridad y disponibilidad de los sistemas y datos de la organización (por ejemplo: autenticación multifactor)
- **Documentación:** acciones implementadas a través de directivas y procedimientos documentados que establecen y definen los controles necesarios para proteger la confidencialidad, integridad y disponibilidad de los sistemas organizativos, activos, datos y personal (por ejemplo, una directiva de seguridad de la información)

- **actionScore:** en este campo obligatorio, proporcione un valor de puntuación numérico para la acción. El valor debe ser un número entero que va de 1 a 99; no puede ser 0, nulo o en blanco. Cuanto mayor sea el número, mayor será su valor para mejorar la posición de cumplimiento. En la imagen siguiente se muestra cómo puntua el Administrador de cumplimiento los controles:

  ![El Administrador de cumplimiento controla los valores de puntos.](../media/compliance-score-action-scoring.png "El Administrador de cumplimiento controla los valores de puntos")

- **actionDescriptionTitle:** este es el título de la descripción y es obligatorio. Este título de descripción te permite tener la misma acción en varias plantillas y mostrar una descripción diferente en cada plantilla.  Este campo le ayuda a aclarar la plantilla a la que hace referencia la descripción. En la mayoría de los casos, puede colocar el nombre de la plantilla que está creando en este campo.

- **actionDescription:** proporcione una descripción de la acción. Puede aplicar formato, como texto en negrita e hipervínculos. Este campo es obligatorio.

- **dimension-Action Purpose:** se trata de un campo opcional. Si lo incluye, el encabezado debe incluir el prefijo "dimension-". Las dimensiones que incluyas aquí se usarán como filtros en el Administrador de cumplimiento y aparecerán en la página de detalles de las acciones de mejora en el Administrador de cumplimiento.

### <a name="dimensions-tab"></a>Ficha Dimensiones

La **pestaña Dimensiones** es opcional. Sin embargo, si hace referencia a una dimensión en otro lugar, debe especificarla aquí si no existe en una plantilla que ya haya creado o en una plantilla de Microsoft. Las columnas de esta pestaña se enumeran a continuación:

- **dimensionKey:** list as "product", "certifications", "action purpose"
- **dimensionValue:** ejemplos: Office 365, HIPPA, Preventative, Detective

Al exportar una plantilla existente, la hoja de cálculo exportada tendrá la pestaña **Dimensiones,** que enumera todas las dimensiones usadas en la plantilla.
