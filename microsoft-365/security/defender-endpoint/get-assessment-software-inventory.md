---
title: Exportación de la evaluación del inventario de software por dispositivo
description: Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.
keywords: api, apis, export assessment, per device assessment, vulnerability assessment report, device vulnerability assessment, device vulnerability report, secure configuration assessment, secure configuration report, software vulnerabilities assessment, software vulnerability report, vulnerability report by machine,
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
search.appverid: met150
ms.openlocfilehash: a2b1678ae873354e8281ccf338374d16d4b3c22e
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67696185"
---
# <a name="export-software-inventory-assessment-per-device"></a>Exportación de la evaluación del inventario de software por dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Esta API devuelve todos los datos del software instalado que tiene una [enumeración de plataforma común (CPE)](https://nvd.nist.gov/products/cpe) por dispositivo.

Las distintas llamadas API obtienen diferentes tipos de datos. Dado que la cantidad de datos puede ser grande, hay dos maneras de recuperarlos:

- [Exportación de la **respuesta JSON** de evaluación del inventario de software](#1-export-software-inventory-assessment-json-response) La API extrae todos los datos de la organización como respuestas Json. Este método es mejor para _organizaciones pequeñas con menos de 100 K dispositivos_. La respuesta está paginada, por lo que puede usar el \@campo odata.nextLink de la respuesta para capturar los resultados siguientes.

- [Exportación de la evaluación del inventario **de software a través de archivos**](#2-export-software-inventory-assessment-via-files)  Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Esta API le permite descargar todos los datos de Azure Storage de la siguiente manera:
  - Llame a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.
  - Descargue todos los archivos mediante las direcciones URL de descarga y procese los datos como desee.

Los datos recopilados (mediante _la respuesta Json_ o _a través de archivos_) son la instantánea actual del estado actual. No contiene datos históricos. Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos.

> [!NOTE]
> A menos que se indique lo contrario, todos los métodos de evaluación de exportación enumerados son **_de exportación completa_** y **_por dispositivo_** (también **_denominados por dispositivo_**).

## <a name="1-export-software-inventory-assessment-json-response"></a>1. Exportación de la evaluación del inventario de software (respuesta JSON)

### <a name="11-api-method-description"></a>Descripción del método de API 1.1

Esta respuesta de API contiene todos los datos del software instalado que tiene una [enumeración de plataforma común (CPE)](https://nvd.nist.gov/products/cpe) por dispositivo. Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.

#### <a name="111-limitations"></a>1.1.1 Limitaciones

- El tamaño máximo de página es de 200 000.
- Las limitaciones de velocidad de esta API son 30 llamadas por minuto y 1000 llamadas por hora.

### <a name="12-permissions"></a>1.2 Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Microsoft Defender para punto de conexión API para obtener más información.](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
---|---|---
Application|Software.Read.All|\'Leer información de software de administración de amenazas y vulnerabilidades\'
Delegado (cuenta profesional o educativa)|Software.Read|\'Leer información de software de administración de amenazas y vulnerabilidades\'

### <a name="13-url"></a>Dirección URL 1.3

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a>1.4 Parámetros

- pageSize (valor predeterminado = 50 000): número de resultados en respuesta.
- $top: número de resultados que se devolverán (no devuelve @odata.nextLink y, por lo tanto, no extrae todos los datos)

### <a name="15-properties"></a>1.5 Propiedades

> [!NOTE]
>
> - Cada registro tiene aproximadamente 0,5 KB de datos. Debe tener esto en cuenta al elegir el parámetro pageSize correcto.
> - Las propiedades definidas en la tabla siguiente se enumeran alfabéticamente, por identificador de propiedad. Al ejecutar esta API, la salida resultante no se devolverá necesariamente en el mismo orden que se muestra en esta tabla.
> - Es posible que se devuelvan algunas columnas adicionales en la respuesta. Estas columnas son temporales y pueden quitarse, use solo las columnas documentadas.

<br>

****

Propiedad (ID)|Tipo de datos|Descripción|Ejemplo de un valor devuelto
:---|:---|:---|:---
DeviceId|string|Identificador único del dispositivo en el servicio.|9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName|string|Nombre de dominio completo (FQDN) del dispositivo.|johnlaptop.europe.contoso.com
DiskPaths|Matriz[cadena]|Prueba de disco de que el producto está instalado en el dispositivo.|[ "C:\\ Archivos de programa (x86)\\Microsoft\\Silverlight\\Application\\silverlight.exe" ]
EndOfSupportDate|string|La fecha en la que la compatibilidad con este software tiene o finalizará.|2020-12-30
EndOfSupportStatus|string|Fin del estado de soporte técnico. Puede contener estos valores posibles: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.|Próximo EOS
Id|string|Identificador único del registro.|123ABG55_573AG&mnp!
NumberOfWeaknesses|Entero|Número de puntos débiles en este software en este dispositivo|3
OSPlatform|string|Plataforma del sistema operativo que se ejecuta en el dispositivo. Se trata de sistemas operativos específicos con variaciones dentro de la misma familia, como Windows 10 y Windows 11. Consulte Administración de vulnerabilidades de Microsoft Defender sistemas operativos y plataformas compatibles para obtener más información.|Windows10 y Windows 11
RbacGroupName|string|El grupo de control de acceso basado en rol (RBAC). Si este dispositivo no está asignado a ningún grupo de RBAC, el valor será "Sin asignar". Si la organización no contiene ningún grupo de RBAC, el valor será "Ninguno".|Servidores
RegistryPaths|Matriz[cadena]|Evidencia del Registro de que el producto está instalado en el dispositivo.|[ "HKEY_LOCAL_MACHINE\\ SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Silverlight" ]
SoftwareFirstSeenTimestamp|string|La primera vez que se vio este software en el dispositivo.|2019-04-07 02:06:47
SoftwareName|string|Nombre del producto de software.|Silverlight
SoftwareVendor|string|Nombre del proveedor de software.|microsoft
SoftwareVersion|string|Número de versión del producto de software.|81.0.4044.138
|

### <a name="16-examples"></a>1.6 Ejemplos

#### <a name="161-request-example"></a>1.6.1 Ejemplo de solicitud

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="162-response-example"></a>Ejemplo de respuesta 1.6.2

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10" "Windows_11",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

> [!NOTE]
> La información devuelta por esta API, junto con la información devuelta por la API [export non product code software inventory assessment](get-assessment-non-cpe-software-inventory.md) para software que no tiene un CPE, proporciona visibilidad completa sobre el software instalado en toda la organización y los dispositivos en los que está instalado.

## <a name="2-export-software-inventory-assessment-via-files"></a>2. Exportación de la evaluación del inventario de software (a través de archivos)

### <a name="21-api-method-description"></a>2.1 Descripción del método de API

Esta respuesta de API contiene todos los datos de software instalado por dispositivo. Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.

#### <a name="211-limitations"></a>2.1.1 Limitaciones

Las limitaciones de frecuencia de esta API son 5 llamadas por minuto y 20 llamadas por hora.

### <a name="22-permissions"></a>2.2 Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Microsoft Defender para punto de conexión API para obtener más información.](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
---|---|---
Application|Software.Read.All|\'Leer información de software de administración de amenazas y vulnerabilidades\'
Delegado (cuenta profesional o educativa)|Software.Read|\'Leer información de software de administración de amenazas y vulnerabilidades\'

### <a name="23-url"></a>Dirección URL 2.3

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a>Parámetros

- sasValidHours: el número de horas durante las que serán válidas las direcciones URL de descarga (máximo 24 horas)

### <a name="25-properties"></a>2.5 Propiedades

> [!NOTE]
>
> - Los archivos se comprimen gzip & en formato JSON multilínea.
> - Las direcciones URL de descarga solo son válidas durante 3 horas. De lo contrario, puede usar el parámetro .
> - Para obtener la máxima velocidad de descarga de los datos, puede asegurarse de que está descargando desde la misma región de Azure en la que residen los datos.

<br>

****

Propiedad (ID)|Tipo de datos|Descripción|Ejemplo de un valor devuelto
:---|:---|:---|:---
Exportación de archivos|cadena de matriz\[\]|Lista de direcciones URL de descarga para los archivos que contienen la instantánea actual de la organización|"[Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1", "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2"]
GeneratedTime|string|Hora en que se generó la exportación.|2021-05-20T08:00:00Z
|

### <a name="26-examples"></a>2.6 Ejemplos

#### <a name="261-request-example"></a>2.6.1 Ejemplo de solicitud

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a>Ejemplo de respuesta 2.6.2

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Vea también

- [Exportación de métodos de evaluación y propiedades por dispositivo](get-assessment-methods-properties.md)
- [Exportación de una evaluación de configuración segura por dispositivo](get-assessment-secure-config.md)
- [Exportación de la evaluación de vulnerabilidades de software por dispositivo](get-assessment-software-vulnerabilities.md)
- [Exportar evaluación de inventario de software sin código de producto](get-assessment-non-cpe-software-inventory.md)

Otros relacionados

- [Administración de vulnerabilidades de Microsoft Defender](next-gen-threat-and-vuln-mgt.md)
- [Vulnerabilidades en la organización](tvm-weaknesses.md)
