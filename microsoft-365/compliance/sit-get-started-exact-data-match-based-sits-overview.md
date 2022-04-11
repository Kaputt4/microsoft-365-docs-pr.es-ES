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
ms.openlocfilehash: 0f221ba0521a50f484bfb9a8d5030e33b495c495
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2022
ms.locfileid: "64759753"
---
# <a name="get-started-with-exact-data-match-based-sensitive-information-types"></a>Introducción a los tipos de información confidencial basados en las coincidencias exactas de datos

La creación y puesta a disposición de un tipo de información confidencial (SIT) basado en una coincidencia exacta de datos (EDM) es un proceso de varias fases. Se pueden usar en directivas de prevención de pérdida de datos, eDiscovery y ciertas tareas de gobernanza de contenido En este artículo se describen el flujo de trabajo y los vínculos a los procedimientos para cada una de las fases.

## <a name="before-you-begin"></a>Antes de empezar

Familiarícese con los conceptos y terminología de estos artículos:

- [Obtener más información acerca de los tipos de información confidencial](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Debe ser un administrador global, administrador de cumplimiento o administrador de Exchange Online para realizar las tareas descritas en este artículo. Para obtener más información acerca de los permisos de DLP, consulte [Permisos](data-loss-prevention-policies.md#permissions).

Consulte la [descripción del servicio de prevención de pérdida de datos](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business) para obtener información completa sobre las licencias.

## <a name="portal-links-for-your-subscription"></a>Vínculos del portal para la suscripción

|Portal|World Wide/GCC|GCC-High|DOD|
|---|---|---|---|
|Office SCC|compliance.microsoft.com|scc.office365.us|scc.protection.apps.mil|
|Portal de Microsoft 365 Defender|security.microsoft.com|security.microsoft.us|security.apps.mil|
|Centro de cumplimiento de Microsoft 365|compliance.microsoft.com|compliance.microsoft.us|compliance.apps.mil|

## <a name="the-work-flow-at-a-glance"></a>El flujo de trabajo de un vistazo

![coincidencia exacta de datos con las fases de flujo de trabajo](..\media\swimlane_edm_process.png)


|Fase|Requisitos|
|---|---|
|[Fase 1: Exportación de datos de origen para el tipo de información confidencial basada en coincidencias exactas de datos](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)|- Acceso de lectura a los datos confidenciales|
|[Fase 2: Creación del esquema para tipos de información confidencial basados en coincidencias de datos exactas](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)|- Acceso al asistente para tipos de información confidencial en el Centro de administración de Microsoft 365 </br>: acceso a [Centro de administración de Microsoft 365 a través de PowerShell de cumplimiento de seguridad &](/powershell/exchange/connect-to-scc-powershell) |
|[Fase 3: Hash y carga de la tabla de origen de información confidencial para obtener datos exactos que coincidan con tipos de información confidencial](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)|- Cuenta de usuario y de grupo de seguridad personalizado </br>- **Hash y carga desde un equipo**: acceso de administrador local a un equipo con acceso directo a Internet y para hospedar el agente de Upload de EDM </br>- **Hash y carga desde equipos independientes**: acceso de administrador local a un equipo con acceso directo a Internet y hospedar el agente de Upload EDM para la carga y el acceso de administrador local a un equipo seguro para hospedar el agente de Upload EDM para aplicar hash a la tabla de origen de información confidencial </br>- Acceso de lectura al archivo de tabla de origen de información confidencial </br> el archivo de esquema |
|[Fase 4: Creación de un paquete de reglas o tipo de información confidencial que coincida con datos exactos](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package) |- Acceso al Centro de cumplimiento de Microsoft 365 |
|[Probar un tipo de información confidencial de coincidencia exacta de datos](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)| - Acceso al Centro de cumplimiento de Microsoft 365

## <a name="see-also"></a>Vea también

- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [Exportar datos de origen para el tipo de información confidencial basada en la coincidencia exacta de datos](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
