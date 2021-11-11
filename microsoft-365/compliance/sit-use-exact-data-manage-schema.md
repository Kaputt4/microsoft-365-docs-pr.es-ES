---
title: Administrar el esquema exacto de coincidencia de datos
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo editar o quitar el esquema exacto de coincidencia de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7fb535f08b178cf934ec7586579a00725747a3ce
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914855"
---
# <a name="manage-your-exact-data-match-schema"></a>Administrar el esquema exacto de coincidencia de datos

## <a name="editing-the-schema-for-edm-based-classification-manually"></a>Edición manual del esquema para la clasificación basada en EDM

Si desea realizar cambios en el esquema de EDM, por ejemplo, el archivo **edm.xml,** como cambiar los campos que se usan para la clasificación basada en EDM, siga estos pasos:

> [!TIP]
> Puede cambiar el esquema de EDM y el archivo de origen de la tabla de información confidencial para aprovechar la coincidencia **configurable.** Cuando se configura, EDM omite las diferencias entre mayúsculas y minúsculas y otros delimitadores cuando evalúa un elemento. Esto facilita la definición del esquema XML y los archivos de datos confidenciales. Para obtener más información, [vea Using the caseInsensitive and ignoredDelimiters fields](sit-get-started-exact-data-match-create-schema.md#using-the-caseinsensitive-and-ignoreddelimiters-fields).

1. Edite **eledm.xml** (este es el archivo que se describe en el tema Crear el esquema para tipos de información confidencial basados en coincidencias [exactas de datos.](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)

2. Conéctese al Centro de seguridad y cumplimiento por medio de los procedimientos que se describen en [Conectar al PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell).

3. Para actualizar el esquema de la base de datos, ejecute, uno a la vez, los siguientes cmdlets:

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      Se le pedirá que confirme lo siguiente:

      > Confirmar
      >
      > ¿Está seguro de que desea realizar esta acción?
      >
      > Se actualizará el esquema EDM para el almacén de datos "registrospacientes".
      >
      > ¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):

      > [!TIP]
      > Si quiere que los cambios se realicen sin confirmación, en el paso 3, use este cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml

      > [!NOTE]
      > La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos. La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.-->

## <a name="removing-the-schema-for-edm-based-classification-manually"></a>Quitar manualmente el esquema de clasificación basada en EDM

Si desea quitar el esquema que está usando para la clasificación basada en EDM, siga estos pasos:

1. Conéctese al Centro de seguridad y cumplimiento por medio de los procedimientos que se describen en [Conectar al PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell).

2. Ejecute los siguientes cmdlets de PowerShell, sustituyendo el nombre del almacén de datos de "registros de pacientes" por el que desea quitar (con el almacén patientrecords como ejemplo):

      ```powershell
      Remove-DlpEdmSchema -Identity 'patientrecords'
      ```

      Se le pedirá una confirmación:

      > Confirmar
      >
      > ¿Está seguro de que desea realizar esta acción?
      >
      > Se quitará el esquema EDM para el almacén de datos "registrospacientes".
      >
      > ¿\[S\] Sí \[T\] Sí a todo \[N\] No \[A\] No a todo \[?\] Ayuda (el valor predeterminado es "S"):

      > [!TIP]
      >  Si quiere que los cambios se realicen sin confirmación, en el paso 2, use este cmdlet: Remove-DlpEdmSchema -Identity registrospacientes -Confirm:$false

### <a name="edit-or-delete-the-edm-schema-with-the-wizard"></a>Editar o eliminar el esquema de EDM con el asistente

1. Open **Compliance Center** Data  >  **classification** Exact data  >  **matches**.

2. Elija **esquemas EDM**.

3. Elija el SIT de EDM que desea editar.

4. Elija **Editar esquema EDM** o **Eliminar esquema EDM** del control desplegable.

> [!IMPORTANT]
> Si desea eliminar un esquema, y ya está asociado a un tipo de información sensible EDM, primero debe borrar el tipo de información confidencial EDM, luego puede eliminar el esquema.