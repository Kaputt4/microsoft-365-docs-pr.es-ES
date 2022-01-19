---
title: Exportar métodos de evaluación y propiedades por dispositivo
description: Proporciona información sobre las API que recopilan datos de "Administración de amenazas y vulnerabilidades". Hay diferentes llamadas API para obtener diferentes tipos de datos. En general, cada llamada API contiene los datos necesarios para los dispositivos de la organización.
keywords: api, apis, evaluación de exportación, por evaluación de dispositivos, por evaluación de máquina, informe de evaluación de vulnerabilidad, evaluación de vulnerabilidad de dispositivo, informe de vulnerabilidad del dispositivo, evaluación de configuración segura, informe de configuración segura, evaluación de vulnerabilidades de software, informe de vulnerabilidad de software, informe de vulnerabilidad por máquina,
ms.prod: m365-security
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: c10f454919afc725b37537aa354fed05b95cb571
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074479"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>Exportar métodos de evaluación y propiedades por dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="api-description"></a>Descripción de la API

Proporciona métodos y detalles de propiedades sobre las API que Administración de amenazas y vulnerabilidades datos por dispositivo. Hay diferentes llamadas API para obtener diferentes tipos de datos. En general, cada llamada API contiene los datos necesarios para los dispositivos de la organización.

> [!NOTE]
> A menos que se indique lo **** contrario, todos los métodos de evaluación de exportación enumerados son exportación completa y por **_dispositivo_** (también **_denominados por dispositivo_**).

Puede usar las API de evaluación de exportación para recuperar (exportar) diferentes tipos de información:

