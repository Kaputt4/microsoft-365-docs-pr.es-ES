---
title: Solucionar cuentas de usuario comprometidas con investigación y respuesta automatizadas
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, protection, compromised
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 06/10/2021
description: Obtenga información sobre cómo acelerar el proceso de detección y tratamiento de cuentas de usuario comprometidas con capacidades automatizadas de investigación y respuesta en Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cd84617230e774b92902ef3d11a365c1965ac814
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904145"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Solucionar cuentas de usuario comprometidas con investigación y respuesta automatizadas

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


[Microsoft Defender para Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) incluye potentes capacidades de investigación y respuesta [automatizadas](office-365-air.md) (AIR). Estas capacidades pueden ahorrarle mucho tiempo y esfuerzo al equipo de operaciones de seguridad que se ocupa de las amenazas. Microsoft sigue mejorando las capacidades de seguridad. Recientemente, las capacidades de AIR se han mejorado para incluir un libro de juegos de seguridad de usuario en peligro (actualmente en versión preliminar). Lea este artículo para obtener más información sobre el libro de juegos de seguridad del usuario en peligro. Y consulta la entrada de blog Acelerar el tiempo para detectar y responder a los compromisos del usuario y limitar el ámbito de infracción con [Microsoft Defender](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) para obtener Office 365 detalles adicionales.

![Investigación automatizada para un usuario en peligro](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

El libro de juegos de seguridad de usuario comprometido permite al equipo de seguridad de la organización:

- Acelerar la detección de cuentas de usuario comprometidas;

- Limitar el ámbito de una infracción cuando una cuenta está en peligro; y

- Responda a los usuarios en peligro de forma más eficaz y eficaz.

## <a name="compromised-user-alerts"></a>Alertas de usuario comprometidas

Cuando una cuenta de usuario está en peligro, se producen comportamientos atípicos o anómalos. Por ejemplo, los mensajes de suplantación de identidad y correo no deseado pueden enviarse internamente desde una cuenta de usuario de confianza. Defender for Office 365 puede detectar estas anomalías en los patrones de correo electrónico y la actividad de colaboración dentro de Office 365. Cuando esto sucede, se desencadenan alertas y comienza el proceso de mitigación de amenazas.

Por ejemplo, esta es una alerta que se desencadenó debido al envío de correo electrónico sospechoso:

![Alerta activada debido al envío de correo electrónico sospechoso](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Y este es un ejemplo de una alerta que se desencadenó cuando se alcanzó un límite de envío para un usuario:

![Alerta desencadenada por el límite de envío alcanzado](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Investigar y responder a un usuario en peligro

Cuando una cuenta de usuario está en peligro, se desencadenan alertas. Y en algunos casos, esa cuenta de usuario se bloquea e impide enviar más mensajes de correo electrónico hasta que el equipo de operaciones de seguridad de la organización resuelva el problema. En otros casos, comienza una investigación automatizada que puede dar como resultado acciones recomendadas que el equipo de seguridad debe llevar a cabo.

- [Ver e investigar usuarios restringidos](#view-and-investigate-restricted-users)

- [Ver detalles sobre las investigaciones automatizadas](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Debe tener los permisos adecuados para realizar las siguientes tareas. Consulte [Permisos necesarios para usar las funcionalidades de AIR.](office-365-air.md#required-permissions-to-use-air-capabilities)

### <a name="view-and-investigate-restricted-users"></a>Ver e investigar usuarios restringidos

Tiene algunas opciones para navegar a una lista de usuarios restringidos. Por ejemplo, en el Centro de seguridad & cumplimiento, puede ir a **Administración** de amenazas \> **Revisar** \> **usuarios restringidos**. En el siguiente procedimiento se describe la navegación mediante el panel **de** alertas, que es una buena manera de ver varios tipos de alertas que podrían haber sido desencadenadas.

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión.

2. En el panel de navegación, elija **Panel de** \> **alertas**.

3. En el **widget Otras alertas,** elija **Usuarios restringidos**.

   ![Widget Otras alertas](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   Esto abre la lista de usuarios restringidos.

   ![Usuarios restringidos en Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. Seleccione una cuenta de usuario en la lista para ver detalles y tomar medidas, como liberar [el usuario restringido](removing-user-from-restricted-users-portal-after-spam.md).

### <a name="view-details-about-automated-investigations"></a>Ver detalles sobre las investigaciones automatizadas

Cuando se inicia una investigación automatizada, puede ver sus detalles y resultados en el Centro de seguridad & cumplimiento. Vaya  a \> **Investigaciones de administración de** amenazas y, a continuación, seleccione una investigación para ver sus detalles.

Para obtener más información, [vea Ver detalles de una investigación](air-view-investigation-results.md).

## <a name="keep-the-following-points-in-mind"></a>Tenga en cuenta los siguientes puntos

- **Mantenerse al tanto de las alertas**. Como sabe, cuanto más tiempo no se detecte un compromiso, mayor será el potencial de impacto y costo generalizado para su organización, clientes y socios. La detección temprana y la respuesta oportuna son fundamentales para mitigar las amenazas, especialmente cuando la cuenta de un usuario está en peligro.

- **La automatización ayuda, pero no reemplaza, al equipo de operaciones de seguridad**. Las capacidades automatizadas de investigación y respuesta pueden detectar un usuario en peligro desde el principio, pero es probable que el equipo de operaciones de seguridad necesite participar y realizar alguna investigación y corrección. ¿Necesita ayuda con esto? Vea [Revisar y aprobar acciones](air-review-approve-pending-completed-actions.md).

- **No confíe en una alerta de inicio de sesión sospechosa como su único indicador**. Cuando una cuenta de usuario está en peligro, es posible que desencadene o no una alerta de inicio de sesión sospechosa. A veces es la serie de actividades que se producen después de que se pone en peligro una cuenta que desencadena una alerta. ¿Desea obtener más información sobre las alertas? Vea [Directivas de alerta](../../compliance/alert-policies.md).

## <a name="next-steps"></a>Siguientes pasos

- [Revisar los permisos necesarios para usar las funcionalidades de AIR](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Buscar e investigar correo electrónico malintencionado en Office 365](investigate-malicious-email-that-was-delivered.md)

- [Obtenga información sobre AIR en Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Visite el Microsoft 365 guía de desarrollo para ver lo que se está implementando próximamente](https://www.microsoft.com/microsoft-365/roadmap?filters=)