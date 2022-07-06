---
title: Más información sobre las entidades con nombre
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo las entidades con nombre le ayudan a detectar elementos confidenciales que contienen nombres de personas, direcciones físicas y términos médicos a través de directivas de prevención de pérdida de datos
ms.openlocfilehash: 013d2453190c692eeb3ae9a0dfd48437bded1f0c
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66633507"
---
# <a name="learn-about-named-entities"></a>Más información sobre las entidades con nombre

*Las entidades con nombre* son [tipos de información confidencial](sensitive-information-type-learn-about.md) (SIT). Son clasificadores complejos basados en patrones y diccionarios que puede usar para detectar nombres de personas, direcciones físicas y términos y condiciones médicos. Puede verlos en la **clasificación de datos portal de cumplimiento Microsoft Purview > > tipos de información confidencial**. Esta es una lista parcial de dónde puede usar los SIT:


- [directivas de Prevención de pérdida de datos de Microsoft Purview (DLP)](dlp-learn-about-dlp.md) 
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Administración de riesgos internos](insider-risk-management-solution-overview.md)
- [Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Purview Information Protection](apply-sensitivity-label-automatically.md)
- [Administración del ciclo de vida de los datos](information-governance.md)
- [Administración de registros](records-management.md)
- [Microsoft Purview eDiscovery](ediscovery.md)
- [Microsoft Priva](/privacy/priva/priva-overview.md)
- [Coincidencia exacta de datos con tipos de información confidencial](sit-learn-about-exact-data-match-based-sits.md)

DLP hace un uso especial de las entidades con nombre en *plantillas de directiva mejoradas*, que son directivas DLP preconfiguradas que puede personalizar para las necesidades de las organizaciones. También puede [crear sus propias directivas DLP](create-test-tune-dlp-policy.md) a partir de una [plantilla en blanco](create-a-dlp-policy-from-a-template.md) y usar una entidad con nombre SIT como condición.

<!-- There are many other SITs that detect strings like social security, credit card, or bank account numbers to identify sensitive items. For more information, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md).-->



## <a name="examples-of-named-entity-sits"></a>Ejemplos de SIT de entidades con nombre

Los SIT de entidad con nombre se incluyen en dos tipos, *agrupados* y *desagregados*.

Los SIT de entidad con nombre agrupados detectan todas las coincidencias posibles. Úselos como criterios generales en las directivas DLP para detectar elementos confidenciales.

Los SIT de entidad con nombre desagregados tienen un enfoque más estrecho, como un solo país. Úselas cuando necesite una directiva DLP con un ámbito de detección más restringido.
 
Estos son algunos ejemplos de SIT de entidad con nombre. Puede encontrarlas todas en [Definiciones de entidad de tipo información confidencial](sensitive-information-type-entity-definitions.md).

|Entidad con nombre |Description  |Agrupada o desagregada  |
|---------|---------|---------|
|Todos los nombres completos    |detectará todas las posibles coincidencias de nombres completos         |   Liado      |
|Todas las direcciones físicas    |detectará todas las posibles coincidencias de direcciones físicas     | Liado |
|Todos los términos y condiciones médicos    |detectará todas las posibles coincidencias de términos y condiciones médicos |Liado |
|Direcciones físicas de Australia |  Detecta patrones relacionados con direcciones físicas de Australia. Se incluye en Todas las direcciones físicas SIT. |Desagregado |
|Términos de análisis de sangre     |Detecta términos relacionados con los análisis de sangre, como "hCG". Solo términos en inglés. Incluido en todos los términos y condiciones médicos SIT      |Desagregado |
|Nombres de medicamentos de marca     |Detecta nombres de medicamentos de marca, como 'Tylenol'. Solo términos en inglés. Incluido en Todos los términos y condiciones médicas.         |Desagregado |

## <a name="examples-of-enhanced-dlp-policies"></a>Ejemplos de directivas DLP mejoradas

Estos son algunos ejemplos de directivas DLP mejoradas que usan SIT de entidad con nombre. Puede encontrar los 10 en la **portal de cumplimiento Microsoft Purview > prevención de pérdida de datos > Crear directiva**. Las plantillas mejoradas se pueden usar en DLP y el etiquetado automático.

|Categoría de directiva  |Plantilla  |Description  |
|---------|---------|---------|
|Financiera|Ley Gramm-Leach-Bliley (GLBA) mejorada de Ee. UU.         |Ayuda a detectar la presencia de datos sujetos a la Ley Gramm-Leach.Bliley (GLBA), incluidos los datos como números de Seguridad Social o de las tarjetas de crédito. Esta plantilla mejorada amplía el original al detectar también los nombres completos de las personas, U.S./U.K. número de pasaporte, número de licencia de conducir de EE. UU. y direcciones físicas de EE. UU.         |
| Medicina y salud   |Ley de registros de salud de Australia (HRIP Act) Mejorada         |Ayuda a detectar la presencia de datos considerados comúnmente sujetos a la Ley de privacidad de información y registros de salud (HRIP) en Australia, como por ejemplo el número de expediente médico y el número de archivo fiscal. Esta plantilla mejorada amplía el original al detectar también los nombres completos de las personas, los términos y condiciones médicos y las direcciones físicas de Australia.         |
|Privacidad   |Reglamento general de protección de datos (RGPD) mejorado         | Ayuda a detectar la presencia de información personal de las personas dentro de la Unión Europea (UE) para ayudar a cumplir las obligaciones de privacidad del RGPD. Esta plantilla mejorada detecta los nombres completos de las personas y las direcciones físicas de los países de la UE.        |


## <a name="next-steps"></a>Pasos siguientes

- [Uso de entidades con nombre en las directivas de prevención de pérdida de datos](named-entities-use.md)


## <a name="for-further-information"></a>Para obtener más información

- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Más información sobre los tipos de información confidencial](sensitive-information-type-learn-about.md)
- [Crear un tipo personalizado de información confidencial](create-a-custom-sensitive-information-type.md)
- [Creación de un tipo de información confidencial personalizada en PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Directivas de prevención de pérdida de datos (DLP)](data-loss-prevention-policies.md) 
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Etiquetas de retención](retention.md)
- [Cumplimiento de las comunicaciones](communication-compliance.md)
- [Directivas de etiquetado automático](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md) 