- [1. Exportar evaluación de configuraciones seguras](#1-export-secure-configurations-assessment)
- [2. Evaluación del inventario de software de exportación](#2-export-software-inventory-assessment)
- [3. Evaluación de vulnerabilidades de software de exportación](#3-export-software-vulnerabilities-assessment)

Las API que corresponden a los tipos de información de exportación se describen en las secciones 1, 2 y 3.

Cada método tiene diferentes llamadas API para obtener diferentes tipos de datos. Dado que la cantidad de datos puede ser grande, hay dos formas de recuperarlos:

- **Respuesta JSON**  La API extrae todos los datos de la organización como respuestas JSON. Este método es el mejor para organizaciones pequeñas con dispositivos de menos de _100 K._ La respuesta se pagina, por lo que puede usar el campo odata.nextLink de la respuesta \@ para obtener los siguientes resultados.

- **a través de archivos** Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Esta API le permite descargar todos los datos de Azure Storage de la siguiente manera:
  - Llama a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.
  - Descargue todos los archivos con las direcciones URL de descarga y procese los datos como quiera.

Los datos que se recopilan con '_respuesta JSON_ o _a_ través de archivos ' es la instantánea actual del estado actual. No contiene datos históricos. Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos.

## <a name="1-export-secure-configurations-assessment"></a>1. Exportar evaluación de configuraciones seguras

Devuelve todas las configuraciones y su estado, por dispositivo.

### <a name="11-methods"></a>1.1 Métodos

Method|Tipo de datos|Descripción
:---|:---|:---
Exportar evaluación de configuración segura **(respuesta JSON)**|Configuración segura por colección de dispositivos. Vea: [Propiedades 1.2 (respuesta JSON)](#12-properties-json-response)|Devuelve una tabla con una entrada para cada combinación única de DeviceId, ConfigurationId. La API extrae todos los datos de la organización como respuestas JSON. Este método es el mejor para organizaciones pequeñas con dispositivos de menos de 100 K. La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los siguientes resultados.
Exportar evaluación de configuración segura **(a través de archivos)**|Configuración segura por colección de dispositivos. Vea: [Propiedades 1.3 (a través de archivos)](#13-properties-via-files)|Devuelve una tabla con una entrada para cada combinación única de DeviceId, ConfigurationId. Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Esta API le permite descargar todos los datos de Azure Storage de la siguiente manera: <ol><li>Llama a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.</li><li>Descargue todos los archivos con las direcciones URL de descarga y procese los datos como quiera.</li></ol>

### <a name="12-properties-json-response"></a>1.2 Propiedades (respuesta JSON)

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
configurationCategory|String|Categoría o agrupación a la que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad.
configurationId|Cadena|Identificador único para una configuración específica.
configurationImpact|String|Efecto clasificado de la configuración a la puntuación de configuración general (1-10).
configurationName|Cadena|Nombre para mostrar de la configuración.
configurationSubcategory|String|Subcategoría o subagrupación a la que pertenece la configuración. En muchos casos, características o funcionalidades específicas.
deviceId|Cadena|Identificador único del dispositivo en el servicio.
deviceName|Cadena|Nombre de dominio completo (FQDN) del dispositivo.
isApplicable|Bool|Indica si la configuración o directiva es aplicable.
isCompliant|Bool|Indica si la configuración o directiva está configurada correctamente.
isExpectedUserImpact|Bool|Indica si el usuario se ve afectado si se aplicará la configuración.
osPlatform|Cadena|Plataforma del sistema operativo que se ejecuta en el dispositivo. Sistemas operativos específicos con variaciones dentro de la misma familia, como Windows 10 y Windows 11. Consulta Sistemas operativos y plataformas compatibles con TVM para obtener más información.
osVersion|Cadena|Versión específica del sistema operativo que se ejecuta en el dispositivo.
rbacGroupName|String|Grupo de control de acceso basado en roles (RBAC). Si el dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned". Si la organización no contiene ningún grupo RBAC, el valor será "None".
rbacGroupId|Cadena|El identificador de grupo de control de acceso basado en roles (RBAC).
recommendationReference|String|Una referencia al identificador de recomendación relacionado con el software.
marca de tiempo|Cadena|La última vez que se vio la configuración en el dispositivo.

### <a name="13-properties-via-files"></a>1.3 Propiedades (a través de archivos)

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
Exportar archivos|cadena de \[ matriz\]|Una lista de direcciones URL de descarga de archivos que contiene la instantánea actual de la organización.
GeneratedTime|Cadena|Hora en que se generó la exportación.

## <a name="2-export-software-inventory-assessment"></a>2. Evaluación del inventario de software de exportación

Devuelve todo el software instalado y sus detalles en cada dispositivo.

### <a name="21-methods"></a>Métodos 2.1

|Method|Tipo de datos|Descripción|
|:---|:---|:---|
|Evaluación del inventario de software **de exportación (respuesta JSON)**|Inventario de software por colección de dispositivos. Vea: [Propiedades 2.2 (respuesta JSON)](#22-properties-json-response)|Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. La API extrae todos los datos de la organización como respuestas JSON. Este método es el mejor para organizaciones pequeñas con dispositivos de menos de 100 K. La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los siguientes resultados. |
| Exportar evaluación de inventario de software **(a través de archivos)**|Inventario de software por archivos de dispositivo. Vea: [Propiedades 2.3 (a través de archivos)](#23-properties-via-files)|Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Esta API le permite descargar datos de Azure Storage como se muestra a continuación: <ol><li>Llamar a la API para obtener una lista de direcciones URL de descarga con los datos de la organización</li><li>Descargue los archivos con las direcciones URL de descarga y procese los datos como quiera.</li></ol> |

### <a name="22-properties-json-response"></a>2.2 Propiedades (respuesta JSON)

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
DeviceId|String|Identificador único del dispositivo en el servicio.
DeviceName|String|Nombre de dominio completo (FQDN) del dispositivo.
DiskPaths|Array[string]|Prueba en disco de que el producto está instalado en el dispositivo.
EndOfSupportDate|String|La fecha en la que la compatibilidad con este software tiene o finalizará.
EndOfSupportStatus|String|Estado de finalización de la compatibilidad. Puede contener estos valores posibles: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.
NumberOfWeaknesses|Int|Número de puntos débiles de este software en este dispositivo.
OSPlatform|String|Plataforma del sistema operativo que se ejecuta en el dispositivo; sistemas operativos específicos con variaciones dentro de la misma familia, como Windows 10 y Windows 11. Consulta sistemas operativos y plataformas compatibles con tvm para obtener más información.
RbacGroupName|String|Grupo de control de acceso basado en roles (RBAC). Si este dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned". Si la organización no contiene ningún grupo RBAC, el valor será "None".
rbacGroupId|String|El identificador de grupo de control de acceso basado en roles (RBAC).
RegistryPaths|Array[string]|El Registro evidencia que el producto está instalado en el dispositivo.
SoftwareFirstSeenTimestamp|String|La primera vez que se vio este software en el dispositivo.
SoftwareName|String|Nombre del producto de software.
SoftwareVendor|Cadena|Nombre del proveedor de software.
SoftwareVersion|Cadena|Número de versión del producto de software.

### <a name="23-properties-via-files"></a>2.3 Propiedades (a través de archivos)

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
Exportar archivos|cadena de \[ matriz\]|Una lista de direcciones URL de descarga de archivos que contiene la instantánea actual de la organización.
GeneratedTime|Cadena|Hora en que se generó la exportación.

## <a name="3-export-software-vulnerabilities-assessment"></a>3. Evaluación de vulnerabilidades de software de exportación

Devuelve todas las vulnerabilidades conocidas en un dispositivo y sus detalles para todos los dispositivos.

### <a name="31-methods"></a>Métodos 3.1

Method|Tipo de datos|Descripción
:---|:---|:---
Evaluación de vulnerabilidades de software **de exportación (respuesta JSON)**|Colección Investigation Vea: [Propiedades 3.2 (respuesta JSON)](#32-properties-json-response)|Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. La API extrae todos los datos de la organización como respuestas JSON. Este método es el mejor para organizaciones pequeñas con dispositivos de menos de 100 K. La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los siguientes resultados.
Evaluación de vulnerabilidades de software **de exportación (a través de archivos)**|Entidad de investigación Vea: [3.3 Propiedades (a través de archivos)](#33-properties-via-files)|Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage. Esta API le permite descargar todos los datos de Azure Storage de la siguiente manera: <ol><li>Llama a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.</li><li>Descargue todos los archivos con las direcciones URL de descarga y procese los datos como quiera.</li></ol>
**Evaluación de vulnerabilidades** de software de exportación delta **(respuesta JSON)**|Colección investigation Vea: [3.4 Properties Delta export (respuesta JSON)](#34-properties-delta-export-json-response)|Devuelve una tabla con una entrada para cada combinación única de: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId y EventTimestamp. <p> La API extrae datos de la organización como respuestas JSON. La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los siguientes resultados. La evaluación completa de vulnerabilidades de software (respuesta JSON) se usa para obtener una instantánea completa de la evaluación de vulnerabilidades de software de su organización por dispositivo. Sin embargo, la llamada a la API de exportación delta se usa para capturar solo los cambios que se han producido entre una fecha seleccionada y la fecha actual (la llamada API "delta"). En lugar de obtener una exportación completa con una gran cantidad de datos cada vez, solo se obtiene información específica sobre vulnerabilidades nuevas, fijas y actualizadas. La llamada a la API de exportación de Delta también se puede usar para calcular diferentes KPI, como "¿cuántas vulnerabilidades se han corregido?". o "¿cuántas vulnerabilidades nuevas se agregaron a mi organización?" <p> Dado que la llamada de la API de exportación delta para vulnerabilidades de software devuelve datos solo para un intervalo de fechas de destino, no se considera una _exportación completa._

### <a name="32-properties-json-response"></a>3.2 Propiedades (respuesta JSON)

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
CveId|Cadena|Identificador único asignado a la vulnerabilidad de seguridad en el sistema vulnerabilidades y exposiciones comunes (CVE).
CvssScore|String|La puntuación CVSS de CVE.
DeviceId|String|Identificador único del dispositivo en el servicio.
DeviceName|Cadena|Nombre de dominio completo (FQDN) del dispositivo.
DiskPaths|Cadena de \[ matriz\]|Prueba en disco de que el producto está instalado en el dispositivo.
ExploitabilityLevel|String|El nivel de vulnerabilidad de esta vulnerabilidad (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp|Cadena|Primera vez que se vio la CVE de este producto en el dispositivo.
Id|Cadena|Identificador único del registro.
LastSeenTimestamp|String|La última vez que se vio CVE en el dispositivo.
OSPlatform|String|Plataforma del sistema operativo que se ejecuta en el dispositivo; sistemas operativos específicos con variaciones dentro de la misma familia, como Windows 10 y Windows 11. Consulta sistemas operativos y plataformas compatibles con tvm para obtener más información.
RbacGroupName|String|Grupo de control de acceso basado en roles (RBAC). Si este dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned". Si la organización no contiene ningún grupo RBAC, el valor será "None".
rbacGroupId|String|El identificador de grupo de control de acceso basado en roles (RBAC).
RecommendationReference|String|Una referencia al identificador de recomendación relacionado con este software.
RecommendedSecurityUpdate|String|Nombre o descripción de la actualización de seguridad proporcionada por el proveedor de software para solucionar la vulnerabilidad.
RecommendedSecurityUpdateId|Cadena|Identificador de las actualizaciones de seguridad o el identificador aplicables para los artículos de guía o knowledge base (KB) correspondientes.
Cadena de matriz rutas de \[ registro\]|El Registro evidencia que el producto está instalado en el dispositivo.
SoftwareName|Cadena|Nombre del producto de software.
SoftwareVendor|Cadena|Nombre del proveedor de software.
SoftwareVersion|Cadena|Número de versión del producto de software.
VulnerabilitySeverityLevel|Cadena|Nivel de gravedad que se asigna a la vulnerabilidad de seguridad en función de la puntuación de CVSS y los factores dinámicos influenciados por el panorama de amenazas.

### <a name="33-properties-via-files"></a>3.3 Propiedades (a través de archivos)

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
Exportar archivos|cadena de \[ matriz\]|Una lista de direcciones URL de descarga de archivos que contiene la instantánea actual de la organización.
GeneratedTime|Cadena|Hora en que se generó la exportación.

### <a name="34-properties-delta-export-json-response"></a>3.4 Propiedades (respuesta JSON de exportación delta)

Propiedad (ID)|Tipo de datos|Descripción
:---|:---|:---
CveId |Cadena|Identificador único asignado a la vulnerabilidad de seguridad en el sistema vulnerabilidades y exposiciones comunes (CVE).
CvssScore|String|La puntuación CVSS de CVE.
DeviceId|String|Identificador único del dispositivo en el servicio.
DeviceName|String|Nombre de dominio completo (FQDN) del dispositivo.
DiskPaths|Array[string]|Prueba en disco de que el producto está instalado en el dispositivo.
EventTimestamp|String|La hora en que se encontró el evento delta.
ExploitabilityLevel|String|Nivel de vulnerabilidad de vulnerabilidad (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp|String|Primera vez que se vio la CVE del producto en el dispositivo.
Id|Cadena|Identificador único del registro.  
LastSeenTimestamp|Cadena|La última vez que se vio CVE en el dispositivo.
OSPlatform|String|Plataforma del sistema operativo que se ejecuta en el dispositivo; sistemas operativos específicos con variaciones dentro de la misma familia, como Windows 10 y Windows 11. Consulta sistemas operativos y plataformas compatibles con tvm para obtener más información.
RbacGroupName|Cadena|Grupo de control de acceso basado en roles (RBAC). Si este dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned". Si la organización no contiene ningún grupo RBAC, el valor será "None".
RecommendationReference|String|Una referencia al identificador de recomendación relacionado con este software.
RecommendedSecurityUpdate |String|Nombre o descripción de la actualización de seguridad proporcionada por el proveedor de software para solucionar la vulnerabilidad.
RecommendedSecurityUpdateId |String|Identificador de las actualizaciones de seguridad o el identificador aplicables para los artículos de guía o knowledge base (KB) correspondientes
RegistryPaths |Array[string]|El Registro evidencia que el producto está instalado en el dispositivo.
SoftwareName|String|Nombre del producto de software.
SoftwareVendor|String|Nombre del proveedor de software.
SoftwareVersion|String|Número de versión del producto de software.
Estado|Cadena|**Nuevo** (para una nueva vulnerabilidad introducida en un dispositivo). **Corregido** (para una vulnerabilidad que ya no existe en el dispositivo, lo que significa que se corrigió). **Actualizado** (para una vulnerabilidad en un dispositivo que ha cambiado. Los posibles cambios son: puntuación CVSS, nivel de vulnerabilidad, nivel de gravedad, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).
VulnerabilitySeverityLevel|String|Nivel de gravedad asignado a la vulnerabilidad de seguridad en función de la puntuación de CVSS y los factores dinámicos influenciados por el panorama de amenazas.

## <a name="see-also"></a>Consulte también

- [Exportar evaluación de configuración segura por dispositivo](get-assessment-secure-config.md)
- [Exportar evaluación de inventario de software por dispositivo](get-assessment-software-inventory.md)
- [Evaluación de vulnerabilidades de software de exportación por dispositivo](get-assessment-software-vulnerabilities.md)

Otros relacionados

- [Amenazas basadas en riesgos & administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Vulnerabilidades de la organización](tvm-weaknesses.md)
