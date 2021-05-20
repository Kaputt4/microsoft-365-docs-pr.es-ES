---
title: Investigan usuarios en Microsoft 365 Defender
description: Investigue a los usuarios por un incidente en el centro de seguridad de Microsoft 365.
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
ms.openlocfilehash: 72eb111da2f342b78aa6161c7334a7252314b4a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572806"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>Investigan usuarios en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

Parte de la investigación de incidentes puede incluir cuentas de usuario. Comience con la pestaña **Usuarios** para detectar un incidente de **incidentes & alertas >** *incidente* **> usuarios.** 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Ejemplo de una página de usuarios para un incidente":::

Para obtener un resumen rápido de una cuenta de usuario para el incidente, seleccione la marca de verificación junto al nombre de la cuenta de usuario. Por ejemplo:

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Ejemplo del panel de resumen de la cuenta de usuario para un incidente en el centro de seguridad de Microsoft 365":::

> [!NOTE]
> La página Usuario muestra Azure Active Directory organización (Azure AD), así como grupos, lo que le ayuda a comprender los grupos y permisos asociados a un usuario.

En esta página desplegable, puede revisar la información de amenazas de los usuarios, incluidos los incidentes actuales, las alertas activas y el nivel de riesgo, así como la exposición del usuario, las cuentas, los dispositivos y mucho más.

Además, puede tomar medidas directamente en el centro de seguridad Microsoft 365 para dirigirse a un usuario comprometido, confirmando que el usuario está comprometido o requiriendo que vuelva a iniciar sesión.

Desde aquí, puede seleccionar **Ir a la página de usuario** para ver los detalles de una cuenta de usuario. Por ejemplo:

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Ejemplo de la página de la cuenta de usuario para un incidente en el centro de seguridad de Microsoft 365":::

También puede ver esta página seleccionando el nombre de la cuenta de usuario de la lista de la página **Usuarios.**

La página de usuario del centro de seguridad de Microsoft 365 combina información de Microsoft Defender para Endpoint, Microsoft Defender for Identity y Microsoft Cloud App Security (en función de las licencias que tenga). 

Esta página muestra información específica del riesgo de seguridad de una cuenta de usuario. Esto incluye una puntuación que ayuda a evaluar el riesgo y los eventos y alertas recientes que contribuyeron al riesgo general del usuario.

Desde esta página, puede realizar estas acciones adicionales: 

- Marque la cuenta de usuario como comprometida
- Requerir que el usuario vuelva a iniciar sesión
- Suspender la cuenta de usuario
- Consulte la configuración de la cuenta de usuario de Azure Active Directory (Azure AD)
- Ver los archivos propiedad de la cuenta de usuario
- Ver archivos compartidos con este usuario. 

Por ejemplo:

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Ejemplo de las acciones de una cuenta de usuario para un incidente en el centro de seguridad de Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a>Pasos siguientes

Según sea necesario para incidentes en proceso, continúe su [investigación.](investigate-incidents.md)

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Administrar incidentes](manage-incidents.md)