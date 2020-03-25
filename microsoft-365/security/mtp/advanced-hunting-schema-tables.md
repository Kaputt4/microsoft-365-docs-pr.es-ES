---
title: Tablas de datos del esquema de la búsqueda avanzada en la Protección contra amenazas de Microsoft
description: Obtenga información sobre las tablas del esquema de búsqueda avanzada para saber sobre qué datos puede ejecutar consultas de búsqueda avanzada de amenazas.
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, datos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 0b28cf2ce96e4c040fac0999d669623cef066fe4
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929497"
---
# <a name="understand-the-advanced-hunting-schema"></a>Descripción del esquema de búsqueda avanzada

**Se aplica a:**
- Protección contra amenazas de Microsoft



El esquema de [búsqueda avanzada](advanced-hunting-overview.md) se compone de varias tablas que proporcionan información de eventos o información sobre equipos y entidades. Para crear consultas eficaces que abarquen varias tablas, debe comprender las tablas y las columnas del esquema de búsqueda avanzada.

## <a name="schema-tables"></a>Tablas del esquema

A continuación se enumeran todas las tablas del esquema. Cada nombre de tabla está vinculado a una página donde se describen los nombres de las columnas de esa tabla. Los nombres de tabla y columna se muestran también en el centro de seguridad como parte de la representación del esquema en la pantalla de la búsqueda avanzada.

| Nombre de tabla | Descripción |
|------------|-------------|
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Alertas de ATP de Microsoft defender, Office 365 ATP, Microsoft Cloud App Security y Azure ATP, incluida la información de gravedad y la categorización de amenazas  |
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Archivos, direcciones IP, URL, usuarios o dispositivos asociados con alertas |
| **[AccountInfo](advanced-hunting-accountinfo-table.md)** | Información de cuenta de varios orígenes, incluido Azure Active Directory |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Eventos de correo electrónico de Office 365, incluidos los eventos de bloqueo y entrega de correo electrónico |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Información sobre los archivos adjuntos de los correos electrónicos de Office 365 |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Información sobre las direcciones URL de los correos electrónicos de Office 365 |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Información del equipo, incluida la información del sistema operativo |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Propiedades de red de equipos, incluidos adaptadores, direcciones IP y MAC, así como redes y dominios conectados |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Creación de procesos y eventos relacionados |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Conexión de red y eventos relacionados |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Creación y modificación de archivos y otros eventos del sistema de archivos |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Creación y modificación de entradas de registro |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Inicios de sesión y otros eventos de autenticación |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | Eventos de carga de DLL |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Varios tipos de eventos, incluidos los eventos desencadenados por controles de seguridad como el Antivirus de Windows Defender y la protección contra vulnerabilidades |
| **[DeviceFileCertificateInfoBeta](advanced-hunting-devicefilecertificateinfobeta-table.md)** | Información de certificado de archivos firmados obtenidos de los eventos de comprobación de certificados en los extremos |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)** | Inventario del software de los dispositivos, así como de cualquier vulnerabilidad conocida de esos productos de software. |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)** | La base de conocimiento de vulnerabilidades de la que se ha informado públicamente, incluyendo si el código que aprovecha la vulnerabilidad está disponible para el público |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)** | Eventos de evaluación de administración de amenazas y vulnerabilidades, donde se indica el estado de las distintas configuraciones de seguridad de los dispositivos |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)** | Base de conocimiento de las configuraciones de seguridad utilizadas por la administración de amenazas y vulnerabilidades para evaluar dispositivos, incluidas las asignaciones a diferentes estándares y criterios de referencia  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Actividades relacionadas con archivos en aplicaciones y servicios en la nube |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Eventos de autenticación registrados por Active Directory y otros servicios de Microsoft online |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Actividades de consulta realizadas en objetos de Active Directory, como usuarios, grupos, dispositivos y dominios |


## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
