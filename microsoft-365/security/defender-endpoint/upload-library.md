---
title: Upload archivos a la biblioteca de respuestas dinámicas
description: Obtenga información sobre cómo cargar un archivo en la biblioteca de respuestas dinámicas.
keywords: api, graph api, api admitidas, carga en la biblioteca
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
ms.openlocfilehash: 8e0bc9ca78a7e0baad7c07e73790215618aff9ab
ms.sourcegitcommit: 35f167725bec5fd4fe131781a53d96b060cf232d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "65873747"
---
#  <a name="upload-files-to-the-live-response-library"></a>Upload archivos a la biblioteca de respuestas dinámicas  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

[!include[Prerelease information](../../includes/prerelease.md)]

>¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Upload biblioteca de respuesta en vivo.

## <a name="limitations"></a>Limitaciones

1.  La limitación de tamaño máximo de archivo es de 20 MB.

2.  Las limitaciones de velocidad de esta API son 100 llamadas por minuto y 1500 llamadas por hora.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Comenzar](apis-intro.md).


| Tipo de permiso                    | Permiso     | Nombre para mostrar del permiso        |
|------------------------------------|----------------|--------------------------------|
| Aplicación                        | Library.Manage | Administración de la biblioteca de respuestas dinámicas |
| Delegado (cuenta profesional o educativa) | Library.Manage | Administración de la biblioteca de respuestas dinámicas |

## <a name="http-request"></a>Solicitud HTTP

Cargar

```HTTP
POST https://api.securitycenter.microsoft.com/api/libraryfiles
```

## <a name="request-headers"></a>Encabezados de solicitud

|  Nombre   |    Tipo    |       Descripción                         |
|-----------------|--------|--------------------------------|
| Authorization   | String | \<token>Portador. Obligatorio.      |
| Content-Type    | string | multipart/form-data. Obligatorio. |

## <a name="request-body"></a>Cuerpo de la solicitud

En el cuerpo de la solicitud, proporcione un objeto form-data con los parámetros siguientes:

| Parameter         |     Tipo         |       Descripción                                        |
|-----------------------|--------------|------------------------------------------------------------|
| Archivo                  | Contenido del archivo | Archivo que se va a cargar en la biblioteca de respuesta activa. Obligatorio |
| Descripción           | String       | Descripción del archivo.                                  |
| ParametersDescription | String       | (Opcional) Parámetros necesarios para que se ejecute el script. El valor predeterminado es una cadena vacía.                |
| OverrideIfExists      | Booleano      | (Opcional) Si se va a invalidar el archivo si ya existe. El valor predeterminado es una cadena vacía.          |



## <a name="response"></a>Respuesta

-   Si se ejecuta correctamente, este método devuelve el código de respuesta 200 - Ok y la entidad de biblioteca de respuestas en directo cargada en el cuerpo de la respuesta.

-   Si no se ejecuta correctamente: este método devuelve 400 - Solicitud incorrecta.  
    La solicitud incorrecta suele indicar un cuerpo incorrecto.

## <a name="example"></a>Ejemplo

Solicitud

Este es un ejemplo de la solicitud mediante curl.

```CURL
curl -X POST https://api.securitycenter.microsoft.com/api/libraryfiles -H
"Authorization: Bearer \$token" -F "file=\@mdatp1.png" -F
"ParametersDescription=test"  
-F "HasParameters=true" -F "OverrideIfExists=true" -F "Description=test
description"
```

## <a name="related-topic"></a>Tema relacionado

-  [Ejecutar respuesta directa](run-live-response.md) 