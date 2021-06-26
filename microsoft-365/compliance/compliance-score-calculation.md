---
title: Cálculo de la puntuación de cumplimiento
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Comprenda cómo Microsoft Compliance Manager calcula una puntuación personalizada en función de las acciones realizadas para abordar los riesgos y mejorar su posición de cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4e1e3f4b90b0a5e83a1e068cd30f76b3a8c7bb22
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149171"
---
# <a name="compliance-score-calculation"></a>Cálculo de la puntuación de cumplimiento

**En este artículo:** Obtenga información sobre cómo el Administrador de cumplimiento calcula una puntuación de cumplimiento para su organización. En este artículo se explica cómo  **interpretar** la puntuación , lo que incluye la evaluación de línea base de protección de **datos,** la supervisión continua y cómo se administran y puntuan los distintos tipos **de acciones.**

> [!IMPORTANT]
> Las recomendaciones del Administrador de cumplimiento no deberán interpretarse como una garantía de cumplimiento. Debe evaluar y validar la eficacia de los controles de los clientes según su entorno normativo. Estos servicios están sujetos a los términos y condiciones de los Términos [de servicios en línea](https://go.microsoft.com/fwlink/?linkid=2108910). Vea también Microsoft 365 [de licencias para seguridad y cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="how-to-read-your-compliance-score"></a>Cómo leer la puntuación de cumplimiento

El panel del Administrador de cumplimiento muestra la puntuación general de cumplimiento. Esta puntuación mide el progreso en completar las acciones de mejora recomendadas dentro de los controles. Su puntuación puede ayudarle a comprender su posición de cumplimiento actual. También puede ayudarle a priorizar las acciones en función de su potencial para reducir el riesgo.

Se asigna un valor de puntuación en tres niveles:

1. **Puntuación de acción de** mejora: cada acción tiene un impacto diferente en la puntuación en función del riesgo potencial implicado

2. **Puntuación de** control: esta puntuación es la suma de puntos ganados al completar acciones de mejora dentro del control. Esta suma se aplica en su totalidad a la puntuación general de cumplimiento cuando el control cumple las dos condiciones siguientes:
    - **El estado de** implementación es **igual a Implementado** o Implementación **alternativa** y
    - **Resultado de prueba** es igual a **Pasado**.

3. **Puntuación de** evaluación: esta puntuación es la suma de las puntuaciones de control. Se calcula con puntuaciones de acción. Cada acción de Microsoft y cada acción de mejora administrada por su organización se cuenta una vez, independientemente de la frecuencia con la que se hace referencia a ella en un control.

La puntuación general de cumplimiento se calcula con puntuaciones de acción, donde cada acción de Microsoft se cuenta una vez, cada acción técnica que administra se cuenta una vez y cada acción no técnica que administre se cuenta una vez por grupo. Esta lógica está diseñada para proporcionar la contabilidad más precisa de cómo se implementan y prueban las acciones en la organización. Es posible que observe que esto puede hacer que la puntuación general de cumplimiento sea diferente de la media de las puntuaciones de evaluación. Obtenga más información a [continuación sobre cómo se puntuan las acciones](#action-types-and-points).

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Puntuación inicial basada en Microsoft 365 base de protección de datos
  
El Administrador de cumplimiento le proporciona una puntuación inicial basada en la línea Microsoft 365 base de protección de datos. Esta línea base es un conjunto de controles que incluye normativas y estándares clave para la protección de datos y el gobierno general de datos. Esta línea base se basa en elementos principalmente de NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Standardization), así como de FedRAMP (Federal Risk and Authorization Management Program) y GDPR (Reglamento general de protección de datos de la Unión Europea).

La puntuación inicial se calcula de acuerdo con la evaluación predeterminada de la línea base de protección de datos proporcionada a todas las organizaciones. Tras su primera visita, el Administrador de cumplimiento ya está recopilando señales de sus Microsoft 365 soluciones. Verá de un vistazo el rendimiento de su organización con respecto a los estándares y normativas clave de protección de datos y verá las acciones de mejora sugeridas que deben realizarse.

Dado que cada organización tiene necesidades específicas, el Administrador de cumplimiento depende de usted para configurar y administrar evaluaciones que ayuden a minimizar y mitigar los riesgos de la forma más completa posible.

## <a name="how-compliance-manager-continuously-assesses-controls"></a>Cómo el Administrador de cumplimiento evalúa continuamente los controles

El Administrador de cumplimiento examina automáticamente el entorno Microsoft 365 y detecta la configuración del sistema, actualizando de forma continua y automática el estado de la acción técnica. Puntuación segura de Microsoft es el motor subyacente que realiza la supervisión.

El estado de la acción se actualiza en el panel cada 24 horas. Una vez que sigas una recomendación para implementar un control, normalmente verás el estado del control actualizado al día siguiente.

Por ejemplo, si activa la autenticación multifactor (MFA) en el portal de Azure AD, el Administrador de cumplimiento detecta la configuración y la refleja en los detalles de la solución de acceso de control. Por el contrario, si no activaste MFA, el Administrador de cumplimiento marca esa acción como una acción recomendada.

Obtenga más información sobre [puntuación segura y cómo funciona](../security/defender/microsoft-secure-score.md).
  
## <a name="action-types-and-points"></a>Tipos y puntos de acción

El Administrador de cumplimiento realiza un seguimiento de dos tipos de acciones:

1. **Acciones de mejora:** acciones que administra la organización.
2. **Acciones de Microsoft:** acciones que Microsoft administra.

Ambos tipos de acciones tienen puntos que cuentan para la puntuación general cuando se completa.

### <a name="technical-and-non-technical-actions"></a>Acciones técnicas y no técnicas

Las acciones se agrupan por su naturaleza técnica o no técnica. El impacto de puntuación de cada acción difiere según el tipo.

- **Las acciones** técnicas se implementan interactuando con la tecnología de una solución (por ejemplo, cambiando una configuración). Los puntos de las acciones técnicas se conceden una vez por acción, independientemente del número de grupos a los que pertenezca.

- **Las acciones no técnicas** son administradas por la organización e implementadas de formas distintas de trabajar con la tecnología de una solución. Existen dos tipos de acciones no técnicas: **documentación** y **operativas.** Los puntos de estas acciones se aplican a la puntuación de cumplimiento en un nivel de grupo. Esto significa que si existe una acción en varios grupos, recibirá el valor de punto de la acción cada vez que la implemente dentro de un grupo.

**Ejemplo de cómo se puntuan las acciones técnicas y no técnicas:**

Supongamos que tiene una acción técnica con un valor de 3 puntos que existe en 5 grupos y que tiene una acción no técnica con un valor de 3 puntos que existe en los mismos 5 grupos.

Si implementa correctamente la acción técnica, el número total de puntos que recibe es 3. Esto se debe a que solo necesita implementar la acción una vez para el inquilino. El estado de implementación y prueba de la acción técnica mostrará lo mismo en todas las instancias de esa acción, en cada grupo al que pertenezca.

Si implementa correctamente la acción no técnica en cada uno de los 5 grupos, el número total de puntos que recibe es 15. Esto se debe a que necesita implementar la acción en cada grupo. El estado de implementación y prueba de la acción no técnica variará entre grupos porque la acción se implementa por separado en cada uno de sus grupos.

Esta lógica de puntuación está diseñada para proporcionar la contabilidad más precisa de cómo se implementan y prueban las acciones en la organización.

### <a name="how-score-values-are-determined"></a>Cómo se determinan los valores de puntuación
 
A las acciones se les asigna un valor de puntuación en función de si son obligatorias o discrecionales, y si son preventivas, detectives o correctivas.

### <a name="mandatory-and-discretionary-actions"></a>Acciones obligatorias y discrecionales

 - **Las acciones obligatorias** no se pueden omitir, ya sea de forma intencionada o accidental. Un ejemplo de una acción obligatoria es una directiva de contraseña administrada centralmente que establece los requisitos de longitud, complejidad y expiración de la contraseña. Los usuarios deben cumplir estos requisitos para acceder al sistema.
  
 - **Las acciones discrecionales** dependen de los usuarios para comprender y cumplir una directiva. Por ejemplo, una directiva que requiere que los usuarios bloqueen el equipo cuando lo abandonen es una acción discrecional porque depende del usuario.
  
### <a name="preventative-detective-and-corrective-actions"></a>Acciones preventivas, de detectives y correctivas
  
 - Las **acciones preventivas** abordan unos riesgos determinados. Por ejemplo, proteger la información en reposo con cifrado es una acción preventiva contra ataques y vulneraciones. La separación de tareas es una acción preventiva para administrar los conflictos de intereses y proteger contra el fraude.
  
 - **Las acciones de detective** supervisan activamente los sistemas para identificar condiciones o comportamientos irregulares que representan un riesgo o que se pueden usar para detectar intrusiones o infracciones. Algunos ejemplos son la auditoría de acceso al sistema y las acciones administrativas con privilegios. Las auditorías de cumplimiento normativo son un tipo de acción de detective que se usa para encontrar problemas de proceso.
  
- **Las acciones correctivas** intentan mantener los efectos adversos de un incidente de seguridad al mínimo, tomar medidas correctivas para reducir el efecto inmediato y revertir el daño si es posible. La respuesta a incidentes de privacidad es una acción correctiva para limitar el daño y restaurar los sistemas a un estado operativo después de una infracción.
  
Cada acción tiene un valor asignado en el Administrador de cumplimiento en función del riesgo que representa:

|**Type**|**Puntuación asignada**|
|:-----|:-----|
| Obligatorio preventivo | 27 |
| Discrecional preventiva | 9  |
| Detective obligatorio | 3  |
| Detective discrecional | 1  |
| Obligatoria correctiva | 3  |
| Discrecionalidad correctiva | 1  |
  
![Valores de punto de acción del Administrador de cumplimiento](../media/compliance-score-action-scoring.png "Valores de punto de acción del Administrador de cumplimiento")