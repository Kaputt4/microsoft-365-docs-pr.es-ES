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
ms.openlocfilehash: 8dca8cac2c66147975f71c86b91aee7b36c92cf9
ms.sourcegitcommit: 51f040a4edb8dd52521a5d7b0f7a975986a1af10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2020
ms.locfileid: "46608338"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Búsqueda proactiva de amenazas con la búsqueda avanzada en la Protección contra amenazas de Microsoft

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consulta que le permite explorar hasta 30 días de datos sin procesar. Puede inspeccionar eventos de forma proactiva en su red para localizar indicadores y entidades interesantes. El acceso flexible a los datos facilita la búsqueda sin restricciones de las amenazas conocidas y potenciales.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

Puede usar las mismas consultas de búsqueda de amenazas para crear reglas de detección personalizadas. Estas reglas se ejecutan automáticamente para buscar diversos eventos y estados del sistema, como actividades de vulneración sospechosas y equipos mal configurados, y responder a ellos.

La característica es similar a la [búsqueda avanzada en ATP de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview), excepto que en el centro de seguridad de Microsoft 365, la búsqueda avanzada admite consultas que buscan datos de varias áreas de trabajo, incluidos datos sobre dispositivos, mensajes de correo electrónico, aplicaciones e identidades de ATP de Microsoft defender, Office 365 ATP, Microsoft Cloud App Security y Azure ATP. Para usar la búsqueda avanzada, [active la Protección contra amenazas de Microsoft](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Introducción a la búsqueda avanzada

Le recomendamos que siga los pasos siguientes para empezar a trabajar rápidamente con la búsqueda avanzada.

| Objetivo de aprendizaje | Descripción | Recurso |
|--|--|--|
| **Conozca el idioma** | La búsqueda avanzada se basa en el [lenguaje de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/)y admite la misma sintaxis y operadores. Empiece a aprender el lenguaje de consulta mediante la ejecución de la primera consulta. | [Introducción al lenguaje de consulta](advanced-hunting-query-language.md) |
| **Obtener información sobre cómo usar los resultados de la consulta** | Obtenga información sobre los gráficos y las distintas formas en que puede ver o exportar los resultados. Explore cómo puede ajustar rápidamente las consultas, profundizar para obtener información más enriquecida y tomar medidas de respuesta. | - [Trabajar con los resultados de la consulta](advanced-hunting-query-results.md)<br>- [Realizar acciones en los resultados de la consulta](advanced-hunting-take-action.md) |
| **Entender el esquema** | Obtenga una visión adecuada y de alto nivel de las tablas en el esquema y sus columnas. Esto le ayudará a determinar dónde buscar datos y cómo crear las consultas. | [Referencia del esquema](advanced-hunting-schema-tables.md) |
| **Aprovechar consultas predefinidas** | Explore colecciones de consultas predefinidas que cubren diferentes escenarios de búsqueda de amenazas. | - [Usar consultas compartidas](advanced-hunting-shared-queries.md)<br>- [Ir a la búsqueda](advanced-hunting-go-hunt.md) |
| **Optimizar las consultas** | Obtenga información acerca de cómo crear consultas eficientes y consultas que combinan datos de mensajes de correo electrónico y dispositivos. | - [Procedimientos recomendados de consulta](advanced-hunting-shared-queries.md) <br>- [Búsqueda en dispositivos y correos electrónicos](advanced-hunting-best-practices.md) |
| **Crear reglas de detección personalizadas** | Comprenda cómo puede usar consultas de búsqueda avanzada para desencadenar alertas y aplicar acciones de respuesta automáticamente. | - [Información general sobre las detecciones personalizadas](custom-detections-overview.md)<br>- [Reglas de detección personalizadas](custom-detection-rules.md) |

## <a name="get-access"></a>Obtener acceso
Para usar características de búsqueda avanzada u otras capacidades de [Microsoft Threat Protection](microsoft-threat-protection.md) , debe tener asignado un rol apropiado en Azure ad. Tenga en cuenta que el acceso a los datos de los extremos se ve influenciado por la configuración de control de acceso basada en roles en ATP de Microsoft defender. [Obtener información acerca de la administración del acceso a protección contra amenazas de Microsoft](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Actualización de datos y frecuencia de actualización
Los datos de búsqueda avanzada pueden clasificarse en dos tipos distintos, cada uno de ellos consolidado de manera diferente.

- **Datos de eventos o actividades** : se rellenan tablas sobre alertas, eventos de seguridad, eventos del sistema y evaluaciones rutinarias. La búsqueda avanzada recibe estos datos casi inmediatamente después de que los sensores que los recopilan los transmitan correctamente a los servicios en la nube correspondientes. Por ejemplo, puede empezar a consultar datos de eventos de sensores saludables en estaciones de trabajo o controladores de dominio casi inmediatamente después de que estén disponibles en Microsoft defender ATP y Azure ATP.
- **Datos de entidad** : rellena tablas con información consolidada acerca de los usuarios y los dispositivos. Estos datos proceden de orígenes de datos relativamente estáticos, como entradas de Active Directory y fuentes dinámicas, como registros de eventos. Para proporcionar datos nuevos, las tablas se actualizan cada 15 minutos con cualquier información nueva, agregando filas que puede que no se llenen completamente. Cada 24 horas, los datos se consolidan para insertar un registro que contenga el conjunto de datos más reciente y completo sobre cada entidad.

## <a name="related-topics"></a>Temas relacionados
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Realizar una acción en los resultados de consulta](advanced-hunting-take-action.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)
