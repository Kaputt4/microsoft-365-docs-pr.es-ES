---
title: Cómo funciona la investigación y respuesta automatizadas en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: respuesta automatizada a incidentes, investigación, corrección, protección contra amenazas
ms.date: 01/29/2021
description: Vea cómo funcionan las capacidades automatizadas de investigación y respuesta en Microsoft Defender para Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e377927156e8c98d07f4527bca09e3764bed3f74
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073499"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Cómo funciona la investigación y respuesta automatizadas en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

A medida que se desencadenan las alertas de seguridad, el equipo de operaciones de seguridad debe buscar esas alertas y tomar medidas para proteger su organización. A veces, los equipos de operaciones de seguridad pueden sentirse abrumados por el volumen de alertas que se desencadenan. Las capacidades automatizadas de investigación y respuesta (AIR) en Microsoft Defender para Office 365 pueden ser de ayuda.

AIR permite que el equipo de operaciones de seguridad funcione de forma más eficaz y eficaz. Las capacidades de AIR incluyen procesos de investigación automatizados en respuesta a amenazas conocidas que existen actualmente. Las acciones de corrección apropiadas esperan su aprobación, lo que permite al equipo de operaciones de seguridad responder a las amenazas detectadas.

En este artículo se describe cómo funciona AIR a través de varios ejemplos. Cuando estés listo para empezar a usar AIR, consulta [Investigar y responder automáticamente a las amenazas.](office-365-air.md)

- [Ejemplo 1: Un mensaje de suplantación de identidad notificado por el usuario inicia un libro de reproducción de investigación](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [Ejemplo 2: Un administrador de seguridad desencadena una investigación desde el Explorador de amenazas](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [Ejemplo 3: un equipo de operaciones de seguridad integra AIR con su SIEM mediante la API de actividad de administración de Office 365](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Ejemplo: un mensaje de suplantación de identidad notificado por el usuario inicia un libro de reproducción de investigación

Supongamos que un usuario de su organización recibe un correo electrónico que cree que es un intento de suplantación de identidad. El usuario, formado para informar de estos mensajes, usa el complemento Report [Message](enable-the-report-message-add-in.md) o el complemento [Report Phishing](enable-the-report-phish-add-in.md) para enviarlo a Microsoft para su análisis. El envío también se envía al sistema y está visible en el Explorador en la vista **Envíos** (anteriormente denominada vista **de notificación de** usuario). Además, el mensaje notificado por el usuario ahora desencadena una alerta de información basada en el sistema, que inicia automáticamente el libro de juegos de investigación.

Durante la fase de investigación raíz, se evalúan varios aspectos del correo electrónico. Estos aspectos incluyen:

- Determinación sobre el tipo de amenaza que podría ser;
- Quién lo envió;
- Desde dónde se envió el correo electrónico (infraestructura de envío);
- Si otras instancias del correo electrónico se entregaron o bloquearon;
- Una evaluación de nuestros analistas;
- Si el correo electrónico está asociado a campañas conocidas;
- y más.

Una vez completada la investigación raíz, el libro de reproducción proporciona una lista de acciones recomendadas para realizar en el correo electrónico original y las entidades asociadas a ella.

A continuación, se ejecutan varios pasos de investigación y búsqueda de amenazas:

- Los mensajes de correo electrónico similares se identifican mediante búsquedas en clústeres de correo electrónico.
- La señal se comparte con otras plataformas, como [Microsoft Defender para endpoint.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- Se determina si los usuarios han hecho clic a través de vínculos malintencionados en mensajes de correo electrónico sospechosos.
- Se realiza una comprobación en Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) y ([Microsoft Defender para Office 365](defender-for-office-365.md)) para ver si hay otros mensajes similares notificados por los usuarios.
- Se realiza una comprobación para ver si un usuario se ha visto comprometido. Esta comprobación aprovecha las señales de Office 365, [Microsoft Cloud App Security](/cloud-app-security)y Azure Active [Directory,](/azure/active-directory)correlacionando las anomalías relacionadas con la actividad del usuario.

Durante la fase de búsqueda, los riesgos y las amenazas se asignan a varios pasos de búsqueda.

La corrección es la fase final del libro de juegos. Durante esta fase, se toman medidas de corrección, en función de las fases de investigación y de búsqueda.

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Ejemplo: un administrador de seguridad desencadena una investigación desde el Explorador de amenazas

Además de las investigaciones automatizadas desencadenadas por una alerta, el equipo de operaciones de seguridad de la organización puede desencadenar una investigación automatizada desde una vista en el Explorador [de amenazas.](threat-explorer.md)  Esta investigación también crea una alerta, para que los incidentes de Microsoft Defender y las herramientas SIEM externas puedan ver que esta investigación se desencadenó.

Por ejemplo, supongamos que está usando la **vista Malware** en el Explorador. Con las pestañas debajo del gráfico, seleccione la **pestaña Correo** electrónico. Si selecciona uno o más elementos de la lista, se activa el **botón +** Acciones.

![Explorador con mensajes seleccionados](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Con el **menú** Acciones, puede seleccionar **Activar investigación**.

![Menú Acciones para los mensajes seleccionados](../../media/explorer-malwareview-selectedemails-actions.jpg)

Al igual que los libros de reproducción desencadenados por una alerta, las investigaciones automáticas que se desencadenan desde una vista en el Explorador incluyen una investigación raíz, pasos para identificar y correlacionar amenazas y acciones recomendadas para mitigar esas amenazas.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Ejemplo: un equipo de operaciones de seguridad integra AIR con su SIEM mediante la API de actividad de administración de Office 365

Las funcionalidades de AIR en Microsoft Defender para Office 365 incluyen informes [&](air-view-investigation-results.md) detalles que los equipos de operaciones de seguridad pueden usar para supervisar y solucionar las amenazas. Pero también puede integrar las capacidades de AIR con otras soluciones. Algunos ejemplos incluyen un sistema de administración de eventos y de información de seguridad (SIEM), un sistema de administración de casos o una solución de informes personalizada. Estos tipos de integraciones se pueden realizar mediante la API de actividad de administración de [Office 365.](/office/office-365-management-api/office-365-management-activity-api-reference)

Por ejemplo, recientemente, una organización estableció una forma de que su equipo de operaciones de seguridad vea alertas de suplantación de identidad notificadas por el usuario que air ya ha procesado. Su solución integra alertas relevantes con el servidor SIEM de la organización y su sistema de administración de casos. La solución reduce en gran medida el número de falsos positivos para que su equipo de operaciones de seguridad pueda centrar su tiempo y esfuerzo en amenazas reales. Para obtener más información sobre esta solución personalizada, vea el blog de tech community: Mejorar la eficacia de su SOC con [Microsoft Defender para Office 365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)y la API de administración de O365 .

## <a name="next-steps"></a>Pasos siguientes

- [Introducción al uso de AIR](office-365-air.md)
- [Ver acciones de corrección pendientes o completadas](air-review-approve-pending-completed-actions.md)