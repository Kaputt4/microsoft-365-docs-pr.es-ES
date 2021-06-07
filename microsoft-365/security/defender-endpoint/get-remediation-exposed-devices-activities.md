---
title: Lista de dispositivos expuestos de una actividad de corrección
description: Devuelve información sobre los dispositivos expuestos para la tarea de corrección especificada.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation exposed devices
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9b10659f76e5b05bea11f5c6c55ca7c2a34a2db5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772166"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a>Lista de dispositivos expuestos de una actividad de corrección

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Devuelve información sobre los dispositivos expuestos para la tarea de corrección especificada.

[Obtenga más información sobre las actividades de corrección](tvm-remediation.md).

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a>Enumerar los dispositivos expuestos asociados con una tarea de corrección (id)

**DIRECCIÓN URL:** GET: /api/remediationTasks/ \{ id \} /machineReferences

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)

Tipo de permiso | Permiso | Nombre para mostrar de permisos
:---|:---|:---
Aplicación | RemediationTask.Read.All | \'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'
Delegado (cuenta profesional o educativa) | RemediationTask.Read.Read | \'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'

## <a name="properties-details"></a>Detalles de propiedades

Propiedad (id) | Tipo de datos | Descripción | Ejemplo
:---|:---|:---|:---
id | Cadena | Id. de dispositivo | w2957837fwda8w9ae7f023dba081059dw8d94503
computerDnsName | Cadena | Nombre del dispositivo | PC-SRV2012R2Foo.UserNameVldNet.local
osPlatform | Cadena | Sistema operativo del dispositivo | WindowsServer2012R2
rbacGroupName | Cadena | Nombre del grupo de dispositivos al que está asociado este dispositivo | Servidores

## <a name="example"></a>Ejemplo:

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

## <a name="see-also"></a>Consulte también

- [Propiedades y métodos de corrección](get-remediation-methods-properties.md)

- [Obtener una actividad de corrección por id.](get-remediation-one-activity.md)

- [Enumerar todas las actividades de corrección](get-remediation-all-activities.md)

- [Amenazas basadas en riesgos & administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilidades de la organización](tvm-weaknesses.md)
