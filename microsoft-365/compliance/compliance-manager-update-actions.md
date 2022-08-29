---
title: Actualizar las acciones de mejora y llevar datos de cumplimiento al Administrador de cumplimiento de Microsoft Purview
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
description: Migre los datos de cumplimiento existentes al Administrador de cumplimiento de Microsoft Purview mediante un proceso de carga basado en Excel.
ms.openlocfilehash: 399e361e7da3e658c30e205efdcde627da9ccae6
ms.sourcegitcommit: 0c8934129b5ed147fb873fc3f4d201042c313571
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67333814"
---
# <a name="update-improvement-actions-and-bring-compliance-data-into-compliance-manager"></a>Actualizar las acciones de mejora y llevar los datos de cumplimiento al Administrador de cumplimiento

**En este artículo:** Obtenga información sobre cómo migrar las actividades de cumplimiento existentes de su organización al Administrador de cumplimiento y actualizar varias acciones de mejora a la vez mediante la carga de un archivo de Excel con formato.

## <a name="overview"></a>Información general

El Administrador de cumplimiento permite a las organizaciones incorporar sus datos y pruebas de actividad de cumplimiento existentes a la solución Administrador de cumplimiento. Al cargar un archivo de Excel con formato especial, las organizaciones que no están familiarizados con el Administrador de cumplimiento pueden migrar las actividades de cumplimiento completadas en otros sistemas al Administrador de cumplimiento y empezar a aumentar rápidamente su puntuación de cumplimiento general.

Este proceso de carga también proporciona a los usuarios nuevos y existentes del Administrador de cumplimiento una mayor flexibilidad y capacidad para actualizar las acciones de mejora a mayor escala. Por ejemplo, puede:

