---
title: Cómo recapacitar un clasificador en el cumplimiento de comunicaciones
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
description: Obtenga información sobre cómo proporcionar comentarios a un clasificador capacitado en el cumplimiento de comunicaciones.
ms.openlocfilehash: cdb8787715c3e022dfa0aa17cd83cc405aeef955
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752654"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a>Cómo recapacitar un clasificador en el cumplimiento de comunicaciones

Un clasificador entrenado de 365 de Microsoft es una herramienta que puede entrenar para que reconozca varios tipos de contenido proporcionándoles ejemplos para mirar. Una vez preparado, puede usarlo para identificar el elemento para la aplicación de las etiquetas de confidencialidad de Office, las directivas de cumplimiento de comunicaciones y las directivas de etiquetas de retención.

En este artículo se muestra cómo mejorar el rendimiento de los clasificadores que se puede entrenar de forma personalizada y algunos clasificadores previamente entrenados proporcionándoles comentarios adicionales.

Para obtener más información acerca de los diferentes tipos de clasificadores, consulte [información sobre los clasificadores](classifier-learn-about.md)que se puedan entrenar.

## <a name="permissions"></a>Permissions

Para acceder a los clasificadores en el centro de cumplimiento de Microsoft 365:

- el rol de administrador de cumplimiento o el administrador de datos de cumplimiento es necesario para entrenar a un clasificador

Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:

- Escenario de directiva de cumplimiento de comunicaciones: administrador de administración de riesgos de Insider, administrador de revisión de supervisión 

## <a name="overall-workflow"></a>Flujo de trabajo general

> [!IMPORTANT]
> Los comentarios se proporcionan en la solución de cumplimiento que usa el clasificador como condición. **Si no tiene una directiva de cumplimiento de comunicaciones que use un clasificador como condición, deténgalo aquí.**

Cuando use los clasificadores, es posible que quiera aumentar la precisión de las clasificaciones que están realizando. Para ello, evalúe la calidad de las clasificaciones realizadas para los elementos que ha identificado como que coinciden o no coinciden. Después de realizar 30 evaluaciones para un clasificador, se toman esos comentarios y se reforman automáticamente.

Para obtener más información sobre el flujo de trabajo general de volver a entrenar un clasificador, consulte [Process Flow for Retraining a Classifier](classifier-learn-about.md#retraining-classifiers).

> [!NOTE]
> Un clasificador ya debe estar publicado y en uso antes de que se pueda volver a entrenar.

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a>Cómo recapacitar un clasificador en directivas de cumplimiento de comunicaciones

1. Abra la Directiva de cumplimiento de comunicaciones que usa un clasificador como condición y elija uno de los elementos identificados de la lista **pendiente** .
2. Elija los puntos suspensivos y **mejore la clasificación**.
3. En el panel de **comentarios detallado** , si el elemento es un verdadero positivo, elija, **hacer coincidir**.  Si el elemento es un falso positivo, es que se incluyó incorrectamente en la categoría, elija **no una coincidencia**.
4. Si hay otro clasificador que sería más apropiado para el elemento, puede elegirlo de la lista **sugerir otros clasificadores** con más formación. Esto hará que se desencadene el otro clasificador para evaluar el elemento.

> [!TIP]
> Puede enviar comentarios sobre varios elementos simultáneamente si los elige todos y, a continuación, elige **proporcionar comentarios detallados** en la barra de comandos.

5. Elija **Enviar comentarios** para enviar la evaluación del `match` , `not a match` clasificaciones y sugerir otros clasificadores capacitados. Una vez que haya especificado 30 instancias de comentarios en un clasificador, se volverá a entrenar automáticamente. La formación puede tardar entre 1-4 horas. Los clasificadores solo se pueden volver a entrenar dos veces al día.

> [!IMPORTANT]
> Esta información va al clasificador en el espacio empresarial, no **se vuelve a Microsoft**.

6.  Abra la página **clasificación de datos** en el centro de cumplimiento de **Microsoft 365**.
7. Abra **clasificadores** que se van a entrenar.
8. El clasificador que se usó en la Directiva de cumplimiento de comunicaciones aparecerá en el encabezado **de reentrenamiento** .

![clasificador en estado de reaprendizaje](../media/classifier-retraining.png)

9. Una vez completada la formación, elija el clasificador para abrir la información general sobre el reentrenamiento.

![Introducción a los resultados de la formación de clasificadores](../media/classifier-retraining-overview.png)

10. Revise la acción recomendada y las comparaciones de predicción de las versiones recapacitadas y publicadas actualmente del clasificador.
11. Si está de acuerdo con los resultados de la nueva formación, elija **volver a publicar**.
12. Si no está satisfecho con los resultados de la nueva formación, puede elegir proporcionar comentarios adicionales al clasificador en la interfaz de cumplimiento de la comunicación e iniciar otro ciclo de entrenamiento o no hacer nada en cuyo caso la versión publicada actualmente del clasificador seguirá utilizándose. 

## <a name="details-on-republishing-recommendations"></a>Detalles sobre las recomendaciones para volver a publicar

A continuación, se muestra una pequeña información sobre cómo formular la recomendación para volver a publicar un clasificador recapacitado o sugerir un nuevo entrenamiento. Esto requiere un conocimiento más profundo de cómo funcionan los clasificadores capacitados.

Después de una reformación, se evalúa el rendimiento del clasificador en los elementos con comentarios, así como con los elementos usados originalmente para entrenar al clasificador. 

- Para los modelos integrados, los elementos que se usan para entrenar al clasificador son los elementos que usa Microsoft para compilar el modelo.
- Para los modelos personalizados, los elementos usados en la formación original del clasificador son de los sitios que ha agregado para probar y revisar.

Comparamos los números de rendimiento en ambos conjuntos de elementos del clasificador recapacitado y publicado para proporcionar una recomendación sobre si había mejoras en la publicación. 

## <a name="see-also"></a>Vea también

- [Obtener información sobre los clasificadores capacitados](classifier-learn-about.md)
- [Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
