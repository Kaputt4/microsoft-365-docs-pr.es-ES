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
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Use estos procedimientos para aprovechar las entidades con nombre en las directivas de prevención de pérdida de datos
ms.openlocfilehash: 5d81f216ddd86816148220c178b991db4e4803b0
ms.sourcegitcommit: aac7e002ec6e10a41baa2d0bd38614b0ed471a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2022
ms.locfileid: "62245104"
---
# <a name="use-named-entities-in-your-data-loss-prevention-policies-preview"></a>Uso de entidades con nombre en las directivas de prevención de pérdida de datos (versión preliminar)

> [!IMPORTANT]
> La característica de entidades con nombre se está implementando y aparecerá en el espacio empresarial cuando esté disponible. Compruebe si están en el explorador de contenido y en el flujo de creación de directivas de prevención de pérdida de datos (DLP). 

Lea más [información sobre las entidades con nombre (versión preliminar)](named-entities-learn.md) antes de empezar a usarlas.

## <a name="before-you-begin"></a>Antes de empezar

### <a name="skusubscriptions-licensing"></a>Licencias de SKU/suscripciones

Debe tener una de estas suscripciones

- Protección de la información y gobierno
- Cumplimiento de Microsoft 365 E5
- Office 365 E5
- Microsoft 365 E5

Para obtener información completa sobre las licencias, [vea la descripción del servicio](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-classification-analytics-overview-content--activity-explorer).

### <a name="permissions"></a>Permisos

La cuenta que use para crear y editar directivas de prevención de pérdida de datos (DLP), debe tener los permisos del rol Administración de cumplimiento **dlp.** Para obtener más información, vea [Dar acceso a los usuarios al Centro de Office 365 cumplimiento](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)


## <a name="supported-locations"></a>Ubicaciones admitidas

Puede usar SITs de entidad con nombre y directivas mejoradas para detectar y proteger elementos confidenciales en estas ubicaciones:

- Sitios de SharePoint
- Cuentas de OneDrive
- Mensajes de canales y chats de Teams
- Dispositivos (Windows 10 dispositivos de punto de conexión)

No se admiten los SIT de entidad con nombre ni las directivas mejoradas para:


- Repositorios locales

## <a name="create-and-edit-enhanced-policies"></a>Crear y editar directivas mejoradas

Para crear o editar una directiva DLP, use los procedimientos de [Crear, probar y ajustar una directiva DLP](create-test-tune-dlp-policy.md).

## <a name="workloads-and-services-that-support-named-entities"></a>Cargas de trabajo y servicios que admiten entidades con nombre


- La exhibición de documentos electrónicos de **Microsoft 3655** admite el uso de entidades con nombre en los servicios de substrate.
- **Microsoft Defender para Aplicaciones en la** nube admite el uso de entidades con nombre en las directivas de Defender para Aplicaciones en la nube.
- **Insider Risk Management** admite el uso de entidades con nombre en los servicios de Substrate.
- **El cumplimiento** de la comunicación no admite el uso de entidades con nombre en Exchange de transporte y datos en reposo.
- **Microsoft Information Governance** (MIG) no admite el uso de entidades con nombre en Exchange de transporte y datos en reposo.
 
### <a name="unified-dlp"></a>DLP unificado

|Carga de trabajo/servicios  |Compatibilidad con vista previa pública para entidades con nombre  |
|---------|---------|
|Office de directiva de clientes de Win32    |no compatible  |
|Office directiva de clientes WAC    |compatible         |
|Sugerencia de directiva de OWA     |no compatible         |
|Outlook de directiva     |no compatible |
|Puntos de conexión (Windows 10 dispositivos)     |compatible  |
|Exchange de transporte     |no compatible |
|OneDrive para la Empresa datos en reposo     |compatible         |
|SharePoint Online data-at-rest     |compatible         |
|Teams datos en reposo     |compatible         |
|Mensajes de correo electrónico datos en reposo     |no compatible         |
|Microsoft Defender for Cloud Apps     |compatible         |

### <a name="autolabeling"></a>Autolabeling

|Carga de trabajo/servicios |Compatibilidad con vista previa pública para entidades con nombre  |
|---------|---------|
|Office clientes de Win32 sin conexión   |compatible, el usuario debe seleccionar etiqueta y aplicar manualmente |
|Online Office clientes de Win32 en línea|compatible con un esquema de confianza antiguo |
|Outlook en línea   |compatible con un esquema de confianza antiguo  |
|Office cliente WAC     |compatible |
|OWA     |compatible |
|Exchange transporte     |no compatible |
|OneDrive para la Empresa datos en reposo     |compatible |
|SharePoint Online data-at-rest|compatible|
|Escáner de Azure Information Protection (AIP)|no compatible|

## <a name="known-issues"></a>Problemas conocidos

|Incidencia  |Impacto  |
|---------|---------|
|Sugerencias de directiva DLP (OWA, Outlook, Office clientes win32)     |   Las sugerencias de directiva con condición de entidad darán como resultado "no coincidir"      |
| Compatibilidad con el idioma asiático para el nombre de la persona (chino, japonés, coreano)    | Entidades con nombre admitidas solo para el conjunto de caracteres basado en latinos (es decir, kanji no es compatible) para el nombre de la persona        |
|Repositorios locales    | No se admite como carga de trabajo|

<!--|Devices workload (Endpoint)     | Not supported as a workload – authoring policy with named entities will not be allowed        |-->

## <a name="for-further-information"></a>Para obtener más información
<!-- - [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)-->
- [Obtenga información sobre las entidades con nombre (versión preliminar)](named-entities-learn.md).
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md)
