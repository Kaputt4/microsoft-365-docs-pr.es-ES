---
title: Exportación de la evaluación del inventario de software que no es de código de producto por dispositivo
description: Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion para software que no tiene una enumeración common platform (CPE)
keywords: api, apis, export assessment, per device assessment, vulnerability assessment report, device vulnerability assessment, device vulnerability report, secure configuration assessment, secure configuration report, software vulnerabilities assessment, software vulnerability report, vulnerability report by machine,
ms.prod: m365-security
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 223ca8ab9eac14b456c62dad3d644ad067092766
ms.sourcegitcommit: 48a75b40e607542e5fe219b6e75ffc757804a9c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "67344552"
---
# <a name="export-non-product-code-software-inventory-assessment-per-device"></a>Exportación de la evaluación del inventario de software que no es de código de producto por dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Esta API devuelve todos los datos del software instalado que no tiene una [enumeración common platform (CPE)](https://nvd.nist.gov/products/cpe) por dispositivo. La información devuelta por esta API, junto con la información devuelta por la API [de evaluación de inventario de software de exportación](get-assessment-non-cpe-software-inventory.md) , para el software que tiene un CPE, proporciona visibilidad completa sobre el software instalado en toda la organización y los dispositivos en los que está instalado.

> [!NOTE]
> Los productos de software sin un CPE no son compatibles con la administración de vulnerabilidades. Se mostrarán en la página de inventario de software, pero como los CPE los usa la administración de vulnerabilidades para identificar el software y las vulnerabilidades, la información como vulnerabilidades, el número de dispositivos expuestos y las debilidades no estarán disponibles para ellos. Para obtener más información, consulte [Inventario de software](../defender-vulnerability-management/tvm-software-inventory.md).

Las distintas llamadas API obtienen diferentes tipos de datos. Dado que la cantidad de datos puede ser grande, hay dos maneras de recuperarlos:

- [Exportación de una **respuesta JSON** de evaluación del inventario de software que no es de código de producto](#1-export-non-product-code-software-inventory-assessment-json-response) La API extrae todos los datos de la organización como respuestas Json. Este método es mejor para _organizaciones pequeñas con menos de 100 K dispositivos_. La respuesta está paginada, por lo que puede usar el \@campo odata.nextLink de la respuesta para capturar los resultados siguientes.

- [Exportación de la evaluación del inventario de software que no es de código **de producto a través de archivos**](#2-export-non-product-code-software-inventory-assessment-via-files)  Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Esta API le permite descargar todos los datos de Azure Storage de la siguiente manera:
  - Llame a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.
  - Descargue todos los archivos mediante las direcciones URL de descarga y procese los datos como desee.

Los datos recopilados (mediante _la respuesta Json_ o _a través de archivos_) son la instantánea actual del estado actual. No contiene datos históricos. Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos.

> [!NOTE]
> A menos que se indique lo contrario, todos los métodos de evaluación de exportación enumerados son **_de exportación completa_** y **_por dispositivo_** (también **_denominados por dispositivo_**).

## <a name="1-export-non-product-code-software-inventory-assessment-json-response"></a>1. Exportación de la evaluación del inventario de software que no es de código de producto (respuesta JSON)

### <a name="11-api-method-description"></a>Descripción del método de API 1.1

Esta respuesta de API contiene todos los datos del software instalado que no tiene una [enumeración de plataforma común (CPE)](https://nvd.nist.gov/products/cpe) por dispositivo. Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.

#### <a name="limitations"></a>Limitaciones

- El tamaño máximo de página es de 200 000.
- Las limitaciones de velocidad de esta API son 30 llamadas por minuto y 1000 llamadas por hora.

### <a name="12-permissions"></a>1.2 Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Microsoft Defender para punto de conexión API para obtener más información.](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
---|---|---
Application|Software.Read.All|\'Lee la información de vulnerabilidades de Administración de amenazas y vulnerabilidades.\'
Delegado (cuenta profesional o educativa)|Software.Read|\'Lee la información de vulnerabilidades de Administración de amenazas y vulnerabilidades.\'

### <a name="13-url"></a>Dirección URL 1.3

```http
GET /api/machines/SoftwareInventoryNoProductCodeByMachine
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

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
DeviceId|string|Identificador único del dispositivo en el servicio.
DeviceName|string|Nombre de dominio completo (FQDN) del dispositivo.
OSPlatform|string|Plataforma del sistema operativo que se ejecuta en el dispositivo. Se trata de sistemas operativos específicos con variaciones dentro de la misma familia, como Windows 10 y Windows 11. Consulte [Sistemas operativos, plataformas y funcionalidades compatibles](../defender-vulnerability-management/tvm-supported-os.md) para obtener más información.
RbacGroupName|string|El grupo de control de acceso basado en rol (RBAC). Si este dispositivo no está asignado a ningún grupo de RBAC, el valor será "Sin asignar". Si la organización no contiene ningún grupo de RBAC, el valor será "Ninguno".
RbacGroupId|string|Identificador de grupo de control de acceso basado en rol (RBAC).
SoftwareLastSeenTimestamp|string|La última vez que se vio este software en el dispositivo.
SoftwareName|string|Nombre del producto de software.
SoftwareVendor|string|Nombre del proveedor de software.
SoftwareVersion|string|Número de versión del producto de software.

### <a name="16-examples"></a>1.6 Ejemplos

#### <a name="161-request-example"></a>1.6.1 Ejemplo de solicitud

```http
https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryNoProductCodeByMachine?pageSize=3  &sinceTime=2021-05-19
```

#### <a name="162-response-example"></a>Ejemplo de respuesta 1.6.2

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetNonCpeSoftware)",
    "value": [
        {
           "deviceId": "1234512345123451234512345",
            "rbacGroupId": 11,
            "rbacGroupName": "London",
            "deviceName": "Device1",
            "osPlatform": "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": "vs_communitymsi",
            "softwareVersion": "11.11.31111.1",
            "softwareLastSeenTimestamp": "2021-01-30 11:31:12.271"
        },
        {
            "deviceId": "232323232323232322323232323",
            "rbacGroupId": 23,
            "rbacGroupName": "Tokyo",
            "deviceName": "Device23",
            "osPlatform": "Windows10",
            "softwareVendor": "intel",
            "softwareName": "intel®_software_installer",
            "softwareVersion": "22.20.2.2",
            "softwareLastSeenTimestamp": "2022-05-30 15:35:12.271"
        },
        {
            "deviceId": "6565656565",
            "rbacGroupId": 65,
            "rbacGroupName": "Center",
            "deviceName": "Device56",
            "osPlatform": "Windows10",
            "softwareVendor": "Lob Apps",
            "softwareName": "Headtrax",
            "softwareVersion": "60.273.3",
            "softwareLastSeenTimestamp": "2022-05-05 15:35:12.271"
        },
    ],
        "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryNoProductCodeByMachine?pagesize=3%20%20&sincetime=2021-05-19&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMi0wNS0zMC8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}

```

## <a name="2-export-non-product-code-software-inventory-assessment-via-files"></a>2. Exportación de la evaluación del inventario de software que no es de código de producto (a través de archivos)

### <a name="21-api-method-description"></a>2.1 Descripción del método de API

Esta respuesta de API contiene todos los datos del software instalado que no tiene una [enumeración de plataforma común (CPE)](https://nvd.nist.gov/products/cpe) por dispositivo. Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.

#### <a name="211-limitations"></a>2.1.1 Limitaciones

Las limitaciones de frecuencia de esta API son 5 llamadas por minuto y 20 llamadas por hora.

### <a name="22-permissions"></a>2.2 Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Microsoft Defender para punto de conexión API para obtener más información.](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
---|---|---
Application|Software.Read.All|\'Lee la información de vulnerabilidades de Administración de amenazas y vulnerabilidades.\'
Delegado (cuenta profesional o educativa)|Software.Read|\'Lee la información de vulnerabilidades de Administración de amenazas y vulnerabilidades.\'

### <a name="23-url"></a>Dirección URL 2.3

```http
GET /api/machines/Api/Machines/SoftwareInventoryNonCpeExport
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
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryNonCpeExport
```

#### <a name="262-response-example"></a>Ejemplo de respuesta 2.6.2

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportexternalprdcanc.blob.core.windows.net/temp-ffd80447-7b3d-4ad2-b366-f0979b129662/2022-05-30/1101/NonCpeSoftwareInventory/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=1/part-00337-5e15412b-5c85-4896-ac60-b7b3ab8da096.c000.json.gz?sv=2020-08-04&st=2022-05-30T13%3A41%3A59Z&se=2022-05-30T16%3A41%3A59Z&sr=b&sp=r&sig=aHnmuOKlIvpR0PsdamYfmCCDZ1nhpuXBzK2%2FkJ9xTpg%3D",
        "https://tvmexportexternalprdcanc.blob.core.windows.net/temp-ffd80447-7b3d-4ad2-b366-f0979b129662/2022-05-30/1101/NonCpeSoftwareInventory/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=1/part-00338-5e15412b-5c85-4896-ac60-b7b3ab8da096.c000.json.gz?sv=2020-08-04&st=2022-05-30T13%3A41%3A59Z&se=2022-05-30T16%3A41%3A59Z&sr=b&sp=r&sig=0fQg%2Ft469x26KvPLmvctLl0g6DC38CNM3lXYi9dnFfo%3D",
        "https://tvmexportexternalprdcanc.blob.core.windows.net/temp-ffd80447-7b3d-4ad2-b366-f0979b129662/2022-05-30/1101/NonCpeSoftwareInventory/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=1/part-00339-5e15412b-5c85-4896-ac60-b7b3ab8da096.c000.json.gz?sv=2020-08-04&st=2022-05-30T13%3A41%3A59Z&se=2022-05-30T16%3A41%3A59Z&sr=b&sp=r&sig=P6HGHoLXXipMauBpLueoQVrwHL7qmvLoCjcij6ERx8o%3D",
        "https://tvmexportexternalprdcanc.blob.core.windows.net/temp-ffd80447-7b3d-4ad2-b366-f0979b129662/2022-05-30/1101/NonCpeSoftwareInventory/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=1/part-00340-5e15412b-5c85-4896-ac60-b7b3ab8da096.c000.json.gz?sv=2020-08-04&st=2022-05-30T13%3A41%3A59Z&se=2022-05-30T16%3A41%3A59Z&sr=b&sp=r&sig=VnpVct%2F8vdiIFTf2xXP9DF7ngWv1Zqew30q2jBPVghg%3D",
        "https://tvmexportexternalprdcanc.blob.core.windows.net/temp-ffd80447-7b3d-4ad2-b366-f0979b129662/2022-05-30/1101/NonCpeSoftwareInventory/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=1/part-00341-5e15412b-5c85-4896-ac60-b7b3ab8da096.c000.json.gz?sv=2020-08-04&st=2022-05-30T13%3A41%3A59Z&se=2022-05-30T16%3A41%3A59Z&sr=b&sp=r&sig=GY0zxMfEmr9v9fZBWYyKEtT2k%2F0ELQIlOP0ct%2B6SdGU%3D",
    ],
    "generatedTime": "2022-05-30T11:01:00Z"
}
```

## <a name="see-also"></a>Vea también

- [Exportación de la evaluación de software por dispositivo](get-assessment-software-inventory.md)
- [Exportación de métodos de evaluación y propiedades por dispositivo](get-assessment-methods-properties.md)
- [Exportación de una evaluación de configuración segura por dispositivo](get-assessment-secure-config.md)
- [Exportación de la evaluación de vulnerabilidades de software por dispositivo](get-assessment-software-vulnerabilities.md)

Otros relacionados
- [Administración de vulnerabilidades de Microsoft Defender](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Vulnerabilidades en la organización](tvm-weaknesses.md)
