---
title: Supervisión de la seguridad de exploración web en ATP de Microsoft Defender
description: Usar la protección web en ATP de Microsoft Defender para supervisar la seguridad de exploración web
keywords: protección web, protección contra amenazas web, exploración web, supervisión, informes, tarjetas, lista de dominios, seguridad, phishing, malware, exploit, sitios web, protección de red, Edge, Internet Explorer, Chrome, Firefox, explorador web
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5d5cb89bccb0d7ea0fa4891c3b5b0d11a7244cf8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071744"
---
# <a name="monitor-web-browsing-security"></a>Supervisar la seguridad de exploración web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

La protección web le permite supervisar la seguridad de navegación web de su organización a través de informes **en Informes > protección web** en el Centro de seguridad de Microsoft Defender. El informe contiene tarjetas que proporcionan estadísticas de detección de amenazas web.

- **Detecciones** de protección contra amenazas web con el tiempo: esta tarjeta de tendencia muestra el número de amenazas web detectadas por tipo durante el período de tiempo seleccionado (Últimos 30 días, Últimos 3 meses, Últimos 6 meses)
 
    ![Imagen de la tarjeta que muestra detecciones de protección contra amenazas web con el tiempo](images/wtp-blocks-over-time.png)

- **Resumen de protección contra** amenazas web: esta tarjeta muestra el total de detecciones de amenazas web en los últimos 30 días, mostrando la distribución entre los diferentes tipos de amenazas web. Al seleccionar un segmento, se abre la lista de dominios que se encontraron con sitios web malintencionados o no deseados.

    ![Imagen de la tarjeta que muestra el resumen de protección contra amenazas web](images/wtp-summary.png)

>[!Note]
>Puede tardar hasta 12 horas antes de que un bloque se refleje en las tarjetas o en la lista de dominios.

## <a name="types-of-web-threats"></a>Tipos de amenazas web

La protección web categoriza los sitios web malintencionados y no deseados como:

- **Phishing:** sitios web que contienen formularios web suplantados y otros mecanismos de suplantación de identidad diseñados para engañar a los usuarios para que divulgen credenciales y otra información confidencial
- **Malintencionado: sitios** web que hospedan malware y código de vulnerabilidad
- **Indicador personalizado:** sitios web cuyas direcciones URL o dominios ha agregado a la lista de [indicadores personalizados](manage-indicators.md) para bloquear

## <a name="view-the-domain-list"></a>Ver la lista de dominios

Seleccione una categoría de amenaza web específica en la **tarjeta de** resumen de protección contra amenazas web para abrir la **página Dominios.** Esta página muestra la lista de dominios bajo esa categoría de amenaza. La página proporciona la siguiente información para cada dominio:

- **Recuento de acceso:** número de solicitudes de direcciones URL en el dominio
- **Bloques:** número de veces que se bloquearon las solicitudes
- **Tendencia de acceso:** cambio en el número de intentos de acceso
- **Categoría de amenaza:** tipo de amenaza web
- **Dispositivos:** número de dispositivos con intentos de acceso

Seleccione un dominio para ver la lista de dispositivos que han intentado obtener acceso a las direcciones URL de ese dominio y la lista de direcciones URL.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a la protección web](web-protection-overview.md)
- [Filtrado de contenido web](web-content-filtering.md)
- [Protección contra amenazas web](web-threat-protection.md)
- [Responder a amenazas web](web-protection-response.md)
