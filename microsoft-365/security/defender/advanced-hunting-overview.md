---
title: 'Información general: Búsqueda avanzada'
description: Obtenga más información sobre las consultas de búsqueda avanzada en Microsoft 365 y cómo usarlas para encontrar de forma proactiva amenazas y debilidades en la red
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto
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
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
search.appverid: met150
ms.openlocfilehash: aaf1ab874eddaae385cf3eaf3f0e3fb0bea8d877
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67741574"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Búsqueda proactiva de amenazas con la búsqueda avanzada de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consultas que le permite explorar hasta 30 días de datos sin procesar. Puede inspeccionar eventos de forma proactiva en su red para localizar entidades e indicadores de amenazas. El acceso flexible a los datos permite la búsqueda sin restricciones de amenazas conocidas y potenciales.

La búsqueda avanzada admite dos modos, guiados y avanzados. Use [el modo guiado](advanced-hunting-query-builder.md) si aún no está familiarizado con Lenguaje de consulta Kusto (KQL) o prefiere la comodidad de un generador de consultas. Use [el modo avanzado](advanced-hunting-query-language.md) si está cómodo con KQL para crear consultas desde cero. 

**Para empezar a buscar, lea [Elegir entre modos guiados y avanzados para cazar en Microsoft 365 Defender](advanced-hunting-modes.md).**
<br><br>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4G6DO]

Puede usar las mismas consultas de búsqueda de amenazas para crear reglas de detección personalizadas. Estas reglas se ejecutan automáticamente para buscar y, a continuación, responder a sospechas de actividad de infracción, máquinas mal configuradas y otros hallazgos.

Esta funcionalidad es similar a la [búsqueda avanzada en Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) y admite consultas que comprueban un conjunto de datos más amplio procedente de:

- Microsoft Defender para punto de conexión
- Microsoft Defender para Office 365
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Identity

Para usar la búsqueda avanzada, [active Microsoft 365 Defender](m365d-enable.md).

Para obtener más información sobre la búsqueda avanzada en Microsoft Defender for Cloud Apps datos, vea el [vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa). 



## <a name="get-access"></a>Obtener acceso
Para usar la búsqueda avanzada u otras funcionalidades [de Microsoft 365 Defender](microsoft-365-defender.md), necesita un rol adecuado en Azure Active Directory. [Obtenga información sobre los roles y permisos necesarios para la búsqueda avanzada](custom-roles.md).

Además, el acceso a los datos de punto de conexión viene determinado por la configuración del control de acceso basado en rol (RBAC) en Microsoft Defender para punto de conexión. [Obtenga información sobre cómo administrar el acceso a Microsoft 365 Defender](m365d-permissions.md).


## <a name="data-freshness-and-update-frequency"></a>Actualización de datos y frecuencia de actualización
Los datos de búsqueda avanzada se pueden clasificar en dos tipos distintos, cada uno consolidado de forma diferente.

- **Datos de eventos o de actividad**: rellena tablas sobre alertas, eventos de seguridad, eventos del sistema y evaluaciones rutinarias. La búsqueda avanzada recibe estos datos casi inmediatamente después de que los sensores que los recopilan los transmitan correctamente a los servicios en la nube correspondientes. Por ejemplo, puede consultar datos de eventos de sensores en buen estado en estaciones de trabajo o controladores de dominio casi inmediatamente después de que estén disponibles en Microsoft Defender para punto de conexión y Microsoft Defender for Identity.
- **Datos de entidad**: rellena tablas con información sobre usuarios y dispositivos. Estos datos proceden tanto de orígenes de datos relativamente estáticos como de orígenes dinámicos, como entradas de Active Directory y registros de eventos. Para proporcionar datos nuevos, las tablas se actualizan con cualquier información nueva cada 15 minutos, agregando filas que podrían no estar completamente rellenadas. Cada 24 horas, los datos se consolidan para insertar un registro que contiene el conjunto de datos más reciente y completo sobre cada entidad.

## <a name="time-zone"></a>Zona horaria
La información de la hora en la búsqueda avanzada está en la zona horaria UTC (Universal Time Coordinated).

## <a name="related-topics"></a>Temas relacionados
- [Elegir entre modos de búsqueda guiados y avanzados](advanced-hunting-modes.md)
- [Compilación de consultas de búsqueda mediante el modo guiado](advanced-hunting-query-builder.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)
