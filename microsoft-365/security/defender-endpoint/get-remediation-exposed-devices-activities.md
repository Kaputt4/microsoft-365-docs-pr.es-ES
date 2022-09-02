---
title: Lista de dispositivos expuestos de una actividad de corrección
description: Devuelve información sobre los dispositivos expuestos para la tarea de corrección especificada.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation exposed devices
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: e4d006f49575cac26d08485c3ff47d6213ab36ad
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67522221"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a>Lista de dispositivos expuestos de una actividad de corrección

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Devuelve información sobre los dispositivos expuestos para la tarea de corrección especificada.

[Obtenga más información sobre las actividades de corrección](tvm-remediation.md).

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a>Enumerar los dispositivos expuestos asociados a una tarea de corrección (id)

**URL:** GET: /api/remediationTasks/\{id\}/machineReferences

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Microsoft Defender para punto de conexión API para obtener más información.](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|RemediationTasks.Read.All|\'Lee la información de vulnerabilidades de Administración de amenazas y vulnerabilidades.\'
Delegado (cuenta profesional o educativa)|RemediationTask.Read.Read|\'Lee la información de vulnerabilidades de Administración de amenazas y vulnerabilidades.\'

## <a name="properties-details"></a>Detalles de propiedades

Propiedad (id)|Tipo de datos|Descripción|Ejemplo
:---|:---|:---|:---
id|Cadena|Id. de dispositivo|w2957837fwda8w9ae7f023dba081059dw8d94503
computerDnsName|Cadena|Nombre del dispositivo|PC-SRV2012R2Foo.UserNameVldNet.local
osPlatform|Cadena|Sistema operativo del dispositivo|WindowsServer2012R2
rbacGroupName|Cadena|Nombre del grupo de dispositivos al que está asociado este dispositivo|Servidores

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a>Ejemplo de respuesta

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "3cb5df6bb3640a2d37ad09fcd357b182d684fafc",
            "computerDnsName": "ComputerPII_2ea21b2d97c9df23c143ad9e3e454cb674232529.DomainPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",

        },
        {
            "id": "3d9b1ca53e8f077199c7dcbfc9dbfa78f9bf1918",
            "computerDnsName": "ComputerPII_001d606fc149567c192747f48fae304b43c0ddba.DomainxPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",

        },
        {
            "id": "3db8b27e6172951d7ea2e2d75945abec56feaf82",
            "computerDnsName": "ComputerPII_ce60cfbjj4b82a091deb5eae560332bba99a9bd7.DomainPII_0bc1aee0fa396d175e514bd61a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",

        },
        {
            "id": "3bad326dcda5b53fab47408cd4a7080f3f3cc8ab",
            "computerDnsName": "ComputerPII_b6b35960dd6539d1d1cef5ada02e235e7b357408.DomainPII_21eed80b089e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",

        }
]
}
```

## <a name="see-also"></a>Vea también

- [Métodos y propiedades de corrección](get-remediation-methods-properties.md)
- [Obtener una actividad de corrección por id.](get-remediation-one-activity.md)
- [Enumerar todas las actividades de corrección](get-remediation-all-activities.md)
- [Administración de vulnerabilidades de Microsoft Defender](next-gen-threat-and-vuln-mgt.md)
- [Vulnerabilidades en la organización](tvm-weaknesses.md)
