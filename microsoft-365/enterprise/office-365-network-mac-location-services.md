---
title: Servicios de ubicación de conectividad de red de Microsoft 365 (versión preliminar)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Servicios de ubicación de conectividad de red de Microsoft 365 (versión preliminar)
ms.openlocfilehash: f2ab872f67eca70ab2791d3ad6fe1396b009cc18
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200786"
---
# <a name="microsoft-365-network-connectivity-location-services-preview"></a>Servicios de ubicación de conectividad de red de Microsoft 365 (versión preliminar)

El Centro de administración de Microsoft 365 muestra ahora Información de red y recomendaciones de rendimiento, que son métricas de rendimiento en directo **recopiladas** de su inquilino de Microsoft 365 y disponibles para que solo las puedan ver los usuarios administrativos de su espacio empresarial. La conectividad de red de la organización se diseña por ubicación de oficina a través de una ubicación de salida de red a Internet. La conectividad de cliente de Microsoft 365 usa esa ruta y, a continuación, a través de Internet a los servidores front-end del servicio de Microsoft. Identificar ubicaciones de oficina es clave para poder mostrar estas conclusiones de red.

## <a name="location-in-network-measurements"></a>Ubicación en las medidas de red

El administrador de una organización puede optar por incluir la ubicación en las medidas de red usadas por esta característica. Esto permite la detección automática de la ciudad donde se encuentra cada oficina. La información de ubicación no es precisa y se oculta a 300 m y se clasifica por ciudad. En el momento en que se captura la  ubicación en un dispositivo Windows, se mostrará un icono ubicación en uso en la bandeja de herramientas y es posible que los administradores quieran notificar a los usuarios esto. Con este procesamiento, la ubicación se trata como la ubicación de la oficina de la organización y no la ubicación de una persona o un dispositivo. La información de red se puede mostrar en estas ciudades de ubicación de oficina detectadas. Si se desea obtener una mayor precisión de las recomendaciones, un administrador puede especificar direcciones de ubicación de oficina específicas y, en su lugar, se agregará la información de red. Las ubicaciones de office no se pueden agregar de forma más cercana a 300 metros.

## <a name="location-in-the-microsoft-365-admin-center"></a>Ubicación en el Centro de administración de Microsoft 365

En el Centro de administración de Microsoft 365, los controles de mapa de Bing se usan para mostrar dónde se encuentran las ubicaciones de las oficinas de la organización y para mostrar la topología perimetral de red de una ubicación de oficina seleccionada. Cuando un administrador agrega detalles de dirección específicos para ubicaciones de oficina, Mapas de Bing también se usa para sugerir direcciones para facilitar la entrada de datos.

## <a name="terms-of-use"></a>Condiciones de uso

Cualquier contenido proporcionado a través de Mapas de Bing, incluidas las geocódigos, solo se puede usar dentro del producto a través del cual se proporciona el contenido. El uso por parte del cliente de la característica servicios de ubicación del Centro de administración de Microsoft 365, con tecnología de Mapas de Bing, se rige por los Términos de uso del usuario final de Mapas de _Bing_ disponibles en y la Declaración de privacidad de <https://go.microsoft.com/?linkid=9710837> _Microsoft_ disponible en <https://go.microsoft.com/fwlink/?LinkID=248686.>

Esta característica, proporcionada a través de Mapas de Bing, también es compatible con **Here Technologies.** La forma en que Mapas de Bing aprovecha los servicios de ubicación proporcionados por Here Technologies se rige por los términos de servicio de _Here Technologies disponibles_ en <https://legal.here.com/en-gb/terms> .

## <a name="related-topics"></a>Temas relacionados

[Conectividad de red en el Centro de administración de Microsoft 365 (versión preliminar)](office-365-network-mac-perf-overview.md)

[Información sobre el rendimiento de la red de Microsoft 365 (versión preliminar)](office-365-network-mac-perf-insights.md)

[Evaluación de red de Microsoft 365 (versión preliminar)](office-365-network-mac-perf-score.md)

[Prueba de conectividad de Microsoft 365 en el Centro de administración de M365 (versión preliminar)](office-365-network-mac-perf-onboarding-tool.md)
