---
title: Compatible con Microsoft Defender para LAS API de punto de conexión
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
ms.technology: mde
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198332"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>Compatible con Microsoft Defender para LAS API de punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a>URI de extremo y control de versiones

### <a name="endpoint-uri"></a>URI del extremo:            

> El URI de base de servicio es: https://api.securitycenter.microsoft.com
> 
> Las consultas basadas en OData tienen el prefijo '/api'. Por ejemplo, para obtener alertas, puede enviar una solicitud GET a https://api.securitycenter.microsoft.com/api/alerts

### <a name="versioning"></a>Control de versiones:

> La API admite el control de versiones.
> 
> La versión actual es **V1.0**.
> 
> Para usar una versión específica, use este formato: `https://api.securitycenter.microsoft.com/api/{Version}` . Por ejemplo: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
> 
> Si no especifica ninguna versión (por ejemplo, ) llegará a https://api.securitycenter.microsoft.com/api/alerts la versión más reciente.


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Obtenga más información sobre las entidades admitidas individualmente en las que puede ejecutar llamadas API y detalles como valores de solicitud HTTP, encabezados de solicitud y respuestas esperadas.

## <a name="in-this-section"></a>En esta sección

Tema | Descripción
:---|:---
Búsqueda avanzada | Ejecutar consultas desde la API.
Alertas | Ejecute llamadas API como obtener alertas, crear alertas, actualizar alertas y mucho más.
Dominios | Ejecute llamadas API como obtener dispositivos relacionados con el dominio, estadísticas de dominio y mucho más.
Archivos | Ejecute llamadas API como obtener información de archivos, alertas relacionadas con archivos, dispositivos relacionados con archivos y estadísticas de archivos.
IP | Ejecute llamadas API como obtener alertas relacionadas con IP y obtener estadísticas de IP.
Equipos | Ejecute llamadas API como obtener dispositivos, obtener dispositivos por identificador, información sobre usuarios que han iniciado sesión, editar etiquetas y mucho más.
Acciones de la máquina | Ejecute una llamada API como Aislamiento, Ejecutar examen antivirus y mucho más.
Indicadores | Ejecute una llamada api como crear indicador, obtener indicadores y eliminar indicadores.
Usuarios | Ejecute llamadas API como obtener alertas relacionadas con el usuario y dispositivos relacionados con el usuario.
Puntuación | Ejecuta llamadas API como obtener puntuación de exposición o obtener puntuación segura del dispositivo.
Software | Ejecute llamadas API como, por ejemplo, enumerar vulnerabilidades por software.
Vulnerabilidad | Ejecute llamadas API, como los dispositivos de lista por vulnerabilidad.
Recomendación | Ejecute llamadas API como Obtener recomendación por identificador.

## <a name="see-also"></a>Vea también
- [Microsoft Defender para api de punto de conexión](apis-intro.md)
