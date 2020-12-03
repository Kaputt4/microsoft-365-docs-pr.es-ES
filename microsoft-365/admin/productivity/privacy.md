---
title: Puntuación de productividad de Microsoft-privacidad
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
ms.openlocfilehash: db123042761b07ed64dd2dd94e783d65205e1460
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561519"
---
# <a name="privacy-controls-for-productivity-score"></a>Controles de privacidad para la puntuación de productividad

La puntuación de productividad proporciona información sobre el recorrido de la transformación digital de la organización mediante el uso de Microsoft 365 y las experiencias tecnológicas que la admiten.  La puntuación de su organización refleja las medidas de los usuarios y la experiencia tecnológica y se puede comparar con los benchmarks de organizaciones similares a la suya. Para obtener más información, vea [información general sobre la puntuación de productividad](productivity-score.md).

Su privacidad es importante para Microsoft. Para obtener información sobre cómo protegemos su privacidad, consulte la [declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement). La puntuación de productividad le proporciona, como administrador de TI de su organización, acceso a la configuración de privacidad para ayudar a garantizar que la información de puntuación de productividad que vea es accionable, sin poner en peligro la confianza que su organización pone en Microsoft.

En el área experiencias de personas, las métricas solo están disponibles en el nivel de la organización. En esta área se analiza la forma en que los usuarios usan Microsoft 365 consultando las categorías de colaboración de contenido, movilidad, reuniones, trabajo en equipo y comunicación. Le habilitamos con varios niveles de controles para ayudarle a satisfacer sus necesidades internas de la Directiva de privacidad.
Los controles le proporcionan:

- Roles de administrador flexibles para controlar quién puede ver la información en la puntuación de productividad.
- La capacidad de dejar de participar en el área experiencias de personas.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Roles de administrador flexibles para controlar quién puede ver la información en la puntuación de productividad

Para ver la puntuación de productividad completa, debe ser uno de los siguientes roles de administrador:

- Administrador global
- Administradores de Exchange
- Administrador de SharePoint
- Administrador de Skype Empresarial
- Administrador de Teams
- Lector global
- Lector de informes
- Lector de informes de Resumen de uso

Asigne el rol lector de informes o informes de Resumen de uso a cualquier usuario responsable de la administración y la adopción de los cambios, pero no necesariamente un administrador de ti. Este rol les da acceso a la experiencia de puntuación de productividad completa en el centro de administración de 365 de Microsoft.

El rol lector de informes de Resumen de uso tendrá que asignarse a través de cmdlets de PowerShell hasta que se pueda asignar desde el centro de administración de Microsoft 365 más adelante en 2020.

Para asignar el rol lector de informes de Resumen de uso con PowerShell:

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


## <a name="capability-to-opt-out-of-people-experiences"></a>Capacidad para dejar de participar en experiencias de personas

También puede optar por no participar en el área de experiencias de personas de la puntuación de productividad. Si opta por no participar, nadie de su organización podrá ver estas métricas y su organización se quitará de los cálculos relacionados con la comunicación, las reuniones, el trabajo en equipo, la colaboración de contenido y la movilidad.

Para opt put:

1. En el centro de administración, vaya a configuración de la organización de **configuración**   >   **Org Settings** y, en la ficha **servicios** , seleccione **informes**.
2. Desactive la casilla de verificación permitir que los  **datos de uso de Microsoft 365 se usen para personas que experimenten** información. Para comprender cómo modificar la configuración de uso compartido de datos para el análisis de extremos en Intune Configuration Manager, seleccione **más información**.
3. Seleccione  **Guardar**.

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Página de configuración de la organización en la que puede rechazar experiencias de personas.":::