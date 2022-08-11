---
title: Ordenación, filtrado y descarga de datos mediante Inteligencia contra amenazas de Microsoft Defender (TI de Defender)
description: Obtenga información sobre cómo ordenar, filtrar y descargar datos mediante Inteligencia contra amenazas de Microsoft Defender (TI de Defender).
author: alexroland24
ms.author: aroland
ms.service: threat-intelligence
ms.topic: how-to
ms.date: 08/02/2022
ms.custom: template-how-to
ms.openlocfilehash: 36648d50033cb00893e9f973641f421274e6e3d8
ms.sourcegitcommit: 414682b9bf42dc19a89c893d3c515aee9765b6e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2022
ms.locfileid: "67280385"
---
# <a name="sorting-filtering-and-downloading-data"></a>Ordenar, filtrar y descargar datos

La plataforma Inteligencia contra amenazas de Microsoft Defender (Defender TI) permite a los analistas acceder a nuestra amplia colección de datos de rastreo en un formato de tabla indexada y dinámica.  Estos conjuntos de datos pueden ser muy grandes y devolver grandes cantidades de datos históricos y recientes. Por lo tanto, permitir que los analistas ordene y filtre adecuadamente los datos proporciona la capacidad de exponer fácilmente las conexiones de interés.

![Captura de pantalla de Chrome de ordenación de conjuntos de datos](media/sortingDataSetsChromeScreenshot.png)

En este artículo de procedimientos, aprenderá a ordenar y filtrar datos para los siguientes conjuntos de datos:

- Soluciones
- WHOIS
- Certificados
- Subdominios
- Seguidores
- Componentes
- Pares de host
- Hashes
- Cookies
- Servicios
- DNS
- DNS inverso

Para obtener más información, consulte [Conjuntos de datos](data-sets.md).

En este artículo de procedimientos, también aprenderá a descargar indicadores o artefactos de las siguientes características:

- Projects
- Artículos
- Conjuntos de datos

## <a name="prerequisites"></a>Requisitos previos

