---
title: API compatibles de Microsoft Defender para punto de conexión
ms.reviewer: ''
description: Obtenga información sobre las entidades específicas admitidas de Microsoft Defender para puntos de conexión a las que puede crear llamadas a la API.
keywords: apis, api admitidas, actor, alertas, dispositivo, usuario, dominio, ip, archivo, consultas avanzadas, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8154c144e82a38665f18ec35fdc8d49247ad75ca
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "53655748"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>API compatibles de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a>URI de extremo y control de versiones

### <a name="endpoint-uri"></a>URI del extremo

> El URI de base de servicio es: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)
>
> Las consultas basadas en OData tienen el prefijo '/api'. Por ejemplo, para obtener alertas, puede enviar una solicitud GET a [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)

### <a name="versioning"></a>Control de versiones

> La API admite el control de versiones.
>
> La versión actual es **V1.0**.
>
> Para usar una versión específica, use este formato: `https://api.securitycenter.microsoft.com/api/{Version}` . Por ejemplo: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
>
> Si no especifica ninguna versión (por ejemplo, ) llegará a `https://api.securitycenter.microsoft.com/api/alerts` la versión más reciente.

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Obtenga más información sobre las entidades admitidas individualmente en las que puede ejecutar llamadas API y detalles como valores de solicitud HTTP, encabezados de solicitud y respuestas esperadas.

## <a name="in-this-section"></a>En esta sección

Tema | Descripción
:---|:---
[Búsqueda avanzada de amenazas](run-advanced-query-api.md) | Ejecutar consultas desde la API.
[Propiedades y métodos de alerta](alerts.md) | Ejecute llamadas API como \- obtener alertas, crear alertas, actualizar alertas y mucho más.
[Exportar métodos de evaluación y propiedades por dispositivo](get-assessment-methods-properties.md) | Ejecute llamadas api para recopilar evaluaciones de vulnerabilidades por dispositivo, como: evaluación de configuración segura de exportación, evaluación de inventario de software de exportación, evaluación de vulnerabilidades de software de exportación y evaluación de vulnerabilidades de software de exportación \- delta.
[Propiedades y métodos de investigación automatizada](investigation.md) | Ejecute llamadas API como \- obtener la colección de Investigación.
[Obtener alertas relacionadas con dominios](get-domain-related-alerts.md) | Ejecute llamadas API como obtener dispositivos relacionados con \- el dominio, estadísticas de dominio y mucho más.
[Propiedades y métodos de archivo](files.md) | Ejecute llamadas API como obtener información de archivos, alertas relacionadas con \- archivos, dispositivos relacionados con archivos y estadísticas de archivos.
[Propiedades y métodos de indicadores](ti-indicator.md) | Ejecute una llamada a la API como \- obtener indicadores, crear indicadores y eliminar indicadores.
[Obtener alertas relacionadas con IP](get-ip-related-alerts.md) | Ejecute llamadas API como \- obtener alertas relacionadas con IP y obtener estadísticas de IP.
[Propiedades y métodos de máquina](machine.md) | Ejecute llamadas API como obtener dispositivos, obtener dispositivos por identificador, información sobre usuarios que han iniciado \- sesión, editar etiquetas y mucho más.
[Métodos y propiedades de acción de máquina](machineaction.md) | Ejecute una llamada API como \- Aislamiento, Ejecutar examen antivirus y mucho más.
[Propiedades y métodos estáticos](recommendation.md) | Ejecute llamadas API como \- obtener recomendación por identificador.
[Propiedades y métodos de la actividad de corrección](get-remediation-methods-properties.md) | Ejecute una llamada API como obtener todas las tareas de corrección, obtener la tarea de corrección de dispositivos expuestos y \- obtener una tarea de corrección por identificador.
[Propiedades y métodos de puntuación](score.md) | Ejecuta llamadas API como obtener \- puntuación de exposición o obtener puntuación segura del dispositivo.
[Propiedades y métodos de software](software.md) | Ejecute llamadas API como, \- por ejemplo, enumerar vulnerabilidades por software.
[Métodos de usuario](user.md) | Ejecute llamadas API como obtener alertas relacionadas con \- el usuario y dispositivos relacionados con el usuario.
[Propiedades y métodos de vulnerabilidad](vulnerability.md) | Ejecute llamadas API, como \- los dispositivos de lista por vulnerabilidad.

## <a name="see-also"></a>Vea también

- [Microsoft Defender para api de punto de conexión](apis-intro.md)

- [Notas de la versión de api de Microsoft Defender para endpoint](api-release-notes.md)
