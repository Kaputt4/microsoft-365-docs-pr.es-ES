---
title: 'Información general: búsqueda avanzada'
description: Obtenga más información sobre las consultas de búsqueda avanzada en Microsoft 365 y cómo usarlas para encontrar de forma proactiva amenazas y debilidades en la red
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, Microsoft 365, protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e586050465464def02c7787a5fb218b0b6071c7
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338478"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Búsqueda proactiva de amenazas con la búsqueda avanzada en la Protección contra amenazas de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consulta que le permite explorar hasta 30 días de datos sin procesar. Puede inspeccionar eventos de forma proactiva en su red para localizar indicadores y entidades de amenazas. El acceso flexible a los datos permite una búsqueda sin restricciones tanto de amenazas conocidas como potenciales.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

Puede usar las mismas consultas de búsqueda de amenazas para crear reglas de detección personalizadas. Estas reglas se ejecutan automáticamente para comprobar y, a continuación, responder a la actividad de infracciones, máquinas mal configuradas y otras conclusiones.

Esta funcionalidad es similar a la [búsqueda avanzada en ATP de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview). Disponible en el centro de seguridad 365 de Microsoft, esta función admite consultas que comprueban un conjunto de datos más amplio desde:

- Protección contra amenazas avanzada de Microsoft Defender
- Protección contra amenazas avanzada de Office 365
- Microsoft Cloud App Security
- Azure Advanced Threat Protection

Para usar la búsqueda avanzada, [active la Protección contra amenazas de Microsoft](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Introducción a la búsqueda avanzada

Le recomendamos que siga varios pasos para empezar rápidamente con la búsqueda avanzada.

| Objetivo de aprendizaje | Descripción | Recurso |
|--|--|--|
| **Obtener información sobre el idioma** | La búsqueda avanzada se basa en el [lenguaje de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/)y admite la misma sintaxis y operadores. Empiece a aprender el lenguaje de consulta mediante la ejecución de la primera consulta. | [Introducción al lenguaje de consulta](advanced-hunting-query-language.md) |
| **Obtener información sobre cómo usar los resultados de la consulta** | Obtenga información sobre los gráficos y las distintas formas en que puede ver o exportar los resultados. Explore cómo puede ajustar rápidamente las consultas, profundizar para obtener información más enriquecida y tomar medidas de respuesta. | - [Trabajar con los resultados de la consulta](advanced-hunting-query-results.md)<br>- [Realizar acciones en los resultados de la consulta](advanced-hunting-take-action.md) |
| **Entender el esquema** | Obtenga una visión adecuada y de alto nivel de las tablas en el esquema y sus columnas. Obtenga información sobre dónde buscar datos al crear consultas. | - [Referencia de esquema](advanced-hunting-schema-tables.md)<br>- [Transición de ATP de Microsoft defender](advanced-hunting-migrate-from-mdatp.md) |
| **Obtener sugerencias y ejemplos de expertos** | Entrenar gratuitamente con las guías de expertos de Microsoft. Explore colecciones de consultas predefinidas que cubren diferentes escenarios de búsqueda de amenazas. | - [Obtener formación experta](advanced-hunting-expert-training.md)<br>- [Usar consultas compartidas](advanced-hunting-shared-queries.md)<br>- [Ir a la búsqueda](advanced-hunting-go-hunt.md)<br>- [Buscar amenazas en dispositivos, mensajes de correo electrónico, aplicaciones e identidades](advanced-hunting-query-emails-devices.md) |
| **Optimizar las consultas y controlar los errores** | Aprenda a crear consultas eficaces y sin errores. | - [Procedimientos recomendados de consulta](advanced-hunting-best-practices.md)<br>- [Controlar errores](advanced-hunting-errors.md) |
| **Crear reglas de detección personalizadas** | Comprenda cómo puede usar consultas de búsqueda avanzada para desencadenar alertas y realizar acciones de respuesta automáticamente. | - [Información general sobre las detecciones personalizadas](custom-detections-overview.md)<br>- [Reglas de detección personalizadas](custom-detection-rules.md) |

## <a name="get-access"></a>Obtener acceso
Para usar la búsqueda avanzada u otras capacidades de [Microsoft Threat Protection](microsoft-threat-protection.md) , necesita un rol apropiado en Azure Active Directory. Además, el acceso a los datos de los extremos se determina mediante la configuración de control de acceso basado en roles (RBAC) en ATP de Microsoft defender. [Obtener información acerca de la administración del acceso a protección contra amenazas de Microsoft](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Actualización de datos y frecuencia de actualización
Los datos de búsqueda avanzada pueden clasificarse en dos tipos distintos, cada uno de ellos consolidado de manera diferente.

- **Datos de eventos o actividades**: se rellenan tablas sobre alertas, eventos de seguridad, eventos del sistema y evaluaciones rutinarias. La búsqueda avanzada recibe estos datos casi inmediatamente después de que los sensores que los recopilan los transmitan correctamente a los servicios en la nube correspondientes. Por ejemplo, puede consultar los datos de eventos de sensores saludables en estaciones de trabajo o controladores de dominio casi inmediatamente después de que estén disponibles en Microsoft defender ATP y Azure ATP.
- **Datos de entidad**: rellena tablas con información acerca de los usuarios y los dispositivos. Estos datos proceden de orígenes de datos relativamente estáticos y dinámicos, como las entradas de Active Directory y los registros de eventos. Para proporcionar datos nuevos, las tablas se actualizan con cualquier información nueva cada 15 minutos, agregando filas que puede que no se llenen completamente. Cada 24 horas, los datos se consolidan para insertar un registro que contenga el conjunto de datos más reciente y completo sobre cada entidad.

## <a name="time-zone"></a>Zona horaria
La información de hora de la búsqueda avanzada está en la zona horaria UTC.

## <a name="related-topics"></a>Temas relacionados
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Obtener formación experta](advanced-hunting-expert-training.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)

