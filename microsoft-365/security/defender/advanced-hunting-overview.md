---
title: 'Información general: Búsqueda avanzada'
description: Obtenga más información sobre las consultas de búsqueda avanzada en Microsoft 365 y cómo usarlas para encontrar de forma proactiva amenazas y debilidades en la red
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto
ms.prod: m365-security
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
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 1ee8d8fbd3b1a56f83106ffaf6be937fa984c272
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2022
ms.locfileid: "64731447"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Búsqueda proactiva de amenazas con la búsqueda avanzada de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consultas que le permite explorar hasta 30 días de datos sin procesar. Puede inspeccionar eventos de forma proactiva en su red para localizar entidades e indicadores de amenazas. El acceso flexible a los datos permite la búsqueda sin restricciones de amenazas conocidas y potenciales.
<br><br>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4G6DO]

Puede usar las mismas consultas de búsqueda de amenazas para crear reglas de detección personalizadas. Estas reglas se ejecutan automáticamente para buscar y, a continuación, responder a sospechas de actividad de infracción, máquinas mal configuradas y otros hallazgos.

Esta funcionalidad es similar a la [búsqueda avanzada en Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) y admite consultas que comprueban un conjunto de datos más amplio desde:

- Microsoft Defender para punto de conexión
- Microsoft Defender para Office 365
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Identity

Para usar la búsqueda avanzada, [active Microsoft 365 Defender](m365d-enable.md).

Para obtener más información sobre la búsqueda avanzada en Microsoft Defender for Cloud Apps datos, vea el [vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa). 

## <a name="get-started-with-advanced-hunting"></a>Introducción a la búsqueda avanzada

Se recomienda seguir varios pasos para empezar a trabajar rápidamente con la búsqueda avanzada.

| Objetivo de aprendizaje | Descripción | Recurso |
|--|--|--|
| **Aprender el idioma** | La búsqueda avanzada se basa en [Kusto lenguaje de consulta](/azure/kusto/query/), que admite la misma sintaxis y operadores. Empiece a aprender el lenguaje de consulta mediante la ejecución de la primera consulta. | [Introducción al lenguaje de consulta](advanced-hunting-query-language.md) |
| **Aprenda a usar los resultados de la consulta.** | Obtenga información sobre los gráficos y las distintas formas en que puede ver o exportar los resultados. Explore cómo puede ajustar rápidamente las consultas, explorar en profundidad para obtener información más completa y realizar acciones de respuesta. | - [Trabajar con los resultados de la consulta](advanced-hunting-query-results.md)<br /> - [Realizar acciones en los resultados de la consulta](advanced-hunting-take-action.md) |
| **Entender el esquema** | Obtenga una visión adecuada y de alto nivel de las tablas en el esquema y sus columnas. Obtenga información sobre dónde buscar datos al construir las consultas. | - [Referencia de esquema](advanced-hunting-schema-tables.md) <br />- [Transición de Microsoft Defender para punto de conexión](advanced-hunting-migrate-from-mde.md) |
| **Obtener sugerencias y ejemplos expertos** | Entrene de forma gratuita con guías de expertos de Microsoft. Explore colecciones de consultas predefinidas que cubren diferentes escenarios de búsqueda de amenazas. | - [Obtener formación de expertos](advanced-hunting-expert-training.md) <br />- [Uso de consultas compartidas](advanced-hunting-shared-queries.md) <br />- [Ir a buscar](advanced-hunting-go-hunt.md) <br />- [Búsqueda de amenazas entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md) |
| **Optimización de consultas y control de errores** | Comprenda cómo crear consultas eficaces y sin errores. | - [Procedimientos recomendados de consulta](advanced-hunting-best-practices.md)<br />- [Controlar errores](advanced-hunting-errors.md) |
| **Crear reglas de detección personalizadas** | Comprenda cómo puede usar consultas de búsqueda avanzadas para desencadenar alertas y realizar acciones de respuesta automáticamente. | - [Introducción a las detecciones personalizadas](custom-detections-overview.md) <br />- [Reglas de detección personalizadas](custom-detection-rules.md) |

## <a name="get-access"></a>Obtener acceso
Para usar la búsqueda avanzada u otras funcionalidades [de Microsoft 365 Defender](microsoft-365-defender.md), necesita un rol adecuado en Azure Active Directory. [Obtenga información sobre los roles y permisos necesarios para la búsqueda avanzada](custom-roles.md).

Además, el acceso a los datos de punto de conexión viene determinado por la configuración del control de acceso basado en rol (RBAC) en Microsoft Defender para punto de conexión. [Obtenga información sobre cómo administrar el acceso a Microsoft 365 Defender](m365d-permissions.md).


## <a name="data-freshness-and-update-frequency"></a>Actualización y frecuencia de actualización de datos
Los datos de búsqueda avanzada se pueden clasificar en dos tipos distintos, cada uno consolidado de forma diferente.

- **Datos de eventos o actividades**: rellena tablas sobre alertas, eventos de seguridad, eventos del sistema y evaluaciones rutinarias. La búsqueda avanzada recibe estos datos casi inmediatamente después de que los sensores que los recopilan los transmitan correctamente a los servicios en la nube correspondientes. Por ejemplo, puede consultar datos de eventos de sensores en buen estado en estaciones de trabajo o controladores de dominio casi inmediatamente después de que estén disponibles en Microsoft Defender para punto de conexión y Microsoft Defender for Identity.
- **Datos de entidad**: rellena tablas con información sobre usuarios y dispositivos. Estos datos proceden tanto de orígenes de datos relativamente estáticos como de orígenes dinámicos, como entradas de Active Directory y registros de eventos. Para proporcionar datos actualizados, las tablas se actualizan con información nueva cada 15 minutos, lo que agrega filas que podrían no estar completamente rellenadas. Cada 24 horas, los datos se consolidan para insertar un registro que contiene el conjunto de datos más reciente y completo sobre cada entidad.

## <a name="time-zone"></a>Zona horaria
La información de hora de la búsqueda avanzada está en la zona horaria UTC.

## <a name="related-topics"></a>Temas relacionados
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Obtener formación experta](advanced-hunting-expert-training.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)
