---
title: Cómo volver a entrenar un clasificador en el explorador de contenido
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
description: Obtenga información sobre cómo proporcionar comentarios a un clasificador que se puede entrenar en el Explorador de contenido.
ms.openlocfilehash: ef0539a3d474ffecaeac8633b4a58aa068a5c182
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793069"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Cómo volver a entrenar un clasificador en el explorador de contenido

Un Microsoft 365 clasificador que se puede entrenar es una herramienta que puede entrenar para reconocer varios tipos de contenido, ya que le proporciona ejemplos para que los vea. Una vez formado, puede usarlo para identificar el elemento para la aplicación de etiquetas de Office de confidencialidad, directivas de cumplimiento de comunicaciones y directivas de etiquetas de retención.

En este artículo se muestra cómo mejorar el rendimiento de los clasificadores personalizados y algunos clasificadores previamente formados proporcionando comentarios adicionales.

Para obtener más información sobre los diferentes tipos de clasificadores, vea [Learn about trainable classifiers](classifier-learn-about.md).

Vea este vídeo para obtener un resumen rápido del proceso de ajuste y reciclaje. Todavía tendrá que leer este artículo completo para obtener los detalles.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a>Permisos

Para obtener acceso a clasificadores en el centro de Microsoft 365 cumplimiento:

- el rol de administrador de cumplimiento o el administrador de datos de cumplimiento es necesario para entrenar a un clasificador

Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:

- Escenario de directiva de etiqueta de retención: roles de administración de registros y administración de retención 

## <a name="overall-workflow"></a>Flujo de trabajo general

> [!IMPORTANT]
> Proporciona comentarios en el explorador de contenido para aplicar automáticamente directivas de etiquetas de retención a Exchange elementos y usa el clasificador como condición. **Si no tiene una directiva de retención que aplique automáticamente una etiqueta de retención a los elementos Exchange y use un clasificador como condición, detén aquí.**

Al usar los clasificadores, es posible que desee aumentar la precisión de las clasificaciones que están realizando. Para ello, evalúe la calidad de las clasificaciones realizadas para los elementos que ha identificado como una coincidencia o no una coincidencia. Después de realizar 30 evaluaciones para un clasificador, toma los comentarios y se vuelve a entrenar automáticamente.

Para obtener más información sobre el flujo de trabajo general de reentrenamiento de un clasificador, vea Flujo de proceso para volver a entrenar [un clasificador](classifier-learn-about.md#retraining-classifiers).

> [!NOTE]
> Un clasificador ya debe publicarse y usarse para poder volver a entrenarlo.

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Cómo volver a entrenar un clasificador en el explorador de contenido

1. Inicie sesión en el Microsoft 365 de cumplimiento con el acceso a roles de administrador de seguridad o administración de cumplimiento y **abra** Microsoft 365 explorador de contenido de clasificación  >  **de** datos del  >  **centro de cumplimiento.** 
2. En la **lista Filtrar por etiquetas, tipos** de información o categorías, expanda **Clasificadores que se pueden entrenar.**

> [!IMPORTANT]
> Los elementos agregados pueden tardar hasta ocho días en aparecer bajo el encabezado clasificadores que se pueden entrenar.

3. Elija el clasificador que usó para aplicar automáticamente la directiva de etiqueta de retención. Este es el clasificador que se puede entrenar en el que darás comentarios.

> [!NOTE]
> Si un elemento tiene una entrada en la columna **Etiqueta** de retención, significa que el elemento se clasificó como `match` .  Si un elemento no tiene una entrada en la columna **Etiqueta** de retención, significa que se clasificó como `close match` . Puedes mejorar la precisión del clasificador más proporcionando comentarios sobre `close match` los elementos. 

4. Elija un elemento y ábralo.
 
 > [!TIP]
> Puede proporcionar comentarios sobre varios elementos al mismo tiempo eligiendo todos ellos y, a continuación, eligiendo Mejorar la **clasificación** en la barra de comandos.

5. Elija **Proporcionar comentarios**.
6. En el **panel Comentarios detallados,** si el elemento es un verdadero positivo, elija **Match**.  Si el elemento es un falso positivo, es decir, se incluyó incorrectamente en la categoría, elija **No coincidir.**
7. Si hay otro clasificador que sería más adecuado para el elemento, puede elegirlo en la lista Sugerir otros **clasificadores entrenables.** Esto desencadenará el otro clasificador para evaluar el elemento.
8. Elija **Enviar comentarios** para enviar la evaluación de las `match` clasificaciones , y sugerir otros `not a match` clasificadores entrenables. Cuando haya proporcionado 30 instancias de comentarios a un clasificador, se volverá a entrenar automáticamente. El reentrenamiento puede tardar de una a cuatro horas. Los clasificadores solo se pueden volver a entrenar dos veces al día.

> [!IMPORTANT]
> Esta información va al clasificador en el espacio empresarial, **no vuelve a Microsoft**.

9. Abra **clasificadores trainables**.
10. El clasificador que se usó en la directiva de cumplimiento de comunicaciones aparecerá en el **encabezado Volver a entrenar.**

![clasificador en estado de reentrenamiento](../media/classifier-retraining.png)

11. Una vez completado el reentrenamiento, elija el clasificador para abrir la introducción al reentrenamiento.

![Introducción a los resultados de reentrenamiento de clasificadores](../media/classifier-retraining-overview.png)

12. Revise la acción recomendada y las comparaciones de predicción de las versiones reentrenadas y publicadas actualmente del clasificador.
13. Si está satisfecho con los resultados de la readaptación, elija **Volver a publicar**.
14. Si no está satisfecho con los resultados de la readaptación, puede elegir proporcionar comentarios adicionales al clasificador en la interfaz del Explorador de contenido e iniciar otro ciclo de reentrenamiento o no hacer nada en cuyo caso se seguirá usando la versión publicada actualmente del clasificador. 

## <a name="details-on-republishing-recommendations"></a>Detalles sobre recomendaciones de reedición

Esta es una pequeña información sobre cómo formulamos la recomendación de volver a publicar un clasificador reentrenado o sugerir más reciclaje. Esto requiere una comprensión un poco más profunda de cómo funcionan los clasificadores entrenables.

Después de un reentrenamiento, se evalúa el rendimiento del clasificador tanto en los elementos con comentarios como en los elementos usados originalmente para entrenar al clasificador. 

- Para los modelos integrados, los elementos usados para entrenar al clasificador son los elementos usados por Microsoft para crear el modelo.
- Para los modelos personalizados, los elementos usados en el aprendizaje original el clasificador son de los sitios que ha agregado para la prueba y revisión.

Comparamos los números de rendimiento en ambos conjuntos de elementos para el clasificador reentrenado y publicado para proporcionar una recomendación sobre si hubo mejoras para volver a publicar. 

## <a name="see-also"></a>Consulte también

- [Obtenga información sobre los clasificadores entrenables](classifier-learn-about.md)
- [Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)