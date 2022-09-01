---
title: Métodos y propiedades de evaluación de línea base de seguridad por dispositivo
description: Proporciona información sobre las API de líneas base de seguridad que extraen datos "Administración de vulnerabilidades de Microsoft Defender". Hay diferentes llamadas API para obtener diferentes tipos de datos. En general, cada llamada API contiene los datos necesarios para los dispositivos de la organización.
keywords: api, apis, export assessment, per device assessment, per machine assessment, vulnerability assessment report, device vulnerability assessment, device vulnerability report, secure configuration assessment, secure configuration report, software vulnerabilities assessment, software vulnerability report, vulnerability report by machine,
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: ffae67db503dba7cd23fc78d6180c2d003c28d30
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67520265"
---
# <a name="export-security-baselines-assessment-per-device"></a>Exportación de la evaluación de líneas base de seguridad por dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quieres experimentar Administración de vulnerabilidades de Microsoft Defender? Obtenga más información sobre cómo puede registrarse en la [versión de prueba de Administración de vulnerabilidades de Microsoft Defender versión preliminar pública](../defender-vulnerability-management/get-defender-vulnerability-management.md).

Hay diferentes llamadas API para obtener diferentes tipos de datos. En general, cada llamada API contiene los datos necesarios para los dispositivos de la organización.

- **Respuesta JSON**  La API extrae todos los datos de la organización como respuestas JSON. Este método es mejor para _organizaciones pequeñas con menos de 100 K dispositivos_. La respuesta está paginada, por lo que puede usar el \@campo odata.nextLink de la respuesta para capturar los resultados siguientes.

- **a través de archivos** Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Puede descargar datos de Azure Storage de la siguiente manera:
  - Llame a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.
  - Descargue todos los archivos mediante las direcciones URL de descarga y procese los datos como desee.

Los datos recopilados mediante "_respuesta JSON_ o _a través de archivos_" son la instantánea actual del estado actual. No contiene datos históricos. Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos.

> [!NOTE]
> A menos que se indique lo contrario, todos los métodos de evaluación de línea base de seguridad de exportación enumerados son **_exportación completa_** y **_por dispositivo_** (también **_denominados por dispositivo_**)

## <a name="1-export-security-baselines-assessment-json-response"></a>1. Exportación de la evaluación de líneas base de seguridad (respuesta JSON)

### <a name="11-api-method-description"></a>Descripción del método de API 1.1

Devuelve todas las evaluaciones de líneas base de seguridad para todos los dispositivos, por dispositivo. Devuelve una tabla con una entrada independiente para cada combinación única de DeviceId, ProfileId y ConfigurationId.

### <a name="12-permissions"></a>1.2 Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Microsoft Defender para punto de conexión API](apis-intro.md) para obtener más información.

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|SecurityBaselinesAssessment.Read.All |"Leer toda la información de las evaluaciones de líneas de base de seguridad"
Delegado (cuenta profesional o educativa)|SecurityBaselinesAssessment.Read|"Leer la información de las evaluaciones de líneas de base de seguridad"

### <a name="13-limitations"></a>1.3 Limitaciones

- El tamaño máximo de página es de 200 000.
- Las limitaciones de velocidad de esta API son 30 llamadas por minuto y 1000 llamadas por hora.

### <a name="14-parameters"></a>1.4 Parámetros

- pageSize (valor predeterminado = 50 000): número de resultados en respuesta.
- $top: número de resultados que se devolverán (no devuelve @odata.nextLink y, por lo tanto, no extrae todos los datos).

### <a name="15-http-request"></a>1.5 Solicitud HTTP

```http
GET /api/machines/baselineComplianceAssessmentByMachine
```

### <a name="16-properties-json-response"></a>Propiedades 1.6 (respuesta JSON)

> [!NOTE]
> Cada registro tiene aproximadamente 1 KB de datos. Debe tener esto en cuenta al elegir el parámetro pageSize correcto.
>
> Es posible que se devuelvan algunas columnas adicionales en la respuesta. Estas columnas son temporales y pueden quitarse. Use solo las columnas documentadas.
>
> Las propiedades definidas en la tabla siguiente se enumeran alfabéticamente por identificador de propiedad. Al ejecutar esta API, la salida resultante no se devolverá necesariamente en el mismo orden que se muestra en esta tabla.

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
|configurationId|Cadena|Identificador único de una configuración específica en el punto de referencia de línea base.
|profileId|Cadena|Identificador único para el perfil evaluado.
|deviceId|Cadena|Identificador único del dispositivo en el servicio.
|deviceName|Cadena|Nombre de dominio completo (FQDN) del dispositivo.
|isApplicable|Boolean|Indica si la configuración es aplicable a este dispositivo.
|isCompliant|Boolean|Indica si el dispositivo es compatible con la configuración.
|id|Cadena|Identificador único del registro, que es una combinación de DeviceId, ProfileId y ConfigurationId.
|osVersion|Cadena|Versión específica del sistema operativo que se ejecuta en el dispositivo.
|osPlatform|Cadena|Plataforma del sistema operativo que se ejecuta en el dispositivo. Sistemas operativos específicos con variaciones dentro de la misma familia, como Windows 10 y Windows 11. Consulte [Sistemas operativos y plataformas compatibles con MDVM](tvm-supported-os.md) para obtener más información.
|rbacGroupId|Int|Identificador del grupo de control de acceso basado en rol (RBAC). Si el dispositivo no está asignado a ningún grupo de RBAC, el valor será "Sin asignar". Si la organización no contiene ningún grupo de RBAC, el valor será "Ninguno".
|rbacGroupName|Cadena|El grupo de control de acceso basado en rol (RBAC). Si el dispositivo no está asignado a ningún grupo de RBAC, el valor será "Sin asignar". Si la organización no contiene ningún grupo de RBAC, el valor será "Ninguno".
|DataCollectionTimeOffset|DateTime|El momento en que se recopilaron los datos del dispositivo. Es posible que este campo no aparezca si no se recopilaron datos.
|ComplianceCalculationTimeOffset|DateTime|El momento en que se realizó el cálculo de la evaluación.
|RecommendedValue|Cadena|Conjunto de valores esperados para que la configuración actual del dispositivo sea reclamada.
|CurrentValue|Cadena|Conjunto de valores detectados que se encuentran en el dispositivo.
|Origen|String|La ruta de acceso del Registro u otra ubicación usada para determinar la configuración actual del dispositivo.

