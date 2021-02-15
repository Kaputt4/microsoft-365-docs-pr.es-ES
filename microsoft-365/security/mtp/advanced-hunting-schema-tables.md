---
title: Tablas de datos del esquema de búsqueda avanzada de Microsoft 365 Defender
description: Obtenga información sobre las tablas del esquema de búsqueda avanzada para saber sobre qué datos puede ejecutar consultas de búsqueda avanzada de amenazas.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, datos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b335ba90479c670d918226caa18f80ee5535f0a1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925068"
---
# <a name="understand-the-advanced-hunting-schema"></a>Descripción del esquema de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

El [esquema de búsqueda](advanced-hunting-overview.md) avanzada está configurado por varias tablas que proporcionan información de eventos o información sobre dispositivos, alertas, identidades y otros tipos de entidad. Para crear consultas eficaces que abarquen varias tablas, debe comprender las tablas y las columnas del esquema de búsqueda avanzada.

## <a name="get-schema-information-in-the-security-center"></a>Obtener información de esquema en el centro de seguridad
Durante la construcción de consultas, use la referencia de esquema integrada para obtener rápidamente la siguiente información sobre cada tabla del esquema:

- **Descripción de** las tablas: tipo de datos contenidos en la tabla y el origen de los datos.
- **Columnas:** todas las columnas de la tabla.
- **Tipos de acción:** valores posibles en `ActionType` la columna que representa los tipos de evento admitidos por la tabla. Esta información solo se proporciona para las tablas que contienen información de eventos.
- **Consulta de ejemplo:** consultas de ejemplo que ofrecen cómo se puede usar la tabla.

### <a name="access-the-schema-reference"></a>Obtener acceso a la referencia de esquema
Para obtener acceso rápidamente a la referencia de esquema, seleccione la acción Ver **referencia** junto al nombre de la tabla en la representación del esquema. También puede seleccionar la **referencia de esquema** para buscar una tabla.   

![Imagen que muestra cómo obtener acceso a la referencia de esquema en el portal ](../../media/mtp-ah/ah-reference.png) 

## <a name="learn-the-schema-tables"></a>Obtenga información sobre las tablas de esquema
A continuación se enumeran todas las tablas del esquema. Cada nombre de tabla está vinculado a una página donde se describen los nombres de las columnas de esa tabla. Los nombres de tabla y columna también se enumeran en el centro de seguridad como parte de la representación del esquema en la pantalla de búsqueda avanzada.

| Nombre de tabla | Descripción |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Archivos, direcciones IP, direcciones URL, usuarios o dispositivos asociados con alertas |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Alertas de Microsoft Defender para Endpoint, Microsoft Defender para Office 365, Microsoft Cloud App Security y Microsoft Defender para Identity, incluida la información de gravedad y la categorización de amenazas  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Actividades relacionadas con archivos en servicios y aplicaciones en la nube |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Eventos que implican cuentas y objetos en Office 365 y otros servicios y aplicaciones en la nube |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Varios tipos de eventos, incluidos los eventos desencadenados por controles de seguridad como el Antivirus de Windows Defender y la protección contra vulnerabilidades |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Información de certificado de archivos firmados obtenidos de eventos de comprobación de certificados en puntos de conexión |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Creación y modificación de archivos y otros eventos del sistema de archivos |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | Eventos de carga de DLL |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Información del equipo, incluida la información del sistema operativo |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Inicios de sesión y otros eventos de autenticación en dispositivos |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Conexión de red y eventos relacionados |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Propiedades de red de dispositivos, incluidos adaptadores físicos, direcciones IP y MAC, así como redes y dominios conectados |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Creación de procesos y eventos relacionados |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Creación y modificación de entradas de registro |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Eventos de evaluación de administración de amenazas y vulnerabilidades, donde se indica el estado de las distintas configuraciones de seguridad de los dispositivos |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Base de conocimiento de las configuraciones de seguridad utilizadas por la administración de amenazas y vulnerabilidades para evaluar dispositivos, incluidas las asignaciones a diferentes estándares y criterios de referencia  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | Inventario de software en dispositivos y vulnerabilidades conocidas en estos productos de software |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | La base de conocimiento de vulnerabilidades de la que se ha informado públicamente, incluyendo si el código que aprovecha la vulnerabilidad está disponible para el público |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Información sobre los archivos adjuntos a los correos electrónicos |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Eventos de correo electrónico de Microsoft 365, incluidos los eventos de entrega y bloqueo de correo electrónico |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Eventos de seguridad que se producen después de la entrega, después de que Microsoft 365 haya entregado los correos electrónicos al buzón del destinatario |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Información sobre las direcciones URL de los correos electrónicos |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Eventos que implican a un controlador de dominio local que ejecuta Active Directory (AD). En esta tabla se trata una serie de eventos relacionados con la identidad y eventos del sistema en el controlador de dominio. |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Información de cuenta de varios orígenes, incluido Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Eventos de autenticación en Active Directory y servicios en línea de Microsoft |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Consultas de objetos de Active Directory, como usuarios, grupos, dispositivos y dominios |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