- [Agregue resultados de pruebas y pruebas](compliance-manager-improvement-actions.md#perform-work-and-store-documentation) a varias acciones de mejora que se probaron en un sistema distinto del Administrador de cumplimiento.
- [Asigne acciones de mejora](compliance-manager-improvement-actions.md#assign-improvement-actions) a varios usuarios en función del potencial de puntuación de las acciones.
- Actualice el [estado de implementación](compliance-manager-improvement-actions.md#change-implementation-details) o [el estado de prueba](compliance-manager-improvement-actions.md#change-test-status) de varias acciones de mejora al mismo tiempo.
- Cambie el origen de [las pruebas](compliance-manager-improvement-actions.md#update-testing-source) de las acciones de mejora de la implementación automática a la manual y las pruebas.
- [Parent the testing source](compliance-manager-improvement-actions.md#parent-testing-source) of multiple actions at one time, para que esas acciones hereden el estado de implementación y prueba de otra acción.

## <a name="getting-started"></a>Introducción

Para migrar los datos existentes al Administrador de cumplimiento o para realizar una actualización masiva de las acciones de mejora, puede empezar desde uno de los dos lugares del Administrador de cumplimiento:

- Desde **la página Evaluaciones** : le ayuda a actualizar evaluaciones específicas con información de otro lugar, como resultados de pruebas o pruebas de las acciones que ha probado un sistema independiente. 
- Desde **la página Acciones de mejora** : facilita la actualización de varias acciones a la vez, como asignarlas a los usuarios, cambiar el estado de implementación o prueba y agregar notas y pruebas.

Para comenzar el proceso de migración de datos o acciones de actualización, [siga los pasos descritos a continuación](#steps-for-updating-actions).

> [!IMPORTANT]
> - Este proceso solo puede actualizar las acciones de mejora administradas por su organización, no las acciones administradas por Microsoft. (Obtenga más información sobre [los tipos de acciones de mejora](compliance-score-calculation.md#action-types-and-points)).
> - Las acciones de mejora ya deben estar asociadas a una evaluación para poder actualizarlas a través de este proceso. (Obtenga más información sobre [la creación y administración de evaluaciones](compliance-manager-assessments.md)).

## <a name="migrating-your-existing-work-into-compliance-manager"></a>Migración del trabajo existente al Administrador de cumplimiento

Si no está familiarizado con el Administrador de cumplimiento, los pasos siguientes ilustran el flujo de trabajo básico para incorporar las actividades de cumplimiento existentes al Administrador de cumplimiento:

1. **Crear una evaluación**: el Administrador de cumplimiento puede recomendar evaluaciones que puedan ser más relevantes para su organización, o bien puede crear una a través de un proceso guiado. Visite [Creación de evaluaciones](compliance-manager-assessments.md#create-assessments) para obtener instrucciones.

2. **Exportar acciones de mejora**: exportará un archivo de Excel que contenga los datos de acción que desea actualizar. Puede tener más sentido iniciar la exportación desde la página **Evaluaciones** , pero también puede exportar desde la página **Acciones de mejora** . Consulte los [pasos descritos a continuación](#steps-for-updating-actions).

3. **Actualizar el archivo de Excel de la acción de mejora**: use las instrucciones de la pestaña **Cómo actualizar acciones** del archivo de Excel para agregar la información.

4. **Cargar el archivo de Excel**: cargue el archivo de Excel editado seleccionando el comando **Cargar acciones** en la página **Evaluaciones** o **Acciones de mejora** .

## <a name="updating-multiple-improvement-actions-at-once"></a>Actualización de varias acciones de mejora a la vez

Para actualizar el estado, la evidencia, las notas u otros datos de varias acciones de mejora a la vez, seguirá el flujo básico que se describe a continuación:

1. **Acciones de mejora de exportación.** Exporte las acciones de mejora que desea actualizar, ya sea desde la página **Acciones de mejora** o desde la página **Evaluaciones** . La exportación es un archivo de Excel descargado que contiene datos de acción de mejora. Consulte los [pasos descritos a continuación](#steps-for-updating-actions).

2. **Actualice el archivo de Excel de la acción de mejora.** Use las instrucciones de la pestaña **Cómo actualizar acciones** del archivo de Excel para agregar o actualizar la información en el archivo de Excel con formato especial.

3. **Cargue el archivo de Excel.** Cargue el archivo de Excel editado seleccionando el comando **Cargar acciones** en la página **Evaluaciones** o **Acciones de mejora** .

> [!NOTE]
> El proceso de actualización de la acción de mejora no se puede usar para agregar nuevas acciones de mejora al Administrador de cumplimiento. Agregar una nueva acción requiere la [creación de una plantilla de evaluación personalizada](compliance-manager-templates-create.md), que implica un tipo diferente de archivo de Excel con datos de asignación de controles y acciones. Consulte las [instrucciones de formato de plantilla](compliance-manager-templates-format-excel.md); en concreto, las instrucciones de la pestaña "Acciones".

> [!NOTE]
> Si exporta las acciones de mejora de una evaluación, el archivo de Excel exportado incluirá datos de asignación de control para esa evaluación. Sin embargo, no podrá cambiar los datos de asignación de controles al editar el archivo de Excel.

## <a name="steps-for-updating-actions"></a>Pasos para actualizar acciones

En los pasos siguientes se describe el proceso para incluir datos de actividad de cumplimiento en las evaluaciones y actualizar las acciones de mejora.

1. En el Administrador de cumplimiento, comience desde la página **Evaluaciones** o desde la página **Acciones de mejora** .

2. Exporte las acciones de mejora que desea actualizar:

    a. En la página **Acciones de mejora** : busque las acciones de mejora que desea actualizar y active la casilla situada a la izquierda de sus nombres. A continuación, seleccione el comando **Exportar acciones** encima de la lista de acciones.
    
    b. En la página **Evaluaciones** : busque la evaluación o las evaluaciones que desea actualizar y active la casilla situada a la izquierda de sus nombres. A continuación, seleccione el comando **Exportar acciones** encima de la lista de evaluaciones.

4. Se descargará un archivo de Excel, que contiene todos los datos relacionados con las acciones. Abra el archivo y consulte las instrucciones de formato de la pestaña con la etiqueta **How to update actions (Cómo actualizar acciones).**

5. Edite la información de la pestaña **Actualización** de acciones de la hoja de cálculo según las instrucciones de formato. A continuación, guarde la versión actualizada del archivo de Excel en el equipo.

6. En **la página Evaluaciones** o en **la página Acciones de mejora** , seleccione el comando **Actualizar acciones** , que abrirá el Asistente para la actualización de acciones de mejora.

7. En la primera página del asistente se enumeran los requisitos previos principales: que todas las acciones de mejora deben estar asociadas al menos a una evaluación y que los datos deben tener formato en un archivo de Excel para su carga. Active las casillas situadas junto a los avisos y, a continuación, continúe con el proceso seleccionando **Siguiente**.

8. En la página **Importar acciones de mejora actualizadas** , seleccione **Examinar** para buscar el archivo de Excel actualizado desde su ubicación guardada y, a continuación, seleccione **Siguiente**. Si hay algún problema con el formato del archivo, un mensaje de error proporcionará instrucciones para solucionar el problema. Vuelva a cargar el archivo corregido y, a continuación, seleccione **Siguiente**.

9. En la página **Revisar y finalizar** , revise el resumen que muestra el número de acciones que se actualizarán, sus evaluaciones asociadas y cómo afectan a la puntuación de cumplimiento. Desde aquí puede cargar un archivo diferente o continuar con la carga seleccionando **Acciones de actualización**.

10. Cuando el archivo se haya cargado correctamente, verá una pantalla de confirmación. Seleccione **Finalizar** para salir del asistente y volver a la página donde inició el proceso de acciones de actualización.

La mayoría de las actualizaciones surtirán efecto de inmediato, pero puede tardar hasta un día para que toda la información actualizada se refleje por completo en el Administrador de cumplimiento.

> [!NOTE]
> La asignación de controles no se incluirá en el archivo de Excel que se descarga al *exportar* acciones. La asignación de controles se controla mediante el proceso de creación de una plantilla de evaluación mediante un [archivo de Excel con formato diferente para importar datos de plantilla](compliance-manager-templates-format-excel.md).
