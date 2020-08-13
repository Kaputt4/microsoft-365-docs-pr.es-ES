---
title: Dirigir las cuentas de usuario en peligro con investigación y respuesta automatizadas
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección, protección, riesgo
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Obtenga información sobre cómo acelerar el proceso de detección y direccionamiento de cuentas de usuario en peligro con capacidades automatizadas de investigación y respuesta en Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 5a1dd64a0b30bb230af0d96432ae9542ce0370d8
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656914"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Dirigir las cuentas de usuario en peligro con investigación y respuesta automatizadas

[Office 365 Advanced Threat Protection Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) incluye capacidades [de investigación y respuesta automáticas](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air) eficaces. Estas capacidades pueden guardar el equipo de operaciones de seguridad en gran cantidad de tiempo y esfuerzo relacionados con las amenazas. Microsoft sigue mejorando las capacidades de seguridad. Recientemente, las capacidades de AIR se mejoraron para incluir una guía de seguridad de usuario en peligro (actualmente en versión preliminar). Lea este artículo para obtener más información acerca de la guía de seguridad de usuario comprometida. Y ve la entrada de blog [acelerar el tiempo de respuesta para detectar y responder a la puesta en peligro del usuario y limitar el ámbito de infracción con Office 365 ATP](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) para obtener más detalles.

![Investigación automatizada para un usuario en peligro](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

La guía de seguridad de usuario comprometida permite que el equipo de seguridad de su organización:

- Acelerar la detección de las cuentas de usuario en peligro;

- Limitar el ámbito de una infracción cuando una cuenta está en peligro; y

- Responder a los usuarios comprometidos de forma más eficaz y eficiente.

## <a name="compromised-user-alerts"></a>Alertas de usuario en peligro

Cuando una cuenta de usuario se ve comprometida, se producen comportamientos atípicos o anómalos. Por ejemplo, los mensajes de suplantación de identidad (phishing) y correo no deseado pueden enviarse internamente desde una cuenta de usuario de confianza. La protección contra amenazas avanzada de Office 365 puede detectar esta anomalías en los patrones de correo electrónico y la actividad de colaboración dentro de Office 365. Cuando esto ocurre, se desencadenan alertas y se inicia el proceso de mitigación de amenazas.

Por ejemplo, a continuación se muestra una alerta que se ha desencadenado debido al envío de correo sospechoso:

![Alerta desencadenada por un envío de correo electrónico sospechoso](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Y este es un ejemplo de una alerta que se ha desencadenado cuando se ha alcanzado el límite de envío de un usuario:

![Alerta desencadenada por el límite de envío alcanzado](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Investigar y responder a un usuario comprometido

Cuando una cuenta de usuario se ve comprometida, se desencadenan alertas. Y, en algunos casos, la cuenta de usuario está bloqueada y se evita que se envíen mensajes de correo electrónico adicionales hasta que el problema se resuelva por el equipo de operaciones de seguridad de la organización. En otros casos, se inicia una investigación automatizada que puede dar como resultado acciones recomendadas que el equipo de seguridad debe llevar a cabo.

- [Ver e investigar usuarios restringidos](#view-and-investigate-restricted-users)

- [Ver detalles sobre las investigaciones automatizadas](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Debe tener los permisos adecuados para realizar las siguientes tareas. Consulte [permisos necesarios para usar la funcionalidad de Air](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities).

### <a name="view-and-investigate-restricted-users"></a>Ver e investigar usuarios restringidos

Tiene algunas opciones para desplazarse a una lista de usuarios restringidos. Por ejemplo, en el centro de seguridad & cumplimiento, puede ir a **Threat management**  >  **Review**  >  **los usuarios restringidos**de revisión de administración de amenazas. El siguiente procedimiento describe la navegación mediante el panel de **alertas** , que es una buena forma de ver los distintos tipos de alertas que se pueden haber desencadenado.

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión.

2. En el panel de navegación, elija Panel de **alertas**  >  **Dashboard**.

3. En el widget **otras alertas** , seleccione **usuarios restringidos**.

   ![Widget de otras alertas](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   Se abrirá la lista de usuarios restringidos.<br/>![Usuarios restringidos en Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. Seleccione una cuenta de usuario en la lista para ver los detalles y realizar acciones, como [la liberación del usuario restringido](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam).

### <a name="view-details-about-automated-investigations"></a>Ver detalles sobre las investigaciones automatizadas

Una vez iniciada una investigación automatizada, puede ver los detalles y los resultados en el centro de seguridad & cumplimiento. Vaya a investigaciones de **Administración de amenazas**  >  **Investigations**y, a continuación, seleccione una investigación para ver sus detalles.

Para obtener más información, consulte [Ver detalles de una investigación](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results).

## <a name="keep-the-following-points-in-mind"></a>Tenga en cuenta los siguientes puntos

- **Mantente al tanto de tus avisos**. Como sabe, cuanto más tiempo no se detecte un riesgo, mayor será el potencial de impacto y de costos generalizados para la organización, los clientes y los asociados. La detección temprana y la respuesta oportuna son críticas para mitigar las amenazas y, especialmente, cuando la cuenta de un usuario está en peligro.

- **Automatización ayuda al equipo de operaciones de seguridad, pero no sustituye a él**. Las capacidades automatizadas de investigación y respuesta pueden detectar los usuarios comprometidos en un primer momento, pero es probable que el equipo de operaciones de seguridad deba participar y realizar alguna investigación y corrección. ¿Necesita ayuda con esto? Consulte [acciones de revisión y aprobación](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions).

- **No confíe en una alerta de inicio de sesión sospechosa como el único indicador**. Cuando una cuenta de usuario está en peligro, puede o no activar una alerta de inicio de sesión sospechosa. A veces, es la serie de actividades que se producen después de que se haya comprometido una cuenta que desencadena una alerta. ¿Desea saber más sobre las alertas? Consulte [directivas de alerta](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).

## <a name="next-steps"></a>Pasos siguientes

- [Revisar los permisos necesarios para usar la funcionalidad de AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)

- [Buscar e investigar correo electrónico malintencionado en Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

- [Obtener información sobre AIR en ATP de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Visite el plan de desarrollo de Microsoft 365 para ver lo que estará próximamente y que se implementará](https://www.microsoft.com/microsoft-365/roadmap?filters=)

