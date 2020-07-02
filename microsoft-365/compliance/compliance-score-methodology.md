---
title: Cálculo de la puntuación de cumplimiento de Microsoft (vista previa)
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
description: Comprenda cómo la puntuación de cumplimiento de Microsoft calcula una puntuación personalizada en función de las acciones realizadas para enfrentarse a los riesgos y mejorar la postura de cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 552f2f85c4659ec24bc717d41c71733764d898ed
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023251"
---
# <a name="compliance-score-preview-calculation"></a>Cálculo de la puntuación de cumplimiento (vista previa)

> [!IMPORTANT]
> Las recomendaciones de la puntuación de cumplimiento y del Administrador de cumplimiento no deben interpretarse como una garantía de cumplimiento. Depende de usted evaluar y validar la eficacia de los controles de cliente según su entorno de reglamentación. Estos servicios están actualmente en versión preliminar y están sujetos a los términos y condiciones de los [términos de servicios en línea](https://go.microsoft.com/fwlink/?linkid=2108910). Vea también la [Guía de licencias de Microsoft 365 por seguridad y cumplimiento normativo](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="how-compliance-score-works"></a>Cómo funciona la puntuación de cumplimiento

El panel de calificaciones de cumplimiento muestra una puntuación que mide su progreso en completar acciones de mejora dentro de los controles. Cada acción tiene un impacto diferente en su puntuación, en función de los posibles riesgos. Su puntuación puede ayudar a priorizar la acción que se debe centrar para mejorar su postura de cumplimiento general.

Los valores de puntuación de cumplimiento que se muestran para el control se aplican *en su totalidad* a la puntuación total sobre una base de superación o error. Puede implementar el control y pasar la prueba de evaluación posterior, o no hacerlo. 

Los puntos se agregan a la puntuación de cumplimiento cuando el control tiene:

- El **Estado de implementación** es igual a **implementación alternativa**o **implementada** , y
- El resultado de la **prueba** es **correcto**.

Una puntuación de control es la suma de los puntos obtenidos al realizar acciones de mejora. La suma de las puntuaciones del control es la puntuación de la evaluación. **La suma de los resultados de la evaluación es la puntuación general de cumplimiento.**

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Puntuación inicial basada en la línea base de protección de datos 365 de Microsoft
  
La puntuación de cumplimiento proporciona una puntuación inicial basada en la línea base de protección de datos 365 de Microsoft. Esta línea base es un conjunto de controles que incluye normas y estándares clave para la protección de datos y el gobierno de datos general. Esta base dibuja los elementos principalmente desde NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Normalization), así como de FedRAMP (programa federal de administración de riesgos y autorización) y RGPD (norma general de protección de datos de la Unión Europea).

La evaluación de línea base de protección de datos (que se proporciona de forma predeterminada para todas las organizaciones) se usa para calcular el resultado inicial antes de configurar otras evaluaciones. En su primera visita, la puntuación de cumplimiento ya está recopilando las señales de las soluciones de Microsoft 365. Ver? a simple vista sobre el rendimiento de su organización con respecto a los estándares y regulaciones clave de protección de datos y ver las acciones de mejora sugeridas que deben tomarse.

Debido a que cada organización tiene necesidades específicas, la puntuación de cumplimiento depende de que configure y administre sus propias evaluaciones para ayudar a minimizar y mitigar el riesgo de la forma más completa posible.

## <a name="how-compliance-score-continuously-assesses-controls"></a>Cómo evalúan de forma continuada los controles la puntuación de cumplimiento

La puntuación de cumplimiento examina automáticamente el entorno de Microsoft 365 y detecta la configuración del sistema, actualizando de forma continua y automática el estado de control técnico. La calificación segura es el motor subyacente que realiza la supervisión.

El estado del control se actualiza en el panel de calificaciones de cumplimiento cada 24 horas. Una vez que haya seguido una recomendación para implementar un control, verá que el estado del control se actualizó el día siguiente.

Por ejemplo, si activa la autenticación multifactor (MFA) en el portal de Azure AD, la puntuación de cumplimiento detecta la configuración y refleja que en los detalles de la solución de control de acceso. Por el contrario, si no activó la MFA, los indicadores de puntuación de cumplimiento como una acción recomendada para realizarla.

Durante la versión preliminar pública, la evaluación continua está disponible para una parte de los controles, pero no para todos.

#### <a name="learn-more"></a>Más información
[Obtenga información sobre la puntuación segura y cómo funciona](../security/mtp/microsoft-secure-score-new.md).
  
## <a name="action-types-and-points"></a>Tipos de acción y puntos

La puntuación de cumplimiento hace un seguimiento de dos tipos de acciones: acciones que se administran y acciones que Microsoft administra. Ambos tipos de acciones tienen puntos que cuentan hacia la calificación general cuando se completa:

1. **Los puntos** contribuyen a la puntuación de cumplimiento basada en los controles administrados por la organización.
2. Los **puntos administrados de Microsoft** contribuyen a la puntuación de cumplimiento basada en acciones administradas por Microsoft como un proveedor de servicios en la nube.

A las acciones se les asigna un valor de puntuación en función de si son obligatorios o discrecionales y si son preventivos, detectives o correctivos.

### <a name="mandatory-and-discretionary-actions"></a>Acciones obligatorias y discrecionales

 - **Las acciones obligatorias** no se pueden omitir, ya sea de forma intencionada o accidental. Un ejemplo es una directiva de contraseñas administrada centralmente que establece los requisitos de longitud, complejidad y expiración de la contraseña. Los usuarios deben seguir estos requisitos para obtener acceso al sistema.
  
 - **Las acciones discrecionales** dependen de que los usuarios sepan la Directiva y actúen en consecuencia. Por ejemplo, una directiva que requiere que los usuarios bloqueen su equipo cuando lo dejan es un control discrecional porque depende del usuario.
  
### <a name="preventative-detective-and-corrective-actions"></a>Acciones preventivas, de detectives y correctivas
  
 - **Las acciones preventivas** solucionan riesgos específicos. Por ejemplo, la protección de la información en reposo mediante el cifrado es una acción preventiva contra ataques e infracciones. La separación de tareas es una acción preventiva para administrar conflictos de intereses y proteger contra el fraude.
  
 - **Las acciones de detectives** supervisan activamente los sistemas para identificar situaciones o comportamientos anómalos que representen el riesgo o que se pueden usar para detectar intrusiones o infracciones. Algunos ejemplos son la auditoría de acceso al sistema y las acciones administrativas con privilegios. Las auditorías de cumplimiento normativo son un tipo de acción de detective que se usa para encontrar problemas del proceso.
  
- **Las acciones correctivas** intentan mantener al mínimo los efectos adversos de un incidente de seguridad, emprender acciones correctivas para reducir el efecto inmediato e invertir el daño, si es posible. La respuesta de la incidencia de privacidad es una acción correctiva que limita los daños y restaura los sistemas a un estado operativo después de una infracción.
  
Cada acción tiene un valor asignado en la puntuación de cumplimiento según el riesgo que representa:

|**Tipo**|**Puntuación asignada**|
|:-----|:-----|
| Obligatorio de prevención | ,27 |
| Discrecional preventivo | 9  |
| Detective obligatorio | 3  |
| Discrecionales de detectives | 1  |
| Obligatorio de corrección | 3  |
| Discrecionales correctivas | 1  |
  
![Puntuación de cumplimiento controles valores de punto](../media/compliance-score-controls-scoring.png "Puntuación de cumplimiento controles valores de punto")