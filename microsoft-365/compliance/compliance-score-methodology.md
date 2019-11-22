---
title: Cálculo de puntuación de cumplimiento
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
ms.openlocfilehash: a94b1051af383041a89fa136ae490875ea48782d
ms.sourcegitcommit: 3eae8fe39cea912d29e211a1c9fd035d6b606f91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793664"
---
# <a name="microsoft-compliance-score-preview-calculation"></a>Cálculo de la puntuación de cumplimiento de Microsoft (vista previa)

> [!IMPORTANT]
> La puntuación de cumplimiento no expresa una medida absoluta de cumplimiento organizacional con cualquier norma o reglamentación en particular. Expresa hasta qué punto ha adoptado los controles que pueden reducir los riesgos para los datos personales y la privacidad individual. Las recomendaciones de la puntuación de cumplimiento y el administrador de cumplimiento no deben interpretarse como una garantía de cumplimiento. Este servicio se encuentra actualmente en versión preliminar y está sujeto a los términos y condiciones de los [términos de servicios en línea](https://go.microsoft.com/fwlink/?linkid=2108910).

## <a name="overview"></a>Información general

El panel de calificaciones de cumplimiento muestra una puntuación que mide su progreso en completar acciones de mejora dentro de los controles. Los puntos se acumulan cuando se realizan acciones.

La puntuación se calcula en función de la finalización de acciones administradas por Microsoft y acciones administradas por el cliente. Cada acción tiene un impacto diferente en su puntuación, en función de los posibles riesgos, por lo que la puntuación puede ayudar a establecer prioridades respecto a la acción que se debe centrar para mejorar su postura de cumplimiento general.

Los valores de puntuación de cumplimiento que se muestran para el control se aplican *en su totalidad* a la puntuación total sobre una base de superación o error. Puede implementar el control y pasar la prueba de evaluación posterior o no. Los puntos asignados se agregan a la puntuación de cumplimiento cuando el control tiene:

- El **Estado de implementación** es igual a **implementación alternativa** o **implementada** y,
- El resultado de la **prueba** es **correcto**.

La suma de los puntos obtenidos al tomar acciones de mejora es la puntuación del control. La suma de las puntuaciones del control es la puntuación de la evaluación. La suma de los resultados de la evaluación es la puntuación general de cumplimiento

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Puntuación inicial basada en la línea base de protección de datos 365 de Microsoft
  
La puntuación de cumplimiento le proporciona una calificación de preinstalación basada en la línea base de protección de datos de Microsoft 365, que es un conjunto de controles que incluye normas y estándares clave para la protección de datos y el gobierno de datos general. Esta línea base dibuja los elementos principalmente desde NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Normalization), así como de FedRAMP (federal Risk and Authorization Management Programa) y RGPD (regla general de protección de datos de la Unión Europea).

## <a name="how-compliance-score-continuously-assesses-controls"></a>Cómo evalúan de forma continuada los controles la puntuación de cumplimiento

La puntuación de cumplimiento examina automáticamente el entorno de Microsoft 365 y detecta la configuración del sistema, actualizando de forma continua y automática el estado de control técnico. Por ejemplo, si ha activado la autenticación multifactor (MFA) en el portal de Azure AD, la puntuación de cumplimiento detecta la configuración y refleja que en los detalles de la solución de control de acceso. Por el contrario, si no activó la MFA, los indicadores de puntuación de cumplimiento como una acción recomendada para realizarla.

Puntuación de cumplimiento actualiza el estado del control cada 24 horas. Una vez que haya seguido una recomendación para implementar un control, verá que el estado del control se actualizó el día siguiente.

Durante la vista previa pública, la evaluación continua está disponible para los controles de parte, pero no para todos.
  
## <a name="control-types-and-points"></a>Tipos y puntos de control

La puntuación de cumplimiento hace un seguimiento de dos tipos de controles: administrados por Microsoft y administrados por el cliente, cada uno con puntos que contribuyen a la puntuación general:

1. Los **puntos administrados** por el cliente contribuyen con la puntuación de cumplimiento basada en los controles administrados por la organización.
2. Los **puntos administrados por Microsoft** contribuyen a la puntuación de cumplimiento basada en los controles administrados por Microsoft como un proveedor de servicios en la nube.

A los controles se les asigna un valor de puntuación en función de si son obligatorios o discrecionales, y si son preventivos, detectives o correctivos, tal como se describe a continuación.

### <a name="mandatory-and-discretionary-controls"></a>Controles obligatorios y discrecionales

 - **Los controles obligatorios** son acciones que no se pueden omitir intencionada o accidentalmente. Un ejemplo es una directiva de contraseñas administrada centralmente que establece los requisitos de longitud, complejidad y expiración de la contraseña. Los usuarios deben cumplir con estos requisitos para tener acceso al sistema.
  
 - Los **controles discrecionales** dependen de los usuarios para comprender la Directiva y actuar en consecuencia. Por ejemplo, una directiva que requiere que los usuarios bloqueen su equipo cuando lo dejan es un control discrecional porque depende del usuario.
  
### <a name="preventative-detective-and-corrective-controls"></a>Controles preventivos, detectives y correctivos
  
 - **Los controles preventivos** solucionan riesgos específicos. Por ejemplo, la protección de la información en reposo mediante el cifrado es un control preventivo contra ataques e infracciones. La separación de tareas es un control preventivo para administrar conflictos de intereses y protegerse contra el fraude.
  
 - **Los controles de detectives** supervisan activamente los sistemas para identificar las condiciones o comportamientos anómalos que representan el riesgo o que se pueden usar para detectar intrusiones o determinar si se produce una infracción. Auditoría de acceso al sistema auditoría de acciones administrativas con privilegios son tipos de controles de supervisión de detectives. Las auditorías de cumplimiento normativo son un tipo de control de detectives que se usa para encontrar problemas del proceso.
  
- **Los controles correctivos** intentan mantener al mínimo los efectos adversos de un incidente de seguridad, emprender acciones correctivas para reducir el efecto inmediato e invertir el daño, si es posible. La respuesta de la incidencia de privacidad es un control correctivo para limitar los daños y restaurar los sistemas a un estado operativo después de una infracción.
  
Cada control tiene un valor asignado en la puntuación de cumplimiento según el riesgo que representa:

|**Tipo**|**Puntuación asignada**|
|:-----|:-----|
| Obligatorio de prevención | ,27 |
| Discrecional preventivo | 9  |
| Detective obligatorio | 3  |
| Discrecionales de detectives | 1  |
| Obligatorio de corrección | 3  |
| Discrecionales correctivas | 1  |
  