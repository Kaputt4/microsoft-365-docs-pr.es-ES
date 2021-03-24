---
title: Licencia y términos de uso de las API de Microsoft 365 Defender
description: Descripción de la licencia y los términos de uso de las API en Microsoft 365 Defender
keywords: api, apis, licencia, términos, apis, legal, avisos, código de conducta
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 9b70311726b6c1c5bedf34a18ee1763255c93ba3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070072"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Licencia y términos de uso de las API de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

## <a name="official-terms"></a>Términos oficiales

Las API de Microsoft 365 Defender se rigen por la licencia de las API de [Microsoft y los términos de uso.](/legal/microsoft-apis/terms-of-use)

## <a name="legal-notices"></a>Avisos legales

Microsoft y los colaboradores le conceden una licencia para la documentación de Microsoft y otro contenido de este [repositorio,](https://github.com/MicrosoftDocs/microsoft-365-docs)en virtud de la Creative Commons Attribution 4.0 International Public License. Para obtener más información, vea el [archivo LICENSE.](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE)

Microsoft, Windows, Microsoft Azure u otros productos y servicios de Microsoft a los que se hace referencia en la documentación pueden ser marcas comerciales o marcas comerciales registradas de Microsoft en los Estados Unidos y/u otros países.

Las licencias de este proyecto no le conceden derechos para usar nombres, logotipos o marcas comerciales de Microsoft. Las directrices generales de marcas comerciales de Microsoft se pueden encontrar en [Microsoft Trademarks](https://go.microsoft.com/fwlink/?LinkID=254653).

La información de privacidad se puede encontrar [en Privacidad en Microsoft](https://privacy.microsoft.com).

Microsoft y cualquier colaborador se reservan todos los demás derechos, ya sea bajo sus respectivos derechos de autor, patentes o marcas comerciales, ya sea por implicación, por impedimento o de otro modo.

## <a name="other-restrictions"></a>Otras restricciones

La API de búsqueda avanzada tiene algunas limitaciones en el número de [resultados devueltos](/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) y los datos que se pueden consultar.

1. Solo puede consultar datos de los últimos 30 días.
1. Los resultados incluirán un máximo de 100 000 filas.

### <a name="quotas-and-resource-allocation"></a>Cuotas y asignación de recursos

Las API de Microsoft 365 Defender tienen umbrales de limitación.

- **API de incidentes:** hasta 50 llamadas por minuto o 1500 llamadas por hora.
- **API de búsqueda avanzada:** hasta 15 llamadas por minuto, 10 minutos de tiempo de ejecución por hora y 4 horas de tiempo de ejecución al día.

El código de estado de respuesta HTTP que indica la limitación es `429` .

Si la solicitud ha sido limitada, el cuerpo de la respuesta indicará la hora en que puede empezar a realizar solicitudes de nuevo.

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las API de Microsoft 365 Defender](api-overview.md)
- [API de Microsoft 365 Defender (versión preliminar) admitidas](api-supported.md)
- [Obtener acceso a las API de Microsoft 365 Defender](api-access.md)