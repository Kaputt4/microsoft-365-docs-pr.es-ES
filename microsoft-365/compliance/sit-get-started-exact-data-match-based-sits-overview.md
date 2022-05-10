---
title: Introducción a los tipos de información confidencial basados en las coincidencias exactas de datos
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Comenzar crear tipos de información confidencial basados en coincidencias exactas de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 592a4c7342af9ffe5c18d0d25b99b12cd1b3e212
ms.sourcegitcommit: f723ebbc56db8013598a88b0d7f13214d9d3eb10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2022
ms.locfileid: "65294677"
---
# <a name="get-started-with-exact-data-match-based-sensitive-information-types"></a>Introducción a los tipos de información confidencial basados en las coincidencias exactas de datos

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

La creación y puesta a disposición de un tipo de información confidencial (SIT) basado en una coincidencia exacta de datos (EDM) es un proceso de varias fases. Se pueden usar en las directivas de prevención de pérdida de datos de Microsoft Purview, eDiscovery y ciertas tareas de gobernanza de contenido Este artículo describe el flujo de trabajo y los vínculos a los procedimientos para cada una de las fases.

## <a name="before-you-begin"></a>Antes de empezar

Familiarícese con los conceptos y terminología de estos artículos:

- [Obtener más información acerca de los tipos de información confidencial](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)

## <a name="supported-regions"></a>Regiones admitidas

La coincidencia exacta de datos está disponible en estas regiones:

- Asia Pacífico
- Australia
- Brasil
- Canadá
- Europa
- Francia
- Alemania
- India
- Japón
- Corea
- Noruega
- Sudáfrica
- Suiza
- Emiratos Árabes Unidos
- Reino Unido
- Estados Unidos
- DoD de EE. UU.
- GCC de EE. UU.
- GCCH de EE. UU.

Puede averiguar en qué región hospeda el inquilino los datos en reposo siguiendo los procedimientos descritos en [Where your Microsoft 365 customer data is stored](../enterprise/o365-data-locations.md) and refer to the data center city locations in the same article (Dónde se almacenan los datos de Microsoft 365 cliente) y haciendo referencia a las ubicaciones de la ciudad del centro de datos en el mismo artículo.

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Debe ser un administrador global, administrador de cumplimiento o administrador de Exchange Online para realizar las tareas descritas en este artículo. Para obtener más información acerca de los permisos de DLP, consulte [Permisos](data-loss-prevention-policies.md#permissions).

Consulte la [descripción del servicio de prevención de pérdida de datos](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business) para obtener información completa sobre las licencias.

## <a name="portal-links-for-your-subscription"></a>Vínculos del portal para la suscripción

|Portal|World Wide/GCC|GCC-High|DOD|
|---|---|---|---|
|Office SCC|compliance.microsoft.com|scc.office365.us|scc.protection.apps.mil|
|Portal de Microsoft 365 Defender|security.microsoft.com|security.microsoft.us|security.apps.mil|
|Portal de cumplimiento de Microsoft Purview.|compliance.microsoft.com|compliance.microsoft.us|compliance.apps.mil|

## <a name="the-work-flow-at-a-glance"></a>El flujo de trabajo de un vistazo

![coincidencia exacta de datos con las fases de flujo de trabajo](..\media\swimlane_edm_process.png)


|Fase|Requisitos|
|---|---|
|[Fase 1: Exportación de datos de origen para el tipo de información confidencial basada en coincidencias exactas de datos](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)|- Acceso de lectura a los datos confidenciales|
|[Fase 2: Creación del esquema para tipos de información confidencial basados en coincidencias de datos exactas](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)|- Acceso al asistente para tipos de información confidencial en el Centro de administración de Microsoft 365 </br>: acceso a [Centro de administración de Microsoft 365 a través de PowerShell de cumplimiento de seguridad &](/powershell/exchange/connect-to-scc-powershell) |
|[Fase 3: Hash y carga de la tabla de origen de información confidencial para obtener datos exactos que coincidan con tipos de información confidencial](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)|- Cuenta de usuario y de grupo de seguridad personalizado </br>- **Hash y carga desde un equipo**: acceso de administrador local a un equipo con acceso directo a Internet y para hospedar el agente de Upload de EDM </br>- **Hash y carga desde equipos independientes**: acceso de administrador local a un equipo con acceso directo a Internet y hospedar el agente de Upload EDM para la carga y el acceso de administrador local a un equipo seguro para hospedar el agente de Upload EDM para aplicar hash a la tabla de origen de información confidencial </br>- Acceso de lectura al archivo de tabla de origen de información confidencial </br> el archivo de esquema |
|[Fase 4: Creación de un paquete de reglas o tipo de información confidencial que coincida con datos exactos](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package) |- Acceso al portal de cumplimiento de Microsoft Purview |
|[Probar un tipo de información confidencial de coincidencia exacta de datos](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)| - Acceso al portal de cumplimiento de Microsoft Purview

## <a name="see-also"></a>Consulte también

- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [Exportar datos de origen para el tipo de información confidencial basada en la coincidencia exacta de datos](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
