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
description: Obtenga información sobre cómo proporcionar comentarios a un clasificador capacitado en cumplimiento de comunicaciones.
ms.openlocfilehash: 75fff8220b052618c70a6490b8c3569c11ecc861
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918151"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a>Cómo volver a entrenar un clasificador en el cumplimiento de las comunicaciones

Un clasificador entrenable de Microsoft 365 es una herramienta que puede entrenar para reconocer varios tipos de contenido, ya que le proporciona ejemplos para que los vea. Una vez formado, puede usarlo para identificar el elemento para la aplicación de etiquetas de confidencialidad de Office, directivas de cumplimiento de comunicaciones y directivas de etiquetas de retención.

En este artículo se muestra cómo mejorar el rendimiento de los clasificadores personalizados y algunos clasificadores previamente formados proporcionando comentarios adicionales.

Para obtener más información sobre los diferentes tipos de clasificadores, vea [Learn about trainable classifiers](classifier-learn-about.md).

## <a name="permissions"></a>Permisos

Para obtener acceso a clasificadores en el Centro de cumplimiento de Microsoft 365:

- el rol de administrador de cumplimiento o el administrador de datos de cumplimiento es necesario para entrenar a un clasificador

Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:

- Escenario de directiva de cumplimiento de comunicaciones: Administrador de administración de riesgos de Insider, Administrador de revisión de supervisión 

## <a name="overall-workflow"></a>Flujo de trabajo general

> [!IMPORTANT]
> Proporciona comentarios en la solución de cumplimiento que usa el clasificador como condición. **Si no tiene una directiva de cumplimiento de comunicaciones que use un clasificador como condición, detén aquí.**

Al usar los clasificadores, es posible que desee aumentar la precisión de las clasificaciones que están realizando. Para ello, evalúe la calidad de las clasificaciones realizadas para los elementos que ha identificado como una coincidencia o no una coincidencia. Después de realizar 30 evaluaciones para un clasificador, toma los comentarios y se vuelve a entrenar automáticamente.

Para obtener más información sobre el flujo de trabajo general de reentrenamiento de un clasificador, vea Flujo de proceso para volver a entrenar [un clasificador](classifier-learn-about.md#retraining-classifiers).

> [!NOTE]
> Un clasificador ya debe publicarse y usarse para poder volver a entrenarlo.

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a>Cómo volver a entrenar a un clasificador en directivas de cumplimiento de comunicaciones

1. Abra la directiva de cumplimiento de comunicaciones que usa un clasificador como condición y elija uno de los elementos identificados de la **lista Pendiente.**
2. Elija los puntos suspensivos y **Mejore la clasificación**.
3. En el **panel Comentarios detallados,** si el elemento es un verdadero positivo, elija **Match**.  Si el elemento es un falso positivo, es decir, se incluyó incorrectamente en la categoría, elija **No coincidir.**
4. Si hay otro clasificador que sería más adecuado para el elemento, puede elegirlo en la lista Sugerir otros **clasificadores entrenables.** Esto desencadenará el otro clasificador para evaluar el elemento.

> [!TIP]
> Puede proporcionar comentarios sobre varios elementos al mismo tiempo eligiendo todos ellos y, a continuación, eligiendo Proporcionar comentarios **detallados** en la barra de comandos.

5. Elija **Enviar comentarios** para enviar la evaluación de las `match` clasificaciones , y sugerir otros `not a match` clasificadores entrenables. Cuando haya proporcionado 30 instancias de comentarios a un clasificador, se volverá a entrenar automáticamente. El reciclaje puede tardar de 1 a 4 horas. Los clasificadores solo se pueden volver a entrenar dos veces al día.

> [!IMPORTANT]
> Esta información va al clasificador en el espacio empresarial, **no vuelve a Microsoft**.

6.  Abra la **página Clasificación de** datos en el Centro de cumplimiento de Microsoft **365**.
7. Abra **clasificadores trainables**.
8. El clasificador que se usó en la directiva de cumplimiento de comunicaciones aparecerá en el **encabezado Volver a entrenar.**

![clasificador en estado de reentrenamiento](../media/classifier-retraining.png)

9. Una vez completado el reentrenamiento, elija el clasificador para abrir la introducción al reentrenamiento.

![Introducción a los resultados de reentrenamiento de clasificadores](../media/classifier-retraining-overview.png)

10. Revise la acción recomendada y las comparaciones de predicción de las versiones reentrenadas y publicadas actualmente del clasificador.
11. Si está satisfecho con los resultados de la readaptación, elija **Volver a publicar**.
12. Si no está satisfecho con los resultados del reentrenamiento, puede elegir proporcionar comentarios adicionales al clasificador en la interfaz de cumplimiento de comunicaciones e iniciar otro ciclo de reciclaje o no hacer nada en cuyo caso se seguirá usando la versión publicada actualmente del clasificador. 

## <a name="details-on-republishing-recommendations"></a>Detalles sobre recomendaciones de reedición

Esta es una pequeña información sobre cómo formulamos la recomendación de volver a publicar un clasificador reentrenado o sugerir más reciclaje. Esto requiere una comprensión un poco más profunda de cómo funcionan los clasificadores entrenables.

Después de un reentrenamiento, se evalúa el rendimiento del clasificador tanto en los elementos con comentarios como en los elementos usados originalmente para entrenar al clasificador. 

- Para los modelos integrados, los elementos usados para entrenar al clasificador son los elementos usados por Microsoft para crear el modelo.
- Para los modelos personalizados, los elementos usados en el aprendizaje original el clasificador son de los sitios que ha agregado para la prueba y revisión.

Comparamos los números de rendimiento en ambos conjuntos de elementos para el clasificador reentrenado y publicado para proporcionar una recomendación sobre si hubo mejoras para volver a publicar. 

## <a name="see-also"></a>Vea también

- [Obtenga información sobre los clasificadores entrenables](classifier-learn-about.md)
- [Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)