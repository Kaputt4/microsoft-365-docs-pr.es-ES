---
title: Modificar plantillas de evaluación en Microsoft Compliance Manager
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
description: Comprenda cómo modificar plantillas de evaluación en Microsoft Compliance Manager.
ms.openlocfilehash: 539da4118843e8d72ead07b06a351d2245c2f6d9
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2021
ms.locfileid: "60335471"
---
# <a name="modify-assessment-templates-in-microsoft-compliance-manager"></a>Modificar plantillas de evaluación en Microsoft Compliance Manager

Al trabajar con evaluaciones en el Administrador de cumplimiento, es posible que desee modificar una plantilla de evaluación que haya creado. El proceso es similar al proceso [de](compliance-manager-templates-create.md) creación de plantillas en el que se cargará un archivo Excel con los datos de la plantilla.

Sin embargo, hay detalles que debe tener en cuenta a medida que se da formato al archivo con cambios en los datos de plantilla existentes. **Te recomendamos que revises estas instrucciones cuidadosamente para asegurarte de que no sobrescriba los datos existentes que quieras conservar.**

Para obtener más información sobre el formato de esta hoja de cálculo, consulte [Format your template data with Excel](compliance-manager-templates-format-excel.md).

## <a name="format-your-excel-file-to-modify-an-existing-template"></a>Dar formato Excel archivo para modificar una plantilla existente

En la **página plantillas de** evaluación, seleccione la plantilla que desea   modificar, que mostrará su página de detalles. A **continuación, seleccione Exportar a Excel**. Se descargará Excel archivo con todos los datos de la plantilla. Guarde el archivo en el equipo local.

Para trabajar con este archivo, vaya a una sección siguiente para encontrar rápidamente las instrucciones que necesita:

