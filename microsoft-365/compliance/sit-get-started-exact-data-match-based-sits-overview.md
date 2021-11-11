---
title: Introducción a tipos exactos de información confidencial basada en coincidencias de datos
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Introducción a la creación de tipos exactos de información confidencial basada en coincidencias de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3621ccdedb5966ae7c70e549c5f0538143df0248
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914872"
---
# <a name="get-started-with-exact-data-match-based-sensitive-information-types"></a>Introducción a tipos exactos de información confidencial basada en coincidencias de datos

Crear y hacer disponible un tipo de información confidencial basado en EDM (EDM) exacto es un proceso de varias fases. Se pueden usar en directivas de prevención de pérdida de datos, exhibición de documentos electrónicos y determinadas tareas de gobierno de contenido En este artículo se describen el flujo de trabajo y los vínculos a los procedimientos para cada una de las fases

## <a name="before-you-begin"></a>Antes de empezar

Familiarícese con los conceptos y la terminología de estos artículos:

- [Obtener más información acerca de los tipos de información confidencial](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [Obtenga información sobre tipos de información confidencial basada en coincidencias de datos exactas](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Debe ser un administrador global, administrador de cumplimiento o administrador de Exchange Online para realizar las tareas descritas en este artículo. Para obtener más información acerca de los permisos de DLP, consulte [Permisos](data-loss-prevention-policies.md#permissions).

Vea la [descripción del servicio de prevención de pérdida](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business) de datos para obtener información completa sobre licencias

## <a name="portal-links-for-your-subscription"></a>Vínculos del portal para la suscripción

|Portal|World Wide/GCC|GCC-High|DOD|
|---|---|---|---|
|Office SCC|compliance.microsoft.com|scc.office365.us|scc.protection.apps.mil|
|Centro de seguridad de Microsoft 365|security.microsoft.com|security.microsoft.us|security.apps.mil|
|Centro de cumplimiento de Microsoft 365|compliance.microsoft.com|compliance.microsoft.us|compliance.apps.mil|

## <a name="the-work-flow-at-a-glance"></a>El flujo de trabajo de un vistazo

![fases exactas de flujo de trabajo de coincidencia de datos](..\media\swimlane_edm_process.png)


|Fase|Requisitos|
|---|---|
|[Fase 1: Exportar datos de origen para el tipo exacto de información confidencial basada en coincidencias de datos](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)|- Acceso de lectura a los datos confidenciales|
|[Fase 2: Crear el esquema para tipos exactos de información confidencial basada en coincidencias de datos](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)|- Acceso al asistente para tipos de información confidencial en el Centro de administración de Microsoft 365 </br>- acceso a [Centro de administración de Microsoft 365 a través de PowerShell de & cumplimiento](/powershell/exchange/connect-to-scc-powershell) |
|[Fase 3: Hash y carga la tabla de origen de información confidencial para los tipos de información confidencial de coincidencia de datos exactos](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)|- Cuenta de usuario y de grupo de seguridad personalizado </br>- **Hash y carga desde un equipo:** acceso de administrador local a un equipo con acceso directo a Internet y para hospedar el agente de Upload EDM </br>- **Hash y carga** desde equipos independientes: acceso de administrador local a un equipo con acceso directo a Internet y hospedar el agente de Upload de EDM para la carga y el acceso de administrador local a un equipo seguro para hospedar el agente de Upload de EDM para hash de la tabla de origen de información confidencial </br>- Acceso de lectura al archivo de tabla de origen de información confidencial </br> el archivo de esquema |
|[Fase 4: Crear un paquete de regla o tipo de información confidencial de coincidencia de datos exactos](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package) |- Acceso al Centro de Microsoft 365 cumplimiento |
|[Probar un tipo de información confidencial de coincidencia exacta de datos](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)| - Acceso al Centro de Microsoft 365 cumplimiento

## <a name="see-also"></a>Consulte también

- [Obtenga información sobre tipos de información confidencial basada en coincidencias de datos exactas](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [Exportar datos de origen para el tipo exacto de información confidencial basada en coincidencias de datos](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
