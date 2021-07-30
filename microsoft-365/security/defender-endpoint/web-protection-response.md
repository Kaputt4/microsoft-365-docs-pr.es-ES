---
title: Responder a amenazas web en Microsoft Defender para endpoint
description: Responder a alertas relacionadas con sitios web malintencionados y no deseados. Comprender cómo la protección contra amenazas web informa a los usuarios finales a través de sus exploradores web y Windows notificaciones
keywords: protección web, protección contra amenazas web, exploración web, alertas, respuesta, seguridad, phishing, malware, vulnerabilidad, sitios web, protección de red, Edge, Internet Explorer, Chrome, Firefox, explorador web, notificaciones, usuarios finales, notificaciones de Windows, página de bloqueo,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6439088073b9b6cfd86988a395028d64a8981a99
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "53651668"
---
# <a name="respond-to-web-threats"></a>Responder a amenazas web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

La protección web en Microsoft Defender para endpoint le permite investigar y responder eficazmente a alertas relacionadas con sitios web y sitios web malintencionados en su lista de indicadores personalizados.

## <a name="view-web-threat-alerts"></a>Ver alertas de amenazas web

Microsoft Defender para endpoint genera las siguientes [alertas para](manage-alerts.md) actividades web malintencionadas o sospechosas:

- **Conexión sospechosa bloqueada** por la protección de red: esta alerta se genera cuando un  intento de acceso a un sitio web malintencionado o a un sitio web de la lista de indicadores personalizados se detiene mediante la protección de red en *modo de* bloqueo
- **Conexión sospechosa detectada** por la protección de red: esta alerta se genera cuando se detecta un intento de acceso a un sitio web malintencionado o a un sitio web en la lista de indicadores personalizados mediante protección de red en modo de solo *auditoría*

Cada alerta proporciona la siguiente información:

- Dispositivo que intentó acceder al sitio web bloqueado
- Aplicación o programa usado para enviar la solicitud web
- Dirección URL malintencionada en la lista de indicadores personalizados
- Acciones recomendadas para respondedores

![Imagen de una alerta relacionada con la protección contra amenazas web](images/wtp-alert.png)

> [!NOTE]
> Para reducir el volumen de alertas, Microsoft Defender para endpoint consolida las detecciones de amenazas web para el mismo dominio en el mismo dispositivo cada día en una sola alerta. Solo se genera una alerta y se cuenta en el informe [de protección web](web-protection-monitoring.md).

## <a name="inspect-website-details"></a>Inspeccionar detalles del sitio web

Puedes profundizar seleccionando la dirección URL o el dominio del sitio web en la alerta. Esto abre una página sobre esa dirección URL o dominio en particular con información diversa, como:

- Dispositivos que intentaron acceder al sitio web
- Incidentes y alertas relacionados con el sitio web
- Con qué frecuencia se ha visto el sitio web en eventos de su organización

    ![Imagen de la página de detalles de la entidad de dirección URL o dominio](images/wtp-website-details.png)

[Más información sobre las páginas de entidad de dominio o URL](investigate-domain.md)

## <a name="inspect-the-device"></a>Inspeccionar el dispositivo

También puedes comprobar el dispositivo que intentó obtener acceso a una dirección URL bloqueada. Al seleccionar el nombre del dispositivo en la página de alerta, se abre una página con información completa sobre el dispositivo.

[Más información sobre las páginas de entidad de dispositivo](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a>Explorador web y notificaciones Windows para usuarios finales

Con la protección web en Microsoft Defender para endpoint, los usuarios finales no podrán visitar sitios web malintencionados o no deseados Microsoft Edge otros exploradores. Dado que el bloqueo se realiza [mediante la protección de red,](network-protection.md)verán un error genérico desde el explorador web. También verán una notificación de Windows.

![Imagen de Microsoft Edge muestra un error 403 y la Windows notificación ](images/wtp-browser-blocking-page.png)
 *web bloqueada en Microsoft Edge*

![Imagen del explorador web Chrome que muestra una advertencia de conexión segura y la Windows notificación ](images/wtp-chrome-browser-blocking-page.png)
 *web bloqueada en Chrome*

## <a name="related-topics"></a>Temas relacionados

- [Introducción a protección web](web-protection-overview.md)
- [Filtrado de contenido web](web-content-filtering.md)
- [Protección contra amenazas web](web-threat-protection.md)
- [Supervisar la seguridad web](web-protection-monitoring.md)
