---
title: Ampliar plantillas de evaluación en Microsoft Compliance Manager
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
description: Comprenda cómo ampliar las plantillas de evaluación en Microsoft Compliance Manager para agregar y modificar controles.
ms.openlocfilehash: 4618c085228c44e3af1aa0b3de9c3b1ebd63424c
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2021
ms.locfileid: "60336064"
---
# <a name="extend-assessment-templates-in-microsoft-compliance-manager"></a>Ampliar plantillas de evaluación en Microsoft Compliance Manager

El Administrador de cumplimiento ofrece la opción de agregar sus propios controles y acciones de mejora a una plantilla existente. Este proceso se denomina extensión de una plantilla.

Para ampliar una plantilla, usará instrucciones especiales para modificar los datos de plantilla, en función de si está ampliando las plantillas de evaluación Microsoft 365 plantillas de evaluación universales.

## <a name="extend-microsoft-365-assessment-templates"></a>Ampliar Microsoft 365 de evaluación

Al ampliar una plantilla de Microsoft 365, microsoft todavía puede recibir actualizaciones [publicadas,](compliance-manager-assessments.md#accept-updates-to-assessments)lo que puede ocurrir cuando hay cambios en la regulación o el producto relacionados (vea Accept updates to assessments ).

### <a name="prepare-template-data-and-create-extension"></a>Preparar datos de plantilla y crear extensión

Para prepararlo, deberá ensamblar una hoja de cálculo Excel formato especial para importar los datos de plantilla necesarios. Los Excel siguen el mismo formato descrito en [Format assessment template data with Excel](compliance-manager-templates-format-excel.md), pero hay requisitos especiales para las extensiones. Vea estos puntos adicionales para ayudar a evitar errores:

- La hoja de cálculo solo debe contener las acciones y controles que desee agregar a la evaluación.
- La hoja de cálculo no puede contener ninguno de los controles o acciones que ya existen en la evaluación que desea modificar.
- Considere la posibilidad de incluir "extensión" en el título de la plantilla, por ejemplo, "RGPD – extensión [nombre de la empresa]". Esto facilita la identificación en la  lista de la página plantillas de evaluación como distinta de la plantilla estándar proporcionada por Microsoft o una plantilla personalizada con un nombre similar.

Después de dar formato a la hoja de cálculo, siga los pasos siguientes.

1. Vaya a la **página Plantillas de evaluación** y seleccione Crear nueva **plantilla.** Se abrirá un asistente para la creación de plantillas.

2. Elija el tipo de plantilla que desea crear. En este caso, seleccione **Extender una plantilla de Microsoft** y, a continuación, Seleccionar plantilla de **Microsoft**.

3. Aparece un panel desplegable de selección de plantilla en el lado derecho de la pantalla, que muestra una lista de todas las plantillas y su estado de activo o inactivo. El **contador de plantillas** activadas muestra cuántas plantillas están actualmente en uso del número total disponible para usar. Si supera el límite, una barra de mensajes le proporcionará aviso.

4. Aparece un panel desplegable de selección de plantilla en el lado derecho de la pantalla. Usar **la** búsqueda para aplicar filtros para localizar la plantilla que desee

5. Una vez que encuentre la plantilla, seleccione el botón de radio situado a la izquierda de su nombre y, a continuación, **seleccione Guardar**.

6. En la siguiente pantalla se muestra la plantilla seleccionada. Si es correcto, seleccione **Siguiente**. (Si es incorrecto, **elija Seleccionar una plantilla diferente** para volver a elegir).

7. En la **Upload de** archivos,  seleccione Examinar para buscar y cargar el archivo Excel formato que contiene todos los datos de plantilla necesarios.

8. Si no hay ningún problema con el archivo, en la siguiente pantalla se muestra el nombre del archivo cargado. Seleccione **Siguiente** para continuar (si necesita cambiar el archivo, **seleccione Upload otro archivo**).

    - Si hay un problema con el archivo, un mensaje de error en la parte superior explica lo que está mal. Tendrás que corregir y volver a cargar el archivo. Los errores se producen si la hoja de cálculo tiene un formato incorrecto o si hay información no válida en determinados campos.

9. La **pantalla Revisar y finalizar** muestra el número de acciones y controles de mejora y la puntuación máxima de la plantilla. Cuando esté listo para aprobar, seleccione **Siguiente**. (Si necesita realizar cambios, seleccione **Upload otro archivo**.)

10. La última pantalla confirma que se ha creado una plantilla nueva. Seleccione **Listo** para salir del asistente.

11. Llegarás a la página de detalles de la nueva plantilla. Desde aquí puede crear su evaluación seleccionando **Crear evaluación**. Para obtener instrucciones, vea [Build and manage assessments](compliance-manager-assessments.md#create-assessments).

## <a name="extend-universal-assessment-templates"></a>Ampliar plantillas de evaluación universal

Las versiones universales de las plantillas también se pueden ampliar para personalizar las evaluaciones específicas del producto. Recibirá una plantilla de extensión especial cuando cree una evaluación con una plantilla universal y la evaluación tenga una combinación única de producto y certificación. Este archivo se puede modificar para satisfacer sus necesidades. Para obtener instrucciones sobre cómo editar la plantilla, vea las instrucciones para [modificar una plantilla](compliance-manager-templates-modify.md).

Al editar una plantilla universal, se puede cambiar todo el contenido de la plantilla, pero al hacerlo se romperá la herencia con la plantilla primaria. Esto significa que ya no recibirá automáticamente actualizaciones de Microsoft si se actualiza la plantilla primaria.
