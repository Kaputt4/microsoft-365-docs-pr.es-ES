---
title: Investigación de usuarios en Microsoft 365 Defender
description: Investigue a los usuarios si hay un incidente en el portal de Microsoft 365 Defender.
keywords: security, malware, Microsoft 365, M365, security center, monitor, report, identities, data, devices, apps, incident, analyze, response
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 75fa4b76017c8fcb1f0ab65b5ed88440c04f47d2
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "67051632"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>Investigación de usuarios en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

Parte de la investigación de incidentes puede incluir cuentas de usuario. Puede ver los detalles de las cuentas de usuario identificadas en las alertas de un incidente en el portal de Microsoft 365 Defender desde **Incidentes & alertas** \> **_incident_*_ \> _* Users**. Por ejemplo:

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="La página Usuarios de un incidente en el portal de Microsoft 365 Defender." lightbox="../../media/investigate-incidents/incident-users.png":::

Para obtener un resumen rápido de una cuenta de usuario para el incidente, seleccione la marca de verificación situada junto al nombre de la cuenta de usuario. Por ejemplo:

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Pestaña Usuarios de un incidente en el portal de Microsoft 365 Defender" lightbox="../../media/investigate-users/incidents-ss-user-pane.png":::

> [!NOTE]
> La página de usuario muestra la organización de Azure Active Directory (Azure AD) y los grupos, lo que le ayuda a comprender los grupos y permisos asociados a un usuario.

En este panel, puede revisar la información de amenazas del usuario, incluidos los incidentes actuales, las alertas activas y el nivel de riesgo, así como la exposición del usuario, las cuentas, los dispositivos, etc.

Además, puede realizar acciones directamente en el portal de Microsoft 365 Defender para dirigirse a un usuario en peligro, como confirmar que la cuenta de usuario está en peligro o requerir un nuevo inicio de sesión.

Desde aquí, puede seleccionar **Ir a la página de usuario** para ver los detalles de una cuenta de usuario. Por ejemplo:

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Detalles de la cuenta de usuario en el portal de Microsoft 365 Defender" lightbox="../../media/investigate-users/incidents-ss-user-details.png":::

También puede ver esta página seleccionando el nombre de la cuenta de usuario de la lista en la página **Usuarios** .

Para ver la pertenencia a grupos del usuario, seleccione el número en **Grupos**. Al seleccionar un grupo, se abrirá el panel **Grupos** , que incluye información adicional, como la fecha de creación y la pertenencia a grupos.

> [!NOTE]
> La pertenencia a grupos solo muestra los primeros 1000 miembros del grupo.

:::image type="content" source="../../media/investigate-users/user-group-membership.png" alt-text="Información sobre la pertenencia a grupos de un usuario en el portal de Microsoft 365 Defender" lightbox="../../media/investigate-users/user-group-membership.png":::

Al seleccionar el icono en **Administrador**, puede ver dónde está el usuario en el árbol de la organización.

La página de usuario del portal de Microsoft 365 Defender combina información de Microsoft Defender para punto de conexión, Microsoft Defender for Identity y Microsoft Defender for Cloud Apps (dependiendo de las licencias que tenga).

En esta página se muestra información específica del riesgo de seguridad de una cuenta de usuario, que incluye una puntuación que ayuda a evaluar el riesgo y los eventos recientes y las alertas que contribuyeron al riesgo general.

Desde esta página, puede realizar estas acciones adicionales:

- Marcar la cuenta de usuario como en peligro
- Requerir que el usuario vuelva a iniciar sesión
- Suspender la cuenta de usuario
- Consulte la configuración de la cuenta de usuario de Azure AD.
- Visualización de los archivos propiedad de la cuenta de usuario
- Ver los archivos compartidos con este usuario.

Por ejemplo:

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="La sección que describe las acciones en una cuenta de usuario para un incidente en el portal de Microsoft 365 Defender" lightbox="../../media/investigate-users/incidents-ss-user-details-actions.png":::

## <a name="view-lateral-movement-paths"></a>Ver rutas de desplazamiento lateral

Al seleccionar la pestaña **Rutas de desplazamiento lateral** , puede ver un mapa totalmente dinámico y en el que se puede hacer clic que proporciona una representación visual de las rutas de desplazamiento lateral hacia y desde este usuario que se pueden usar para infiltrarse en la red.

El mapa proporciona una lista de cuántos saltos entre equipos o usuarios tendría un atacante hacia y desde este usuario para poner en peligro una cuenta confidencial y, si el usuario tiene una cuenta confidencial, puede ver cuántos recursos y cuentas están conectados directamente.

Si no se detectó una posible ruta de desplazamiento lateral para la entidad durante los últimos dos días, el gráfico no se muestra. Seleccione una fecha diferente mediante Ver una fecha diferente para ver los gráficos de rutas de desplazamiento lateral anteriores detectados para esta entidad. El informe de rutas de desplazamiento lateral siempre está disponible para proporcionarle información sobre las posibles rutas de desplazamiento lateral detectadas y se puede personalizar por tiempo.

:::image type="content" source="../../media/investigate-users/lateral-movement-path.png" alt-text="Ruta de desplazamiento lateral de un usuario en el portal de Microsoft 365 Defender" lightbox="../../media/investigate-users/lateral-movement-path.png":::

Para obtener más información, consulte [Rutas de desplazamiento lateral](/defender-for-identity/use-case-lateral-movement-path).

## <a name="next-steps"></a>Siguientes pasos

Según sea necesario para incidentes en proceso, continúe con la [investigación](investigate-incidents.md).

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Administrar incidentes](manage-incidents.md)