## <a name="17-example"></a>Ejemplo 1.7

### <a name="171-request-example"></a>1.7.1 Ejemplo de solicitud

```http
GET https://api.securitycenter.microsoft.com/api/machines/BaselineComplianceAssessmentByMachine
```

### <a name="172-response-example"></a>Ejemplo de respuesta 1.7.2

```json
{
"@odata.context": " https://api.securitycenter.microsoft.com /api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetBaselineAssessment)",
"value": [
{
    "id": "0000682575d5d473e82ed4d8680425d152411251_9e1b90be-e83e-485b-a5ec-4a429412e734_1.1.1",
    "configurationId": "1.1.1",
    "deviceId": "0000682575d5d473242222425d152411251",
    "deviceName": " ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596 ",
    "profileId": "9e1b90be-e83e-485b-a5ec-4a429412e734",
    "osPlatform": "WindowsServer2019",
    "osVersion": "10.0.17763.2330",
    "rbacGroupId": 86,
    "rbacGroupName": "UnassignedGroup",
    "isApplicable": true,
    "isCompliant": false,
    "dataCollectionTimeOffset": "2021-12-22T00:08:02.478Z",
    "recommendedValue": [
                    "Greater than or equal '24'"
                ],
                "currentValue": [
                    "24"
                ],
                "source": [
                    "password_hist_len"
                ],
}
```

## <a name="2-export-security-baselines-assessment-via-files"></a>2. Exportación de la evaluación de líneas base de seguridad (a través de archivos)

### <a name="21-api-method-description"></a>2.1 Descripción del método de API

Devuelve todas las evaluaciones de líneas base de seguridad para todos los dispositivos, por dispositivo. Devuelve una tabla con una entrada independiente para cada combinación única de DeviceId, ProfileId y ConfigurationId.

### <a name="22-limitations"></a>2.2 Limitaciones

- Las limitaciones de frecuencia de esta API son 5 llamadas por minuto y 20 llamadas por hora.

### <a name="23-url"></a>Dirección URL 2.3

```http
GET /api/machines/BaselineComplianceAssessmentExport
```

### <a name="24-parameters"></a>2.4 Parámetros

- sasValidHours: el número de horas durante las que serán válidas las direcciones URL de descarga (máximo 24 horas).

### <a name="25-properties-via-files"></a>2.5 Propiedades (a través de archivos)

> [!NOTE]
> Los archivos se comprimen gzip & en formato Json multilínea.
>
>Las direcciones URL de descarga solo son válidas durante 3 horas; De lo contrario, puede usar el parámetro .
>
>Para maximizar las velocidades de descarga, asegúrese de que está descargando los datos de la misma región de Azure donde residen los datos.
>
>Cada registro tiene aproximadamente 1 KB de datos. Debe tener esto en cuenta al elegir el parámetro pageSize que funciona automáticamente.
>
>Es posible que se devuelvan algunas columnas adicionales en la respuesta. Estas columnas son temporales y pueden quitarse. Use solo las columnas documentadas.

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
|Exportación de archivos|array[string]|Una lista de direcciones URL de descarga para los archivos que contienen la instantánea actual de la organización.
|GeneratedTime|Cadena|Hora en que se generó la exportación.

## <a name="26-example"></a>Ejemplo 2.6

### <a name="261-request-example"></a>2.6.1 Ejemplo de solicitud

```http
GET https://api.securitycenter.microsoft.com/api/machines/BaselineComplianceAssessmentExport
```

### <a name="262-response-example"></a>Ejemplo de respuesta 2.6.2

```json
{
    "@odata.context": "https://api.securitycenter. contoso.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": 
    [
    "https://tvmexportexternalstgeus.blob.core.windows.net/temp-1ebd3d09-d06a-4aad-ab80-ebc536cec61c/2021-12-22/0500/BaselineAssessmentExport/json/OrgId= OrgId=<Org Id>/_RbacGroupId=<Rbac Group Id>/part-00000-c09dfd00-2278-4735-b23a-71733751fcbc.c000.json.gz?sv=ABCD",
   "https://tvmexportexternalstgeus.blob.core.windows.net/temp-1ebd3d09-d06a-4aad-ab80-ebc536cec61c/2021-12-22/0500/BaselineAssessmentExport/json/OrgId=<Org Id>/_RbacGroupId=<Rbac Group Id>/part-00001-c09dfd00-2278-4735-b23a-71733751fcbc.c000.json.gz?sv= ABCD",
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Vea también

- [Obtención de perfiles de evaluación de líneas de base de seguridad](get-security-baselines-assessment-profiles.md)
- [Obtención de configuraciones de evaluación de líneas de base de seguridad](get-security-baselines-assessment-configurations.md)
