---
title: Informes de estado del antivirus de exportación de dispositivos antivirus de Microsoft Defender Antivirus
description: Presenta métodos para recuperar los detalles del estado del dispositivo antivirus de Microsoft Defender.
keywords: apis, graph api, api admitidas, get, device health api, Microsoft Defender para punto de conexión api report api microsoft defender reports api, microsoft defender for endpoint reporting api, windows defender reporting api, defender for endpoint reporting api, windows defender reporting api, windows defender reporting api, windows defender report api
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
ms.date: 09/01/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 56568bc702ffba5e762df877d2ed3f7f80a6b0f4
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67731209"
---
# <a name="export-device-antivirus-health-report"></a>Exportar informe de estado del antivirus del dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Esta API tiene dos métodos para recuperar los detalles de estado del antivirus del dispositivo Antivirus de Microsoft Defender:

- **Método uno:** [1 Exportación de **la respuesta**\) JSON de informes de \( mantenimiento](#1-export-health-reporting-json-response) El método extrae todos los datos de la organización como respuestas JSON. Este método es mejor para _organizaciones pequeñas con menos de 100 K dispositivos_. La respuesta está paginada, por lo que puede usar el \@campo odata.nextLink de la respuesta para capturar los resultados siguientes.

- **Método dos:** [2 Exportar informes \( de estado **a través de archivos**\)](#2-export-health-reporting-via-files) Este método permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Esta API le permite descargar todos los datos de Azure Storage de la siguiente manera:
  - Llame a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.
  - Descargue todos los archivos mediante las direcciones URL de descarga y procese los datos como desee.

Los datos recopilados mediante "_respuesta JSON_ o _a través de archivos_" son la instantánea actual del estado actual. No contiene datos históricos. Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos. Consulte [Exportación de propiedades y métodos de API de detalles de estado del dispositivo](device-health-api-methods-properties.md).

> [!IMPORTANT]
>
> Actualmente, solo la **respuesta JSON de estado del antivirus** está disponible con carácter general. **Antivirus Health API a través de archivos** solo está disponible actualmente en versión preliminar pública.
>
> **La consulta personalizada de búsqueda avanzada** solo está disponible actualmente en versión preliminar pública, incluso si las consultas siguen estando visibles.

> [!IMPORTANT]
>
> Para que Windows&nbsp;Server 2012 R2&nbsp;y Windows&nbsp;Server&nbsp;2016 aparezcan en los informes de estado del dispositivo, estos dispositivos deben incorporarse mediante el paquete de solución unificado&nbsp;moderno. Para obtener más información, consulte [Nueva funcionalidad en la solución unificada moderna para Windows Server 2012 R2 y 2016](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution).

> [!NOTE]
>
> Para obtener información sobre el uso de la herramienta de informes de **cumplimiento antivirus y estado del dispositivo** en el panel seguridad de Microsoft 365, vea: [Informe de cumplimiento del estado del dispositivo y antivirus en Microsoft Defender para punto de conexión](machine-reports.md).
>

## <a name="1-export-health-reporting-json-response"></a>1 Exportación de informes de estado (respuesta JSON)

### <a name="11-api-method-description"></a>Descripción del método de API 1.1

Esta API recupera una lista de detalles de estado del antivirus del dispositivo Antivirus de Microsoft Defender. Devuelve una tabla con una entrada para cada combinación única de:

- DeviceId
- Nombre del dispositivo
- Modo AV
- Estado actualizado
- Resultados del examen.

#### <a name="111-limitations"></a>1.1.1 Limitaciones

- El tamaño máximo de página es de 200 000
- Las limitaciones de velocidad de esta API son (**_por ejemplo_** , 30 llamadas por minuto y 1000 llamadas por hour._).

#### <a name="odata-supported-operators"></a>Operadores compatibles con OData

- ```$filter``` on: ```machineId```, ```computerDnsName```, , ```osKind```, ```osPlatform```, ```osVersion```, ```avMode```, ```avEngineVersion``````avSignatureVersion```, , ```avPlatformVersion```, ```quickScanResult```, , ```quickScanError```, ```fullScanResult```, ```fullScanError``````avIsSignatureUpToDate```, ```avIsEngineUpToDate```, , , ```avIsPlatformUpToDate``````rbacGroupId```
- ```$top``` con un valor máximo de 10 000.
- ```$skip```.

### <a name="12-permissions"></a>1.2 Permisos

Se requiere uno de los permisos siguientes para llamar a esta API. Para obtener más información, incluido cómo elegir permisos, consulte Uso de api de Microsoft Defender para punto de conexión para obtener más información.

| Tipo de permiso | Permiso | Nombre para mostrar del permiso |
|:---|:---|:---|
| Application | Machine.Read.All | "Leer todos los perfiles de máquina" |
|Delegado (cuenta profesional o educativa) | Machine.Read | "Leer información de la máquina" |

### <a name="13-url-http-request"></a>1.3 URL (solicitud HTTP)

```http
URL: GET: /api/deviceavinfo
```

#### <a name="131-request-headers"></a>1.3.1 Encabezados de solicitud

| Nombre | Tipo | Descripción |
|:---|:---|:---|
| Authorization | Cadena | Portador {token}.Necesario. |

#### <a name="132-request-body"></a>1.3.2 Cuerpo de la solicitud

En blanco

#### <a name="133-response"></a>1.3.3 Respuesta

Si se ejecuta correctamente, este método devuelve 200 OK con una lista de detalles de estado del dispositivo.

### <a name="14-parameters"></a>1.4 Parámetros

- El tamaño de página predeterminado es 20
- Vea ejemplos en [consultas de OData con Microsoft Defender para punto de conexión](exposed-apis-odata-samples.md).

### <a name="15-properties"></a>1.5 Propiedades

Consulte: [1.2 Exportación de propiedades de API de detalles de estado del antivirus de dispositivo (respuesta JSON)](device-health-api-methods-properties.md#12-export-device-antivirus-health-details-api-properties-json-response)

Admite [consultas de OData V4](https://www.odata.org/documentation/).

### <a name="16-example"></a>Ejemplo 1.6

#### <a name="request-example"></a>Ejemplo de solicitud

Esta es una solicitud de ejemplo:

```http
GET https://api.securitycenter.microsoft.com/api/deviceavinfo 
```

#### <a name="response-example"></a>Ejemplo de respuesta

Esta es una respuesta de ejemplo:

```json
{ 

    @odata.context: "https://api.securitycenter.microsoft.com/api/$metadata#DeviceAvInfo", 

"value": [{ 

            "id": "Sample Guid", 

            "machineId": "Sample Machine Guid", 

            "computerDnsName": "appblockstg1", 

            "osKind": "windows", 

            "osPlatform": "Windows10", 

            "osVersion": "10.0.19044.1865", 

            "avMode": "0", 

            "avSignatureVersion": "1.371.1279.0", 

            "avEngineVersion": "1.1.19428.0", 

            "avPlatformVersion": "4.18.2206.108", 

            "lastSeenTime": "2022-08-02T19:40:45Z", 

            "quickScanResult": "Completed", 

            "quickScanError": "", 

            "quickScanTime": "2022-08-02T18:40:15.882Z", 

            "fullScanResult": "", 

            "fullScanError": "", 

            "fullScanTime": null, 

            "dataRefreshTimestamp": "2022-08-02T21:16:23Z", 

            "avEngineUpdateTime": "2022-08-02T00:03:39Z", 

            "avSignatureUpdateTime": "2022-08-02T00:03:39Z", 

            "avPlatformUpdateTime": "2022-06-20T16:59:35Z", 

            "avIsSignatureUpToDate": "True", 

            "avIsEngineUpToDate": "True", 

            "avIsPlatformUpToDate": "True", 

            "avSignaturePublishTime": "2022-08-02T00:03:39Z", 

            "rbacGroupName": "TVM1", 

            "rbacGroupId": 4415 

        }, 

        ... 

     ] 

} 
```

## <a name="2-export-health-reporting-via-files"></a>2 Exportar informes de estado (a través de archivos)

> [!IMPORTANT]
> La información de esta sección se refiere al producto preliminar que se puede modificar sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

### <a name="21-api-method-description"></a>2.1 Descripción del método de API

Esta respuesta de API contiene todos los datos de estado y estado del Antivirus por dispositivo. Devuelve una tabla con una entrada para cada combinación única de:

- DeviceId
- nombre de dispositivo
- Modo AV
- Estado actualizado
- Resultados del examen.

#### <a name="212-limitations"></a>2.1.2 Limitaciones

- El tamaño máximo de página es de 200 000.
- Las limitaciones de velocidad de esta API son 30 llamadas por minuto y 1000 llamadas por hora.

### <a name="22-permissions"></a>2.2 Permisos

Se requiere uno de los permisos siguientes para llamar a esta API.

| Tipo de permiso | Permiso | Nombre para mostrar del permiso |
|:---|:---|:---|
| Application | Vulnerability.Read.All | "Leer la información de vulnerabilidad de "Administración de amenazas y vulnerabilidades""  |
| Delegado (cuenta profesional o educativa) | Vulnerability.Read | "Leer la información de vulnerabilidad de "Administración de amenazas y vulnerabilidades"" |

Para obtener más información, incluido cómo elegir permisos, consulte [Uso de Microsoft Defender para punto de conexión API para obtener más información](apis-intro.md).

### <a name="23-url"></a>Dirección URL 2.3

```http
GET /api/machines/InfoGatheringExport 
```

### <a name="24-parameters"></a>2.4 Parámetros

- ```sasValidHours```: el número de horas para las que serán válidas las direcciones URL de descarga (máximo 24 horas).

### <a name="25-properties"></a>2.5 Propiedades

Consulte: [1.3 Export device antivirus health details API properties via files (Exportación de propiedades \(de API de detalles de estado del antivirus de dispositivo a través de archivos\)](device-health-api-methods-properties.md#13-export-device-antivirus-health-details-api-properties-via-files)).

### <a name="26-examples"></a>2.6 Ejemplos

#### <a name="261-request-example"></a>2.6.1 Ejemplo de solicitud

Esta es una solicitud de ejemplo:

```HTTP
GET https://api-us.securitycenter.contoso.com/api/machines/InfoGatheringExport 
```

#### <a name="262-response-example"></a>Ejemplo de respuesta 2.6.2  

Esta es una respuesta de ejemplo:

```json
{

   "@odata.context": "https://api-us.securitycenter.windows.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",

   "exportFiles": [

       "https://tvmexportexternalprdeus.blob.core.windows.net/temp-../2022-08-02/2201/InfoGatheringExport/json/OrgId=../_RbacGroupId=../part-00055-12fc2fcd-8f56-4e09-934f-e8efe7ce74a0.c000.json.gz?sv=2020-08-04&st=2022-08-02T22%3A47%3A11Z&se=2022-08-03T01%3A47%3A11Z&sr=b&sp=r&sig=..",               

       "https://tvmexportexternalprdeus.blob.core.windows.net/temp-../2022-08-02/2201/InfoGatheringExport/json/OrgId=../_RbacGroupId=../part-00055-12fc2fcd-8f56-4e09-934f-e8efe7ce74a0.c000.json.gz?sv=2020-08-04&st=2022-08-02T22%3A47%3A11Z&se=2022-08-03T01%3A47%3A11Z&sr=b&sp=r&sig=.."

   ],


   "generatedTime": "2022-08-02T22:01:00Z"


}
```

## <a name="see-also"></a>Vea también

[Exportar las propiedades y los métodos de estado del dispositivo](device-health-api-methods-properties.md)

[Informes de cumplimiento y estado del dispositivo](device-health-reports.md)
