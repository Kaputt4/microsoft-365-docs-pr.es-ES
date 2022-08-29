---
title: Creación de una experiencia clásica de flujo de trabajo de tipo de información confidencial de coincidencia exacta de datos
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
description: Empiece a crear tipos de información confidencial basados en coincidencias de datos exactas mediante el flujo de trabajo de experiencia de usuario clásica.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0d01d90c83c8bdd919de275ea2f173082737de94
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "67360785"
---
# <a name="create-exact-data-match-sensitive-information-type-workflow-classic-experience"></a>Creación de una experiencia clásica de flujo de trabajo de tipo de información confidencial de coincidencia exacta de datos

La creación y puesta a disposición de un tipo de información confidencial (SIT) basado en una coincidencia exacta de datos (EDM) es un proceso de varias fases. Se pueden usar en directivas de prevención de pérdida de datos de Microsoft Purview, etiquetado automático, exhibición de documentos electrónicos y determinadas tareas de gobernanza de contenido.  En este artículo se describe el flujo de trabajo y los vínculos a los procedimientos de cada fase mediante la experiencia clásica.

## <a name="applies-to"></a>Se aplica a

- Experiencia clásica

Si desea crear una sit de EDM con la nueva experiencia, consulte Creación de un [flujo de trabajo de nueva experiencia de SIT de EDM ](sit-create-edm-sit-unified-ux-workflow.md).

## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de revisar:

- [Más información sobre los SIT basados en EDM](sit-learn-about-exact-data-match-based-sits.md)
- [Introducción a los tipos de información confidencial basados en coincidencias de datos exactas](sit-get-started-exact-data-match-based-sits-overview.md)

## <a name="the-work-flow-at-a-glance"></a>El flujo de trabajo de un vistazo

![coincidencia exacta de datos con las fases de flujo de trabajo](..\media\swimlane_edm_process.png)


|Fase|Requisitos|
|---|---|
|[Fase 1: Exportación de datos de origen para el tipo de información confidencial basada en coincidencias exactas de datos](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)|- Acceso de lectura a los datos confidenciales|
|[Fase 2: Creación del esquema para tipos de información confidencial basados en coincidencias de datos exactas](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)|- Acceso al asistente para tipos de información confidencial en el portal de cumplimiento </br>: acceso a la [Centro de administración de Microsoft 365 a través de PowerShell de cumplimiento de & de seguridad](/powershell/exchange/connect-to-scc-powershell) |
|[Fase 3: Hash y carga de la tabla de origen de información confidencial para obtener datos exactos que coincidan con tipos de información confidencial](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)|- Cuenta de usuario y de grupo de seguridad personalizado </br>- **Hash y carga desde un equipo**: acceso de administrador local a un equipo con acceso directo a Internet y para hospedar el agente de carga de EDM </br>- **Hash y carga desde equipos independientes**: acceso de administrador local a un equipo con acceso directo a Internet y hospedar el agente de carga de EDM para la carga y el acceso de administrador local a un equipo seguro para hospedar el agente de carga de EDM para aplicar hash a la tabla de origen de información confidencial </br>- Acceso de lectura al archivo de tabla de origen de información confidencial </br> el archivo de esquema |
|[Fase 4: Creación de un paquete de reglas o tipo de información confidencial que coincida con datos exactos](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package) |- Acceso al portal de cumplimiento Microsoft Purview |
|[Probar un tipo de información confidencial de coincidencia exacta de datos](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)| - Acceso al portal de cumplimiento Microsoft Purview

## <a name="see-also"></a>Vea también

- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [Exportar datos de origen para el tipo de información confidencial basada en la coincidencia exacta de datos](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
