---
title: Evaluación de vulnerabilidades de software de exportación por dispositivo
description: La respuesta de la API es por dispositivo y contiene software vulnerable instalado en los dispositivos expuestos, así como cualquier vulnerabilidad conocida en estos productos de software. Esta tabla también incluye información sobre el sistema operativo, IDs de CVE e información sobre la gravedad de la vulnerabilidad.
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
ms.openlocfilehash: ea05d37ebcd0953dd109f524775a55cf8d6b3683
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984969"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a>Evaluación de vulnerabilidades de software de exportación por dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
Devuelve todas las vulnerabilidades de software conocidas y sus detalles para todos los dispositivos, por dispositivo.

Hay diferentes llamadas API para obtener diferentes tipos de datos. Dado que la cantidad de datos puede ser muy grande, hay dos formas de recuperarlos:

1. [Evaluación de vulnerabilidades de software de exportación de OData](#1-export-software-vulnerabilities-assessment-odata)  La API extrae todos los datos de la organización como respuestas Json, siguiendo el protocolo OData. Este método es el mejor para _organizaciones pequeñas con dispositivos de menos de 100 K._ La respuesta se pagina, por lo que puede usar el campo odata.nextLink de la respuesta \@ para obtener los siguientes resultados.

2. [Evaluación de vulnerabilidades de software de exportación a través de archivos](#2-export-software-vulnerabilities-assessment-via-files) Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Via-files se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Almacenamiento de Azure. Esta API le permite descargar todos los datos de Almacenamiento de Azure de la siguiente manera:

   - Llama a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.

   - Descargue todos los archivos con las direcciones URL de descarga y procese los datos como quiera.

3. [Evaluación de vulnerabilidades de software de exportación delta OData](#3-delta-export-software-vulnerabilities-assessment-odata)  Devuelve una tabla con una entrada para cada combinación única de: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId y EventTimestamp.
La API extrae datos de la organización como respuestas Json, siguiendo el protocolo OData. La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los siguientes resultados. <br><br> A diferencia de la evaluación completa de vulnerabilidades de software (OData), que se usa para obtener una instantánea completa de la evaluación de vulnerabilidades de software de su organización por dispositivo, la llamada a la API de OData de exportación delta se usa para capturar solo los cambios que han ocurrido entre una fecha seleccionada y la fecha actual (la llamada a la API "delta"). En lugar de obtener una exportación completa con una gran cantidad de datos cada vez, solo se obtiene información específica sobre vulnerabilidades nuevas, fijas y actualizadas. La llamada a la API de OData de exportación de Delta también se puede usar para calcular diferentes KPI, como "¿cuántas vulnerabilidades se han corregido?". o "¿cuántas vulnerabilidades nuevas se agregaron a mi organización?" <br><br> Dado que la llamada de la API de OData de exportación de Delta para vulnerabilidades de software devuelve datos solo para un intervalo de fechas de destino, no se considera una _exportación completa_.

Los datos recopilados (mediante _OData_ o a través de _archivos)_ son la instantánea actual del estado actual y no contienen datos históricos. Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos.

> [!Note]
>
> A menos que se indique lo **** contrario, todos los métodos de evaluación de exportación enumerados son exportación completa y por **_dispositivo_** (también **_denominados por dispositivo_**).

## <a name="1-export-software-vulnerabilities-assessment-odata"></a>1. Evaluación de vulnerabilidades de software de exportación (OData)

### <a name="11-api-method-description"></a>Descripción del método de api 1.1

Esta respuesta de la API contiene todos los datos del software instalado por dispositivo. Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.

#### <a name="limitations"></a>Limitaciones

>- El tamaño máximo de página es 200 000.
>
>- Las limitaciones de velocidad para esta API son 30 llamadas por minuto y 1000 llamadas por hora.

### <a name="12-permissions"></a>1.2 Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)

Tipo de permiso | Permiso | Nombre para mostrar de permisos
---|---|---
Aplicación | Vulnerability.Read.All | \'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'
Delegado (cuenta profesional o educativa) | Vulnerability.Read | \'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'

### <a name="13-url"></a>DIRECCIÓN URL 1.3

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a>1.4 Parámetros

- pageSize (valor predeterminado = 50.000): número de resultados en la respuesta
- $top: número de resultados que se devolverán (no devuelve @odata.nextLink y, por lo tanto, no extrae todos los datos)

### <a name="15-properties"></a>1.5 Propiedades
>
>[!Note]
>
>- Cada registro tiene aproximadamente 1 KB de datos. Debe tener esto en cuenta al elegir el parámetro pageSize correcto.
>
>- Es posible que se devuelvan algunas columnas adicionales en la respuesta. Estas columnas son temporales y pueden quitarse, use solo las columnas documentadas.
>
>- Las propiedades definidas en la tabla siguiente se enumeran alfabéticamente, por identificador de propiedad.  Al ejecutar esta API, el resultado resultante no se devolverá necesariamente en el mismo orden enumerado en esta tabla.
>

Propiedad (ID) | Tipo de datos | Descripción | Ejemplo de un valor devuelto
:---|:---|:---|:---
CveId | string | Identificador único asignado a la vulnerabilidad de seguridad en el sistema vulnerabilidades y exposiciones comunes (CVE). | CVE-2020-15992
CvssScore | string | La puntuación CVSS de CVE. | 6.2
DeviceId | string | Identificador único del dispositivo en el servicio. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | string | Nombre de dominio completo (FQDN) del dispositivo. | johnlaptop.europe.contoso.com
DiskPaths  | Cadena de \[ matriz\] | Prueba en disco de que el producto está instalado en el dispositivo. | [ "C:\Archivos de programa (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]
ExploitabilityLevel | string | El nivel de vulnerabilidad de esta vulnerabilidad (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit) | ExploitIsInKit
FirstSeenTimestamp | string | Primera vez que se vio la CVE de este producto en el dispositivo. | 2020-11-03 10:13:34.8476880
Id | string | Identificador único del registro. | 123ABG55_573AG&mnp!
LastSeenTimestamp | string | La última vez que se vio CVE en el dispositivo. | 2020-11-03 10:13:34.8476880
OSPlatform | string | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esta propiedad indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 10 y Windows 7. Consulta sistemas operativos y plataformas compatibles con tvm para obtener más información. | Windows10
RbacGroupName  | string | Grupo de control de acceso basado en roles (RBAC). Si este dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned". Si la organización no contiene ningún grupo RBAC, el valor será "None". | Servidores
RecommendationReference | string | Una referencia al identificador de recomendación relacionado con este software. | va-_-microsoft-_-silverlight
RecommendedSecurityUpdate (opcional) | string | Nombre o descripción de la actualización de seguridad proporcionada por el proveedor de software para solucionar la vulnerabilidad. | Actualizaciones de seguridad de abril de 2020
RecommendedSecurityUpdateId (opcional) | string | Identificador de las actualizaciones de seguridad o el identificador aplicables para los artículos de guía o knowledge base (KB) correspondientes | 4550961
RegistryPaths  | Cadena de \[ matriz\] | El Registro evidencia que el producto está instalado en el dispositivo. | [ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]
SoftwareName | string | Nombre del producto de software. | chrome
SoftwareVendor | string | Nombre del proveedor de software. | google
SoftwareVersion | string | Número de versión del producto de software. | 81.0.4044.138
VulnerabilitySeverityLevel  | string | Nivel de gravedad asignado a la vulnerabilidad de seguridad en función de la puntuación de CVSS y los factores dinámicos influenciados por el panorama de amenazas. | Medio

### <a name="16-examples"></a>1.6 Ejemplos

#### <a name="161-request-example"></a>1.6.1 Ejemplo de solicitud

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a>Ejemplo de respuesta 1.6.2

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a>2. Evaluación de vulnerabilidades de software de exportación (a través de archivos)

### <a name="21-api-method-description"></a>Descripción del método api 2.1

Esta respuesta de la API contiene todos los datos del software instalado por dispositivo. Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.

#### <a name="212-limitations"></a>2.1.2 Limitaciones

Las limitaciones de velocidad para esta API son 5 llamadas por minuto y 20 llamadas por hora.

### <a name="22-permissions"></a>2.2 Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)

Tipo de permiso | Permiso | Nombre para mostrar de permisos
---|---|---
Aplicación | Vulnerability.Read.All | \'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'
Delegado (cuenta profesional o educativa) | Vulnerability.Read | \'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'

### <a name="23-url"></a>DIRECCIÓN URL 2.3

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a>Parámetros 2.4

- sasValidHours: el número de horas durante las que las direcciones URL de descarga serán válidas (máximo 24 horas)

### <a name="25-properties"></a>2.5 Propiedades

>[!Note]
>
>- Los archivos son archivos comprimidos de gzip & en formato Json de varias líneas.
>
>- Las direcciones URL de descarga solo son válidas durante 3 horas; de lo contrario, puede usar el parámetro.
>
>- Para obtener la velocidad máxima de descarga de los datos, puede asegurarse de que está descargando desde la misma región de Azure en la que residen los datos.
>

>[!Note]
>
>- Cada registro tiene aproximadamente 1 KB de datos. Debe tener esto en cuenta al elegir el parámetro pageSize correcto.
>
>- Es posible que se devuelvan algunas columnas adicionales en la respuesta. Estas columnas son temporales y pueden quitarse, use solo las columnas documentadas.
>

Propiedad (ID) | Tipo de datos | Descripción | Ejemplo de un valor devuelto
:---|:---|:---|:---
Exportar archivos | cadena de \[ matriz\]  | Una lista de direcciones URL de descarga de archivos que contiene la instantánea actual de la organización. | [  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]
GeneratedTime | string | Hora en que se generó la exportación. | 2021-05-20T08:00:00Z

### <a name="26-examples"></a>2.6 Ejemplos

#### <a name="261-request-example"></a>2.6.1 Ejemplo de solicitud

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a>Ejemplo de respuesta 2.6.2

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="3-delta-export-software-vulnerabilities-assessment-odata"></a>3. Evaluación de vulnerabilidades de software de exportación delta (OData)

### <a name="31-api-method-description"></a>Descripción del método de api 3.1

Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. La API extrae datos de la organización como respuestas Json, siguiendo el protocolo OData. La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los siguientes resultados. A diferencia de la evaluación completa de vulnerabilidades de software (OData), que se usa para obtener una instantánea completa de la evaluación de vulnerabilidades de software de su organización por dispositivo, la llamada a la API de OData de exportación delta se usa para capturar solo los cambios que han ocurrido entre una fecha seleccionada y la fecha actual (la llamada a la API "delta"). En lugar de obtener una exportación completa con una gran cantidad de datos cada vez, solo se obtiene información específica sobre vulnerabilidades nuevas, fijas y actualizadas. La llamada a la API de OData de exportación de Delta también se puede usar para calcular diferentes KPI, como "¿cuántas vulnerabilidades se han corregido?". o "¿cuántas vulnerabilidades nuevas se agregaron a mi organización?"

>[!NOTE]
>
>Es muy recomendable que use la evaluación completa de vulnerabilidades de software de exportación por llamada api de dispositivo al menos una vez a la semana, y esta vulnerabilidad de software de exportación adicional cambia por API de dispositivo (delta) llamar a todos los demás días de la semana.  A diferencia de la otra API de OData de evaluaciones, la "exportación delta" no es una exportación completa. La exportación delta incluye solo los cambios que se han producido entre una fecha seleccionada y la fecha actual (la llamada a la API "delta").

#### <a name="limitations"></a>Limitaciones

- El tamaño máximo de página es 200 000.

- El parámetro sinceTime tiene un máximo de 14 días.

- Las limitaciones de velocidad para esta API son 30 llamadas por minuto y 1000 llamadas por hora.

### <a name="32-permissions"></a>3.2 Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)

Tipo de permiso | Permiso | Nombre para mostrar de permisos
---|---|---
Aplicación | Vulnerability.Read.All | 'Leer información de vulnerabilidad de administración de amenazas y vulnerabilidades'
Delegado (cuenta profesional o educativa) | Vulnerability.Read | 'Leer información de vulnerabilidad de administración de amenazas y vulnerabilidades'

### <a name="33-url"></a>DIRECCIÓN URL 3.3

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine 
```

### <a name="34-parameters"></a>Parámetros 3.4

- sinceTime (obligatorio): los datos entre una hora seleccionada y la actualidad.
- pageSize (valor predeterminado = 50.000): número de resultados en la respuesta
- $top: número de resultados que se devolverán (no devuelve @odata.nextLink y, por lo tanto, no extrae todos los datos)

### <a name="35-properties"></a>3.5 Propiedades

Cada registro devuelto contiene todos los datos de la evaluación completa de vulnerabilidades de software de exportación por parte de la API de OData del dispositivo, además de dos campos adicionales:  _**EventTimestamp**_ y _**Status**_.

>[!NOTE]
>-Es posible que se devuelvan algunas columnas adicionales en la respuesta. Estas columnas son temporales y pueden quitarse, por lo que use solo las columnas documentadas.
>
>-Las propiedades definidas en la tabla siguiente se enumeran alfabéticamente, por identificador de propiedad.  Al ejecutar esta API, el resultado resultante no se devolverá necesariamente en el mismo orden enumerado en esta tabla.
<br>

Propiedad (ID) | Tipo de datos | Descripción | Ejemplo del valor devuelto
:---|:---|:---|:---
CveId | string | Identificador único asignado a la vulnerabilidad de seguridad en el sistema vulnerabilidades y exposiciones comunes (CVE). | CVE-2020-15992  
CvssScore | string | La puntuación CVSS de CVE. | 6.2  
DeviceId | string | Identificador único del dispositivo en el servicio. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1  
DeviceName | string | Nombre de dominio completo (FQDN) del dispositivo. | johnlaptop.europe.contoso.com  
DiskPaths | Array[string] | Prueba en disco de que el producto está instalado en el dispositivo. | [ "C:\Archivos de programa (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]  
EventTimestamp | String | Hora en que se encontró este evento delta. | 2021-01-11T11:06:08.291Z
ExploitabilityLevel | string | El nivel de vulnerabilidad de esta vulnerabilidad (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit) | ExploitIsInKit  
FirstSeenTimestamp | string | Primera vez que se vio la CVE de este producto en el dispositivo. | 2020-11-03 10:13:34.8476880  
Id | string | Identificador único del registro. | 123ABG55_573AG&mnp!  
LastSeenTimestamp | string | La última vez que se vio CVE en el dispositivo. | 2020-11-03 10:13:34.8476880  
OSPlatform | string | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7. Consulta sistemas operativos y plataformas compatibles con tvm para obtener más información. | Windows10  
RbacGroupName | string | Grupo de control de acceso basado en roles (RBAC). Si este dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned". Si la organización no contiene ningún grupo RBAC, el valor será "None". | Servidores  
RecommendationReference | string | Una referencia al identificador de recomendación relacionado con este software. | va--microsoft--silverlight  
RecommendedSecurityUpdate  | string | Nombre o descripción de la actualización de seguridad proporcionada por el proveedor de software para solucionar la vulnerabilidad. | Actualizaciones de seguridad de abril de 2020  
RecommendedSecurityUpdateId  | string | Identificador de las actualizaciones de seguridad o el identificador aplicables para los artículos de guía o knowledge base (KB) correspondientes | 4550961  
RegistryPaths  | Array[string] | El Registro evidencia que el producto está instalado en el dispositivo. | [ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]  
SoftwareName | string | Nombre del producto de software. | chrome  
SoftwareVendor | string | Nombre del proveedor de software. | google  
SoftwareVersion | string | Número de versión del producto de software. | 81.0.4044.138  
Estado | String | **Nuevo**   (para una nueva vulnerabilidad introducida en un dispositivo)  (1) **Corregido**(si esta vulnerabilidad ya no existe en el dispositivo, lo que   significa que se corrigió). (2)  **Actualizado**   (si ha cambiado una vulnerabilidad en un dispositivo. Los posibles cambios son: puntuación CVSS, nivel de vulnerabilidad, nivel de gravedad, DiskPaths, RegistryPaths, RecommendedSecurityUpdate). | Decimal
VulnerabilitySeverityLevel | string | Nivel de gravedad asignado a la vulnerabilidad de seguridad en función de la puntuación de CVSS y los factores dinámicos influenciados por el panorama de amenazas. | Medio  

#### <a name="clarifications"></a>Aclaraciones

- Si el software se actualizó de la versión 1.0 a la versión 2.0 y ambas versiones se exponen a CVE-A, recibirás 2 eventos independientes:  
   a. Corregido: CVE-A en la versión 1.0 era fijo  
   b. Nuevo: se agregó CVE-A en la versión 2.0

- Si una vulnerabilidad específica (por ejemplo, CVE-A) se vio por primera vez en un momento específico (por ejemplo, el 10 de enero) en software con la versión 1.0 y unos días más tarde ese software se actualizó a la versión 2.0, que también se expone a la misma CVE-A, recibirá estos dos eventos separados:  
   a. Corregido: CVE-X, FirstSeenTimestamp el 10 de enero, versión 1,0.  
   b. Nuevo: CVE-X, FirstSeenTimestamp el 10 de enero, versión 2.0.

### <a name="36-examples"></a>3.6 Ejemplos

#### <a name="361-request-example"></a>Ejemplo de solicitud 3.6.1

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a>Ejemplo de respuesta 3.6.2

```json
{ 
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)", 
    "value": [ 
        { 
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__", 
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "87.0.4280.88", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome" 
            ], 
            "lastSeenTimestamp": "2021-01-04 00:29:42", 
            "firstSeenTimestamp": "2020-11-06 03:12:44", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__", 
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "onedrive", 
            "softwareVersion": "20.64.329.3", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe" 
            ], 
            "lastSeenTimestamp": "2020-12-11 19:49:48", 
            "firstSeenTimestamp": "2020-12-07 18:25:47", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-onedrive", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_", 
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "mozilla", 
            "softwareName": "firefox", 
            "softwareVersion": "83.0.0.0", 
            "cveId": "CVE-2020-26971", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "193220", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)" 
            ], 
            "lastSeenTimestamp": "2021-01-05 17:04:30", 
            "firstSeenTimestamp": "2020-05-06 12:42:19", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-mozilla-_-firefox", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__", 
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "project", 
            "softwareVersion": "16.0.13701.20000", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us" 
            ], 
            "lastSeenTimestamp": "2021-01-03 23:38:03", 
            "firstSeenTimestamp": "2019-08-01 22:56:12", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-project", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_", 
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "81.0.4044.138", 
            "cveId": "CVE-2020-16011", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "ADV 200002", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}" 
            ], 
            "lastSeenTimestamp": "2020-12-10 22:45:41", 
            "firstSeenTimestamp": "2020-07-26 02:13:43", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        } 
    ], 
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9" 
} 
```

## <a name="see-also"></a>Vea también

- [Exportar métodos de evaluación y propiedades por dispositivo](get-assessment-methods-properties.md)

- [Exportar evaluación de configuración segura por dispositivo](get-assessment-secure-config.md)

- [Exportar evaluación de inventario de software por dispositivo](get-assessment-software-inventory.md)

Otros relacionados

- [Amenazas basadas en riesgos & administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilidades de la organización](tvm-weaknesses.md)
