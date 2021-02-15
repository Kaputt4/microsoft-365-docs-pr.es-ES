---
title: Cómo volver a entrenar un clasificador en el cumplimiento de las comunicaciones
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo proporcionar comentarios a un clasificador que se puede entrenar en el cumplimiento de las comunicaciones.
ms.openlocfilehash: cdb8787715c3e022dfa0aa17cd83cc405aeef955
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752654"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a>Cómo volver a entrenar un clasificador en el cumplimiento de las comunicaciones

Un clasificador que se puede entrenar de Microsoft 365 es una herramienta que puede entrenar para reconocer distintos tipos de contenido, ya que le proporciona ejemplos para que los vea. Una vez formado, puede usarlo para identificar el elemento para la aplicación de etiquetas de confidencialidad de Office, directivas de cumplimiento de comunicaciones y directivas de etiquetas de retención.

En este artículo se muestra cómo mejorar el rendimiento de los clasificadores que se pueden entrenar personalizados y algunos clasificadores previamente formados proporcionando comentarios adicionales.

Para obtener más información acerca de los distintos tipos de clasificadores, vea [Learn about trainable classifiers](classifier-learn-about.md).

## <a name="permissions"></a>Permissions

Para acceder a clasificadores en el Centro de cumplimiento de Microsoft 365:

- El rol de administrador de cumplimiento o el administrador de datos de cumplimiento es necesario para entrenar a un clasificador

Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:

- Escenario de directiva de cumplimiento de comunicaciones: administrador de administración de riesgos de Insider, administrador de revisión de supervisión 

## <a name="overall-workflow"></a>Flujo de trabajo general

> [!IMPORTANT]
> Proporciona comentarios en la solución de cumplimiento que usa el clasificador como condición. **Si no tiene una directiva de cumplimiento de comunicaciones que use un clasificador como condición, detén esto.**

A medida que use los clasificadores, es posible que desee aumentar la precisión de las clasificaciones que están realizando. Para ello, evalúe la calidad de las clasificaciones realizadas para los elementos que ha identificado como coincidencia o no. Después de realizar 30 evaluaciones para un clasificador, toma ese comentario y se vuelve a entrenar automáticamente.

Para obtener más información sobre el flujo de trabajo general de volver a entrenar un clasificador, vea Flujo de proceso para volver a entrenar [un clasificador.](classifier-learn-about.md#retraining-classifiers)

> [!NOTE]
> Un clasificador ya debe estar publicado y en uso para poder volver a entrenarse.

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a>Cómo volver a entrenar un clasificador en las directivas de cumplimiento de comunicaciones

1. Abra la directiva de cumplimiento de comunicaciones que usa un clasificador como condición y elija uno de los elementos identificados en la **lista Pendiente.**
2. Elija los puntos suspensivos y **mejore la clasificación.**
3. En el **panel comentarios detallados,** si el elemento es un verdadero positivo, elija **Coincidir**.  Si el elemento es un falso positivo, es decir, se incluyó incorrectamente en la categoría, elija **No coincidir.**
4. Si hay otro clasificador que sería más apropiado para el elemento, puedes elegirlo en la lista Sugerir otros clasificadores que se pueden **entrenar.** Esto desencadenará que el otro clasificador evalúe el elemento.

> [!TIP]
> Puedes proporcionar comentarios sobre varios elementos simultáneamente eligiendo todos ellos y, a continuación, eligiendo **Proporcionar** comentarios detallados en la barra de comandos.

5. Elige **Enviar comentarios** para enviar tu evaluación de las `match` clasificaciones y sugerir otros `not a match` clasificadores que se puedan entrenar. Cuando hayas proporcionado 30 instancias de comentarios a un clasificador, se volverá a entrenar automáticamente. La readaptación puede tardar de 1 a 4 horas. Los clasificadores solo se pueden volver a entrenar dos veces al día.

> [!IMPORTANT]
> Esta información va al clasificador de su espacio empresarial, **no vuelve a Microsoft.**

6.  Abra la **página Clasificación de** datos en el Centro de cumplimiento de Microsoft **365.**
7. Abra **clasificadores que se pueden entrenar.**
8. El clasificador que se usó en la directiva de cumplimiento de comunicaciones aparecerá bajo el **encabezado De nuevo** aprendizaje.

![clasificador en el estado de reentrenamiento](../media/classifier-retraining.png)

9. Una vez completada la nueva formación, elija el clasificador para abrir la información general sobre el reentrenamiento.

![Introducción a los resultados de la nueva formación de clasificadores](../media/classifier-retraining-overview.png)

10. Revise la acción recomendada y las comparaciones de predicción de las versiones actualizadas y publicadas actualmente del clasificador.
11. Si está satisfecho con los resultados de la readaptación, elija **Volver a publicar.**
12. Si no está satisfecho con los resultados de la nueva formación, puede proporcionar comentarios adicionales al clasificador en la interfaz de cumplimiento de comunicaciones e iniciar otro ciclo de reentrenamiento o no hacer nada en cuyo caso se seguirá usando la versión publicada actualmente del clasificador. 

## <a name="details-on-republishing-recommendations"></a>Detalles sobre las recomendaciones para volver a publicar

Aquí tiene un poco de información sobre cómo formulamos la recomendación de volver a publicar un clasificador reentrenado o sugerir una nueva formación. Esto requiere un conocimiento más profundo de cómo funcionan los clasificadores que se pueden entrenar.

Después de una nueva formación, se evalúa el rendimiento del clasificador tanto en los elementos con comentarios como en los elementos usados originalmente para entrenar al clasificador. 

- Para los modelos integrados, los elementos usados para entrenar al clasificador son los elementos usados por Microsoft para crear el modelo.
- Para los modelos personalizados, los elementos usados en el entrenamiento original el clasificador son de los sitios que ha agregado para su prueba y revisión.

Comparamos los números de rendimiento en ambos conjuntos de elementos para el clasificador reedidores y publicados para proporcionar una recomendación sobre si hubo alguna mejora para volver a publicar. 

## <a name="see-also"></a>Vea también

- [Obtenga información sobre los clasificadores entrenables](classifier-learn-about.md)
- [Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
