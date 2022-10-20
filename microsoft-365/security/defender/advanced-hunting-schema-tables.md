---
title: Tablas de datos del esquema de búsqueda avanzada Microsoft 365 Defender
description: Obtenga información sobre las tablas del esquema de búsqueda avanzada para saber sobre qué datos puede ejecutar consultas de búsqueda avanzada de amenazas.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, datos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.openlocfilehash: 2fb0ebc9b3bc095a7cf0eb76fe4440283e175b7f
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68639585"
---
# <a name="understand-the-advanced-hunting-schema"></a>Descripción del esquema de búsqueda avanzada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

El esquema de [búsqueda avanzada](advanced-hunting-overview.md) se compone de varias tablas que proporcionan información de eventos o información sobre dispositivos, alertas, identidades y otros tipos de entidad. Para crear consultas eficaces que abarquen varias tablas, debe comprender las tablas y las columnas del esquema de búsqueda avanzada.

<a name="get-schema-information-in-the-security-center"></a>

## <a name="get-schema-information"></a>Obtener información de esquema

Al crear consultas, use la referencia de esquema integrada para obtener rápidamente la siguiente información sobre cada tabla del esquema:

- **Descripción de las tablas**: tipo de datos contenidos en la tabla y el origen de esos datos.
- **Columnas**: todas las columnas de la tabla.
- **Tipos de acción**: valores posibles en la `ActionType` columna que representan los tipos de evento admitidos por la tabla. Esta información solo se proporciona para las tablas que contienen información de eventos.
- **Consulta de** ejemplo: consultas de ejemplo que incluyen cómo se puede usar la tabla.

### <a name="access-the-schema-reference"></a>Acceso a la referencia de esquema
Para acceder rápidamente a la referencia de esquema, seleccione la acción **Ver referencia** junto al nombre de la tabla en la representación del esquema. También puede seleccionar **Referencia de esquema** para buscar una tabla.

:::image type="content" source="../../media/understand-schema-1.png" alt-text="La página Referencia de esquema de la página Búsqueda avanzada del portal de Microsoft 365 Defender" lightbox="../../media/understand-schema-1.png":::

## <a name="learn-the-schema-tables"></a>Obtenga información sobre las tablas de esquema
A continuación se enumeran todas las tablas del esquema. Cada nombre de tabla está vinculado a una página donde se describen los nombres de las columnas de esa tabla. Los nombres de tabla y columna también se muestran en Defender for Cloud como parte de la representación de esquema en la pantalla de búsqueda avanzada.

| Nombre de tabla | Descripción |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Archivos, direcciones IP, direcciones URL, usuarios o dispositivos asociados a alertas |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Alertas de Microsoft Defender para punto de conexión, Microsoft Defender para Office 365, Microsoft Defender for Cloud Apps y Microsoft Defender for Identity , incluida la información de gravedad y la categorización de amenazas  |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Eventos relacionados con cuentas y objetos en Office 365 y otras aplicaciones y servicios en la nube |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Varios tipos de eventos, incluidos los eventos desencadenados por controles de seguridad, como Microsoft Defender Antivirus y protección contra vulnerabilidades de seguridad |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Información de certificados de archivos firmados obtenidos de los eventos de comprobación de certificados en puntos de conexión |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Creación y modificación de archivos y otros eventos del sistema de archivos |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | Eventos de carga de DLL |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Información del equipo, incluida la información del sistema operativo |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Inicios de sesión y otros eventos de autenticación en dispositivos |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Conexión de red y eventos relacionados |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Propiedades de red de dispositivos, incluyendo adaptadores físicos, direcciones IP y MAC, así como redes y dominios conectados |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Creación de procesos y eventos relacionados |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Creación y modificación de entradas de Registro |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Administración de vulnerabilidades de Microsoft Defender eventos de evaluación, que indican el estado de varias configuraciones de seguridad en los dispositivos |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Base de conocimiento de varias configuraciones de seguridad usadas por Administración de vulnerabilidades de Microsoft Defender para evaluar dispositivos; incluye asignaciones a diversos estándares y pruebas comparativas  |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | Inventario del software instalado en dispositivos, incluida la información de la versión y el estado de finalización del soporte técnico |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | Vulnerabilidades de software encontradas en los dispositivos y lista de actualizaciones de seguridad disponibles que abordan cada vulnerabilidad |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | La base de conocimiento de vulnerabilidades de la que se ha informado públicamente, incluyendo si el código que aprovecha la vulnerabilidad está disponible para el público |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Información sobre los archivos adjuntos a los correos electrónicos |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Eventos de correo electrónico de Microsoft 365, incluidos los eventos de bloqueo y entrega de correo electrónico |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Eventos de seguridad que se producen después de la entrega, una vez que Microsoft 365 ha entregado ya los correos electrónicos al buzón del destinatario |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Información sobre las direcciones URL de los correos electrónicos |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Eventos que implican un controlador de dominio local que ejecuta Active Directory (AD). En esta tabla se describen una serie de eventos relacionados con la identidad y eventos del sistema en el controlador de dominio. |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Información de la cuenta de varios orígenes, incluyendo Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Eventos de autenticación en Active Directory y en servicios en línea de Microsoft |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Consultas sobree objetos de Active Directory, como usuarios, grupos, dispositivos y dominios |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
