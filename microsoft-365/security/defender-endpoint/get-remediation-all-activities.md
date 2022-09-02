---
title: Enumerar todas las actividades de corrección
description: Devuelve información sobre todas las actividades de corrección.
keywords: API, corrección, API de corrección, obtención, tareas de corrección, toda la corrección,
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
ms.openlocfilehash: a7283db5041c8d4aabee406676e3c61e1d2f4385
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67523872"
---
# <a name="list-all-remediation-activities"></a>Enumerar todas las actividades de corrección

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una evaluación gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> ¿Quieres experimentar Administración de vulnerabilidades de Microsoft Defender? Obtenga más información sobre cómo puede registrarse en la [versión de prueba de Administración de vulnerabilidades de Microsoft Defender versión preliminar pública](../defender-vulnerability-management/get-defender-vulnerability-management.md).

[!Include[Prerelease information](../../includes/prerelease.md)]

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descripción de la API

Devuelve información sobre todas las actividades de corrección.

[Obtenga más información sobre las actividades de corrección](tvm-remediation.md).

**URL:** GET: /api/remediationTasks
<br>Admite [consultas de OData V4](https://www.odata.org/documentation/).
<br>Operadores compatibles con OData:
<br>```$filter``` on:  ```createdon``` y ```status``` propiedades.
<br>```$top``` con un valor máximo de 10 000.
<br>```$skip```.
<br>Vea ejemplos en [consultas de OData con Microsoft Defender para punto de conexión](exposed-apis-odata-samples.md).

## <a name="permissions"></a>Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Microsoft Defender para punto de conexión API para obtener más información.](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|RemediationTasks.Read.All|\'Lee la información de vulnerabilidades de Administración de amenazas y vulnerabilidades.\'
Delegado (cuenta profesional o educativa)|RemediationTask.Read|\'Lee la información de vulnerabilidades de Administración de amenazas y vulnerabilidades.\'

## <a name="properties"></a>Propiedades

Propiedad (ID)|Tipo de datos|Descripción|Ejemplo de un valor devuelto
:---|:---|:---|:---
Categoría|Cadena|Categoría de la actividad de corrección (configuración de software/seguridad)|Software
completerEmail|Cadena|Si alguien completó manualmente la actividad de corrección, esta columna contiene su correo electrónico.|Null
completerId|Cadena|Si alguien completó manualmente la actividad de corrección, esta columna contiene su identificador de objeto.|Null
completionMethod|Cadena|Una actividad de corrección se puede completar "automáticamente" (si todos los dispositivos están revisados) o "manualmente" por una persona que selecciona "marcar como completado"|Automático
createdOn|DateTime|Hora en que se creó esta actividad de corrección|2021-01-12T18:54:11.5499478Z
Descripción|Cadena|Descripción de esta actividad de corrección|Actualice Microsoft Silverlight a una versión posterior para mitigar las vulnerabilidades conocidas que afectan a los dispositivos.
dueOn|DateTime|Fecha de vencimiento establecida por el creador para esta actividad de corrección|2021-01-13T00:00:00Z
fixedDevices|.|Número de dispositivos que se han corregido|2
Id.|Cadena|Identificador de esta actividad de corrección|097d9735-5479-4899-b1b7-77398899df92
nameId|Cadena|Nombre del producto relacionado|Microsoft Silverlight
Prioridad|Cadena|Prioridad del creador establecido para esta actividad de corrección (Alto\Medio\Bajo)|Alto
Productid|Cadena|Identificador de producto relacionado|microsoft-_-silverlight
productivityImpactRemediationType|Cadena|Solo se pueden solicitar algunos cambios de configuración para los dispositivos que no afectan a los usuarios. Este valor indica la selección entre "todos los dispositivos expuestos" o "solo los dispositivos sin ningún impacto en el usuario".|AllExposedAssets
rbacGroupNames|Cadena|Nombres de grupos de dispositivos relacionados|[ "Servidores Windows", "Windows 11", "Windows 10" ]
recommendedProgram|Cadena|Programa recomendado para actualizar a|Null
recommendedVendor|Cadena|Proveedor recomendado para actualizar a|Null
recommendedVersion|Cadena|Versión recomendada para actualizar o actualizar a|Null
relatedComponent|Cadena|Componente relacionado de esta actividad de corrección (similar al componente relacionado para una recomendación de seguridad)|Microsoft Silverlight
requesterEmail|Cadena|Dirección de correo electrónico de Creator|globaladmin@UserName.contoso.com
requesterId|Cadena|Identificador de objeto de Creator|r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes|Cadena|Las notas (texto libre) que el creador agregó para esta actividad de corrección|Null
Scid|Cadena|SCID de la recomendación de seguridad relacionada|Null
Estado|Cadena|Estado de la actividad de corrección (activo/completado)|Activo
statusLastModifiedOn|DateTime|Fecha en que se actualizó el campo de estado|2021-01-12T18:54:11.5499487Z
targetDevices|Long|Número de dispositivos expuestos a los que se aplica esta corrección|43
Título|Cadena|Título de esta actividad de corrección|Actualización de Microsoft Silverlight
Tipo|Cadena|Tipo de corrección|Actualizar
vendorId|Cadena|Nombre del proveedor relacionado|Microsoft

## <a name="example"></a>Ejemplo

### <a name="request-example"></a>Ejemplo de solicitud

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a>Ejemplo de respuesta

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.",
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
    ]
}
```

## <a name="see-also"></a>Vea también

- [Métodos y propiedades de corrección](get-remediation-methods-properties.md)
- [Obtener una actividad de corrección de acuerdo con su id](get-remediation-one-activity.md)
- [Lista de dispositivos expuestos de una actividad de corrección](get-remediation-exposed-devices-activities.md)
- [Administración de vulnerabilidades de Microsoft Defender](next-gen-threat-and-vuln-mgt.md)
- [Vulnerabilidades en la organización](tvm-weaknesses.md)
