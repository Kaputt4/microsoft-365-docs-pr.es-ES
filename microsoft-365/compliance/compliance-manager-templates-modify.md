---
title: Modificación de plantillas de evaluación en el Administrador de cumplimiento de Microsoft Purview
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
description: Obtenga información sobre cómo modificar las plantillas de evaluación en el Administrador de cumplimiento de Microsoft Purview.
ms.openlocfilehash: f21ff61f6bb06f00d1db8381e3760e7c4b5343aa
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66630419"
---
# <a name="modify-assessment-templates-in-microsoft-purview-compliance-manager"></a>Modificación de plantillas de evaluación en el Administrador de cumplimiento de Microsoft Purview

Al trabajar con evaluaciones en el Administrador de cumplimiento, es posible que desee modificar una plantilla de evaluación que ha creado. El proceso es similar al proceso de [creación de plantillas](compliance-manager-templates-create.md) en el que cargará un archivo de Excel con formato con los datos de la plantilla.

Sin embargo, hay detalles que debe tener en cuenta al dar formato al archivo con cambios en los datos de plantilla existentes. **Se recomienda revisar detenidamente estas instrucciones para asegurarse de que no sobrescribe los datos existentes que desea conservar.**

Para obtener más información sobre el formato de esta hoja de cálculo, consulte [Formatear los datos de la plantilla con Excel](compliance-manager-templates-format-excel.md).

## <a name="format-your-excel-file-to-modify-an-existing-template"></a>Dar formato al archivo de Excel para modificar una plantilla existente

En la página **de plantillas de evaluación** , seleccione la plantilla que desea modificar, que mostrará su página de detalles. A continuación, seleccione **Exportar a Excel**. Se descargará un archivo de Excel con todos los datos de plantilla. Guarde el archivo en el equipo local.

Para trabajar con este archivo, vaya a una sección a continuación para encontrar rápidamente las instrucciones que necesita:

