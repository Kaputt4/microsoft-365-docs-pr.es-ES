---
title: Información general sobre la búsqueda avanzada en Microsoft Defender para endpoint
description: Usar las capacidades de búsqueda de amenazas en Microsoft Defender para endpoint para crear consultas que encuentren amenazas y debilidades en la red
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, microsoft defender para punto de conexión, wdatp, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, zona horaria, UTC
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c106e76486854817c87f290f060999020beae5fd
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "53655460"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a>Búsqueda proactiva de amenazas con búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedhunting-abovefoldlink)

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consulta que le permite explorar hasta 30 días de datos sin procesar. Puede inspeccionar de forma proactiva los eventos de la red para localizar indicadores y entidades de amenazas. El acceso flexible a los datos permite la búsqueda sin restricciones para amenazas conocidas y potenciales.

Vea este vídeo para obtener una introducción rápida a la búsqueda avanzada y un breve tutorial que le ayudará a empezar rápidamente.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqo]

Puede usar las mismas consultas de búsqueda de amenazas para crear reglas de detección personalizadas. Estas reglas se ejecutan automáticamente para buscar y responder a una actividad de infracción sospechosa, máquinas mal configuradas y otras conclusiones.

> [!TIP]
> Usa la búsqueda [avanzada en Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview) para buscar amenazas mediante datos de Defender para endpoint, Microsoft Defender para Office 365, Microsoft Cloud App Security y Microsoft Defender para Identity. [Active la Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable).

Obtenga más información sobre cómo mover los flujos de trabajo de búsqueda avanzados de Microsoft Defender para endpoint a Microsoft 365 Defender en Migrar consultas avanzadas de búsqueda de [Microsoft Defender para endpoint](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde).

## <a name="get-started-with-advanced-hunting"></a>Introducción a la búsqueda avanzada

Siga estos pasos para aumentar los conocimientos avanzados de búsqueda.

Le recomendamos que siga los pasos siguientes para empezar a trabajar rápidamente con la búsqueda avanzada.

<br>

****

|Objetivo de aprendizaje|Descripción|Recurso|
|---|---|---|
|**Aprender el idioma**|La búsqueda avanzada se basa en [el lenguaje de consulta Kusto,](/azure/kusto/query/)que admite la misma sintaxis y operadores. Empiece a aprender el lenguaje de consulta mediante la ejecución de la primera consulta.|[Introducción al lenguaje de consulta](advanced-hunting-query-language.md)|
|**Obtenga información sobre cómo usar los resultados de la consulta**|Obtenga información sobre gráficos y diversas formas de ver o exportar los resultados. Explore cómo puede ajustar rápidamente las consultas y profundizar para obtener información más enriquecente.|[Trabajar con resultados de consulta](advanced-hunting-query-results.md)|
|**Entender el esquema**|Obtenga una visión adecuada y de alto nivel de las tablas en el esquema y sus columnas. Obtenga información sobre dónde buscar datos al crear las consultas.|[Referencia del esquema](advanced-hunting-schema-reference.md)|
|**Usar consultas predefinidas**|Explore colecciones de consultas predefinidas que cubren diferentes escenarios de búsqueda de amenazas.|[Consultas compartidas](advanced-hunting-shared-queries.md)|
|**Optimizar consultas y controlar errores**|Comprenda cómo crear consultas eficientes y libres de errores.|- [Procedimientos recomendados de consulta](advanced-hunting-best-practices.md)<br>- [Controlar errores](advanced-hunting-errors.md)|
|**Obtener la cobertura más completa**|Use la configuración de auditoría para proporcionar una mejor cobertura de datos para su organización.|- [Ampliar la cobertura de búsqueda avanzada](advanced-hunting-extend-data.md)|
|**Ejecutar una investigación rápida**|Ejecute rápidamente una consulta de búsqueda avanzada para investigar la actividad sospechosa.|- [Búsqueda rápida de información de entidad o evento con *go hunt*](advanced-hunting-go-hunt.md)|
|**Contener amenazas y solucionar compromisos**|Responder a los ataques mediante la quarantining de archivos, la restricción de la ejecución de aplicaciones y otras acciones|- [Realizar acciones en los resultados avanzados de la consulta de búsqueda](advanced-hunting-take-action.md)|
|**Crear reglas de detección personalizadas**|Comprenda cómo puede usar consultas de búsqueda avanzadas para desencadenar alertas y realizar acciones de respuesta automáticamente.|- [Introducción a las detecciones personalizadas](overview-custom-detections.md)<br>- [Reglas de detección personalizadas](custom-detection-rules.md)|
|


## <a name="data-freshness-and-update-frequency"></a>Actualización de datos y frecuencia de actualización

Los datos de búsqueda avanzados se pueden clasificar en dos tipos distintos, cada uno consolidado de forma diferente.

- **Datos de eventos o actividades:** rellena tablas sobre alertas, eventos de seguridad, eventos del sistema y evaluaciones rutinarias. La búsqueda avanzada recibe estos datos casi inmediatamente después de que los sensores que los recopilan los transmitan correctamente a Defender for Endpoint.
- **Datos de entidad:** rellena tablas con información consolidada sobre usuarios y dispositivos. Estos datos proceden de orígenes de datos relativamente estáticos y orígenes dinámicos, como entradas de Active Directory y registros de eventos. Para proporcionar datos nuevos, las tablas se actualizan con cualquier información nueva cada 15 minutos, agregando filas que podrían no estar completamente rellenadas. Cada 24 horas, los datos se consolidan para insertar un registro que contiene el conjunto de datos más reciente y completo sobre cada entidad.

## <a name="time-zone"></a>Zona horaria

La información de hora en la búsqueda avanzada se encuentra actualmente en la zona horaria UTC.

## <a name="related-topics"></a>Temas relacionados

- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Entender el esquema](advanced-hunting-schema-reference.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a las detecciones personalizadas](overview-custom-detections.md)