- Una cuenta de Azure Active Directory o microsoft personal. [Iniciar sesión o crear una cuenta](https://signup.microsoft.com/)
- Una licencia Premium de Inteligencia contra amenazas de Microsoft Defender (Defender TI).
    > [!NOTE]
    > Los usuarios sin una licencia de Defender TI Premium seguirán siendo capaces de iniciar sesión en el portal de Inteligencia sobre amenazas de Defender y acceder a nuestra oferta gratuita de TI de Defender.

## <a name="open-defender-tis-threat-intelligence-home-page"></a>Abrir la página principal de Inteligencia sobre amenazas de Defender TI

1. Acceda al [portal de Inteligencia sobre amenazas de Defender](https://ti.defender.microsoft.com/).
2. Complete la autenticación de Microsoft para acceder al portal.

## <a name="sorting-data"></a>Ordenación de datos

La función de ordenación de la pestaña Datos permite a los usuarios ordenar rápidamente los conjuntos de datos por los valores de columna. De forma predeterminada, la mayoría de los resultados se ordenan por "Última vista" (descendente) para que los resultados observados más recientemente aparezcan en la parte superior de la lista; esto muestra los datos más recientes para proporcionar información inmediata sobre la infraestructura actual de un artefacto. Actualmente, todos los conjuntos de datos se pueden ordenar mediante los siguientes valores "First Seen" y "Last Seen":

- Descendiendo por última vez (valor predeterminado)
- Ascendente visto por última vez
- Ascendente visto por primera vez
- Descendiendo por primera vez

Los datos se pueden ordenar en cada hoja del conjunto de datos de la pestaña Datos para cada dirección IP, dominio o entidad host en la que se busca o se dinamizará.

1. Busque un dominio, una dirección IP o un host en la barra de búsqueda de Inteligencia sobre amenazas de TI de Defender y vaya a la pestaña Datos.
2. Aplique las preferencias de ordenación a las columnas First Seen y Last Seen en la hoja Datos de resoluciones.

![Resoluciones de ordenación](media/sortingResolutions.gif)

## <a name="filtering-data"></a>Filtrado de datos

El filtrado de datos permite a los analistas acceder a un grupo selecto de datos en función de un valor de metadatos determinado. Por ejemplo, un analista puede seleccionar para ver solo las resoluciones IP detectadas desde un origen seleccionado o componentes de un tipo determinado (por ejemplo, servidores, marcos). Esto permite a los usuarios restringir los resultados de la consulta a elementos de interés particular. Puesto que la plataforma threat Intelligence proporciona metadatos específicos que coinciden con tipos de datos determinados, las opciones de filtro serán diferentes para cada conjunto de datos.

## <a name="resolution-filters"></a>Filtros de resolución

Los filtros siguientes se aplican a los datos de resolución:

- **Etiqueta del sistema**: estas etiquetas las crea el sistema de inteligencia sobre amenazas en función de la información detectada por nuestro equipo de investigación.
- **Etiqueta**: etiquetas que han aplicado los usuarios de Threat Intelligence.
- **ASN**: resultados relacionados con un número de sistema autónomo (ASN) designado.
- **Red**: resultados relacionados con la red designada.
- **Origen**: origen de datos que produjo el resultado (por ejemplo, riskiq, emerging_threats).

1. Busque un dominio, una dirección IP o un host en la barra de búsqueda de Inteligencia sobre amenazas de TI de Defender y vaya a la pestaña Datos.
2. Aplique filtros a cada uno de los tipos de opciones de filtro indicadas anteriormente en la hoja Datos de resoluciones.

![Filtros de resoluciones](media/filtersResolutions.gif)

## <a name="tracker-filters"></a>Filtros de seguimiento

Los filtros siguientes se aplican a los datos de seguimiento:

- **Tipo**: el tipo de seguimiento identificado para cada artefacto (por ejemplo, JarmFuzzyHash, GoogleAnalyticsID).
- **Dirección**: la dirección IP que observó directamente el rastreador o tiene un host de resolución que observó el seguimiento. (Aparece al buscar una dirección IP)
- **Nombre de host**: el host que observó este valor de seguimiento. (Aparece al buscar un dominio o host)

1. Busque un dominio, una dirección IP o un host en la barra de búsqueda de Inteligencia sobre amenazas de TI de Defender y vaya a la pestaña Datos.
2. Vaya a la hoja Datos de seguimiento.
3. Aplique filtros a cada uno de los tipos de opciones de filtro indicadas anteriormente en la hoja Datos de seguimiento.

![Filtros rastreadores](media/filtersTrackers.gif)

## <a name="component-filters"></a>Filtros de componentes

Los filtros siguientes se aplican a los datos del componente:

- **Ipaddressraw:** la dirección IP que coincide con el nombre de host devuelto.
- **Tipo:** el tipo de componente designado (por ejemplo, acceso remoto, sistema operativo).
- **Nombre:** el nombre del componente detectado (por ejemplo, Cobalt Strike, PHP).

1. Busque un dominio, una dirección IP o un host en la barra de búsqueda de Inteligencia sobre amenazas de TI de Defender y vaya a la pestaña Datos.
2. Vaya a la hoja Datos de componentes.
3. Aplique filtros a cada uno de los tipos de opciones de filtro indicadas anteriormente en la hoja Datos de componentes.

![Filtros de componentes](media/filtersComponents.gif)

## <a name="host-pair-filters"></a>Filtros de par de host

Los filtros siguientes se aplican a los datos del par de hosts:

- **Dirección:** dirección de la conexión observada. Esto indica si el elemento primario redirige al elemento secundario o viceversa.
- **Nombre de host primario:** nombre de host del artefacto primario.
- **Causa:** la causa detectada de la relación principal/secundaria del host (por ejemplo, redirección, iframe.src).
- **Nombre de host secundario:** nombre de host del artefacto secundario.

1. Busque un dominio, una dirección IP o un host en la barra de búsqueda de Inteligencia sobre amenazas de TI de Defender y vaya a la pestaña Datos.
2. Vaya a la hoja Datos de pares de host.
3. Aplique filtros a cada uno de los tipos de opciones de filtro indicadas anteriormente en la hoja Datos de pares de host.

![Filtros de pares de host](media/filtersHostPairs.gif)

## <a name="dns--reverse-dns-filters"></a>Filtros DNS & inversos

Los filtros siguientes se aplican a los datos DNS y DNS inversos:

- **Tipo** de registro: el tipo de registro detectado en el registro DNS (por ejemplo, NS, CNAME).
- **Valor:** el valor designado del registro (por ejemplo, nameserver.host.com).

1. Busque un dominio, una dirección IP o un host en la barra de búsqueda de Inteligencia sobre amenazas de TI de Defender y vaya a la pestaña Datos.
2. Vaya a las hojas DNS y versiones posteriores de Datos DNS inversos.
3. Aplique filtros a cada uno de los tipos de opciones de filtro indicadas anteriormente en las hojas DNS e Reverse DNS Data (Datos DNS inversos).

![Filtra DNS](media/filtersDNS.gif)

## <a name="downloading-data"></a>Descarga de datos

En TI de Defender, hay varias secciones en las que un usuario puede descargar datos como exportación csv.   Los usuarios deben buscar el icono de descarga para exportar datos como un csv.

![Icono de descarga](media/downloadIcon.png)

Los datos se pueden descargar en las secciones siguientes:

- La mayoría de las hojas del conjunto de datos
- Project
- Artículo de inteligencia sobre amenazas

Los encabezados siguientes se exportan como resultado de la descarga de resoluciones, DNS y datos DNS inversos:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **Resolver**                | Registro asociado al dominio buscado (resolución de dirección IP) o dominio que se ha resuelto en una dirección IP cuando se busca una dirección IP. |
| **Ubicación**               | País en el que se hospeda la dirección IP |
| **Red**                | Netblock o subred |
| **autonomousSystemNumber** | Número del sistema autónomo |
| **firstSeen**              | Fecha y hora en que Microsoft observó por primera vez la resolución (formato: mm/dd/aaaa hh:mm) |
| **lastSeen**               | Fecha y hora en que Microsoft observó por última vez la resolución (formato: mm/dd/aaaa hh:mm) |
| **Source**                 | Origen que observó esta resolución |
| **Tags**                   | Etiquetas personalizadas o del sistema asociadas al artefacto |

Los encabezados siguientes se exportan como resultado de la descarga de datos de subdominios:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **hostname**               | Subdominio del dominio buscado |
| **Etiquetas**                   | Etiquetas personalizadas o del sistema asociadas al artefacto |

Los encabezados siguientes se exportan como resultado de la descarga de datos de Trackers:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **hostname**               | Nombre de host que observó o está observando actualmente el rastreador |
| **firstSeen**              | Fecha y hora en que Microsoft observó por primera vez que el nombre de host usaba el rastreador (formato: mm/dd/aaaa hh:mm) |
| **lastSeen**               | Fecha y hora en que Microsoft observó por primera vez que el nombre de host usaba el rastreador (formato: mm/dd/aaaa hh:mm) |
| **Attributetype**          | Tipo de seguimiento |
| **attributeValue**         | Valor de seguimiento |
| **Tags**                   | Etiquetas personalizadas o del sistema asociadas al artefacto |

Los encabezados siguientes se exportan como resultado de la descarga de datos de componentes:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **hostname**               | Nombre de host que observó o está observando actualmente el componente |
| **firstSeen**              | Fecha y hora en que Microsoft observó por primera vez que el nombre de host usaba el rastreador (formato: mm/dd/aaaa hh:mm |
| **lastSeen**               | Fecha y hora en que Microsoft observó por última vez que el nombre de host usaba el componente (formato: mm/dd/aaaa hh:mm |
| **Categoría**               | Tipo de componente |
| **name**                   | Nombre del componente |
| **version**                | Versión del componente |
| **Tags**                   | Etiquetas personalizadas o del sistema asociadas al artefacto |

Los encabezados siguientes se exportan como resultado de la descarga de datos de pares de host:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **parentHostname**         | Nombre de host que se está llegando al nombre de host secundario |
| **childHostname**          | Nombre de host que alimenta los recursos que hospedan al nombre de host primario. |
| **firstSeen**              | Fecha y hora en que Microsoft observó por primera vez la relación entre el nombre de host primario y secundario (formato: mm/dd/aaaa hh:mm) |
| **lastSeen**               | Fecha y hora en que Microsoft observó por última vez la relación entre el nombre de host primario y el secundario (formato: mm/dd/aaaa hh:mm) |
| **attributeCause**         | Causa de la relación entre el nombre de host primario y secundario |
| **Tags**                   | Etiquetas personalizadas o del sistema asociadas al artefacto |

Los encabezados siguientes se exportan como resultado de la descarga de datos Hashes:

| &nbsp;             | &nbsp;                     |
|--------------------|----------------------------|
| **source**         | Origen que observó el ejemplo de hash MD5 |
| **Muestra**                  | Hash md5 |
| **fecha de recopilación**         | Fecha de recopilación capturada por el origen |

Los encabezados siguientes se exportan como resultado de la descarga de datos de cookies:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **hostname**               | Nombre de host que observó el nombre de la cookie |
| **firstSeen**              | Cuando se observó por primera vez el nombre de cookie en el nombre de host que se originó en el dominio de cookies (formato: mm/dd/aaaa hh:mm) |
| **lastSeen**               | Fecha y hora en que se observó por última vez el nombre de cookie en el nombre de host que se originó en el dominio de cookies (formato: mm/dd/aaaa hh:mm) |
| **cookieName**             | Nombre de la cookie |
| **cookieDomain**           | Servidor del nombre de dominio del que se originó el nombre de la cookie |
| **Tags**                   | Etiquetas personalizadas o del sistema asociadas al artefacto |

Los encabezados siguientes se exportan como resultado de la descarga de listas de proyectos para mis proyectos compartidos, equipos y :

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **name**                   | Nombre del proyecto |
| **artefactos (recuento)**      | Recuento de artefactos dentro del proyecto |
| **creado por (usuario)**      | Usuario que creó el proyecto |
| **creado en**             | Cuando se creó el proyecto |
| **Etiquetas**                   | Etiquetas personalizadas o del sistema asociadas al artefacto |
| **Colaboradores**          | Quién se ha agregado como colaborador(s) al proyecto. Esto solo es visible para los proyectos que se han descargado de las páginas Mis proyectos y Proyectos compartidos. |

Los encabezados siguientes se exportan como resultado de la descarga de detalles del proyecto (artefactos) de un proyecto:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **Artefacto**               | Valor del artefacto (por ejemplo, dirección IP, dominio, host, valor WHOIS, certificado SHA-1, etc.) |
| **type**                   | Tipo de artefacto (por ejemplo, IP, dominio, host, organización WHOIS, teléfono WHOIS, certificado SHA-1, etc.) |
| **Creado**                | Fecha y hora en que se agregó el artefacto al proyecto (formato: mm/dd/aaaa hh:mm) |
| **creador**                | Email dirección del usuario que agregó el artefacto |
| **context**                | Cómo se agregó el artefacto al proyecto |
| **Etiquetas**                   | Etiquetas personalizadas o del sistema asociadas al artefacto |
| **Colaboradores**          | Quién se ha agregado como colaborador(s) al proyecto. Esto solo es visible para los proyectos que se han descargado de las páginas Mis proyectos y Proyectos compartidos. |

Los encabezados siguientes se exportan como resultado de la descarga de indicadores de inteligencia sobre amenazas pública o riskiq:

| &nbsp;                     | &nbsp;                     |
|----------------------------|----------------------------|
| **type**                | Tipo de indicador (por ejemplo, ip, certificado, dominio, hash_sha256) |
| **value**               | Valor del indicador (por ejemplo, dirección IP, dominio, nombre de host) |
| **source**              | Origen del indicador (RiskIQ o OSINT) |

## <a name="next-steps"></a>Siguientes pasos

Para obtener más información, consulte [Conjuntos de datos](data-sets.md).
