---
title: Exportar métodos de evaluación y propiedades por dispositivo
description: Proporciona información sobre las API que recopilan datos de "Administración de amenazas y vulnerabilidades". Hay diferentes llamadas API para obtener diferentes tipos de datos. En general, cada llamada API contiene los datos necesarios para los dispositivos de la organización. Dado que la cantidad de datos puede ser grande, hay dos formas de recuperarlos
keywords: api, apis, evaluación de exportación, por evaluación de dispositivos, por evaluación de máquina, informe de evaluación de vulnerabilidad, evaluación de vulnerabilidad de dispositivo, informe de vulnerabilidad del dispositivo, evaluación de configuración segura, informe de configuración segura, evaluación de vulnerabilidades de software, informe de vulnerabilidad de software, informe de vulnerabilidad por máquina,
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
ms.openlocfilehash: ace9f55b0b083faaeeb620700a43a1216c4451c2
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984873"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>Exportar métodos de evaluación y propiedades por dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="api-description"></a>Descripción de la API

Proporciona métodos y detalles de propiedades sobre las API que Administración de amenazas y vulnerabilidades datos por dispositivo. Hay diferentes llamadas API para obtener diferentes tipos de datos. En general, cada llamada API contiene los datos necesarios para los dispositivos de la organización.

> [!Note]
>
> A menos que se indique lo **** contrario, todos los métodos de evaluación de exportación enumerados son exportación completa y por **_dispositivo_** (también **_denominados por dispositivo_**).

Puede usar las API de evaluación de exportación para recuperar (exportar) diferentes tipos de información:

