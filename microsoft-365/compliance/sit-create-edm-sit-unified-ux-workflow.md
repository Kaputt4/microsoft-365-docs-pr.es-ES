---
title: Creación de una nueva experiencia de flujo de trabajo de tipo de información confidencial que coincida con datos exactos
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
description: Empiece a crear tipos de información confidencial basados en coincidencias de datos exactas mediante la nueva experiencia.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47fa9bd604f5a905ce46dad2ef0b2177c86cfdec
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "67360776"
---
# <a name="create-exact-data-match-sensitive-information-type-workflow-new-experience"></a>Creación de una nueva experiencia de flujo de trabajo de tipo de información confidencial que coincida con datos exactos

La creación y puesta a disposición de un tipo de información confidencial (SIT) basado en una coincidencia exacta de datos (EDM) es un proceso de varias fases. Se pueden usar en las directivas de prevención de pérdida de datos de Microsoft Purview, eDiscovery y ciertas tareas de gobernanza de contenido Este artículo describe el flujo de trabajo y los vínculos a los procedimientos para cada una de las fases.

## <a name="applies-to"></a>Se aplica a

- Nueva experiencia

Si quiere crear una sit de EDM con la experiencia clásica, consulte Creación de una [experiencia clásica sit de EDM](sit-create-edm-sit-classic-ux-workflow.md).

## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de revisar:

- [Más información sobre los SIT basados en EDM](sit-learn-about-exact-data-match-based-sits.md)
- [Introducción a los tipos de información confidencial basados en coincidencias de datos exactas](sit-get-started-exact-data-match-based-sits-overview.md)

## <a name="the-work-flow-at-a-glance"></a>El flujo de trabajo de un vistazo


|Fase|Requisitos|
|---|---|
|[Fase 1: Exportación de datos de origen para el tipo de información confidencial basada en coincidencias exactas de datos](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)|- Acceso de lectura a los datos confidenciales|
|[Fase 2: Creación del archivo de ejemplo](sit-create-edm-sit-unified-ux-sample-file.md)|- Conozca los encabezados de columna y el formato de los datos que va a buscar en cada columna.
|[Fase 3: Creación del SIT de EDM](sit-create-edm-sit-unified-ux-schema-rule-package.md)|- Acceso al portal  > **de cumplimiento de Microsoft Purview****Clasificación** >  de **datos Coincidencia exacta de datos** |
|[Fase 4: Hash y carga de la tabla de origen de información confidencial para obtener datos exactos que coincidan con tipos de información confidencial](sit-get-started-exact-data-match-hash-upload.md)|- Cuenta de usuario y de grupo de seguridad personalizado </br>- **Hash y carga desde un equipo**: acceso de administrador local a un equipo con acceso directo a Internet y para hospedar el agente de carga de EDM </br>- **Hash y carga desde equipos independientes**: acceso de administrador local a un equipo con acceso directo a Internet y hospedar el agente de carga de EDM para la carga y el acceso de administrador local a un equipo seguro para hospedar el agente de carga de EDM para aplicar hash a la tabla de origen de información confidencial </br>- Acceso de lectura al archivo de tabla de origen de información confidencial|
|[Fase 5: Prueba de un tipo de información confidencial de coincidencia exacta de datos](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)| - Acceso al portal de cumplimiento Microsoft Purview

## <a name="see-also"></a>Vea también

- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)


## <a name="next-step"></a>Paso siguiente

- **Para obtener una nueva experiencia**: [Exportación de datos de origen para el tipo de información confidencial basado en coincidencias exactas de datos](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
