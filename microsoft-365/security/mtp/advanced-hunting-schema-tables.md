---
title: Tablas de datos del esquema de la búsqueda avanzada en la Protección contra amenazas de Microsoft
description: Obtenga información sobre las tablas del esquema de búsqueda avanzada para saber sobre qué datos puede ejecutar consultas de búsqueda avanzada de amenazas.
keywords: búsqueda avanzada, búsqueda avanzada de amenazas, búsqueda avanzada de amenazas cibernéticas, búsqueda, consulta, telemetría, referencia del esquema, kusto, tabla, columna, datos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 631b328168003668ed06e37d76177c327794ed18
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808665"
---
# <a name="understand-the-advanced-hunting-schema"></a>Descripción del esquema de búsqueda avanzada

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

El esquema de [búsqueda avanzada](advanced-hunting-overview.md) se compone de varias tablas que proporcionan información de eventos o información sobre equipos y entidades. Para crear consultas eficaces que abarquen varias tablas, debe comprender las tablas y las columnas del esquema de búsqueda avanzada.

## <a name="schema-tables"></a>Tablas del esquema

A continuación se enumeran todas las tablas del esquema. Cada nombre de tabla está vinculado a una página donde se describen los nombres de las columnas de esa tabla. Los nombres de tabla y columna se muestran también en el centro de seguridad como parte de la representación del esquema en la pantalla de la búsqueda avanzada.

| Nombre de tabla | Descripción |
|------------|-------------|
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Información del equipo, incluida la información del sistema operativo |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Propiedades de red de equipos, incluidos adaptadores, direcciones IP y MAC, así como redes y dominios conectados |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Creación de procesos y eventos relacionados |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Conexión de red y eventos relacionados |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Creación y modificación de archivos y otros eventos del sistema de archivos |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Creación y modificación de entradas de registro |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Inicios de sesión y otros eventos de autenticación |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | Eventos de carga de DLL |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Varios tipos de eventos, incluidos los eventos desencadenados por controles de seguridad como el Antivirus de Windows Defender y la protección contra vulnerabilidades |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Eventos de correo electrónico de Office 365, incluidos los eventos de bloqueo y entrega de correo electrónico |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Información sobre los archivos adjuntos de los correos electrónicos de Office 365 |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Información sobre las direcciones URL de los correos electrónicos de Office 365 |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)** | Inventario del software de los dispositivos, así como de cualquier vulnerabilidad conocida de esos productos de software. |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)** | La base de conocimiento de vulnerabilidades de la que se ha informado públicamente, incluyendo si el código que aprovecha la vulnerabilidad está disponible para el público |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)** | Eventos de evaluación de administración de amenazas y vulnerabilidades, donde se indica el estado de las distintas configuraciones de seguridad de los dispositivos |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)** | Base de conocimiento de las configuraciones de seguridad utilizadas por la administración de amenazas y vulnerabilidades para evaluar dispositivos, incluidas las asignaciones a diferentes estándares y criterios de referencia  |

## <a name="related-topics"></a>Temas relacionados
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
