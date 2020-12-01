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
ms.openlocfilehash: c88886e9d1470bda48d023b77472e7dd296508a0
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519358"
---
# <a name="privacy-controls-for-productivity-score"></a>Controles de privacidad para la puntuación de productividad

La puntuación de productividad ayuda a las organizaciones a transformar la manera en que se realiza el trabajo con métricas que le ayudarán a evaluar y mejorar las experiencias de personal y tecnología. Ayuda a obtener visibilidad sobre cómo funciona la organización y ofrece métricas que le ayudarán a centrarse en la habilitación de experiencias mejoradas.  También puede conectar las métricas a acciones para ayudarle a actualizar las habilidades y los sistemas de modo que todos los usuarios puedan trabajar mejor. La puntuación refleja el rendimiento de su organización y también le permite comparar de forma segura su puntuación con otras organizaciones como la suya.  Para obtener más información, consulte [información general sobre la puntuación de productividad](productivity-score.md).

Su privacidad es importante para nosotros. Para obtener información sobre cómo protegemos su privacidad, consulte la [declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement). Puntuación de productividad proporciona información vital sobre la forma en que los usuarios de las organizaciones trabajan junto con los controles para asegurarse de que la información se puede accionar sin poner en peligro la confianza que se pone en Microsoft.

En el área experiencias de personas, las métricas están disponibles en el nivel de la organización e incluyen a todos los usuarios de su inquilino de Microsoft 365. En esta área se analiza la forma en que los usuarios usan Microsoft 365 consultando las categorías de colaboración de contenido, movilidad, reuniones, trabajo en equipo y comunicación. Para ayudarle a impulsar el aprendizaje y el reconocimiento del conjunto adecuado de personas que puedan necesitar soporte con nuestros productos, también le proporcionamos información sobre el nivel individual. Aunque proporcionamos este nivel de transparencia, también le permiten disponer de varios niveles de controles para ayudarle a satisfacer sus necesidades internas de la Directiva de privacidad.
Los siguientes controles le proporcionan:

- Roles de administrador flexibles para controlar quién puede ver la información en la puntuación de productividad.
- La capacidad de identificar las métricas de nivel de usuario.
- Capacidad para dejar de participar en las experiencias de los usuarios.
- La capacidad de dejar de participar en el área de experiencias de personas

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Roles de administrador flexibles para controlar quién puede ver la información en la puntuación de productividad

Para ver toda la puntuación de productividad, incluidas las métricas a nivel de inquilino y los detalles por usuario, su rol debe ser uno de los siguientes roles de administrador:

- Administrador global
- Administradores de Exchange
- Administrador de SharePoint
- Administrador de Skype Empresarial
- Administrador de Teams
- Lector global
- Lector de informes

Asigne el rol de lector de informes a cualquier persona responsable de la administración y la adopción de los cambios. Este rol les da acceso a la experiencia completa, incluidas las métricas de nivel de inquilino y los detalles de nivel por usuario.

El informe de experiencias de personas contiene detalles de actividad por usuario para cada página de detalles de categoría. Asigne un rol personalizado denominado lector de informes de Resumen de uso (disponible a partir del 29 de octubre de 2020) para permitir el acceso solo a las métricas de las experiencias de personas. Este rol tendrá que asignarse a través de cmdlets de PowerShell hasta que se pueda asignar desde el centro de administración de Microsoft más adelante este año.

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

:::image type="content" source="../../media/communicationspage.jpg" alt-text="Página comunicaciones en los informes de productividad.":::

## <a name="de-identification-of-user-level-metrics"></a>Desidentificación de métricas en el nivel de usuario

Para hacer anónimos los datos que se recopilan para todos los informes, debe ser un administrador global. Esta acción ocultará la información identificable, como los nombres de usuario, grupo y sitio, en todos los informes, incluida la puntuación de productividad y el uso de 365 de Microsoft.

1. En el centro de administración, vaya a configuración **de la**   >   **organización** y, en la ficha **servicios** , elija **informes**.
2. Seleccione  **informes** y, a continuación, elija  **Mostrar identificadores anónimos para los nombres de usuario, grupo y sitio en informes de uso y puntuación de productividad**. Esta configuración se aplica tanto a los informes de uso como a la aplicación de plantilla.
3. Seleccione  **Guardar cambios**.

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="Hacer que la información de usuario sea anónima para los informes.":::

## <a name="capability-to-opt-out-of-people-experiences"></a>Capacidad para dejar de participar en experiencias de personas

Cuando la puntuación de productividad esté disponible por lo general, también podrá optar por el área experiencias de personas de la puntuación de productividad. Si opta por no participar, nadie de la organización podrá ver estas métricas y su organización se quitará de los cálculos relacionados con la comunicación, las reuniones, el trabajo en equipo, la colaboración de contenido y la movilidad.

1. En el centro de administración, vaya a configuración **de la**   >   **organización** y, en la ficha **servicios** , elija **informes**.
2. Seleccione  **informes** y, a continuación, desactive la casilla de verificación permitir que los  **datos de uso de Microsoft 365 se usen para personas experimenta** información. Para comprender cómo modificar la configuración de uso compartido de datos para el análisis de extremos en Intune Configuration Manager, haga clic en **más información**.
3. Seleccione  **Guardar cambios**.

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="Página de configuración de la organización en la que puede rechazar experiencias de personas.":::