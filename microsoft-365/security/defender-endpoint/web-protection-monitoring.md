---
title: Supervisión de la seguridad de la exploración web en Microsoft Defender para punto de conexión
description: Uso de la protección web en Microsoft Defender para punto de conexión para supervisar la seguridad de la exploración web
keywords: protección web, protección contra amenazas web, exploración web, supervisión, informes, tarjetas, lista de dominios, seguridad, phishing, malware, vulnerabilidad de seguridad, sitios web, protección de red, Edge, Internet Explorer, Chrome, Firefox, explorador web
search.appverid: met150
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
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: ec3cadaa674311f19a08d1455293649c84e84962
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68233472"
---
# <a name="monitor-web-browsing-security"></a>Supervisión de la seguridad de la exploración web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

La protección web le permite supervisar la seguridad de la exploración web de su organización a través de informes en **Informes > protección web** en el portal de Microsoft 365 Defender. El informe contiene tarjetas que proporcionan estadísticas de detección de amenazas web.

- **Detecciones de protección contra amenazas web a lo largo del tiempo** : esta tarjeta de tendencia muestra el número de amenazas web detectadas por tipo durante el período de tiempo seleccionado (Últimos 30 días, Últimos 3 meses, Últimos 6 meses)

  :::image type="content" source="images/wtp-blocks-over-time.png" alt-text="La tarjeta que muestra las detecciones de protección contra amenazas web a lo largo del tiempo" lightbox="images/wtp-blocks-over-time.png":::

- **Resumen de protección contra amenazas web** : esta tarjeta muestra el total de detecciones de amenazas web en los últimos 30 días, que muestra la distribución entre los distintos tipos de amenazas web. Al seleccionar un segmento, se abre la lista de los dominios que se encontraron con sitios web malintencionados o no deseados.

  :::image type="content" source="images/wtp-summary.png" alt-text="La tarjeta que muestra el resumen de la protección contra amenazas web"  lightbox="images/wtp-summary.png":::

> [!NOTE]
> Un bloque puede tardar hasta 12 horas en reflejarse en las tarjetas o en la lista de dominios.

## <a name="types-of-web-threats"></a>Tipos de amenazas web

La protección web clasifica los sitios web malintencionados y no deseados como:

- **Phishing** : sitios web que contienen formularios web suplantados y otros mecanismos de suplantación de identidad diseñados para engañar a los usuarios para que divulguen credenciales y otra información confidencial
- **Malintencionado:** sitios web que hospedan malware y aprovechan el código
- **Indicador personalizado** : sitios web cuyas direcciones URL o dominios ha agregado a la [lista de indicadores personalizados](manage-indicators.md) para el bloqueo

## <a name="view-the-domain-list"></a>Ver la lista de dominios

Seleccione una categoría de amenaza web específica en la tarjeta de **resumen de protección contra amenazas web** para abrir la página **Dominios** . En esta página se muestra la lista de dominios de esa categoría de amenaza. La página proporciona la siguiente información para cada dominio:

- **Recuento de acceso** : número de solicitudes de direcciones URL en el dominio
- **Bloques** : número de veces que se bloquearon las solicitudes
- **Tendencia de acceso** : cambio en el número de intentos de acceso
- **Categoría de amenaza** : tipo de amenaza web
- **Dispositivos** : número de dispositivos con intentos de acceso

Seleccione un dominio para ver la lista de dispositivos que han intentado acceder a las direcciones URL de ese dominio y a la lista de direcciones URL.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a protección web](web-protection-overview.md)
- [Filtrado de contenido web](web-content-filtering.md)
- [Protección contra amenazas web](web-threat-protection.md)
- [Responder a amenazas web](web-protection-response.md)
