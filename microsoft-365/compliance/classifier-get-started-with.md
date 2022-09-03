---
title: Introducción a los clasificadores que se pueden entrenar
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
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: admindeeplinkDEFENDER
search.appverid:
- MOE150
- MET150
description: Un clasificador de Microsoft 365 es una herramienta que puede entrenar para reconocer diversos tipos de contenido al darle ejemplos a los que examinar. En este artículo se muestra cómo crear y entrenar un clasificador personalizado y cómo volver a entrenarlos para aumentar la precisión.
ms.openlocfilehash: 3dd74cd247c8709ce0974a52efd75893f02496f9
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67576415"
---
# <a name="get-started-with-trainable-classifiers"></a>Introducción a los clasificadores que se pueden entrenar

Un clasificador que se puede entrenar de Microsoft 365 es una herramienta que puede entrenar para reconocer varios tipos de contenido al darle ejemplos a los que examinar. Una vez entrenado, puede usarlo para identificar el elemento para la aplicación de etiquetas de confidencialidad de Office, directivas de cumplimiento de comunicaciones y directivas de etiquetas de retención.

La creación de un clasificador personalizado que se puede entrenar primero implica darle ejemplos que son seleccionados por el ser humano y que coinciden positivamente con la categoría. A continuación, una vez procesados, se prueba la capacidad de los clasificadores de predecir proporcionándole una combinación de muestras positivas y negativas. En este artículo se muestra cómo crear y entrenar un clasificador personalizado y cómo mejorar el rendimiento de clasificadores entrenables personalizados y clasificadores previamente entrenados a lo largo de su duración mediante el reentrenamiento.

Para obtener más información sobre los distintos tipos de clasificadores, consulte [Más información sobre los clasificadores que se pueden entrenar](classifier-learn-about.md).

Vea este vídeo para obtener un resumen rápido de la creación de un clasificador que se puede entrenar. Seguirá teniendo que leer este artículo completo para obtener los detalles.

</br>