- [Edición de los atributos de plantilla principales](#edit-the-main-template-attributes)
- [Agregar una acción de mejora](#add-an-improvement-action)
- [Editar la información de una acción de mejora](#edit-an-improvement-actions-information)
- [Cambiar el nombre de una acción de mejora](#change-an-improvement-actions-name)
- [Quitar una acción de mejora](#remove-an-improvement-action)
- [Quitar un control](#remove-a-control)

### <a name="edit-the-main-template-attributes"></a>Edición de los atributos de plantilla principales

En la pestaña **Plantillas** , puede editar cualquier cosa en la columna **de título** , en la columna **inScopeServices** y en cualquier otra columna que haya agregado. Sin embargo, no puede editar nada en las columnas **de producto** o **certificación** .

### <a name="add-an-improvement-action"></a>Agregar una acción de mejora

1. Vaya a la pestaña **Acciones** . Agregue la información en los campos necesarios de la primera fila vacía debajo de las acciones existentes.
2. Vaya a la pestaña **ControlFamily** . Busque la fila que contiene el control al que se asigna la acción de mejora. Agregue la nueva acción a la columna **controlActionTitle** de esa fila (recuerde separar varias acciones en este campo con dos puntos y coma, sin espacio entre sí).
3. Guarde la hoja de cálculo.

### <a name="edit-an-improvement-actions-information"></a>Editar la información de una acción de mejora

Puede cambiar la información de cualquier acción de mejora *excepto por su título*. Puede editar cualquier celda de las columnas B en adelante y, al volver a importar el archivo en la plantilla, las acciones de mejora de esa plantilla ahora contendrá los datos actualizados.

No se puede editar **actionTitle** (columna A) porque, si lo hace, el Administrador de cumplimiento considera que se trata de una nueva acción de mejora. Si desea cambiar el nombre de una acción de mejora, consulte las instrucciones inmediatamente siguientes.

### <a name="change-an-improvement-actions-name"></a>Cambiar el nombre de una acción de mejora

Si desea cambiar el nombre de una acción de mejora, debe designar explícitamente en la hoja de cálculo que va a reemplazar un nombre existente por un nuevo nombre. Siga estos pasos:

1. En la pestaña **Acciones** de la hoja de cálculo, agregue una nueva columna a la hoja de cálculo después de la columna A.
2. En esta nueva columna, que ahora es la columna B, coloque como su encabezado en la fila 1: **oldActionTitle**.
3. Copie el contenido de la columna A y péguelo en la columna B. Esto coloca los títulos de acción de mejora existentes, que son los que desea cambiar, en la columna B.
4. En la columna A, **actionTitle**, elimine el nombre anterior y reemplácelo por el nuevo nombre de la acción de mejora.

Tenga en cuenta que los títulos de acción, tanto para las acciones de mejora como para las acciones de Microsoft, deben escribirse en inglés para poder reconocerse cuando se hace referencia a ellos en los controles.

### <a name="remove-an-improvement-action"></a>Quitar una acción de mejora

Para quitar una acción de mejora de una plantilla, deberá quitarla de todos los controles que hacen referencia a ella. Siga los pasos siguientes para modificar la hoja de cálculo:

1. En la pestaña **ControlFamily** , busque el título de la acción de mejora que desea quitar.
2. Elimine el título de la acción de mejora en las celdas donde aparece. Si la acción de mejora es la única acción en esa fila, elimine toda la fila (lo que quita el control).
3. En la pestaña **Acciones** , elimine la fila que contiene la acción de mejora que va a eliminar.
4. Guarde la hoja de cálculo.

Al volver a importar la hoja de cálculo en la plantilla, la acción de mejora se quitará de la plantilla.

La eliminación de una acción de mejora de una plantilla no elimina completamente la acción de mejora del Administrador de cumplimiento. Otra plantilla puede seguir haciendo referencia a esa acción.

### <a name="remove-a-control"></a>Quitar un control

Para quitar un control, modifique la hoja de cálculo siguiendo los pasos siguientes y, a continuación, vuelva a importar la hoja de cálculo:

1. En la pestaña **ControlFamily** , busque el control que desea quitar en la columna **controlName** .
2. Elimine la fila de ese control.
    - Si este control eliminado contiene acciones de mejora a las que ningún otro control hace referencia, deberá quitar esas acciones de mejora de la pestaña **Acciones** . De lo contrario, recibirá un error de validación.

3. Guarde la hoja de cálculo.

Al volver a importar la hoja de cálculo en la plantilla, el control se quitará de la plantilla.

## <a name="modify-template-info-in-compliance-manager"></a>Modificación de la información de plantilla en el Administrador de cumplimiento

Una vez completado y guardado el archivo de Excel, siga estos pasos.

1. Vuelva a abrir la página de la plantilla de evaluación y seleccione la plantilla. En la página de detalles de la plantilla, seleccione **Modificar plantilla** para iniciar el asistente de modificación.
2. En la pantalla **Cargar archivo** , seleccione **Examinar** para buscar y cargar el archivo de Excel.
3. Si no hay ningún problema con el archivo, en la siguiente pantalla se muestra el nombre del archivo cargado. Seleccione **Siguiente** para continuar (si necesita cambiar el archivo, seleccione **Cargar otro archivo**).
    - Si hay un problema con el archivo, un mensaje de error en la parte superior explica qué ocurre. Tendrá que corregir el archivo y cargarlo de nuevo. Los errores se producirán si la hoja de cálculo tiene un formato incorrecto o si hay información no válida en determinados campos.

4. La pantalla **Revisar y finalizar** muestra el número de acciones y controles de mejora y la puntuación máxima de la plantilla. Cuando esté listo para aprobar, seleccione **Siguiente**.
5. La última pantalla confirma que se ha modificado la plantilla. Seleccione **Listo** para salir del asistente.

La plantilla incluirá ahora los cambios realizados. Las evaluaciones que usen esta plantilla modificada ahora mostrarán actualizaciones pendientes y deberá aceptar las actualizaciones de las evaluaciones para reflejar los cambios realizados en la plantilla. Obtenga más información sobre [las actualizaciones de las evaluaciones](compliance-manager-assessments.md#accept-updates-to-assessments).

> [!NOTE]
> Si usa el Administrador de cumplimiento en un idioma distinto del inglés, observará que algún texto aparece en inglés al exportar una plantilla a Excel. Los títulos de las acciones (tanto las acciones de mejora como, si procede, las acciones de Microsoft) deben estar en inglés para que los controles los reconozcan. Si realiza cambios en un título de acción, asegúrese de escribirlo en inglés para que el archivo importe correctamente.
