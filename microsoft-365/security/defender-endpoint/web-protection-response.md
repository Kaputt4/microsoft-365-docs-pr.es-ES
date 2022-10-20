---
title: Respuesta a amenazas web en Microsoft Defender para punto de conexión
description: Responder a alertas relacionadas con sitios web malintencionados y no deseados. Descripción de cómo la protección contra amenazas web informa a los usuarios finales a través de sus exploradores web y notificaciones de Windows
keywords: protección web, protección contra amenazas web, exploración web, alertas, respuesta, seguridad, phishing, malware, vulnerabilidad de seguridad, sitios web, protección de red, Edge, Internet Explorer, Chrome, Firefox, explorador web, notificaciones, usuarios finales, notificaciones de Windows, página de bloqueo,
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: d46400787d98cf3bf7620ae9003b9fd47e581381
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68644161"
---
# <a name="respond-to-web-threats"></a>Responder a amenazas web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

La protección web en Microsoft Defender para punto de conexión le permite investigar y responder de forma eficaz a alertas relacionadas con sitios web malintencionados y sitios web en su lista de indicadores personalizados.

## <a name="view-web-threat-alerts"></a>Visualización de alertas de amenazas web

Microsoft Defender para punto de conexión genera las siguientes [alertas](manage-alerts.md) para actividades web malintencionadas o sospechosas:

- **Conexión sospechosa bloqueada por la protección de red**: esta alerta se genera cuando la protección de red detiene un intento de acceder a un sitio web malintencionado o  a un sitio web en la lista de indicadores personalizados en modo *de bloque*.
- **Conexión sospechosa detectada por la protección de red**: esta alerta se genera cuando la protección de red detecta un intento de acceder a un sitio web malintencionado o a un sitio web en la lista de indicadores personalizados en modo *de solo auditoría* .

Cada alerta proporciona la siguiente información:

- Dispositivo que intentó acceder al sitio web bloqueado
- Aplicación o programa que se usa para enviar la solicitud web
- Dirección URL o dirección URL malintencionadas en la lista de indicadores personalizados
- Acciones recomendadas para respondedores

:::image type="content" source="images/wtp-alert.png" alt-text="La alerta relacionada con la protección contra amenazas web" lightbox="images/wtp-alert.png":::

> [!NOTE]
> Para reducir el volumen de alertas, Microsoft Defender para punto de conexión consolida las detecciones de amenazas web para el mismo dominio en el mismo dispositivo cada día en una sola alerta. Solo se genera una alerta y se cuenta en el [informe de protección web](web-protection-monitoring.md).

## <a name="inspect-website-details"></a>Inspeccionar los detalles del sitio web

Puede profundizar más si selecciona la dirección URL o el dominio del sitio web en la alerta. Se abre una página sobre esa dirección URL o dominio concretos con información diversa, entre las que se incluyen:

- Dispositivos que intentaron acceder al sitio web
- Incidentes y alertas relacionados con el sitio web
- Frecuencia con la que se ha visto el sitio web en los eventos de su organización

  :::image type="content" source="images/wtp-website-details.png" alt-text="Página de detalles de la entidad de dominio o dirección URL" lightbox="images/wtp-website-details.png":::

[Más información sobre la dirección URL o las páginas de entidad de dominio](investigate-domain.md)

## <a name="inspect-the-device"></a>Inspeccionar el dispositivo

También puede comprobar el dispositivo que intentó acceder a una dirección URL bloqueada. Al seleccionar el nombre del dispositivo en la página de alerta, se abre una página con información completa sobre el dispositivo.

[Más información sobre las páginas de entidad de dispositivo](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a>Notificaciones del explorador web y Windows para los usuarios finales

Con la protección web en Microsoft Defender para punto de conexión, se impedirá que los usuarios finales visiten sitios web malintencionados o no deseados mediante Microsoft Edge u otros exploradores. Dado que la protección de [red](network-protection.md) realiza el bloqueo, verá un error genérico desde el explorador web. También verán una notificación de Windows.

:::image type="content" source="images/wtp-browser-blocking-page.png" alt-text="Microsoft Edge muestra un error 403 y la notificación de Windows" lightbox="images/wtp-browser-blocking-page.png":::

*Amenaza web bloqueada en Microsoft Edge*

:::image type="content" source="images/wtp-chrome-browser-blocking-page.png" alt-text="El explorador web Chrome que muestra una advertencia de conexión segura y la notificación de Windows" lightbox="images/wtp-chrome-browser-blocking-page.png":::
*Amenaza web bloqueada en Chrome*

## <a name="related-topics"></a>Temas relacionados

- [Introducción a protección web](web-protection-overview.md)
- [Filtrado de contenido web](web-content-filtering.md)
- [Protección contra amenazas web](web-threat-protection.md)
- [Supervisar la seguridad web](web-protection-monitoring.md)
