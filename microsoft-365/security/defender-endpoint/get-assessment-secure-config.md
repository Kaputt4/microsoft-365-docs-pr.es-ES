---
title: Exportar evaluación de configuración segura por dispositivo
description: Devuelve una entrada para cada combinación única de DeviceId, ConfigurationId.
keywords: api, apis, evaluación de exportación, evaluación por dispositivo, informe de evaluación de vulnerabilidad, evaluación de vulnerabilidad de dispositivo, informe de vulnerabilidad de dispositivo, evaluación de configuración segura, informe de configuración segura, evaluación de vulnerabilidades de software, informe de vulnerabilidades de software, informe de vulnerabilidad por máquina,
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: ad8b2030da4fb4815eb71ca53fb2dbac67a05d79
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022395"
---
# <a name="export-secure-configuration-assessment-per-device"></a>Exportar evaluación de configuración segura por dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
Devuelve todas las configuraciones y su estado, por dispositivo.

Hay diferentes llamadas API para obtener diferentes tipos de datos. Dado que la cantidad de datos puede ser grande, hay dos formas de recuperarlos:

- [Exportar respuesta **JSON** de evaluación de](#1-export-secure-configuration-assessment-json-response)configuración segura: la API extrae todos los datos de la organización como respuestas Json. Este método es el mejor para organizaciones pequeñas con dispositivos de menos de _100 K._ La respuesta se pagina, por lo que puede usar el campo odata.nextLink de la respuesta \@ para obtener los siguientes resultados.

- [Exportar la evaluación de configuración **segura a través**](#2-export-secure-configuration-assessment-via-files)de archivos: esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Almacenamiento de Azure. Esta API le permite descargar todos los datos de Almacenamiento de Azure de la siguiente manera:

  - Llama a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.

  - Descargue todos los archivos con las direcciones URL de descarga y procese los datos como quiera.

Los datos recopilados (mediante _OData_ o a través de _archivos)_ son la instantánea actual del estado actual y no contienen datos históricos. Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos.

> [!Note]
>
> A menos que se indique lo **** contrario, todos los métodos de evaluación de exportación enumerados son exportación completa y por **_dispositivo_** (también **_denominados por dispositivo_**).

## <a name="1-export-secure-configuration-assessment-json-response"></a>1. Exportar evaluación de configuración segura (respuesta JSON)

### <a name="11-api-method-description"></a>Descripción del método de api 1.1

Esta respuesta de la API contiene la evaluación de configuración segura en los dispositivos expuestos y devuelve una entrada para cada combinación única de DeviceId, ConfigurationId.

#### <a name="111-limitations"></a>1.1.1 Limitaciones

- El tamaño máximo de página es 200 000.

- Las limitaciones de velocidad para esta API son 30 llamadas por minuto y 1000 llamadas por hora.

### <a name="12-permissions"></a>1.2 Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md) para obtener más información.

Tipo de permiso | Permiso | Nombre para mostrar de permisos
---|---|---
Aplicación | Vulnerability.Read.All | \'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'
Delegado (cuenta profesional o educativa) | Vulnerability.Read | \'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'

### <a name="13-url"></a>DIRECCIÓN URL 1.3

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a>1.4 Parámetros

- pageSize \( predeterminado = 50.000: \) número de resultados en la respuesta

- \$top: el número de resultados que se devolverán no \( devuelve odata.nextLink y, por lo tanto, \@ no extrae todos los datos\)

### <a name="15-properties"></a>1.5 Propiedades

>[!Note]
>
>- Las propiedades definidas en la tabla siguiente se enumeran alfabéticamente, por identificador de propiedad.  Al ejecutar esta API, el resultado resultante no se devolverá necesariamente en el mismo orden enumerado en esta tabla.
>
>- Es posible que se devuelvan algunas columnas adicionales en la respuesta. Estas columnas son temporales y pueden quitarse, use solo las columnas documentadas.
>

Propiedad (ID) | Tipo de datos | Description | Ejemplo de un valor devuelto
:---|:---|:---|:---
ConfigurationCategory | string | Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad | Controles de seguridad
ConfigurationId | string | Identificador único para una configuración específica | scid-10000
ConfigurationImpact | string | Impacto valorado de la configuración en el resultado general de la configuración (1-10) | 9 
ConfigurationName | string | Nombre para mostrar de la configuración | Incorporar dispositivos a Microsoft Defender para punto de conexión
ConfigurationSubcategory | string | Subcategoría o subagrupación a la que pertenece la configuración. En muchos casos, describe funciones o características específicas. | Dispositivos integrados
DeviceId | string | Identificador único del dispositivo en el servicio. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | string | Nombre de dominio completo (FQDN) del dispositivo. | johnlaptop.europe.contoso.com
IsApplicable | bool | Indica si la configuración o directiva es aplicable | true
IsCompliant | bool | Indica si la configuración o la directiva está configurada correctamente | false
IsExpectedUserImpact | bool | Indica si habrá impacto del usuario si se aplicará la configuración | true
OSPlatform | string | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7. Consulta sistemas operativos y plataformas compatibles con tvm para obtener más información. | Windows10
RbacGroupName | string | Grupo de control de acceso basado en roles (RBAC). Si este dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned". Si la organización no contiene ningún grupo RBAC, el valor será "None". | Servidores
RecommendationReference | string | Una referencia al identificador de recomendación relacionado con este software. | sca-_-scid-20000
Timestamp | string | La última vez que se vio la configuración en el dispositivo | 2020-11-03 10:13:34.8476880

### <a name="16-examples"></a>1.6 Ejemplos

#### <a name="161-request-example"></a>1.6.1 Ejemplo de solicitud

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a>Ejemplo de respuesta 1.6.2

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a>2. Exportar evaluación de configuración segura (a través de archivos)

### <a name="21-api-method-description"></a>Descripción del método api 2.1

Esta respuesta de la API contiene la evaluación de configuración segura en los dispositivos expuestos y devuelve una entrada para cada combinación única de DeviceId, ConfigurationId.

#### <a name="212-limitations"></a>2.1.2 Limitaciones

Las limitaciones de velocidad para esta API son 5 llamadas por minuto y 20 llamadas por hora.

### <a name="22-permissions"></a>2.2 Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)

Tipo de permiso | Permiso | Nombre para mostrar de permisos
---|---|---
Aplicación | Vulnerability.Read.All | \'Leer la información Administración de amenazas y vulnerabilidades vulnerabilidad de "Administración de amenazas y vulnerabilidades"\'
Delegado (cuenta profesional o educativa) | Vulnerability.Read | \'Leer la información Administración de amenazas y vulnerabilidades vulnerabilidad de "Administración de amenazas y vulnerabilidades"\'

### <a name="23-url"></a>DIRECCIÓN URL 2.3

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a>Parameters

- sasValidHours: el número de horas durante las que las direcciones URL de descarga serán válidas (máximo 24 horas).

### <a name="25-properties"></a>2.5 Propiedades

>[!Note]
>
>- Los archivos son archivos comprimidos de gzip & en formato Json de varias líneas.
>
>- Las direcciones URL de descarga solo son válidas durante 3 horas; de lo contrario, puede usar el parámetro.
>
>- Para obtener la velocidad máxima de descarga de los datos, puede asegurarse de que está descargando desde la misma región de Azure en la que residen los datos.
>
Propiedad (ID) | Tipo de datos | Description | Ejemplo de un valor devuelto
:---|:---|:---|:---
Exportar archivos | cadena de \[ matriz\] | Una lista de direcciones URL de descarga de archivos que contiene la instantánea actual de la organización | [  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]
GeneratedTime | string | Hora en que se generó la exportación. | 2021-05-20T08:00:00Z ]

### <a name="26-examples"></a>2.6 Ejemplos

#### <a name="261-request-example"></a>2.6.1 Ejemplo de solicitud

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a>Ejemplo de respuesta 2.6.2

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Vea también

- [Exportar métodos de evaluación y propiedades por dispositivo](get-assessment-methods-properties.md)

- [Exportar evaluación de inventario de software por dispositivo](get-assessment-software-inventory.md)

- [Evaluación de vulnerabilidades de software de exportación por dispositivo](get-assessment-software-vulnerabilities.md)

Otros relacionados

- [Amenazas basadas en riesgos & administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilidades de la organización](tvm-weaknesses.md)
