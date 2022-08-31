---
title: Abordar las cuentas de usuario en peligro con una investigación y respuesta automatizadas
keywords: AIR, autoIR, Microsoft Defender para punto de conexión, automatizado, investigación, respuesta, corrección, amenazas, avanzado, amenaza, protección, en peligro
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.custom: ''
ms.date: 06/10/2021
description: Obtenga información sobre cómo acelerar el proceso de detección y direccionamiento de cuentas de usuario en peligro con funcionalidades automatizadas de investigación y respuesta en Microsoft Defender para Office 365 Plan 2.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 5c6bd48759382209375201b2e95ac71ccce4d0f4
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482216"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Abordar las cuentas de usuario en peligro con una investigación y respuesta automatizadas

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender para Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) incluye eficaces funcionalidades [de investigación y respuesta automatizadas](office-365-air.md) (AIR). Estas funcionalidades pueden ahorrar mucho tiempo y esfuerzo al equipo de operaciones de seguridad frente a amenazas. Microsoft sigue mejorando las funcionalidades de seguridad. Recientemente, las funcionalidades de AIR se han mejorado para incluir un cuaderno de estrategias de seguridad de usuario en peligro (actualmente en versión preliminar). Lea este artículo para obtener más información sobre el cuaderno de estrategias de seguridad de usuario en peligro. Y vea la entrada de blog [Acelerar el tiempo para detectar y responder al riesgo del usuario y limitar el ámbito de vulneración con Microsoft Defender para Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) para obtener más detalles.

