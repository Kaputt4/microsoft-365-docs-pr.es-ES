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
ms.localizationpriority: ''
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo proporcionar comentarios a un clasificador que se puede entrenar en el Explorador de contenido.
ms.openlocfilehash: e4cf09599d95d7e19f565a9bd0e30213e3057984
ms.sourcegitcommit: 771f7bbb241f910b3e16b4d1f9bbd9c0c8c6fa34
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "67309469"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Cómo volver a entrenar un clasificador en el explorador de contenido

Un clasificador que se puede entrenar de Microsoft 365 es una herramienta que puede entrenar para reconocer varios tipos de contenido al darle ejemplos a los que examinar. Una vez entrenado, puede usarlo para identificar elementos para la aplicación de etiquetas de confidencialidad de Office, directivas de cumplimiento de comunicaciones y directivas de etiquetas de retención.

En este artículo se muestra cómo mejorar el rendimiento de los clasificadores entrenables personalizados proporcionándoles más comentarios.

Para obtener más información sobre los distintos tipos de clasificadores, consulte [Más información sobre los clasificadores que se pueden entrenar](classifier-learn-about.md).

Vea este vídeo para obtener un resumen rápido del proceso de optimización y reentrenamiento. Seguirá teniendo que leer este artículo completo para obtener los detalles.

</br>

<!-- > [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]-->

> [!NOTE]
> Los clasificadores previamente entrenados no se pueden volver a entrenar.

## <a name="permissions"></a>Permisos

Para acceder a clasificadores en el portal de cumplimiento Microsoft Purview:

- el rol de administrador de cumplimiento o administrador de datos de cumplimiento es necesario para entrenar un clasificador

Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:

- Escenario de directiva de etiqueta de retención: roles de administración de registros y administración de retención 

## <a name="overall-workflow"></a>Flujo de trabajo general

> [!IMPORTANT]
> Proporcione comentarios en el Explorador de contenido para aplicar automáticamente directivas de etiquetas de retención a elementos de Exchange y use el clasificador como condición. **Si no tiene una directiva de retención que aplique automáticamente una etiqueta de retención a los elementos de Exchange y use un clasificador como condición, deténgase aquí.**

Al usar los clasificadores, es posible que desee aumentar la precisión de las clasificaciones que están realizando. Para ello, evalúe la calidad de las clasificaciones realizadas para los elementos que ha identificado como coincidencia o no. Después de realizar 30 evaluaciones para un clasificador, toma esos comentarios y se vuelve a entrenar automáticamente.

Para obtener más información sobre el flujo de trabajo general de volver a entrenar un clasificador, consulte [Flujo de proceso para volver a entrenar un clasificador](classifier-learn-about.md#retraining-classifiers).

> [!NOTE]
> Un clasificador ya debe estar publicado y en uso para poder volver a entrenarse.

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Cómo volver a entrenar un clasificador en el explorador de contenido

1. Inicie sesión en portal de cumplimiento Microsoft Purview con el acceso al rol de administrador de seguridad o administrador de cumplimiento y abra **portal de cumplimiento Microsoft Purview** >  Explorador **de contenido** de **clasificación** >  de datos. 
2. En la lista **Filtrar por etiquetas, tipos de información o categorías** , expanda **Clasificadores entrenables**.

> [!IMPORTANT]
> Los elementos agregados pueden tardar hasta ocho días en aparecer en el encabezado de clasificadores entrenables.

3. Elija el clasificador entrenable que usó en la directiva de etiqueta de retención de aplicación automática. Este es el clasificador que se puede entrenar sobre el que se proporcionarán comentarios.

> [!NOTE]
> Si un elemento tiene una entrada en la columna **Etiqueta de retención**, significa que el elemento se clasificó como .`match`  Si un elemento no tiene una entrada en la columna **Etiqueta de retención** , significa que se clasificó como `close match`. Puede mejorar la precisión del clasificador al máximo si proporciona comentarios sobre `close match` los elementos. 

4. Elija un elemento y ábralo.
 
 > [!TIP]
> Puede proporcionar comentarios sobre varios elementos simultáneamente eligiendo todos ellos y, a continuación, eligiendo **Mejorar clasificación** en la barra de comandos.

5. Elija **Proporcionar comentarios**.
6. En el panel **Comentarios detallados** , si el elemento es un verdadero positivo, elija **Coincidir**.  Si el elemento es un falso positivo, es decir, se incluyó incorrectamente en la categoría, elija **No una coincidencia**.
7. Si hay otro clasificador que sería más adecuado para el elemento, puede elegirlo en la lista **Sugerir otros clasificadores entrenables** . Esto desencadenará el otro clasificador para evaluar el elemento.
8. Elija **Enviar comentarios** para enviar la evaluación de las `match``not a match` clasificaciones y sugerir otros clasificadores que se puedan entrenar. Cuando haya proporcionado 30 instancias de comentarios a un clasificador, se volverá a entrenar automáticamente. El reentrenamiento puede tardar de una a cuatro horas. Los clasificadores solo se pueden volver a entrenar dos veces al día.

> [!IMPORTANT]
> Esta información va al clasificador del inquilino, **no vuelve a Microsoft**.

9. Abra **Clasificadores entrenables**.
10. El clasificador que se usó en la directiva de cumplimiento de comunicaciones aparecerá en el encabezado **Volver a entrenar** .

![clasificador en estado de reentrenamiento.](../media/classifier-retraining.png)

11. Una vez completado el reentrenamiento, elija el clasificador para abrir la introducción al reentrenamiento.

![Introducción a los resultados de reentrenamiento del clasificador.](../media/classifier-retraining-overview.png)

12. Revise la acción recomendada y las comparaciones de predicción de las versiones reentrenadas y publicadas actualmente del clasificador.
13. Si está satisfecho con los resultados del reentrenamiento, elija **Volver a publicar**.
14. Si no está satisfecho con los resultados del reentrenamiento, puede optar por proporcionar más comentarios al clasificador en la interfaz del Explorador de contenido e iniciar otro ciclo de reentrenamiento o no hacer nada en cuyo caso se seguirá usando la versión publicada actualmente del clasificador. 

## <a name="details-on-republishing-recommendations"></a>Detalles sobre la nueva publicación de recomendaciones

Esta es una pequeña información sobre cómo formulamos la recomendación de volver a publicar un clasificador reentrenado o sugerir un nuevo entrenamiento. Esto requiere una comprensión un poco más profunda de cómo funcionan los clasificadores entrenables.

Después de volver a entrenar, se evalúa el rendimiento del clasificador tanto en los elementos con comentarios como en los elementos que se usaron originalmente para entrenar el clasificador. 

- En el caso de los modelos integrados, los elementos que se usan para entrenar el clasificador son los elementos usados por Microsoft para compilar el modelo.
- En el caso de los modelos personalizados, los elementos usados en el entrenamiento original del clasificador proceden de los sitios que ha agregado para la prueba y la revisión.

Comparamos los números de rendimiento de ambos conjuntos de elementos para el clasificador reentrenado y publicado para proporcionar una recomendación sobre si se ha mejorado la publicación. 

## <a name="see-also"></a>Vea también

- [Obtenga información sobre los clasificadores entrenables](classifier-learn-about.md)
- [Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
