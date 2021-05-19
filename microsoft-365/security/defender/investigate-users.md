---
title: Investigar usuarios en Microsoft 365 Defender
description: Investigar a los usuarios por un incidente en el Microsoft 365 de seguridad.
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
ms.openlocfilehash: 7084b9370a0dd83265b37ff1d152e2164fe32813
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539136"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>Investigar usuarios en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

Parte de la investigación de incidentes puede incluir cuentas de usuario. Comience con la **pestaña Usuarios** para un incidente de incidentes & **alertas** >*incidentes>* **Usuarios**. 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Ejemplo de una página Usuarios para un incidente":::

Para obtener un resumen rápido de una cuenta de usuario para el incidente, seleccione la marca de verificación junto al nombre de la cuenta de usuario. Por ejemplo:

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Ejemplo del panel de resumen de la cuenta de usuario para un incidente en el centro Microsoft 365 de seguridad":::

> [!NOTE]
> La página Usuario muestra Azure Active Directory organización (AD) así como grupos, lo que le ayuda a comprender los grupos y permisos asociados con un usuario.

En esta página desplegable, puede revisar la información de amenazas del usuario, incluidos los incidentes actuales, las alertas activas y el nivel de riesgo, así como la exposición del usuario, cuentas, dispositivos y mucho más.

Además, puede realizar acciones directamente en el centro de seguridad de Microsoft 365 para abordar un usuario en peligro, confirmando que el usuario está en peligro o requiriendo que vuelva a iniciar sesión.

Desde aquí, puede seleccionar **Ir a la página de usuario** para ver los detalles de una cuenta de usuario. Por ejemplo:

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Ejemplo de la página de cuenta de usuario para un incidente en el centro Microsoft 365 seguridad":::

También puede ver esta página seleccionando el nombre de la cuenta de usuario de la lista de la **página** Usuarios.

La página Microsoft 365 usuario del Centro de seguridad combina información de Microsoft Defender para endpoint, Microsoft Defender for Identity y Microsoft Cloud App Security (en función de las licencias que tenga). 

Esta página muestra información específica del riesgo de seguridad de una cuenta de usuario. Esto incluye una puntuación que ayuda a evaluar el riesgo y los eventos recientes y las alertas que contribuyeron al riesgo general del usuario.

Desde esta página, puede realizar estas acciones adicionales: 

- Marcar la cuenta de usuario como comprometida
- Requerir que el usuario inicie sesión de nuevo
- Suspender la cuenta de usuario
- Consulta la configuración Azure Active Directory cuenta de usuario de Azure Active Directory (Azure AD)
- Ver los archivos propiedad de la cuenta de usuario
- Ver archivos compartidos con este usuario. 

Por ejemplo:

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Ejemplo de las acciones en una cuenta de usuario para un incidente en el centro Microsoft 365 seguridad":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a>Pasos siguientes

Según sea necesario para incidentes en el proceso, continúe con la [investigación](investigate-incidents.md).

## <a name="see-also"></a>Consulte también

- [Información general sobre incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Administrar incidentes](manage-incidents.md)