![Investigación automatizada para un usuario en peligro.](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

El cuaderno de estrategias de seguridad de usuario en peligro permite al equipo de seguridad de su organización:

- Acelerar la detección de cuentas de usuario en peligro;
- Limitar el ámbito de una infracción cuando una cuenta está en peligro; Y
- Responda a los usuarios en peligro de forma más eficaz y eficaz.

## <a name="compromised-user-alerts"></a>Alertas de usuario en peligro

Cuando una cuenta de usuario está en peligro, se producen comportamientos atípicos o anómalo. Por ejemplo, los mensajes de phishing y correo no deseado se pueden enviar internamente desde una cuenta de usuario de confianza. Defender para Office 365 puede detectar estas anomalías en los patrones de correo electrónico y la actividad de colaboración dentro de Office 365. Cuando esto sucede, se desencadenan alertas y comienza el proceso de mitigación de amenazas.

Por ejemplo, esta es una alerta que se desencadenó debido al envío de correo electrónico sospechoso:

![Alerta desencadenada debido al envío de correo electrónico sospechoso.](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Este es un ejemplo de una alerta que se desencadenó cuando se alcanzó un límite de envío para un usuario:

![Alerta desencadenada por el envío del límite alcanzado.](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Investigación y respuesta a un usuario en peligro

Cuando una cuenta de usuario está en peligro, se desencadenan alertas. Y, en algunos casos, esa cuenta de usuario se bloquea e impide el envío de más mensajes de correo electrónico hasta que el equipo de operaciones de seguridad de la organización resuelva el problema. En otros casos, comienza una investigación automatizada que puede dar lugar a acciones recomendadas que el equipo de seguridad debe realizar.

- [Visualización e investigación de usuarios restringidos](#view-and-investigate-restricted-users)

- [Ver detalles sobre las investigaciones automatizadas](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Debe tener los permisos adecuados para realizar las siguientes tareas. Consulte [Permisos necesarios para usar las funcionalidades de AIR](office-365-air.md#required-permissions-to-use-air-capabilities).

Vea este breve vídeo para aprender a detectar y responder a los riesgos del usuario en Microsoft Defender para Office 365 mediante la investigación y respuesta automatizadas (AIR) y las alertas de usuario en peligro.
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWAl83]

### <a name="view-and-investigate-restricted-users"></a>Visualización e investigación de usuarios restringidos

Tiene algunas opciones para navegar a una lista de usuarios restringidos. Por ejemplo, en el portal de Microsoft 365 Defender, puede ir a **Email & colaboración** \> **Revisar** \> **usuarios restringidos**. En el procedimiento siguiente se describe la navegación mediante el panel **Alertas** , que es una buena manera de ver varios tipos de alertas que podrían haberse desencadenado.

1. Abra el portal Microsoft 365 Defender en <https://security.microsoft.com> y vaya a **Incidentes & alertas** \> **alertas**. O bien, para ir directamente a la página **Alertas** , use <https://security.microsoft.com/alerts>.

2. En la página **Alertas** , filtre los resultados por período de tiempo y la directiva denominada **Usuario restringido al envío de correo electrónico**.

   :::image type="content" source="../../media/m365-sc-alerts-page-with-restricted-user.png" alt-text="Página Alertas del portal de Microsoft 365 Defender filtrado para usuarios restringidos" lightbox="../../media/m365-sc-alerts-page-with-restricted-user.png":::

3. Si selecciona la entrada haciendo clic en el nombre, se abrirá una página **Usuario restringido al envío de correo electrónico** con detalles adicionales para revisar. Junto al botón **Administrar alerta** , puede hacer clic en ![el icono Más opciones.](../../media/m365-cc-sc-more-actions-icon.png) **Más opciones** y, a continuación, seleccione **Ver detalles de usuario restringido** para ir a la página **Usuarios restringidos** , donde puede [liberar al usuario restringido](removing-user-from-restricted-users-portal-after-spam.md).

  :::image type="content" source="../../media/m365-sc-alerts-user-restricted-from-sending-email-page.png" alt-text="La página Usuario restringido al envío de correo electrónico" lightbox="../../media/m365-sc-alerts-user-restricted-from-sending-email-page.png":::

### <a name="view-details-about-automated-investigations"></a>Ver detalles sobre las investigaciones automatizadas

Una vez iniciada una investigación automatizada, puede ver sus detalles y resultados en el Centro de cumplimiento de seguridad &. Vaya a **Investigaciones** de **administración** \> de amenazas y seleccione una investigación para ver sus detalles.

Para más información, consulte [Visualización de los detalles de una investigación](air-view-investigation-results.md).

## <a name="keep-the-following-points-in-mind"></a>Tenga en cuenta los siguientes puntos

- **Manténgase al tanto de las alertas**. Como sabe, cuanto más tiempo no se detecte un riesgo, mayor será el potencial de impacto y costo generalizados para su organización, clientes y asociados. La detección temprana y la respuesta oportuna son fundamentales para mitigar las amenazas y, especialmente, cuando la cuenta de un usuario está en peligro.

- **Automation ayuda, pero no reemplaza, al equipo de operaciones de seguridad**. Las funcionalidades automatizadas de investigación y respuesta pueden detectar un usuario en peligro al principio, pero es probable que el equipo de operaciones de seguridad tenga que participar y realizar alguna investigación y corrección. ¿Necesitas ayuda con esto? Consulte [Revisar y aprobar acciones](air-review-approve-pending-completed-actions.md).

- **No confíe en una alerta de inicio de sesión sospechosa como único indicador**. Cuando una cuenta de usuario está en peligro, es posible que desencadene o no una alerta de inicio de sesión sospechosa. A veces es la serie de actividades que se producen después de que una cuenta está en peligro lo que desencadena una alerta. ¿Desea obtener más información sobre las alertas? Consulte [Directivas de alerta](../../compliance/alert-policies.md).

## <a name="next-steps"></a>Pasos siguientes

- [Revisión de los permisos necesarios para usar las funcionalidades de AIR](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Búsqueda e investigación de correo electrónico malintencionado en Office 365](investigate-malicious-email-that-was-delivered.md)

- [Más información sobre AIR en Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Visite la hoja de ruta de Microsoft 365 para ver lo que se va a implementar próximamente.](https://www.microsoft.com/microsoft-365/roadmap?filters=)
