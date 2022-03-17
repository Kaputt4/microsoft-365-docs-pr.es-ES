---
title: Eliminar un archivo de la biblioteca de respuestas en directo
description: Obtenga información sobre cómo eliminar un archivo de la biblioteca de respuestas en directo.
keywords: apis, api de gráficos, api admitidas, eliminación de la biblioteca
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
ms.openlocfilehash: 23625c8b7160d604df5f3a8b1b1387fc31027acf
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526819"
---
#  <a name="delete-a-file-from-the-live-response-library"></a>Eliminar un archivo de la biblioteca de respuestas en directo  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Elimine un archivo de la biblioteca de respuestas en directo.

## <a name="limitations"></a>Limitaciones

1.  Las limitaciones de velocidad para esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Introducción](apis-intro.md).

| Tipo de permiso                    | Permiso     | Nombre para mostrar de permisos        |
|------------------------------------|----------------|--------------------------------|
| Aplicación                        | Library.Manage | Administrar biblioteca de respuestas en directo |
| Delegado (cuenta profesional o educativa) | Library.Manage | Administrar biblioteca de respuestas en directo |

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

-   Si no se encontró el nombre de archivo especificado, no se encontró 404.

## <a name="example"></a>Ejemplo

Solicitud

Aquí tiene un ejemplo de la solicitud.

```HTTP
DELETE https://api.securitycenter.microsoft.com/api/libraryfiles/script1.ps1
```

## <a name="related-topic"></a>Tema relacionado
- [Ejecutar respuesta directa](run-live-response.md) 