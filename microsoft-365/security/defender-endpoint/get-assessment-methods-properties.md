---
title: Exportación de métodos de evaluación y propiedades por dispositivo
description: Proporciona información sobre las API que extraen datos "Administración de vulnerabilidades de Microsoft Defender". Hay diferentes llamadas API para obtener diferentes tipos de datos. En general, cada llamada API contiene los datos necesarios para los dispositivos de la organización.
keywords: api, apis, export assessment, per device assessment, per machine assessment, vulnerability assessment report, device vulnerability assessment, device vulnerability report, secure configuration assessment, secure configuration report, software vulnerabilities assessment, software vulnerability report, vulnerability report by machine,
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
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
ms.openlocfilehash: bc186dc9808febf2e770c78f57ee199c57461329
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68167195"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>Exportación de métodos de evaluación y propiedades por dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="api-description"></a>Descripción de la API

Proporciona métodos y detalles de propiedades sobre las API que extraen datos de administración de vulnerabilidades por dispositivo. Hay diferentes llamadas API para obtener diferentes tipos de datos. En general, cada llamada API contiene los datos necesarios para los dispositivos de la organización.

> [!NOTE]
> A menos que se indique lo contrario, todos los métodos de evaluación de exportación enumerados son **_de exportación completa_** y **_por dispositivo_** (también **_denominados por dispositivo_**).

Puede usar las API de evaluación de exportación para recuperar (exportar) diferentes tipos de información:

