---
title: Extensión de plantillas de evaluación en el Administrador de cumplimiento de Microsoft Purview
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
description: Comprenda cómo ampliar las plantillas de evaluación en el Administrador de cumplimiento de Microsoft Purview para agregar y modificar controles.
ms.openlocfilehash: b4cf642e7b5a9dac47cd513251c05a802f16b77b
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66630463"
---
# <a name="extend-assessment-templates-in-microsoft-purview-compliance-manager"></a>Extensión de plantillas de evaluación en el Administrador de cumplimiento de Microsoft Purview

El Administrador de cumplimiento ofrece la opción de agregar sus propios controles y acciones de mejora a una plantilla existente. Este proceso se denomina extensión de una plantilla.

Para ampliar una plantilla, usará instrucciones especiales para modificar los datos de la plantilla, en función de si va a ampliar las plantillas de evaluación de Microsoft o las plantillas de evaluación universal.

## <a name="extend-microsoft-assessment-templates"></a>Extensión de plantillas de evaluación de Microsoft

Al ampliar una plantilla de Microsoft, como una creada para su uso con Microsoft 365, todavía puede recibir actualizaciones publicadas por Microsoft. Novedades puede producirse cuando hay cambios en la regulación o el producto relacionados (consulte [Aceptar actualizaciones de evaluaciones](compliance-manager-assessments.md#accept-updates-to-assessments)).

### <a name="prepare-template-data-and-create-extension"></a>Preparación de datos de plantilla y creación de una extensión

Para prepararse, deberá ensamblar una hoja de cálculo de Excel con formato especial para importar los datos de plantilla necesarios. Los archivos de Excel siguen el mismo formato descrito en [Formato de datos de plantilla de evaluación con Excel](compliance-manager-templates-format-excel.md), pero hay requisitos especiales para las extensiones. Consulte estos puntos adicionales para ayudar a evitar errores:

- La hoja de cálculo solo debe contener las acciones y los controles que desea agregar a la evaluación.
- La hoja de cálculo no puede contener ninguno de los controles o acciones que ya existen en la evaluación que desea modificar.
- Considere la posibilidad de incluir "extensión" en el título de la plantilla, por ejemplo, "RGPD – [nombre de su empresa] extensión". Esto facilita la identificación en la lista de la página **de plantillas de evaluación** como distinta de la plantilla estándar proporcionada por Microsoft o una plantilla personalizada con un nombre similar.

Después de dar formato a la hoja de cálculo, siga estos pasos.

1. Vaya a la página **Plantillas de evaluación** y seleccione **Crear nueva plantilla**. Se abrirá un asistente para la creación de plantillas.

2. Elija el tipo de plantilla que desea crear. En este caso, seleccione **Extender una plantilla de Microsoft** y seleccione **Plantilla de Microsoft**.

3. En el lado derecho de la pantalla aparece un panel flotante de selección de plantilla que muestra una lista de todas las plantillas y su estado de activo o inactivo. El contador **de plantillas activadas** muestra cuántas plantillas están actualmente en uso del número total disponible para su uso. Si supera el límite, una barra de mensajes proporcionará un aviso.

4. Aparece un panel flotante de selección de plantilla en el lado derecho de la pantalla. Usar **búsqueda** para aplicar filtros para localizar la plantilla que desee

5. Una vez que encuentre la plantilla, seleccione el botón de radio situado a la izquierda de su nombre y, a continuación, seleccione **Guardar**.

6. En la siguiente pantalla se muestra la plantilla seleccionada. Si es correcto, seleccione **Siguiente**. (Si es incorrecto, elija **Seleccionar una plantilla diferente** para volver a elegir).

7. En la pantalla **Cargar archivo** , seleccione **Examinar** para buscar y cargar el archivo de Excel con formato que contiene todos los datos de plantilla necesarios.

8. Si no hay ningún problema con el archivo, en la siguiente pantalla se muestra el nombre del archivo cargado. Seleccione **Siguiente** para continuar (si necesita cambiar el archivo, seleccione **Cargar otro archivo**).

    - Si hay un problema con el archivo, un mensaje de error en la parte superior explica qué ocurre. Tendrá que corregir y volver a cargar el archivo. Los errores se producirán si la hoja de cálculo tiene un formato incorrecto o si hay información no válida en determinados campos.

9. La pantalla **Revisar y finalizar** muestra el número de acciones y controles de mejora y la puntuación máxima de la plantilla. Cuando esté listo para aprobar, seleccione **Siguiente**. (Si necesita realizar cambios, seleccione **Cargar un archivo diferente**).

10. La última pantalla confirma que se ha creado una nueva plantilla. Seleccione **Listo** para salir del asistente.

11. Llegará a la página de detalles de la nueva plantilla. Desde aquí, puede crear la evaluación seleccionando **Crear evaluación**. Para obtener instrucciones, consulte [Compilación y administración de evaluaciones](compliance-manager-assessments.md#create-assessments).

## <a name="extend-universal-assessment-templates"></a>Ampliación de plantillas de evaluación universal

Las versiones universales de las plantillas también se pueden ampliar para personalizar las evaluaciones específicas del producto. Recibirá una plantilla de extensión especial al crear una evaluación mediante una plantilla universal y la evaluación tiene una combinación única de producto y certificación. Este archivo se puede modificar para satisfacer sus necesidades. Para obtener instrucciones sobre cómo editar la plantilla, consulte las instrucciones sobre cómo [modificar una plantilla](compliance-manager-templates-modify.md).

Al editar una plantilla universal, todo el contenido de la plantilla se puede cambiar, pero al hacerlo se interrumpirá la herencia con la plantilla primaria. Esto significa que ya no recibirá actualizaciones automáticamente de Microsoft si se actualiza la plantilla primaria.
