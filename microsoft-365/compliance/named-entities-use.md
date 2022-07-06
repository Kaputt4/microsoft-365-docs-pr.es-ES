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
ms.openlocfilehash: 0cdf544eddf873f3bbf761bd613641433dd2da6b
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66623723"
---
# <a name="use-named-entities-in-your-data-loss-prevention-policies"></a>Uso de entidades con nombre en las directivas de prevención de pérdida de datos

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
|Sugerencia de directiva de clientes Win32 de Office    |No se admite  |
|Sugerencia de directiva de clientes WAC de Office    |Compatible         |
|Sugerencia de directiva de OWA     |No admitido         |
|Sugerencia de directiva de Outlook     |No se admite |
|Puntos de conexión (Windows 10 y 11 dispositivos)     |Compatible  |
|Reglas de transporte de Exchange     |Compatible |
|OneDrive para la Empresa datos en reposo     |Compatible         |
|Datos en reposo de SharePoint Online     |Compatible         |
|Datos en reposo de Teams     |Compatible         |
|Datos en reposo de mensajes de correo electrónico     |Compatible con inquilinos con el plan de servicio de privacidad         |
|Microsoft Defender for Cloud Apps     |Compatible         |

### <a name="autolabeling"></a>Etiquetado automático

|Carga de trabajo o servicios |Compatibilidad con entidades con nombre  |
|---------|---------|
|Clientes de Office Win32 sin conexión   |Compatible, el usuario debe seleccionar la etiqueta y aplicar manualmente |
|Clientes win32 de Office en línea|Compatible con el esquema de confianza antiguo |
|Outlook online   |Compatible con el esquema de confianza antiguo  |
|Cliente WAC de Office     |Compatible |
|OWA     |Compatible |
|Transporte de Exchange     |Compatible |
|OneDrive para la Empresa datos en reposo     |Compatible |
|Datos en reposo de SharePoint Online|Compatible|
|Analizador de Azure Information Protection (AIP)|No admitido|

## <a name="known-issues"></a>Problemas conocidos

|Problema  |Impacto  |
|---------|---------|
|Sugerencias de directiva DLP (clientes de OWA, Outlook y Office Win32)     |   Las sugerencias de directiva con la condición de entidad provocarán que "no coincida"      |
| Compatibilidad con idiomas asiáticos para el nombre de persona (chino, japonés, coreano)    | Entidades con nombre admitidas solo para el conjunto de caracteres basado en latín (es decir, no se admite kanji) para el nombre de persona.        |
|Repositorios locales    | No se admite como carga de trabajo|
|Power BI (versión preliminar) | No admitido

<!--|Devices workload (Endpoint)     | Not supported as a workload – authoring policy with named entities will not be allowed        |-->

## <a name="best-practices-for-using-named-entity-sits"></a>Procedimientos recomendados para usar SIT de entidad con nombre

Estas son algunas prácticas que puede usar al crear o editar una directiva que usa una entidad con nombre SIT.

- Use recuentos de instancias bajos (de tres a cinco) cuando busque datos que se encuentran en una hoja de cálculo y la palabra clave necesaria por sit para esos datos solo se encuentra en el encabezado de columna. Por ejemplo, supongamos que está buscando números del Seguro Social de EE. UU. y la palabra clave `Social Security Number` solo se produce en el encabezado de columna. Dado que los valores (la evidencia corroborativa) están en las celdas siguientes, es probable que solo las primeras instancias estén lo suficientemente cerca de la palabra clave que se va a detectar.  

- Si usa una entidad con nombre SIT, como Todos los nombres completos, para ayudar a encontrar números del Seguro Social de EE. UU., use recuentos de instancias más grandes, como 10 o 50. A continuación, cuando se detectan juntos los nombres de persona y los SSN, es más probable que obtenga verdaderos positivos.

- Puede usar [simulaciones de etiquetado automático](apply-sensitivity-label-automatically.md#learn-about-simulation-mode) para probar la precisión de los SIT de entidad con nombre. Ejecute una simulación con una entidad con nombre SIT para ver qué elementos coinciden con la directiva. Con esta información, puede ajustar la precisión ajustando los recuentos de instancias y los niveles de confianza en las directivas personalizadas o en las condiciones de plantilla mejoradas. Puede recorrer en iteración las simulaciones hasta que la precisión sea la que desee, antes de implementar una directiva DLP o de etiquetado automático que contenga entidades con nombre en producción. Esta es una introducción al flujo:

1. Identifique el SIT o la combinación de SIT que desea probar en modo de simulación, ya sea personalizado o clonado y editado.
1. Identifique o cree una etiqueta de confidencialidad que se aplicará cuando la directiva de etiquetado automático encuentre una coincidencia en exchange, sitios de SharePoint o cuentas de OneDrive.
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