- [1. Exportación de la evaluación de configuraciones seguras](#1-export-secure-configurations-assessment)
- [2. Exportación de la evaluación del inventario de software](#2-export-software-inventory-assessment)
- [3. Evaluación de vulnerabilidades de software de exportación](#3-export-software-vulnerabilities-assessment)
- [4. Exportación de la evaluación del inventario de software que no es de código de producto](#4-export-non-product-code-software-inventory-assessment)

Las API que corresponden a los tipos de información de exportación se describen en las secciones 1, 2 y 3.

Cada método tiene diferentes llamadas API para obtener diferentes tipos de datos. Dado que la cantidad de datos puede ser grande, hay dos maneras de recuperarlos:

- **Respuesta JSON**  La API extrae todos los datos de la organización como respuestas JSON. Este método es mejor para _organizaciones pequeñas con menos de 100 K dispositivos_. La respuesta está paginada, por lo que puede usar el \@campo odata.nextLink de la respuesta para capturar los resultados siguientes.

- **a través de archivos** Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Esta API le permite descargar todos los datos de Azure Storage de la siguiente manera:
  - Llame a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.
  - Descargue todos los archivos mediante las direcciones URL de descarga y procese los datos como desee.

Los datos recopilados mediante "_respuesta JSON_ o _a través de archivos_" son la instantánea actual del estado actual. No contiene datos históricos. Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos.

## <a name="1-export-secure-configurations-assessment"></a>1. Exportación de la evaluación de configuraciones seguras

Devuelve todas las configuraciones y su estado, por dispositivo.

### <a name="11-methods"></a>1.1 Métodos

Método|Tipo de datos|Descripción
:---|:---|:---
Exportación de una evaluación de configuración segura **(respuesta JSON)**|Configuración segura por recopilación de dispositivos. Consulte: [Propiedades 1.2 (respuesta JSON)](#12-properties-json-response)|Devuelve una tabla con una entrada para cada combinación única de DeviceId, ConfigurationId. La API extrae todos los datos de la organización como respuestas JSON. Este método es mejor para organizaciones pequeñas con menos de 100 K dispositivos. La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los resultados siguientes.
Exportación de una evaluación de configuración segura **(a través de archivos)**|Configuración segura por recopilación de dispositivos. Vea: [Propiedades 1.3 (a través de archivos)](#13-properties-via-files)|Devuelve una tabla con una entrada para cada combinación única de DeviceId, ConfigurationId. Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Esta API le permite descargar todos los datos de Azure Storage de la siguiente manera: <ol><li>Llame a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.</li><li>Descargue todos los archivos mediante las direcciones URL de descarga y procese los datos como desee.</li></ol>

### <a name="12-properties-json-response"></a>Propiedades 1.2 (respuesta JSON)

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
configurationCategory|Cadena|Categoría o agrupación a la que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad.
configurationId|Cadena|Identificador único de una configuración específica.
configurationImpact|Cadena|Efecto clasificado de la configuración en la puntuación de configuración general (1-10).
configurationName|Cadena|Nombre para mostrar de la configuración.
configurationSubcategory|Cadena|Subcategoría o subagrupación a la que pertenece la configuración. En muchos casos, funcionalidades o características específicas.
deviceId|Cadena|Identificador único del dispositivo en el servicio.
deviceName|Cadena|Nombre de dominio completo (FQDN) del dispositivo.
isApplicable|Bool|Indica si la configuración o la directiva son aplicables.
isCompliant|Bool|Indica si la configuración o directiva está configurada correctamente.
isExpectedUserImpact|Bool|Indica si el usuario se ve afectado si se aplicará la configuración.
osPlatform|Cadena|Plataforma del sistema operativo que se ejecuta en el dispositivo. Sistemas operativos específicos con variaciones dentro de la misma familia, como Windows 10 y Windows 11. Consulte [Sistemas operativos, plataformas y funcionalidades compatibles](../defender-vulnerability-management/tvm-supported-os.md) para obtener más información.
osVersion|Cadena|Versión específica del sistema operativo que se ejecuta en el dispositivo.
rbacGroupName|Cadena|El grupo de control de acceso basado en rol (RBAC). Si el dispositivo no está asignado a ningún grupo de RBAC, el valor será "Sin asignar". Si la organización no contiene ningún grupo de RBAC, el valor será "Ninguno".
rbacGroupId|Cadena|Identificador de grupo de control de acceso basado en rol (RBAC).
recommendationReference|Cadena|Referencia al identificador de recomendación relacionado con el software.
Timestamp|Cadena|La última vez que se vio la configuración en el dispositivo.

### <a name="13-properties-via-files"></a>1.3 Propiedades (a través de archivos)

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
Exportación de archivos|cadena de matriz\[\]|Una lista de direcciones URL de descarga para los archivos que contienen la instantánea actual de la organización.
GeneratedTime|Cadena|Hora en que se generó la exportación.

## <a name="2-export-software-inventory-assessment"></a>2. Exportación de la evaluación del inventario de software

Devuelve todo el software instalado y sus detalles en cada dispositivo.

### <a name="21-methods"></a>2.1 Métodos

|Método|Tipo de datos|Descripción|
|:---|:---|:---|
|Exportación de la evaluación del inventario de software **(respuesta JSON)**|Inventario de software por recopilación de dispositivos. Consulte: [Propiedades 2.2 (respuesta JSON)](#22-properties-json-response)|Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. La API extrae todos los datos de la organización como respuestas JSON. Este método es mejor para organizaciones pequeñas con menos de 100 K dispositivos. La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los resultados siguientes. |
| Exportación de la evaluación del inventario de software **(a través de archivos)**|Inventario de software por archivos de dispositivo. Vea: [Propiedades 2.3 (a través de archivos)](#23-properties-via-files)|Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Esta API le permite descargar datos de Azure Storage de la siguiente manera: <ol><li>Llame a la API para obtener una lista de direcciones URL de descarga con los datos de la organización.</li><li>Descargue los archivos mediante las direcciones URL de descarga y procese los datos como desee.</li></ol> |

### <a name="22-properties-json-response"></a>Propiedades 2.2 (respuesta JSON)

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
DeviceId|Cadena|Identificador único del dispositivo en el servicio.
DeviceName|Cadena|Nombre de dominio completo (FQDN) del dispositivo.
DiskPaths|Matriz[cadena]|Prueba de disco de que el producto está instalado en el dispositivo.
EndOfSupportDate|Cadena|La fecha en la que la compatibilidad con este software tiene o finalizará.
EndOfSupportStatus|Cadena|Fin del estado de soporte técnico. Puede contener estos valores posibles: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.
NumberOfWeaknesses|Int|Número de puntos débiles en este software en este dispositivo.
OSPlatform|Cadena|Plataforma del sistema operativo que se ejecuta en el dispositivo; sistemas operativos específicos con variaciones dentro de la misma familia, como Windows 10 y Windows 11. Consulte [Sistemas operativos, plataformas y funcionalidades compatibles](../defender-vulnerability-management/tvm-supported-os.md) para obtener más información.
RbacGroupName|Cadena|El grupo de control de acceso basado en rol (RBAC). Si este dispositivo no está asignado a ningún grupo de RBAC, el valor será "Sin asignar". Si la organización no contiene ningún grupo de RBAC, el valor será "Ninguno".
rbacGroupId|Cadena|Identificador de grupo de control de acceso basado en rol (RBAC).
RegistryPaths|Matriz[cadena]|Evidencia del Registro de que el producto está instalado en el dispositivo.
SoftwareFirstSeenTimestamp|Cadena|La primera vez que se vio este software en el dispositivo.
SoftwareName|Cadena|Nombre del producto de software.
SoftwareVendor|Cadena|Nombre del proveedor de software.
SoftwareVersion|Cadena|Número de versión del producto de software.

### <a name="23-properties-via-files"></a>2.3 Propiedades (a través de archivos)

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
Exportación de archivos|cadena de matriz\[\]|Una lista de direcciones URL de descarga para los archivos que contienen la instantánea actual de la organización.
GeneratedTime|Cadena|Hora en que se generó la exportación.

## <a name="3-export-software-vulnerabilities-assessment"></a>3. Evaluación de vulnerabilidades de software de exportación

Devuelve todas las vulnerabilidades conocidas de un dispositivo y sus detalles para todos los dispositivos.

### <a name="31-methods"></a>3.1 Métodos

Método|Tipo de datos|Descripción
:---|:---|:---
Exportación de la evaluación de vulnerabilidades de software **(respuesta JSON)**|Colección de investigación Consulte: [Propiedades 3.2 (respuesta JSON)](#32-properties-json-response)|Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. La API extrae todos los datos de la organización como respuestas JSON. Este método es mejor para organizaciones pequeñas con menos de 100 K dispositivos. La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los resultados siguientes.
Exportación de la evaluación de vulnerabilidades de software **(a través de archivos)**|Entidad de investigación Vea: [Propiedades 3.3 (a través de archivos)](#33-properties-via-files)|Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Esta API le permite descargar todos los datos de Azure Storage de la siguiente manera: <ol><li>Llame a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.</li><li>Descargue todos los archivos mediante las direcciones URL de descarga y procese los datos como desee.</li></ol>
Evaluación de vulnerabilidades de software **de exportación delta** **(respuesta JSON)**|Colección de investigación Consulte: [Exportación delta de propiedades 3.4 (respuesta JSON)](#34-properties-delta-export-json-response)|Devuelve una tabla con una entrada para cada combinación única de: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId y EventTimestamp. <p> La API extrae datos de la organización como respuestas JSON. La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los resultados siguientes. La evaluación completa de vulnerabilidades de software (respuesta JSON) se usa para obtener una instantánea completa de la evaluación de vulnerabilidades de software de su organización por dispositivo. Sin embargo, la llamada a la API de exportación diferencial se usa para capturar solo los cambios que se han producido entre una fecha seleccionada y la fecha actual (la llamada a la API "delta"). En lugar de obtener una exportación completa con una gran cantidad de datos cada vez, solo obtendrá información específica sobre las vulnerabilidades nuevas, fijas y actualizadas. La llamada API de exportación diferencial también se puede usar para calcular KPI diferentes, como "¿cuántas vulnerabilidades se han corregido?". o "¿cuántas vulnerabilidades nuevas se agregaron a mi organización?" <p> Dado que la llamada a la API de exportación delta para vulnerabilidades de software devuelve datos solo para un intervalo de fechas de destino, no se considera una _exportación completa_.

### <a name="32-properties-json-response"></a>Propiedades 3.2 (respuesta JSON)

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
CveId|Cadena|Identificador único asignado a la vulnerabilidad de seguridad en el sistema de vulnerabilidades y exposiciones comunes (CVE).
CvssScore|Cadena|La puntuación CVSS del CVE.
DeviceId|Cadena|Identificador único del dispositivo en el servicio.
DeviceName|Cadena|Nombre de dominio completo (FQDN) del dispositivo.
DiskPaths|Cadena de matriz\[\]|Prueba de disco de que el producto está instalado en el dispositivo.
ExploitabilityLevel|Cadena|El nivel de vulnerabilidad de esta vulnerabilidad (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp|Cadena|La primera vez que se vio el CVE de este producto en el dispositivo.
Id|Cadena|Identificador único del registro.
LastSeenTimestamp|Cadena|La última vez que se vio el CVE en el dispositivo.
OSPlatform|Cadena|Plataforma del sistema operativo que se ejecuta en el dispositivo; sistemas operativos específicos con variaciones dentro de la misma familia, como Windows 10 y Windows 11. Consulte [Sistemas operativos, plataformas y funcionalidades compatibles](../defender-vulnerability-management/tvm-supported-os.md) para obtener más información.
RbacGroupName|Cadena|El grupo de control de acceso basado en rol (RBAC). Si este dispositivo no está asignado a ningún grupo de RBAC, el valor será "Sin asignar". Si la organización no contiene ningún grupo de RBAC, el valor será "Ninguno".
rbacGroupId|Cadena|Identificador de grupo de control de acceso basado en rol (RBAC).
RecommendationReference|Cadena|Referencia al identificador de recomendación relacionado con este software.
RecommendedSecurityUpdate|Cadena|Nombre o descripción de la actualización de seguridad proporcionada por el proveedor de software para solucionar la vulnerabilidad.
RecommendedSecurityUpdateId|Cadena|Identificador de las actualizaciones de seguridad o identificador aplicables para los artículos de guía o knowledge base (KB) correspondientes.
Rutas de acceso del Registro|Matriz[cadena]|Evidencia del Registro de que el producto está instalado en el dispositivo.
SecurityUpdateAvailable|Boolean|Indica si hay una actualización de seguridad disponible para el software.
SoftwareName|Cadena|Nombre del producto de software.
SoftwareVendor|Cadena|Nombre del proveedor de software.
SoftwareVersion|Cadena|Número de versión del producto de software.
VulnerabilitySeverityLevel|Cadena|Nivel de gravedad asignado a la vulnerabilidad de seguridad en función de la puntuación de CVSS.

### <a name="33-properties-via-files"></a>3.3 Propiedades (a través de archivos)

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
Exportación de archivos|cadena de matriz\[\]|Una lista de direcciones URL de descarga para los archivos que contienen la instantánea actual de la organización.
GeneratedTime|Cadena|Hora en que se generó la exportación.

### <a name="34-properties-delta-export-json-response"></a>Propiedades 3.4 (respuesta JSON de exportación diferencial)

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
CveId |Cadena|Identificador único asignado a la vulnerabilidad de seguridad en el sistema de vulnerabilidades y exposiciones comunes (CVE).
CvssScore|Cadena|La puntuación CVSS del CVE.
DeviceId|Cadena|Identificador único del dispositivo en el servicio.
DeviceName|Cadena|Nombre de dominio completo (FQDN) del dispositivo.
DiskPaths|Matriz[cadena]|Prueba de disco de que el producto está instalado en el dispositivo.
EventTimestamp|Cadena|La hora en que se encontró el evento delta.
ExploitabilityLevel|Cadena|El nivel de vulnerabilidad de vulnerabilidad (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp|Cadena|La primera vez que se vio el CVE del producto en el dispositivo.
Id|Cadena|Identificador único del registro.  
LastSeenTimestamp|Cadena|La última vez que se vio el CVE en el dispositivo.
OSPlatform|Cadena|Plataforma del sistema operativo que se ejecuta en el dispositivo; sistemas operativos específicos con variaciones dentro de la misma familia, como Windows 10 y Windows 11. Consulte [Sistemas operativos, plataformas y funcionalidades compatibles](../defender-vulnerability-management/tvm-supported-os.md) para obtener más información.
RbacGroupName|Cadena|El grupo de control de acceso basado en rol (RBAC). Si este dispositivo no está asignado a ningún grupo de RBAC, el valor será "Sin asignar". Si la organización no contiene ningún grupo de RBAC, el valor será "Ninguno".
RecommendationReference|Cadena|Referencia al identificador de recomendación relacionado con este software.
RecommendedSecurityUpdate |Cadena|Nombre o descripción de la actualización de seguridad proporcionada por el proveedor de software para solucionar la vulnerabilidad.
RecommendedSecurityUpdateId |Cadena|Identificador de las actualizaciones de seguridad o identificador aplicables para los artículos de guía o knowledge base (KB) correspondientes
RegistryPaths |Matriz[cadena]|Evidencia del Registro de que el producto está instalado en el dispositivo.
SoftwareName|Cadena|Nombre del producto de software.
SoftwareVendor|Cadena|Nombre del proveedor de software.
SoftwareVersion|Cadena|Número de versión del producto de software.
Estado|Cadena|**Nuevo** (para una nueva vulnerabilidad introducida en un dispositivo). **Se ha corregido** (para una vulnerabilidad que ya no existe en el dispositivo, lo que significa que se corrigió). **Se ha actualizado** (para una vulnerabilidad en un dispositivo que ha cambiado. Los cambios posibles son: puntuación CVSS, nivel de vulnerabilidad, nivel de gravedad, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).
VulnerabilitySeverityLevel|Cadena|Nivel de gravedad asignado a la vulnerabilidad de seguridad en función de la puntuación de CVSS.

## <a name="4-export-non-product-code-software-inventory-assessment"></a>4. Exportación de la evaluación del inventario de software que no es de código de producto

Devuelve todo el software instalado que no tiene una [enumeración de plataforma común (CPE)](https://nvd.nist.gov/products/cpe) y sus detalles en cada dispositivo.

### <a name="41-methods"></a>4.1 Métodos

|Método|Tipo de datos|Descripción|
|:---|:---|:---|
|Exportación de la evaluación del inventario de software que no es de código de producto **(respuesta JSON)**|Inventario de software que no es de código de producto por recopilación de dispositivos. Consulte: [Propiedades 4.2 (respuesta JSON)](#42-properties-json-response)|Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. La API extrae todos los datos de la organización como respuestas JSON. Este método es mejor para organizaciones pequeñas con menos de 100 K dispositivos. La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los resultados siguientes. |
| Exportación de la evaluación del inventario de software que no es de código de producto **(a través de archivos)**|Inventario de software que no es de código de producto por archivos de dispositivo. Vea: [Propiedades 4.3 (a través de archivos)](#43-properties-via-files)|Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Esta API le permite descargar datos de Azure Storage de la siguiente manera: <ol><li>Llame a la API para obtener una lista de direcciones URL de descarga con los datos de la organización.</li><li>Descargue los archivos mediante las direcciones URL de descarga y procese los datos como desee.</li></ol> |

### <a name="42-properties-json-response"></a>Propiedades 4.2 (respuesta JSON)

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

### <a name="43-properties-via-files"></a>4.3 Propiedades (a través de archivos)

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
Exportación de archivos|cadena de matriz\[\]|Una lista de direcciones URL de descarga para los archivos que contienen la instantánea actual de la organización.
GeneratedTime|Cadena|Hora en que se generó la exportación.

## <a name="see-also"></a>Vea también

- [Exportación de una evaluación de configuración segura por dispositivo](get-assessment-secure-config.md)
- [Exportación de la evaluación del inventario de software por dispositivo](get-assessment-software-inventory.md)
- [Exportación de la evaluación de vulnerabilidades de software por dispositivo](get-assessment-software-vulnerabilities.md)
- [Exportación de la evaluación del inventario de software que no es cpe por dispositivo](get-assessment-non-cpe-software-inventory.md)

Otros relacionados

- [Administración de vulnerabilidades de Microsoft Defender](next-gen-threat-and-vuln-mgt.md)
- [Vulnerabilidades en la organización](tvm-weaknesses.md)
