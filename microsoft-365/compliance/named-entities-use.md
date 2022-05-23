---
title: Uso de entidades con nombre en directivas DLP
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
ms.openlocfilehash: 85d3d11704ea238f6c1acff64193d8aaba8994b8
ms.sourcegitcommit: db1e48af88995193f15bbd5962f5101a6088074b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2022
ms.locfileid: "65637194"
---
# <a name="use-named-entities-in-your-data-loss-prevention-policies"></a>Uso de entidades con nombre en las directivas de prevención de pérdida de datos

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Lea [Más información sobre las entidades con nombre](named-entities-learn.md) antes de empezar a usarlas.

## <a name="before-you-begin"></a>Antes de empezar

### <a name="skusubscriptions-licensing"></a>Licencias de SKU/suscripciones

Para obtener detalles completos sobre las licencias, consulte [la descripción del servicio](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-classification-analytics-overview-content--activity-explorer).

### <a name="permissions"></a>Permisos

La cuenta que usa para crear y editar directivas de prevención de pérdida de datos (DLP) debe tener los permisos del rol **Administración de cumplimiento de DLP** . Para obtener más información, vea [Proporcionar a los usuarios acceso al Centro de cumplimiento de Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).


## <a name="supported-locations"></a>Ubicaciones admitidas

Puede usar SIT de entidad con nombre y directivas mejoradas para detectar y proteger elementos confidenciales en estas ubicaciones:

- Sitios de SharePoint
- Cuentas de OneDrive
- Mensajes de canales y chats de Teams
- Dispositivos (Windows 10 y 11 dispositivos de punto de conexión)
- Buzones de Exchange
- Microsoft Defender for Cloud Apps

Los SIT de entidad con nombre y las directivas mejoradas no se admiten para:

- Repositorios locales
- Power BI

## <a name="create-and-edit-enhanced-policies"></a>Creación y edición de directivas mejoradas

Para crear o editar una directiva DLP, use los procedimientos de [Creación, prueba y ajuste de una directiva DLP](create-test-tune-dlp-policy.md).

## <a name="workloads-and-services-that-support-named-entities"></a>Cargas de trabajo y servicios que admiten entidades con nombre

- **Microsoft 365 eDiscovery** admite el uso de entidades con nombre en los servicios de Substrate.
- **Microsoft Defender for Cloud Apps** admite el uso de entidades con nombre en las directivas de Defender for Cloud Apps en el portal de aplicaciones de Defender for Cloud.
- **Insider Risk Management** admite el uso de entidades con nombre en los servicios de Substrate.
- **Records Management** admite el uso de entidades con nombre.
- **Exact Data Match Sensitive Information Types** admite el uso de entidades con nombre.
<!--- **Communication Compliance** doesn't support the use of named entities in Exchange transport rules and data-at-rest.
- **Microsoft Information Governance** (MIG) doesn't support the use of named entities in Exchange transport rules and data-at-rest.-->
 
### <a name="unified-dlp"></a>DLP unificado

|Carga de trabajo o servicios  |Compatibilidad con entidades con nombre  |
|---------|---------|
|Office sugerencia de directiva de clientes Win32    |No se admite  |
|Office sugerencia de directiva de clientes WAC    |Compatible         |
|Sugerencia de directiva de OWA     |No admitido         |
|sugerencia de directiva de Outlook     |No admitido |
|Puntos de conexión (Windows 10 y 11 dispositivos)     |Compatible  |
|reglas de transporte de Exchange     |Compatible |
|OneDrive para la Empresa datos en reposo     |Compatible         |
|SharePoint datos en reposo en línea     |Compatible         |
|Teams datos en reposo     |Compatible         |
|Datos en reposo de mensajes de correo electrónico     |Compatible con inquilinos con el plan de servicio de privacidad         |
|Microsoft Defender for Cloud Apps     |Compatible         |

### <a name="autolabeling"></a>Etiquetado automático

