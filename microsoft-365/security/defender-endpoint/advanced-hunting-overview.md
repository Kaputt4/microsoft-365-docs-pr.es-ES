---
title: Introducción a la búsqueda avanzada en Microsoft Defender para punto de conexión
description: Uso de funcionalidades de búsqueda de amenazas en Microsoft Defender para punto de conexión para crear consultas que encuentren amenazas y puntos débiles en la red
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, mdatp, atp de microsoft defender, microsoft defender para punto de conexión, wdatp, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, zona horaria, UTC
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 4995e9b2090b3de237581bb2200304a7a37db7f1
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67679435"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a>Búsqueda proactiva de amenazas con búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedhunting-abovefoldlink)

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consulta que le permite explorar hasta 30 días de datos sin procesar. Puede inspeccionar eventos de forma proactiva en su red para localizar entidades e indicadores de amenazas. El acceso flexible a los datos permite la búsqueda sin restricciones de amenazas conocidas y potenciales.

Vea este vídeo para obtener una introducción rápida a la búsqueda avanzada y un breve tutorial que le ayudará a empezar rápidamente.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqo]

Puede usar las mismas consultas de búsqueda de amenazas para crear reglas de detección personalizadas. Estas reglas se ejecutan automáticamente para buscar y, a continuación, responder a sospechas de actividad de infracción, máquinas mal configuradas y otros hallazgos.

> [!TIP]
> Usar [la búsqueda avanzada en Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview) para buscar amenazas mediante datos de Defender para punto de conexión, Microsoft Defender para Office 365, Microsoft Defender for Cloud Apps y Microsoft Defender for Identity. [Active Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable).

Obtenga más información sobre cómo mover los flujos de trabajo de búsqueda avanzados de Microsoft Defender para punto de conexión a Microsoft 365 Defender en [Migración de consultas de búsqueda avanzadas desde Microsoft Defender para punto de conexión](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde).

## <a name="get-started-with-advanced-hunting"></a>Introducción a la búsqueda avanzada

Siga estos pasos para aumentar sus conocimientos avanzados de búsqueda.

Le recomendamos que siga los pasos siguientes para empezar a trabajar rápidamente con la búsqueda avanzada.

<br>

****

|Objetivo de aprendizaje|Descripción|Recurso|
|---|---|---|
|**Aprender el idioma**|La búsqueda avanzada se basa en el [lenguaje de consulta Kusto](/azure/kusto/query/), que admite la misma sintaxis y operadores. Empiece a aprender el lenguaje de consulta mediante la ejecución de la primera consulta.|[Introducción al lenguaje de consulta](advanced-hunting-query-language.md)|
|**Aprenda a usar los resultados de la consulta.**|Obtenga información sobre los gráficos y las distintas formas en que puede ver o exportar los resultados. Explore cómo puede ajustar rápidamente las consultas y explorar en profundidad para obtener información más enriquecida.|[Trabajar con resultados de consulta](advanced-hunting-query-results.md)|
|**Entender el esquema**|Obtenga una visión adecuada y de alto nivel de las tablas en el esquema y sus columnas. Obtenga información sobre dónde buscar datos al construir las consultas.|[Referencia del esquema](advanced-hunting-schema-reference.md)|
|**Usar consultas predefinidas**|Explore colecciones de consultas predefinidas que cubren diferentes escenarios de búsqueda de amenazas.|[Consultas compartidas](advanced-hunting-shared-queries.md)|
|**Optimización de consultas y control de errores**|Comprenda cómo crear consultas eficaces y sin errores.|[Prácticas recomendadas de consulta](advanced-hunting-best-practices.md) <p> [Controlar los errores](advanced-hunting-errors.md)|
|**Obtener la cobertura más completa**|Use la configuración de auditoría para proporcionar una mejor cobertura de datos para su organización.|[Ampliación de la cobertura de búsqueda avanzada](advanced-hunting-extend-data.md)|
|**Ejecución de una investigación rápida**|Ejecute rápidamente una consulta de búsqueda avanzada para investigar actividades sospechosas.|[Búsqueda rápida de información de entidades o eventos con *go hunt*](advanced-hunting-go-hunt.md)|
|**Contener amenazas y abordar los riesgos**|Responder a ataques mediante la cuarentena de archivos, la restricción de la ejecución de aplicaciones y otras acciones|[Realizar acciones en los resultados de consultas de búsqueda avanzadas](advanced-hunting-take-action.md)|
|**Crear reglas de detección personalizadas**|Comprenda cómo puede usar consultas de búsqueda avanzadas para desencadenar alertas y realizar acciones de respuesta automáticamente.|[Introducción a las detecciones personalizadas](overview-custom-detections.md) <p> [Reglas de detección personalizada](custom-detection-rules.md)|
|

## <a name="data-freshness-and-update-frequency"></a>Actualización de datos y frecuencia de actualización

Los datos de búsqueda avanzada se pueden clasificar en dos tipos distintos, cada uno consolidado de forma diferente.

- **Datos de eventos o actividades**: rellena tablas sobre alertas, eventos de seguridad, eventos del sistema y evaluaciones rutinarias. La búsqueda avanzada recibe estos datos casi inmediatamente después de que los sensores que los recopilan los transmitan correctamente a Defender para punto de conexión.
- **Datos de entidad**: rellena tablas con información consolidada sobre usuarios y dispositivos. Estos datos proceden tanto de orígenes de datos relativamente estáticos como de orígenes dinámicos, como entradas de Active Directory y registros de eventos. Para proporcionar datos nuevos, las tablas se actualizan con cualquier información nueva cada 15 minutos, agregando filas que podrían no estar completamente rellenadas. Cada 24 horas, los datos se consolidan para insertar un registro que contiene el conjunto de datos más reciente y completo sobre cada entidad.

## <a name="time-zone"></a>Zona horaria

La información de hora de la búsqueda avanzada está actualmente en la zona horaria UTC.

## <a name="related-topics"></a>Temas relacionados

- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Entender el esquema](advanced-hunting-schema-reference.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a las detecciones personalizadas](overview-custom-detections.md)
- [Introducción a la cuenta de almacenamiento](/azure/storage/common/storage-account-overview)
- [Azure Event Hubs: una plataforma de streaming de macrodatos y un servicio de ingesta de eventos](/azure/event-hubs/event-hubs-about)
