---
title: Métodos y propiedades de evaluación de certificados por dispositivo
description: Proporciona información sobre las API de certificados que extraen datos "Administración de amenazas y vulnerabilidades". Hay diferentes llamadas API para obtener diferentes tipos de datos. En general, cada llamada API contiene los datos necesarios para los dispositivos de la organización.
keywords: api, apis, export assessment, per device assessment, per machine assessment, vulnerability assessment report, device vulnerability assessment, device vulnerability report, secure configuration assessment, secure configuration report, software vulnerabilities assessment, software vulnerability report, vulnerability report by machine,
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
ms.openlocfilehash: c5f89d92e754648dcaffb134de70516c7274625d
ms.sourcegitcommit: a7cd723fd62b4b0aae9c2c2df04ead3c28180084
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2022
ms.locfileid: "66998165"
---
# <a name="export-certificate-inventory-per-device"></a>Exportación del inventario de certificados por dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quieres experimentar Administración de vulnerabilidades de Microsoft Defender? [Regístrese para obtener una evaluación gratuita.- Actualizar](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

Hay diferentes llamadas API para obtener diferentes tipos de datos. En general, cada llamada API contiene los datos necesarios para los dispositivos de la organización.

- **Respuesta JSON**  La API extrae todos los datos de la organización como respuestas JSON. Este método es mejor para _organizaciones pequeñas con menos de 100 K dispositivos_. La respuesta está paginada, por lo que puede usar el \@campo odata.nextLink de la respuesta para capturar los resultados siguientes.

- **a través de archivos** Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Puede descargar datos de Azure Storage de la siguiente manera:
  - Llame a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.
  - Descargue todos los archivos mediante las direcciones URL de descarga y procese los datos como desee.

Los datos recopilados mediante "_respuesta JSON_ o _a través de archivos_" son la instantánea actual del estado actual. No contiene datos históricos. Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos.

> [!NOTE]
> A menos que se indique lo contrario, todos los métodos de evaluación de línea base de seguridad de exportación enumerados son **_exportación completa_** y **_por dispositivo_** (también **_denominados por dispositivo_**)

## <a name="1-export-certificate-assessment-json-response"></a>1. Exportación de la evaluación de certificados (respuesta JSON)

### <a name="11-api-method-description"></a>Descripción del método de API 1.1

Devuelve todas las evaluaciones de certificados para todos los dispositivos, por dispositivo. Devuelve una tabla con una entrada independiente para cada combinación única de DeviceId, Huella digital y Ruta de acceso.

#### <a name="12-limitations"></a>1.2 Limitaciones

- El tamaño máximo de página es de 200 000.
- Las limitaciones de velocidad de esta API son 30 llamadas por minuto y 1000 llamadas por hora.

### <a name="13-parameters"></a>1.3 Parámetros

- pageSize (valor predeterminado = 50 000): número de resultados en respuesta.
- $top: número de resultados que se devolverán (no devuelve @odata.nextLink y, por lo tanto, no extrae todos los datos).

### <a name="14-http-request"></a>1.4 Solicitud HTTP

```http
GET /api/machines/certificateAssessmentByMachine
```

### <a name="15-properties-json-response"></a>Propiedades 1.5 (respuesta JSON)

> [!NOTE]
> Cada registro tiene aproximadamente 1 KB de datos. Debe tener esto en cuenta al elegir el parámetro pageSize correcto.
>
> Es posible que se devuelvan algunas columnas adicionales en la respuesta. Estas columnas son temporales y pueden quitarse. Use solo las columnas documentadas.
>
> Las propiedades definidas en la tabla siguiente se enumeran alfabéticamente por identificador de propiedad. Al ejecutar esta API, la salida resultante no se devolverá necesariamente en el mismo orden que se muestra en esta tabla.

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
|DeviceId|String|Identificador único del dispositivo en el servicio.
|DeviceName|Cadena|Nombre de dominio completo (FQDN) del dispositivo.
|Huella digital|Boolean|Identificador único para el certificado.
|Ruta de acceso|String|Ubicación del certificado.
|SignatureAlgorithm|Cadena|Algoritmo hash y algoritmo de cifrado utilizados.
|KeySize|String|Tamaño de la clave usada en el algoritmo de firma.
|ExpirationDate|Cadena|Fecha y hora posteriores a la cual el certificado ya no es válido.
|IssueDate|Cadena|Fecha y hora más tempranas en que el certificado se convirtió en válido.
|SubjectType|Cadena|Indica si el titular del certificado es una entidad de certificación o una entidad final.
|Número de serie.|Cadena|Identificador único del certificado dentro de los sistemas de una entidad de certificación.
|IssuedTo|Objeto|Entidad a la que pertenece un certificado; puede ser un dispositivo, un individuo o una organización.
|IssuedBy|Objeto|Entidad que comprobó la información y firmó el certificado.
|KeyUsage|Cadena|Los usos criptográficos válidos de la clave pública del certificado.
|ExtendedKeyUsage|String|Otros usos válidos para el certificado.
|RbacGroupId|String|Identificador de grupo de control de acceso basado en rol (RBAC).
|RbacGroupName|Cadena|El grupo de control de acceso basado en rol (RBAC). Si este dispositivo no está asignado a ningún grupo de RBAC, el valor será "Sin asignar". Si la organización no contiene ningún grupo de RBAC, el valor será "Ninguno".

## <a name="16-example"></a>Ejemplo 1.6

### <a name="161-request-example"></a>1.6.1 Ejemplo de solicitud