- [Editar los atributos de plantilla principales](#edit-the-main-template-attributes)
- [Agregar una acción de mejora](#add-an-improvement-action)
- [Editar la información de una acción de mejora](#edit-an-improvement-actions-information)
- [Cambiar el nombre de una acción de mejora](#change-an-improvement-actions-name)
- [Quitar una acción de mejora](#remove-an-improvement-action)
- [Quitar un control](#remove-a-control)

### <a name="edit-the-main-template-attributes"></a>Editar los atributos de plantilla principales

En la **pestaña** Plantillas, puede editar cualquier elemento de la columna **de** título, la columna **inScopeServices** y cualquier otra columna que haya agregado. Sin embargo, no puede editar nada en las columnas **de producto** **o** certificación.

### <a name="add-an-improvement-action"></a>Agregar una acción de mejora

1. Vaya a la **pestaña** Acciones. Agregue la información en los campos necesarios en la primera fila vacía debajo de las acciones existentes.
2. Vaya a la **pestaña ControlFamily.** Busque la fila que contiene el control al que se asigna la acción de mejora. Agregue la nueva acción a la **columna controlActionTitle** de esa fila (recuerde separar varias acciones en este campo con dos puntos y comas, sin espacio entre).
3. Guarde la hoja de cálculo.

### <a name="edit-an-improvement-actions-information"></a>Editar la información de una acción de mejora

Puede cambiar la información de cualquier acción de mejora *excepto por su título*. Puede editar cualquier celda de las columnas B en adelante y, al volver a importar el archivo a la plantilla, las acciones de mejora de esa plantilla ahora contendrán los datos actualizados.

No puede editar **actionTitle** (columna A) porque, si lo hace, el Administrador de cumplimiento considera que se trata de una nueva acción de mejora. Si quieres cambiar el nombre de una acción de mejora, consulta las instrucciones que aparecen a continuación.

### <a name="change-an-improvement-actions-name"></a>Cambiar el nombre de una acción de mejora

Si desea cambiar el nombre de una acción de mejora, debe designar explícitamente en la hoja de cálculo que va a reemplazar un nombre existente por un nuevo nombre. Siga estos pasos:

1. En la **pestaña Acciones** de la hoja de cálculo, agregue una nueva columna a la hoja de cálculo después de la columna A.
2. En esta nueva columna, que ahora es la columna B, se coloca como su encabezado en la fila 1: **oldActionTitle**.
3. Copie el contenido de la columna A y péguelo en la columna B. Esto coloca los títulos de acción de mejora existentes, que es lo que desea cambiar, en la columna B.
4. En la columna A, **actionTitle**, elimine el nombre antiguo y reemplácelo por el nuevo nombre de la acción de mejora.

Tenga en cuenta que los títulos de acción, tanto para las acciones de mejora como para las acciones de Microsoft, deben escribirse en inglés para que se reconozcan cuando se hace referencia en controles.

### <a name="remove-an-improvement-action"></a>Quitar una acción de mejora

Para quitar una acción de mejora de una plantilla, tendrás que quitarla de cada control que haga referencia a ella. Siga los pasos siguientes para modificar la hoja de cálculo:

1. En la **pestaña ControlFamily,** busque el título de la acción de mejora que desea quitar.
2. Elimine el título de la acción de mejora en las celdas donde aparece. Si la acción de mejora es la única acción de esa fila, elimine toda la fila (que quita el control).
3. En la **pestaña** Acciones, elimine la fila que contiene la acción de mejora que está eliminando.
4. Guarde la hoja de cálculo.

Al volver a importar la hoja de cálculo a la plantilla, la acción de mejora se quitará de la plantilla.

Quitar una acción de mejora de una plantilla no quita completamente la acción de mejora del Administrador de cumplimiento. Otra plantilla puede hacer referencia a esa acción.

### <a name="remove-a-control"></a>Quitar un control

Para quitar un control, modifique la hoja de cálculo siguiendo los pasos siguientes y vuelva a importar la hoja de cálculo:

1. En la **pestaña ControlFamily,** busque el control que desea quitar en la **columna controlName.**
2. Elimine la fila de ese control.
    - Si este control eliminado contiene acciones de mejora a las que ningún otro control hace referencia, deberá quitar esas acciones de mejora de la **pestaña** Acciones. De lo contrario, recibirá un error de validación.

3. Guarde la hoja de cálculo.

Al volver a importar la hoja de cálculo a la plantilla, el control se quitará de la plantilla.

## <a name="modify-template-info-in-compliance-manager"></a>Modificar información de plantilla en el Administrador de cumplimiento

Después de Excel y guardado el archivo, siga estos pasos.

1. Vuelva a abrir la página de la plantilla de evaluación y seleccione la plantilla. En la página de detalles de la plantilla, seleccione **Modificar plantilla** para iniciar el asistente de modificación.
2. En la **Upload de archivos,** seleccione **Examinar** para buscar y cargar el Excel archivo.
3. Si no hay ningún problema con el archivo, en la siguiente pantalla se muestra el nombre del archivo cargado. Seleccione **Siguiente** para continuar (si necesita cambiar el archivo, **seleccione Upload otro archivo**).
    - Si hay un problema con el archivo, un mensaje de error en la parte superior explica lo que está mal. Tendrás que corregir el archivo y cargarlo de nuevo. Los errores se producen si la hoja de cálculo tiene un formato incorrecto o si hay información no válida en determinados campos.

4. La **pantalla Revisar y finalizar** muestra el número de acciones y controles de mejora y la puntuación máxima de la plantilla. Cuando esté listo para aprobar, seleccione **Siguiente**.
5. La última pantalla confirma que la plantilla se ha modificado. Seleccione **Listo** para salir del asistente.

La plantilla ahora incluirá los cambios realizados. Las evaluaciones que usen esta plantilla modificada ahora mostrarán actualizaciones pendientes y deberá aceptar las actualizaciones de las evaluaciones para reflejar los cambios realizados en la plantilla. Obtenga más información sobre [las actualizaciones de las evaluaciones](compliance-manager-assessments.md#accept-updates-to-assessments).

> [!NOTE]
> Si usa el Administrador de cumplimiento en un idioma distinto del inglés, observará que algún texto aparece en inglés al exportar una plantilla a Excel. Los títulos de las acciones (tanto las acciones de mejora como, en su caso, las acciones de Microsoft) deben estar en inglés para que los controles los reconozcan. Si realiza cambios en un título de acción, asegúrese de escribirlo en inglés para que el archivo se importe correctamente.
