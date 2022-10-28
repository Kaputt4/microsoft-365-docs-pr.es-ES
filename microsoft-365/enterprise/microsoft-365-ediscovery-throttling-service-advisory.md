---
title: Avisos de servicio para la limitación de eDiscovery en la supervisión de Exchange Online
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: ''
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- admindeeplinkMAC
- admindeeplinkEXCHANGE
f1.keywords:
- NOCSH
description: Obtenga información sobre los avisos de servicio para la limitación de exhibición de documentos electrónicos en la supervisión de Exchange Online.
ms.openlocfilehash: 6199ff2ddf9a906774d8008c0cb67130cd8e7bc0
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68769059"
---
# <a name="service-advisories-for-ediscovery-throttling-in-exchange-online-monitoring"></a>Avisos de servicio para la limitación de eDiscovery en la supervisión de Exchange Online

Hemos publicado un nuevo aviso de servicio de Exchange Online que le informa de que se está limitando la exhibición de documentos electrónicos. Estos avisos de servicio proporcionan visibilidad sobre las instancias cuando el usuario no puede enviar búsqueda y exportación debido a la limitación.

Estos avisos de servicio se muestran en el Centro de administración de Microsoft 365. Para ver estos avisos de servicio, vaya a **Mantenimiento**  |  **[Estado del servicio](https://go.microsoft.com/fwlink/p/?linkid=842900)** |  **Exchange Online**. Este es un ejemplo de aviso del servicio eDiscovery.

![Captura de pantalla de estado del servicio eDiscovery](../media/ediscovery-service-health.jpg)

## <a name="what-does-this-service-advisory-indicate"></a>¿Qué indica este aviso de servicio?

Los avisos de servicio para la limitación de exhibición de documentos electrónicos informan a los administradores sobre la limitación de su inquilino debido al número de trabajos de búsqueda y exportación que superan el límite establecido por Microsoft. Se aplican varios límites a las herramientas de búsqueda de exhibición de documentos electrónicos en el portal de cumplimiento de [Microsoft Purview](~/compliance/index.yml) . Esto incluye búsquedas que se ejecutan en la página [Búsqueda de contenido](~/compliance/search-for-content.md) y búsquedas asociadas a un caso de exhibición de documentos electrónicos en la página [eDiscovery (estándar).](~/compliance/get-started-core-ediscovery.md) Estos límites ayudan a mantener la salud y la calidad de los servicios proporcionados a las organizaciones. Estos avisos proporcionan conocimientos para que pueda tener en cuenta estos límites al planear, ejecutar y solucionar problemas de búsquedas y exportaciones de eDiscovery.

Para conocer los límites relacionados con la herramienta de Microsoft Purview eDiscovery (estándar), consulte [Límites de búsqueda de contenido y exhibición de documentos electrónicos (estándar) en el centro de cumplimiento](~/compliance/limits-for-content-search.md?viewFallbackFrom=o365-worldwide%20for%20service%20limits).

### <a name="how-often-will-i-see-these-service-advisories"></a>¿Con qué frecuencia veré estos avisos de servicio?

Puede esperar ver este tipo de aviso hasta el momento en que los trabajos de búsqueda y exportación están dentro del límite definido.

## <a name="more-information"></a>Más información

- Para obtener información sobre la solución de problemas y la resolución de problemas de cumplimiento de eDiscovery, consulte [Solución de problemas de Microsoft Purview](/troubleshoot/microsoft-365-compliance-welcome).
- Para obtener información sobre Microsoft Purview, consulte [¿Qué es Microsoft Purview?](/purview/purview)
- Para obtener más información sobre las soluciones de Microsoft Purview eDiscovery, consulte [soluciones de Microsoft Purview eDiscovery](~/compliance/ediscovery.md)
