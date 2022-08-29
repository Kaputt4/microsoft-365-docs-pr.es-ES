---
title: Enumerar dispositivos por software
description: Recupere una lista de dispositivos que tengan instalado este software.
keywords: apis, graph api, api admitidas, get, list devices, devices list, list devices by software, Microsoft Defender para punto de conexión tvm api
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: fba7fc216f126a9b6f166fe0287a75f5a3b38214
ms.sourcegitcommit: 48a75b40e607542e5fe219b6e75ffc757804a9c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "67345105"
---
# <a name="list-devices-by-software"></a>Enumerar dispositivos por software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

>¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Recupere una lista de referencias de dispositivo que tenga instalado este software.

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Microsoft Defender para punto de conexión API](apis-intro.md) para obtener más información.

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Software.Read.All|"Leer la información del software de administración de amenazas y vulnerabilidades"
Delegado (cuenta profesional o educativa)|Software.Read|"Leer la información del software de administración de amenazas y vulnerabilidades"

## <a name="http-request"></a>Solicitud HTTP

```http
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a>Encabezados de solicitud

|Nombre|Tipo|Descripción
|---|---|---|
|Authorization|Cadena|Portador {token}. **Obligatorio**.

## <a name="request-body"></a>Cuerpo de solicitud

En blanco

## <a name="response"></a>Respuesta

Si se ejecuta correctamente, este método devuelve 200 OK y una lista de dispositivos con el software instalado en el cuerpo. 

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
            "osPlatform": "Windows10" "Windows11",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10" "Windows11",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Temas relacionados

- [Administración de vulnerabilidades de Microsoft Defender](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Inventario de software de Administración de vulnerabilidades de Defender](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
