---
title: API de detalles del estado del dispositivo antivirus de Microsoft Defender
description: Recupera una lista de detalles de estado del dispositivo antivirus de Microsoft Defender.
keywords: apis, graph api, api admitidas, get, device health api, Microsoft Defender para punto de conexión api report api microsoft defender reports api, microsoft defender for endpoint reporting api, windows defender reporting api, defender for endpoint reporting api, windows defender reporting api, windows defender reporting api, windows defender report api
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
ms.date: 08/08/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: 6907852501ac78784a3a642851c62cfeb2a065ac
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67520366"
---
# <a name="microsoft-defender-antivirus-device-health-details-api"></a>API de detalles del estado del dispositivo antivirus de Microsoft Defender

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="api-description"></a>Descripción de la API

Recupera una lista de detalles de estado del dispositivo antivirus de Microsoft Defender.
DIRECCIÓN URL: GET: /api/public/avdeviceshealth
<br>Admite [consultas de OData V4](https://www.odata.org/documentation/).
<br>Operadores compatibles con OData:
<br>```$filter```on: ```machineId```, ```computerDnsName```, ```osKind```, , ```osPlatform```, ```osVersion```, a```vMode```, ```avSignatureVersion```, ```avEngineVersion```, ```avPlatformVersion```, ```quickScanResult```, ```quickScanError```, , ```fullScanResult``````fullScanError```, ```avIsSignatureUpToDate```, ```avIsEngineUpToDate```, , , ```vIsPlatformUpToDate``````rbacGroupId```
<br>```$top``` con un valor máximo de 10 000.
<br>```$skip```.
<br>Vea ejemplos en [Consultas de OData con Microsoft Defender para punto de conexión.] (exposed-apis-odata-samples.md]

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Microsoft Defender para punto de conexión API](apis-intro.md) para obtener más información.

| Tipo de permiso | Permiso | Nombre para mostrar del permiso |
|:----|:----|:----|
| Application | Machine.Read.All | "Leer todos los perfiles de máquina" |
| Application | Machine.ReadWrite.All | "Leer y escribir toda la información de la máquina" |
| Delegado (cuenta profesional o educativa) | Machine.Read | "Leer información de la máquina" |
| Delegado (cuenta profesional o educativa) | Macine.ReadWrite | "Leer y escribir información de la máquina" |

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/public/avdeviceshealth
```

## <a name="request-headers"></a>Encabezados de solicitud

| Nombre | Tipo | Descripción |
|:----|:----|:----|
| Authorization | Cadena | Portador {token}. **Required** |

## <a name="request-body"></a>Cuerpo de la solicitud

_Empty_

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 200 OK con una lista de detalles de estado del dispositivo.

## <a name="example"></a>Ejemplo

### <a name="example-request"></a>Ejemplo de solicitud

Este es un ejemplo de la solicitud:

```http
GET https://api.securitycenter.microsoft.com/api/public/avdeviceshealth 
```

### <a name="example-response"></a>Ejemplo de respuesta

Este es un ejemplo de la respuesta:

```json
{ 

    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#avdeviceshealth", 

    "value": [ 

        { 

           "id": "sampleId", 

           "machineId": "sampleMachineId", 

           "computerDnsName": "sampleDnsName", 

           "osKind": "mac", 

           "osPlatform": "macOS", 

           "osVersion": "11.6.5.0", 

           "avMode": "0", 

           "avSignatureVersion": "87523", 

           "avEngineVersion": "3.0", 

           "avPlatformVersion": "101.61.69", 

           "lastSeenTime": "2022-04-02T06:12:07+00:00", 

           "quickScanResult": "-", 

           "quickScanError": "-", 

           "fullScanResult": "-", 

           "fullScanError": "-", 

           "dataRefreshTimestamp": "2022-04-06T21:50:48+00:00", 

           "avSignatureUpdateTime": "2022-04-01T01:31:58+00:00", 

           "avIsSignatureUpToDate": "Unknown", 

           "avIsEngineUpToDate": "Unknown", 

           "avIsPlatformUpToDate": "Unknown", 

           "rbacGroupId": 86 

        }, 

        ... 

     ] 

}  
```

## <a name="see-also"></a>Vea también

[Informe de estado y cumplimiento del dispositivo en Microsoft Defender para punto de conexión](machine-reports.md)