|Carga de trabajo o servicios |Compatibilidad con entidades con nombre  |
|---------|---------|
|Office clientes Win32 sin conexión   |Compatible, el usuario debe seleccionar la etiqueta y aplicar manualmente |
|Clientes de Win32 en línea Office en línea|Compatible con el esquema de confianza antiguo |
|Outlook en línea   |Compatible con el esquema de confianza antiguo  |
|Office cliente WAC     |Compatible |
|OWA     |Compatible |
|transporte Exchange     |Compatible |
|OneDrive para la Empresa datos en reposo     |Compatible |
|SharePoint datos en reposo en línea|Compatible|
|Analizador de Azure Information Protection (AIP)|No se admite|

## <a name="known-issues"></a>Problemas conocidos

|Problema  |Impacto  |
|---------|---------|
|Sugerencias de directiva DLP (OWA, Outlook, Office clientes Win32)     |   Las sugerencias de directiva con la condición de entidad provocarán que "no coincida"      |
| Compatibilidad con idiomas asiáticos para el nombre de persona (chino, japonés, coreano)    | Entidades con nombre admitidas solo para el conjunto de caracteres basado en latín (es decir, no se admite kanji) para el nombre de persona.        |
|Repositorios locales    | No se admite como carga de trabajo|
|Power BI (versión preliminar) | No se admite

<!--|Devices workload (Endpoint)     | Not supported as a workload – authoring policy with named entities will not be allowed        |-->

## <a name="best-practices-for-using-named-entity-sits"></a>Procedimientos recomendados para usar SIT de entidad con nombre

Estas son algunas prácticas que puede usar al crear o editar una directiva que usa una entidad con nombre SIT.

- Use recuentos de instancias bajos (de tres a cinco) cuando busque datos que se encuentran en una hoja de cálculo y la palabra clave necesaria por sit para esos datos solo se encuentra en el encabezado de columna. Por ejemplo, supongamos que está buscando números del Seguro Social de EE. UU. y la palabra clave `Social Security Number` solo se produce en el encabezado de columna. Dado que los valores (la evidencia corroborativa) están en las celdas siguientes, es probable que solo las primeras instancias estén lo suficientemente cerca de la palabra clave que se va a detectar.  

- Si usa una entidad con nombre SIT, como Todos los nombres completos, para ayudar a encontrar números del Seguro Social de EE. UU., use recuentos de instancias más grandes, como 10 o 50. A continuación, cuando se detectan juntos los nombres de persona y los SSN, es más probable que obtenga verdaderos positivos.

- Puede usar [simulaciones de etiquetado automático](apply-sensitivity-label-automatically.md#learn-about-simulation-mode) para probar la precisión de los SIT de entidad con nombre. Ejecute una simulación con una entidad con nombre SIT para ver qué elementos coinciden con la directiva. Con esta información, puede ajustar la precisión ajustando los recuentos de instancias y los niveles de confianza en las directivas personalizadas o en las condiciones de plantilla mejoradas. Puede recorrer en iteración las simulaciones hasta que la precisión sea la que desee, antes de implementar una directiva DLP o de etiquetado automático que contenga entidades con nombre en producción. Esta es una introducción al flujo:

1. Identifique el SIT o la combinación de SIT que desea probar en modo de simulación, ya sea personalizado o clonado y editado.
1. Identifique o cree una etiqueta de confidencialidad que se aplicará cuando la directiva de etiquetado automático encuentre una coincidencia en Exchange, sitios SharePoint o cuentas de OneDrive.
1. Cree una directiva de etiquetado automático de confidencialidad que use sit del paso 1 y con las mismas condiciones y excepciones que se usarán en la directiva DLP.
1. Ejecución de la simulación de directiva
1. Visualización de los resultados
1. Ajuste el SIT o la directiva y el recuento de instancias y los niveles de confianza para reducir los falsos positivos.
1. Repita la operación hasta que obtenga los resultados de precisión que desee.


## <a name="for-further-information"></a>Para obtener más información
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Obtenga información sobre las entidades con nombre](named-entities-learn.md).
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md)
