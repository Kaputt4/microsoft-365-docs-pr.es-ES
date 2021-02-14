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
description: Comprenda cómo el Administrador de cumplimiento de Microsoft calcula una puntuación personalizada en función de las acciones tomadas para abordar los riesgos y mejorar su posición de cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f1707e0117d0a61f572716f21d13a02821955401
ms.sourcegitcommit: 61d7284b412d0f7bbd8bbb2225c2e6324f86b717
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262273"
---
# <a name="compliance-score-calculation"></a>Cálculo de puntuación de cumplimiento

**En este artículo:** Obtenga información sobre cómo el Administrador de cumplimiento calcula una puntuación de cumplimiento para su organización. En este artículo se explica cómo  interpretar la puntuación, lo que incluye la evaluación de línea base de protección de datos, la supervisión continua y cómo se administran y puntuan los distintos tipos de **acciones.** 

> [!IMPORTANT]
> Las recomendaciones del Administrador de cumplimiento no deberán interpretarse como una garantía de cumplimiento. Usted debe evaluar y validar la eficacia de los controles de los clientes según su entorno normativo. Estos servicios están sujetos a los términos y condiciones de los [Términos de Online Services.](https://go.microsoft.com/fwlink/?linkid=2108910) Vea también la [guía de licencias de Microsoft 365 para seguridad y cumplimiento.](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="how-to-read-your-compliance-score"></a>Cómo leer la puntuación de cumplimiento

El panel del Administrador de cumplimiento muestra la puntuación de cumplimiento general. Esta puntuación mide el progreso de completar las acciones de mejora recomendadas dentro de los controles. Su puntuación puede ayudarle a comprender su posición de cumplimiento actual. También puede ayudarle a priorizar las acciones en función de su potencial para reducir el riesgo.

Se asigna un valor de puntuación en tres niveles:

1. **Puntuación de acción de** mejora: cada acción tiene un impacto diferente en la puntuación en función del riesgo potencial implicado.

2. **Puntuación de** control: esta puntuación es la suma de puntos obtenidos al completar acciones de mejora dentro del control. Esta suma se aplica en su totalidad a la puntuación de cumplimiento general cuando el control cumple las dos condiciones siguientes:
    - **El estado de** implementación es **igual a implementación** o implementación **alternativa,** y
    - **El resultado de la** prueba es igual a **Pasado**.

3. **Puntuación de** evaluación: esta puntuación es la suma de las puntuaciones de control. Se calcula mediante puntuaciones de acción. Cada acción de Microsoft y cada acción de mejora administrada por su organización se cuenta una vez, independientemente de la frecuencia con la que se hace referencia a ella en un control.

La puntuación de cumplimiento general se calcula mediante puntuaciones de acción, donde cada acción de Microsoft se cuenta una vez, cada acción técnica que administra se cuenta una vez y cada acción no técnica que administra se cuenta una vez por grupo. Esta lógica está diseñada para proporcionar una contabilidad más precisa de cómo se implementan y prueban las acciones en la organización. Es posible que observe que esto puede hacer que la puntuación general de cumplimiento sea diferente del promedio de las puntuaciones de evaluación. Obtenga más información a continuación [sobre cómo se puntuan las acciones.](#action-types-and-points)

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Puntuación inicial basada en la línea base de protección de datos de Microsoft 365
  
El Administrador de cumplimiento le proporciona una puntuación inicial basada en la línea base de protección de datos de Microsoft 365. Esta línea base es un conjunto de controles que incluye normas y estándares clave para la protección de datos y el gobierno general de datos. Esta línea base dibuja elementos principalmente de NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Standardization), así como de FedRAMP (Programa federal de administración de riesgos y autorización) y RGPD (Reglamento general de protección de datos de la Unión Europea).

La puntuación inicial se calcula de acuerdo con la evaluación de línea base de protección de datos predeterminada proporcionada a todas las organizaciones. Tras su primera visita, el Administrador de cumplimiento ya está recopilando señales de sus soluciones de Microsoft 365. Verá de un vistazo el rendimiento de su organización en relación con los estándares y normativas clave de protección de datos, y verá las acciones de mejora sugeridas que debe realizar.

Dado que cada organización tiene necesidades específicas, el Administrador de cumplimiento depende de usted para configurar y administrar evaluaciones para ayudar a minimizar y mitigar los riesgos de la forma más completa posible.

## <a name="how-compliance-manager-continuously-assesses-controls"></a>Cómo evalúa continuamente el Administrador de cumplimiento los controles

El Administrador de cumplimiento examina automáticamente el entorno de Microsoft 365 y detecta la configuración del sistema, actualizando continua y automáticamente el estado de la acción técnica. Puntuación de seguridad de Microsoft es el motor subyacente que realiza la supervisión.

El estado de la acción se actualiza en el panel cada 24 horas. Una vez que sigas una recomendación para implementar un control, normalmente verás el estado del control actualizado el día siguiente.

Por ejemplo, si activa la autenticación multifactor (MFA) en el portal de Azure AD, el Administrador de cumplimiento detecta la configuración y la refleja en los detalles de la solución de acceso de control. Por el contrario, si no ha activar MFA, el Administrador de cumplimiento lo marca como una acción recomendada que debe realizar.

Obtenga más información sobre [la puntuación de seguridad y cómo funciona.](../security/mtp/microsoft-secure-score-new.md)
  
## <a name="action-types-and-points"></a>Tipos de acción y puntos

El Administrador de cumplimiento realiza un seguimiento de dos tipos de acciones:

1. **Sus acciones de mejora:** acciones que administra su organización.
2. **Acciones de Microsoft:** acciones que administra Microsoft.

Ambos tipos de acciones tienen puntos que cuentan para la puntuación general cuando se completa.

### <a name="technical-and-non-technical-actions"></a>Acciones técnicas y no técnicas

Las acciones se agrupan por su naturaleza técnica o no técnica. El impacto en la puntuación de cada acción difiere según el tipo.

- **Las acciones** técnicas se implementan interactuando con la tecnología de una solución (por ejemplo, cambiando una configuración). Los puntos de las acciones técnicas se conceden una vez por acción, independientemente del número de grupos a los que pertenezca.

- **Las acciones no técnicas** son administradas por su organización e implementadas de maneras distintas de trabajar con la tecnología de una solución. Existen dos tipos de acciones no técnicas: **documentación** y **operaciones.** Los puntos de estas acciones se aplican a la puntuación de cumplimiento en el nivel de grupo. Esto significa que si existe una acción en varios grupos, recibirá el valor de punto de la acción cada vez que la implemente dentro de un grupo.

**Ejemplo de puntuación de las acciones técnicas y no técnicas:**

Supongamos que tiene una acción técnica de 3 puntos que existe en 5 grupos y que tiene una acción no técnica de 3 puntos que existe en los mismos 5 grupos.

Si implementa correctamente la acción técnica, el número total de puntos que recibe es 3. Esto se debe a que solo necesita implementar la acción una vez para su espacio empresarial. El estado de implementación y prueba de la acción técnica mostrará lo mismo en todas las instancias de esa acción, en todos los grupos a los que pertenece.

Si implementa correctamente la acción no técnica en cada uno de los 5 grupos, el número total de puntos que recibe es 15. Esto se debe a que necesita implementar la acción en cada grupo. El estado de implementación y prueba de la acción no técnica variará entre grupos porque la acción se implementa por separado en cada uno de sus grupos.

Esta lógica de puntuación está diseñada para proporcionar la contabilidad más precisa de cómo se implementan y prueban las acciones en la organización.

### <a name="how-score-values-are-determined"></a>Cómo se determinan los valores de puntuación
 
Las acciones se asignan a un valor de puntuación en función de si son obligatorias o discrecionales, y si son preventivas, de investigación o correctivas.

### <a name="mandatory-and-discretionary-actions"></a>Acciones obligatorias y discrecionales

 - **Las acciones obligatorias** no se pueden omitir, ya sea de forma intencionada o accidental. Un ejemplo de una acción obligatoria es una directiva de contraseña administrada de forma centralizada que establece los requisitos de longitud, complejidad y expiración de la contraseña. Los usuarios deben seguir estos requisitos para acceder al sistema.
  
 - **Las acciones discrecionales** dependen de que los usuarios comprendan y se adhiera a una directiva. Por ejemplo, una directiva que requiere que los usuarios bloqueen su equipo cuando lo dejen es una acción discrecional porque depende del usuario.
  
### <a name="preventative-detective-and-corrective-actions"></a>Acciones preventivas, de investigación y correctivas
  
 - **Las acciones preventivas** abordan riesgos específicos. Por ejemplo, proteger la información en reposo mediante cifrado es una acción preventiva contra ataques e infracciones. La separación de funciones es una acción preventiva para administrar conflictos de intereses y proteger contra el fraude.
  
 - **Las acciones de** investigación supervisan activamente los sistemas para identificar las condiciones o comportamientos irregulares que representan un riesgo, o que se pueden usar para detectar intrusiones o infracciones. Algunos ejemplos son la auditoría de acceso al sistema y las acciones administrativas con privilegios. Las auditorías de cumplimiento normativo son un tipo de acción de investigación que se usa para buscar problemas de procesos.
  
- **Las acciones correctivas** intentan reducir al mínimo los efectos negativos de un incidente de seguridad, tomar medidas correctivas para reducir el efecto inmediato y revertir los daños si es posible. La respuesta a incidentes de privacidad es una acción correctiva para limitar los daños y restaurar los sistemas a un estado operativo después de una infracción.
  
Cada acción tiene un valor asignado en el Administrador de cumplimiento en función del riesgo que representa:

|**Tipo**|**Puntuación asignada**|
|:-----|:-----|
| Obligatorio preventivo | 27 |
| Discrecionalidad preventiva | 9  |
| Inspector obligatorio | 3  |
| Investigación discrecional | 1  |
| Correctivo obligatorio | 3  |
| Correctiva discrecional | 1  |
  
![Valores de punto de acción del Administrador de cumplimiento](../media/compliance-score-action-scoring.png "Valores de punto de acción del Administrador de cumplimiento")