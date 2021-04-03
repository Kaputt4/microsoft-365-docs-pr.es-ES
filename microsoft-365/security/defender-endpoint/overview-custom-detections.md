---
title: Información general sobre las detecciones personalizadas en ATP de Microsoft Defender
ms.reviewer: ''
description: Comprender cómo puede usar la búsqueda avanzada para crear detecciones personalizadas y generar alertas
keywords: detecciones personalizadas, alertas, reglas de detección, búsqueda avanzada, búsqueda, consulta, acciones de respuesta, intervalo, mdatp, atp de microsoft defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 20bd70653f535bb732c252224c1e6efd5cf65035
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500651"
---
# <a name="custom-detections-overview"></a>Introducción a las detecciones personalizadas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Con las detecciones personalizadas, puede supervisar proactivamente y responder a varios eventos y estados del sistema, incluidos la actividad de infracciones sospechosas y los dispositivos mal configurados. Puedes hacerlo con reglas de detección personalizables que desencadenan automáticamente alertas y acciones de respuesta.

Las detecciones personalizadas funcionan [con](advanced-hunting-overview.md)búsqueda avanzada, lo que proporciona un lenguaje de consulta eficaz y flexible que cubre un amplio conjunto de información de eventos e sistema de la red. Puede configurarlos para que se ejecuten a intervalos regulares, generando alertas y llevando a cabo acciones de respuesta siempre que haya coincidencias.

Las detecciones personalizadas proporcionan:
- Alertas para detecciones basadas en reglas creadas a partir de consultas de búsqueda avanzadas
- Acciones de respuesta automáticas que se aplican a archivos y dispositivos

## <a name="related-topics"></a>Temas relacionados
- [Crear y administrar reglas de detección](custom-detection-rules.md)
- [Ver y administrar reglas de detección](custom-detections-manage.md)
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
