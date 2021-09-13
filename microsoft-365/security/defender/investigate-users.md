---
title: Investigar usuarios en Microsoft 365 Defender
description: Investigue a los usuarios por un incidente en el portal Microsoft 365 Defender web.
keywords: seguridad, malware, Microsoft 365, M365, centro de seguridad, monitor, informe, identidades, datos, dispositivos, aplicaciones, incidentes, análisis, respuesta
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: d7decb3e566f8bb0abf4a3aec12e2e3a43ae3511
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218180"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>Investigar usuarios en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

Parte de la investigación de incidentes puede incluir cuentas de usuario. Comience con la **pestaña Usuarios** para un incidente de Incidentes & **de** \> **_alertas_ _ *\> _* Usuarios**.

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Ejemplo de una página Usuarios para un incidente.":::

Para obtener un resumen rápido de una cuenta de usuario para el incidente, seleccione la marca de verificación junto al nombre de la cuenta de usuario. Por ejemplo:

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Ejemplo del panel de resumen de la cuenta de usuario para un incidente en el portal Microsoft 365 Defender usuario":::

> [!NOTE]
> La página Usuario muestra Azure Active Directory organización (Azure AD) así como grupos, lo que le ayuda a comprender los grupos y permisos asociados con un usuario.

En esta página desplegable, puede revisar la información de amenazas del usuario, incluidos los incidentes actuales, las alertas activas y el nivel de riesgo, así como la exposición del usuario, cuentas, dispositivos y mucho más.

Además, puede realizar acciones directamente en el portal de Microsoft 365 Defender para abordar un usuario en peligro, confirmando que el usuario está en peligro o requiriendo que vuelva a iniciar sesión.

Desde aquí, puede seleccionar **Ir a la página de usuario** para ver los detalles de una cuenta de usuario. Por ejemplo:

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Ejemplo de la página de cuenta de usuario para un incidente en el portal Microsoft 365 Defender usuario":::

También puede ver esta página seleccionando el nombre de la cuenta de usuario de la lista de la **página** Usuarios.

Puede ver la pertenencia a grupos para el usuario, seleccionando el número en **Grupos**.

:::image type="content" source="../../media/investigate-users/user-group-membership.png" alt-text="Ejemplo de pertenencia a grupos para un usuario en el portal de Microsoft 365 Defender grupo":::

Al seleccionar el icono en **Administrador,** puede ver dónde está el usuario en el árbol de la organización.

La página Microsoft 365 Defender usuario del portal combina información de Microsoft Defender para endpoint, Microsoft Defender for Identity y Microsoft Cloud App Security (en función de las licencias que tenga).

Esta página muestra información específica del riesgo de seguridad de una cuenta de usuario. Esto incluye una puntuación que ayuda a evaluar el riesgo y los eventos recientes y las alertas que contribuyeron al riesgo general del usuario.

Desde esta página, puede realizar estas acciones adicionales:

- Marcar la cuenta de usuario como comprometida
- Requerir que el usuario inicie sesión de nuevo
- Suspender la cuenta de usuario
- Consulta la configuración Azure Active Directory cuenta de usuario de Azure Active Directory (Azure AD)
- Ver los archivos propiedad de la cuenta de usuario
- Ver archivos compartidos con este usuario.

Por ejemplo:

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Ejemplo de las acciones de una cuenta de usuario para un incidente en el portal Microsoft 365 Defender usuario":::

<!--
You can access this page from multiple areas in the Microsoft 365 Defender portal. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

-->

## <a name="view-lateral-movement-paths"></a>Ver rutas de movimiento lateral

Al seleccionar  la pestaña Rutas de movimiento lateral, puede ver un mapa totalmente dinámico y en el que se puede hacer clic que le proporciona una representación visual de las rutas de acceso de movimiento lateral hacia y desde este usuario que se puede usar para infiltrar la red.

El mapa le proporciona una lista de la cantidad de saltos entre equipos o usuarios que un atacante tendría que hacer y desde este usuario para poner en peligro una cuenta confidencial, y si el usuario tiene una cuenta confidencial, puede ver cuántos recursos y cuentas están conectados directamente.

Si no se detectó una ruta de movimiento lateral potencial para la entidad durante los últimos dos días, el gráfico no se muestra. Seleccione una fecha diferente mediante Ver una fecha diferente para ver los gráficos de rutas de movimiento lateral anteriores detectados para esta entidad. El informe de ruta de movimiento lateral siempre está disponible para proporcionar información sobre las rutas de movimiento lateral potenciales detectadas y se puede personalizar por tiempo.

:::image type="content" source="../../media/investigate-users/lateral-movement-path.png" alt-text="Ejemplo de la ruta de acceso de movimiento lateral para un usuario en el portal Microsoft 365 Defender usuario":::

Para obtener más información, vea [Rutas de movimiento lateral](/defender-for-identity/use-case-lateral-movement-path).

## <a name="next-steps"></a>Siguientes pasos

Según sea necesario para incidentes en el proceso, continúe con la [investigación](investigate-incidents.md).

## <a name="see-also"></a>Consulte también

- [Información general sobre incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Administrar incidentes](manage-incidents.md)
