---
title: Propiedades y métodos de API de detalles de estado del antivirus de exportación del antivirus de Microsoft Defender
description: Obtenga información sobre cómo exportar una lista de detalles de estado del dispositivo antivirus de Microsoft Defender.
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
ms.openlocfilehash: 06339d5313b0921a5560ef7db53d2b1dad1b771f
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67520378"
---
# <a name="export-device-antivirus-health-details-api-methods-and-properties"></a>Exportación de propiedades y métodos de API de detalles de estado del antivirus de dispositivo

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="export-device-antivirus-health-details-api-description"></a>Exportación de la descripción de la API de detalles de estado del antivirus del dispositivo

Recupera una lista de detalles de estado del dispositivo antivirus de Microsoft Defender. Esta API tiene diferentes llamadas API (métodos) para obtener diferentes tipos de datos. Dado que la cantidad de datos puede ser grande, hay dos maneras de recuperarlos:

- **Respuesta JSON**  La API extrae todos los datos de la organización como respuestas JSON. Este método es mejor para _organizaciones pequeñas con menos de 100 K dispositivos_. La respuesta está paginada, por lo que puede usar el \@campo odata.nextLink de la respuesta para capturar los resultados siguientes.

- **a través de archivos** Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Esta API le permite descargar todos los datos de Azure Storage de la siguiente manera:
  - Llame a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.
  - Descargue todos los archivos mediante las direcciones URL de descarga y procese los datos como desee.

Los datos recopilados mediante "_respuesta JSON_ o _a través de archivos_" son la instantánea actual del estado actual. No contiene datos históricos. Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos.

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

### <a name="11-export-device-antivirus-health-details-api-methods"></a>1.1 Exportar métodos de API de detalles de estado del antivirus de dispositivo

