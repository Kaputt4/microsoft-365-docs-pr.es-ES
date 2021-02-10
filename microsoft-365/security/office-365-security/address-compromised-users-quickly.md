---
title: Solucionar cuentas de usuario comprometidas con investigación y respuesta automatizadas
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección, en peligro
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
ms.date: 02/25/2020
description: Obtenga información sobre cómo acelerar el proceso de detección y tratamiento de cuentas de usuario comprometidas con capacidades automatizadas de investigación y respuesta en Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2159ab7ad7e13c4cd4c2c428317ee7d99f78158c
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "50176068"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Solucionar cuentas de usuario comprometidas con investigación y respuesta automatizadas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


El Plan 2 de Microsoft Defender para [Office 365](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) incluye potentes capacidades de investigación y [respuesta](office-365-air.md) automatizadas (AIR). Estas funcionalidades pueden ahorrarle mucho tiempo y esfuerzo al equipo de operaciones de seguridad que se enfrenta a las amenazas. Microsoft continúa mejorando las capacidades de seguridad. Recientemente, las capacidades de AIR se han mejorado para incluir un libro de juegos de seguridad de usuario comprometido (actualmente en versión preliminar). Lea este artículo para obtener más información sobre el libro de juegos de seguridad de usuario comprometido. Vea la entrada de blog Acelerar el tiempo para detectar y responder al compromiso del usuario y limitar el ámbito de infracción con [Microsoft Defender para Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) para obtener más información.

![Investigación automatizada de un usuario comprometido](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

El libro de juegos de seguridad de usuario comprometido permite al equipo de seguridad de su organización:

- Acelerar la detección de cuentas de usuario comprometidas;

- Limitar el ámbito de una infracción cuando se pone en peligro una cuenta; y

- Responder a los usuarios comprometidos de forma más eficaz y eficaz.

## <a name="compromised-user-alerts"></a>Alertas de usuario comprometidas

Cuando una cuenta de usuario está en peligro, se producen comportamientos atípicos o anómalos. Por ejemplo, los mensajes de suplantación de identidad (phishing) y correo no deseado pueden enviarse internamente desde una cuenta de usuario de confianza. Defender para Office 365 puede detectar estas anomalías en los patrones de correo electrónico y la actividad de colaboración en Office 365. Cuando esto sucede, se desencadenan alertas y comienza el proceso de mitigación de amenazas.

Por ejemplo, esta es una alerta que se desencadenó debido al envío sospechoso de correo electrónico:

![Alerta desencadenada debido al envío sospechoso de correo electrónico](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Y este es un ejemplo de una alerta que se desencadenó cuando se alcanzó un límite de envío para un usuario:

![Alerta desencadenada por el límite de envío alcanzado](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Investigar y responder a un usuario comprometido

Cuando una cuenta de usuario está en peligro, se desencadenan alertas. Y, en algunos casos, se bloquea esa cuenta de usuario e impide que se envíen más mensajes de correo electrónico hasta que el equipo de operaciones de seguridad de la organización resuelva el problema. En otros casos, se inicia una investigación automatizada que puede dar como resultado acciones recomendadas que el equipo de seguridad debe realizar.

- [Ver e investigar usuarios restringidos](#view-and-investigate-restricted-users)

- [Ver detalles sobre investigaciones automatizadas](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Debe tener los permisos adecuados para realizar las siguientes tareas. Vea [los permisos necesarios para usar las funcionalidades de AIR.](office-365-air.md#required-permissions-to-use-air-capabilities)

### <a name="view-and-investigate-restricted-users"></a>Ver e investigar usuarios restringidos

Tienes algunas opciones para navegar a una lista de usuarios restringidos. Por ejemplo, en el Centro de seguridad & cumplimiento, puede ir a Administración **de** amenazas \> **Revisar** \> **usuarios restringidos.** En el siguiente procedimiento  se describe la navegación mediante el panel alertas, que es una buena manera de ver varios tipos de alertas que se podrían haber desencadenado.

1. Vaya a <https://protection.office.com> e inicie sesión.

2. En el panel de navegación, elija **Panel de** \> **alertas.**

3. En el widget **Otras alertas,** elija **Usuarios restringidos.**

   ![Widget Otras alertas](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   Se abrirá la lista de usuarios restringidos.

   ![Usuarios restringidos en Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. Seleccione una cuenta de usuario en la lista para ver los detalles y tomar medidas, como liberar [el usuario restringido.](removing-user-from-restricted-users-portal-after-spam.md)

### <a name="view-details-about-automated-investigations"></a>Ver detalles sobre investigaciones automatizadas

Cuando haya comenzado una investigación automatizada, puede ver sus detalles y resultados en el Centro de & cumplimiento. Vaya  a \> **Investigaciones de administración de** amenazas y, a continuación, seleccione una investigación para ver sus detalles.

Para obtener más información, [vea Ver detalles de una investigación.](air-view-investigation-results.md)

## <a name="keep-the-following-points-in-mind"></a>Tenga en cuenta lo siguiente

- **Manténgase al tanto de las alertas.** Como ya sabe, cuanto más tiempo no se detecte un compromiso, mayor será el potencial de un impacto y costo generalizados para la organización, los clientes y los partners. La detección temprana y la respuesta oportuna son fundamentales para mitigar las amenazas, especialmente cuando la cuenta de un usuario está en peligro.

- **La automatización ayuda, pero no reemplaza,** al equipo de operaciones de seguridad. Las capacidades automatizadas de investigación y respuesta pueden detectar un usuario comprometido desde el principio, pero es probable que el equipo de operaciones de seguridad deba implicarse y realizar alguna investigación y corrección. ¿Necesita ayuda con esto? Vea [Revisar y aprobar acciones.](air-review-approve-pending-completed-actions.md)

- **No se base en una alerta de inicio de sesión sospechoso como su único indicador.** Cuando una cuenta de usuario está en peligro, es posible que desencadene o no una alerta de inicio de sesión sospechoso. A veces, es la serie de actividades que se producen después de que se pone en peligro una cuenta que desencadena una alerta. ¿Desea obtener más información sobre las alertas? Vea [Directivas de alerta.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)

## <a name="next-steps"></a>Siguientes pasos

- [Revisar los permisos necesarios para usar las funcionalidades de AIR](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Buscar e investigar correo electrónico malintencionado en Office 365](investigate-malicious-email-that-was-delivered.md)

- [Más información sobre AIR en Microsoft Defender para puntos de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Visite el mapa de ruta de Microsoft 365 para ver lo que estará próximamente y su implementación](https://www.microsoft.com/microsoft-365/roadmap?filters=)
