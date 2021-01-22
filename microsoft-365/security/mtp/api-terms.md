---
title: Licencia de las API de Microsoft 365 Defender y términos de uso
description: Descripción de la licencia y los términos de uso de las API en Microsoft 365 Defender
keywords: api, api, licencia, términos, api, legal, avisos, código de conducta
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 82f31c449ae2e102ac7464e0fef75277660844d1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930959"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Licencia de las API de Microsoft 365 Defender y términos de uso

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información está relacionada con el producto de versión preliminar que puede modificarse considerablemente antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="official-terms"></a>Términos oficiales

Las API de Microsoft 365 Defender se rigen por la licencia de las API de [Microsoft y los términos de uso.](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use)

## <a name="legal-notices"></a>Avisos legales

Microsoft y todos los colaboradores le conceden una licencia para la documentación de Microsoft y otro contenido de este [repositorio,](https://github.com/MicrosoftDocs/microsoft-365-docs)en virtud de la licencia pública internacional de Creative Commons Attribution 4.0. Para obtener más información, vea el [archivo LICENSE.](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE)

Microsoft, Windows, Microsoft Azure u otros productos y servicios de Microsoft a los que se hace referencia en la documentación pueden ser marcas comerciales o marcas registradas de Microsoft en Estados Unidos u otros países.

Las licencias de este proyecto no le conceden derechos para usar nombres, logotipos o marcas comerciales de Microsoft. Las directrices generales de marca comercial de Microsoft pueden encontrarse en [Marcas comerciales de Microsoft.](https://go.microsoft.com/fwlink/?LinkID=254653)

La información de privacidad puede encontrarse [en Privacidad en Microsoft.](https://privacy.microsoft.com)

Microsoft y todos los colaboradores se reservan todos los demás derechos, ya sea bajo sus respectivos derechos de autor, patentes o marcas comerciales, ya sea por implicación, impedimento u otro tipo.

## <a name="other-restrictions"></a>Otras restricciones

La API de búsqueda avanzada tiene algunas limitaciones en el número de [resultados](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) devueltos y los datos que se pueden consultar.

1. Solo puede consultar datos de los últimos 30 días.
1. Los resultados incluirán un máximo de 100 000 filas.

### <a name="quotas-and-resource-allocation"></a>Cuotas y asignación de recursos

Las API de Microsoft 365 Defender tienen umbrales de limitación.

- **API de incidentes:** hasta 50 llamadas por minuto o 1500 llamadas por hora.
- **API de búsqueda avanzada:** hasta 15 llamadas por minuto, 10 minutos de tiempo de ejecución por hora y 4 horas de tiempo de ejecución por día.

El código de estado de respuesta HTTP que indica que la limitación es `429` .

Si la solicitud se ha limitada, el cuerpo de la respuesta indicará la hora en la que puede empezar a realizar solicitudes de nuevo.

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las API de Microsoft 365 Defender](api-overview.md)
- [API de Microsoft 365 Defender (versión preliminar) admitidas](api-supported.md)
- [Obtener acceso a las API de Microsoft 365 Defender](api-access.md)
