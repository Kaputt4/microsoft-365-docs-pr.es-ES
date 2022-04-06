---
title: Uso de entidades con nombre en las directivas de prevención de pérdida de datos (versión preliminar)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
description: Use estos procedimientos para aprovechar las entidades con nombre en las directivas de prevención de pérdida de datos.
ms.openlocfilehash: 9b3a8899ef4b64c682289e29df19648a00d4f048
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665170"
---
# <a name="use-named-entities-in-your-data-loss-prevention-policies-preview"></a>Uso de entidades con nombre en las directivas de prevención de pérdida de datos (versión preliminar)

> [!IMPORTANT]
> La característica de entidades con nombre se está implementando y aparecerá en el inquilino cuando esté disponible para usted. Compruébalos en el explorador de contenido y en el flujo de creación de directivas de prevención de pérdida de datos (DLP). 

Lea [Más información sobre las entidades con nombre (versión preliminar)](named-entities-learn.md) antes de empezar a usarlas.

## <a name="before-you-begin"></a>Antes de empezar

### <a name="skusubscriptions-licensing"></a>Licencias de SKU/suscripciones

Tiene que tener una de estas suscripciones.

- Information Protection y gobernanza
- Cumplimiento de Microsoft 365 E5
- Office 365 E5
- Microsoft 365 E5

Para obtener detalles completos sobre las licencias, consulte [la descripción del servicio](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-classification-analytics-overview-content--activity-explorer).

### <a name="permissions"></a>Permissions

La cuenta que usa para crear y editar directivas de prevención de pérdida de datos (DLP) debe tener los permisos del rol **Administración de cumplimiento de DLP** . Para obtener más información, vea [Proporcionar a los usuarios acceso al Centro de cumplimiento de Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).


## <a name="supported-locations"></a>Ubicaciones admitidas

Puede usar SIT de entidad con nombre y directivas mejoradas para detectar y proteger elementos confidenciales en estas ubicaciones:

- Sitios de SharePoint
- Cuentas de OneDrive
- Mensajes de canales y chats de Teams
- Dispositivos (Windows 10 dispositivos de punto de conexión)

Los SIT de entidad con nombre y las directivas mejoradas no se admiten para:


- Repositorios locales
- Power BI

## <a name="create-and-edit-enhanced-policies"></a>Creación y edición de directivas mejoradas

Para crear o editar una directiva DLP, use los procedimientos de [Creación, prueba y ajuste de una directiva DLP](create-test-tune-dlp-policy.md).

## <a name="workloads-and-services-that-support-named-entities"></a>Cargas de trabajo y servicios que admiten entidades con nombre


- **Microsoft 3655 eDiscovery** admite el uso de entidades con nombre en los servicios de Substrate.
- **Microsoft Defender for Cloud Apps** admite el uso de entidades con nombre en directivas de Defender for Cloud Apps.
- **Insider Risk Management** admite el uso de entidades con nombre en los servicios de Substrate.
<!--- **Communication Compliance** doesn't support the use of named entities in Exchange transport rules and data-at-rest.
- **Microsoft Information Governance** (MIG) doesn't support the use of named entities in Exchange transport rules and data-at-rest.-->
 
### <a name="unified-dlp"></a>DLP unificado

|Carga de trabajo o servicios  |Compatibilidad con la versión preliminar pública para entidades con nombre  |
|---------|---------|
|Office sugerencia de directiva de clientes Win32    |no compatible  |
|Office sugerencia de directiva de clientes WAC    |compatible         |
|Sugerencia de directiva de OWA     |no compatible         |
|sugerencia de directiva de Outlook     |no compatible |
|Puntos de conexión (dispositivos Windows 10)     |compatible  |
|reglas de transporte de Exchange     |no compatible |
|OneDrive para la Empresa datos en reposo     |compatible         |
|SharePoint datos en reposo en línea     |compatible         |
|Teams datos en reposo     |compatible         |
|Datos en reposo de mensajes de correo electrónico     |no compatible         |
|Microsoft Defender for Cloud Apps     |compatible         |

### <a name="autolabeling"></a>Etiquetado automático

|Carga de trabajo o servicios |Compatibilidad con la versión preliminar pública para entidades con nombre  |
|---------|---------|
|Office clientes Win32 sin conexión   |compatible, el usuario debe seleccionar la etiqueta y aplicar manualmente |
|Clientes de Win32 en línea Office en línea|compatible con el esquema de confianza antiguo |
|Outlook en línea   |compatible con el esquema de confianza antiguo  |
|Office cliente WAC     |compatible |
|OWA     |compatible |
|transporte Exchange     |no compatible |
|OneDrive para la Empresa datos en reposo     |compatible |
|SharePoint datos en reposo en línea|compatible|
|Analizador de Azure Information Protection (AIP)|no compatible|

## <a name="known-issues"></a>Problemas conocidos

|Problema  |Impacto  |
|---------|---------|
|Sugerencias de directiva DLP (OWA, Outlook, Office clientes Win32)     |   Las sugerencias de directiva con la condición de entidad provocarán que "no coincida"      |
| Compatibilidad con idiomas asiáticos para el nombre de persona (chino, japonés, coreano)    | Entidades con nombre admitidas solo para el conjunto de caracteres basado en latín (es decir, no se admite kanji) para el nombre de persona.        |
|Repositorios locales    | No se admite como carga de trabajo|

<!--|Devices workload (Endpoint)     | Not supported as a workload – authoring policy with named entities will not be allowed        |-->

## <a name="for-further-information"></a>Para obtener más información
<!-- - [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)-->
- [Obtenga información sobre las entidades con nombre (versión preliminar).](named-entities-learn.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md)
