---
title: Enumerar dispositivos por software
description: Recupera una lista de dispositivos que tienen instalado este software.
keywords: apis, api de gráficos, api admitidas, get, dispositivos de lista, lista de dispositivos, lista de dispositivos por software, Api de Microsoft Defender para Endpoint tvm
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 84cb368d1b54e953932741b2610e435ddc8b7045868b8dd3de2f2cc7d46661bc
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53793789"
---
# <a name="list-devices-by-software"></a>Enumerar dispositivos por software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Recupera una lista de referencias de dispositivo que tiene instalado este software.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.

Tipo de permiso|Permiso|Nombre para mostrar de permisos
:---|:---|:---
Aplicación|Software.Read.All|'Leer información de software de administración de amenazas y vulnerabilidades'
Delegado (cuenta profesional o educativa)|Software.Read|'Leer información de software de administración de amenazas y vulnerabilidades'

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a>Encabezados de solicitud

|Nombre|Tipo|Descripción
|---|---|---|
|Authorization|String|Portador {token}. **Obligatorio**.

## <a name="request-body"></a>Cuerpo de la solicitud

En blanco

## <a name="response"></a>Respuesta

Si se realiza correctamente, este método devuelve 200 OK y una lista de dispositivos con el software instalado en el cuerpo. 

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

Aquí tiene un ejemplo de la solicitud.

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

### <a name="response-example"></a>Ejemplo de respuesta

Aquí tiene un ejemplo de la respuesta.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Temas relacionados

- [Administración de vulnerabilidades basada & riesgos](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Inventario & de software de vulnerabilidad](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
