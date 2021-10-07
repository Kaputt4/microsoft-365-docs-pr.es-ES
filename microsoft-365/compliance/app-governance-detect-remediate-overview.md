---
title: Más información sobre la detección y corrección de aplicaciones
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: Más información sobre la detección y corrección de aplicaciones.
ms.openlocfilehash: 90cddc1ffc386a2f691b27e77765a42f46778c82
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60171020"
---
# <a name="learn-about-app-threat-detection-and-remediation"></a>Más información sobre la detección y corrección de aplicaciones

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Con la gobernanza de aplicaciones de Microsoft, usted puede:

- Monitorear fácilmente las alertas de amenazas que están siendo generadas por métodos de detección de gobernanza de aplicaciones integrados para actividades de aplicaciones malintencionadas, y alertas basadas en directivas generadas por las directivas de aplicación activas que usted cree. Estas alertas pueden indicar anomalías en la actividad de la aplicación y cuando se usen aplicaciones no compatibles, malintencionadas o de riesgo.  También puede usar patrones en las alertas para crear nuevas directivas de aplicación o modificar la configuración de las directivas existentes para acciones más restrictivas.
- Corrija fácilmente las alertas manualmente después de la investigación o automáticamente a través de la configuración de acciones en las directivas de aplicación activas.


>[!Note]
>Las actividades anómalas solo de las aplicaciones de Azure a las que no se les conceden permisos para acceder a los recursos de Microsoft 365 no se incluyen en la detección y alertas de gobernanza de aplicaciones.
>

Consulte los [roles de administrador de](app-governance-get-started.md#administrator-roles) para saber qué roles pueden acceder a las páginas de gobernanza de aplicaciones.


## <a name="app-governance-integration-with-azure-active-directory-and-microsoft-cloud-app-security"></a>Integración de gobernanza de aplicaciones con Azure Active Directory y Microsoft Cloud App Security

La gobernanza de aplicaciones, Azure Active Directory (Azure AD), y Microsoft Cloud App Security recopilan y proporcionan diferentes conjuntos de datos:

- La gobernanza de aplicaciones proporciona información detallada sobre la actividad de una aplicación en el nivel de API.
- Azure AD proporciona metadatos de aplicaciones fundamentales e información detallada sobre los inicios de sesión en las aplicaciones.
- Microsoft Cloud App Security proporciona información de riesgo de la aplicación.

Al compartir información entre el gobierno de aplicaciones, Azure AD y Microsoft Cloud App Security, puede mostrar información agregada en un portal y vincular fácilmente a otro portal para obtener más información. Aquí hay unos ejemplos:

- Información de inicio de sesión de la aplicación en la gobernanza de aplicaciones:

  Desde el portal de gobernanza de aplicaciones, puede ver la actividad de inicio de sesión agregada de cada aplicación y volver a vincularla al centro de administración de Azure Active Directory para obtener los detalles de los eventos de inicio de sesión.

- Información del uso de la API en el portal de Microsoft Cloud App Security: 

  Desde el portal de Microsoft Cloud App Security, puede visualizar el nivel de uso de la API, la transferencia de datos agregados y el vínculo al portal de gobernanza de aplicaciones para obtener los detalles.

Este es un resumen de la integración.

![La Integración de gobernanza de aplicaciones con Azure AD y Microsoft Cloud App Security.](..\media\manage-app-protection-governance\mapg-integration.png)

Además, la gobernanza de aplicaciones envía sus alertas como señales a Microsoft Cloud App Security y Microsoft 365 Defender para obtener un análisis más detallado de los incidentes de seguridad basados en aplicaciones.

<!--

CFA #3 Scenario 1:  As an admin, I can investigate alerts associated to my M365 apps through MAPG.
CFA #3 Scenario 2: As an admin, I can manually remediate 
CFA #3 Scenario 3: As an admin, I can configure policies to perform automatic 
--> 

## <a name="next-step"></a>Paso siguiente

[Introducción a la detección y corrección de amenazas de aplicaciones.](app-governance-detect-remediate-get-started.md)
