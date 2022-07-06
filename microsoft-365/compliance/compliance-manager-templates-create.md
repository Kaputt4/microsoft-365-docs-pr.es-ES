---
title: Creación de plantillas de evaluación en el Administrador de cumplimiento de Microsoft Purview
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
description: Obtenga información sobre cómo crear plantillas para evaluaciones en el Administrador de cumplimiento de Microsoft Purview. Cree y modifique plantillas mediante un archivo de Excel con formato.
ms.openlocfilehash: f7198d9b7bb9c30d388924d9c1b16a79e86bb8ee
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66638672"
---
# <a name="create-an-assessment-template-in-microsoft-purview-compliance-manager"></a>Creación de una plantilla de evaluación en el Administrador de cumplimiento de Microsoft Purview

Para crear su propia plantilla para evaluaciones personalizadas en el Administrador de cumplimiento, usará una hoja de cálculo de Excel con formato especial para ensamblar los datos de control necesarios. Después de completar la hoja de cálculo, la importará en el Administrador de cumplimiento.

Para obtener información sobre cómo dar formato a la hoja de cálculo, consulte [Dar formato a los datos de la plantilla de evaluación con Excel](compliance-manager-templates-format-excel.md).

## <a name="required-roles"></a>Roles necesarios

Solo los usuarios que tienen un rol de administrador global o administrador de cumplimiento pueden crear y modificar plantillas. Obtenga más información sobre [los roles y permisos](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

## <a name="create-new-template-in-compliance-manager"></a>Creación de una nueva plantilla en el Administrador de cumplimiento

1. Vaya a la página **de plantillas de evaluación** en el Administrador de cumplimiento.
2. Seleccione **Crear nueva plantilla**. Se abrirá un asistente para la creación de plantillas.
3. Elija el tipo de plantilla que desea crear. En este caso, seleccione **Crear una plantilla personalizada** y, a continuación, seleccione **Siguiente**.
4. En la pantalla **Cargar archivo** , seleccione **Examinar** para buscar y cargar el archivo de Excel con formato que contiene todos los datos de plantilla necesarios.
5. Si no hay ningún problema con el archivo, se mostrará el nombre del archivo cargado. Seleccione **Siguiente** para continuar. (Si necesita cambiar el archivo, seleccione **Cargar un archivo diferente**).
    - Si hay un error con el archivo, un mensaje de error en la parte superior explica qué ocurre. Tendrá que corregir el archivo y cargarlo de nuevo. Los errores se producirán si la hoja de cálculo tiene un formato incorrecto o si hay información no válida en determinados campos.
6. La pantalla **Revisar y finalizar** muestra el número de acciones y controles de mejora y la puntuación máxima de la plantilla. Cuando esté listo para aprobar, seleccione **Crear plantilla.** (Si necesita realizar cambios, seleccione **Atrás**).
7. La última pantalla confirma que se ha creado una nueva plantilla. Seleccione **Listo** para salir del asistente.
8. Llegará a la página de detalles de la nueva plantilla, donde puede [crear la evaluación](compliance-manager-assessments.md#create-assessments).
