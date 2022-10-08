---
title: Elija entre modos guiados y avanzados para la búsqueda en Microsoft 365 Defender
description: La búsqueda guiada en Microsoft 365 Defender no requiere conocimientos de KQL, mientras que la búsqueda avanzada permite escribir una consulta desde cero.
keywords: modo guiado, búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365initiative-m365-defender
- tier2
ms.topic: conceptual
ms.custom: seo-marvel-apr2020
search.appverid: met150
ms.openlocfilehash: 1c47ebc606c4dc2e4fd0b7e5d41a5e7a5ea035d1
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68078217"
---
# <a name="choose-between-guided-and-advanced-modes-to-hunt-in-microsoft-365-defender"></a>Elija entre modos guiados y avanzados para cazar en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Para encontrar la página de **búsqueda avanzada**, vaya a la barra de navegación izquierda en Microsoft 365 Defender y seleccione **Búsqueda** > **avanzada**. Si la barra de navegación está contraída, seleccione el icono](../../media/guided-hunting/hunting-icon.png) de búsqueda de icono ![de búsqueda. 

En la página **de búsqueda avanzada** , se admiten dos modos:
- **Modo guiado** : para realizar consultas mediante el generador de consultas
- **Modo avanzado**: para realizar consultas mediante el editor de consultas mediante Lenguaje de consulta Kusto (KQL)

La principal diferencia entre los dos modos es que el modo guiado *no* requiere que el cazador conozca KQL para consultar la base de datos, mientras que el modo avanzado requiere conocimientos de KQL. 

