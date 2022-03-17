---
title: Más información sobre las entidades con nombre (versión preliminar)
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
ms.openlocfilehash: 79f375fecf09a6f7ffe4c1a97b8d6864fbfb3e13
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63524871"
---
# <a name="learn-about-named-entities-preview"></a>Más información sobre las entidades con nombre (versión preliminar)

> [!IMPORTANT]
> La característica de entidades con nombre se está implementando y aparecerá en el espacio empresarial cuando esté disponible. Compruebe si están en el explorador de contenido y en el flujo de creación de directivas de prevención de pérdida de datos (DLP). 

*Las entidades con nombre* son [tipos de información confidencial](sensitive-information-type-learn-about.md) (SIT). Son diccionarios complejos y clasificadores basados en patrones que puede usar para detectar nombres de personas, direcciones físicas y términos y condiciones médicas. Puedes verlos en el Centro de cumplimiento > **clasificación de datos > tipos de información confidencial**. Esta es una lista parcial de dónde puede usar los SIT:

- [Directivas de prevención de pérdida de datos (DLP)](dlp-learn-about-dlp.md) 
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Administración de riesgos internos](insider-risk-management-solution-overview.md)
- [Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)

DLP hace un uso especial de las entidades con nombre en plantillas de directiva mejoradas *, que* son directivas DLP preconfiguradas que puede personalizar para las necesidades de las organizaciones. También puede crear [sus propias directivas DLP](create-test-tune-dlp-policy.md) [a partir](create-a-dlp-policy-from-a-template.md) de una plantilla en blanco y usar una entidad con nombre SIT como condición.

<!-- There are many other SITs that detect strings like social security, credit card, or bank account numbers to identify sensitive items. For more information, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md).-->



## <a name="examples-of-named-entity-sits"></a>Ejemplos de SITs de entidad con nombre

Los SIT de entidad con nombre vienen en dos *sabores,* agrupados *y desagrupados*

Los SIT de entidad con nombre agrupados detectan todas las coincidencias posibles. Úsenlos como criterios generales en las directivas DLP para detectar elementos confidenciales.

Los SIT de entidad con nombre desagregados tienen un enfoque más estrecho, como un solo país. Úselos cuando necesite una directiva DLP con un ámbito de detección más estrecho.
 
Estos son algunos ejemplos de SIT de entidad con nombre. Puedes encontrar los 52 en el Centro de cumplimiento > **clasificación de datos > tipos de información confidencial**.

|Entidad con nombre |Descripción  |Bundled/Unbundled  |
|---------|---------|---------|
|Todos los nombres completos    |detectará todas las coincidencias posibles de nombres completos         |   bundled      |
|Todas las direcciones físicas    |detectará todas las coincidencias posibles de direcciones físicas     | bundled |
|Todos los términos y condiciones médicos    |detectará todas las coincidencias posibles de términos y condiciones médicas |bundled |
|Direcciones físicas de Australia |  Detecta patrones relacionados con direcciones físicas de Australia. |desagrupados |
|Términos del examen de sangre     |Detecta términos relacionados con exámenes de sangre, como "hCG". Solo términos en inglés.      |desagrupados |
|Nombres de medicación de marca     |Detecta los nombres de los medicamentos de marca, como "Tylenol". Solo términos en inglés.         |desagrupados |

## <a name="examples-of-enhanced-dlp-policies"></a>Ejemplos de directivas DLP mejoradas

Estos son algunos ejemplos de directivas DLP mejoradas que usan SITs de entidad con nombre. Puede encontrar los 10 en el Centro de cumplimiento y > **prevención de pérdida de datos > Crear directiva**. Las plantillas mejoradas se pueden usar en DLP y el etiquetado automático.

|Categoría de directiva  |Plantilla  |Descripción  |
|---------|---------|---------|
|Financiera|Ley Gramm-Leach-Bliley (GLBA) de Ee.UU. Mejorada         |Ayuda a detectar la presencia de datos sujetos a la Ley Gramm-Leach.Bliley (GLBA), incluidos los datos como números de Seguridad Social o de las tarjetas de crédito. Esta plantilla mejorada amplía el original al detectar también los nombres completos de las personas, ESTADOS UNIDOS/Reino Unido. número de pasaporte, número de licencia de conducir de ESTADOS UNIDOS y direcciones físicas de Estados Unidos.         |
| Medicina y salud   |Ley de registros de salud de Australia (ley HRIP) mejorada         |Ayuda a detectar la presencia de datos considerados comúnmente sujetos a la Ley de privacidad de información y registros de salud (HRIP) en Australia, como por ejemplo el número de expediente médico y el número de archivo fiscal. Esta plantilla mejorada amplía el original al detectar también los nombres completos de las personas, los términos y condiciones médicos y las direcciones físicas de Australia.         |
|Privacidad   |Reglamento general de protección de datos (RGPD) mejorado         | Ayuda a detectar la presencia de información personal de personas dentro de la Unión Europea (UE) para ayudar a cumplir con las obligaciones de privacidad del RGPD. Esta plantilla mejorada detecta los nombres completos de las personas y las direcciones físicas de los países de la UE.        |


## <a name="next-steps"></a>Siguientes pasos

- [Uso de entidades con nombre en las directivas de prevención de pérdida de datos (versión preliminar)](named-entities-use.md)


## <a name="for-further-information"></a>Para obtener más información
<!--- [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)-->
- [Información sobre tipos de información confidencial](sensitive-information-type-learn-about.md)
- [Crear un tipo personalizado de información confidencial](create-a-custom-sensitive-information-type.md)
- [Crear un tipo de información confidencial personalizada en PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Directivas de prevención de pérdida de datos (DLP)](data-loss-prevention-policies.md) 
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Etiquetas de retención](retention.md)
- [Cumplimiento de las comunicaciones](communication-compliance.md)
- [Directivas de etiquetado automático](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md) 
