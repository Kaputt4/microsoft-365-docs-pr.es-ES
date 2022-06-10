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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo editar o quitar el esquema de coincidencia de datos exacto.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29cfefbd6bf9bb9f92fe5ed7664575ec75adfa12
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66014682"
---
# <a name="manage-your-exact-data-match-schema"></a>Administrar el esquema exacto de coincidencia de datos

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

## <a name="editing-the-schema-for-edm-based-classification-manually"></a>Edición manual del esquema para la clasificación basada en EDM

Si desea realizar cambios en el esquema de EDM, por ejemplo, el archivo **edm.xml** , como cambiar qué campos se usan para la clasificación basada en EDM, siga estos pasos:

> [!TIP]
> Puede cambiar el esquema de EDM y el archivo de origen de la tabla de información confidencial para aprovechar la **coincidencia configurable**. Cuando se configura, EDM omite las diferencias entre mayúsculas y minúsculas y otros delimitadores cuando evalúa un elemento. Esto facilita la definición del esquema XML y los archivos de datos confidenciales. Para obtener más información, consulte [Uso de los campos caseInsensitive e ignoreDelimiters](sit-get-started-exact-data-match-create-schema.md#using-the-caseinsensitive-and-ignoreddelimiters-fields).

1. Edite el archivo **deedm.xml** (este es el archivo descrito en [Crear el esquema para los tipos de información confidencial basados en coincidencias de datos exactas](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types).

2. [Conectar a PowerShell de cumplimiento de & de seguridad](/powershell/exchange/connect-to-scc-powershell).

3. Para actualizar el esquema de base de datos, ejecute el siguiente comando:

      ```powershell
      Set-DlpEdmSchema -FileData ([System.IO.File]::ReadAllBytes('.\\edm.xml')) -Confirm:$true
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
      > Si desea que los cambios se produzcan sin confirmación, no use `-Confirm:$true` en el paso 3.

      > [!NOTE]
      > La actualización de EDMSchema con adiciones puede tardar de 10 a 60 minutos. La actualización debe completarse antes de ejecutar los pasos que usan las adiciones.

## <a name="removing-the-schema-for-edm-based-classification-manually"></a>Eliminación manual del esquema para la clasificación basada en EDM

Si desea quitar el esquema que usa para la clasificación basada en EDM, siga estos pasos:

1. [Conectar a PowerShell de cumplimiento de & de seguridad](/powershell/exchange/connect-to-scc-powershell).

2. Ejecute el siguiente comando, sustituyendo el nombre del almacén de datos de "registros de pacientes" por el que desea quitar (con el almacén patientrecords como ejemplo):

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
      > Si desea que los cambios se produzcan sin confirmación, no use `-Confirm:$true` en el paso 2.

### <a name="edit-or-delete-the-edm-schema-with-the-wizard"></a>Editar o eliminar el esquema EDM con el asistente

1. Abra **Clasificación de** datos del Centro \> de **cumplimiento** \> **Coincidencias exactas de datos**.

2. Elija **esquemas EDM**.

3. Elija el sit de EDM que desea editar.

4. Elija **Editar esquema EDM** o **Eliminar esquema EDM** en el control flotante.

> [!IMPORTANT]
> Si desea eliminar un esquema, y ya está asociado a un tipo de información sensible EDM, primero debe borrar el tipo de información confidencial EDM, luego puede eliminar el esquema.
