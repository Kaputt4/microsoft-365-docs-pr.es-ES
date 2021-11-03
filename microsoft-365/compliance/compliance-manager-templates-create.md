---
title: Crear plantillas de evaluación en Microsoft Compliance Manager
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
description: Comprenda cómo crear plantillas para evaluaciones en El Administrador de cumplimiento de Microsoft. Cree y modifique plantillas con un archivo Excel formato.
ms.openlocfilehash: be8d3356bd47289e3822133a2f97cf6349fad05c
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2021
ms.locfileid: "60701638"
---
# <a name="create-an-assessment-template-in-microsoft-compliance-manager"></a>Crear una plantilla de evaluación en Microsoft Compliance Manager

Para crear su propia plantilla nueva para evaluaciones personalizadas en el Administrador de cumplimiento, usará una hoja de cálculo Excel formato especial para ensamblar los datos de control necesarios. Después de completar la hoja de cálculo, la importará al Administrador de cumplimiento.

Para obtener información sobre el formato de la hoja de cálculo, vea [Format assessment template data with Excel](compliance-manager-templates-format-excel.md).

## <a name="required-roles"></a>Roles obligatorios

Solo los usuarios que tienen un rol de administrador global o administrador de cumplimiento pueden crear y modificar plantillas. Obtenga más información [sobre roles y permisos](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

## <a name="create-new-template-in-compliance-manager"></a>Crear nueva plantilla en el Administrador de cumplimiento

1. Vaya a la página **plantillas de evaluación** en el Administrador de cumplimiento.
2. Seleccione **Crear nueva plantilla**. Se abrirá un asistente para la creación de plantillas.
3. Elija el tipo de plantilla que desea crear. En este caso, seleccione **Crear una plantilla personalizada** y, a continuación, seleccione **Siguiente**.
4. En la **Upload de** archivos,  seleccione Examinar para buscar y cargar el archivo Excel formato que contiene todos los datos de plantilla necesarios.
5. Si no hay ningún problema con el archivo, se mostrará el nombre del archivo cargado. Seleccione **Siguiente** para continuar. (Si necesita cambiar el archivo, **seleccione Upload un archivo diferente**).
    - Si hay un error en el archivo, un mensaje de error en la parte superior explica lo que está mal. Tendrás que corregir el archivo y cargarlo de nuevo. Los errores se producen si la hoja de cálculo tiene un formato incorrecto o si hay información no válida en determinados campos.
6. La **pantalla Revisar y finalizar** muestra el número de acciones y controles de mejora y la puntuación máxima de la plantilla. Cuando esté listo para aprobar, seleccione **Crear plantilla.** (Si necesita realizar cambios, seleccione **Atrás**.)
7. La última pantalla confirma que se ha creado una plantilla nueva. Seleccione **Listo** para salir del asistente.
8. Llegará a la página de detalles de la nueva plantilla, donde puede [crear la evaluación](compliance-manager-assessments.md#create-assessments).