[!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a>Requisitos previos

### <a name="licensing-requirements"></a>Requisitos de licencias

Los clasificadores son una característica de cumplimiento de Microsoft 365 E5 o E5. Debe tener una de estas suscripciones para poder usarlas.

### <a name="permissions"></a>Permisos

Para acceder a clasificadores en la interfaz de usuario: 

- el administrador global debe participar en el inquilino para crear clasificadores personalizados.
- El rol de administrador de cumplimiento es necesario para entrenar un clasificador.

Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:

- Escenario de directiva de etiqueta de retención: roles de administración de registros y administración de retención 
- Escenario de directiva de etiqueta de confidencialidad: Administrador de seguridad, Administrador de cumplimiento, Administrador de datos de cumplimiento
- Escenario de directiva de cumplimiento de comunicaciones: Insider Risk Management Administración, Supervisor Review Administrator 

> [!IMPORTANT]
> De forma predeterminada, solo el usuario que crea un clasificador personalizado puede entrenar y revisar las predicciones realizadas por ese clasificador.

## <a name="prepare-for-a-custom-trainable-classifier"></a>Preparación para un clasificador personalizado que se puede entrenar 

Es útil comprender lo que implica la creación de un clasificador personalizado que se puede entrenar antes de profundizar. 

### <a name="timeline"></a>Escala de tiempo

Esta escala de tiempo refleja una implementación de ejemplo de clasificadores entrenables.

![trainable-classifier-timeline.](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> La participación es necesaria la primera vez para los clasificadores que se pueden entrenar. Microsoft 365 tarda doce días en completar una evaluación de línea base del contenido de las organizaciones. Póngase en contacto con el administrador global para iniciar el proceso de participación.

### <a name="overall-workflow"></a>Flujo de trabajo general

Para obtener más información sobre el flujo de trabajo general de la creación de clasificadores entrenables personalizados, consulte [Flujo de proceso para crear clasificadores entrenables personalizados](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).

### <a name="seed-content"></a>Contenido de inicialización

Cuando quieras que un clasificador entrenado identifique de forma independiente y precisa un elemento como en una categoría específica de contenido, primero tienes que presentarlo con muchos ejemplos del tipo de contenido que se encuentran en la categoría. Esta alimentación de muestras al clasificador entrenable se conoce como *propagación*. Un humano selecciona el contenido de inicialización y se considera que representa la categoría de contenido.

> [!TIP]
> Debe tener al menos 50 muestras positivas y hasta 500. El clasificador entrenable procesará hasta los 500 ejemplos creados más recientes (por marca de fecha y hora creada por el archivo). Cuantos más ejemplos proporcione, más precisas serán las predicciones que realizará el clasificador.

### <a name="testing-content"></a>Pruebas de contenido

Una vez que el clasificador entrenable ha procesado suficientes ejemplos positivos para compilar un modelo de predicción, debe probar las predicciones que realiza para ver si el clasificador puede distinguir correctamente entre los elementos que coinciden con la categoría y los elementos que no. Para ello, seleccione otro conjunto más grande de contenido seleccionado por humanos que consta de ejemplos que deben pertenecer a la categoría y muestras que no lo harán. Debe probar con datos diferentes a los datos iniciales de inicialización que proporcionó primero. Una vez que los procesa, se recorren manualmente los resultados y se comprueba si cada predicción es correcta, incorrecta o no está segura. El clasificador que se puede entrenar usa estos comentarios para mejorar su modelo de predicción.

> [!TIP]
> Para obtener mejores resultados, tenga al menos 200 elementos en el conjunto de muestras de prueba con una distribución uniforme de coincidencias positivas y negativas.

## <a name="how-to-create-a-trainable-classifier"></a>Creación de un clasificador que se puede entrenar

1. Recopile entre 50 y 500 elementos de contenido de inicialización. Estos solo deben ser ejemplos que representen fuertemente el tipo de contenido que desea que el clasificador que se puede entrenar identifique positivamente como en la categoría de clasificación. Consulte [Extensiones de nombre de archivo rastreadas predeterminadas y tipos de archivo analizados en SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para conocer los tipos de archivo admitidos.

   > [!IMPORTANT]
   > Asegúrese de que los elementos del conjunto de inicialización son ejemplos **seguros** de la categoría. El clasificador que se puede entrenar crea inicialmente su modelo en función de lo que se haya inicializado con él. El clasificador supone que todas las muestras de inicialización son fuertes positivos y no tiene forma de saber si una muestra es una coincidencia débil o negativa con la categoría.

2. Coloque el contenido de inicialización en una carpeta de SharePoint Online dedicada solo a contener *el contenido de inicialización*. Anote la dirección URL del sitio, la biblioteca y la carpeta.

   > [!TIP]
   > Si crea un sitio y una carpeta nuevos para los datos de inicialización, espere al menos una hora para que esa ubicación se indexe antes de crear el clasificador entrenable que usará esos datos de inicialización.

3. Inicie sesión en portal de cumplimiento Microsoft Purview con el acceso al rol de administrador de seguridad o administrador de cumplimiento y abra <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a> o <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a> > **Datos clasificación**.

4. Elija la pestaña **Clasificadores entrenables** .

5. Elija **Crear clasificador entrenable**.

6. Rellene los valores adecuados para los `Name` campos y `Description` de la categoría de elementos que desea que identifique este clasificador entrenable.

7. Elija el sitio, la biblioteca y la dirección URL de carpeta de SharePoint Online para el sitio de contenido de inicialización del paso 2. Elija `Add`.

8. Revise la configuración y elija `Create trainable classifier`.

9. En un plazo de 24 horas, el clasificador entrenable procesará los datos de inicialización y creará un modelo de predicción. El estado del clasificador es `In progress` mientras procesa los datos de inicialización. Cuando el clasificador termina de procesar los datos de inicialización, el estado cambia a `Need test items`.

10. Ahora puede ver la página de detalles eligiendo el clasificador.

    > [!div class="mx-imgBorder"]
    > ![clasificador entrenable listo para las pruebas.](../media/classifier-trainable-ready-to-test-detail.png)

11. Recopile al menos 200 elementos de contenido de prueba (10 000 como máximo) para obtener los mejores resultados. Estos deben ser una combinación de elementos que son positivos fuertes, negativos fuertes y algunos que son un poco menos obvios en su naturaleza. Consulte [Extensiones de nombre de archivo rastreadas predeterminadas y tipos de archivo analizados en SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para conocer los tipos de archivo admitidos.

12. Coloque el contenido de prueba en una carpeta de SharePoint Online dedicada solo a contener *el contenido de prueba*. Anote la dirección URL del sitio, la biblioteca y la carpeta de SharePoint Online.

    > [!TIP]
    > Si crea un nuevo sitio y una carpeta para los datos de prueba, espere al menos una hora para que esa ubicación se indexe antes de crear el clasificador entrenable que usará esos datos de inicialización.

13. Elija `Add items to test`.

14. Elija el sitio, la biblioteca y la dirección URL de carpeta de SharePoint Online para el sitio de contenido de prueba del paso 12. Elija `Add`.

15. Para finalizar el asistente, elija `Done`. El clasificador que se puede entrenar tardará hasta una hora en procesar los archivos de prueba.

16. Cuando el clasificador entrenable haya terminado de procesar los archivos de prueba, el estado de la página de detalles cambiará a `Ready to review`. Si necesita aumentar el tamaño de la muestra de prueba, elija `Add items to test` y permita que el clasificador entrenado procese los elementos adicionales.

    > [!div class="mx-imgBorder"]
    > ![lista para revisar la captura de pantalla.](../media/classifier-trainable-ready-to-review-detail.png)

17. Elija `Tested items to review` la pestaña para revisar los elementos.

18. Microsoft 365 presentará 30 elementos a la vez. Revíselos y, en el `We predict this item is "Relevant". Do you agree?` cuadro, elija `Yes` o `No` `Not sure, skip to next item`. La precisión del modelo se actualiza automáticamente después de cada 30 elementos.

    > [!div class="mx-imgBorder"]
    > ![cuadro de elementos de revisión.](../media/classifier-trainable-review-detail.png)

19. Revise *al menos* 200 elementos. Una vez estabilizada la puntuación de precisión, la opción **de publicación** estará disponible y el estado del clasificador dirá `Ready to use`.

    > [!div class="mx-imgBorder"]
    > ![puntuación de precisión y listo para publicar.](../media/classifier-trainable-review-ready-to-publish.png)

20. Publique el clasificador.

21. Una vez publicado el clasificador estará disponible como condición en el [etiquetado automático de Office con etiquetas de confidencialidad](apply-sensitivity-label-automatically.md), [aplique automáticamente la directiva de etiquetas de retención en función de una condición](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) y en [Cumplimiento de comunicaciones](communication-compliance.md).
