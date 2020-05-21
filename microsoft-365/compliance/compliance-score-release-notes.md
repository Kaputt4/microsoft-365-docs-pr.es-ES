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
ms.openlocfilehash: 1567921b8bd07b0fe4deda0bab6601898eed75a9
ms.sourcegitcommit: 56772bed89516cebc5eb370e292ccfbb4889cb38
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "44330784"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Notas de la versión de calificación de cumplimiento de Microsoft (versión preliminar)

La versión preliminar pública de la puntuación de cumplimiento de Microsoft proporciona un acceso anticipado a las actualizaciones y funciones futuras. Consulte esta página con frecuencia para conocer las novedades.

La puntuación de cumplimiento es una nueva característica del [centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center.md) que calcula una puntuación basada en riesgos, que mide el progreso hacia la realización de acciones recomendadas que ayudan a reducir los riesgos de cumplimiento.

## <a name="new-templates-for-assessments"></a>Nuevas plantillas para evaluaciones

Las nuevas plantillas preconfiguradas para evaluaciones se publican en producción para la puntuación de cumplimiento (versión preliminar) a medida que estén disponibles. Compruebe la [lista completa de plantillas aquí](compliance-score.md#templates). Las plantillas agregadas recientemente incluyen:

- Ley de protección de datos general de Brasil (LGPD)
- Solución de seguridad de la información Dubai (DGISR)
- IRAP/Australian Government ISM (versión preliminar)
- ISO 27701:2019
- SOC 1
- SOC 2

## <a name="improvements-in-managing-assessments"></a>Mejoras en la administración de evaluaciones

La última versión del administrador de cumplimiento en abril de 2020 incluye actualizaciones que simplifican la creación y personalización de las evaluaciones y las mantienen actualizadas. Vea las [notas](compliance-manager-release-notes.md) de la versión del administrador de cumplimiento para obtener información detallada.

## <a name="language-support"></a>Compatibilidad con idiomas

La puntuación de cumplimiento ahora está disponible en los siguientes idiomas, además de en Inglés: Chino (simplificado), Chino (tradicional), Francés, alemán, Italiano, Japonés, Coreano, Portugués (Brasil), Ruso y español.

## <a name="common-actions-will-synch-status-across-groups"></a>Las acciones comunes sincronizarán el estado entre grupos

Si su organización tiene varios grupos de evaluaciones, el comportamiento de las acciones **técnicas** (es decir, las acciones que afectan a toda la organización) ha cambiado. Todas las acciones duplicadas entre grupos se han combinado en una sola acción. Esa única acción contiene todas las notas y evidencias cargadas de las versiones duplicadas. Con este cambio, las acciones técnicas se comportarán como lo hacían cuando pertenecían al mismo grupo. Cualquier cambio realizado en la acción en un grupo o evaluación se reflejará ahora en todas las instancias. El **Estado de implementación**, la **fecha de implementación**, el **Estado de prueba**y la fecha de **prueba**   reflejarán las actualizaciones más recientes.

## <a name="compliance-score-relationship-to-compliance-manager"></a>Relación de puntuación de cumplimiento con el administrador de cumplimiento

Muchas de las funciones que se administran en el administrador de cumplimiento se pueden realizar ahora con la puntuación de cumplimiento. Sin embargo, algunas funciones aún se activan en el administrador de cumplimiento. Tenga en cuenta estos puntos cuando trabaje con la puntuación de cumplimiento y el administrador de cumplimiento durante la versión preliminar pública:

- **Administración de evaluaciones**: los usuarios pueden ver las evaluaciones y sus detalles de estado en la puntuación de cumplimiento. Sin embargo, los usuarios solo pueden realizar tareas de administración de la evaluación en el administrador de cumplimiento ([instrucciones de vista](working-with-compliance-manager.md#assessments)). Algunos ejemplos de estas tareas son:
    - Creación y copia de evaluaciones
    - Evaluación de la exportación
    - Evaluaciones de archivo
    - Ver evaluaciones archivadas
 - **Creación de plantillas para evaluaciones**: 
   - Los usuarios deben ir al administrador de cumplimiento para crear nuevas plantillas y modificar [las plantillas](working-with-compliance-manager.md#templates)existentes. 
   - Al crear una plantilla, debe incluir las dimensiones del **producto** y la **certificación** para asegurarse de que la plantilla se muestra en la puntuación de cumplimiento.
 - **Establecer permisos**: puntuación de cumplimiento los usuarios que ya no tenían permisos en el administrador de cumplimiento necesitan sus permisos establecidos en el centro de cumplimiento de Microsoft 365 (más[información](compliance-score-setup.md#set-user-permissions-and-assign-roles)).
- **Transferencia de datos**: las organizaciones con datos en el administrador de cumplimiento verán que los datos en la puntuación de cumplimiento y lo mismo se aplican de la misma manera.
- **Iniciar sesión en el administrador de cumplimiento desde la puntuación de cumplimiento**: Si un usuario ha iniciado sesión en puntuación de cumplimiento y selecciona un vínculo para ir al administrador de cumplimiento, el usuario no tendrá que volver a iniciar sesión. Después de hacer clic en el vínculo, se abre una nueva pestaña en el explorador que incluye un cuadro de diálogo. En la sección superior con el encabezado, "¿ya es un cliente de Microsoft Cloud Services? Inicie sesión en su cuenta, "Seleccione el botón **iniciar** sesión para iniciar sesión automáticamente en el administrador de cumplimiento.

## <a name="known-issues-in-compliance-score-preview"></a>Problemas conocidos en la puntuación de cumplimiento (versión preliminar)

En las siguientes secciones se abordan los problemas conocidos que deben resolverse en próximas versiones de la puntuación de cumplimiento.

### <a name="long-load-times-for-non-admin-users"></a>Tiempos de carga prolongados para usuarios que no son administradores
Puntuación de cumplimiento los usuarios que tienen roles que no son un rol de administrador pueden experimentar tiempos de carga prolongados al intentar iniciar sesión. Al actualizar el explorador se resolverá este problema. (Obtenga más información sobre los [roles de puntuación de cumplimiento](compliance-score-setup.md#set-user-permissions-and-assign-roles)).

### <a name="supported-browsers"></a>Exploradores compatibles

- Se admiten las versiones más recientes de Microsoft Edge, Chrome y Safari.
- A veces, los datos actualizados no aparecen hasta que se actualiza el explorador.
- Internet Explorer no es compatible.
