---
title: Obtener una actividad de corrección de acuerdo con su id
description: Devuelve información sobre la actividad de corrección especificada.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation by ID,
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 6ea413621ad9d2e3b99fc5abdafd843705e7dc87
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2022
ms.locfileid: "62073395"
---
# <a name="get-one-remediation-activity-by-id"></a>Obtener una actividad de corrección de acuerdo con su id

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Prerelease information](../../includes/prerelease.md)]

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Devuelve información sobre la actividad de corrección especificada. Presenta las mismas columnas que [Obtener toda](get-remediation-all-activities.md)la actividad de corrección ", pero devuelve resultados solo para la actividad _de corrección especificada_.

[Obtenga más información sobre las actividades de corrección](tvm-remediation.md).

## <a name="list-a-specified-remediation-activity-for-id"></a>Enumerar una actividad de corrección especificada para (ID)

**DIRECCIÓN URL:** GET: /api/remediationTasks/ \{ id\}

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar de permisos
:---|:---|:---
Aplicación|RemediationTasks.Read.All|\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'
Delegado (cuenta profesional o educativa)|RemediationTask.Read.Read|\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'

## <a name="properties"></a>Propiedades

Propiedad (ID)|Tipo de datos|Descripción|Ejemplo de un valor devuelto
:---|:---|:---|:---
Categoría|Cadena|Categoría de la actividad de corrección (configuración software/seguridad)|Software
completerEmail|Cadena|Si alguien completó manualmente la actividad de corrección, esta columna contiene su correo electrónico|Null
completerId|String|Si alguien completó manualmente la actividad de corrección, esta columna contiene su identificador de objeto.|Null
completionMethod|Cadena|Una actividad de corrección se puede completar "automáticamente" (si todos los dispositivos están parcheados) o "manualmente" por una persona que selecciona "marcar como completada"|Automático
createdOn|DateTime|Hora en que se creó esta actividad de corrección|2021-01-12T18:54:11.5499478Z
Descripción|Cadena|Descripción de esta actividad de corrección|Actualiza Microsoft Silverlight a una versión posterior para mitigar las vulnerabilidades conocidas que afectan a los dispositivos.
dueOn|DateTime|Fecha de vencimiento que el creador estableció para esta actividad de corrección|2021-01-13T00:00:00Z
fixedDevices||Número de dispositivos que se han corregido|2
Id.|String|Identificador de esta actividad de corrección|097d9735-5479-4899-b1b7-77398899df92
nameId|String|Nombre del producto relacionado|Microsoft Silverlight
Prioridad|String|Prioridad del conjunto de creadores para esta actividad de corrección (High\Medium\Low)|Alto
productId|String|Id. de producto relacionado|microsoft-_-silverlight
productivityImpactRemediationType|String|Solo se podrían solicitar algunos cambios de configuración para dispositivos que no afecten a los usuarios. Este valor indica la selección entre "todos los dispositivos expuestos" o "solo dispositivos sin impacto del usuario".|AllExposedAssets
rbacGroupNames|String|Nombres de grupo de dispositivos relacionados|[ "Windows servidores", "Windows 11", "Windows 10" ]
recommendedProgram|String|Programa recomendado para actualizar a|Null
recommendedVendor|Cadena|Proveedor recomendado para actualizar a|Null
recommendedVersion|Cadena|Versión recomendada para actualizar o actualizar a|Null
relatedComponent|Cadena|Componente relacionado de esta actividad de corrección (similar al componente relacionado para una recomendación de seguridad)|Microsoft Silverlight
requesterEmail|Cadena|Dirección de correo electrónico del creador|globaladmin@UserName.contoso.com
requesterId|Cadena|Id. de objeto Creator|r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes|Cadena|Las notas (texto libre) que el creador agregó para esta actividad de corrección|Null
Scid|Cadena|SCID de la recomendación de seguridad relacionada|Null
Estado|Cadena|Estado de la actividad de corrección (Activo/Completado)|Activo
statusLastModifiedOn|DateTime|Fecha en la que se actualizó el campo de estado|2021-01-12T18:54:11.5499487Z
targetDevices|Long|Número de dispositivos expuestos a los que se aplica esta corrección|43
Título|Cadena|Título de esta actividad de corrección|Microsoft Silverlight
Tipo|Cadena|Tipo de corrección|Actualizar
vendorId|Cadena|Nombre de proveedor relacionado|Microsoft

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a>Ejemplo de respuesta

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity",
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c",
    "title": "Update Microsoft Silverlight",
    "createdOn": "2021-02-10T13:20:36.4718166Z",
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4",
    "requesterEmail": "user1@contoso.com",
    "status": "Active",
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.",
    "relatedComponent": "Microsoft Silverlight",
    "targetDevices": 18511,
    "rbacGroupNames": [
        "UnassignedGroup",
        "hhh"
    ],
    "fixedDevices": 2866,
    "requesterNotes": "test",
    "dueOn": "2021-02-11T00:00:00Z",
    "category": "Software",
    "productivityImpactRemediationType": null,
    "priority": "Medium",
    "completionMethod": null,
    "completerId": null,
    "completerEmail": null,
    "scid": null,
    "type": "Update",
    "productId": "microsoft-_-silverlight",
    "vendorId": "microsoft",
    "nameId": "silverlight",
    "recommendedVersion": null,
    "recommendedVendor": null,
    "recommendedProgram": null
}
```

## <a name="see-also"></a>Consulte también

- [Propiedades y métodos de corrección](get-remediation-methods-properties.md)
- [Enumerar todas las actividades de corrección](get-remediation-all-activities.md)
- [Lista de dispositivos expuestos de una actividad de corrección](get-remediation-exposed-devices-activities.md)
- [Amenazas basadas en riesgos & administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Vulnerabilidades de la organización](tvm-weaknesses.md)
