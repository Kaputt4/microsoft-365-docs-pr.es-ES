---
title: API compatibles de Microsoft Defender para punto de conexión
ms.reviewer: ''
description: Obtenga información sobre las entidades de Microsoft Defender para punto de conexión admitidas específicas en las que puede crear llamadas API.
keywords: apis, api admitidas, actor, alertas, dispositivo, usuario, dominio, ip, archivo, consultas avanzadas, búsqueda avanzada
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9b8009af5bd88c1dfd37dc7e8297e3c7e05f1356
ms.sourcegitcommit: 414682b9bf42dc19a89c893d3c515aee9765b6e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2022
ms.locfileid: "67280771"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>API compatibles de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para Empresas](../defender-business/index.yml)

> [!IMPORTANT]
> Las funcionalidades avanzadas de búsqueda no se incluyen en Defender para empresas. Consulte [Comparar Microsoft Defender para Empresas con los planes 1 y 2 de Microsoft Defender para punto de conexión](../defender-business/compare-mdb-m365-plans.md#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2).


> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a>Uri de punto de conexión y control de versiones

### <a name="endpoint-uri"></a>URI del extremo

> El URI base del servicio es: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)
>
> Las consultas basadas en OData tienen el prefijo "/api". Por ejemplo, para obtener alertas, puede enviar una solicitud GET a [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)

### <a name="versioning"></a>Control de versiones

> La API admite el control de versiones.
>
> La versión actual es **V1.0**.
>
> Para usar una versión específica, use este formato: `https://api.securitycenter.microsoft.com/api/{Version}`. Por ejemplo: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
>
> Si no especifica ninguna versión (por ejemplo, `https://api.securitycenter.microsoft.com/api/alerts`) llegará a la versión más reciente.

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Obtenga más información sobre las entidades admitidas individuales en las que puede ejecutar llamadas API y detalles como valores de solicitud HTTP, encabezados de solicitud y respuestas esperadas.

## <a name="in-this-section"></a>En esta sección

Tema | Descripción
:---|:---
[**Métodos de búsqueda avanzada**](run-advanced-query-api.md) | Ejecute consultas desde la API.
[Métodos y propiedades **de alerta**](alerts.md) | Ejecute llamadas API, como \- obtener alertas, crear alertas, actualizar alertas, etc.
[Exportación de métodos y propiedades de **evaluación** por dispositivo](get-assessment-methods-properties.md) | Ejecute llamadas API para recopilar evaluaciones de vulnerabilidades por dispositivo, como: \- evaluación de configuración segura de exportación, evaluación del inventario de software de exportación, evaluación de vulnerabilidades de software de exportación y evaluación de vulnerabilidades de software de exportación diferencial.
[Propiedades y métodos **de investigación automatizados**](investigation.md) | Ejecute llamadas API, como \- get collection of Investigation.
[Exportación de propiedades y métodos de mantenimiento del dispositivo](device-health-api-methods-properties.md) | Ejecutar llamadas API como - GET /api/public/avdeviceshealth.
[Alertas relacionadas con **el dominio**](get-domain-related-alerts.md) | Ejecute llamadas API, como \- obtener dispositivos relacionados con el dominio, estadísticas de dominio, etc.
[Propiedades y métodos **de archivo**](files.md) | Ejecute llamadas API, como \- obtener información de archivos, alertas relacionadas con archivos, dispositivos relacionados con archivos y estadísticas de archivos.
[Métodos y propiedades **de indicadores**](ti-indicator.md) | Ejecute una llamada API, como \- obtener indicadores, crear indicador y eliminar indicadores.
[Alertas relacionadas con **IP**](get-ip-related-alerts.md) | Ejecute llamadas API, como \- obtener alertas relacionadas con IP y obtener estadísticas de IP.
[Métodos y propiedades **de la máquina**](machine.md) | Ejecute llamadas API, como \- obtener dispositivos, obtener dispositivos por identificador, información sobre los usuarios que han iniciado sesión, editar etiquetas, etc.
[Propiedades y métodos **de acción de la máquina**](machineaction.md) | Ejecute una llamada API, como \- Aislamiento, Ejecutar examen antivirus y mucho más.
[Métodos y propiedades **de recomendación**](recommendation.md) | Ejecute llamadas API, como \- obtener una recomendación por identificador.
[Propiedades y métodos **de actividad de corrección**](get-remediation-methods-properties.md) | Ejecute una llamada API, como \- obtener todas las tareas de corrección, obtener la tarea de corrección de dispositivos expuestos y obtener una tarea de corrección por identificador.
[**Puntuación de** métodos y propiedades](score.md) | Ejecute llamadas API, como \- obtener la puntuación de exposición o obtener la puntuación de seguridad del dispositivo.
[Propiedades y métodos **de software**](software.md) | Ejecute llamadas API, como \- enumerar vulnerabilidades por software.
[**Métodos de usuario** y propiedades](user.md) | Ejecute llamadas API, como \- obtener alertas relacionadas con el usuario y dispositivos relacionados con el usuario.
[Propiedades y métodos **de vulnerabilidad**](vulnerability.md) | Ejecute llamadas API, como \- enumerar dispositivos por vulnerabilidad.

## <a name="see-also"></a>Vea también

- [API de Microsoft Defender para punto de conexión](apis-intro.md)

- [notas de la versión de la API de Microsoft Defender para punto de conexión](api-release-notes.md)