- [1. Exportar evaluación de configuraciones seguras](#1-export-secure-configurations-assessment)

- [2. Evaluación del inventario de software de exportación](#2-export-software-inventory-assessment)

- [3. Evaluación de vulnerabilidades de software de exportación](#3-export-software-vulnerabilities-assessment)

Las API que corresponden a los tipos de información de exportación se describen en las secciones 1, 2 y 3.

Para cada método, hay diferentes llamadas API para obtener diferentes tipos de datos. Dado que la cantidad de datos puede ser grande, hay dos formas de recuperarlos:

- **OData**  La API extrae todos los datos de la organización como respuestas Json, siguiendo el protocolo OData. Este método es el mejor para organizaciones pequeñas con dispositivos de menos de _100 K._ La respuesta se pagina, por lo que puede usar el campo odata.nextLink de la respuesta \@ para obtener los siguientes resultados.

- **a través de archivos** Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Almacenamiento de Azure. Esta API le permite descargar todos los datos de Almacenamiento de Azure de la siguiente manera:

  - Llama a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.

  - Descargue todos los archivos con las direcciones URL de descarga y procese los datos como quiera.

Los datos recopilados (mediante _OData_ o a través de _archivos)_ son la instantánea actual del estado actual y no contienen datos históricos. Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos.

## <a name="1-export-secure-configurations-assessment"></a>1. Exportar evaluación de configuraciones seguras

Devuelve todas las configuraciones y su estado, por dispositivo.

### <a name="11-methods"></a>1.1 Métodos

Método | Tipo de datos | Descripción
:---|:---|:---
Exportar evaluación de configuración **segura (OData)** | Configuración segura por colección de dispositivos. Vea: [Propiedades 1.2 (OData)](#12-properties-odata) | Devuelve una tabla con una entrada para cada combinación única de DeviceId, ConfigurationId. La API extrae todos los datos de la organización como respuestas Json, siguiendo el protocolo OData. Este método es el mejor para organizaciones pequeñas con dispositivos de menos de 100 K. La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los siguientes resultados.
Exportar evaluación de configuración segura **(a través de archivos)** | Configuración segura por colección de dispositivos. Vea: [Propiedades 1.2 (OData)](#12-properties-odata) | Devuelve una tabla con una entrada para cada combinación única de DeviceId, ConfigurationId. Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Almacenamiento de Azure. Esta API le permite descargar todos los datos de Almacenamiento de Azure de la siguiente manera: 1.  Llama a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización. 2.  Descargue todos los archivos con las direcciones URL de descarga y procese los datos como quiera.

### <a name="12-properties-odata"></a>1.2 Propiedades (OData)

Propiedad (ID) | Tipo de datos | Descripción
:---|:---|:---
ConfigurationCategory | string | Categoría o grupos a los que pertenece la configuración: aplicación, sistema operativo, red, cuentas, controles de seguridad
ConfigurationId | string | Identificador único para una configuración específica
ConfigurationImpact | string | Impacto valorado de la configuración en el resultado general de la configuración (1-10)
ConfigurationName | string | Nombre para mostrar de la configuración
ConfigurationSubcategory | string | Subcategoría o subagrupación a la que pertenece la configuración. En muchos casos, describe funciones o características específicas.
DeviceId | string | Identificador único del dispositivo en el servicio.
DeviceName | string | Nombre de dominio completo (FQDN) del dispositivo.
IsApplicable | bool | Indica si la configuración o directiva es aplicable
IsCompliant | bool | Indica si la configuración o la directiva está configurada correctamente
IsExpectedUserImpact | bool | Indica si habrá impacto del usuario si se aplicará la configuración
OSPlatform | string | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7. Consulta sistemas operativos y plataformas compatibles con tvm para obtener más información.
RbacGroupName | string | Grupo de control de acceso basado en roles (RBAC). Si este dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned". Si la organización no contiene ningún grupo RBAC, el valor será "None".
RecommendationReference | string | Una referencia al identificador de recomendación relacionado con este software.
Timestamp | string | La última vez que se vio la configuración en el dispositivo

### <a name="13-properties-via-files"></a>1.3 Propiedades (a través de archivos)

Propiedad (ID) | Tipo de datos | Descripción
:---|:---|:---
Exportar archivos | cadena de \[ matriz\] | Una lista de direcciones URL de descarga de archivos que contiene la instantánea actual de la organización.
GeneratedTime | string | Hora en que se generó la exportación.

## <a name="2-export-software-inventory-assessment"></a>2. Evaluación del inventario de software de exportación

Devuelve todo el software instalado y sus detalles en cada dispositivo.

### <a name="21-methods"></a>Métodos 2.1

Método | Tipo de datos | Descripción
:---|:---|:---
Evaluación del inventario de software **de exportación (OData)** | Inventario de software por colección de dispositivos. Vea: [Propiedades 2.2 (OData)](#22-properties-odata) | Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. La API extrae todos los datos de la organización como respuestas Json, siguiendo el protocolo OData. Este método es el mejor para organizaciones pequeñas con dispositivos de menos de 100 K. La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los siguientes resultados.
Exportar evaluación de inventario de software **(a través de archivos)** | Inventario de software por archivos de dispositivo. Vea: [Propiedades 2.3 (a través de archivos)](#23-properties-via-files) | Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Almacenamiento de Azure. Esta API le permite descargar todos los datos de Almacenamiento de Azure de la siguiente manera: 1.  Llama a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización. 2.  Descargue todos los archivos con las direcciones URL de descarga y procese los datos como quiera.

### <a name="22-properties-odata"></a>2.2 Propiedades (OData)

Propiedad (ID) | Tipo de datos | Descripción
:---|:---|:---
DeviceId | string | Identificador único del dispositivo en el servicio.
DeviceName | string | Nombre de dominio completo (FQDN) del dispositivo.
DiskPaths | Array[string]  | Prueba en disco de que el producto está instalado en el dispositivo.
EndOfSupportDate | string | La fecha en la que la compatibilidad con este software tiene o finalizará.
EndOfSupportStatus | string | Estado de finalización de la compatibilidad. Puede contener estos valores posibles: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.
Id | string | Identificador único del registro.
NumberOfWeaknesses | int|Número de debilidades de este software en este dispositivo
OSPlatform | string | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7. Consulta sistemas operativos y plataformas compatibles con tvm para obtener más información.
RbacGroupName | string | Grupo de control de acceso basado en roles (RBAC). Si este dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned". Si la organización no contiene ningún grupo RBAC, el valor será "None".
RegistryPaths | Array[string] | El Registro evidencia que el producto está instalado en el dispositivo.
SoftwareFirstSeenTimestamp | string | La primera vez que se vio este software en el dispositivo.
SoftwareName | string | Nombre del producto de software.
SoftwareVendor | string | Nombre del proveedor de software.
SoftwareVersion | string | Número de versión del producto de software.

### <a name="23-properties-via-files"></a>2.3 Propiedades (a través de archivos)

Propiedad (ID) | Tipo de datos | Descripción
:---|:---|:---
Exportar archivos | cadena de \[ matriz\] | Una lista de direcciones URL de descarga de archivos que contiene la instantánea actual de la organización.
GeneratedTime | string | Hora en que se generó la exportación.

## <a name="3-export-software-vulnerabilities-assessment"></a>3. Evaluación de vulnerabilidades de software de exportación

Devuelve todas las vulnerabilidades conocidas en un dispositivo y sus detalles para todos los dispositivos.

### <a name="31-methods"></a>Métodos 3.1

Método | Tipo de datos | Descripción
:---|:---|:---
Evaluación de vulnerabilidades de software **de exportación (OData)** | Colección Investigation Vea: [3.2 Properties (OData)](#32-properties-odata) | Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. La API extrae todos los datos de la organización como respuestas Json, siguiendo el protocolo OData. Este método es el mejor para organizaciones pequeñas con dispositivos de menos de 100 K. La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los siguientes resultados.
Evaluación de vulnerabilidades de software **de exportación (a través de archivos)** | Entidad de investigación Vea: [3.3 Propiedades (a través de archivos)](#33-properties-via-files) | Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable. Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos. Esta API extrae todos los datos de la organización como archivos de descarga. La respuesta contiene direcciones URL para descargar todos los datos de Almacenamiento de Azure. Esta API le permite descargar todos los datos de Almacenamiento de Azure de la siguiente manera: 1.  Llama a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización. 2.  Descargue todos los archivos con las direcciones URL de descarga y procese los datos como quiera.
**Evaluación de vulnerabilidades** de software de exportación delta **(OData)** | Colección investigation Vea: [3.4 Properties Delta export OData)](#34-properties-delta-export-odata) | Devuelve una tabla con una entrada para cada combinación única de: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId y EventTimestamp. <br><br> La API extrae datos de la organización como respuestas Json, siguiendo el protocolo OData. La respuesta está paginada, por lo que puede usar el campo @odata.nextLink de la respuesta para capturar los siguientes resultados. A diferencia de la evaluación completa de vulnerabilidades de software (OData), que se usa para obtener una instantánea completa de la evaluación de vulnerabilidades de software de su organización por dispositivo, la llamada a la API de OData de exportación delta se usa para capturar solo los cambios que han ocurrido entre una fecha seleccionada y la fecha actual (la llamada a la API "delta"). En lugar de obtener una exportación completa con una gran cantidad de datos cada vez, solo se obtiene información específica sobre vulnerabilidades nuevas, fijas y actualizadas. La llamada a la API de OData de exportación de Delta también se puede usar para calcular diferentes KPI, como "¿cuántas vulnerabilidades se han corregido?". o "¿cuántas vulnerabilidades nuevas se agregaron a mi organización?"  <br><br> Dado que la llamada de la API de OData de exportación de Delta para vulnerabilidades de software devuelve datos solo para un intervalo de fechas de destino, no se considera una _exportación completa_.

### <a name="32-properties-odata"></a>Propiedades 3.2 (OData)

Propiedad (ID) | Tipo de datos | Descripción
:---|:---|:---
CveId | string | Identificador único asignado a la vulnerabilidad de seguridad en el sistema vulnerabilidades y exposiciones comunes (CVE).
CvssScore | string | La puntuación CVSS de CVE.
DeviceId | string | Identificador único del dispositivo en el servicio.
DeviceName | string | Nombre de dominio completo (FQDN) del dispositivo.
DiskPaths | Cadena de \[ matriz\] | Prueba en disco de que el producto está instalado en el dispositivo.
ExploitabilityLevel | string | El nivel de vulnerabilidad de esta vulnerabilidad (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp | string | Primera vez que se vio la CVE de este producto en el dispositivo.
Id | string | Identificador único del registro.
LastSeenTimestamp | string | La última vez que se vio CVE en el dispositivo.
OSPlatform | string | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7. Consulta sistemas operativos y plataformas compatibles con tvm para obtener más información.
RbacGroupName | string | Grupo de control de acceso basado en roles (RBAC). Si este dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned". Si la organización no contiene ningún grupo RBAC, el valor será "None".
RecommendationReference | string | Una referencia al identificador de recomendación relacionado con este software.
RecommendedSecurityUpdate | string | Nombre o descripción de la actualización de seguridad proporcionada por el proveedor de software para solucionar la vulnerabilidad.
RecommendedSecurityUpdateId | string | Identificador de las actualizaciones de seguridad o el identificador aplicables para los artículos de guía o knowledge base (KB) correspondientes
Cadena de matriz rutas de \[ registro\] | El Registro evidencia que el producto está instalado en el dispositivo.
SoftwareName | string | Nombre del producto de software.
SoftwareVendor | string | Nombre del proveedor de software.
SoftwareVersion | string | Número de versión del producto de software.
VulnerabilitySeverityLevel | string | Nivel de gravedad asignado a la vulnerabilidad de seguridad en función de la puntuación de CVSS y los factores dinámicos influenciados por el panorama de amenazas.

### <a name="33-properties-via-files"></a>3.3 Propiedades (a través de archivos)

Propiedad (ID) | Tipo de datos | Descripción
:---|:---|:---
Exportar archivos | cadena de \[ matriz\]  | Una lista de direcciones URL de descarga de archivos que contiene la instantánea actual de la organización.
GeneratedTime | string | Hora en que se generó la exportación.

### <a name="34-properties-delta-export-odata"></a>3.4 Propiedades (OData de exportación delta)

Propiedad (ID) | Tipo de datos | Descripción
:---|:---|:---
CveId | string | Identificador único asignado a la vulnerabilidad de seguridad en el sistema vulnerabilidades y exposiciones comunes (CVE).
CvssScore | string | La puntuación CVSS de CVE.
DeviceId | string | Identificador único del dispositivo en el servicio.
DeviceName | string | Nombre de dominio completo (FQDN) del dispositivo.
DiskPaths | Array[string] | Prueba en disco de que el producto está instalado en el dispositivo.
EventTimestamp | String | Hora en que se encontró este evento delta.
ExploitabilityLevel | string | El nivel de vulnerabilidad de esta vulnerabilidad (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp | string | Primera vez que se vio la CVE de este producto en el dispositivo.
Id | string | Identificador único del registro.  
LastSeenTimestamp | string | La última vez que se vio CVE en el dispositivo.
OSPlatform | string | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7. Consulta sistemas operativos y plataformas compatibles con tvm para obtener más información.
RbacGroupName | string | Grupo de control de acceso basado en roles (RBAC). Si este dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned". Si la organización no contiene ningún grupo RBAC, el valor será "None".
RecommendationReference | string | Una referencia al identificador de recomendación relacionado con este software.
RecommendedSecurityUpdate  | string | Nombre o descripción de la actualización de seguridad proporcionada por el proveedor de software para solucionar la vulnerabilidad.
RecommendedSecurityUpdateId  | string | Identificador de las actualizaciones de seguridad o el identificador aplicables para los artículos de guía o knowledge base (KB) correspondientes
RegistryPaths  | Array[string] | El Registro evidencia que el producto está instalado en el dispositivo.
SoftwareName | string | Nombre del producto de software.
SoftwareVendor | string | Nombre del proveedor de software.
SoftwareVersion | string | Número de versión del producto de software.
Estado | String | **Nuevo**   (para una nueva vulnerabilidad introducida en un dispositivo).  **Corregido**   (para una vulnerabilidad que ya no existe en el dispositivo, lo que significa que se ha corregido). **Actualizado**   (para una vulnerabilidad en un dispositivo que ha cambiado. Los posibles cambios son: puntuación CVSS, nivel de vulnerabilidad, nivel de gravedad, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).
VulnerabilitySeverityLevel | string | Nivel de gravedad asignado a la vulnerabilidad de seguridad en función de la puntuación de CVSS y los factores dinámicos influenciados por el panorama de amenazas.

## <a name="see-also"></a>Vea también

- [Exportar evaluación de configuración segura por dispositivo](get-assessment-secure-config.md)

- [Exportar evaluación de inventario de software por dispositivo](get-assessment-software-inventory.md)

- [Evaluación de vulnerabilidades de software de exportación por dispositivo](get-assessment-software-vulnerabilities.md)

Otros relacionados

- [Amenazas basadas en riesgos & administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilidades de la organización](tvm-weaknesses.md)
