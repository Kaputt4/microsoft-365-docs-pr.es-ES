---
title: Notas de la versión de calificación de cumplimiento de Microsoft
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
ms.openlocfilehash: 370c714c927d09a16272f8ab265c7b0c4e36381a
ms.sourcegitcommit: 5fc0f2cd1f2596fd10299333c826c501936dcd98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2020
ms.locfileid: "41261874"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Notas de la versión de calificación de cumplimiento de Microsoft (versión preliminar)

La versión preliminar pública de la puntuación de cumplimiento de Microsoft proporciona un acceso anticipado a las actualizaciones y funciones futuras. Consulte esta página con frecuencia para conocer las novedades.

La puntuación de cumplimiento es una nueva característica del [centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center.md) que calcula una puntuación basada en riesgos, que mide el progreso hacia la realización de acciones recomendadas que ayudan a reducir los riesgos de cumplimiento.

## <a name="whats-new"></a>Novedades

### <a name="new-templates-for-assessments"></a>Nuevas plantillas para evaluaciones

Las nuevas plantillas preconfiguradas para evaluaciones se publican en producción para la puntuación de cumplimiento (versión preliminar) a medida que estén disponibles. Compruebe la [lista completa de plantillas aquí](compliance-score.md#templates). Las plantillas agregadas recientemente incluyen:

- Ley de protección de datos general de Brasil (LGPD)
- IRAP/Australian Government ISM (versión preliminar)
- ISO 27701:2019
- SOC 1
- SOC 2

### <a name="compliance-score-relationship-to-compliance-manager"></a>Relación de puntuación de cumplimiento con el administrador de cumplimiento

Muchas de las funciones de cumplimiento que se administran en el administrador de cumplimiento se pueden realizar ahora con la puntuación de cumplimiento. Sin embargo, algunas funciones todavía residen en el administrador de cumplimiento y se modifica alguna de las funciones anteriores del administrador de cumplimiento durante el período de versión preliminar pública. 

Tenga en cuenta estos puntos cuando trabaje con la puntuación de cumplimiento y el administrador de cumplimiento durante la versión preliminar pública:

- **Administración de evaluaciones**: los usuarios pueden ver las evaluaciones y sus detalles de estado en la puntuación de cumplimiento. Sin embargo, los usuarios solo pueden realizar tareas de administración de evaluación en el administrador de cumplimiento ([instrucciones de vista](working-with-compliance-manager.md#assessments)) y las tareas se limitan a lo siguiente:
    - Cargar nuevas evaluaciones, pero no modificar las evaluaciones existentes. Si necesita modificar una evaluación existente, tendrá que cargar una nueva plantilla.
    - Evaluación de la exportación
    - Evaluaciones de archivo
    - Ver evaluaciones archivadas
 - **Creación de plantillas para evaluaciones**: 
   - Los usuarios deben ir al administrador de cumplimiento para crear nuevas plantillas y exportar las plantillas existentes. 
   - Las plantillas existentes no se pueden personalizar. Lea las instrucciones para [administrar plantillas en el administrador de cumplimiento](working-with-compliance-manager.md#templates).
   - Al crear una plantilla, debe incluir las dimensiones del **producto** y la **certificación** para asegurarse de que la plantilla se muestra en la puntuación de cumplimiento.
 - **Establecer permisos**: puntuación de cumplimiento los usuarios a los que no se concedieron previamente permisos en el administrador de cumplimiento deben tener sus permisos establecidos en el centro de cumplimiento de Microsoft 365 (más[información](compliance-score-setup.md#set-user-permissions-and-assign-roles)). Los usuarios cuyas funciones se establecieron previamente en el administrador de cumplimiento puede usar el mismo nivel de acceso al trabajar con la puntuación de cumplimiento.
- **Transferencia de datos**: las organizaciones con datos que residen en el administrador de cumplimiento verán los datos en la puntuación de cumplimiento y viceversa.
- **Iniciar sesión en el administrador de cumplimiento desde la puntuación de cumplimiento**: Si un usuario ha iniciado sesión en puntuación de cumplimiento y selecciona un vínculo para ir al administrador de cumplimiento, el usuario no tendrá que volver a iniciar sesión. Después de hacer clic en el vínculo, se abre una nueva pestaña en el explorador que incluye un cuadro de diálogo. En la sección superior con el encabezado, "¿ya es un cliente de Microsoft Cloud Services? Inicie sesión en su cuenta, "Seleccione el botón **iniciar** sesión para iniciar sesión automáticamente en el administrador de cumplimiento.

## <a name="known-issues-in-compliance-score-preview"></a>Problemas conocidos en la puntuación de cumplimiento (versión preliminar)

En las siguientes secciones se abordan los problemas conocidos que deben resolverse en próximas versiones de la puntuación de cumplimiento.

### <a name="launch-now-links-in-certain-improvement-actions"></a>Iniciar ahora vínculos en determinadas acciones de mejora

En determinadas acciones de mejora, al seleccionar el vínculo **iniciar ahora** que aparece debajo de las instrucciones de implementación, se produce un error. Para obtener acceso al destino adecuado, que es el centro de administración de SharePoint, siga estos pasos:

1. Vaya al [centro de administración de Microsoft 365](https://admin.microsoft.com).
2. En el menú de navegación izquierdo, seleccione **Mostrar todo**.
3. En **centros de administración,** seleccione **SharePoint**.

A continuación se muestran las acciones de mejora afectadas, que residen en la categoría **proteger información** :
  - Aplicar el cifrado a la biblioteca de SharePoint
  - Clasificar datos en SharePoint Online
  - Configurar los vínculos de uso compartido externo para que expiren
  - Habilitar el control de versiones para bibliotecas de documentos

### <a name="long-load-times-for-non-admin-users"></a>Tiempos de carga prolongados para usuarios que no son administradores
Puntuación de cumplimiento los usuarios que tienen roles que no son un rol de administrador pueden experimentar tiempos de carga prolongados al intentar iniciar sesión. Al actualizar el explorador se resolverá este problema. (Obtenga más información sobre los [roles de puntuación de cumplimiento](compliance-score-setup.md#set-user-permissions-and-assign-roles)).

### <a name="supported-browsers"></a>Exploradores compatibles

- Se admiten las versiones más recientes de Microsoft Edge, Chrome y Safari.
- Puede haber casos en los que los datos actualizados no aparezcan hasta que se actualice el explorador.
- La versión preliminar de Microsoft Edge no es compatible, pero no tiene problemas conocidos.
- Internet Explorer no es compatible.
 
### <a name="language-support"></a>Compatibilidad con idiomas

- La puntuación de cumplimiento solo está disponible en inglés (Estados Unidos).