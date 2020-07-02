---
title: Notas de la versión de calificación de cumplimiento de Microsoft
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Notas de la versión y problemas conocidos de la puntuación de cumplimiento de Microsoft (versión preliminar), una característica del centro de cumplimiento de M365 que ayuda a simplificar y automatizar las evaluaciones de riesgos.
ms.openlocfilehash: 6678ec03d2cd87a97244acaa55a15483d78dd632
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022197"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Notas de la versión de calificación de cumplimiento de Microsoft (versión preliminar)

**En este artículo:** Esta **página muestra las novedades de** la versión preliminar pública de la puntuación de cumplimiento de [Microsoft](compliance-score.md), que proporciona acceso anticipado a la nueva funcionalidad.

## <a name="assessment-creation-and-management-functionality"></a>Funcionalidad de creación y administración de la evaluación

La versión de junio de 2020 agrega funcionalidad a los usuarios para crear, eliminar y administrar sus evaluaciones directamente en la puntuación de cumplimiento. Anteriormente, toda la administración de evaluaciones residía en el administrador de cumplimiento. Al crear o modificar una evaluación en la puntuación de cumplimiento, las actualizaciones se verán en el administrador de cumplimiento. Del mismo modo, cualquier trabajo de evaluación realizado en el administrador de cumplimiento tendrá como resultado la puntuación de cumplimiento. Obtenga información sobre cómo [administrar las evaluaciones en la puntuación de cumplimiento](compliance-score-assessments.md). Tenga en cuenta que la creación y modificación de plantillas todavía se administran en el administrador de cumplimiento.

## <a name="new-templates-for-assessments"></a>Nuevas plantillas para evaluaciones

Las plantillas listas para usar nuevas para las evaluaciones se publican en la puntuación de cumplimiento cuando están disponibles. Compruebe la [lista completa de plantillas aquí](compliance-score-templates.md). Agregado recientemente:

- Solución de seguridad de la información Dubai (DGISR)

## <a name="compliance-score-relationship-to-compliance-manager"></a>Relación de puntuación de cumplimiento con el administrador de cumplimiento

Muchas de las funciones que se administran en el administrador de cumplimiento se pueden realizar ahora con la puntuación de cumplimiento. Sin embargo, algunas funciones aún se activan en el administrador de cumplimiento. Tenga en cuenta estos puntos cuando trabaje con la puntuación de cumplimiento y el administrador de cumplimiento durante la versión preliminar pública:

 - **Creación de plantillas para evaluaciones**: 
   - Los usuarios deben ir al administrador de cumplimiento para [crear nuevas plantillas y modificar las plantillas existentes](working-with-compliance-manager.md#templates).
   - Las plantillas nuevas deben incluir dimensiones tanto para el **producto** como para la **certificación**.
 - **Establecer permisos**: puntuación de cumplimiento los usuarios que ya no tenían permisos en el administrador de cumplimiento necesitan sus permisos establecidos en el centro de cumplimiento de Microsoft 365 (más[información](compliance-score-setup.md#set-user-permissions-and-assign-roles)).
- **Transferencia de datos**: las organizaciones con datos en el administrador de cumplimiento verán que los datos en la puntuación de cumplimiento y lo mismo se aplican de la misma manera.
- **Iniciar sesión en el administrador de cumplimiento desde la puntuación de cumplimiento**: Si un usuario ha iniciado sesión en puntuación de cumplimiento y selecciona un vínculo para ir al administrador de cumplimiento, el usuario no tendrá que volver a iniciar sesión. Después de hacer clic en el vínculo, se abre una nueva pestaña en el explorador que incluye un cuadro de diálogo. En la sección superior con el encabezado, "¿ya es un cliente de Microsoft Cloud Services? Inicie sesión en su cuenta, "Seleccione el botón **iniciar** sesión para iniciar sesión automáticamente en el administrador de cumplimiento.

## <a name="known-issues-in-compliance-score-preview"></a>Problemas conocidos en la puntuación de cumplimiento (versión preliminar)

En las siguientes secciones se abordan los problemas conocidos que deben resolverse en próximas versiones de la puntuación de cumplimiento.

### <a name="long-load-times-for-non-admin-users"></a>Tiempos de carga prolongados para usuarios que no son administradores
Puntuación de cumplimiento los usuarios que tienen roles que no son un rol de administrador pueden experimentar tiempos de carga prolongados al intentar iniciar sesión. Al actualizar el explorador se resolverá este problema. Obtenga más información sobre los [roles de puntuación de cumplimiento](compliance-score-setup.md#set-user-permissions-and-assign-roles).

### <a name="supported-browsers"></a>Exploradores compatibles

- Se admiten las versiones más recientes de Microsoft Edge, Chrome y Safari.
- A veces, los datos actualizados no aparecen hasta que se actualiza el explorador.
- Internet Explorer no es compatible.