```http
GET https://api.securitycenter.microsoft.com/api/machines/BaselineComplianceAssessmentByMachine
```

### <a name="162-response-example"></a>Ejemplo de respuesta 1.6.2

```json

  {
     "@odata.context":"https://127.0.0.1/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetCertificateAssessment)",
      "value":[
        {
        "deviceId":"49126b9e4a5473b5229c73799e9e55c48668101b",
        "deviceName":"testmachine5",
        "thumbprint":"A4B37F4F6DE956922273D5CB8E7E0AAFB7033B90",
        "path":"LocalMachine\\TestSignRoot\\A4B37F4F6DE956922273D5CB8E7E0AAFB7033B90",
        "signatureAlgorithm":"sha384ECDSA",
        "keyLength":0,"notAfter":"0001-01-01T00:00:00Z",
        "notBefore":"0001-01-01T00:00:00Z",
        "subjectType":"CA",
        "serialNumber":"6086A185EAFA2B9943B4671603F40323",
        "subjectObject":null,
        "issuerObject":null,
        "keyUsageArray":null,
        "extendedKeyUsageArray":null,
        "isSelfSigned":false,
        "rbacGroupId":4226,
        "rbacGroupName":"testO6343398Gq31"}],
        "@odata.nextLink":"https://127.0.0.1/api/machines/CertificateAssessmentByMachine?pagesize=1&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMi0wMy0yMS8wNTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjF9"
  }
```

## <a name="2-export-certificate-assessment-via-files"></a>2. Exportación de la evaluación de certificados (a través de archivos)

### <a name="21-api-method-description"></a>2.1 Descripción del método de API

Devuelve todas las evaluaciones de certificados para todos los dispositivos, por dispositivo. Devuelve una tabla con una entrada independiente para cada combinación única de DeviceId, Huella digital y Ruta de acceso.

#### <a name="22-limitations"></a>2.2 Limitaciones

- Las limitaciones de frecuencia de esta API son 5 llamadas por minuto y 20 llamadas por hora. 

### <a name="23-parameters"></a>2.3 Parámetros

- sasValidHours: el número de horas durante las que serán válidas las direcciones URL de descarga (máximo 24 horas).

### <a name="24-http-request"></a>2.4 Solicitud HTTP

```http
GET /api/machines/certificateAssessmentExport
```

### <a name="25-properties-json-response"></a>Propiedades 2.5 (respuesta JSON)

> [!NOTE]
> Los archivos se comprimen gzip & en formato Json multilínea.
>
> Las direcciones URL de descarga solo son válidas durante 3 horas; De lo contrario, puede usar el parámetro .
>
> Para maximizar las velocidades de descarga, asegúrese de que está descargando los datos de la misma región de Azure donde residen los datos.
>
> Cada registro tiene aproximadamente 1 KB de datos. Debe tener esto en cuenta al elegir el parámetro pageSize que funciona automáticamente.
>
> Es posible que se devuelvan algunas columnas adicionales en la respuesta. Estas columnas son temporales y pueden quitarse. Use solo las columnas documentadas.

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
|Exportación de archivos|String[array]|Una lista de direcciones URL de descarga para los archivos que contienen la instantánea actual de la organización.
|GeneratedTime|DateTime|El momento en que se generó la exportación.


## <a name="26-example"></a>Ejemplo 2.6

### <a name="261-request-example"></a>2.6.1 Ejemplo de solicitud

```http
GET https://api.securitycenter.contoso.com/api/machines/certificateAssessmentExport
```

### <a name="262-response-example"></a>Ejemplo de respuesta 2.6.2

```json
    {
        "@odata.context":"https://127.0.0.1/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
        "exportFiles":["https://tvmexportexternalstgeus.blob.core.windows.net/temp-5c080622-f613-42bb-9fee-e17ccdff90d3/2022-03-20/1318/CertificateAssessmentExport/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=4226/part-00000-65a62a9d-7a01-4d78-bbdb-6d3e07b34cc9.c000.json.gz?sv=2020-02-10&st=2022-03-20T13%3A35%3A37Z&se=2022-03-20T16%3A35%3A37Z&sr=b&sp=r&sig=IMmwTOYmGvU0ei5AHLNAxnFCmZkE2jvBHzRmuAu9xaA%3D","https://tvmexportexternalstgeus.blob.core.windows.net/temp-5c080622-f613-42bb-9fee-e17ccdff90d3/2022-03-20/1318/CertificateAssessmentExport/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=4414/part-00000-65a62a9d-7a01-4d78-bbdb-6d3e07b34cc9.c000.json.gz?sv=2020-02-10&st=2022-03-20T13%3A35%3A37Z&se=2022-03-20T16%3A35%3A37Z&sr=b&sp=r&sig=2r0y74WZsATa0DjQTwfBxNqL5vN2Wl0AZKHMNrxuJ30%3D","https://tvmexportexternalstgeus.blob.core.windows.net/temp-5c080622-f613-42bb-9fee-e17ccdff90d3/2022-03-20/1318/CertificateAssessmentExport/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=75/part-00000-65a62a9d-7a01-4d78-bbdb-6d3e07b34cc9.c000.json.gz?sv=2020-02-10&st=2022-03-20T13%3A35%3A37Z&se=2022-03-20T16%3A35%3A37Z&sr=b&sp=r&sig=uVdY4%2BBpMdPMwaD3G0RJTZkS4R9J8oN8I3tu%2FOcG35c%3D"],
        "generatedTime":"2022-03-20T13:18:00Z"
   }
```
