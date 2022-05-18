---
title: Puntuación de productividad de Microsoft e información de privacidad
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Cómo se protege la privacidad con la Puntuación de productividad.
ms.openlocfilehash: 823e2cc087d3f0e9c486d8c0c4eca92ba42aee21
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2022
ms.locfileid: "65467940"
---
# <a name="privacy-controls-for-productivity-score"></a>Controles de privacidad para la puntuación de productividad

La puntuación de productividad proporciona información sobre el recorrido de transformación digital de su organización a través de su uso de Microsoft 365 y las experiencias tecnológicas que lo respaldan.  La puntuación de su organización refleja las mediciones de la experiencia de las personas y la tecnología y se puede comparar con las pruebas comparativas de organizaciones similares a las suyas. Para obtener más información, vea la [introducción a la puntuación de productividad](productivity-score.md).

Su privacidad es importante para Microsoft. Para obtener información sobre cómo protegemos su privacidad, consulte [la declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement). La puntuación de productividad le proporciona, como administrador de TI de su organización, acceso a la configuración de privacidad para asegurarse de que cualquier información de puntuación de productividad que vea sea accionable, sin poner en peligro la confianza que su organización coloca en Microsoft.

Dentro del área de experiencias de personas, las métricas solo están disponibles a nivel organizativo. En esta área se examina cómo los usuarios usan Microsoft 365 examinando las categorías de colaboración de contenido, movilidad, reuniones, trabajo en equipo y comunicación. Le habilitamos con varios niveles de controles para ayudarle a satisfacer sus necesidades de directiva de privacidad internas.
Los controles proporcionan lo siguiente:

- Roles de administrador flexibles para controlar quién puede ver la información en Puntuación de productividad.
- La capacidad de optar por no participar en el área de experiencias de personas.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Roles de administrador flexibles para controlar quién puede ver la información en Puntuación de productividad

Para ver toda la puntuación de productividad, debe ser uno de los siguientes roles de administrador:

- Administrador global
- Administrador de Exchange
- Administrador de SharePoint
- Administrador de Skype Empresarial
- Administrador de Teams
- Lector global
- Lector de informes
- Resumen de uso de Lector de informes

Asigne el rol Lector de informes o Lector de informes de resumen de uso a cualquier persona responsable de la administración y adopción de cambios, pero no necesariamente un administrador de TI. Este rol les proporciona acceso a la experiencia de puntuación de productividad completa en el Centro de administración de Microsoft 365.

El rol Lector de informes de resumen de uso tendrá que asignarse a través de cmdlets de PowerShell hasta que se pueda asignar desde el Centro de administración de Microsoft 365 más adelante en 2020.

Para asignar el rol Lector de informes de resumen de uso con PowerShell:

- Ejecute el siguiente PowerShell:

```powershell
Connect-AzureAD
Enable-AzureADDirectoryRole -RoleTemplateId '75934031-6c7e-415a-99d7-48dbd49e875e'
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>


## <a name="capability-to-opt-out-of-people-experiences"></a>Capacidad para no participar en experiencias de personas

También puede optar por no participar en el área de experiencias de personas de La puntuación de productividad. Si opta por no participar, nadie de su organización podrá ver estas métricas y su organización se quitará de los cálculos que impliquen comunicación, reuniones, trabajo en equipo, colaboración de contenido y movilidad. Debe ser un administrador global para excluir a su organización de los informes de experiencias de personas.

Para optar por no participar:

1. En el centro de administración, vaya a **Configuración**  >   **Org Configuración** >  **Productivity Score(Puntuación de producción).**
2. Quite la marca de la casilla **Permitir que se usen datos de uso de Microsoft 365 para la información de experiencias de las personas**. Para comprender cómo modificar la configuración de uso compartido de datos para Endpoint Analytics en el administrador de configuración de Intune, seleccione **Más información**.
3. Seleccione  **Guardar**.

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Página de configuración de la organización en la que puede optar por no participar en experiencias de personas.":::
