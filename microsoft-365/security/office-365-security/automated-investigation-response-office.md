---
title: Funcionamiento de la investigación y respuesta automatizadas en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- m365-security
- m365initiative-defender-office365
keywords: respuesta a incidentes automatizada, investigación, corrección, protección contra amenazas
ms.date: 01/29/2021
description: Vea cómo funcionan las funcionalidades automatizadas de investigación y respuesta en Microsoft Defender para Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: d2ad16d558ea9843670d51dfc7f64b7652e1c881
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68055334"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Funcionamiento de la investigación y respuesta automatizadas en Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

A medida que se desencadenan alertas de seguridad, depende del equipo de operaciones de seguridad examinar esas alertas y tomar medidas para proteger su organización. A veces, los equipos de operaciones de seguridad pueden sentirse abrumados por el volumen de alertas que se desencadenan. Las funcionalidades de investigación y respuesta automatizadas (AIR) en Microsoft Defender para Office 365 pueden ayudar.

AIR permite al equipo de operaciones de seguridad operar de forma más eficaz y eficaz. Las funcionalidades de AIR incluyen procesos de investigación automatizados en respuesta a amenazas conocidas que existen actualmente. Las acciones de corrección adecuadas esperan la aprobación, lo que permite al equipo de operaciones de seguridad responder a las amenazas detectadas.

En este artículo se describe cómo funciona AIR a través de varios ejemplos. Cuando esté listo para empezar a usar AIR, consulte [Investigación automática y respuesta a amenazas](office-365-air.md).

- [Ejemplo 1: Un mensaje de phish notificado por el usuario inicia un cuaderno de estrategias de investigación](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [Ejemplo 2: Un administrador de seguridad desencadena una investigación desde el Explorador de amenazas](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [Ejemplo 3: Un equipo de operaciones de seguridad integra AIR con su SIEM mediante la API de actividad de administración de Office 365](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Ejemplo: Un mensaje de phish notificado por el usuario inicia un cuaderno de estrategias de investigación

Supongamos que un usuario de su organización recibe un correo electrónico que cree que es un intento de suplantación de identidad (phishing). El usuario, entrenado para notificar dichos mensajes, usa el [complemento Mensaje](enable-the-report-message-add-in.md) de informe o el [complemento De suplantación de identidad](enable-the-report-phish-add-in.md) de informe para enviarlo a Microsoft para su análisis. El envío también se envía al sistema y está visible en el Explorador en la vista **Envíos** (anteriormente denominada vista **Notificada** por el usuario). Además, el mensaje notificado por el usuario ahora desencadena una alerta informativa basada en el sistema, que inicia automáticamente el cuaderno de estrategias de investigación.

Durante la fase de investigación raíz, se evalúan varios aspectos del correo electrónico. Estos aspectos incluyen:

- Determinación sobre el tipo de amenaza que podría ser;
- Quién lo envió;
- Desde dónde se envió el correo electrónico (infraestructura de envío);
- Si se entregaron o bloquearon otras instancias del correo electrónico;
- Una evaluación de nuestros analistas;
- Si el correo electrónico está asociado a campañas conocidas;
- y mucho más.

Una vez completada la investigación raíz, el cuaderno de estrategias proporciona una lista de las acciones recomendadas para realizar el correo electrónico original y las entidades asociadas a él.

A continuación, se ejecutan varios pasos de investigación y búsqueda de amenazas:

- Los mensajes de correo electrónico similares se identifican mediante búsquedas en clústeres de correo electrónico.
- La señal se comparte con otras plataformas, como [Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- Se determina si los usuarios han hecho clic a través de vínculos malintencionados en mensajes de correo electrónico sospechosos.
- Se realiza una comprobación en Exchange Online Protection ([EOP](exchange-online-protection-overview.md) y ([Microsoft Defender para Office 365](defender-for-office-365.md) para ver si hay otros mensajes similares notificados por los usuarios.
- Se realiza una comprobación para ver si un usuario ha estado en peligro. Esta comprobación aprovecha las señales entre Office 365, [Microsoft Defender for Cloud Apps](/cloud-app-security) y [Azure Active Directory](/azure/active-directory), correlacionando las anomalías relacionadas con la actividad del usuario.

Durante la fase de búsqueda, los riesgos y las amenazas se asignan a varios pasos de búsqueda.

La corrección es la fase final del cuaderno de estrategias. Durante esta fase, se realizan los pasos de corrección, en función de las fases de investigación y búsqueda.

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Ejemplo: Un administrador de seguridad desencadena una investigación desde el Explorador de amenazas

Además de las investigaciones automatizadas desencadenadas por una alerta, el equipo de operaciones de seguridad de la organización puede desencadenar una investigación automatizada desde una vista en [el Explorador de amenazas](threat-explorer.md). Esta investigación también crea una alerta, por lo que Microsoft 365 Defender incidentes y herramientas SIEM externas pueden ver que se desencadenó esta investigación.

Por ejemplo, supongamos que usa la vista **Malware** en el Explorador. Con las pestañas debajo del gráfico, seleccione la pestaña **Email**. Si selecciona uno o varios elementos de la lista, se activa el botón **+ Acciones**.

:::image type="content" source="../../media/Explorer-Malware-Email-ActionsInvestigate.png" alt-text="Explorador con mensajes seleccionados" lightbox="../../media/Explorer-Malware-Email-ActionsInvestigate.png":::

Con el menú **Acciones** , puede seleccionar **Desencadenar investigación**.

:::image type="content" source="../../media/explorer-malwareview-selectedemails-actions.jpg" alt-text="Menú Acciones para los mensajes seleccionados" lightbox="../../media/explorer-malwareview-selectedemails-actions.jpg":::

De forma similar a los cuadernos de estrategias desencadenados por una alerta, las investigaciones automáticas que se desencadenan desde una vista en el Explorador incluyen una investigación raíz, pasos para identificar y correlacionar amenazas y acciones recomendadas para mitigar esas amenazas.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Ejemplo: Un equipo de operaciones de seguridad integra AIR con su SIEM mediante la API de actividad de administración de Office 365

Las funcionalidades de AIR en Microsoft Defender para Office 365 incluyen [informes & detalles](air-view-investigation-results.md) que los equipos de operaciones de seguridad pueden usar para supervisar y abordar las amenazas. Pero también puede integrar las funcionalidades de AIR con otras soluciones. Entre los ejemplos se incluyen un sistema de administración de eventos e información de seguridad (SIEM), un sistema de administración de casos o una solución de informes personalizada. Estos tipos de integraciones se pueden realizar mediante la [API de actividad de administración de Office 365](/office/office-365-management-api/office-365-management-activity-api-reference).

Por ejemplo, recientemente, una organización ha configurado una forma para que su equipo de operaciones de seguridad vea las alertas de phish notificadas por el usuario que AIR ya ha procesado. Su solución integra alertas pertinentes con el servidor SIEM de la organización y su sistema de administración de casos. La solución reduce en gran medida el número de falsos positivos para que su equipo de operaciones de seguridad pueda centrar su tiempo y esfuerzo en amenazas reales. Para más información sobre esta solución personalizada, consulte [el blog de Tech Community: Mejora de la eficacia de su SOC con Microsoft Defender para Office 365 y la API de administración de O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

## <a name="next-steps"></a>Pasos siguientes

- [Introducción al uso de AIR](office-365-air.md)
- [Ver acciones de corrección pendientes o completadas](air-review-approve-pending-completed-actions.md)