Método|Tipo de datos|Descripción
:---|:---|:---
**(respuesta JSON)**|Estado del Antivirus de Microsoft Defender por recopilación de dispositivos. Consulte: [1.2 Exportación de propiedades de API de detalles de estado del antivirus de dispositivo (respuesta JSON)](#12-export-device-antivirus-health-details-api-properties-json-response)|Devuelve una tabla con una entrada para cada combinación única de DeviceId, ConfigurationId. | La API extrae todos los datos de la organización como respuestas JSON. Este método es mejor para organizaciones pequeñas con menos de 100 K dispositivos. La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los resultados siguientes.
**(a través de archivos)**|Estado del Antivirus de Microsoft Defender por recopilación de dispositivos. Consulte: [1.3 Exportación de propiedades \(de api de detalles de estado del antivirus de dispositivos a través de archivos\)](#13-export-device-antivirus-health-details-api-properties-via-files)|Devuelve una tabla con una entrada para cada combinación única de DeviceId, ConfigurationId. |Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Esta API le permite descargar todos los datos de Azure Storage de la siguiente manera: <ol><li>Llame a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.</li><li>Descargue todos los archivos mediante las direcciones URL de descarga y procese los datos como desee.</li></ol>

### <a name="12-export-device-antivirus-health-details-api-properties-json-response"></a>1.2 Export device antivirus health details API properties (RESPUESTA JSON)

> [!NOTE]
>
> - Las propiedades definidas en la tabla siguiente se enumeran alfabéticamente, por identificador de propiedad. Al ejecutar esta API, la salida resultante no se devolverá necesariamente en el mismo orden que se muestra en esta tabla.
> - Es posible que se devuelvan algunas columnas adicionales en la respuesta. Estas columnas son temporales y pueden quitarse, use solo las columnas documentadas.

| Propiedad (ID) | Tipo de datos | Descripción | Ejemplo de un valor devuelto |
|:----|:----|:----|:----|
| avEngineUpdateTime | DateTimeOffset | Fecha y hora en que se actualizó por última vez el motor av en el dispositivo | "2022-08-04T12:44:02Z" |
| avEngineVersion | Cadena | Versión del motor antivirus | "1.1.19400.3" |
| avIsEngineUpToDate | Cadena | Estado actualizado del motor de AV | "True", "False", "Unknown" |
| avIsPlatformUpToDate | Cadena | Stauts actualizados de la plataforma av | "True", "False", "Unknown" |
| avIsSignatureUpToDate | Cadena | Estado actualizado de la firma de AV | "True", "False", "Unknown" |
| avMode | Cadena | Modo antivirus. | Cada modo será un valor entero con tipo de cadena que va de 0 a 5. Consulte la asignación siguiente para ver el significado de su valor: <ul><li>'' = Otros</li><li> '0' = Activo</li><li> '1' = Pasivo</li><li> '2' = Deshabilitado</li><li> '3' = Otros</li><li> '4' = EDRBlocked</li><li>'5' = PassiveAudit</li></ul> |
| avPlatformUpdateTime | DateTimeOffset | Fecha y hora en que se actualizó por última vez la plataforma av en el dispositivo | "2022-08-04T12:44:02Z" |
| avPlatformVersion | Cadena | Versión de la plataforma antivirus | "4.18.2203.5" |
| avSignaturePublishTime | DateTimeOffset | Fecha y hora en que se publicó la compilación de inteligencia de seguridad de AV | "2022-08-04T12:44:02Z" |
| avSignatureUpdateTime | DateTimeOffset | Fecha y hora en que se actualizó por última vez la inteligencia de seguridad de ANTIVIRUS en el dispositivo | "2022-08-04T12:44:02Z" |
| avSignatureVersion | Cadena | Versión de inteligencia de seguridad antivirus | "1.371.1323.0" |
| computerDnsName | Cadena | Nombre DNS | "SampleDns" |
| dataRefreshTimestamp | DateTimeOffset | Fecha y hora en que se actualizan los datos para este informe | "2022-08-04T12:44:02Z" |
| fullScanError | Cadena | Códigos de error del examen completo | "0x80508023" |
| fullScanResult | Cadena | Resultado del examen completo de este dispositivo | "Completado" <br> "Cancelado" <br>"Error" |
| fullScanTime | DateTimeOffset | Fecha y hora en que se ha completado el examen completo | "2022-08-04T12:44:02Z" |
| id | Cadena | GUID de máquina | "30a8fa2826abf24d24379b23f8a44d471f00feab" |
| lastSeenTime | DateTimeOffset | Fecha y hora de la última vez que se ha visto en esta máquina | "2022-08-04T12:44:02Z" |
| machineId | Cadena | GUID de máquina | "30a8fa2826abf24d24379b23f8a44d471f00feab" |
| osKind | Cadena | Tipo de sistema operativo | "windows", "mac", "linux" |
| osPlatform | Cadena | Nombre de la versión principal del sistema operativo | Windows 10, macOs |
| osVersion | Cadena | Versión del sistema operativo | 10.0.18363.1440, 12.4.0.0 |
| quickScanError | Cadena | Códigos de error del examen rápido | "0x80508023" |
| quickScanResult | Cadena | Resultado del examen rápido de este dispositivo | "Completado" <br>"Cancelado" <br>"Error" |
| quickScanTime | DateTimeOffset | Fecha y hora en que se ha completado el examen rápido   | "2022-08-04T12:44:02Z" |
| rbacGroupId | Long | Identificador de grupo de dispositivos al que pertenece esta máquina | 712 |
| rbacGroupName | Cadena | Nombre del grupo de dispositivos al que pertenece esta máquina | "SampleGroup" |

### <a name="13-export-device-antivirus-health-details-api-properties-via-files"></a>1.3 Export device antivirus health details API properties (via files)

> [!IMPORTANT]
> La información de esta sección se refiere al producto preliminar que se puede modificar sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

> [!NOTE]
>
> - Los archivos se comprimen gzip & en formato Json multilínea.
> - Las direcciones URL de descarga solo son válidas durante 3 horas; De lo contrario, puede usar el parámetro .
> - Para obtener la máxima velocidad de descarga de los datos, puede asegurarse de que está descargando desde la misma región de Azure en la que residen los datos.
> - Cada registro tiene aproximadamente 1 KB de datos. Debe tener esto en cuenta al elegir el parámetro pageSize correcto.
> - Es posible que se devuelvan algunas columnas adicionales en la respuesta. Estas columnas son temporales y pueden quitarse, use solo las columnas documentadas.

| Propiedad (ID) | Tipo de datos | Descripción | Ejemplo de un valor devuelto |
|:----|:----|:----|:----|
| Exportación de archivos | array[string] | Una lista de direcciones URL de descarga para los archivos que contienen la instantánea actual de la organización. | ["https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1", "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2"] |
| GeneratedTime | Cadena | Hora en que se generó la exportación. | 2022-05-20T08:00:00Z |

> [!NOTE]
> En cada uno de los archivos de exportación se puede encontrar una propiedad "DeviceGatheredInfo" que contiene los datos sobre la información del antivirus. Cada uno de sus atributos puede proporcionar información sobre el estado del dispositivo y su estado.

## <a name="see-also"></a>Vea también

[Exportar informe de estado del antivirus del dispositivo](device-health-export-antivirus-health-report-api.md)

[Informes de cumplimiento y estado del dispositivo](machine-reports.md)