El modo guiado incluye un generador de consultas que tiene un estilo de bloque de creación visual y fácil de usar de construir consultas a través de menús desplegables que contienen filtros y condiciones disponibles. Para usar el modo guiado, consulte [Introducción al modo de búsqueda guiada](advanced-hunting-modes.md#get-started-with-guided-hunting-mode).

El modo avanzado incluye un área del editor de consultas donde los usuarios pueden crear consultas desde cero. Para usar el modo avanzado, consulte [Introducción al modo de búsqueda avanzada](advanced-hunting-modes.md#get-started-with-advanced-hunting-mode).

## <a name="get-started-with-guided-hunting-mode"></a>Introducción al modo de búsqueda guiada

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Al abrir la página de búsqueda avanzada por primera vez después de que la búsqueda guiada esté disponible, se le invita a realizar el recorrido para obtener más información sobre las distintas partes de la página, como las pestañas y las áreas de consulta. 

Para realizar el recorrido, seleccione **Tomar tour** cuando aparezca este banner:


[![banner invitando al usuario a realizar el recorrido](../../media/guided-hunting/1-guided-hunting-banner-tb.png) ](../../media/guided-hunting/1-guided-hunting-banner.png#lightbox)

Siga las burbujas de enseñanza azules que aparecen a lo largo de la página y seleccione **Siguiente** para pasar de un paso al siguiente.

Para volver a realizar el recorrido en cualquier momento, vaya a **Recursos** >  de ayuda **Más información** y seleccione **Tomar el recorrido**.

![Captura de pantalla de los recursos de ayuda](../../media/guided-hunting/help-resources.png)


A continuación, puede empezar a compilar la consulta para buscar amenazas. Los siguientes artículos pueden ayudarle a sacar el máximo partido a la búsqueda en modo guiado:


| Objetivo de aprendizaje | Descripción | Recurso |
|--|--|--|
| **Creación de la primera consulta** | Obtenga información sobre los conceptos básicos del generador de consultas, como especificar el dominio de datos y agregar condiciones y filtros para ayudarle a crear una consulta significativa. Para más información, ejecute consultas de ejemplo. | [Compilación de consultas de búsqueda mediante el modo guiado](advanced-hunting-query-builder.md) |
| **Obtenga información sobre las distintas funcionalidades del generador de consultas** |  Conozca los diferentes tipos de datos admitidos y las funcionalidades de modo guiado para ayudarle a ajustar la consulta según sus necesidades. | [Refinar la consulta en modo guiado](advanced-hunting-query-builder-details.md) |
| **Obtenga información sobre lo que puede hacer con los resultados de la consulta.** | Familiarícese con la vista Resultados y lo que puede hacer con los resultados generados, como cómo realizar acciones en ellos o vincularlos a un incidente. | - [Trabajar con resultados de consulta en modo guiado](advanced-hunting-query-builder-results.md)<br /> - [Realizar acciones en los resultados de la consulta](advanced-hunting-take-action.md) <br /> - [Vinculación de los resultados de la consulta a un incidente](advanced-hunting-link-to-incident.md) |
| **Crear reglas de detección personalizadas** | Comprenda cómo puede usar consultas de búsqueda avanzadas para desencadenar alertas y realizar acciones de respuesta automáticamente. | - [Introducción a las detecciones personalizadas](custom-detections-overview.md) <br />- [Reglas de detección personalizadas](custom-detection-rules.md) |

## <a name="get-started-with-advanced-hunting-mode"></a>Introducción al modo de búsqueda avanzada
Se recomienda seguir estos pasos para empezar a trabajar rápidamente con la búsqueda avanzada: 

| Objetivo de aprendizaje | Descripción | Recurso |
|--|--|--|
| **Aprender el idioma** | La búsqueda avanzada se basa en el [lenguaje de consulta Kusto](/azure/kusto/query/), que admite la misma sintaxis y operadores. Empiece a aprender el lenguaje de consulta mediante la ejecución de la primera consulta. | [Introducción al lenguaje de consulta](advanced-hunting-query-language.md) |
| **Aprenda a usar los resultados de la consulta.** | Obtenga información sobre los gráficos y las distintas formas en que puede ver o exportar los resultados. Explore cómo puede ajustar rápidamente las consultas, explorar en profundidad para obtener información más completa y realizar acciones de respuesta. | - [Trabajar con resultados de consulta en modo avanzado](advanced-hunting-query-results.md)<br /> - [Realizar acciones en los resultados de la consulta](advanced-hunting-take-action.md) <br /> - [Vinculación de los resultados de la consulta a un incidente](advanced-hunting-link-to-incident.md)  |
| **Entender el esquema** | Obtenga una visión adecuada y de alto nivel de las tablas en el esquema y sus columnas. Obtenga información sobre dónde buscar datos al construir las consultas. | - [Referencia de esquema](advanced-hunting-schema-tables.md) <br />- [Transición de Microsoft Defender para punto de conexión](advanced-hunting-migrate-from-mde.md) |
| **Obtener sugerencias y ejemplos expertos** | Entrene de forma gratuita con guías de expertos de Microsoft. Explore colecciones de consultas predefinidas que cubren diferentes escenarios de búsqueda de amenazas. | - [Obtener formación de expertos](advanced-hunting-expert-training.md) <br />- [Uso de consultas compartidas](advanced-hunting-shared-queries.md) <br />- [Ir a buscar](advanced-hunting-go-hunt.md) <br />- [Búsqueda de amenazas entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md) |
| **Optimización de consultas y control de errores** | Comprenda cómo crear consultas eficaces y sin errores. | - [Procedimientos recomendados de consulta](advanced-hunting-best-practices.md)<br />- [Controlar errores](advanced-hunting-errors.md) |
| **Crear reglas de detección personalizadas** | Comprenda cómo puede usar consultas de búsqueda avanzadas para desencadenar alertas y realizar acciones de respuesta automáticamente. | - [Introducción a las detecciones personalizadas](custom-detections-overview.md) <br />- [Reglas de detección personalizadas](custom-detection-rules.md)|

## <a name="see-also"></a>Vea también
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Compilación de consultas de búsqueda mediante el modo guiado](advanced-hunting-query-builder.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)