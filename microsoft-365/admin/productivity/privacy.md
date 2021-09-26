---
title: 'Puntuación de productividad de Microsoft: privacidad'
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Cómo se protege la privacidad con la puntuación de productividad.
ms.openlocfilehash: d849f4cc8924aac09ca41f30682e32babfcc7f13
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2021
ms.locfileid: "59776121"
---
# <a name="privacy-controls-for-productivity-score"></a>Controles de privacidad para la puntuación de productividad

La puntuación de productividad proporciona información sobre el recorrido de transformación digital de su organización a través del uso de Microsoft 365 y las experiencias tecnológicas que lo admiten.  La puntuación de su organización refleja las mediciones de la experiencia de personas y tecnología y se puede comparar con los puntos de referencia de organizaciones similares al tuyo. Para obtener más información, vea la información general [sobre la puntuación de productividad](productivity-score.md).

Su privacidad es importante para Microsoft. Para obtener información sobre cómo protegemos su privacidad, vea [la declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement). La puntuación de productividad le ofrece, como administrador de TI de su organización, acceso a la configuración de privacidad para asegurarse de que cualquier información de puntuación de productividad que vea sea útil, sin comprometer la confianza que su organización deposita en Microsoft.

Dentro del área de experiencias de personas, las métricas solo están disponibles en el nivel organizativo. En esta área se analiza cómo las personas usan Microsoft 365 las categorías de colaboración de contenido, movilidad, reuniones, trabajo en equipo y comunicación. Le habilitamos con varios niveles de controles para ayudarle a satisfacer sus necesidades de directiva de privacidad interna.
Los controles le dan:

- Roles de administrador flexibles para controlar quién puede ver la información en La puntuación de productividad.
- La capacidad de no participar en el área de experiencias de personas.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Roles de administrador flexibles para controlar quién puede ver la información en La puntuación de productividad

Para ver toda la puntuación de productividad, debe ser uno de los siguientes roles de administrador:

- Administrador global
- Administrador de Exchange
- Administrador de SharePoint
- Administrador de Skype Empresarial
- Administrador de Teams
- Lector global
- Lector de informes
- Resumen de uso de Lector de informes

Asigna el lector de informes o el rol lector de informes de resumen de uso a cualquier persona responsable de la administración y adopción de cambios, pero no necesariamente un administrador de TI. Este rol les da acceso a la experiencia completa de la puntuación de productividad en el Centro Microsoft 365 administración.

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


## <a name="capability-to-opt-out-of-people-experiences"></a>Capacidad para excluirse de las experiencias de las personas

También puede optar por no participar en el área de experiencias de personas de La puntuación de productividad. Si opta por no participar, nadie de su organización podrá ver estas métricas y su organización se quitará de los cálculos que impliquen comunicación, reuniones, trabajo en equipo, colaboración de contenido y movilidad. Debe ser un administrador global para excluir la organización de los informes de experiencias de personas.

Para optar por no participar:

1. En el Centro de administración, vaya **a Configuración**   >   **Org Configuración** Productivity  >  **Score**.
2. Des active la casilla que indica Permitir Microsoft 365 datos de uso **que se usarán para las experiencias de personas.** Para comprender cómo modificar la configuración de uso compartido de datos para Endpoint Analytics en el administrador de configuración de Intune, seleccione **Obtener más información.**
3. Seleccione  **Guardar**.

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Página de configuración de la organización en la que puedes excluirte de las experiencias de las personas.":::
