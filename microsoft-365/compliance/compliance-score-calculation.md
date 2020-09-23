---
title: Cálculo de puntuación de cumplimiento
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Comprenda cómo Microsoft Compliance Manager calcula una puntuación personalizada en función de las acciones realizadas para enfrentarse a los riesgos y mejorar la postura de cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9fd71b4953dc40a3c1e7601f42f595488fcef98b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204517"
---
# <a name="compliance-score-calculation"></a>Cálculo de puntuación de cumplimiento

> [!IMPORTANT]
> Las recomendaciones del administrador de cumplimiento no deben interpretarse como una garantía de cumplimiento. Depende de usted evaluar y validar la eficacia de los controles de cliente según su entorno de reglamentación. Estos servicios están sujetos a los términos y condiciones de los [términos de servicios en línea](https://go.microsoft.com/fwlink/?linkid=2108910). Vea también la [Guía de licencias de Microsoft 365 por seguridad y cumplimiento normativo](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="how-to-read-your-compliance-score"></a>Cómo leer la puntuación de cumplimiento

El panel del administrador de cumplimiento muestra la puntuación de cumplimiento general. Esta puntuación mide el progreso de la finalización de las acciones de mejora recomendadas dentro de los controles. Su puntuación puede ayudarle a comprender su postura de cumplimiento actual. También puede ayudarle a priorizar las acciones en función de su potencial para reducir el riesgo.

Un valor de puntuación se asigna en tres niveles:

1. **Puntuación**de la acción de mejora: cada acción tiene un impacto diferente en su puntuación en función del riesgo potencial implicado

2. **Puntuación de control**: esta puntuación es la suma de los puntos obtenidos al completar acciones de mejora en el control. Esta suma se aplica en su totalidad a la puntuación de cumplimiento general cuando el control cumple las dos condiciones siguientes:
    - El **Estado de implementación** es igual a **implementación alternativa**o **implementada** , y
    - El resultado de la **prueba** es **correcto**.

3. **Puntuación**de la evaluación: esta puntuación es la suma de las puntuaciones del control. Se calcula mediante resultados de acciones. Cada acción de Microsoft y cada acción de mejora administradas por la organización se cuentan una vez, independientemente de la frecuencia con la que se hace referencia en un control.

La puntuación de cumplimiento general se calcula mediante resultados de acciones, donde cada acción de Microsoft se cuenta una vez, cada acción técnica que administre se contará una vez y cada acción no técnica que administre se contará una vez por grupo. Esta lógica está diseñada para proporcionar la contabilidad más precisa de cómo se implementan y se prueban las acciones en la organización. Es posible que observe que esto puede hacer que la puntuación de cumplimiento global sea diferente de la media de los resultados de la evaluación. Lea más información a continuación sobre [cómo se puntuan las acciones](#action-types-and-points).

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Puntuación inicial basada en la línea base de protección de datos 365 de Microsoft
  
El administrador de cumplimiento le da una puntuación inicial basada en la línea base de protección de datos 365 de Microsoft. Esta línea base es un conjunto de controles que incluye normas y estándares clave para la protección de datos y el gobierno de datos general. Esta base dibuja los elementos principalmente desde NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Normalization), así como de FedRAMP (programa federal de administración de riesgos y autorización) y RGPD (norma general de protección de datos de la Unión Europea).

La puntuación inicial se calcula de acuerdo con la evaluación de línea base de protección de datos predeterminada que se proporciona a todas las organizaciones. Tras su primera visita, el administrador de cumplimiento ya está recopilando señales de sus soluciones de Microsoft 365. Ver? a simple vista sobre el rendimiento de su organización con respecto a los estándares y regulaciones clave de protección de datos y ver las acciones de mejora sugeridas que deben tomarse.

Como cada organización tiene necesidades específicas, el administrador de cumplimiento depende de que configure y administre las evaluaciones para ayudar a minimizar y mitigar el riesgo de la forma más completa posible.

## <a name="how-compliance-manager-continuously-assesses-controls"></a>Cómo evalúa el administrador de cumplimiento de forma continua los controles

El administrador de cumplimiento analiza automáticamente el entorno de Microsoft 365 y detecta la configuración del sistema, actualizando de forma continua y automática el estado de la acción técnica. La calificación segura de Microsoft es el motor subyacente que realiza la supervisión.

El estado de la acción se actualiza en el panel cada 24 horas. Una vez que haya seguido una recomendación para implementar un control, normalmente verá que el estado del control se actualizó el día siguiente.

Por ejemplo, si activa la autenticación multifactor (MFA) en el portal de Azure AD, el administrador de cumplimiento detecta la configuración y la refleja en los detalles de la solución de control de acceso. Por el contrario, si no activó MFA, el administrador de cumplimiento marca las marcas como una acción recomendada para realizar.

Obtenga más información sobre [la puntuación segura y cómo funciona](../security/mtp/microsoft-secure-score-new.md).
  
## <a name="action-types-and-points"></a>Tipos de acción y puntos

El administrador de cumplimiento sigue dos tipos de acciones:

1. **Sus acciones de mejora**: las acciones que administra su organización.
2. **Acciones de Microsoft**: acciones que administra Microsoft.

Ambos tipos de acciones tienen puntos que cuentan hacia la calificación general cuando se completa.

### <a name="technical-and-non-technical-actions"></a>Acciones técnicas y no técnicas

Las acciones se agrupan en función de si son de naturaleza técnica o no técnica. El impacto de los resultados de cada acción difiere por tipo.

- **Las acciones técnicas** se implementan mediante la interacción con la tecnología de una solución (por ejemplo, el cambio de una configuración). Los puntos de las acciones técnicas se conceden una vez por acción, independientemente del número de grupos a los que pertenece.

- Las **acciones no técnicas** se administran en la organización y se implementan de maneras distintas al trabajo con la tecnología de una solución. Hay dos tipos de acciones no técnicas: **documentación** y **operativa**. Los puntos para estas acciones se aplican a la puntuación de cumplimiento en un nivel de grupo. Esto significa que si existe una acción en varios grupos, recibirá el valor de punto de la acción cada vez que lo implemente dentro de un grupo.

**Ejemplo de cómo se califican las acciones técnicas y no técnicas:**

Supongamos que tiene una acción técnica que merece 3 puntos que existen en 5 grupos y que tiene una acción no técnica de 3 puntos que existe en los mismos cinco grupos.

Si implementa correctamente la acción técnica, el número total de puntos que recibe es 3. Esto se debe a que solo tiene que implementar la acción una vez para el inquilino. El estado de implementación y pruebas de la acción técnica mostrará lo mismo en todas las instancias de esa acción, en cada grupo al que pertenezca.

Si implementa correctamente la acción no técnica en cada uno de los 5 grupos, el número total de puntos que recibe es 15. Esto se debe a que debe implementar la acción en cada grupo. La implementación y el estado de prueba de la acción no técnica diferirán entre grupos, ya que la acción se implementa por separado en cada uno de sus grupos.

Esta lógica de puntuación está diseñada para proporcionar la contabilidad más precisa de cómo se implementan y se prueban las acciones en la organización.

### <a name="how-score-values-are-determined"></a>Cómo se determinan los valores de puntuación
 
A las acciones se les asigna un valor de puntuación en función de si son obligatorios o discrecionales y si son preventivos, detectives o correctivos.

### <a name="mandatory-and-discretionary-actions"></a>Acciones obligatorias y discrecionales

 - **Las acciones obligatorias** no se pueden omitir, ya sea de forma intencionada o accidental. Un ejemplo de acción obligatoria es una directiva de contraseñas administrada centralmente que establece los requisitos de longitud, complejidad y expiración de la contraseña. Los usuarios deben seguir estos requisitos para obtener acceso al sistema.
  
 - **Las acciones discrecionales** dependen de que los usuarios sepan y sigan una directiva. Por ejemplo, una directiva que requiere que los usuarios bloqueen su equipo cuando lo abandonan es una acción discrecional porque depende del usuario.
  
### <a name="preventative-detective-and-corrective-actions"></a>Acciones preventivas, de detectives y correctivas
  
 - **Las acciones preventivas** solucionan riesgos específicos. Por ejemplo, la protección de la información en reposo mediante el cifrado es una acción preventiva contra ataques e infracciones. La separación de tareas es una acción preventiva para administrar conflictos de intereses y proteger contra el fraude.
  
 - **Las acciones de detectives** supervisan activamente los sistemas para identificar situaciones o comportamientos anómalos que representen el riesgo o que se pueden usar para detectar intrusiones o infracciones. Algunos ejemplos son la auditoría de acceso al sistema y las acciones administrativas con privilegios. Las auditorías de cumplimiento normativo son un tipo de acción de detective que se usa para encontrar problemas del proceso.
  
- **Las acciones correctivas** intentan mantener al mínimo los efectos adversos de un incidente de seguridad, emprender acciones correctivas para reducir el efecto inmediato e invertir el daño, si es posible. La respuesta de la incidencia de privacidad es una acción correctiva que limita los daños y restaura los sistemas a un estado operativo después de una infracción.
  
Cada acción tiene asignado un valor en el administrador de cumplimiento según el riesgo que representa:

|**Tipo**|**Puntuación asignada**|
|:-----|:-----|
| Obligatorio de prevención | ,27 |
| Discrecional preventivo | 9  |
| Detective obligatorio | 3 |
| Discrecionales de detectives | 1  |
| Obligatorio de corrección | 3 |
| Discrecionales correctivas | 1  |
  
![Valores del punto de acción del administrador de cumplimiento](../media/compliance-score-action-scoring.png "Valores del punto de acción del administrador de cumplimiento")