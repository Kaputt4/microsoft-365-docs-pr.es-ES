---
title: Exportación de la evaluación de extensiones del explorador
description: Devuelve una tabla con una entrada para cada combinación única de DeviceId, BrowserName y ExtensionID.
keywords: api, apis, export assessment, per device assessment, vulnerability assessment report, device vulnerability assessment, device vulnerability report, browser extension assessment
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 8d728bd4e59371783725844fe83e16b4be62311d
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68168493"
---
# <a name="export-browser-extensions-assessment-per-device"></a>Exportación de la evaluación de extensiones de explorador por dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una evaluación gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> ¿Quieres experimentar Administración de vulnerabilidades de Microsoft Defender? Obtenga más información sobre cómo puede registrarse en la [versión de prueba de Administración de vulnerabilidades de Microsoft Defender versión preliminar pública](../defender-vulnerability-management/get-defender-vulnerability-management.md).

Devuelve todas las extensiones de explorador instaladas conocidas y sus detalles para todos los dispositivos, por dispositivo.

Las distintas llamadas API obtienen diferentes tipos de datos. Dado que la cantidad de datos puede ser grande, hay dos maneras de recuperarlos:

- [Exportación de la **respuesta JSON** de evaluación de extensiones del explorador](#1-export-browser-extensions-assessment-json-response) La API extrae todos los datos de la organización como respuestas Json. Este método es mejor para _organizaciones pequeñas con menos de 100 K dispositivos_. La respuesta está paginada, por lo que puede usar el \@campo odata.nextLink de la respuesta para capturar los resultados siguientes.

- [Exportación de la evaluación de extensiones del explorador **a través de archivos**](#2-export-browser-extension-assessment-via-files) Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Esta API le permite descargar todos los datos de Azure Storage de la siguiente manera:
  - Llame a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.
  - Descargue todos los archivos mediante las direcciones URL de descarga y procese los datos como desee.

Los datos recopilados (mediante _la respuesta Json_ o _a través de archivos_) son la instantánea actual del estado actual. No contiene datos históricos. Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos.

> [!NOTE]
> A menos que se indique lo contrario, todos los métodos de evaluación de exportación enumerados son **_de exportación completa_** y **_por dispositivo_** (también **_denominados por dispositivo_**).

## <a name="1-export-browser-extensions-assessment-json-response"></a>1. Exportación de la evaluación de extensiones del explorador (respuesta JSON)

### <a name="11-api-method-description"></a>Descripción del método de API 1.1

Esta respuesta de API contiene todos los datos de las extensiones de explorador instaladas por dispositivo. Devuelve una tabla con una entrada para cada combinación única de DeviceId, BrowserName y ExtensionId.

#### <a name="111-limitations"></a>1.1.1 Limitaciones

- El tamaño máximo de página es de 200 000.
- Las limitaciones de velocidad de esta API son 30 llamadas por minuto y 1000 llamadas por hora.

### <a name="12-permissions"></a>1.2 Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Microsoft Defender para punto de conexión API para obtener más información.](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Software.Read.All|"Leer la información del software de administración de amenazas y vulnerabilidades"
Delegado (cuenta profesional o educativa)|Software.Read|"Leer la información del software de administración de amenazas y vulnerabilidades"

### <a name="13-url"></a>Dirección URL 1.3

```http
GET api/Machines/BrowserExtensionsInventoryByMachine
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

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
BrowserName|string|Nombre del explorador donde está instalada la extensión.
DeviceId|string|Identificador único del dispositivo.
DeviceName|string|Nombre de dominio completo (FQDN) del dispositivo.
ExtensionDescription|string| Descripción de una extensión específica del explorador.
ExtensionId|string|Identificador único de una extensión de explorador específica.
ExtensionName|string|Nombre de una extensión de explorador específica.
ExtensionRisk|string|El nivel de riesgo más alto generado por la extensión del explorador. Los valores posibles son: "None", "Low", "Medium", "High", "Critical".
ExtensionVersion|string|Número de versión de una extensión de explorador específica.
IsActivated|Boolean|Indica si una extensión del explorador está activa.
RbacGroupId|integer|Identificador de grupo de control de acceso basado en rol (RBAC).
RbacGroupName|string|El grupo de control de acceso basado en rol (RBAC). Si este dispositivo no está asignado a ningún grupo de RBAC, el valor será "Sin asignar". Si la organización no contiene ningún grupo de RBAC, el valor será "Ninguno".
InstallationTime|string|La hora en que se instaló la extensión del explorador.
Permisos|Matriz[cadena]|Conjunto de permisos solicitados por una extensión de explorador específica.

### <a name="16-examples"></a>1.6 Ejemplos

#### <a name="161-request-example"></a>1.6.1 Ejemplo de solicitud

```http
GET https://api.securitycenter.microsoft.com/api/Machines/BrowserExtensionsInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="162-response-example"></a>Ejemplo de respuesta 1.6.2

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "DeviceId": "1c32162b42e9efa1f5de42f951775f22f435c997",
            "DeviceName": "computerpii_1363c2e016e2225cb03974df58f14e6968067aa8.domainpii_f260e982985f7e8eee198b4332e0ae5b2a069cd6.corp.microsoft.com",
            "RbacGroupId": 86,
            "RbacGroupName": "UnassignedGroup",
            "InstallationTime": "2022-05-26T18:46:27.000Z",
            "BrowserName": "chrome",
            "ExtensionId": "dkpejdfnpdkhifgbancbammdijojoffk",
            "ExtensionName": "Logitech Smooth Scrolling",
            "ExtensionDescription": "Buttery-smooth scrolling for Logitech mice and touchpads.",
            "ExtensionVersion": "6.65.62",
            "ExtensionRisk": "High",
            "IsActivated": true,
            "Permissions": [
                        {
                                    "Id": "tabs",
                                    "IsRequired": true,
                                    "Risk": "High"
                        },
                        {
                                    "Id": http://*/*,
                                    "IsRequired": true,
                                    "Risk": "High"
                        },
                        {
                                    "Id": https://*/*,
                                    "IsRequired": true,
                                    "Risk": "High"
                        }
            ]
}
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/Machines/BrowserExtensionsInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-browser-extension-assessment-via-files"></a>2. Exportación de la evaluación de la extensión del explorador (a través de archivos)

### <a name="21-api-method-description"></a>2.1 Descripción del método de API

Esta respuesta de API contiene todos los datos de las extensiones de explorador instaladas por dispositivo. Devuelve una tabla con una entrada para cada combinación única de DeviceId, BrowserName y ExtensionId.

#### <a name="211-limitations"></a>2.1.1 Limitaciones

Las limitaciones de frecuencia de esta API son 5 llamadas por minuto y 20 llamadas por hora.

### <a name="22-permissions"></a>2.2 Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Microsoft Defender para punto de conexión API para obtener más información.](apis-intro.md)

Tipo de permiso|Permiso|Nombre para mostrar del permiso
:---|:---|:---
Application|Software.Read.All|"Leer la información del software de administración de amenazas y vulnerabilidades"
Delegado (cuenta profesional o educativa)|Software.Read|"Leer la información del software de administración de amenazas y vulnerabilidades"

### <a name="23-url"></a>Dirección URL 2.3

```http
GET /api/Machines/BrowserExtensionsInventoryByMachine
```

### <a name="24-parameters"></a>2.4 Parámetros

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

### <a name="26-examples"></a>2.6 Ejemplos

#### <a name="261-request-example"></a>2.6.1 Ejemplo de solicitud

```http
GET https://api.securitycenter.microsoft.com/api/machines/BrowserExtensionsExport
```

#### <a name="262-response-example"></a>Ejemplo de respuesta 2.6.2

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/BrowserExtensions/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/BrowserExtensions/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/BrowserExtensions/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Vea también

- [Obtener información de permisos de extensiones de explorador](get-browser-extensions-permission-info.md)
- [Evaluación de extensiones del explorador](../defender-vulnerability-management/tvm-browser-extensions.md)

## <a name="other-related"></a>Otros relacionados

- [Administración de amenazas y vulnerabilidades](../defender-vulnerability-management/defender-vulnerability-management.md)
- [Vulnerabilidades en la organización](../defender-vulnerability-management/tvm-weaknesses.md)
