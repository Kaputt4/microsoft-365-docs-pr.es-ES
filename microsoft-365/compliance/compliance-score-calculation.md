---
title: Cálculo de la puntuación de cumplimiento
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Comprenda cómo Microsoft Purview Compliance Manager calcula una puntuación personalizada en función de las acciones realizadas para abordar los riesgos y mejorar su posición de cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a33cbe9c4ea5b12ab0fec40068ba7dcd2f561e4e
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66635685"
---
# <a name="compliance-score-calculation"></a>Cálculo de la puntuación de cumplimiento

**En este artículo:** Obtenga información sobre cómo el Administrador de cumplimiento calcula una puntuación de cumplimiento para su organización. En este artículo se explica cómo **interpretar la puntuación**, lo que incluye la **evaluación de base de referencia de protección de datos** , **la supervisión continua** y **cómo se administran y puntúan los distintos tipos de acciones**.

> [!IMPORTANT]
> Las recomendaciones del Administrador de cumplimiento no deberán interpretarse como una garantía de cumplimiento. Depende de usted evaluar y validar la eficacia de los controles de los clientes según su entorno normativo. Estos servicios están sujetos a los términos y condiciones de los [Términos del producto](https://go.microsoft.com/fwlink/?linkid=2108910). Consulte también [la guía de licencias de Microsoft 365 para obtener información sobre seguridad y cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-compliance-manager).

## <a name="how-to-read-your-compliance-score"></a>Cómo leer la puntuación de cumplimiento

El panel administrador de cumplimiento muestra la puntuación de cumplimiento general. Esta puntuación mide el progreso al completar las acciones de mejora recomendadas dentro de los controles. La puntuación puede ayudarle a comprender la posición de cumplimiento actual. También puede ayudarle a priorizar las acciones en función de su potencial para reducir el riesgo.

Un valor de puntuación se asigna en tres niveles:

1. **Puntuación de acción de mejora**: cada acción tiene un impacto diferente en la puntuación en función del riesgo potencial implicado

2. **Puntuación de control**: esta puntuación es la suma de los puntos obtenidos al completar acciones de mejora dentro del control. Esta suma se aplica en su totalidad a la puntuación de cumplimiento general cuando el control cumple las dos condiciones siguientes:
    - **El estado de implementación** es igual a implementación **implementada** o **alternativa**, y
    - **El resultado de la prueba** es igual a **Pasado**.

3. **Puntuación de evaluación**: esta puntuación es la suma de las puntuaciones de control. Se calcula mediante puntuaciones de acción. Cada acción de Microsoft y cada acción de mejora administrada por su organización se cuentan una vez, independientemente de la frecuencia con la que se haga referencia a ella en un control.

La puntuación de cumplimiento general se calcula mediante puntuaciones de acción, donde cada acción de Microsoft se cuenta una vez, cada acción técnica que administra se cuenta una vez y cada acción no técnica que administra se cuenta una vez por grupo. Esta lógica está diseñada para proporcionar la contabilidad más precisa de cómo se implementan y prueban las acciones en su organización. Es posible que observe que esto puede hacer que la puntuación de cumplimiento general difiera del promedio de las puntuaciones de evaluación. Obtenga más información a continuación sobre [cómo se puntúan las acciones](#action-types-and-points).

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Puntuación inicial basada en la línea base de protección de datos de Microsoft 365
  
El Administrador de cumplimiento proporciona una puntuación inicial basada en la línea base de protección de datos de Microsoft 365. Esta línea base es un conjunto de controles que incluye normas clave y estándares para la protección de datos y la gobernanza general de datos. Esta línea de base extrae elementos principalmente de NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Standardization), así como de FedRAMP (Federal Risk and Authorization Management Program) y RGPD (Reglamento general de protección de datos de la Unión Europea).

La puntuación inicial se calcula según la evaluación predeterminada de la línea base de protección de datos proporcionada a todas las organizaciones. Tras su primera visita, el Administrador de cumplimiento ya está recopilando señales de las soluciones de Microsoft 365. Verá de un vistazo cómo funciona su organización en relación con los estándares y regulaciones clave de protección de datos, y verá las acciones de mejora sugeridas que debe realizar.

Dado que cada organización tiene necesidades específicas, el Administrador de cumplimiento se basa en usted para configurar y administrar evaluaciones para ayudar a minimizar y mitigar el riesgo de la forma más completa posible.

## <a name="how-compliance-manager-continuously-assesses-controls"></a>Cómo el Administrador de cumplimiento evalúa continuamente los controles

El Administrador de cumplimiento identifica automáticamente la configuración en el entorno de Microsoft 365 que ayuda a determinar cuándo determinadas configuraciones cumplen los requisitos de implementación de acciones de mejora. El Administrador de cumplimiento detecta señales de otras soluciones de cumplimiento que puede haber implementado, incluida la administración del ciclo de vida de los datos, la protección de la información, el cumplimiento de comunicaciones y la administración de riesgos internos, y también aprovecha la supervisión de puntuación segura de Microsoft de las acciones de mejora complementarias.

El estado de la acción se actualiza en el panel en un plazo de 24 horas después de realizar un cambio. Una vez que siga una recomendación para implementar un control, normalmente verá el estado del control actualizado al día siguiente.

Por ejemplo, si activa la autenticación multifactor (MFA) en el portal de Azure AD, el Administrador de cumplimiento detecta la configuración y la refleja en los detalles de la solución de acceso de control. Por el contrario, si no ha activado MFA, el Administrador de cumplimiento lo marca como una acción recomendada.

Obtenga más información sobre [la puntuación segura y cómo funciona](../security/defender/microsoft-secure-score.md).
  
## <a name="action-types-and-points"></a>Tipos y puntos de acción

El Administrador de cumplimiento realiza un seguimiento de dos tipos de acciones:

1. **Acciones de mejora**: acciones que la organización administra.
2. **Acciones de Microsoft**: acciones que administra Microsoft.

Ambos tipos de acciones tienen puntos que cuentan para la puntuación general cuando se completan.

### <a name="technical-and-non-technical-actions"></a>Acciones técnicas y no técnicas

Las acciones se agrupan por si son de naturaleza técnica o no técnica. El impacto de puntuación de cada acción difiere por tipo.

- **Las acciones técnicas** se implementan interactuando con la tecnología de una solución (por ejemplo, cambiando una configuración). Los puntos de las acciones técnicas se conceden una vez por acción, independientemente del número de grupos a los que pertenezca.

- Su organización administra **las acciones no técnicas** y las implementa de maneras distintas a trabajar con la tecnología de una solución. Hay dos tipos de acciones no técnicas: **documentación** y **operativas**. Los puntos de estas acciones se aplican a la puntuación de cumplimiento en un nivel de grupo. Esto significa que si existe una acción en varios grupos, recibirá el valor de punto de la acción cada vez que la implemente dentro de un grupo.

**Ejemplo de cómo se puntúan las acciones técnicas y no técnicas:**

Supongamos que tiene una acción técnica por valor de 3 puntos que existe en 5 grupos, y tiene una acción no técnica por valor de 3 puntos que existe en los mismos 5 grupos.

Si implementa correctamente la acción técnica, el número total de puntos que recibe es de 3. Esto se debe a que solo necesita implementar la acción una vez para el inquilino. El estado de implementación y prueba de la acción técnica mostrará lo mismo en todas las instancias de esa acción, en cada grupo al que pertenece.

Si implementa correctamente la acción no técnica en cada uno de los cinco grupos, el número total de puntos que recibe es de 15. Esto se debe a que debe implementar la acción en cada grupo. El estado de implementación y prueba de la acción no técnica variará entre grupos porque la acción se implementa por separado dentro de cada uno de sus grupos.

Esta lógica de puntuación está diseñada para proporcionar la contabilidad más precisa de cómo se implementan y prueban las acciones en su organización.

### <a name="how-score-values-are-determined"></a>Cómo se determinan los valores de puntuación

A las acciones se les asigna un valor de puntuación en función de si son obligatorias o discrecionales, y si son preventivas, detectives o correctivas.

### <a name="mandatory-and-discretionary-actions"></a>Acciones obligatorias y discrecionales

- Las **acciones obligatorias** no se pueden omitir, ya sea de forma intencionada o accidental. Un ejemplo de una acción obligatoria es una directiva de contraseña administrada centralmente que establece los requisitos de longitud, complejidad y expiración de contraseñas. Los usuarios deben cumplir estos requisitos para acceder al sistema.
  
- **Las acciones discrecionales** dependen de los usuarios para comprender y cumplir una directiva. Por ejemplo, una directiva que requiere que los usuarios bloqueen el equipo cuando lo abandonen es una acción discrecional porque depende del usuario.
  
### <a name="preventative-detective-and-corrective-actions"></a>Acciones preventivas, detectives y correctivas
  
- **Las acciones preventivas** abordar riesgos específicos. Por ejemplo, la protección de la información en reposo mediante cifrado es una acción preventiva frente a ataques e infracciones. La separación de obligaciones es una acción preventiva para administrar los conflictos de interés y protegerse contra el fraude.
  
- **Las acciones de los detectives** supervisan activamente los sistemas para identificar condiciones o comportamientos irregulares que representan un riesgo, o que se pueden usar para detectar intrusiones o infracciones. Algunos ejemplos son la auditoría de acceso al sistema y las acciones administrativas con privilegios. Las auditorías de cumplimiento normativo son un tipo de acción de detective que se usa para buscar problemas de proceso.
  
- **Las acciones correctivas** intentan mantener al mínimo los efectos adversos de un incidente de seguridad, tomar medidas correctivas para reducir el efecto inmediato e invertir el daño si es posible. La respuesta a incidentes de privacidad es una acción correctiva para limitar el daño y restaurar los sistemas a un estado operativo después de una infracción.
  
Cada acción tiene un valor asignado en el Administrador de cumplimiento en función del riesgo que representa:

|**Tipo**|**Puntuación asignada**|
|:-----|:-----|
| Obligatorio preventivo | 27 |
| Discrecional preventiva | 9  |
| Detective obligatorio | 3  |
| Detective discrecional | 1  |
| Correctiva obligatoria | 3  |
| Discreción correctiva | 1  |
  
![Valores de punto de acción del Administrador de cumplimiento.](../media/compliance-score-action-scoring.png "Valores de punto de acción del Administrador de cumplimiento")
