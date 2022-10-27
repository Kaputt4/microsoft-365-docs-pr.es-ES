---
title: 'Puntuación de adopción de Microsoft: privacidad'
f1.keywords:
- NOCSH
ms.author: camillepack
author: camillepack
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
monikerRange: o365-worldwide
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Cómo se protege la privacidad con la Puntuación de adopción.
ms.openlocfilehash: 74ca30762ecaccc03ff76c7c928f3f96f566a05c
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68726869"
---
# <a name="privacy-controls-for-adoption-score"></a>Controles de privacidad para la puntuación de adopción

La Puntuación de adopción proporciona información sobre el recorrido de transformación digital de su organización a través de su uso de Microsoft 365 y las experiencias tecnológicas que la admiten.  La puntuación de su organización refleja las mediciones de la experiencia de las personas y la tecnología y se puede comparar con las pruebas comparativas de organizaciones similares a las suyas. Para obtener más información, vea la [introducción a la puntuación de adopción](adoption-score.md).

Su privacidad es importante para Microsoft. Para obtener información sobre cómo protegemos su privacidad, consulte [la declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement). La puntuación de adopción le proporciona, como administrador de TI de su organización, acceso a la configuración de privacidad para asegurarse de que cualquier información de puntuación de adopción que vea sea accionable, sin poner en peligro la confianza que su organización coloca en Microsoft.

Dentro del área de experiencias de personas, las métricas solo están disponibles a nivel organizativo. En esta área se examina cómo los usuarios usan Microsoft 365 examinando las categorías de colaboración de contenido, movilidad, reuniones, trabajo en equipo y comunicación. Le habilitamos con varios niveles de controles para ayudarle a satisfacer sus necesidades de directiva de privacidad internas.
Los controles proporcionan lo siguiente:

- Roles de administrador flexibles para controlar quién puede ver la información en La puntuación de adopción
- La capacidad de quitar usuarios y grupos de los cálculos de la experiencia de los usuarios
- La capacidad de optar por no participar en el área de experiencias de personas

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-adoption-score"></a>Roles de administrador flexibles para controlar quién puede ver la información en La puntuación de adopción

Para ver toda la puntuación de adopción, debe ser uno de los siguientes roles de administrador:

- Administrador global
- Administrador de Exchange
- Administrador de SharePoint
- Administrador de Skype Empresarial
- Administrador de Teams
- Lector global
- Lector de informes
- Resumen de uso de Lector de informes
- Administrador de éxito de la experiencia del usuario

El administrador global puede asignar el rol Lector de informes, el rol Lector de informes de resumen de uso o el rol Administrador de éxito de experiencia de usuario a cualquier persona responsable de la administración y adopción de cambios, pero no necesariamente un administrador de TI.

Los usuarios con el rol Lector de informes pueden ver los datos de informes de uso y el panel de informes en Centro de administración de Microsoft 365 y el paquete de contexto de adopción en Power BI. Los usuarios con el rol Lector de informes de resumen de uso solo pueden ver agregados de nivel de inquilino y agregados de nivel de grupo en Análisis de uso y puntuación de adopción de Microsoft 365. El rol Administrador de éxito de experiencia del usuario incluye los permisos del rol Lector de informes de resumen de uso y puede obtener acceso a más información relacionada con la adopción, como el Centro de mensajes, los comentarios del producto y el estado del servicio. Consulte [Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference) para obtener más información sobre los distintos roles.

## <a name="capability-to-choose-specific-users-or-certain-groups"></a>Capacidad para elegir usuarios específicos o determinados grupos

Puede elegir los usuarios y grupos cuyos datos se usarán para determinar la información de experiencias de personas de la organización. La omisión de algunos grupos afectará a los cálculos de conclusiones. Debe ser un administrador global para excluir a su organización de los informes de experiencias de personas. El cambio puede tardar hasta 24 horas en aplicarse.

Para omitir determinados grupos:

1. En el centro de administración, vaya a **Configuración Configuración** > **De la configuración de** >  la organización **Puntuación de adopción**.
2. Seleccione **Excluir usuarios específicos a través del grupo**.  
3. Elija uno o varios grupos de AAD del Centro de Administración para omitirlos.
4. Seleccione **Guardar cambios**.

:::image type="content" source="../../media/adoption-score-exclude-users.png" alt-text="Captura de pantalla: opción para excluir usuarios específicos a través del grupo al calcular la información.":::

## <a name="capability-to-opt-out-of-people-experiences"></a>Capacidad para no participar en experiencias de personas

También puede optar por no participar en el área de experiencias de personas de La puntuación de adopción. Si opta por no participar, nadie de su organización podrá ver estas métricas y su organización se quitará de los cálculos que impliquen comunicación, reuniones, trabajo en equipo, colaboración de contenido y movilidad. Debe ser un administrador global para excluir a su organización de los informes de experiencias de personas. El cambio puede tardar hasta 24 horas en aplicarse. Puede revertir el cambio antes del final del día en hora UTC para mantener los datos históricos.

Para optar por no participar:

1. En el centro de administración, vaya a **Configuración Configuración**  >  **De la configuración de** >  la organización **Puntuación de adopción**.
2. Seleccione **No calcular para ningún usuario**. 
3. En la pantalla de confirmación **¿Desea quitar datos de experiencias de personas?** , seleccione **Quitar datos**.
4. Seleccione  **Guardar**.

:::image type="content" source="../../media/adoption-score-calculate-insights.png" alt-text="Captura de pantalla: Opción de configuración de la organización para no participar en la información de experiencias de personas":::
