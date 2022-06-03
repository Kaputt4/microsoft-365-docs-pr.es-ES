---
title: Eliminación de un archivo de la biblioteca de respuestas dinámicas
description: Obtenga información sobre cómo eliminar un archivo de la biblioteca de respuestas dinámicas.
keywords: api, graph api, api admitidas, eliminación de la biblioteca
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: reference
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 97a2a2152a60ff542cb946c4283fe3f26c4b9c8e
ms.sourcegitcommit: 35f167725bec5fd4fe131781a53d96b060cf232d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "65874138"
---
#  <a name="delete-a-file-from-the-live-response-library"></a>Eliminación de un archivo de la biblioteca de respuestas dinámicas  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

[!include[Prerelease information](../../includes/prerelease.md)]

>¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Elimine un archivo de la biblioteca de respuestas dinámicas.

## <a name="limitations"></a>Limitaciones

1.  Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Comenzar](apis-intro.md).

| Tipo de permiso                    | Permiso     | Nombre para mostrar del permiso        |
|------------------------------------|----------------|--------------------------------|
| Aplicación                        | Library.Manage | Administración de la biblioteca de respuestas dinámicas |
| Delegado (cuenta profesional o educativa) | Library.Manage | Administración de la biblioteca de respuestas dinámicas |

## <a name="http-request"></a>Solicitud HTTP

DELETE https://api.securitycenter.microsoft.com/api/libraryfiles/{fileName}

## <a name="request-headers"></a>Encabezados de solicitud

| Nombre            | Tipo   | Descripción               |
|-----------------|--------|---------------------------|
| Authorization   | String | Portador\<token>\. Obligatorio. |

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

-   Si el archivo existe en la biblioteca y se eliminó correctamente 204 Sin contenido.

-   Si no se encontró el nombre de archivo especificado 404 No encontrado.

## <a name="example"></a>Ejemplo

Solicitud

Aquí tiene un ejemplo de la solicitud.

```HTTP
DELETE https://api.securitycenter.microsoft.com/api/libraryfiles/script1.ps1
```

## <a name="related-topic"></a>Tema relacionado
- [Ejecutar respuesta directa](run-live-response.md) 