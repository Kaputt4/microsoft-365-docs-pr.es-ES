---
title: 'Puntuación de productividad de Microsoft: privacidad'
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Cómo se protege la privacidad con la puntuación de productividad.
ms.openlocfilehash: ceb19fcb7bbf2f6a58e38684604ed3b0dac2a5d4
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604331"
---
# <a name="privacy-controls-for-productivity-score"></a>Controles de privacidad para la puntuación de productividad

La puntuación de productividad proporciona información sobre el recorrido de transformación digital de su organización a través del uso de Microsoft 365 y las experiencias tecnológicas que lo admiten.  La puntuación de su organización refleja las mediciones de experiencia de personas y tecnología y se puede comparar con los indicadores de organizaciones similares a los tuyos. Para obtener más información, vea la información general [sobre la puntuación de productividad.](productivity-score.md)

Su privacidad es importante para Microsoft. Para obtener información sobre cómo protegemos su privacidad, consulte la [declaración de privacidad de Microsoft.](https://privacy.microsoft.com/privacystatement) La puntuación de productividad le proporciona, como administrador de TI de su organización, acceso a la configuración de privacidad para ayudar a asegurarse de que cualquier información de puntuación de productividad que vea sea útil, sin poner en peligro la confianza que su organización coloca en Microsoft.

Dentro del área de experiencias de personas, las métricas solo están disponibles en el nivel organizativo. En esta área se analiza cómo los usuarios usan Microsoft 365 al ver las categorías de colaboración de contenido, movilidad, reuniones, trabajo en equipo y comunicación. Le habilitamos con varios niveles de controles para ayudarle a satisfacer sus necesidades de directiva de privacidad interna.
Los controles te dan:

- Roles de administrador flexibles para controlar quién puede ver la información en la puntuación de productividad.
- La capacidad de optar por no participar en el área de experiencias de personas.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Roles de administrador flexibles para controlar quién puede ver la información en la puntuación de productividad

Para ver la puntuación de productividad completa, debe ser uno de los siguientes roles de administrador:

- Administrador global
- Administrador de Exchange
- Administrador de SharePoint
- Administrador de Skype Empresarial
- Administrador de Teams
- Lector global
- Lector de informes
- Resumen de uso de Lector de informes

Asigne el lector de informes o el rol lector de informes de resumen de uso a cualquier persona responsable de la administración y adopción de cambios, pero no necesariamente un administrador de TI. Este rol les proporciona acceso a la experiencia completa de la puntuación de productividad en el Centro de administración de Microsoft 365.

El rol lector de informes de resumen de uso tendrá que asignarse a través de los cmdlets de PowerShell hasta que se pueda asignar desde el Centro de administración de Microsoft 365 más adelante en 2020.

Para asignar el rol lector de informes de resumen de uso con PowerShell:

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


## <a name="capability-to-opt-out-of-people-experiences"></a>Capacidad de optar por no participar en experiencias de personas

También puede optar por no participar en el área de experiencias de personas de la puntuación de productividad. Si opta por no participar, nadie de su organización podrá ver estas métricas y su organización se quitará de los cálculos que impliquen comunicación, reuniones, trabajo en equipo, colaboración de contenido y movilidad. Debe ser un administrador global para excluir a su organización de los informes de experiencias de personas.

Para optar por poner:

1. En el centro de administración, vaya a **Configuración** de la organización y, en la pestaña   >   Servicios, seleccione **Informes.** 
2. Des marque la casilla que indica Permitir que los datos de uso de  **Microsoft 365 se** usen para obtener información sobre las experiencias de las personas. Para comprender cómo modificar la configuración de uso compartido de datos para Endpoint Analytics en el Administrador de configuración de Intune, seleccione **Más información.**
3. Seleccione  **Guardar**.

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Página de configuración de la organización en la que puede optar por no participar en las experiencias de las personas.":::