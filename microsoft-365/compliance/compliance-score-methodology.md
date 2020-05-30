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
description: Comprenda cómo la puntuación de cumplimiento de Microsoft calcula una puntuación personalizada en función de las acciones realizadas para enfrentarse a los riesgos y mejorar la postura de cumplimiento.
ms.openlocfilehash: e1a13cee8086e158f3869a00384166366c0a63dc
ms.sourcegitcommit: 436841236dc41390a3be9f8936d19d3d017fa35c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2020
ms.locfileid: "44429195"
---
# <a name="microsoft-compliance-score-preview-calculation"></a>Cálculo de la puntuación de cumplimiento de Microsoft (vista previa)

> [!IMPORTANT]
> Las recomendaciones de la puntuación de cumplimiento y del Administrador de cumplimiento no deben interpretarse como una garantía de cumplimiento. Depende de usted evaluar y validar la eficacia de los controles de cliente según su entorno de reglamentación. Estos servicios están actualmente en versión preliminar y están sujetos a los términos y condiciones de los [términos de servicios en línea](https://go.microsoft.com/fwlink/?linkid=2108910). Vea también la [Guía de licencias de Microsoft 365 por seguridad y cumplimiento normativo](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="overview"></a>Visión general

El panel de calificaciones de cumplimiento muestra una puntuación que mide su progreso en completar acciones de mejora dentro de los controles. Los puntos se acumulan cuando se realizan acciones.

La puntuación se calcula en función de la finalización de acciones administradas por Microsoft y acciones administradas por el cliente. Cada acción tiene un impacto diferente en su puntuación, en función de los posibles riesgos. Su puntuación puede ayudar a priorizar la acción que se debe centrar para mejorar su postura de cumplimiento general.

Los valores de puntuación de cumplimiento que se muestran para el control se aplican *en su totalidad* a la puntuación total sobre una base de superación o error. O bien el control se implementa y pasa la prueba de evaluación posterior, o no es así. Los puntos asignados se agregan a la puntuación de cumplimiento cuando el control tiene:

- El **Estado de implementación** es igual a **implementación alternativa** o **implementada** y,
- El resultado de la **prueba** es **correcto**.

La suma de los puntos obtenidos al tomar acciones de mejora es la puntuación del control. La suma de las puntuaciones del control es la puntuación de la evaluación. La suma de los resultados de la evaluación es la puntuación general de cumplimiento.

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Puntuación inicial basada en la línea base de protección de datos 365 de Microsoft
  
La puntuación de cumplimiento proporciona una puntuación inicial basada en la línea base de protección de datos 365 de Microsoft, que es un conjunto de controles que incluye normas y estándares clave para la protección de datos y el gobierno de datos general. Esta base dibuja los elementos principalmente desde NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Normalization), así como de FedRAMP (programa federal de administración de riesgos y autorización) y RGPD (norma general de protección de datos de la Unión Europea).

## <a name="how-compliance-score-continuously-assesses-controls"></a>Cómo evalúan de forma continuada los controles la puntuación de cumplimiento

La puntuación de cumplimiento examina automáticamente el entorno de Microsoft 365 y detecta la configuración del sistema, actualizando de forma continua y automática el estado de control técnico. La calificación segura es el motor subyacente que realiza la supervisión. [Obtenga más información sobre la puntuación segura y cómo funciona](../security/mtp/microsoft-secure-score.md).

El estado del control se actualiza en el panel de calificaciones de cumplimiento cada 24 horas. Una vez que haya seguido una recomendación para implementar un control, verá que el estado del control se actualizó el día siguiente.

Por ejemplo, si activa la autenticación multifactor (MFA) en el portal de Azure AD, la puntuación de cumplimiento detecta la configuración y refleja que en los detalles de la solución de control de acceso. Por el contrario, si no activó la MFA, los indicadores de puntuación de cumplimiento como una acción recomendada para realizarla.

Durante la versión preliminar pública, la evaluación continua está disponible para una parte de los controles, pero no para todos.
  
## <a name="control-types-and-points"></a>Tipos y puntos de control

La puntuación de cumplimiento hace un seguimiento de dos tipos de controles: administrados por Microsoft y administrados por el cliente, cada uno con puntos que contribuyen a la puntuación general:

1. Los **puntos administrados** por el cliente contribuyen con la puntuación de cumplimiento basada en los controles administrados por la organización.
2. Los **puntos administrados por Microsoft** contribuyen a la puntuación de cumplimiento basada en los controles administrados por Microsoft como un proveedor de servicios en la nube.

A los controles se les asigna un valor de puntuación en función de si son obligatorios o discrecionales, y si son preventivos, detectives o correctivos.

### <a name="mandatory-and-discretionary-controls"></a>Controles obligatorios y discrecionales

 - **Los controles obligatorios** son acciones que no se pueden omitir, ya sea de forma intencionada o accidental. Un ejemplo es una directiva de contraseñas administrada centralmente que establece los requisitos de longitud, complejidad y expiración de la contraseña. Los usuarios deben seguir estos requisitos para obtener acceso al sistema.
  
 - Los **controles discrecionales** dependen de los usuarios para comprender la Directiva y actuar en consecuencia. Por ejemplo, una directiva que requiere que los usuarios bloqueen su equipo cuando lo dejan es un control discrecional porque depende del usuario.
  
### <a name="preventative-detective-and-corrective-controls"></a>Controles preventivos, detectives y correctivos
  
 - **Los controles preventivos** solucionan riesgos específicos. Por ejemplo, la protección de la información en reposo mediante el cifrado es un control preventivo contra ataques e infracciones. La separación de tareas es un control preventivo para administrar conflictos de intereses y protegerse contra el fraude.
  
 - **Los controles de detectives** supervisan activamente los sistemas para identificar las condiciones o comportamientos anómalos que representan el riesgo o que se pueden usar para detectar intrusiones o infracciones. Auditoría de acceso al sistema auditoría de acciones administrativas con privilegios son tipos de controles de supervisión de detectives. Las auditorías de cumplimiento normativo son un tipo de control de detectives que se usa para encontrar problemas del proceso.
  
- **Los controles correctivos** intentan mantener al mínimo los efectos adversos de un incidente de seguridad, emprender acciones correctivas para reducir el efecto inmediato e invertir el daño, si es posible. La respuesta de la incidencia de privacidad es un control correctivo para limitar los daños y restaurar los sistemas a un estado operativo después de una infracción.
  
Cada control tiene un valor asignado en la puntuación de cumplimiento según el riesgo que representa:

|**Tipo**|**Puntuación asignada**|
|:-----|:-----|
| Obligatorio de prevención | ,27 |
| Discrecional preventivo | 9  |
| Detective obligatorio | 3 |
| Discrecionales de detectives | 1  |
| Obligatorio de corrección | 3 |
| Discrecionales correctivas | 1  |
  
![Puntuación de cumplimiento controles valores de punto](../media/compliance-score-controls-scoring.png "Puntuación de cumplimiento controles valores de punto")