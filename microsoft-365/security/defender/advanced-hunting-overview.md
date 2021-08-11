---
title: 'Información general: búsqueda avanzada'
description: Obtenga más información sobre las consultas de búsqueda avanzada en Microsoft 365 y cómo usarlas para encontrar de forma proactiva amenazas y debilidades en la red
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 564afed2c10d232076bf6875e035bcf03ea7712ada2b430729f4a936a675b8bb
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53833200"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Búsqueda proactiva de amenazas con búsqueda avanzada en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

> ¿Quiere experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de pruebas](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o bien [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).
>

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consultas que te permite explorar hasta 30 días de datos sin procesar. Puede inspeccionar de forma proactiva los eventos de la red para localizar indicadores y entidades de amenazas. El acceso flexible a los datos permite la búsqueda sin restricciones para amenazas conocidas y potenciales.
<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

Puede usar las mismas consultas de búsqueda de amenazas para crear reglas de detección personalizadas. Estas reglas se ejecutan automáticamente para buscar y responder a una actividad de infracción sospechosa, máquinas mal configuradas y otras conclusiones.

Esta funcionalidad es similar a la búsqueda avanzada en [Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) y admite consultas que comprueban un conjunto de datos más amplio desde:

- Microsoft Defender para punto de conexión
- Microsoft Defender para Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

Para usar la búsqueda avanzada, [active Microsoft 365 Defender](m365d-enable.md).

Para obtener más información sobre la búsqueda avanzada en Microsoft Cloud App Security datos, vea el [vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa). 

## <a name="get-started-with-advanced-hunting"></a>Introducción a la búsqueda avanzada

Se recomienda seguir varios pasos para empezar rápidamente con la búsqueda avanzada.

| Objetivo de aprendizaje | Descripción | Recurso |
|--|--|--|
| **Aprender el idioma** | La búsqueda avanzada se basa en [el lenguaje de consulta Kusto,](/azure/kusto/query/)que admite la misma sintaxis y operadores. Empiece a aprender el lenguaje de consulta mediante la ejecución de la primera consulta. | [Introducción al lenguaje de consulta](advanced-hunting-query-language.md) |
| **Obtenga información sobre cómo usar los resultados de la consulta** | Obtenga información sobre gráficos y diversas formas de ver o exportar los resultados. Explore cómo puede ajustar rápidamente las consultas, profundizar para obtener más información y realizar acciones de respuesta. | - [Trabajar con resultados de consulta](advanced-hunting-query-results.md)<br /> - [Realizar acciones en los resultados de la consulta](advanced-hunting-take-action.md) |
| **Entender el esquema** | Obtenga una visión adecuada y de alto nivel de las tablas en el esquema y sus columnas. Obtenga información sobre dónde buscar datos al crear las consultas. | - [Referencia de esquema](advanced-hunting-schema-tables.md) <br />- [Transición desde Microsoft Defender para endpoint](advanced-hunting-migrate-from-mde.md) |
| **Obtener sugerencias y ejemplos de expertos** | Entrena de forma gratuita con guías de expertos de Microsoft. Explore colecciones de consultas predefinidas que cubren diferentes escenarios de búsqueda de amenazas. | - [Obtener formación de expertos](advanced-hunting-expert-training.md) <br />- [Usar consultas compartidas](advanced-hunting-shared-queries.md) <br />- [Ir a la búsqueda](advanced-hunting-go-hunt.md) <br />- [Buscar amenazas en dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md) |
| **Optimizar consultas y controlar errores** | Comprenda cómo crear consultas eficientes y libres de errores. | - [Procedimientos recomendados de consulta](advanced-hunting-best-practices.md)<br />- [Controlar errores](advanced-hunting-errors.md) |
| **Crear reglas de detección personalizadas** | Comprenda cómo puede usar consultas de búsqueda avanzadas para desencadenar alertas y realizar acciones de respuesta automáticamente. | - [Introducción a las detecciones personalizadas](custom-detections-overview.md) <br />- [Reglas de detección personalizadas](custom-detection-rules.md) |

## <a name="get-access"></a>Obtener acceso
Para usar la búsqueda avanzada u [otras Microsoft 365 Defender](microsoft-365-defender.md) de búsqueda, necesita un rol adecuado en Azure Active Directory. [Obtenga información sobre los roles y permisos necesarios para la búsqueda avanzada.](custom-roles.md)

Además, el acceso a los datos del punto de conexión viene determinado por la configuración del control de acceso basado en roles (RBAC) en Microsoft Defender para endpoint. [Obtenga información sobre cómo administrar el acceso a Microsoft 365 Defender](m365d-permissions.md).


## <a name="data-freshness-and-update-frequency"></a>Actualización de datos y frecuencia de actualización
Los datos de búsqueda avanzados se pueden clasificar en dos tipos distintos, cada uno consolidado de forma diferente.

- **Datos de eventos o actividades:** rellena tablas sobre alertas, eventos de seguridad, eventos del sistema y evaluaciones rutinarias. La búsqueda avanzada recibe estos datos casi inmediatamente después de que los sensores que los recopilan los transmitan correctamente a los servicios en la nube correspondientes. Por ejemplo, puede consultar datos de eventos desde sensores en buen estado en estaciones de trabajo o controladores de dominio casi inmediatamente después de que estén disponibles en Microsoft Defender para Endpoint y Microsoft Defender para Identity.
- **Datos de entidad:** rellena las tablas con información sobre usuarios y dispositivos. Estos datos proceden de orígenes de datos relativamente estáticos y orígenes dinámicos, como entradas de Active Directory y registros de eventos. Para proporcionar datos nuevos, las tablas se actualizan con cualquier información nueva cada 15 minutos, agregando filas que podrían no estar completamente rellenadas. Cada 24 horas, los datos se consolidan para insertar un registro que contiene el conjunto de datos más reciente y completo sobre cada entidad.

## <a name="time-zone"></a>Zona horaria
La información de hora en la búsqueda avanzada se encuentra en la zona horaria UTC.

## <a name="related-topics"></a>Temas relacionados
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Obtener formación experta](advanced-hunting-expert-training.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)
