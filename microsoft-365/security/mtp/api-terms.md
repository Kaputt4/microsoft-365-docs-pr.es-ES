---
title: Licencia y términos de uso de las API de Microsoft 365 defender
description: Descripción de la licencia y de los términos de uso de las API en Microsoft 365 defender
keywords: API, API, licencia, términos, API, legal, avisos, código de conducta
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: d9b3c48e4b9e89ef7648086b05c9fdd9f078f51e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719303"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Licencia y términos de uso de las API de Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="official-terms"></a>Términos oficiales

Las API de Microsoft 365 defender se rigen por la [licencia y los términos de uso de las API de Microsoft](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use).

## <a name="legal-notices"></a>Avisos legales

Microsoft y todos los colaboradores le conceden una licencia para la documentación de Microsoft y otros contenidos de [este repositorio](https://github.com/MicrosoftDocs/microsoft-365-docs)en la licencia pública internacional de Creative Commons atribution 4,0. Para obtener más información, vea el archivo de [licencia](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE) .

Microsoft, Windows, Microsoft Azure y otros productos y servicios de Microsoft a los que se hace referencia en la documentación pueden ser marcas comerciales o marcas comerciales registradas de Microsoft en Estados Unidos u otros países.

Las licencias de este proyecto no le conceden derechos para usar nombres, logotipos o marcas comerciales de Microsoft. Las instrucciones de marcas comerciales generales de Microsoft se pueden encontrar en [Microsoft](https://go.microsoft.com/fwlink/?LinkID=254653)Trademark.

La información de privacidad se puede encontrar en [privacidad en Microsoft](https://privacy.microsoft.com).

Microsoft y todos los colaboradores se reservan todos los demás derechos, ya sea bajo sus respectivos derechos de autor, patentes o marcas comerciales, ya sea por implicación, por exclusión o de otro modo.

## <a name="other-restrictions"></a>Otras restricciones

La API de búsqueda avanzada tiene algunas [limitaciones](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) en el número de resultados devueltos y los datos que se pueden consultar.

1. Solo puede consultar datos de los últimos 30 días.
1. Los resultados incluirán un máximo de 100.000 filas.

### <a name="quotas-and-resource-allocation"></a>Cuotas y asignación de recursos

Las API de Microsoft 365 defender tienen umbrales de limitación.

- **API de incidentes**: hasta 50 llamadas por minuto o 1500 por hora.
- **API de búsqueda avanzada**: hasta 15 llamadas por minuto, 10 minutos de tiempo de ejecución por hora y 4 horas de tiempo de ejecución por día.

El código de estado de respuesta HTTP que indica que la limitación es `429` .

Si la solicitud se ha limitado, el cuerpo de la respuesta indicará la hora en la que puede empezar a hacer solicitudes de nuevo.

## <a name="related-articles"></a>Artículos relacionados

- [Información general sobre las API de Microsoft 365 defender](api-overview.md)
- [API de Microsoft 365 Defender (versión preliminar) admitidas](api-supported.md)
- [Acceso a las API de Microsoft 365 defender](api-access.md)
